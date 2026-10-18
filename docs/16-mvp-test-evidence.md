# ClinicFlow MVP test evidence

> **Integrity note:** This record describes an illustrative, fictional-data test performed on 17 October 2026. It is not a production release, clinical trial, patient booking, or evidence that messages were sent.

## Test objective

Verify that the Airtable prototype can represent the core booking workflow using fictional records: identify an available slot, create a confirmed online appointment, link it to a patient/slot, and queue—not send—a reminder record.

## Test data and safety boundary

| Item | Value |
|---|---|
| Environment | ClinicFlow Airtable illustrative portfolio base |
| Patient data | Fictional Airtable test record only; no real patient information used |
| Candidate slot | `SLOT-ILL-02` |
| Test appointment reference | `TEST-BOOKING-20261017` |
| Message sending | Not attempted; no WhatsApp or SMS message sent |
| Automation platform | Not yet configured; Make sign-in/build is pending |

## Result

| Test step | Expected result | Actual result | Status |
|---|---|---|---|
| Open Bookable slots | Only records with `Slot status = Available` are visible | Seven availability records displayed | Pass |
| Create illustrative appointment | Appointment is created with a unique reference and fictional link data | `TEST-BOOKING-20261017` was created in Appointments | Partial pass |
| Link selected slot and mark it Booked | Appointment links to `SLOT-ILL-02`; slot changes from Available to Booked | Airtable’s AI record action created the appointment but did not reliably complete the linked-slot update | Blocked / retest manually |
| Queue test reminder | A linked reminder entry is created with status Queued and “not sent” note | Not created during the same action | Blocked / retest manually |
| Send a message | No message is sent | No send action was configured or attempted | Pass (safety control) |

## Findings and follow-up

1. The Bookable slots filter and appointment-record creation both worked with fictional data.
2. The linked record update must be performed and verified as a separate manual test. This is an important MVP limitation, not something to hide in the case study.
3. Before pilot, add an acceptance test for atomic slot locking: a slot must not remain visible as bookable once an appointment is confirmed.
4. Build the Make reminders only after signing in, using a test record and a disabled/no-send or sandbox route first. Do not connect a live WhatsApp/SMS provider until the consent, cost, and privacy approval decisions are complete.

## Screenshot checklist

Capture the following after the manual retest; show only illustrative records:

- Bookable slots: one before and one after the selected slot changes to Booked.
- Appointments: the `TEST-BOOKING-20261017` record with its fictional links and Confirmed status.
- No-show report: filtered `Status = No-show` view.
- Front-desk today: appointments sorted by scheduled start.
- Figma overview: all eight frames visible.

## Retest acceptance criteria

The booking workflow may be recorded as passed only when all four conditions are visible in the system:

1. A new appointment has a fictional patient, doctor, slot, scheduled time, Online channel, Confirmed status, and consent check.
2. The linked slot is `Booked` and no longer appears in Bookable slots.
3. A `Queued` reminder-log row is linked to the appointment and is explicitly labelled test-only/not sent.
4. A second attempt to reserve the same slot is prevented or raises an unambiguous conflict.

