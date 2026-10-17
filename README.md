# ClinicFlow — Project Management Portfolio

ClinicFlow is a self-initiated, low-code appointment-scheduling and no-show-reduction MVP for a five-doctor outpatient clinic. It is not a paid client engagement and contains no patient data.

**Project dates:** 3 August–11 October 2026  
**Project manager:** Kirito  
**Delivery approach:** plan and budget baseline first, then three two-week Scrum sprints and controlled pilot release.

## Portfolio map

- [Charter and business case](docs/01-charter-business-case.md)
- [Stakeholders and feasibility](docs/02-stakeholders-feasibility.md)
- [Product requirements document](docs/03-prd.md)
- [Work breakdown structure and schedule](docs/04-wbs-schedule.md)
- [RACI](docs/05-raci.md)
- [Risk register](docs/06-risk-register.md)
- [Communications, quality, and change control](docs/07-controls-plan.md)
- [Backlog and Jira setup](docs/08-jira-backlog.md)
- [Airtable / Make solution design](docs/09-solution-design.md)
- [UAT, cutover, and training](docs/10-go-live.md)
- [Closure, handover, and retrospective](docs/11-closure-retrospective.md)
- [Project logs](docs/12-project-logs.md)
- [Weekly status reports](status-reports/)
- [Control spreadsheet](sheets/ClinicFlow-control-pack.xlsx)

## Evidence and integrity

The baseline is **illustrative pending observation**, not client data: five simulated phone-booking observations average 6 minutes 18 seconds, and a hypothetical historical sample of 11 no-shows from 61 appointments gives an 18.0% rate. Before publishing this portfolio, replace these values with timed observations and anonymised findings from 2–3 real front-desk staff interviews. Record the collection date and source in the assumption log; never backdate evidence.

The schedule dates precede the package creation date. The files in `status-reports/` are therefore explicitly labelled planning templates, not historical reports.

## Repository conventions

Jira issue keys should appear in implementation commits, for example `CLIN-14: add slot conflict check`. Public screenshots may show only fictional test data. The backlog is designed for the Jira workflow `Backlog → Selected → In Progress → In Review → Testing → Done`.
