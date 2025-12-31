# [backend] - Notifications & SMS Integration

**Jira Key**: [SAL-8](https://techsharif.atlassian.net/browse/SAL-8)
**Type**: Epic
**Status**: To Do
**Priority**: High
**Assignee**: Unassigned
**Labels**: [backend, notifications, sms, integration, phase1]
**Component**: Backend
**Phase**: Phase 1 (Months 1-5)
**Created**: 2025-12-12
**Last Updated**: 2025-12-12

## Description

This epic implements the complete notification and SMS integration system that handles all SMS communications throughout the platform. It includes SMS gateway integration, notification queue system, template management, and delivery tracking for various notification types including booking confirmations, reminders, salon approvals, and cancellations.

SMS notifications are critical for the platform as they are the primary communication method with users. The system must be reliable, handle high volumes, and provide delivery tracking. This epic spans across Phase 1 as notifications are needed from the beginning for authentication OTPs and throughout for booking-related communications.

## Scope

### SMS Gateway Integration
- Integrate with SMS gateway provider
- SMS sending service
- Delivery status tracking
- Error handling and retry logic
- Fallback mechanisms
- Cost tracking

### Notification Queue System
- Queue management for SMS notifications
- Priority handling (urgent vs. normal)
- Retry logic for failed sends
- Rate limiting
- Batch processing

### Notification Templates
- Template management system
- Template variables (customer name, salon name, date, time, etc.)
- Multi-language templates (English, Bengali)
- Template versioning

### Notification Types

**Authentication Notifications:**
- OTP codes for customer/salon manager registration
- OTP codes for login
- Admin 2FA codes

**Booking Notifications:**
- Booking confirmation SMS
- Booking reminder (24 hours before)
- Booking reminder (2 hours before)
- Booking cancellation (customer side)
- Booking cancellation (salon side)
- Booking completion notification

**Salon Management Notifications:**
- Salon approval notification
- Salon rejection notification (with reason)
- Salon status change notifications

**System Notifications:**
- Account suspension notification
- Account ban notification
- Account reactivation notification

### Delivery Tracking
- Track SMS delivery status
- Log delivery failures
- Retry failed deliveries
- Delivery reports

## Key Components

- **SMS Gateway Service**: Integration with SMS provider
- **Notification Queue Service**: Queue management and processing
- **Template Service**: Template management and rendering
- **Delivery Tracking Service**: Status tracking and reporting
- **Notification Scheduler**: Scheduled notifications (reminders)

## Acceptance Criteria

- [ ] SMS gateway integrated and working
- [ ] OTP codes sent successfully for authentication
- [ ] Booking confirmation SMS sent immediately on booking
- [ ] Booking reminder SMS sent 24 hours before appointment
- [ ] Booking reminder SMS sent 2 hours before appointment
- [ ] Cancellation SMS sent when booking cancelled
- [ ] Salon approval SMS sent when salon approved
- [ ] Salon rejection SMS sent with reason when rejected
- [ ] Notification templates working with variables
- [ ] Multi-language templates (English/Bengali) working
- [ ] Notification queue processing correctly
- [ ] Failed notifications retried automatically
- [ ] Delivery status tracked and logged
- [ ] Rate limiting prevents abuse
- [ ] Error handling for SMS gateway failures
- [ ] Fallback mechanisms working

## Technical Details

### SMS Gateway Integration
- Provider selection (local Bangladesh provider recommended)
- API integration
- Authentication and security
- Cost per SMS tracking
- Delivery status webhooks

### Notification Queue
- Queue system (Redis, RabbitMQ, or database-based)
- Priority levels (High, Normal, Low)
- Retry strategy (exponential backoff)
- Dead letter queue for failed notifications

### Template System
- Template storage (database or files)
- Variable substitution
- Language selection
- Template examples:
  - "Your OTP code is {otp_code}. Valid for 10 minutes."
  - "Booking confirmed! {salon_name} on {date} at {time}. Reference: {booking_ref}"
  - "Reminder: Your appointment at {salon_name} is in 24 hours on {date} at {time}"

### Scheduled Notifications
- Job scheduler for reminders
- Calculate reminder times (24h before, 2h before)
- Queue notifications at appropriate times
- Handle timezone considerations

### Dependencies
- EPIC-01 (Backend Foundation) - Database and API structure
- EPIC-02 (Authentication) - OTP generation
- EPIC-03 (Booking System) - Booking data for notifications
- EPIC-06 (Admin Portal) - Salon approval notifications
- SMS gateway provider account

## Related Items

- **Related Requirements**: 
  - Section 3.1 (Customer Features - SMS confirmations and reminders)
  - Section 3.2 (Admin Features - Salon approval notifications)
  - Section 3.3 (Salon Manager Features - Booking notifications)
  - Section 4 (All Process Flows - SMS notifications throughout)
- **Blocks**: All Phase 1 epics that require SMS notifications
- **Is Blocked By**: EPIC-01 (Backend Foundation)
- **Related Confluence Docs**: SMS Integration Guide (to be created)

## Notes

- SMS delivery rate target: 95%+ (as per success criteria)
- OTP codes should expire after 10 minutes
- Booking reminders should be sent at exact times (24h and 2h before)
- Notification templates should be easily editable by admins (future)
- Consider implementing SMS delivery webhooks for real-time status
- Cost tracking is important for budget management
- Rate limiting prevents SMS spam and cost overruns
- Consider implementing notification preferences (future)
- Bengali language support is critical for Bangladesh market
- SMS gateway should have good coverage in Bangladesh

## History

- 2025-12-12: Epic created

