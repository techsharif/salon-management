# [backend] - Authentication & Authorization System

**Jira Key**: [SAL-2](https://techsharif.atlassian.net/browse/SAL-2)
**Type**: Epic
**Status**: To Do
**Priority**: Highest
**Assignee**: Unassigned
**Labels**: [backend, authentication, security, sms, phase1]
**Component**: Backend
**Phase**: Phase 1 (Months 1-2)
**Created**: 2025-12-12
**Last Updated**: 2025-12-12

## Description

This epic implements the complete authentication and authorization system for the Salon Reservation Service platform. It includes SMS OTP authentication for customers and salon managers, two-factor authentication (2FA) for admin users, role-based access control, and session management.

The authentication system is critical for securing the platform and enabling user-specific features. It must support three distinct user types (Customers, Salon Managers, Admins) with different authentication methods and permission levels.

## Scope

### SMS OTP Authentication
- Phone number-based registration for customers
- Phone number-based registration for salon managers
- SMS OTP generation and validation
- OTP expiration and rate limiting
- Login flow with SMS verification

### Admin Authentication
- Email and password authentication for admins
- Two-factor authentication (2FA) via SMS
- Secure admin session management
- Admin role management (Super Admin, Moderator, Support)

### Authorization & Access Control
- Role-based access control (RBAC) system
- Permission management per role
- API endpoint protection
- Resource-level authorization

### Session Management
- JWT token generation and validation
- Token refresh mechanism
- Session timeout handling
- Secure token storage

## Key Components

- **SMS Gateway Integration**: Service for sending OTP codes via SMS
- **OTP Service**: Generation, validation, and expiration handling
- **Authentication Middleware**: API protection and user verification
- **Authorization Service**: Role and permission checking
- **JWT Token Management**: Token creation, validation, refresh
- **Admin 2FA Service**: Two-factor authentication for admin users

## Acceptance Criteria

- [ ] SMS OTP authentication working for customers
- [ ] SMS OTP authentication working for salon managers
- [ ] Admin email/password authentication implemented
- [ ] Admin 2FA (SMS-based) working
- [ ] JWT token generation and validation working
- [ ] Role-based access control implemented
- [ ] API endpoints protected with authentication middleware
- [ ] Session management and timeout handling working
- [ ] OTP rate limiting implemented (prevent abuse)
- [ ] Token refresh mechanism working
- [ ] Password reset flow for admins (if needed)
- [ ] Secure password hashing implemented

## Technical Details

### Authentication Flows

**Customer/Salon Manager Flow:**
1. User enters phone number
2. System generates 6-digit OTP
3. OTP sent via SMS
4. User enters OTP
5. System validates OTP
6. JWT token issued on success

**Admin Flow:**
1. Admin enters email and password
2. System validates credentials
3. System generates 2FA code
4. Code sent via SMS
5. Admin enters 2FA code
6. System validates code
7. JWT token issued on success

### SMS Integration
- Integration with SMS gateway provider
- Template management for OTP messages
- Delivery tracking and error handling
- Fallback mechanisms for SMS failures

### Security Considerations
- OTP expiration (5-10 minutes)
- Rate limiting (max 3 OTP requests per phone per hour)
- Secure token storage (httpOnly cookies or secure storage)
- Password hashing (bcrypt or similar)
- Token expiration and refresh

### Dependencies
- EPIC-01 (Backend Foundation) - Database and API structure
- EPIC-08 (Notifications & SMS) - SMS gateway service
- SMS gateway provider account

## Related Items

- **Related Requirements**: 
  - Section 3.1 (Customer Features - Registration & Login)
  - Section 3.3 (Salon Manager Features - Registration & Setup)
  - Section 3.2 (Admin Features - Admin Access)
  - Section 4 (Process Flows - Authentication steps)
- **Blocks**: EPIC-04 (Customer Web App), EPIC-05 (Salon Manager Web App), EPIC-06 (Admin Portal)
- **Is Blocked By**: EPIC-01 (Backend Foundation)
- **Related Confluence Docs**: Authentication Architecture Document (to be created)

## Notes

- SMS OTP is the primary authentication method for customers and salon managers (no passwords)
- Admin accounts require stronger security with 2FA
- Consider implementing account lockout after failed attempts
- OTP codes should be stored securely and expired after use
- Token refresh should be seamless for users
- Consider implementing "Remember Me" functionality for better UX

## History

- 2025-12-12: Epic created

