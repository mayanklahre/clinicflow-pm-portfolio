# Airtable / Make solution design

## MVP architecture

`Booking form → Airtable appointment base → Make scenario → WhatsApp/SMS provider → status written back to Airtable → front-desk dashboard / no-show report`

## Airtable tables

| Table | Key fields | Purpose |
|---|---|---|
| Doctors | Doctor ID, name, active | Staff reference |
| Availability | Availability ID, doctor, date, start/end, slot length, status | Generates/selects available slots |
| Patients (pilot) | Patient ID, display name, contact channel, consent, consent timestamp | Minimum contact data only |
| Appointments | Appointment ID, patient, doctor, start, status, reminder state, audit note | Central operational record |
| Reminder log | Reminder ID, appointment, channel, scheduled/sent time, delivery status | Traceable reminder events |
| Exceptions | Doctor, date, unavailable window, reason | Overrides recurring availability |

## Automation safeguards

- Validate that the selected slot is still available immediately before confirmation.
- Change slot status to `held` then `booked` in the same controlled sequence; show a retry/error message if it is no longer available.
- Send reminders only where consent is `Yes` and appointment status is `Booked` or `Confirmed`.
- Store delivery result, never message body containing sensitive health details.
- Use generic reminder copy: “ClinicFlow reminder: you have an appointment at [time]. Reply/contact the clinic to change it.”
- Restrict edit access by role; use a paper fallback during outage and reconcile with an audit note.

## Data and consent

Prototype uses fictional data. A live pilot requires privacy-adviser review, final consent wording, retention/deletion decision, staff access list, approved provider terms, and a clear opt-out/change-contact route. Do not store diagnosis, clinical notes, payment data, or government identifiers.
