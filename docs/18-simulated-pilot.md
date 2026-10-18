# Simulated limited pilot dry run

**Recorded:** 18 October 2026
**Classification:** fictional-data rehearsal; not a clinic pilot, not patient activity, and not a claim of operational benefit.

## Purpose and safety boundary

This is a controlled scenario test of the pilot measurement approach. It uses invented bookings and invented appointment outcomes only. No clinic, clinician, patient, phone number, WhatsApp/SMS message, or personal data was involved. The Make scenario remains inactive and no message was sent.

## Simulated pilot design

| Item | Dry-run value |
| --- | --- |
| Duration | One fictional test day |
| Scope | Ten fictional appointment attempts across two fictional doctors |
| Booking channel | Airtable MVP walkthrough |
| Reminder channel | Queue-only design; no provider connected and no messages sent |
| Success gates | No duplicate confirmed slots; all fictional data visible in dashboard/report; no live data or messaging |
| Stop condition | Any slot conflict, consent/access issue, or unexpected real-data exposure |

## Fictional measurement output

| Metric | Illustrative baseline | Simulated output | Interpretation |
| --- | ---: | ---: | --- |
| Average booking time | 6:18 from five simulated observations | 2:15 across ten fictional walkthroughs | Demonstrates the calculation method only; not a measured improvement. |
| Confirmed appointments | N/A | 8 of 10 fictional attempts | Two attempts were intentionally routed to cancellation/no-show test paths. |
| No-shows | 18.0% hypothetical baseline | 1 / 10 = 10.0% fictional outcome | Not comparable with real operations and not a performance claim. |
| Reminder messages sent | N/A | 0 | Required safety outcome: the workflow was not connected to a provider. |
| Duplicate confirmed slots | N/A | 0 observed in sequential walkthroughs | Insufficient evidence; concurrent-booking test remains mandatory. |

## Findings and decision

The dry run confirms that the KPI table, outcome categories, and stop conditions are usable for a future pilot. It does **not** authorise a live pilot. The apparent 4:03 booking-time reduction and 8-point no-show-rate difference are fictional scenario outputs and must never be presented as achieved results.

## Required before a live, consented pilot

1. Complete a privacy/consent review and access-control check.
2. Obtain sponsor and product-owner approval for a defined pilot period.
3. Connect Make to Airtable with a test-only configuration, then test the reminder queue without a live provider.
4. Prove atomic slot locking with simultaneous-booking tests.
5. Collect a measured baseline and real pilot data with stated dates, sample sizes, and denominators.
6. Document cutover, rollback, support owner, and data-retention decisions.
