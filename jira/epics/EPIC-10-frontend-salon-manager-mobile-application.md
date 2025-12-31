# [frontend] - Salon Manager Mobile Application

**Jira Key**: [SAL-10](https://techsharif.atlassian.net/browse/SAL-10)
**Type**: Epic
**Status**: To Do
**Priority**: Medium
**Assignee**: Unassigned
**Labels**: [frontend, salon-manager, mobile-app, react-native, phase2]
**Component**: Frontend
**Phase**: Phase 2 (Months 6-7)
**Created**: 2025-12-12
**Last Updated**: 2025-12-12

## Description

This epic implements the salon manager mobile application for iOS and Android using React Native. The mobile app provides feature parity with the salon manager web application, optimized for mobile devices with native UI components, push notifications for new bookings, and mobile-optimized booking management.

The mobile app enables salon managers to manage their salon operations on-the-go, receive instant notifications for new bookings, and manage appointments from their mobile devices. It includes all salon manager features from the web app with mobile-specific optimizations.

## Scope

### Mobile App Foundation
- React Native project setup
- iOS and Android configuration
- Navigation structure
- State management
- API integration
- Error handling

### Feature Parity with Web App
- Phone number login with OTP
- Salon dashboard (mobile-optimized)
- Booking management (view, accept, decline, complete, cancel)
- Service management (view, add, edit)
- Schedule management (view, edit operating hours)
- Salon profile management
- View reviews and ratings
- Add manual bookings (walk-ins)

### Mobile-Specific Features
- Push notifications for new bookings
- Push notifications for cancellations
- Quick actions from notifications
- Mobile-optimized dashboard
- Touch-optimized booking management
- Photo upload from mobile camera
- Offline support (view bookings, cached data)

### Mobile UI/UX
- Native navigation patterns
- Mobile-friendly dashboard
- Touch-optimized booking cards
- Swipe gestures for actions
- Pull-to-refresh
- Mobile-optimized forms
- Camera integration for photos

## Key Components

- **Mobile Navigation**: React Navigation setup
- **Login Screen**: OTP authentication
- **Dashboard**: Mobile-optimized overview
- **Booking Management**: Mobile booking interface
- **Service Management**: Mobile service CRUD
- **Schedule Management**: Mobile schedule configuration
- **Push Notification Handler**: Real-time booking alerts
- **Photo Upload**: Camera and gallery integration

## Acceptance Criteria

- [ ] React Native app builds for iOS and Android
- [ ] App published to App Store and Play Store
- [ ] Salon manager can login with phone number and OTP
- [ ] Dashboard shows today's overview
- [ ] Salon manager can view all bookings
- [ ] Salon manager can accept/decline bookings
- [ ] Salon manager can mark bookings as completed
- [ ] Salon manager can mark bookings as no-show
- [ ] Salon manager can cancel bookings
- [ ] Salon manager can add manual bookings
- [ ] Push notifications working for new bookings
- [ ] Quick actions from notifications working
- [ ] Salon manager can manage services
- [ ] Salon manager can edit schedule
- [ ] Salon manager can view reviews
- [ ] Photo upload from camera working
- [ ] App works offline (view cached data)
- [ ] App performance is smooth
- [ ] App handles network errors gracefully

## Technical Details

### Technology Stack
- React Native (Expo as per user rules)
- TypeScript (.tsx files)
- React Navigation
- State management (Context API or Zustand)
- Push notifications (Expo Notifications)
- Camera integration (Expo Camera)
- Image picker (Expo Image Picker)

### Mobile-Specific Considerations
- Real-time booking updates
- Push notification handling in foreground and background
- Quick actions from notification (accept/decline booking)
- Mobile-optimized dashboard with key metrics
- Touch-friendly booking cards
- Swipe actions for common operations
- Offline data caching

### Push Notifications
- New booking alerts (instant)
- Cancellation alerts
- Reminder before appointments
- Notification actions (accept/decline from notification)

### Booking Management
- List view with filters
- Calendar view (optional)
- Quick status updates
- Customer contact integration (call, SMS)

### Dependencies
- EPIC-01 (Backend Foundation) - API endpoints
- EPIC-02 (Authentication) - Login APIs
- EPIC-03 (Booking System) - Booking management APIs
- EPIC-05 (Salon Manager Web App) - Feature reference
- EPIC-08 (Notifications) - Push notification backend

## Related Items

- **Related Requirements**: 
  - Section 3.3 (Salon Manager Features - All features)
  - Section 5.2 (Phase 2: Mobile Applications)
  - Section 5.2.1 (Month 6-7: Mobile App Development)
- **Blocks**: None (Phase 2 epic)
- **Is Blocked By**: EPIC-01, EPIC-02, EPIC-03, EPIC-05, EPIC-08
- **Related Confluence Docs**: Salon Manager Mobile App Design (to be created)

## Notes

- Mobile app should have feature parity with web app
- Push notifications are critical for salon managers to respond quickly
- Quick actions from notifications improve response time
- Mobile dashboard should show most important information first
- Offline support allows viewing bookings without internet
- Camera integration simplifies photo uploads
- Consider implementing voice notes for booking notes (future)
- App should handle high booking volumes efficiently
- Real-time updates are important for booking management
- Consider implementing booking calendar view for better visualization

## History

- 2025-12-12: Epic created

