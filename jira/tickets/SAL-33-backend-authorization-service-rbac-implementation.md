# [backend] - Authorization Service (RBAC) Implementation

**Jira Key**: [SAL-33](https://techsharif.atlassian.net/browse/SAL-33)
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

Implement Role-Based Access Control (RBAC) service for authorization. This includes role definitions, permission management, permission checking, and resource-level authorization.

The authorization service ensures users can only access resources and perform actions they are permitted to based on their role.

## Acceptance Criteria

* [ ] Role definitions implemented (Customer, Salon Manager, Super Admin, Moderator, Support)
* [ ] Permission system designed and implemented
* [ ] Permission checking service implemented
* [ ] Resource-level authorization implemented
* [ ] Authorization middleware created
* [ ] Role-based route protection working
* [ ] Permission matrix documented
* [ ] Authorization service tested

## Technical Details

### Roles

* **Customer**: Can access own bookings, reviews, profile
* **Salon Manager**: Can access own salon, bookings, services, schedule
* **Super Admin**: Full access to everything
* **Moderator**: Can approve salons, manage content, view users
* **Support**: Read-only access, can view users and bookings

### Permissions

* View own resources
* View all resources (admin)
* Create resources
* Update own resources
* Update all resources (admin)
* Delete own resources
* Delete all resources (admin)
* Approve salons (moderator/admin)
* Suspend users (admin)
* View analytics (admin)

### Authorization Checks

* Check user role
* Check user permissions for action
* Check resource ownership (for customer/salon manager)
* Return 403 Forbidden if unauthorized

### Authorization Middleware

```javascript
authorize(requiredRole, requiredPermission)
```

### Resource-Level Authorization

* Verify user owns resource (e.g., booking belongs to customer)
* Verify user has permission to access resource
* Handle cross-role access (e.g., salon manager viewing customer booking)

## Related Items

* **Epic**: SAL-2 - Authentication & Authorization System
* **Depends On**: Authentication Middleware, Database Schema
* **Blocks**: All Protected API Endpoints

## Notes

* Design permission system to be extensible
* Document all role permissions clearly
* Test authorization with various user roles
* Consider implementing permission caching for performance
* Log authorization failures for security auditing

