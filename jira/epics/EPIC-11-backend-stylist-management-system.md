# [backend] - Stylist Management System

**Jira Key**: [SAL-11](https://techsharif.atlassian.net/browse/SAL-11)
**Type**: Epic
**Status**: To Do
**Priority**: Low
**Assignee**: Unassigned
**Labels**: [backend, stylist, phase3]
**Component**: Backend
**Phase**: Phase 3 (Months 9-10)
**Created**: 2025-12-12
**Last Updated**: 2025-12-12

## Description

This epic implements the stylist management system that allows salons to manage their staff members (stylists), assign stylists to bookings, track stylist schedules, and monitor stylist performance. This is a Phase 3 enhancement that adds individual stylist management capabilities to the platform.

The stylist management system enables salons to offer customers the option to choose specific stylists, manage stylist schedules, and track individual stylist performance. This feature enhances the booking experience by allowing customers to book with preferred stylists.

## Scope

### Stylist CRUD Operations
- Create stylist profiles (name, photo, phone, bio)
- Update stylist information
- Delete/deactivate stylists
- View all stylists for a salon
- Stylist profile management

### Stylist Schedule Management
- Set stylist working hours per day
- Set stylist weekly schedule
- Mark stylist vacation/time-off
- Handle stylist availability
- Stylist schedule conflicts detection

### Stylist Assignment to Bookings
- Assign stylist to booking during creation
- Customer can select preferred stylist (or "No Preference")
- Auto-assign stylist based on availability
- Reassign stylist to booking
- View stylist's upcoming bookings

### Stylist Performance Tracking
- Track bookings per stylist
- Calculate stylist ratings (from customer reviews)
- Track services completed per stylist
- Stylist performance analytics
- Stylist revenue tracking (if applicable)

### Stylist Availability
- Calculate stylist availability
- Consider stylist schedule
- Consider stylist existing bookings
- Show available stylists for time slot
- Handle stylist breaks and time-off

## Key Components

- **Stylist Service**: Stylist CRUD operations
- **Stylist Schedule Service**: Schedule management
- **Stylist Assignment Service**: Booking assignment logic
- **Stylist Availability Service**: Availability calculation
- **Stylist Performance Service**: Analytics and tracking

## Acceptance Criteria

- [ ] Salon manager can add stylists
- [ ] Salon manager can edit stylist information
- [ ] Salon manager can delete/deactivate stylists
- [ ] Salon manager can set stylist working hours
- [ ] Salon manager can set stylist weekly schedule
- [ ] Salon manager can mark stylist vacation/time-off
- [ ] Customer can select preferred stylist during booking
- [ ] System can auto-assign stylist based on availability
- [ ] Stylist can be assigned to booking
- [ ] Stylist availability calculated correctly
- [ ] Stylist's upcoming bookings can be viewed
- [ ] Stylist performance metrics tracked
- [ ] Stylist ratings calculated from reviews
- [ ] Stylist schedule conflicts detected
- [ ] Stylist API endpoints working correctly

## Technical Details

### Stylist Data Model
- Stylist ID
- Salon ID
- Name
- Photo URL
- Phone number
- Bio/Description
- Status (active, inactive)
- Created timestamp
- Services assigned (array of service IDs)

### Stylist Schedule
- Day of week
- Working hours (start, end)
- Break times
- Vacation dates
- Time-off periods

### Stylist Assignment Logic
1. Customer selects preferred stylist (or "No Preference")
2. If stylist selected, check availability for time slot
3. If available, assign stylist to booking
4. If not available, suggest alternative times or stylists
5. If "No Preference", auto-assign based on availability

### Stylist Performance Metrics
- Total bookings
- Completed bookings
- Cancelled bookings
- Average rating
- Total reviews
- Services completed count
- Revenue (if applicable)

### Dependencies
- EPIC-01 (Backend Foundation) - Database and API structure
- EPIC-02 (Authentication) - User identification
- EPIC-03 (Booking System) - Booking assignment
- EPIC-05 (Salon Manager Web App) - Stylist management UI
- EPIC-07 (Reviews & Ratings) - Stylist ratings

## Related Items

- **Related Requirements**: 
  - Section 3.1 (Customer Features - Optional: Choose Stylist - Phase 2)
  - Section 3.3 (Salon Manager Features - Stylist Management - Phase 2)
  - Section 5.3 (Phase 3: Enhanced Features)
- **Blocks**: Stylist selection UI in customer and salon manager apps
- **Is Blocked By**: EPIC-01, EPIC-02, EPIC-03, EPIC-05, EPIC-07
- **Related Confluence Docs**: Stylist Management System Design (to be created)

## Notes

- Stylist management is a Phase 3 feature (enhancement)
- Customer stylist selection was mentioned as Phase 2 in requirements, but full stylist management is Phase 3
- Stylist availability calculation must consider schedule, existing bookings, and time-off
- Auto-assignment should balance workload across stylists
- Stylist performance tracking helps salons optimize staffing
- Consider implementing stylist-specific ratings and reviews
- Stylist schedules should integrate with salon operating hours
- Consider implementing stylist commission tracking (future)

## History

- 2025-12-12: Epic created

