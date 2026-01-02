# [backend] - Customer SMS OTP Authentication

**Jira Key**: [SAL-27](https://techsharif.atlassian.net/browse/SAL-27)
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

Implement SMS OTP authentication flow for customers. This includes phone number registration, OTP generation and sending, OTP verification, and JWT token issuance upon successful authentication.

Customers use phone number and SMS OTP for both registration and login (no passwords required).

## Acceptance Criteria

* [ ] Customer registration endpoint (phone number input)
* [ ] OTP generation and SMS sending on registration
* [ ] OTP verification endpoint for registration
* [ ] Customer account creation after OTP verification
* [ ] Customer login endpoint (phone number input)
* [ ] OTP generation and SMS sending on login
* [ ] OTP verification endpoint for login
* [ ] JWT token issuance after successful authentication
* [ ] Phone number validation implemented
* [ ] Existing customer detection (login vs registration)
* [ ] Authentication flow tested end-to-end

## Technical Details

### Registration Flow

1. Customer enters phone number
2. System checks if phone exists
3. If new: Generate OTP, send SMS, store OTP
4. Customer enters OTP
5. System validates OTP
6. Create customer account
7. Issue JWT token

### Login Flow

1. Customer enters phone number
2. System verifies phone exists
3. Generate OTP, send SMS, store OTP
4. Customer enters OTP
5. System validates OTP
6. Issue JWT token

### API Endpoints

* POST /api/v1/auth/customer/register/request-otp
* POST /api/v1/auth/customer/register/verify-otp
* POST /api/v1/auth/customer/login/request-otp
* POST /api/v1/auth/customer/login/verify-otp

## Related Items

* **Epic**: SAL-2 - Authentication & Authorization System
* **Depends On**: OTP Service, SMS Gateway, JWT Token Management
* **Blocks**: Customer Web App (EPIC-04)

## Notes

* Phone numbers should be normalized (format consistency)
* Handle edge cases (expired OTP, invalid phone format)
* Provide clear error messages
* Consider implementing "Resend OTP" functionality

