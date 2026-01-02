# [backend] - Salon Manager SMS OTP Authentication

**Jira Key**: [SAL-28](https://techsharif.atlassian.net/browse/SAL-28)
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

Implement SMS OTP authentication flow for salon managers. This includes phone number registration, OTP generation and sending, OTP verification, and JWT token issuance upon successful authentication.

Salon managers use phone number and SMS OTP for both registration and login (no passwords required), similar to customers.

## Acceptance Criteria

* [ ] Salon manager registration endpoint (phone number input)
* [ ] OTP generation and SMS sending on registration
* [ ] OTP verification endpoint for registration
* [ ] Salon manager account creation after OTP verification
* [ ] Salon manager login endpoint (phone number input)
* [ ] OTP generation and SMS sending on login
* [ ] OTP verification endpoint for login
* [ ] JWT token issuance after successful authentication
* [ ] Phone number validation implemented
* [ ] Existing salon manager detection (login vs registration)
* [ ] Authentication flow tested end-to-end

## Technical Details

### Registration Flow

1. Salon manager enters phone number
2. System checks if phone exists
3. If new: Generate OTP, send SMS, store OTP
4. Salon manager enters OTP
5. System validates OTP
6. Create salon manager account
7. Issue JWT token

### Login Flow

1. Salon manager enters phone number
2. System verifies phone exists
3. Generate OTP, send SMS, store OTP
4. Salon manager enters OTP
5. System validates OTP
6. Issue JWT token

### API Endpoints

* POST /api/v1/auth/salon-manager/register/request-otp
* POST /api/v1/auth/salon-manager/register/verify-otp
* POST /api/v1/auth/salon-manager/login/request-otp
* POST /api/v1/auth/salon-manager/login/verify-otp

## Related Items

* **Epic**: SAL-2 - Authentication & Authorization System
* **Depends On**: OTP Service, SMS Gateway, JWT Token Management
* **Blocks**: Salon Manager Web App (EPIC-05)

## Notes

* Reuse OTP service from customer authentication
* Ensure phone number uniqueness across user types
* Handle edge cases (expired OTP, invalid phone format)
* Provide clear error messages

