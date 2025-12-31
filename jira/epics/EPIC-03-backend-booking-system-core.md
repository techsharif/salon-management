# [backend] - Booking System Core

**Jira Key**: [SAL-3](https://techsharif.atlassian.net/browse/SAL-3)
**Type**: Epic
**Status**: To Do
**Priority**: Highest
**Assignee**: Unassigned
**Labels**: [backend, booking, scheduling, availability, phase1]
**Component**: Backend
**Phase**: Phase 1 (Months 1-2)
**Created**: 2025-12-12
**Last Updated**: 2025-12-12

## Description

This epic implements the core booking system that is the heart of the Salon Reservation Service platform. It includes booking creation and management, availability calculation engine, time slot management, booking status workflow, cancellation logic, and schedule conflict detection.

The booking system must handle complex scenarios including multiple services, overlapping time slots, schedule changes, and real-time availability updates. It serves as the foundation for both customer booking flows and salon management features.

## Scope

### Booking Creation & Management
- Create new bookings with service selection
- Handle multiple services in single booking
- Booking validation and conflict checking
- Booking status management (Pending, Confirmed, Completed, Cancelled, No-Show)
- Booking modification (Phase 2 feature)

### Availability Calculation Engine
- Calculate available time slots based on:
  - Salon operating hours
  - Existing bookings
  - Service duration
  - Break times
  - Holidays and off days
- Real-time availability updates
- Support for 30-day booking window

### Time Slot Management
- Time slot generation (e.g., 30-minute intervals)
- Slot availability tracking
- Slot conflict detection
- Slot reservation during booking flow

### Booking Status Workflow
- State machine for booking statuses
- Status transition rules
- Automatic status updates (e.g., past appointments)
- Status change notifications

### Cancellation Logic
- Customer cancellation (2+ hours before)
- Salon cancellation
- Automatic slot release on cancellation
- Cancellation reason tracking

### Schedule Conflict Detection
- Prevent double-booking
- Handle overlapping services
- Validate against operating hours
- Check for holidays and breaks

## Key Components

- **Booking Service**: Core booking CRUD operations
- **Availability Service**: Calculate and manage available time slots
- **Schedule Service**: Manage salon schedules and operating hours
- **Conflict Detection Service**: Prevent booking conflicts
- **Booking State Machine**: Manage booking status transitions
- **Time Slot Service**: Generate and manage time slots

## Acceptance Criteria

- [ ] Booking creation API working
- [ ] Multiple services can be booked in single appointment
- [ ] Availability calculation engine working correctly
- [ ] Time slots generated based on service duration
- [ ] Booking status workflow implemented (all statuses)
- [ ] Conflict detection prevents double-booking
- [ ] Cancellation logic working (customer and salon)
- [ ] Slot release on cancellation working
- [ ] Booking validation against operating hours
- [ ] Holiday and break time handling
- [ ] 30-day booking window enforced
- [ ] Real-time availability updates
- [ ] Booking history tracking

## Technical Details

### Booking Status Flow
```
Pending → Confirmed → Completed
   ↓         ↓
Cancelled  Cancelled
   ↓
No-Show
```

### Availability Calculation Logic
1. Get salon operating hours for selected date
2. Get all existing bookings for that date
3. Get service duration(s)
4. Generate time slots based on operating hours
5. Mark slots as unavailable if:
   - Overlaps with existing booking
   - Falls during break time
   - Outside operating hours
   - On holiday/off day
6. Return available slots

### Booking Data Model
- Booking ID
- Customer ID
- Salon ID
- Service IDs (array)
- Date and time
- Duration
- Status
- Created timestamp
- Cancellation reason (if applicable)
- Completion timestamp

### Dependencies
- EPIC-01 (Backend Foundation) - Database and API structure
- EPIC-02 (Authentication) - User identification
- Salon schedule data
- Service definitions

## Related Items

- **Related Requirements**: 
  - Section 3.1 (Customer Features - Booking Appointments, Managing Bookings)
  - Section 3.3 (Salon Manager Features - Booking Management)
  - Section 4.1 (Process Flow 1: Customer Booking an Appointment)
  - Section 4.3 (Process Flow 3: Salon Managing a Booking)
- **Blocks**: EPIC-04 (Customer Web App), EPIC-05 (Salon Manager Web App)
- **Is Blocked By**: EPIC-01 (Backend Foundation), EPIC-02 (Authentication)
- **Related Confluence Docs**: Booking System Architecture (to be created)

## Notes

- Availability calculation must be efficient (consider caching)
- Handle edge cases: same customer booking multiple times, rapid cancellations
- Consider implementing booking locks during checkout process
- Time slots should account for service duration (not just start time)
- Support for "buffer time" between bookings (future enhancement)
- Booking modifications (Phase 2) should reuse cancellation and creation logic

## History

- 2025-12-12: Epic created

