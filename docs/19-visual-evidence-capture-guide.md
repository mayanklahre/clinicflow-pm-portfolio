# Visual evidence capture guide

This guide uses fictional portfolio data only. Do not capture real patient names, phone numbers, emails, clinical notes, or clinic identifiers. Do not make an Airtable or Figma link public merely to take a screenshot.

## Required screenshots

Save each as a PNG in `assets/` using the filename shown below.

| File | What must be visible | How to capture |
| --- | --- | --- |
| `assets/jira-backlog.png` | Project name ClinicFlow, `CLIN` issue keys, and the three sprint headers/counts | Open the CLIN backlog; expand the three sprints; take one browser screenshot. |
| `assets/airtable-bookable-slots.png` | Base title showing illustrative data, Bookable slots view, and only fictional slot IDs | Open Availability slots → Bookable slots. Do not open Share. Screenshot the grid. |
| `assets/airtable-test-appointment.png` | `TEST-BOOKING-20261018`, selected fictional slot, Confirmed status, and consent tick | Complete the manual retest below, open the appointment record, then screenshot its detail panel. |
| `assets/airtable-reminder-queue.png` | Reminder log entry marked `Queued` and `Test only — not sent` | Create the test-only reminder-log record; screenshot the entry. |
| `assets/airtable-no-show-report.png` | A filtered no-show view containing fictional data only | Filter Appointments to Status = No-show; screenshot the view. |
| `assets/figma-wireframes.png` | File name and the overview of the eight ClinicFlow frames | Zoom to show all frames; screenshot. |
| `assets/make-disabled-scenario.png` | Scenario name, Airtable Watch records module, and inactive toggle | Open Make scenario and ensure the toggle is off; screenshot. |

## Complete the Airtable manual retest

1. In **Appointments**, open `TEST-BOOKING-20261018`.
2. Set **Patient** to a fictional `PAT-ILL-*` record; set **Doctor** to the matching illustrative doctor.
3. Set **Appointment type**, **Scheduled start**, **Status = Confirmed**, **Booking channel = Online**, and tick **Consent verified**.
4. Set **Slot** to `SLOT-ILL-02`.
5. Open **Availability slots** → Grid view, find `SLOT-ILL-02`, and change **Slot status** from `Available` to `Booked`.
6. In **Reminder log**, add one record: reference `REM-TEST-20261018`, appointment `TEST-BOOKING-20261018`, channel `Test only`, status `Queued`, note `Test only — not sent`. Do not connect or invoke a messaging provider.
7. Return to the appointment, link the new reminder-log record, and verify that no reminder-sent checkbox is ticked.
8. Capture the three Airtable screenshots specified above.

## Private-window verification

1. Open a new private/incognito browser window.
2. Paste the Airtable link. If it requests sign-in, record “owner-only access; no public-share link”. Do not change sharing settings.
3. Paste the Figma link. If it requests sign-in, record the same result.
4. If either opens without a sign-in prompt, check only that it contains fictional data; then close the private window. Do not change permissions.

## Add screenshots to the repository

1. Create an `assets` folder in the local repository.
2. Copy only the reviewed PNGs above into it.
3. Add the following links to `README.md`: Jira backlog, Airtable bookable slots, test appointment, reminder queue, no-show report, Figma overview, and Make disabled scenario.
4. Commit with a message such as `Add fictional MVP evidence screenshots`.
