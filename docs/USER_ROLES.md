# User Roles and Permissions

**Status:** Proposed — decisions established, pending formal approval.

This document defines the user roles, responsibilities, and access boundaries for the Campus Connect application. It establishes the foundation for role-based access control (RBAC). It does not describe an implemented authorization system.

## 1. Objectives

The role system aims to:

- Define responsibilities for different categories of users.
- Ensure users have access only to functionality necessary for their responsibilities.
- Protect private student information and sensitive submissions.
- Support delegated management of clubs, communities, and institutional activities.
- Establish accountability for administrative and moderation actions.
- Allow users to hold multiple roles when appropriate.

## 2. User Roles

The application will initially support six roles.

### 2.1 Student

The default role for student contributors.

**Permissions:**
- Create and manage their own profile.
- Browse campus announcements.
- Discover events and register for them.
- Discover and join student communities and clubs.
- Create and manage their own Lost and Found posts.
- Participate in student project collaborations.
- Access available academic resources.
- Browse the campus directory.
- Submit feedback and grievances.
- Create, manage, and browse marketplace listings.

**Restrictions:**
- Cannot access another student's private information without authorization.
- Cannot assign elevated roles.
- Must follow platform guidelines.

### 2.2 Club Representative

A student authorized to represent and manage a particular club or student community.

**Permissions:**
- Perform regular student activities.
- Manage assigned clubs or communities.
- Publish club-related announcements.
- Create and manage club events.
- Review membership requests.
- Coordinate club activities.

**Restrictions:**
- Can manage only assigned clubs or communities.
- Cannot modify platform-wide settings.
- Cannot grant themselves additional privileges.

### 2.3 Faculty / Staff

Verified institutional personnel with permissions appropriate to their responsibilities.

**Permissions:**
- Access permitted regular user functionality.
- Publish authorized campus announcements.
- Create and manage institutional events.
- Upload and maintain approved academic resources.
- Maintain relevant campus directory information.

**Restrictions:**
- Permissions depend on assigned institutional responsibilities.
- Cannot automatically access private student information.
- Cannot access confidential grievances unless separately authorized.

### 2.4 Moderator

Responsible for maintaining appropriate platform conduct across the community.

**Permissions:**
- Review reported announcements, posts, and listings.
- Review reported community activity.
- Remove, restrict, or flag content that violates platform guidelines.
- Handle reports of inappropriate behavior.
- Record moderation decisions.

**Restrictions:**
- Moderators have community-wide moderation responsibilities.
- Cannot automatically access confidential grievances.
- Cannot modify platform-wide configuration.
- Moderation actions should be recorded.

### 2.5 Grievance Officer

Authorized personnel responsible for handling sensitive student feedback and grievances.

**Permissions:**
- Access grievances assigned to them.
- Review submitted complaints.
- Update grievance status.
- Communicate with concerned students.
- Record investigation progress and resolution details.

**Restrictions:**
- Can access only grievances they are authorized to handle.
- Must maintain confidentiality.
- Cannot disclose grievance information to unauthorized users.

### 2.6 Platform Administrator (Superadmin)

Responsible for overall project and application management.

The Superadmin is the highest-authority account responsible for managing the platform.

**Permissions:**
- Manage user accounts.
- Assign and revoke roles.
- Verify faculty and staff identities.
- Approve Club Representative, Moderator, and Grievance Officer assignments.
- Suspend or deactivate accounts when necessary.
- Configure platform-wide settings.
- Manage permissions and access policies.
- Oversee application modules.

**Restrictions:**
- Administrative actions should be accountable.
- Confidential grievance information should remain protected.
- Role assignments and account restrictions should follow documented procedures.

The project will initially use a simple administrative structure rather than introducing multiple levels of administrators.

## 3. Permission Matrix

| Feature | Student | Club Representative | Faculty / Staff | Moderator | Grievance Officer | Superadmin |
| --- | --- | --- | --- | --- | --- | --- |
| Student Profiles | Own profile | Own profile | Own profile | Limited | Assigned cases | Manage accounts |
| Announcements | View | Manage assigned club announcements | Manage authorized announcements | Moderate | — | Manage |
| Events | Register | Manage assigned club events | Manage authorized institutional events | Moderate | — | Manage |
| Communities and Clubs | Join | Manage assigned clubs | Participate where permitted | Moderate | — | Manage |
| Lost and Found | Own posts | Same as Student | Same as Student | Moderate | — | Manage |
| Project Collaboration | Participate | Same as Student | Participate | Moderate | — | Manage |
| Academic Resources | Access | Access | Manage authorized resources | Moderate | — | Manage |
| Campus Directory | View | View | Manage authorized entries | Moderate | — | Manage |
| Feedback and Grievances | Submit | Submit | Submit | No confidential access by default | Assigned grievances | Manage workflow |
| Student Marketplace | Own listings | Same as Student | Same as Student | Moderate | — | Manage |

**Note:** A dash indicates that no standard permission is proposed for that role. Additional permissions require explicit authorization.

## 4. Role Assignment and Management

### 4.1 Default Student Role

- Students are the default contributors to the platform.
- Student accounts receive the Student role.
- Ordinary student participation does not require elevated-role approval.
- Additional verification requirements can be introduced if necessary.

### 4.2 Faculty / Staff Verification

- Faculty and staff identities must be verified by the Superadmin.
- Faculty / Staff permissions are assigned after verification.

### 4.3 Elevated Role Approval

The following assignments require Superadmin approval:

- Club Representative.
- Faculty / Staff.
- Moderator.
- Grievance Officer.

### 4.4 Multiple Roles

A user may hold multiple roles simultaneously.

Examples:
- A student may also be a Club Representative.
- A user may simultaneously be a Moderator and Grievance Officer.
- A faculty member may also be an authorized Moderator.

Permissions should be evaluated based on assigned roles, subject to applicable restrictions.

### 4.5 Role Revocation

- When a contributor leaves the project or no longer wishes to participate, their elevated roles and associated access should be revoked.
- Accounts may be deactivated when appropriate.
- Role changes should be recorded.
- Revoking an elevated role should not unnecessarily deactivate a user's regular account.

## 5. Access Control Principles

### 5.1 Least Privilege

Users should receive only the permissions necessary for their responsibilities.

### 5.2 Explicit Authorization

Access to sensitive operations must be explicitly authorized.

### 5.3 Scoped Permissions

Permissions should be limited to relevant resources.

For example, a Club Representative should manage only their assigned club.

### 5.4 Privacy and Confidentiality

- Private student information must be protected.
- Sensitive grievances must be accessible only to authorized personnel.
- Personal information should not be exposed unnecessarily.

### 5.5 Accountability

Important administrative and moderation actions should be recorded.

## 6. Role Hierarchy

The following diagram illustrates the conceptual relationship between regular users and users with additional responsibilities.

```text
                 Superadmin
                     |
          +----------+----------+
          |          |          |
      Moderator  Grievance   Faculty / Staff
                  Officer
                     |
                  Student
                     |
             Club Representative
```

**Important:** This is a conceptual representation, not a strict inheritance hierarchy. Roles are independently assignable, and users may hold multiple roles.

## 7. Moderation Disputes

If a user disagrees with a moderation decision:

1. The user may request a review through a private discussion.
2. The moderator should explain the reason for the decision.
3. The decision may be reconsidered after discussion.
4. The outcome should be communicated to the concerned user.

The process should remain straightforward and appropriate for the size of the college community.

## 8. Audit and Accountability

The application should maintain basic records of important actions, including:

- Role assignments and removals.
- Faculty identity verification.
- Account suspension or deactivation.
- Content moderation actions.
- Changes to sensitive grievance records.

Each record should identify the action, the responsible user, and the date and time.

The project does not need a complicated auditing system initially. The exact retention period for these records can be decided before implementation.

## 9. Implementation Status

This document defines the proposed role and access-control policies.

The following are not yet implemented:

- Role-based authorization.
- Role assignment and revocation workflows.
- Faculty identity verification.
- Permission enforcement.
- Moderation workflows.
- Grievance-specific access controls.
- Audit logging.

These requirements should be considered during the design and implementation of authentication, authorization, and individual application modules.

---

**Document Status:** Proposed  
**Scope:** Application-wide user roles and permissions  
**Implementation:** Not yet started