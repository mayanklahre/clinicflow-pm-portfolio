# Risk register

Review weekly. Score = likelihood × impact (each 1–5). Status reflects the project baseline and must be updated with dated evidence.

| ID | Risk | L | I | Score | Trigger | Mitigation | Owner | Status |
|---|---|---:|---:|---:|---|---|---|---|
| R1 | Front-desk staff resist the system | 4 | 4 | 16 | Negative interview feedback or low training attendance | Involve staff in design; pilot; train | PM | Open |
| R2 | Simultaneous booking causes double booking | 3 | 4 | 12 | Duplicate doctor/start-time test fails | Slot lock; unique check; concurrency test | Dev | Open |
| R3 | Scope creep into billing or records | 4 | 3 | 12 | Request adds out-of-scope capability | MoSCoW; change-request form | PM | Open |
| R4 | Team availability falls | 4 | 3 | 12 | Missed commitment or planned absence | Sprint-3 buffer; cross-train | PM | Open |
| R5 | Internet/power outage | 3 | 4 | 12 | Connectivity interruption during pilot | Paper fallback; reconcile later | Dev | Open |
| R6 | Patient-data breach/non-compliance | 2 | 5 | 10 | Consent/access review fails | Minimum data; consent; access control; privacy review | Privacy adviser | Open |
| R7 | SMS provider fails or changes price | 3 | 3 | 9 | Delivery failures/cost increase | Compare providers; fallback channel | PM | Open |
| R8 | Paid-service budget overrun | 2 | 3 | 6 | Forecast exceeds baseline + contingency | 10–15% contingency; monthly review | PM | Open |

Risk response is escalated to the sponsor at score ≥15, on any privacy incident, or when mitigation requires a budget/scope decision.
