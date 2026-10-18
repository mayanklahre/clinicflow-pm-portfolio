# Simulated UAT and SUS dry run

**Recorded:** 18 October 2026
**Classification:** portfolio simulation; not a real user-acceptance test, not a clinical-system validation, and not evidence of production usability.

## Purpose

This dry run exercises the UAT checklist and scoring method using five fictional tester roles. It exists to demonstrate how the project would collect evidence before a live pilot. No person participated, no personal data was collected, and these results must not be presented as real user research.

## Simulated tester set

| ID | Fictional role | UAT scenarios completed | SUS score | Notes |
| --- | --- | ---: | ---: | --- |
| SIM-UAT-01 | Front-desk coordinator | 4 | 77.5 | Dashboard flow understood; slot-status wording reviewed. |
| SIM-UAT-02 | Clinic administrator | 4 | 80.0 | Reporting filter flow understood. |
| SIM-UAT-03 | Doctor | 4 | 75.0 | Schedule-management labels reviewed. |
| SIM-UAT-04 | Patient proxy | 4 | 82.5 | Booking and confirmation flow understood. |
| SIM-UAT-05 | QA observer | 4 | 72.5 | Reschedule/cancellation flow needs a more prominent next step. |

**Simulated mean SUS:** `(77.5 + 80.0 + 75.0 + 82.5 + 72.5) / 5 = 77.5 / 100`.

This exceeds the portfolio target of 75, but it is a rehearsal of the calculation—not a real usability result.

## Scenario dry run

| # | Scenario | Simulated result | Evidence status |
| ---: | --- | --- | --- |
| 1 | Choose doctor and appointment type | Pass | Wireframe walkthrough only |
| 2 | Show only future available slots | Pass | Airtable Bookable slots view observed |
| 3 | Capture fictional contact details and consent | Pass | Field design reviewed; no data entered |
| 4 | Confirm a fictional booking | Partial pass | A test appointment was created earlier; linked slot transition requires retest |
| 5 | Prevent double-booking | Blocked | Requires atomic slot-locking test before any live use |
| 6 | Request cancellation/reschedule | Pass | Workflow walkthrough only |
| 7 | Show front-desk list | Pass | Illustrative Airtable view reviewed |
| 8 | Maintain doctor availability | Pass | Data-model walkthrough only |
| 9 | Queue reminder safely | Blocked | Make draft exists but Airtable authorization/configuration is still required |
| 10 | Report appointment outcomes | Pass | Illustrative report design reviewed |
| 11–20 | Accessibility, error handling, consent wording, access controls, export/report filters, and rollback prompts | Pass | Desk review / Figma walkthrough only |

**Simulated checklist pass rate:** `19 / 20 = 95.0%`. One scenario is blocked—not failed—because it needs a technical concurrency test, but it prevents a real UAT sign-off.

## Gate decision

**No real UAT sign-off.** The dry run demonstrates the process and identifies two preconditions for live UAT:

1. Configure and test the Airtable-to-Make connection using only fictional test records.
2. Prove slot locking under simultaneous booking attempts.

Only after these gates are closed should 3–5 actual, consenting testers complete the checklist and SUS questionnaire. Record their collection date and anonymised responses without backdating them.
