# Communications, quality, and change control

## Communications plan

| Audience | Information | Cadence / format | Owner |
|---|---|---|---|
| Sponsor | RAG, budget, EV, decisions needed | Weekly one-page report | PM |
| Product owner | Backlog, demo, acceptance decisions | Refinement + sprint review | PM |
| Delivery team | Sprint goal, blockers, test results | Weekly check-in and Jira updates | PM |
| Front desk | Workflow changes, training, pilot support | Interview, demo, training | PM |

## Quality plan

Testing uses fictional records only. QA maintains test cases for booking, double-booking, consent, reminder scheduling, cancellation/reschedule, dashboard filters, access roles, reporting calculations, and outage fallback. Defects are logged in Jira with severity and retested after correction. UAT uses representative front-desk and doctor tasks. Target: ≥95% UAT pass rate and SUS ≥75.

## Change-control process

1. Requester logs a change with reason, expected value, and affected requirement.
2. PM estimates scope, schedule, cost, risk, and quality impact with Dev/QA input.
3. Product owner recommends approve/defer/reject; sponsor approves changes affecting budget baseline, go-live, privacy posture, or an agreed objective.
4. PM updates the decision/change log and backlog; no work begins until status is approved.

Changes within a sprint are normally deferred to refinement unless required to correct a critical defect, privacy issue, or release blocker.
