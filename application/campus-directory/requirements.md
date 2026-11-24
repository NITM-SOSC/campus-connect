# Campus Directory — Requirements

**Status:** Proposed; requires maintainer review.  
**Scope:** Searchable directory of campus places, facilities, departments, and approved contacts.  
**Implementation status:** Not implemented.

## 1. Purpose

Help members find useful campus information in one place, including departments, offices, facilities, and general campus locations.

## 2. Users and access

- Members can browse and search published directory entries.
- Authorized administrators or designated maintainers can create and update entries.
- Directory information should be limited to information approved for campus-wide sharing.
- Private personal contact details must not be published without an approved basis and permission.

## 3. Functional requirements

### Directory entries
- The system shall support entries for campus departments, offices, facilities, buildings, and other approved campus resources.
- Each entry shall include a name, category, and description or purpose.
- An entry may include a building or general location, opening hours, official contact route, website, and accessibility information.
- The system shall distinguish active entries from entries that are closed or outdated.

### Search and browsing
- Members shall be able to browse entries by category.
- Members should be able to search by name, category, or keyword.
- Search results shall provide enough information to identify the relevant entry.
- Members shall be able to open an entry for its full details.

### Content management
- Authorized maintainers shall be able to create, edit, publish, archive, and correct entries.
- The system shall record the last-updated date.
- Members should be able to report outdated or incorrect information.
- Reported entries shall be reviewable by authorized maintainers.

### Location information
- The module may provide building names, directions, or campus map references where reliable information is available.
- The system shall not claim precise accessibility or opening-hour information unless it has been verified.
- Personal residential addresses and sensitive location information shall not be included.

## 4. Main user flows

1. A member searches for a campus office.
2. The member filters entries by category.
3. The member opens an entry and views its details.
4. An authorized maintainer adds or updates an entry.
5. A member reports outdated information.
6. A maintainer reviews and corrects the entry.

## 5. Validation and error handling

- Entry names and categories must be present.
- URLs and contact details must be validated.
- Duplicate entries should be avoided.
- Archived entries should not appear as current results by default.
- Users without directory-management permission must not be able to modify entries.

## 6. Security and quality requirements

- Directory-management actions must be authorized by the backend.
- Only approved contact information should be displayed.
- Search and detail views should be responsive and accessible.
- Information should display a last-updated date so users can assess freshness.
- The module should not depend on live map services for its basic functionality.

## 7. Out of scope for the initial version

- Live indoor navigation.
- Real-time room occupancy.
- Personal student or staff contact directories.
- Campus-wide asset management.

## 8. Open decisions

- Who is responsible for maintaining directory information?
- Which campus categories should be included initially?
- Should the directory include a map, or only text-based location information?
- Which official contact details may be published?
- How will outdated information be verified?
