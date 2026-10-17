# UAT, cutover, rollback, and training

## UAT acceptance checklist

| Check | Evidence | Acceptance |
|---|---|---|
| Booking creates one appointment | Test case + screenshot | Pass |
| Duplicate slot is rejected | Concurrency test evidence | Pass |
| Consent gates reminders | Test record with/without consent | Pass |
| Reminder is queued and logged | Reminder log | Pass |
| Staff can search/update status | UAT task result | Pass |
| Doctor exception hides slot | UAT task result | Pass |
| No-show rate formula is correct | Recalculated sample | Pass |
| Outage fallback is understood | Training acknowledgment | Pass |

Product owner signs only when UAT pass rate is ≥95%, critical defects are closed, and privacy review is complete.

## Cutover plan

1. Confirm approved pilot cohort and fictional/demo data is removed where required.
2. Snapshot Airtable configuration and export a backup.
3. Confirm provider credits, approved message copy, Make scenario off/on state, and staff access.
4. Train staff, distribute one-page quick guide, and perform a dry run.
5. Open a limited pilot window; monitor booking/reminder logs daily.

## Rollback plan

Pause the Make scenario and booking form, tell staff to use the paper/phone process, preserve logs for review, restore the approved Airtable configuration if needed, and notify sponsor/product owner. Restart only after the root cause, test evidence, and go/no-go approval are recorded.

## Training plan

30-minute session: purpose and privacy (5 min), dashboard/booking walkthrough (10 min), create/change/cancel/check-in practice (10 min), outage fallback and questions (5 min). Attendance, completion and questions are recorded in the hypercare log.
