# Events and Registrations — Requirements

**Status:** Proposed; requires maintainer review.  
**Scope:** Campus event discovery, event publishing, registration, and participant management.  
**Implementation status:** Not implemented.

## 1. Purpose

Allow members to discover campus events and, where registration is enabled, register to participate. Authorized organizers should be able to manage event information and registrations.

## 2. Users and access

- Members can browse published events.
- Members can register for eligible events and manage their own registrations.
- Authorized organizers can create and manage events.
- Organizers may manage registrations for events they are authorized to manage.
- Moderators or administrators may review reported content.
- Exact role-to-permission mappings must follow the approved application authorization design.

## 3. Functional requirements

### Event discovery
- The system shall display published events with title, summary, organizer, date/time, location or online venue, and registration status.
- Members shall be able to open an event to view its details.
- Members should be able to search and filter events by date, category, or organizer.
- The system should distinguish upcoming, ongoing, completed, and cancelled events.

### Event creation and management
- Authorized organizers shall be able to create an event.
- Required event information shall include a title, description, start date/time, end date/time, and venue or participation method.
- Events may include a registration deadline, participant limit, category, and poster or supporting link.
- Organizers shall be able to edit events they are authorized to manage.
- Organizers shall be able to cancel an event and provide a cancellation notice.
- The system shall preserve event status and relevant timestamps.

### Registration
- Members shall be able to register for an event when registration is open.
- The system shall prevent duplicate active registrations by the same member for the same event.
- The system shall reject registrations after the deadline, after cancellation, or when the participant limit has been reached.
- Members shall be able to cancel their own registration before the applicable cutoff.
- The system shall show a clear registration status to the member.
- If waitlists are introduced, their rules must be defined separately.

### Organizer tools
- Authorized organizers shall be able to view the participant list for events they manage.
- Organizers shall be able to view registration counts.
- Attendance tracking may be added if approved for the initial release.
- Access to participant information shall be limited to people who need it to organize the event.

## 4. Main user flows

1. A member browses upcoming events.
2. The member opens an event and reviews its details.
3. The member registers and receives confirmation.
4. The member views or cancels their registration.
5. An authorized organizer creates or updates an event.
6. The organizer views registrations for that event.
7. The organizer cancels an event and members can see its updated status.

## 5. Validation and error handling

- End time must be later than start time.
- Registration deadlines must be consistent with event dates.
- Participant limits, if set, must be positive.
- The backend must recheck capacity when processing registration to prevent overbooking.
- Users must not access participant lists for events they do not manage.
- Failed registration must not leave a partial or duplicate record.

## 6. Security and quality requirements

- All event-management and registration permissions must be checked by the backend.
- Participant information must not be publicly exposed by default.
- Date/time display must follow a consistent timezone policy.
- Event pages and registration controls should be responsive and accessible.
- The system should preserve a useful record of cancellations and significant changes.

## 7. Out of scope for the initial version

- Ticket payments.
- QR-code ticketing.
- Complex seat allocation.
- External calendar integrations.
- Automated attendance recognition.

## 8. Open decisions

- Which roles can create events?
- Can any student create an event, or must an organizer be approved?
- Are registrations mandatory for every event?
- Should events have participant limits or waitlists?
- Is attendance tracking required in the first release?
- What participant details may organizers access?
