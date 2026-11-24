# Permissions and Access Control

**Status:** Proposed — pending review and approval.

This document defines the individual permissions associated with user roles in the Campus Connect application. It establishes the proposed authorization rules for application modules and serves as a reference for future implementation.

This document complements `USER_ROLES.md`, which defines user categories and their responsibilities.

No permission enforcement system has been implemented yet.

## 1. Objectives

The permission system aims to:

- Define exactly what users can and cannot do.
- Associate permissions with application roles.
- Support users holding multiple roles.
- Restrict access to resources based on ownership and assigned responsibilities.
- Protect sensitive student information and grievances.
- Keep authorization manageable for a college community project.

## 2. Permission Naming Convention

Permissions follow this format:

`module.action`

Examples:

- `announcements.view`
- `announcements.create`
- `announcements.edit`
- `events.register`
- `clubs.manage`
- `users.assign_roles`
- `grievances.view_assigned`

Each permission represents an action that a user may perform within a particular module.

Permissions should be checked by the backend before executing protected operations.

## 3. Permission Definitions

### 3.1 Authentication and Student Profiles

| Permission | Description |
|---|---|
| `profiles.view_own` | View one's own profile. |
| `profiles.edit_own` | Edit one's own profile. |
| `profiles.view_public` | View publicly available student profile information. |
| `profiles.view_restricted` | View restricted profile information when explicitly authorized. |
| `profiles.manage` | Manage user profiles as an administrator. |

Private profile information must not become accessible merely because a user has a higher-level role.

### 3.2 Campus Announcements

| Permission | Description |
|---|---|
| `announcements.view` | View published announcements. |
| `announcements.create` | Create announcements. |
| `announcements.edit_own` | Edit one's own announcements. |
| `announcements.edit_assigned` | Edit announcements belonging to assigned clubs or responsibilities. |
| `announcements.delete_own` | Delete one's own announcements. |
| `announcements.delete_any` | Remove announcements when authorized. |
| `announcements.moderate` | Review and moderate reported announcements. |

### 3.3 Events and Registrations

| Permission | Description |
|---|---|
| `events.view` | Browse available events. |
| `events.create` | Create events. |
| `events.edit_own` | Edit events created by the user. |
| `events.edit_assigned` | Manage events belonging to assigned clubs or responsibilities. |
| `events.delete_own` | Delete one's own events. |
| `events.delete_any` | Remove events when authorized. |
| `events.register` | Register for events. |
| `events.manage_registrations` | Manage registrations for authorized events. |
| `events.moderate` | Moderate reported event content. |

### 3.4 Student Communities and Clubs

| Permission | Description |
|---|---|
| `clubs.view` | Browse clubs and communities. |
| `clubs.join` | Request or complete membership where permitted. |
| `clubs.create` | Create a club or community, subject to approval. |
| `clubs.manage_assigned` | Manage assigned clubs. |
| `clubs.manage_members` | Review and manage membership requests for assigned clubs. |
| `clubs.publish_announcements` | Publish announcements for assigned clubs. |
| `clubs.moderate` | Moderate reported club content. |

### 3.5 Lost and Found

| Permission | Description |
|---|---|
| `lost_found.view` | Browse Lost and Found posts. |
| `lost_found.create` | Create a post. |
| `lost_found.edit_own` | Edit one's own posts. |
| `lost_found.delete_own` | Delete one's own posts. |
| `lost_found.moderate` | Moderate reported posts. |
| `lost_found.manage` | Manage posts when administratively authorized. |

### 3.6 Student Project Collaboration

| Permission | Description |
|---|---|
| `projects.view` | Browse project opportunities. |
| `projects.create` | Create project listings. |
| `projects.edit_own` | Edit one's own listings. |
| `projects.delete_own` | Delete one's own listings. |
| `projects.join` | Express interest in joining projects. |
| `projects.manage_members` | Manage participants in projects owned by the user. |
| `projects.moderate` | Moderate reported project content. |

### 3.7 Academic Resources

| Permission | Description |
|---|---|
| `resources.view` | Access available academic resources. |
| `resources.upload` | Upload academic materials. |
| `resources.edit_own` | Edit one's own uploaded materials. |
| `resources.delete_own` | Delete one's own uploaded materials. |
| `resources.manage` | Manage approved academic resources. |
| `resources.moderate` | Review and moderate reported resources. |

### 3.8 Campus Directory

| Permission | Description |
|---|---|
| `directory.view` | Browse campus directory information. |
| `directory.create` | Add directory entries. |
| `directory.edit` | Edit authorized directory entries. |
| `directory.delete` | Remove directory entries when authorized. |

### 3.9 Feedback and Grievance Management

| Permission | Description |
|---|---|
| `feedback.submit` | Submit general feedback. |
| `feedback.view_own` | View one's own feedback submissions. |
| `feedback.manage` | Manage general feedback. |
| `grievances.submit` | Submit a confidential grievance. |
| `grievances.view_own` | View one's own grievances. |
| `grievances.view_assigned` | View grievances assigned to the user. |
| `grievances.update_assigned` | Update the status of assigned grievances. |
| `grievances.respond_assigned` | Communicate with students regarding assigned grievances. |
| `grievances.manage` | Manage grievance assignments and workflow when explicitly authorized. |

Grievance permissions must be kept separate from general moderation permissions.

A Moderator must not automatically receive access to confidential grievances.

### 3.10 Student Marketplace

| Permission | Description |
|---|---|
| `marketplace.view` | Browse marketplace listings. |
| `marketplace.create` | Create listings. |
| `marketplace.edit_own` | Edit one's own listings. |
| `marketplace.delete_own` | Delete one's own listings. |
| `marketplace.manage_own` | Manage one's own active listings. |
| `marketplace.moderate` | Review and moderate reported listings. |
| `marketplace.manage` | Manage listings when administratively authorized. |

## 4. Role-Permission Mapping

The following table defines the proposed permissions for each role.

| Module | Student | Club Representative | Faculty / Staff | Moderator | Grievance Officer | Superadmin |
|---|---|---|---|---|---|---|
| Profiles | Own | Own | Own | Public information | Assigned cases | Manage accounts |
| Announcements | View | Create and manage assigned | Create and manage authorized | Moderate globally | View | Manage |
| Events | View and register | Manage assigned events | Manage authorized events | Moderate globally | View | Manage |
| Clubs | View and join | Manage assigned clubs | View and participate | Moderate globally | View | Manage |
| Lost and Found | Own posts | Same as Student | Same as Student | Moderate globally | View | Manage |
| Project Collaboration | Participate | Same as Student | Participate | Moderate globally | View | Manage |
| Academic Resources | Access | Access | Upload and manage authorized | Moderate globally | Access | Manage |
| Campus Directory | View | View | Manage authorized entries | Moderate globally | View | Manage |
| Feedback | Submit | Submit | Submit | — | Manage assigned grievances | Manage workflow |
| Marketplace | Own listings | Same as Student | Same as Student | Moderate globally | View | Manage |

**Important:** This table is a summary. The detailed permission definitions and restrictions in this document take precedence.

## 5. Special Authorization Rules

Some permissions require additional checks beyond the user's assigned role.

### 5.1 Resource Ownership

Users should generally be allowed to edit or delete only resources they own.

For example:

- A student can edit their own marketplace listing.
- A student cannot edit another student's listing.
- A project creator can manage their own project participants.

### 5.2 Assigned Club Access

Club Representatives can manage only clubs assigned to them.

A role alone does not grant access to every club.

### 5.3 Global Moderation

Moderators have community-wide moderation responsibilities across the Campus Connect platform.

They may review reported content in any application module, subject to the restrictions on confidential information.

### 5.4 Grievance Confidentiality

Grievances require separate authorization.

- Students can submit and view their own grievances.
- Grievance Officers can access grievances assigned to them.
- Moderators cannot access confidential grievances merely because they are moderators.
- Superadmin access to grievance content should be limited to explicitly authorized situations.

### 5.5 Multiple Roles

A user may hold multiple roles.

The effective permissions of a user are determined by combining the permissions of their assigned roles, while respecting ownership, assignment, and confidentiality restrictions.

For example, a user who is both a Student and Moderator can:

- Perform regular student activities.
- Review reported content across the platform.
- Manage their own profile and listings.

However, the Moderator role does not grant access to confidential grievances.

### 5.6 Administrative Permissions

The Superadmin can manage application-wide settings, accounts, and role assignments.

Administrative permissions should not automatically bypass privacy restrictions on sensitive records.

## 6. Authorization Process

Every protected operation should follow this general process:

1. Identify the authenticated user.
2. Retrieve the user's assigned roles.
3. Determine the permission required for the requested action.
4. Check whether one of the user's roles grants that permission.
5. Verify resource ownership or assignment where applicable.
6. Apply additional privacy restrictions.
7. Allow or reject the operation.

The backend must enforce these checks.

Frontend visibility controls may improve the user experience but must never be treated as a replacement for backend authorization.

## 7. Permission Management

- The Superadmin is responsible for assigning and revoking elevated roles.
- Users cannot grant permissions to themselves.
- Permissions should be centrally defined rather than independently invented by individual modules.
- Role changes should take effect without requiring account recreation.
- Removing an elevated role should remove the permissions associated with that role.
- Users who leave the project should have their elevated roles and access revoked.

## 8. Audit and Accountability

The application should maintain basic records of important actions:

- Role assignments and removals.
- Faculty verification.
- Account suspension or deactivation.
- Content moderation actions.
- Changes to sensitive grievance records.

Records should identify the responsible user, the action performed, and the date and time.

## 9. Implementation Status

This document defines the proposed permission model.

The following are not yet implemented:

- Permission storage and role mapping.
- Backend authorization checks.
- Resource ownership checks.
- Club assignment checks.
- Global moderation controls.
- Grievance-specific access restrictions.
- Administrative permission management.

These requirements will guide the future implementation of the authorization system.

---

**Document Status:** Proposed  
**Scope:** Application-wide permissions and authorization  
**Implementation:** Not yet started