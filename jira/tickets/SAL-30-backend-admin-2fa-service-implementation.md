# [backend] - Admin 2FA Service Implementation

**Jira Key**: [SAL-30](https://techsharif.atlassian.net/browse/SAL-30)
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

Implement two-factor authentication (2FA) service for admin users. This includes 2FA code generation, SMS sending, code validation, and integration with admin login flow.

Admin users must complete 2FA after email/password authentication for enhanced security.

## Acceptance Criteria

* [ ] 2FA code generation service implemented
* [ ] 2FA code SMS sending integrated
* [ ] 2FA code validation endpoint
* [ ] 2FA code expiration (5 minutes)
* [ ] 2FA code one-time use enforcement
* [ ] 2FA integrated with admin login flow
* [ ] 2FA rate limiting implemented
* [ ] 2FA bypass mechanism for testing (if needed)
* [ ] 2FA flow tested end-to-end

## Technical Details

### 2FA Flow

1. Admin completes email/password authentication
2. System generates 6-digit 2FA code
3. System sends code via SMS to admin's phone
4. System stores code with expiration
5. Admin enters 2FA code
6. System validates code
7. If valid: Issue JWT token and complete login
8. If invalid: Allow retry (with attempt limit)

### 2FA Code Management

* Generate secure random 6-digit codes
* Store with admin ID, expiration time, attempts
* Expire after 5 minutes
* Invalidate after successful use
* Track failed validation attempts

### Security

* Limit 2FA code requests (e.g., 3 per hour)
* Lock admin account after max failed 2FA attempts
* Log all 2FA attempts for auditing

### API Endpoints

* POST /api/v1/auth/admin/2fa/request-code
* POST /api/v1/auth/admin/2fa/verify-code

## Related Items

* **Epic**: SAL-2 - Authentication & Authorization System
* **Depends On**: Admin Email/Password Authentication, SMS Gateway, OTP Service
* **Blocks**: Admin Portal (EPIC-06)

## Notes

* 2FA codes should be different from regular OTP codes (separate service/table)
* Consider implementing backup codes for admin recovery
* Monitor 2FA success/failure rates
* Provide clear error messages for failed 2FA attempts

