# Jira setup and prioritised backlog

Create a Scrum project named **ClinicFlow** with key **CLIN**. Add components: `Booking`, `Reminders`, `Dashboard`, `Schedules`, `Reporting`, `Privacy`, `Release`. Add version `MVP Pilot 1.0`. Use the workflow `Backlog → Selected → In Progress → In Review → Testing → Done`. Dashboard gadgets: burndown, velocity, created versus resolved, and roadmap.

## Epics

| Epic | Component | Outcome |
|---|---|---|
| Online Booking | Booking | Patient can select and reserve an available slot |
| Reminders | Reminders | Consented patient receives traceable reminders |
| Front-Desk Dashboard | Dashboard | Staff can manage appointment flow |
| Doctor Schedules | Schedules | Availability and exceptions control slots |
| No-Show Reports | Reporting | Owner can see missed-appointment trend |
| Privacy and Consent | Privacy | Minimum data and access controls are applied |
| Go-Live | Release | Pilot is trained, accepted, and recoverable |

## Stories (35)

| # | Epic | Story / acceptance criteria | Priority | Points | Sprint |
|---:|---|---|---|---:|---|
| 1 | Online Booking | As a patient, I select doctor and appointment type. **AC:** only active doctors/types appear. | Must | 3 | 1 |
| 2 | Online Booking | As a patient, I see future available slots. **AC:** unavailable/past slots do not show. | Must | 5 | 1 |
| 3 | Online Booking | As a patient, I enter minimum contact details. **AC:** required fields validate clearly. | Must | 3 | 1 |
| 4 | Online Booking | As a patient, I receive booking confirmation. **AC:** appointment ID, time, doctor, and change route are shown. | Must | 3 | 1 |
| 5 | Online Booking | As the system, I prevent duplicate confirmed slots. **AC:** concurrent attempt gets conflict message; only one booking remains. | Must | 8 | 1 |
| 6 | Online Booking | As staff, I create a booking for a phone caller. **AC:** uses same slot rules and audit note. | Must | 5 | 1 |
| 7 | Online Booking | As a patient, I request cancellation/reschedule. **AC:** request updates status or creates staff task. | Should | 5 | 2 |
| 8 | Privacy and Consent | As a patient, I see reminder consent language. **AC:** unchecked consent prevents reminder queue. | Must | 3 | 1 |
| 9 | Privacy and Consent | As staff, I record consent timestamp/channel. **AC:** value is visible in record and immutable in audit log. | Must | 3 | 1 |
| 10 | Privacy and Consent | As an admin, I limit data access by role. **AC:** test accounts cannot edit restricted fields. | Must | 5 | 2 |
| 11 | Privacy and Consent | As a patient, I can opt out of reminders. **AC:** future reminder jobs are cancelled and recorded. | Must | 3 | 2 |
| 12 | Doctor Schedules | As staff, I set recurring doctor availability. **AC:** valid slot pattern is created for a selected doctor. | Must | 5 | 1 |
| 13 | Doctor Schedules | As staff, I add time-off exception. **AC:** overlapping slots are hidden/blocked. | Must | 3 | 2 |
| 14 | Doctor Schedules | As a doctor, I view my own schedule. **AC:** date view filters to selected doctor accurately. | Should | 3 | 2 |
| 15 | Doctor Schedules | As staff, I set slot duration/buffer. **AC:** generated slots follow configured interval. | Should | 3 | 2 |
| 16 | Front-Desk Dashboard | As staff, I view today's appointments. **AC:** date, doctor, status and reminder state are visible. | Must | 5 | 2 |
| 17 | Front-Desk Dashboard | As staff, I search an appointment. **AC:** search by display name, date or appointment ID returns matching result. | Must | 3 | 2 |
| 18 | Front-Desk Dashboard | As staff, I check in a patient. **AC:** status changes to Attended/Checked-in and audit note records actor/date. | Must | 3 | 2 |
| 19 | Front-Desk Dashboard | As staff, I mark no-show/cancelled. **AC:** valid status change updates report denominator correctly. | Must | 3 | 2 |
| 20 | Front-Desk Dashboard | As staff, I see attention flags. **AC:** unconfirmed/today/failed-reminder items are distinguishable. | Should | 3 | 3 |
| 21 | Reminders | As the system, I queue a 24-hour reminder. **AC:** eligible booked appointment produces one scheduled log entry. | Must | 5 | 2 |
| 22 | Reminders | As the system, I queue a 2-hour reminder. **AC:** eligible appointment receives correct timing without duplicate send. | Must | 5 | 2 |
| 23 | Reminders | As staff, I see delivery state. **AC:** queued/sent/failed state and timestamp are stored. | Must | 3 | 2 |
| 24 | Reminders | As the system, I use fallback channel. **AC:** failed preferred channel creates configured fallback/manual follow-up task. | Should | 5 | 3 |
| 25 | Reminders | As staff, I use approved generic copy. **AC:** message contains no clinical detail and includes change route. | Must | 2 | 2 |
| 26 | No-Show Reports | As product owner, I see bookings/attended/cancelled/no-shows by period. **AC:** totals reconcile to appointments. | Must | 5 | 3 |
| 27 | No-Show Reports | As product owner, I filter report by doctor. **AC:** result changes correctly and total is traceable. | Must | 3 | 3 |
| 28 | No-Show Reports | As product owner, I see no-show rate. **AC:** formula is no-shows ÷ completed outcomes; zero denominator shows n.a. | Must | 3 | 3 |
| 29 | No-Show Reports | As PM, I export aggregate pilot results. **AC:** export contains no contact data. | Should | 3 | 3 |
| 30 | No-Show Reports | As PM, I compare baseline/target/pilot outcome. **AC:** illustrative baseline is clearly labelled until replaced. | Should | 2 | 3 |
| 31 | Go-Live | As QA, I execute functional/regression tests. **AC:** evidence linked; no critical open defect. | Must | 5 | 3 |
| 32 | Go-Live | As UAT participant, I complete workflow checklist. **AC:** pass/fail, defect and SUS response captured. | Must | 3 | 3 |
| 33 | Go-Live | As PM, I train front desk. **AC:** attendance and practice completion recorded. | Must | 3 | 3 |
| 34 | Go-Live | As PM, I run cutover checklist. **AC:** backup, access, provider, fallback and approval checks complete. | Must | 3 | 3 |
| 35 | Go-Live | As sponsor, I approve pilot/rollback readiness. **AC:** dated go/no-go decision is recorded. | Must | 2 | 3 |

**Planned capacity:** Sprint 1 = 45 points, Sprint 2 = 50 points, Sprint 3 = 45 points. Treat this as a planning estimate. Reforecast after each sprint using actual velocity.
