# [frontend] - Salon Manager Web Application

**Jira Key**: [SAL-5](https://techsharif.atlassian.net/browse/SAL-5)
**Type**: Epic
**Status**: To Do
**Priority**: High
**Assignee**: Unassigned
**Labels**: [frontend, salon-manager, web-app, phase1]
**Component**: Frontend
**Phase**: Phase 1 (Month 4)
**Created**: 2025-12-12
**Last Updated**: 2025-12-12

## Description

This epic implements the complete salon manager web application that allows salon owners and managers to register their salon, manage bookings, configure services, set schedules, and manage their salon profile. The application provides a comprehensive dashboard for salon operations.

The salon manager web app is essential for salon operations and must provide efficient tools for managing daily bookings, services, and salon information. It includes registration, dashboard, booking management, service management, schedule management, and profile management features.

## Scope

### Salon Registration & Onboarding
- Multi-step registration wizard
- Phone number verification (SMS OTP)
- Basic information form (name, address, contact)
- Map location pinning
- Gender type selection (Boys/Girls/Unisex)
- Photo upload (minimum 3 photos)
- Business document upload (optional)
- Operating hours configuration
- Service addition during registration
- Submission for admin approval
- Status tracking (Pending/Approved/Rejected)

### Dashboard
- Today's overview (bookings count, upcoming appointments)
- This week preview
- Quick actions (add booking, mark completed, etc.)
- Today's completed services
- Today's cancelled bookings
- Busy days highlighted

### Booking Management
- View all bookings (Today, Upcoming, Past, Cancelled, All tabs)
- Booking list with filters (date range, status)
- Booking details view
- Accept booking (if manual approval enabled)
- Decline booking with reason
- Mark booking as completed
- Mark booking as no-show
- Cancel booking (salon side) with reason
- Add manual booking (walk-in customers)
- Search bookings by customer name

### Service Management
- View all services list
- Add new service (name, category, price, duration, description, photo)
- Edit existing service
- Delete/deactivate service
- Service status (active/inactive)
- Sort by category or name

### Schedule Management
- Set operating hours per day
- Set holidays (specific dates)
- Set off days
- Configure break times
- View schedule calendar
- Edit schedule

### Salon Profile Management
- Edit salon description
- Update contact information
- Change phone number
- Update address (requires admin approval)
- Add/remove photos
- View customer reviews
- View salon rating and statistics

### Notifications
- New booking alerts
- Cancellation alerts
- Reminder before appointments
- Daily summary (optional)

## Key Components

- **Registration Wizard**: Multi-step salon registration flow
- **Dashboard**: Overview and quick actions
- **Booking Management Interface**: Complete booking CRUD operations
- **Service Management Pages**: Service CRUD interface
- **Schedule Configuration**: Operating hours and availability setup
- **Profile Management**: Salon information editing
- **Photo Upload Interface**: Multiple photo upload and management

## Acceptance Criteria

- [ ] Salon manager can register with phone number and OTP
- [ ] Multi-step registration wizard working
- [ ] Salon manager can upload minimum 3 photos
- [ ] Salon manager can set operating hours
- [ ] Salon manager can add services during registration
- [ ] Salon manager can submit for approval
- [ ] Dashboard shows today's overview correctly
- [ ] Salon manager can view all bookings with filters
- [ ] Salon manager can accept/decline bookings
- [ ] Salon manager can mark bookings as completed
- [ ] Salon manager can mark bookings as no-show
- [ ] Salon manager can cancel bookings with reason
- [ ] Salon manager can add manual bookings (walk-ins)
- [ ] Service management (CRUD) working
- [ ] Schedule management working (hours, holidays, breaks)
- [ ] Salon manager can edit salon profile
- [ ] Salon manager can view reviews and ratings
- [ ] Notifications working for new bookings
- [ ] All forms validate input correctly

## Technical Details

### Registration Flow
1. Phone verification (SMS OTP)
2. Basic information (name, address, contact)
3. Location pinning on map
4. Gender type selection
5. Photo upload (min 3)
6. Business documents (optional)
7. Operating hours setup
8. Service addition
9. Review and submit
10. Wait for admin approval

### Booking Management Features
- Real-time booking updates
- Status filtering and sorting
- Date range filtering
- Customer search
- Quick actions (complete, cancel, no-show)

### Service Management
- Service categories (Haircut, Facial, Coloring, etc.)
- Price in BDT
- Duration in minutes
- Optional service photos
- Active/inactive toggle

### Schedule Configuration
- Day-by-day operating hours
- Break time configuration
- Holiday date selection
- Off day marking
- Visual schedule calendar

### Dependencies
- EPIC-01 (Backend Foundation) - API endpoints
- EPIC-02 (Authentication) - Login/registration APIs
- EPIC-03 (Booking System) - Booking management APIs
- EPIC-06 (Admin Portal) - Approval workflow
- EPIC-08 (Notifications) - SMS notifications

## Related Items

- **Related Requirements**: 
  - Section 3.3 (Complete Salon Manager Features)
  - Section 4.2 (Process Flow 2: Salon Registration & Approval)
  - Section 4.3 (Process Flow 3: Salon Managing a Booking)
  - Section 5.1.4 (Month 4: Salon Manager Web App)
- **Blocks**: EPIC-10 (Salon Manager Mobile App) - Mobile app will reuse web app logic
- **Is Blocked By**: EPIC-01, EPIC-02, EPIC-03, EPIC-06, EPIC-08
- **Related Confluence Docs**: Salon Manager Web App Design Document (to be created)

## Notes

- Registration wizard should save progress (allow continuation if interrupted)
- Dashboard should load quickly with essential information
- Booking management should be efficient for high-volume salons
- Service management should support bulk operations (future)
- Schedule changes should update availability immediately
- Photo upload should support multiple formats and sizes
- Consider implementing booking calendar view (visual schedule)
- Notifications should be non-intrusive but visible

## History

- 2025-12-12: Epic created

