# [backend] - Database Schema Design & Documentation

**Jira Key**: [SAL-18](https://techsharif.atlassian.net/browse/SAL-18)
**Type**: Task
**Status**: To Do
**Priority**: Highest
**Assignee**: Unassigned
**Labels**: [backend, database, schema, design, phase1]
**Component**: Backend
**Epic**: [SAL-1](https://techsharif.atlassian.net/browse/SAL-1)
**Created**: 2025-12-20
**Last Updated**: 2025-12-20

## Description

Design and document the complete PostgreSQL database schema for the Salon Reservation Service platform. This includes designing all tables, relationships, constraints, indexes, and planning for scalability and performance.

The database schema is the foundation of the entire platform and must support all features including user management, salon management, bookings, reviews, schedules, and notifications.

## Acceptance Criteria

- [ ] Complete database schema designed
- [ ] All core tables designed (users, admins, salons, services, bookings, reviews, schedules, notifications, files)
- [ ] Table relationships and foreign keys defined
- [ ] Constraints defined (NOT NULL, UNIQUE, CHECK, etc.)
- [ ] Indexes designed for common queries
- [ ] Primary keys defined for all tables
- [ ] Schema documented with ER diagrams
- [ ] Data types chosen appropriately
- [ ] Future scalability considered (stylists, payments, etc.)
- [ ] Schema reviewed and approved
- [ ] Migration scripts prepared

## Technical Details

### Core Tables

**User Management:**
- `users` - Customer and salon manager accounts
- `admins` - Platform administrator accounts

**Salon Management:**
- `salons` - Salon information and metadata
- `services` - Service definitions per salon
- `salon_photos` - Salon photos

**Booking System:**
- `bookings` - Appointment records
- `booking_services` - Many-to-many relationship (bookings to services)

**Reviews & Ratings:**
- `reviews` - Customer reviews and ratings
- `review_photos` - Photos attached to reviews

**Schedule Management:**
- `schedules` - Operating hours per salon
- `holidays` - Holiday dates per salon
- `break_times` - Break times per salon

**Notifications:**
- `notifications` - Notification records

**File Management:**
- `files` - Uploaded photos and documents

### Relationships
- Users → Salons (one-to-many)
- Salons → Services (one-to-many)
- Salons → Bookings (one-to-many)
- Users → Bookings (one-to-many)
- Bookings → Services (many-to-many)
- Salons → Reviews (one-to-many)
- Users → Reviews (one-to-many)

### Indexes
- Primary keys on all tables
- Foreign key indexes
- Common query indexes (salon_id, user_id, booking_date, etc.)
- Composite indexes for complex queries

## Related Items

- **Epic**: [SAL-1](https://techsharif.atlassian.net/browse/SAL-1) - Backend Foundation & Infrastructure
- **Depends On**: SAL-14 (Repository Setup)
- **Blocks**: SAL-19 (Database Migration System)

## Notes

- Design schema with future features in mind (stylists, payments, etc.)
- Consider performance from the start (indexes, query optimization)
- Use appropriate data types (timestamps, enums, etc.)
- Plan for scalability (partitioning, sharding considerations)
- Document all design decisions
- Create ER diagrams for visualization

## History

- 2025-12-20: Task created

