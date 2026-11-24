# Academic Resources — Requirements

**Status:** Proposed; requires maintainer review.  
**Scope:** Uploading, organizing, discovering, and accessing academic learning resources.  
**Implementation status:** Not implemented.

## 1. Purpose

Provide a structured place for campus members to share and discover useful academic resources, such as notes, study guides, reference links, and learning materials.

## 2. Users and access

- Members can browse and access resources they are permitted to view.
- Authorized contributors can submit resources.
- Resource owners can manage their own submissions.
- Moderators or designated administrators can review reports and manage content according to the approved permission policy.
- Faculty/staff verification is handled by the identity module and does not automatically grant unrestricted access to every resource-management function.

## 3. Functional requirements

### Resource submission
- Authorized members shall be able to submit a resource.
- A resource shall include a title, description, subject or category, and contributor.
- A resource may include a file or an external link.
- Resources may include course, department, semester, topic, and resource-type metadata.
- The system shall capture the source or attribution information where supplied.
- The system shall require the contributor to confirm that they have the right to share the material.

### Browsing and discovery
- Members shall be able to browse published resources.
- Members should be able to search by title, subject, course, topic, or contributor.
- Members should be able to filter by resource type and relevant academic metadata.
- Each resource shall display its title, description, category, contributor, and submission date.
- The system shall distinguish pending, published, rejected, and removed resources where review is required.

### Resource management
- Contributors shall be able to edit or withdraw their own submissions where permitted.
- Authorized reviewers shall be able to approve, reject, hide, or remove resources according to the moderation policy.
- The system should retain a basic record of review decisions.
- Broken external links and unavailable files should be reported clearly to users.

### Copyright and content quality
- The module shall not encourage uploading material that the contributor does not have permission to distribute.
- The system should support attribution and source links.
- Reported copyright concerns shall be reviewable by authorized personnel.
- The module should provide a reporting route for inaccurate, unsafe, or inappropriate resources.

## 4. Main user flows

1. A member browses resources by subject or course.
2. The member opens or downloads an available resource.
3. An authorized contributor submits a resource with metadata and attribution.
4. The resource is published directly or reviewed, depending on the approved policy.
5. A contributor edits or withdraws their submission.
6. A member reports a resource concern and an authorized reviewer handles it.

## 5. Validation and error handling

- Required metadata must be present.
- File type and file size must be checked against configured limits.
- External links must use supported URL formats.
- Duplicate submissions should be detected where practical.
- Failed uploads must not create incomplete published resources.
- Users must receive a clear message if a resource is unavailable.

## 6. Security and quality requirements

- Uploaded files must be stored and served safely.
- The backend must enforce upload, edit, review, and deletion permissions.
- Files must not be executable as part of normal resource viewing.
- Access restrictions must be enforced on the server, not only hidden in the interface.
- Resource pages should be accessible and responsive.

## 7. Out of scope for the initial version

- Paid notes or resource sales.
- Automated plagiarism detection.
- Integrated online classrooms.
- Full learning-management-system functionality.

## 8. Open decisions

- Which file types and maximum sizes should be supported?
- Should submissions require approval before publication?
- Which academic categories and metadata fields are required?
- Should access be limited by department or course?
- How should copyright complaints and takedown requests be handled?
