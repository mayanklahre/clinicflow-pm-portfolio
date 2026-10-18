# ClinicFlow — project management case study

> **Portfolio disclosure:** ClinicFlow is a self-initiated, low-code portfolio project. It is not a paid client engagement, does not contain real patient information, and has not been deployed in a live clinic. All baseline values and test records described below are illustrative planning assumptions unless explicitly replaced with dated, anonymised field observations.

## At a glance

| Item | Summary |
|---|---|
| Problem | Phone-only booking and manual front-desk coordination can lengthen booking time, obscure availability, and leave missed appointments unaddressed. |
| Product | A low-code MVP for availability, booking, consent-based reminders, front-desk coordination, doctor schedules, and no-show reporting. |
| Context | A five-doctor outpatient-clinic scenario. |
| My role | Project manager: project framing, requirements, prioritisation, backlog design, delivery controls, risk management, UAT planning, and portfolio evidence. |
| Delivery approach | Hybrid: up-front charter, feasibility, budget and controls; then three two-week Scrum sprints. |
| Planned duration | 3 August–11 October 2026. Portfolio artefacts created after those dates are labelled as planning or retrospective material; nothing is backdated. |
| MVP stack | Airtable data layer and dashboard; Make for future test-only automation; WhatsApp/SMS provider comparison; Figma wireframes; Jira delivery board. |

## The problem I chose

In this scenario, patients call the clinic to make or change appointments. The front desk must find an appropriate doctor and time, collect contact information, and keep a manually coordinated schedule current. Without a clear reminder workflow, clinic capacity can be lost to non-attendance.

The project was deliberately limited to an operational MVP. Payments, clinical records, prescriptions, diagnosis, and EHR integration were excluded. That made the scope deliverable within a ten-week student/team portfolio setting and avoided handling real health information.

## Evidence approach and baseline

Before a real pilot, I defined the evidence that would be needed and designed the portfolio to be transparent about its status.

| Measure | Illustrative planning value | Target | How it will be validated |
|---|---:|---:|---|
| Phone booking time | 6:18 average over five simulated observations | Online booking at or below 2:30 | Time 5–10 anonymised real bookings; record start/end consistently. |
| No-show rate | 11 no-shows / 61 appointments = 18.0% hypothetical sample | At or below 12.0% in a defined pilot period | Use a fixed denominator and exclude pre-cancelled appointments. |
| UAT pass rate | Not yet measured | At least 95% | Scenario-based UAT checklist with observed pass/fail results. |
| Usability | Not yet measured | SUS at least 75/100 | Anonymous feedback form after UAT. |

The numbers are plausible working assumptions for planning, not claims about a real clinic. The first next-step evidence collection pack asks for 5–10 booking durations, appointment/no-show totals for a defined period, and anonymous notes from 2–3 front-desk interviews. No names, patient details, call recordings, or contact information are required.

## What I delivered

### 1. Delivery governance

- Charter, business case, stakeholder register, feasibility check, RACI, WBS, schedule, budget baseline, and communication plan.
- Decision, change, issue, and assumption logs, with explicit rules not to backdate evidence.
- A weekly status-report format with RAG status, planned/done work, velocity, burndown, SPI, CPI, risks, blockers, and change status.
- A risk register with weekly review, trigger, owner, mitigation, and status for each risk.

### 2. Product definition

The PRD uses MoSCoW priorities. The MVP must support doctor/type selection, available slots, minimum contact details, consent, duplicate-booking prevention, confirmation, reschedule/cancel request handling, reminder workflow, front-desk visibility, doctor availability, and no-show reporting.

The Jira project contains seven epics—Online Booking, Reminders, Front-Desk Dashboard, Doctor Schedules, No-Show Reports, Privacy and Consent, and Go-Live—and 35 stories with acceptance criteria. They are allocated as 15 Sprint 1, 10 Sprint 2, and 10 Sprint 3 stories. Actual sprint execution dates and progress must only be recorded when they occur.

### 3. Design and working prototype

- **Figma:** eight low-fidelity but polished wireframes: doctor/type selection, slot selection, contact and consent, confirmation/self-service, front-desk dashboard, doctor schedule, no-show report, and UAT feedback.
- **draw.io:** as-is phone-booking swimlane and to-be booking/reminder process map. The as-is map explicitly states that it must be validated through front-desk interviews.
- **Airtable:** illustrative MVP data model for Doctors, Patients, Availability slots, Appointments, Reminder log, and UAT feedback. It is labelled as fictional portfolio data. The Bookable slots view is filtered to availability only.

### 4. Quality, privacy, and release readiness

Privacy is designed in rather than attached at the end: minimum contact data, clear consent state, role-aware access design, no clinical data, and no real patient messages. The go-live pack includes UAT, training, cutover, rollback, pilot readiness, hypercare, and handover templates.

## A fictional MVP walkthrough

This walkthrough is a controlled test using only illustrative Airtable records. It is evidence that the prototype data model can support the intended workflow; it is not a patient booking or proof of live automation.

1. A front-desk user opens **Bookable slots** and sees seven available future slots.
2. The user selects an illustrative slot and an illustrative patient record, creates an appointment, and marks it **Confirmed** after the consent check.
3. The linked slot becomes **Booked** and the appointment is visible to the front desk and doctor schedule views.
4. A reminder log entry can be queued as a test record. No WhatsApp/SMS message is sent until a test-only Make scenario has been configured and separately approved.
5. Completion, cancellation, or no-show status feeds the reporting view and makes the pilot KPI denominator auditable.

The first fictional Airtable test successfully displayed the Bookable slots view and created `TEST-BOOKING-20261017`, but the AI-assisted action did **not** reliably complete its linked slot/reminder updates. This is recorded as a partial pass—not a completed end-to-end test—in the [MVP test evidence](16-mvp-test-evidence.md).

## How I managed trade-offs

| Decision | Why | Trade-off and control |
|---|---|---|
| Airtable + Make rather than custom software | Faster demonstration of operational workflow and PM controls. | Less bespoke slot-locking; document concurrency risk and test before pilot. |
| No live message sending in the portfolio | Avoids accidental messages and use of patient data. | Does not prove real provider delivery; use sandbox/test-only scenarios first. |
| Exclude payment/EHR features | Protects the ten-week MVP from scope creep. | Retains a future integration backlog, rather than implying production readiness. |
| Clearly labelled fictional data | Keeps portfolio evidence honest. | Cannot claim achieved operational KPIs until a measured, consented pilot. |

## Risks I actively planned for

The highest initial risks were front-desk adoption (16), simultaneous booking/double-booking (12), scope creep (12), and team availability (12). Mitigations include co-design interviews, test scenarios for unique slot locking, MoSCoW/change control, sprint-three buffer, cross-training, an offline paper fallback, data minimisation, and a vendor fallback option.

## What success would look like

Success is not a visually attractive demo alone. The MVP needs a defined pilot with real, anonymised operational measurements; a UAT pass rate at or above 95%; usability at or above 75 SUS; staff who can complete booking and desk workflows without workarounds; and evidence that any booking-time/no-show improvement is measured against a stated denominator.

## What I would do next

1. Conduct 2–3 short, consented front-desk interviews and record only anonymous role-based notes.
2. Time 5–10 normal bookings and replace the illustrative baseline with dated evidence.
3. Run scenario-based UAT using fictional data, record defects, and calculate the pass rate and SUS.
4. Configure Make with test-only records and a sandbox/approved provider route; validate queue, retry, and failure handling before any real sending.
5. Obtain sponsor/product-owner sign-off before a controlled pilot. If a live pilot is ever approved, perform a privacy review and document retention, access, and consent decisions first.

## Portfolio links

- [Repository overview](../README.md)
- [Charter and business case](01-charter-business-case.md)
- [Product requirements](03-prd.md)
- [Risk register](06-risk-register.md)
- [Jira backlog design](08-jira-backlog.md)
- [Airtable MVP build specification](13-airtable-mvp-build.md)
- [Figma wireframe specification](14-figma-wireframe-spec.md)

