# [backend] - OTP Service Implementation

**Jira Key**: [SAL-26](https://techsharif.atlassian.net/browse/SAL-26)
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

Implement OTP (One-Time Password) service for generating, validating, and managing OTP codes. This includes OTP generation, expiration handling, rate limiting, and secure storage.

The OTP service is the core component for SMS-based authentication for customers and salon managers.

## Acceptance Criteria

* [ ] OTP generation service implemented (6-digit codes)
* [ ] OTP validation service implemented
* [ ] OTP expiration mechanism (5-10 minutes)
* [ ] OTP rate limiting implemented (max 3 requests per phone per hour)
* [ ] OTP storage in database (with expiration timestamps)
* [ ] OTP one-time use enforcement (invalidate after use)
* [ ] OTP cleanup job for expired codes
* [ ] OTP service integrated with SMS gateway
* [ ] OTP service tested with various scenarios
* [ ] Security measures implemented (prevent brute force)

## Technical Details

### OTP Generation

* Generate random 6-digit numeric codes
* Ensure codes are cryptographically secure
* Store OTP with phone number, expiration time, and attempt count

### OTP Storage

* Store in database table (otps or similar)
* Include: phone_number, code, expires_at, attempts, created_at
* Index on phone_number and expires_at for performance

### Rate Limiting

* Track OTP requests per phone number
* Limit to 3 requests per hour per phone number
* Return appropriate error messages when rate limited

### Security

* Invalidate OTP after successful use
* Track failed validation attempts
* Lock OTP after max failed attempts (e.g., 5 attempts)
* Clean up expired OTPs regularly

## Related Items

* **Epic**: SAL-2 - Authentication & Authorization System
* **Depends On**: SAL-1 (Database Schema), SMS Gateway Integration
* **Blocks**: Customer Authentication, Salon Manager Authentication

## Notes

* OTP codes should be unique and unpredictable
* Consider implementing OTP resend functionality
* Monitor OTP generation and validation rates
* Implement proper logging for security auditing

