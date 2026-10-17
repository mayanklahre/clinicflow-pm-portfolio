# Product requirements document

## Product vision

Give patients a simple way to request an appointment while giving staff and doctors one dependable view of availability, reminder status, and missed appointments.

## Users and primary flows

| User | Need | Flow |
|---|---|---|
| Patient | Book a suitable appointment and receive reminders | Select doctor/service → choose open slot → enter minimum contact data → consent → receive confirmation/reminder |
| Front-desk staff | Find, create, move, cancel, and check in appointments quickly | Open dashboard → search/date filter → update status or create booking |
| Doctor | Keep availability accurate | Set recurring availability / exception → review own schedule |
| PM / owner | Understand no-shows and adoption | Open report → filter date/doctor → export aggregate counts |

## MoSCoW priorities

| Priority | Requirement |
|---|---|
| Must | Availability slots, booking form, conflict check, confirmation, consent capture, staff dashboard, doctor schedules, reminder status, no-show report, role-based access, test/UAT evidence |
| Should | Reschedule/cancel links, WhatsApp-to-SMS fallback, daily summary, usability survey, exportable report |
| Could | Waitlist, multilingual copy, calendar overlay, satisfaction follow-up |
| Won't (MVP) | Payments, billing, medical records, clinical advice, EHR integration, production patient database |

## Functional requirements

1. The system shall display only future slots marked available for the selected doctor and appointment type.
2. A patient shall provide name, contact channel, and consent before confirmation.
3. The system shall prevent two confirmed bookings for the same doctor and start time.
4. Staff shall create, search, reschedule, cancel, check in, and mark no-shows.
5. Doctors or authorised staff shall maintain recurring availability and exceptions.
6. The system shall queue reminders at 24 hours and 2 hours before an appointment where consent exists.
7. Staff shall see appointment date, doctor, status, reminder status, and contact preference in one dashboard.
8. The report shall show bookings, attended, cancelled, and no-show counts/rates by date and doctor.
9. The system shall retain a change/audit note for staff edits during the pilot.

## Non-functional requirements

| Area | Requirement |
|---|---|
| Privacy | Collect minimum data; consent wording and withdrawal route; restrict staff access; use fictional data until approved pilot. |
| Availability | During outages, staff use the paper fallback and reconcile later. |
| Performance | Dashboard and booking views should load in normal browser use within 3 seconds for pilot-sized data. |
| Usability | UAT participants complete common booking/front-desk tasks with ≥95% pass rate and SUS ≥75. |
| Accessibility | Plain language, visible error messages, keyboard-friendly form where supported. |

## Acceptance and release criteria

A story is ready when it has acceptance criteria and an estimate. It is done only when peer-reviewed, tested, merged/configured, evidence is linked, and product-owner acceptance is recorded where applicable. The MVP release requires no open critical defects, privacy approval, UAT pass rate ≥95%, training completion, fallback materials, and sponsor approval.
