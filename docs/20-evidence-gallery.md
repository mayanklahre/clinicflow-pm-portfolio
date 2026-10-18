# Evidence gallery

All screenshots in this gallery use illustrative portfolio data only. They were captured on 18 October 2026 and document configuration or controlled manual testing. They are not proof of a paid engagement, production release, real patient activity, or live reminder delivery.

| Asset | Caption and interpretation |
| --- | --- |
| [Jira sprint allocation](../assets/jira-sprint-allocation.png) | The configured ClinicFlow Jira board contains 35 work items allocated 15 / 10 / 10 across its three sprints. The board shows no estimates; do not use it as evidence of velocity. |
| [Bookable slots before retest](../assets/airtable-bookable-slots-before-retest.png) | A pre-test view of seven fictional available slots, including SLOT-ILL-02. It establishes the state before the controlled booking retest. |
| [Appointments before retest](../assets/airtable-appointments-before-retest.png) | The fictional appointments table before manual completion of the new test booking. |
| [Appointment links after retest](../assets/airtable-appointment-links.png) | The fictional TEST-BOOKING-20261018 record is linked to SLOT-ILL-02 and REM-TEST-20261018. The 24-hour and 2-hour “sent” fields are clear; no message was sent. |
| [No-show workflow evidence](../assets/airtable-no-show-evidence.png) | An illustrative No-show row supporting the proposed report workflow. It is not a measured pilot result. |
| [Figma wireframe overview](../assets/figma-wireframes-overview.png) | Eight planned MVP frames: booking, slots, contact/consent, confirmation, front desk, doctor schedule, no-show report, and UAT feedback. |

## Known gaps

- The supplied Bookable Slots view is pre-test evidence. The manual test later changed SLOT-ILL-02 to Booked; its status and linked appointment were verified directly in Airtable and recorded in [MVP test evidence](16-mvp-test-evidence.md).
- The evidence does not demonstrate automated messaging. Make is unconnected and the reminder record is explicitly no-send.
- Atomic duplicate-booking prevention remains to be tested before any real pilot.
