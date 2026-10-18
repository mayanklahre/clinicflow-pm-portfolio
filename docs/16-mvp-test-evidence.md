# ClinicFlow MVP test evidence

> **Integrity note:** This record describes illustrative, fictional-data tests performed on 17 and 18 October 2026. It is not a production release, clinical trial, patient booking, or evidence that messages were sent.

## Test objective

Verify that the Airtable prototype can represent the core booking workflow using fictional records: identify an available slot, create a confirmed online appointment, link it to a patient/slot, and queue—not send—a reminder record.

## Test data and safety boundary

| Item | Value |
|---|---|
| Environment | ClinicFlow Airtable illustrative portfolio base |
| Patient data | Fictional Airtable test record only; no real patient information used |
| Candidate slot | `SLOT-ILL-02` |
| Test appointment references | `TEST-BOOKING-20261017`; manual-retest record `TEST-BOOKING-20261018` |
| Message sending | Not attempted; no WhatsApp or SMS message sent |
| Automation platform | Not yet configured; Make sign-in/build is pending |

## Result

| Test step | Expected result | Actual result | Status |
|---|---|---|---|
| Open Bookable slots | Only records with `Slot status = Available` are visible | Seven availability records displayed | Pass |
| Create illustrative appointment | Appointment is created with a unique reference and fictional link data | `TEST-BOOKING-20261017` and `TEST-BOOKING-20261018` were created in Appointments; the latter was created manually on 18 October 2026 | Pass for record creation only |
| Link selected slot and mark it Booked | Appointment links to `SLOT-ILL-02`; slot changes from Available to Booked | On 18 October, `TEST-BOOKING-20261018` was linked to `SLOT-ILL-02` and the slot status was changed to `Booked` | Pass (manual retest) |
| Queue test reminder | A linked reminder entry is created with status Queued and “not sent” note | `REM-TEST-20261018` was linked to the appointment with type `24 hours`, status `Queued`, blank channel/provider fields, and the note “TEST ONLY — NOT SENT”. The base currently offers only WhatsApp/SMS channel options, so no channel was selected rather than misrepresenting a live route. | Pass (manual retest; no-send) |
| Send a message | No message is sent | No send action was configured or attempted | Pass (safety control) |

## Findings and follow-up

1. The Bookable-slots filter, appointment creation, linked-slot update, and queued no-send reminder record worked with fictional data in a manual retest.
2. The Airtable Channel field currently offers only WhatsApp and SMS. Leave it blank for test-only reminders until a distinct `Test only` option is added; this avoids falsely recording a live message channel.
3. Before pilot, add an acceptance test for atomic slot locking: a slot must not remain visible as bookable once an appointment is confirmed, and a second attempt must be rejected.
4. Make remains unconnected. Build it only with a disabled/no-send or sandbox route first; do not connect a live WhatsApp/SMS provider until consent, cost, and privacy decisions are approved.

## Screenshot checklist

Capture the following from the completed manual retest; show only illustrative records:

- Bookable slots: one before and one after the selected slot changes to Booked.
- Appointments: the `TEST-BOOKING-20261018` record with its fictional links and Confirmed status.
- No-show report: filtered `Status = No-show` view.
- Front-desk today: appointments sorted by scheduled start.
- Figma overview: all eight frames visible.

## Retest acceptance criteria

The core manual workflow is evidenced for criteria 1–3. It may be recorded as a complete booking-control pass only when all four conditions are visible in the system:

1. A new appointment has a fictional patient, doctor, slot, scheduled time, Online channel, Confirmed status, and consent check.
2. The linked slot is `Booked` and no longer appears in Bookable slots.
3. A `Queued` reminder-log row is linked to the appointment and is explicitly labelled test-only/not sent.
4. A second attempt to reserve the same slot is prevented or raises an unambiguous conflict.

