# Airtable MVP build specification

This is the target data model for the ClinicFlow low-code MVP. Use fictitious demonstration records only in the portfolio base. Do not add real patient data unless an authorised clinic environment, consent process, access-control review, and privacy approval are in place.

## Tables

| Table | Primary field | Required fields | Purpose |
| --- | --- | --- | --- |
| Doctors | Doctor ID | Display name, specialty, active | Five-doctor clinic roster and schedule owner. |
| Availability slots | Slot ID | Doctor, start time, end time, status, appointment type | The source of bookable capacity. |
| Patients | Patient ID | First name, last initial, mobile number, reminder consent, opt-out date | Minimum data needed for a booking and reminder. |
| Appointments | Appointment ID | Patient, doctor, slot, appointment type, status, booked at, consent captured | Single system of record for bookings and outcomes. |
| Reminder log | Reminder ID | Appointment, channel, scheduled time, sent time, delivery status | Audit trail for the 24-hour and 2-hour reminder workflow. |
| UAT feedback | Feedback ID | Scenario, tester role, pass/fail, usability score, feedback | Pilot test evidence without patient data. |

## Field definitions

### Doctors

| Field | Airtable type | Rule |
| --- | --- | --- |
| Doctor ID | Single line text | Use `DOC-01` through `DOC-05`. |
| Display name | Single line text | Use a fictitious display name in the demo. |
| Specialty | Single select | General Medicine, Paediatrics, Dermatology, Cardiology, Orthopaedics. |
| Active | Checkbox | Only active doctors appear in the booking form. |

### Availability slots

| Field | Airtable type | Rule |
| --- | --- | --- |
| Slot ID | Formula | `Doctor ID & "-" & DATETIME_FORMAT({Start time}, "YYYYMMDD-HHmm")`. |
| Doctor | Link to Doctors | Required. |
| Start time | Date with time | Clinic local time. |
| End time | Formula or date with time | Start time plus configured duration/buffer. |
| Appointment type | Single select | New consultation, follow-up, procedure review. |
| Status | Single select | Available, locked, booked, blocked. |
| Booking lock expiry | Date with time | Clear stale locks with a Make scenario. |

### Patients

| Field | Airtable type | Rule |
| --- | --- | --- |
| Patient ID | Autonumber or formula | Use a non-clinical identifier in the demo. |
| First name | Single line text | Minimum necessary data. |
| Last initial | Single line text | Do not collect a full name in the portfolio dataset. |
| Mobile number | Phone number | Store only with explicit reminder consent. |
| Reminder consent | Checkbox | Required before any automated message is queued. |
| Consent captured at | Date with time | Required if consent is checked. |
| Consent channel | Single select | Web form, phone, front desk. |
| Opt-out date | Date with time | Suppresses future reminders immediately. |

### Appointments

| Field | Airtable type | Rule |
| --- | --- | --- |
| Appointment ID | Formula | `"APT-" & RECORD_ID()`. |
| Patient | Link to Patients | Required. |
| Doctor | Link to Doctors | Required. |
| Slot | Link to Availability slots | Required and unique for a confirmed booking. |
| Appointment type | Lookup or single select | Must agree with the selected slot. |
| Status | Single select | Pending, confirmed, checked in, attended, cancelled, no-show, reschedule requested. |
| Booked at | Created time | Booking timestamp. |
| Scheduled start | Lookup | From selected slot. |
| Outcome recorded at | Date with time | Required for attended, cancelled, and no-show outcomes. |
| Reminder eligible | Formula | Consent is true, no opt-out date, and status is confirmed. |

### Reminder log

| Field | Airtable type | Rule |
| --- | --- | --- |
| Reminder ID | Autonumber | Unique audit record. |
| Appointment | Link to Appointments | Required. |
| Reminder type | Single select | 24-hour or 2-hour. |
| Channel | Single select | WhatsApp, SMS. |
| Scheduled time | Date with time | Derived from appointment start. |
| Sent time | Date with time | Written by Make after send attempt. |
| Delivery status | Single select | Queued, sent, delivered, failed, suppressed. |
| Provider reference | Single line text | Provider message ID where available. |
| Failure reason | Long text | Keep non-sensitive diagnostic detail only. |

## Views

| View | Source table | Filter / grouping | User |
| --- | --- | --- | --- |
| Bookable slots | Availability slots | Active doctor, status = Available, future start time | Patient booking form / front desk |
| Front desk today | Appointments | Scheduled date = today; group by doctor and status | Front desk |
| Action queue | Appointments | Reschedule requested or consent missing or reminder failed | Front desk |
| Doctor schedule | Appointments | Filtered by doctor; ordered by scheduled start | Doctor / front desk |
| Reminder queue | Reminder log | Scheduled time in next 24 hours and delivery status = Queued | Make scenario |
| No-show report | Appointments | Outcomes only; grouped by doctor and appointment type | PM / product owner |

## Make scenarios

1. **Booking confirmation:** trigger when an appointment changes to Confirmed; mark slot Booked; send a generic confirmation only when reminder consent is recorded; write the provider reference to Reminder log.
2. **24-hour reminder:** every 15 minutes, find eligible confirmed appointments starting in 23–25 hours; create/send one 24-hour reminder; update delivery status.
3. **2-hour reminder:** every 15 minutes, find eligible confirmed appointments starting in 1.5–2.5 hours; create/send one 2-hour reminder; update delivery status.
4. **Failure fallback:** when WhatsApp delivery fails, create an SMS attempt only if consent permits the fallback channel; otherwise mark Suppressed.
5. **Stale slot lock cleanup:** every 15 minutes, return locked slots with an expired lock to Available when no appointment exists.

## Acceptance checks

- A confirmed appointment cannot reuse a booked slot.
- An opt-out prevents new reminder attempts.
- Every send attempt creates exactly one Reminder log record.
- A front-desk user can check in, cancel, reschedule, or mark no-show without editing patient consent.
- No-show rate equals no-shows divided by attended plus no-shows; cancelled appointments are excluded from the denominator.
- The portfolio base contains no real patient data.

## Illustrative baseline and targets

The portfolio currently uses a **simulated** booking-time baseline of **6 minutes 18 seconds** and an **illustrative** no-show baseline of **18.0% (11 of 61 appointments)**. The target is booking completion in 2 minutes 30 seconds or less and a pilot no-show rate of 12% or lower. Replace these planning assumptions only with dated, anonymised observations.
