# [backend] - Admin Email/Password Authentication

**Jira Key**: [SAL-29](https://techsharif.atlassian.net/browse/SAL-29)
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

Implement email and password authentication for admin users. This includes admin registration (if applicable), login with email/password, password hashing, and secure credential validation.

Admin users require stronger authentication than customers/salon managers, starting with email and password before 2FA.

## Acceptance Criteria

* [ ] Admin login endpoint (email and password)
* [ ] Password hashing implemented (bcrypt or similar)
* [ ] Password validation and strength requirements
* [ ] Email validation implemented
* [ ] Credential verification working
* [ ] Failed login attempt tracking
* [ ] Account lockout after multiple failed attempts
* [ ] Secure password storage in database
* [ ] Admin session initialization after successful login
* [ ] Authentication flow tested

## Technical Details

### Login Flow

1. Admin enters email and password
2. System validates email format
3. System retrieves admin by email
4. System verifies password hash
5. System checks account status (active/locked)
6. System tracks login attempt
7. If valid: Initialize 2FA flow
8. If invalid: Increment failed attempts, lock if threshold reached

### Password Security

* Use bcrypt or Argon2 for password hashing
* Minimum password requirements (length, complexity)
* Salt passwords automatically
* Never store plain text passwords

### Account Security

* Track failed login attempts
* Lock account after N failed attempts (e.g., 5 attempts)
* Implement lockout duration (e.g., 30 minutes)
* Log all login attempts for security auditing

### API Endpoints

* POST /api/v1/auth/admin/login

## Related Items

* **Epic**: SAL-2 - Authentication & Authorization System
* **Depends On**: Database Schema (admins table), Password Hashing Service
* **Blocks**: Admin 2FA Service

## Notes

* Admin accounts should be created manually or through separate admin creation process
* Consider implementing password reset flow (future task)
* Implement proper logging for security auditing
* Use secure password hashing algorithms

