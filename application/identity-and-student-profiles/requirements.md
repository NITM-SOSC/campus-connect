# Identity and Student Profiles — Requirements

**Status:** Proposed; requires maintainer review.  
**Scope:** Student identity, account profile information, and profile visibility.  
**Implementation status:** Not implemented.

## 1. Purpose

Provide each Campus Connect user with an account and a profile that helps members recognize one another and participate in campus activities. The module must protect account security and avoid exposing unnecessary personal information.

## 2. Users and access

- **Student:** Default account type; can view and update permitted parts of their own profile.
- **Approved club representative:** May have additional capabilities defined by the Communities and Clubs module.
- **Verified faculty/staff:** May have additional capabilities once verified by the platform administrator.
- **Platform administrators:** Manage account status and verification.
- Other application roles and permissions must follow the approved application authorization design. GitHub repository roles are separate from application roles.

## 3. Functional requirements

### Account identity
- The system shall support account registration and sign-in using the authentication method selected for the project.
- Each account shall have a unique internal identifier.
- The system shall prevent duplicate accounts according to the chosen identity rule.
- The system shall provide a sign-out function.
- Users shall be able to request account recovery through the approved recovery process.

### Profile management
- Users shall be able to view their own profile.
- Users shall be able to edit permitted profile fields.
- The profile may include a display name, profile image, academic department/programme, year of study, and a short biography.
- The system shall distinguish required fields from optional fields.
- The system shall validate profile data before saving.
- Users shall be able to preview the information visible to other members.

### Visibility and privacy
- The system shall support a defined distinction between public-to-members profile information and restricted account information.
- Authentication secrets, recovery data, and internal account identifiers shall not be displayed as public profile information.
- Users shall not be required to publish optional personal information.
- The system shall not expose a user's private contact details by default.
- Users shall be able to report an impersonation or profile concern.

### Verification and account status
- Faculty/staff accounts shall remain unverified until reviewed by the designated platform administrator.
- The system shall record the verification status and the administrator action.
- The system shall support account states such as active, suspended, and deactivated.
- Account suspension or deactivation shall not silently erase records that other modules need for integrity; handling of retained records must follow the platform's privacy and retention policy.

## 4. Main user flows

1. A student registers and completes the required account fields.
2. The student signs in and views their profile.
3. The student edits permitted fields and saves the changes.
4. A faculty/staff member submits information for verification.
5. The platform administrator reviews the submission and approves or rejects verification.
6. A user reports a profile that appears misleading or inappropriate.

## 5. Validation and error handling

- Required fields must be checked before account creation.
- Email/phone formats, where collected, must be validated.
- Duplicate identity details must produce a clear error without revealing another user's private information.
- Users must receive understandable feedback when a profile update fails.
- Unauthorized users must not be able to edit another user's profile.

## 6. Security and quality requirements

- Passwords, if used, must be stored using a secure password-hashing algorithm; never store plaintext passwords.
- Sensitive account operations must be authorized on the server.
- Private profile fields must not be included in public API responses.
- Authentication and verification events should be logged without recording passwords, tokens, or other secrets.
- Profile pages should work on mobile and desktop and support keyboard navigation.

## 7. Out of scope for the initial version

- Social-media-style feeds or follower systems.
- Direct messaging.
- Public display of private contact information.
- Complex identity-provider integrations unless separately approved.

## 8. Open decisions

- Which campus identity attributes are required for student accounts?
- What registration method will be used, and how will student status be verified?
- Which profile fields are visible to all signed-in members?
- Can users change their registered email/phone, and what verification is required?
- What should happen to authored content when an account is deactivated?
