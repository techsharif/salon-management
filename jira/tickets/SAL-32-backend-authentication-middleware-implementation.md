# [backend] - Authentication Middleware Implementation

**Jira Key**: [SAL-32](https://techsharif.atlassian.net/browse/SAL-32)
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

Implement authentication middleware to protect API endpoints. This middleware validates JWT tokens, extracts user information, and attaches user context to requests.

All protected API endpoints require valid authentication tokens, and this middleware enforces that requirement.

## Acceptance Criteria

* [ ] Authentication middleware implemented
* [ ] JWT token extraction from request headers/cookies
* [ ] Token validation logic integrated
* [ ] User context attachment to request object
* [ ] Unauthorized request handling (401 responses)
* [ ] Token expiration handling
* [ ] Middleware applied to protected routes
* [ ] Public routes excluded from authentication
* [ ] Middleware tested with various scenarios

## Technical Details

### Middleware Flow

1. Extract token from Authorization header or cookie
2. If no token: Return 401 Unauthorized
3. Validate token signature and expiration
4. If invalid: Return 401 Unauthorized
5. Extract user information from token payload
6. Verify user exists and is active
7. Attach user to request object (req.user)
8. Continue to next middleware/route handler

### Token Extraction

* Check Authorization header: `Bearer <token>`
* Check httpOnly cookie (if using cookies)
* Support both methods for flexibility

### Error Handling

* 401 Unauthorized: No token or invalid token
* 403 Forbidden: Valid token but insufficient permissions (handled by authorization middleware)
* Clear error messages for debugging

### Middleware Application

* Apply to all routes by default
* Exclude public routes (registration, login, health check)
* Apply per-route or route-group basis

### User Context

Attach to request:

```javascript
req.user = {
  id: "123",
  type: "customer",
  role: "customer"
}
```

## Related Items

* **Epic**: SAL-2 - Authentication & Authorization System
* **Depends On**: JWT Token Management Service
* **Blocks**: All Protected API Endpoints

## Notes

* Middleware should be fast and efficient
* Cache user lookups if needed for performance
* Log authentication failures for security monitoring
* Consider implementing request rate limiting per user

