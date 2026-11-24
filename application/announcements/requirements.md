# Announcements — Requirements

**Status:** Proposed; requires maintainer review.  
**Scope:** Creating, publishing, browsing, and managing campus announcements.  
**Implementation status:** Not implemented.

## 1. Purpose

Provide a central place for authorized members and campus representatives to publish important information for the campus community.

## 2. Users and access

- Signed-in students and other permitted members can browse published announcements.
- Authorized users can create announcements according to the approved application roles and permissions.
- Authors can edit their own announcements within the permitted rules.
- Designated moderators or administrators can review or remove content when necessary.
- GitHub repository permissions do not grant announcement permissions inside Campus Connect.

## 3. Functional requirements

### Viewing announcements
- The system shall display published announcements in a browsable list.
- Each announcement shall show a title, content, author or publishing authority, publication date, and status.
- Users shall be able to open an announcement to read its full content.
- Users shall be able to browse announcements in reverse chronological order.
- The system should support filtering by category and searching by title or content.

### Creating and editing
- Authorized users shall be able to create an announcement with a title and body.
- Announcements may include a category, relevant dates, and attachments or links where supported.
- The system shall validate required fields before publication.
- Authors shall be able to save a draft if draft support is included in the first release.
- Authors shall be able to edit their own announcements, subject to the approved edit rules.
- The system shall clearly distinguish drafts from published announcements.

### Publishing and lifecycle
- The system shall support publishing and unpublishing or archiving announcements.
- The system shall record publication and update timestamps.
- Expired announcements may be marked as expired or archived without deleting their historical record.
- Users shall not see unpublished drafts unless authorized.

### Reporting and moderation
- Members shall be able to report an announcement that appears inaccurate, inappropriate, or abusive.
- Authorized moderators shall be able to review reports and take permitted action.
- Moderation actions should record the action taken and the responsible account.

## 4. Main user flows

1. A member opens the announcements page and browses published items.
2. A member searches or filters announcements.
3. An authorized user creates an announcement and publishes it.
4. The author edits an announcement they are allowed to edit.
5. A member reports an announcement.
6. An authorized reviewer reviews the report and records an outcome.

## 5. Validation and error handling

- Titles and bodies must not be empty.
- Unsupported or oversized attachments must be rejected with a clear message.
- Only authorized users may create, edit, publish, or moderate announcements.
- A user must not be able to modify another author's announcement unless explicitly authorized.
- Failed operations must not create duplicate announcements.

## 6. Security and quality requirements

- Authorization must be enforced by the backend.
- Uploaded files, if supported, must be validated and safely stored.
- Announcement content should be rendered safely; user-submitted content must not execute scripts.
- The list and detail views should be responsive and accessible.
- Important dates and timestamps should use a consistent timezone policy.

## 7. Out of scope for the initial version

- Real-time push notifications.
- Personalized recommendation algorithms.
- Complex approval workflows unless required by the final role policy.

## 8. Open decisions

- Which roles may publish announcements?
- Do announcements from faculty or administrators require review?
- Which categories should be available?
- Should announcements support attachments in the first release?
- Should authors be able to edit after publication, and should edit history be visible?
- Should members receive email or in-app notifications?
