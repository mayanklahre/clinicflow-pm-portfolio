# Figma wireframe specification

Create one Figma file named **ClinicFlow MVP Wireframes**. Use a simple greyscale design with a single blue action colour, high-contrast labels, and desktop frames at 1440 px wide unless noted. These screens are conceptual portfolio wireframes, not evidence of a deployed product.

## Frame 1 — Patient booking: doctor and appointment type

- Header: ClinicFlow logo, `Book an appointment`, `Call clinic` fallback.
- Progress indicator: `1. Details` → `2. Time` → `3. Confirm`.
- Main fields: doctor cards, specialty, next available time, appointment type radio cards.
- Primary action: `Continue to available times`.
- Accessibility note: fully visible labels, not placeholder-only fields.

## Frame 2 — Patient booking: available slots

- Doctor name and appointment type summary with `Change` links.
- Week selector and a simple list/grid of future available slots.
- Selected slot has a clear selected state.
- Supporting note: `Times are shown in clinic local time.`
- Primary action remains disabled until one slot is selected.

## Frame 3 — Patient booking: contact and consent

- Minimum fields: first name, last initial, mobile number.
- Checkbox: `I agree to receive appointment reminders by WhatsApp or SMS.`
- Secondary link: `I do not want reminders`.
- Plain-language privacy note: `Messages will not include diagnosis or treatment details.`
- Error state for missing consent only when the user has selected reminders.

## Frame 4 — Booking confirmation and self-service actions

- Confirmation card: appointment date/time, doctor, clinic contact number, booking reference.
- Status: `Confirmed`.
- Actions: `Add to calendar`, `Request reschedule`, `Cancel appointment`.
- Reminder note: `We will send a reminder 24 hours before your appointment if you opted in.`

## Frame 5 — Front-desk dashboard

- Left navigation: Today, Appointments, Doctors, Reports.
- Header: date selector, search by booking reference/first name, `Create phone booking` button.
- Main table: time, patient label, doctor, appointment type, reminder state, status, actions.
- Attention flags: reminder failed, reschedule requested, late arrival.
- Actions: Check in, Mark no-show, Cancel, Reschedule.

## Frame 6 — Doctor schedule management

- Doctor selector and week/day view.
- Appointment blocks with anonymised patient labels and statuses.
- Controls: `Set recurring availability`, `Add time-off`, `Block slot`.
- Slot configuration panel: duration, buffer, active appointment types.

## Frame 7 — No-show report

- Filters: date range, doctor, appointment type.
- KPI cards: booked, attended, cancelled, no-shows, no-show rate.
- Trend chart placeholder and outcome table by doctor.
- Export action labelled `Export aggregate data`; no patient mobile/contact data appears on this screen.

## Frame 8 — UAT feedback form

- Scenario selector, pass/fail control, severity selector, free-text feedback.
- Single System Usability Scale question shown as a 1–5 scale; use all ten items in the actual UAT form.
- Submit action and a thank-you state.

## Prototype links

- Frame 1 → Frame 2 → Frame 3 → Frame 4 for the booking journey.
- Frame 5 action `Mark no-show` → confirmation modal.
- Frame 5 navigation `Doctors` → Frame 6.
- Frame 5 navigation `Reports` → Frame 7.

## Review checklist

- Every critical action has a visible status/error state.
- Consent and opt-out are clear and separate from booking completion.
- No diagnostic or treatment details appear in reminders or reporting exports.
- Dashboard actions reflect the Jira workflow and Airtable status values.
- Wireframes show the user journey, operational workflow, and reporting outcome in one coherent MVP.
