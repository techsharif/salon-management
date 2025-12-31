# [backend] - Reviews & Ratings System

**Jira Key**: [SAL-7](https://techsharif.atlassian.net/browse/SAL-7)
**Type**: Epic
**Status**: To Do
**Priority**: Medium
**Assignee**: Unassigned
**Labels**: [backend, reviews, ratings, phase1]
**Component**: Backend
**Phase**: Phase 1 (Month 5)
**Created**: 2025-12-12
**Last Updated**: 2025-12-12

## Description

This epic implements the complete reviews and ratings system that allows customers to rate and review salons after completing appointments. It includes review creation and validation, rating calculation and aggregation, photo uploads for reviews, review moderation capabilities, and verified booking badges.

The reviews and ratings system is essential for building trust and helping customers make informed decisions. It also provides valuable feedback for salons to improve their services. Reviews can only be submitted after a completed appointment to ensure authenticity.

## Scope

### Review Creation & Validation
- Create review after completed appointment
- Validate that appointment is completed
- Prevent duplicate reviews for same appointment
- Review text validation (length, content)
- Photo upload for reviews (optional)
- Rating validation (1-5 stars)

### Rating Calculation & Aggregation
- Calculate salon average rating
- Update rating when new review added
- Update rating when review deleted/modified
- Rating breakdown (how many 5-star, 4-star, etc.)
- Total review count
- Rating distribution statistics

### Review Management
- View all reviews for a salon
- View customer's review history
- Edit review (if allowed)
- Delete review (if allowed)
- Flag inappropriate reviews
- Review moderation API

### Verified Booking Badges
- Mark reviews from verified bookings
- Display "Verified Booking" badge
- Track booking verification status

### Photo Management
- Upload photos with reviews
- Photo storage and retrieval
- Photo moderation
- Photo deletion

## Key Components

- **Review Service**: Review CRUD operations
- **Rating Service**: Rating calculation and aggregation
- **Review Validation Service**: Ensure review eligibility
- **Review Moderation Service**: Content moderation tools
- **Photo Service**: Photo upload and management
- **Verification Service**: Verified booking badge logic

## Acceptance Criteria

- [ ] Customer can create review after completed appointment
- [ ] System validates appointment completion before allowing review
- [ ] System prevents duplicate reviews for same appointment
- [ ] Customer can rate salon (1-5 stars)
- [ ] Customer can write review text (optional)
- [ ] Customer can upload photos with review (optional)
- [ ] Salon average rating calculated correctly
- [ ] Rating updates automatically when review added/modified/deleted
- [ ] Rating breakdown calculated (5-star count, 4-star count, etc.)
- [ ] All reviews for salon can be retrieved
- [ ] Reviews show "Verified Booking" badge when applicable
- [ ] Admin can moderate reviews (approve/remove)
- [ ] Inappropriate reviews can be flagged
- [ ] Review photos stored and retrieved correctly
- [ ] Review API endpoints working correctly

## Technical Details

### Review Data Model
- Review ID
- Customer ID
- Salon ID
- Booking ID (links to completed appointment)
- Rating (1-5 stars)
- Review text (optional)
- Photo URLs (array, optional)
- Created timestamp
- Modified timestamp
- Status (active, flagged, removed)
- Verified booking flag

### Rating Calculation
- Average = Sum of all ratings / Total review count
- Round to 1 decimal place
- Update in real-time when review added/modified/deleted
- Handle edge cases (no reviews, single review)

### Review Validation Rules
- Appointment must be in "Completed" status
- Customer must have attended appointment (not cancelled/no-show)
- One review per completed appointment
- Review text: max 1000 characters
- Rating: required, must be 1-5
- Photos: max 5 photos per review, max 5MB each

### Review Moderation
- Admin can flag reviews
- Admin can remove inappropriate reviews
- System can auto-flag based on keywords (future)
- Removed reviews don't affect rating calculation
- Customer notified if review removed

### Dependencies
- EPIC-01 (Backend Foundation) - Database and API structure
- EPIC-02 (Authentication) - User identification
- EPIC-03 (Booking System) - Completed appointment validation
- File storage service for photos

## Related Items

- **Related Requirements**: 
  - Section 3.1 (Customer Features - Reviews & Ratings)
  - Section 3.2 (Admin Features - Content Moderation)
  - Section 3.3 (Salon Manager Features - View Customer Reviews)
  - Section 4.1 (Process Flow 1 - Step 10: Review)
- **Blocks**: Part of EPIC-04 (Customer Web App) - Review UI
- **Is Blocked By**: EPIC-01, EPIC-02, EPIC-03
- **Related Confluence Docs**: Reviews & Ratings System Design (to be created)

## Notes

- Reviews should only be allowed after completed appointments to ensure authenticity
- Rating aggregation should be efficient (consider caching)
- Photo uploads should be optimized for mobile devices
- Consider implementing review helpfulness voting (future)
- Review moderation should be quick to maintain platform quality
- Verified booking badges increase trust and review credibility
- Consider implementing response feature for salons (future)
- Rating system should handle edge cases (all 5-star, all 1-star, etc.)

## History

- 2025-12-12: Epic created

