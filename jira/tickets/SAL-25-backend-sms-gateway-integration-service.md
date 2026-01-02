# [backend] - SMS Gateway Integration Service

**Jira Key**: [SAL-25](https://techsharif.atlassian.net/browse/SAL-25)
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

Integrate SMS gateway provider for sending OTP codes and notifications. This includes setting up the SMS service, configuring templates, handling delivery tracking, and implementing error handling with fallback mechanisms.

This service is critical for authentication as it enables OTP delivery for customer and salon manager registration/login, as well as admin 2FA.

## Acceptance Criteria

* [ ] SMS gateway provider selected and account configured
* [ ] SMS service implemented with provider SDK/API
* [ ] OTP message templates created
* [ ] SMS sending functionality working
* [ ] Delivery tracking implemented
* [ ] Error handling and retry logic implemented
* [ ] Fallback mechanism for SMS failures (if applicable)
* [ ] SMS service tested with real phone numbers
* [ ] Rate limiting considerations documented
* [ ] SMS service integrated with OTP service

## Technical Details

### SMS Gateway Options

* Twilio, Nexmo, AWS SNS, or local Bangladesh SMS providers
* Consider cost, delivery rate, and reliability

### SMS Templates

* OTP code: "Your verification code is {code}. Valid for 10 minutes."
* Admin 2FA: "Your admin login code is {code}. Valid for 5 minutes."

### Error Handling

* Handle provider API failures
* Log failed SMS attempts
* Implement retry logic with exponential backoff
* Consider alternative providers for fallback

## Related Items

* **Epic**: SAL-2 - Authentication & Authorization System
* **Blocks**: OTP Service, Customer Authentication, Salon Manager Authentication, Admin 2FA
* **Depends On**: SAL-1 (Backend Foundation)

## Notes

* Choose SMS provider based on Bangladesh coverage and cost
* Test SMS delivery in target regions
* Monitor SMS delivery rates and costs
* Consider implementing SMS queue for high volume

