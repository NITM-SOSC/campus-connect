# Student Marketplace — Requirements

**Status:** Proposed; requires maintainer review.  
**Scope:** Student-to-student listings for permitted goods or services within the campus community.  
**Implementation status:** Not implemented.

## 1. Purpose

Provide a simple campus-focused place for students to discover and post permitted listings. The module is intended to support community exchanges, not to operate as a payment processor or guarantee transactions.

## 2. Users and access

- Signed-in members can browse published listings.
- Members can create and manage their own listings.
- Members can contact a listing owner through an approved contact method.
- Authorized moderators can review reports and moderate listings.
- Exact role and permission mappings must follow the approved application authorization design.

## 3. Functional requirements

### Listing creation
- Members shall be able to create a listing with a title, description, category, and listing type.
- A listing may include images, condition, approximate price or indicate that the price is negotiable, and a general campus-area handover location.
- The system shall identify the listing owner.
- Members shall be able to edit or remove their own listings.
- The system shall support listing states such as available, reserved, completed, and removed.
- The system should require users to confirm that their listing follows marketplace rules.

### Browsing and discovery
- Members shall be able to browse published listings.
- Members should be able to search by title or description and filter by category, listing type, or status.
- Each listing shall display its current status and date posted.
- Completed or removed listings shall not appear among active listings by default.

### Contact and transaction coordination
- Interested members shall be able to contact the listing owner using the approved contact route.
- Private contact information shall not be exposed publicly by default.
- The module shall make clear that users are responsible for assessing listings and arranging exchanges safely.
- The system shall not claim to verify the condition, ownership, or quality of listed items.
- The initial release shall not process payments.

### Reporting and moderation
- Members shall be able to report a listing or user for suspected scams, prohibited items, misleading information, or inappropriate content.
- Authorized moderators shall be able to review reports and take permitted action.
- Moderation actions should record the reason, action, actor, and timestamp.
- The system shall support removing or hiding listings that violate the marketplace rules.

## 4. Marketplace safety rules

- Listings must comply with applicable law and campus rules.
- Weapons, dangerous items, illegal goods, controlled substances, alcohol, nicotine products, and other age-restricted or hazardous goods must not be listed.
- Stolen, counterfeit, or unlawfully obtained goods must not be listed.
- Adult or sexually explicit products and content must not be listed.
- Listings must not solicit sensitive personal information or encourage unsafe exchanges.
- The final prohibited-items policy must be reviewed and published before the marketplace is enabled.

## 5. Main user flows

1. A student browses active listings.
2. The student searches or filters for an item.
3. A member creates a listing and publishes it.
4. Another member contacts the listing owner.
5. The owner updates the listing status when it is reserved or completed.
6. A member reports a suspicious listing.
7. An authorized moderator reviews the report and records an outcome.

## 6. Validation and error handling

- Required title, description, category, and listing type must be present.
- Price fields, if used, must accept only valid non-negative values.
- Images must be checked for supported file types and size.
- Users must not edit or remove listings owned by other members unless authorized.
- The system should prevent duplicate active submissions where practical.
- A removed or completed listing must not be presented as available.

## 7. Security and quality requirements

- Backend authorization must enforce listing ownership and moderation permissions.
- User-submitted text, images, and links must be handled safely.
- Private contact details must not be included in public listing responses.
- The module should provide clear guidance to avoid sharing personal addresses or meeting alone in isolated places.
- The interface should be responsive and accessible.
- The system should provide a clear reporting route.

## 8. Out of scope for the initial version

- In-app payments, escrow, or refunds.
- Shipping and delivery management.
- Automated price recommendations.
- Public ratings or reputation scores.
- Guaranteed transaction protection.

## 9. Open decisions

- Which listing categories are permitted?
- Are services as well as physical goods allowed?
- Should listings require moderator approval before publication?
- What contact method should be used?
- What listing duration and renewal rules should apply?
- What additional campus-specific rules should govern exchanges?
