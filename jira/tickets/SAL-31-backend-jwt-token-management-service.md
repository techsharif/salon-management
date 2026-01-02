# [backend] - JWT Token Management Service

**Jira Key**: [SAL-31](https://techsharif.atlassian.net/browse/SAL-31)
**Type**: Task
**Status**: To Do
**Priority**: Medium
**Assignee**: Unassigned
**Labels**: []
**Component**: Backend
**Epic**: [SAL-2](https://techsharif.atlassian.net/browse/SAL-2) - Authentication & Authorization System
**Created**: 2026-01-03
**Last Updated**: 2026-01-03

## Description

Implement JWT (JSON Web Token) token management service for authentication. This includes token generation, validation, refresh mechanism, and token expiration handling.

JWT tokens are used to maintain user sessions across all user types (customers, salon managers, admins).

## Acceptance Criteria

* [ ] JWT token generation service implemented
* [ ] JWT token validation service implemented
* [ ] Token payload structure defined (user ID, role, type)
* [ ] Token expiration configured (access token: 15min-1hr, refresh token: 7-30 days)
* [ ] Token refresh endpoint implemented
* [ ] Token blacklisting mechanism (for logout)
* [ ] Secure token signing (secret key management)
* [ ] Token validation middleware ready
* [ ] Token service tested

## Technical Details

### Token Types

* **Access Token**: Short-lived (15 minutes to 1 hour), contains user info
* **Refresh Token**: Long-lived (7-30 days), used to get new access tokens

### Token Payload

```json
{
  "userId": "123",
  "userType": "customer|salon_manager|admin",
  "role": "customer|salon_manager|super_admin|moderator|support",
  "iat": 1234567890,
  "exp": 1234567890
}
```

### Token Generation

* Sign tokens with secret key (from environment)
* Include user ID, type, and role in payload
* Set appropriate expiration times
* Generate refresh tokens separately

### Token Refresh Flow

1. Client sends refresh token
2. System validates refresh token
3. System checks if refresh token is blacklisted
4. If valid: Generate new access token
5. Return new access token

### Security

* Use strong secret keys (from environment variables)
* Implement token blacklisting for logout
* Validate token signature on every request
* Handle token expiration gracefully

### API Endpoints

* POST /api/v1/auth/refresh-token

## Related Items

* **Epic**: SAL-2 - Authentication & Authorization System
* **Depends On**: Database Schema, Environment Configuration
* **Blocks**: Authentication Middleware, All Authentication Flows

## Notes

* Use industry-standard JWT libraries
* Store refresh tokens securely (httpOnly cookies or secure storage)
* Consider implementing token rotation for enhanced security
* Monitor token usage and expiration patterns

