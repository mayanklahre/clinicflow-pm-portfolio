# ClinicFlow — Project Management Portfolio

ClinicFlow is a self-initiated, low-code appointment-scheduling and no-show-reduction MVP for a five-doctor outpatient clinic. It is not a paid client engagement and contains no patient data.

**Project dates:** 3 August–11 October 2026  
**Project manager:** Mayank Lahre  
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
- [Airtable MVP build specification](docs/13-airtable-mvp-build.md)
- [Figma wireframe specification](docs/14-figma-wireframe-spec.md)
- [Portfolio case study](docs/15-portfolio-case-study.md)
- [MVP test evidence](docs/16-mvp-test-evidence.md)
- [Simulated UAT and SUS dry run](docs/17-simulated-uat-sus.md)
- [Simulated limited pilot dry run](docs/18-simulated-pilot.md)
- [Visual evidence capture guide](docs/19-visual-evidence-capture-guide.md)
- [Evidence gallery and captions](docs/20-evidence-gallery.md)
- [Weekly status reports](status-reports/)
- [Control spreadsheet](sheets/ClinicFlow-control-pack.xlsx)

## Evidence and integrity

The baseline is **illustrative pending observation**, not client data: five simulated phone-booking observations average 6 minutes 18 seconds, and a hypothetical historical sample of 11 no-shows from 61 appointments gives an 18.0% rate. Before publishing this portfolio, replace these values with timed observations and anonymised findings from 2–3 real front-desk staff interviews. Record the collection date and source in the assumption log; never backdate evidence.

The schedule dates precede the package creation date. The files in `status-reports/` are therefore explicitly labelled planning templates, not historical reports.

## Repository conventions

Jira issue keys should appear in implementation commits, for example `CLIN-14: add slot conflict check`. Public screenshots may show only fictional test data. The backlog is designed for the Jira workflow `Backlog → Selected → In Progress → In Review → Testing → Done`.

## Live portfolio artefacts

- [Figma — ClinicFlow MVP Wireframes](https://www.figma.com/design/sYNusDRBYRRAoBrUZGB80R/ClinicFlow-%E2%80%94-MVP-Wireframes?node-id=0-1)
- [Airtable — ClinicFlow illustrative MVP base](https://airtable.com/appPRFexcwanz7lC0)
- [Process maps — draw.io source](diagrams/ClinicFlow-process-maps.drawio)

The live Figma and Airtable links may require the owner to grant view access. Before making a public share link, confirm that each screen and record contains only fictional portfolio data.

## Evidence gallery

All screenshots below contain illustrative portfolio data only. They document the configuration and a manual test; they do not represent a production deployment, a live patient booking, or SMS/WhatsApp delivery.

| Evidence | What it shows |
| --- | --- |
| [Jira sprint allocation](assets/jira-sprint-allocation.png) | The configured CLIN board with 15, 10, and 10 work items in Sprints 1–3. |
| [Bookable slots — before manual retest](assets/airtable-bookable-slots-before-retest.png) | The fictional slot was available before the test booking. |
| [Airtable appointment — before manual retest](assets/airtable-appointments-before-retest.png) | The illustrative appointment table before the test record was completed. |
| [Linked appointment evidence](assets/airtable-appointment-links.png) | TEST-BOOKING-20261018 linked to SLOT-ILL-02 and REM-TEST-20261018; reminder-sent fields remain clear. |
| [No-show evidence](assets/airtable-no-show-evidence.png) | An illustrative no-show record used for the reporting workflow. |
| [Figma wireframe overview](assets/figma-wireframes-overview.png) | The eight planned MVP screens. |


## Standard project layer

This standard navigation layer complements the detailed portfolio documents above.

- [Standard brief](docs/01-brief.md)
- [Standard requirements summary](docs/02-requirements.md)
- [Standard decision-log summary](docs/03-decision-log.md)
- [Standard risk summary](docs/04-risks.md)
- [Standard quality and tests summary](docs/05-quality-and-tests.md)
- [Standard retrospective](docs/06-retrospective.md)
