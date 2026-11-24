# Feedback and Grievance Management — Requirements

**Status:** Proposed; requires maintainer review.  
**Scope:** General feedback submission and confidential grievance handling.  
**Implementation status:** Not implemented.

## 1. Purpose

Give members a clear way to share general feedback and raise concerns. Grievances must be handled with stricter confidentiality and access controls than ordinary feedback.

## 2. Important distinction

- **Feedback** is general input, suggestions, or comments about Campus Connect or campus services.
- **Grievance** is a concern or complaint that may involve an individual, sensitive circumstances, or a request for intervention.

The two flows must not expose the same information to the same audience by default.

## 3. Users and access

- Members can submit feedback and grievances.
- Members can view the status of their own submissions.
- Assigned grievance officers can access only the grievances assigned to them.
- Authorized administrators can manage assignment and operational settings, but access to grievance contents must remain limited to legitimate handling needs.
- A user may hold both Moderator and Grievance Officer roles if approved; these roles must not automatically grant access to every grievance.
- Moderation of public content and handling confidential grievances are separate responsibilities.

## 4. Functional requirements

### General feedback
- Members shall be able to submit feedback with a subject, category, and description.
- Members may optionally provide contact details if they want a response, subject to the privacy policy.
- Members shall be able to view the status of their own feedback.
- Authorized personnel shall be able to review and update feedback status.
- The system may support a response to the submitter.

### Grievance submission
- Members shall be able to submit a grievance through a clearly distinguished form.
- The form shall explain who can access the submission and how it will be handled.
- A grievance shall include a description and may include a category and supporting information.
- The system shall assign a unique reference identifier.
- The system shall not display grievance contents in public feeds or ordinary profile pages.
- The submitter shall be able to view the status of their own grievance without gaining access to internal notes.

### Assignment and handling
- An authorized administrator shall be able to assign a grievance to an eligible grievance officer.
- A grievance officer shall be able to view and update grievances assigned to them.
- A grievance officer shall be able to record a response or status update.
- Internal notes shall be distinguishable from messages visible to the submitter.
- Reassignment and status changes shall be recorded.
- Users who are not assigned or otherwise explicitly authorized shall not be able to access grievance details.

### Status and closure
- The system shall support a simple lifecycle such as submitted, under review, awaiting information, resolved, and closed.
- The submitter shall be informed of relevant status changes through the available notification mechanism.
- A grievance shall not be marked resolved without an appropriate recorded outcome.
- Reopening a grievance, if supported, shall be an explicit action.

### Privacy and reporting
- The system shall explain any confidentiality limits before submission.
- The system shall collect only information needed to handle the concern.
- Access to grievance content shall be restricted and auditable.
- The system shall provide a way to report a concern about mishandling or inappropriate access.

## 5. Main user flows

1. A member chooses either general feedback or grievance submission.
2. The member submits the appropriate form.
3. The system creates a private record and reference identifier.
4. An authorized administrator assigns a grievance, where applicable.
5. The assigned officer reviews it and records internal notes or a response.
6. The submitter checks the status and receives appropriate updates.
7. The authorized handler records the outcome and closes the case.

## 6. Validation and error handling

- Required descriptions must not be empty.
- Users must not be able to access another person's submission by changing an identifier.
- Internal notes must never be returned to the submitter-facing view.
- Assignment must be checked on every relevant request.
- Failed submissions must not create duplicate cases.
- Errors must not reveal confidential information.

## 7. Security and quality requirements

- Enforce authorization on the backend for every grievance operation.
- Apply least-privilege access to grievance records.
- Keep an audit record of access-relevant administrative actions, assignment changes, and status changes.
- Never log full grievance contents, passwords, authentication tokens, or unnecessary sensitive data in general application logs.
- Define a retention and deletion policy before production use.
- Use secure transport and protect stored data according to the platform's security design.
- The interface must be accessible and should explain privacy expectations in plain language.

## 8. Out of scope for the initial version

- Public grievance boards.
- Anonymous submissions unless a safe handling and abuse-prevention policy is approved.
- Automated decisions about the validity of a grievance.
- Complex legal case-management workflows.

## 9. Open decisions

- Who may act as a grievance officer, and how are they approved?
- Can a submitter request a particular officer or request reassignment?
- What information should be visible to the submitter at each status?
- What is the escalation route if a grievance concerns its assigned officer?
- What retention period and deletion process should apply?
- Is anonymous submission necessary, and if so, how will follow-up work?
