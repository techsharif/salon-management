# [frontend] - Admin Portal

**Jira Key**: [SAL-6](https://techsharif.atlassian.net/browse/SAL-6)
**Type**: Epic
**Status**: To Do
**Priority**: High
**Assignee**: Unassigned
**Labels**: [frontend, admin, web-app, phase1]
**Component**: Frontend
**Phase**: Phase 1 (Month 4)
**Created**: 2025-12-12
**Last Updated**: 2025-12-12

## Description

This epic implements the admin web portal that allows platform administrators to manage the entire Salon Reservation Service platform. It includes salon approval/rejection workflows, user management, salon management, platform analytics, content moderation, and administrative tools.

The admin portal is critical for platform operations and quality control. It enables admins to review and approve new salon registrations, manage users and salons, monitor platform health, and handle disputes. The portal requires enhanced security with 2FA authentication.

## Scope

### Admin Authentication
- Email and password login
- Two-factor authentication (2FA) via SMS
- Secure admin session management
- Role-based access (Super Admin, Moderator, Support)
- Session timeout and security

### Salon Onboarding & Approval
- View pending salon registrations list
- Search and filter pending salons
- Review complete salon information
- View salon photos (minimum 3 required)
- View business documents
- View services and pricing
- View location on map
- Approve salon with optional notes
- Reject salon with required reason
- Notify salon manager of decision
- View approval history

### User Management
- View all users (customers, salon managers, stylists)
- Search users by name, phone, or email
- Filter by user type and status
- View user details (profile, bookings, reviews)
- Suspend user account with reason and duration
- Ban user permanently with reason
- Reactivate suspended/banned users
- View user activity timeline

### Salon Management
- View all salons (approved, pending, suspended)
- Search salons by name or location
- Filter by status
- Sort by rating, bookings, date
- View salon performance metrics
- Suspend salon with reason
- Reactivate salon
- Edit salon information (correct errors)
- View salon booking history

### Platform Analytics Dashboard
- Total users count (customers, salon managers)
- Total salons count (active, pending)
- Total bookings (today, this week, this month)
- User growth charts
- Booking trends charts
- Popular cities/areas
- Popular services
- Cancellation rates
- Export reports (PDF, Excel)
- Date range filtering

### Content Moderation
- View flagged reviews
- Approve or remove inappropriate reviews
- Handle customer-salon disputes
- View both sides of disputes
- Take appropriate actions

### Admin User Management
- Add new admin users
- Assign admin roles (Super Admin, Moderator, Support)
- Set permissions per role
- Edit admin user details
- Deactivate admin accounts
- Send invitation emails

### Activity Logs
- View all admin actions
- Filter by admin user, action type, date
- See who approved which salon
- See who suspended which user
- Full audit trail
- Immutable logs (cannot be deleted or modified)

## Key Components

- **Admin Login Page**: Email/password with 2FA
- **Pending Salons Review Page**: Salon approval/rejection interface
- **User Management Interface**: User CRUD and status management
- **Salon Management Interface**: Salon CRUD and status management
- **Analytics Dashboard**: Charts and statistics
- **Content Moderation Tools**: Review and dispute handling
- **Activity Logs Viewer**: Audit trail interface

## Acceptance Criteria

- [ ] Admin can login with email/password and 2FA
- [ ] Admin can view pending salon registrations
- [ ] Admin can review complete salon information
- [ ] Admin can approve salon with optional notes
- [ ] Admin can reject salon with required reason
- [ ] Salon manager receives SMS notification on approval/rejection
- [ ] Admin can view all users with search and filters
- [ ] Admin can suspend user with reason and duration
- [ ] Admin can ban user permanently with reason
- [ ] Admin can reactivate users
- [ ] Admin can view all salons with search and filters
- [ ] Admin can suspend/reactivate salons
- [ ] Admin can edit salon information
- [ ] Analytics dashboard shows all key metrics
- [ ] Charts display user growth and booking trends
- [ ] Admin can export reports (PDF, Excel)
- [ ] Admin can moderate reviews
- [ ] Admin can handle disputes
- [ ] Activity logs show all admin actions
- [ ] Role-based access control working
- [ ] All actions require proper permissions

## Technical Details

### Admin Roles & Permissions

**Super Admin:**
- Full access to all features
- Can manage other admins
- Can view all activity logs

**Moderator:**
- Can approve/reject salons
- Can manage users and salons
- Can moderate content
- Cannot manage other admins

**Support:**
- View-only access
- Can view user and salon information
- Can help customers
- Cannot make changes

### Salon Approval Workflow
1. Salon submits registration
2. Admin receives notification
3. Admin reviews salon information
4. Admin checks photos (minimum 3)
5. Admin verifies business documents (if uploaded)
6. Admin checks location on map
7. Admin approves or rejects
8. System notifies salon manager via SMS
9. If approved, salon goes live immediately

### Analytics Data Points
- User registrations (daily, weekly, monthly)
- Salon registrations and approvals
- Booking counts and trends
- Completion rates
- Cancellation rates
- Popular services
- Geographic distribution
- Peak booking times

### Dependencies
- EPIC-01 (Backend Foundation) - API endpoints
- EPIC-02 (Authentication) - Admin 2FA authentication
- EPIC-03 (Booking System) - Booking data for analytics
- EPIC-05 (Salon Manager Web App) - Salon registration data
- EPIC-08 (Notifications) - SMS notifications

## Related Items

- **Related Requirements**: 
  - Section 3.2 (Complete Admin Features)
  - Section 4.2 (Process Flow 2: Salon Registration & Approval)
  - Section 4.4 (Process Flow 4: Admin Managing Platform)
  - Section 5.1.5 (Month 4: Admin Web Portal)
- **Is Blocked By**: EPIC-01, EPIC-02, EPIC-03, EPIC-05, EPIC-08
- **Related Confluence Docs**: Admin Portal Design Document (to be created)

## Notes

- Admin portal requires highest security standards
- 2FA should be mandatory for all admin logins
- Activity logs are critical for compliance and auditing
- Salon approval process should be efficient (target: 5 minutes per salon)
- Analytics should update in near real-time
- Export functionality should handle large datasets
- Consider implementing bulk actions for efficiency
- Dispute handling should preserve all communication history
- Admin actions should have confirmation dialogs for critical operations

## History

- 2025-12-12: Epic created

