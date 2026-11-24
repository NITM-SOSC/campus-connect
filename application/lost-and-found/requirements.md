# Lost and Found — Requirements

**Status:** Proposed; requires maintainer review.  
**Scope:** Posting, browsing, and resolving lost or found item reports.  
**Implementation status:** Not implemented.

## 1. Purpose

Help campus members report lost or found belongings and coordinate their return while minimizing disclosure of personal information and reducing false claims.

## 2. Users and access

- Signed-in members can browse active lost and found posts.
- Members can create and manage their own posts.
- Authorized moderators can review reports and remove inappropriate or misleading posts.
- A member who claims an item must follow the contact or handover process approved by the project.
- Exact moderation permissions must follow the approved application authorization design.

## 3. Functional requirements

### Creating a post
- Members shall be able to create either a **Lost** or **Found** post.
- A post shall include an item title, description, approximate date, and general location.
- A post may include an image.
- The form should allow a category to be selected.
- The system shall warn users not to publish sensitive identifying information, such as full identity-card numbers, private addresses, or personal contact details.
- The system should allow a finder to withhold one or more identifying details so a claimant can describe the item to establish a credible claim.

### Browsing and searching
- Members shall be able to browse active posts.
- Members should be able to search or filter by lost/found status, category, date, or general location.
- Each post shall display its current status.
- Resolved posts should no longer appear among active results by default.

### Contact and claims
- Interested members shall be able to use an approved contact route without exposing private contact details publicly.
- The system should support a claim or response workflow.
- The poster shall be able to mark a post as resolved or returned.
- The system shall avoid publicly revealing sensitive details that could enable false claims.
- The initial version may use a simple contact/claim process rather than automated identity verification.

### Moderation
- Members shall be able to report suspicious, inappropriate, or misleading posts.
- Authorized moderators shall be able to review reports and take permitted action.
- The system shall record moderation outcomes.

## 4. Main user flows

1. A student loses an item and creates a Lost post.
2. Another student finds an item and creates a Found post.
3. A member browses or searches relevant posts.
4. The member contacts the poster through the approved process.
5. The poster verifies the claim using details not disclosed publicly.
6. The poster marks the post as resolved.
7. A member reports a suspicious post and a moderator reviews it.

## 5. Validation and error handling

- Required title and description fields must not be empty.
- Dates must be valid and should not be implausibly far in the future.
- Images must be checked for allowed file types and size.
- A user must not edit or delete another member's post unless authorized.
- The system must prevent a resolved post from being treated as an active listing without an explicit status change.

## 6. Security and quality requirements

- Private contact details must not be exposed in public post data.
- Uploaded images must be validated and safely served.
- The module should provide clear safety guidance for arranging item return through appropriate campus channels.
- Backend authorization must protect ownership and moderation actions.
- The interface should be mobile-friendly and accessible.

## 7. Out of scope for the initial version

- Payments or rewards for returning items.
- Automated identity verification.
- Live location tracking.
- Public posting of exact residential or highly sensitive locations.

## 8. Open decisions

- What contact method should be used between posters and claimants?
- Should claims require poster approval?
- Which general campus location categories should be offered?
- How long should resolved posts remain available?
- Should posts be limited to campus-related belongings?
