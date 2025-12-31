# [frontend] - Customer Mobile Application

**Jira Key**: [SAL-9](https://techsharif.atlassian.net/browse/SAL-9)
**Type**: Epic
**Status**: To Do
**Priority**: Medium
**Assignee**: Unassigned
**Labels**: [frontend, customer, mobile-app, react-native, phase2]
**Component**: Frontend
**Phase**: Phase 2 (Months 6-7)
**Created**: 2025-12-12
**Last Updated**: 2025-12-12

## Description

This epic implements the customer mobile application for iOS and Android using React Native. The mobile app provides feature parity with the customer web application, optimized for mobile devices with native UI components, push notifications, and location services integration.

The mobile app extends the platform's reach and provides a better user experience for customers on mobile devices. It includes all customer features from the web app with mobile-specific optimizations and native capabilities like push notifications and location services.

## Scope

### Mobile App Foundation
- React Native project setup
- iOS and Android configuration
- Navigation structure
- State management
- API integration
- Error handling

### Feature Parity with Web App
- Phone number registration and OTP login
- Salon search and discovery
- Salon details view
- Booking flow (service selection, calendar, time selection)
- My Bookings page
- Booking cancellation
- Profile management
- Reviews and ratings
- Language support (English/Bengali)

### Mobile-Specific Features
- Push notifications for booking reminders
- Location services for nearby salon search
- Native calendar integration
- Native sharing capabilities
- Offline support (view bookings, cached salon data)
- Mobile-optimized UI/UX
- Touch-optimized interactions

### Mobile UI/UX
- Native navigation patterns
- Mobile-friendly forms
- Touch-optimized buttons and inputs
- Swipe gestures
- Pull-to-refresh
- Mobile-optimized image loading
- Responsive layouts

## Key Components

- **Mobile Navigation**: React Navigation setup
- **Authentication Screens**: Login and registration
- **Salon Discovery**: Search and map integration
- **Booking Flow**: Mobile-optimized booking process
- **Booking Management**: My Bookings interface
- **Profile Settings**: User profile and preferences
- **Push Notification Handler**: Notification processing
- **Location Services**: GPS and map integration

## Acceptance Criteria

- [ ] React Native app builds for iOS and Android
- [ ] App published to App Store and Play Store
- [ ] Customer can register with phone number and OTP
- [ ] Customer can login with phone number and OTP
- [ ] Customer can search salons by location
- [ ] Location services working (GPS-based search)
- [ ] Customer can view salon details
- [ ] Customer can book appointments
- [ ] Calendar and time selection working on mobile
- [ ] Customer can view and manage bookings
- [ ] Customer can cancel bookings
- [ ] Push notifications working for reminders
- [ ] Customer can leave reviews
- [ ] Language toggle working (English/Bengali)
- [ ] App works offline (view cached data)
- [ ] Native sharing working
- [ ] App performance is smooth (60fps)
- [ ] App handles network errors gracefully

## Technical Details

### Technology Stack
- React Native (Expo as per user rules)
- TypeScript (.tsx files)
- React Navigation
- State management (Context API or Zustand)
- Push notifications (Expo Notifications)
- Location services (Expo Location)
- Map integration (React Native Maps)

### Mobile-Specific Considerations
- Touch targets minimum 44x44 points
- Optimize images for mobile networks
- Lazy loading for lists
- Pull-to-refresh for data updates
- Native keyboard handling
- Deep linking support
- App state management (foreground/background)

### Push Notifications
- Booking confirmation notifications
- Reminder notifications (24h and 2h before)
- Cancellation notifications
- Review request notifications
- Notification permissions handling

### Location Services
- Request location permissions
- Get current location
- Search salons by proximity
- Show salons on map
- Directions to salon

### Dependencies
- EPIC-01 (Backend Foundation) - API endpoints
- EPIC-02 (Authentication) - Login/registration APIs
- EPIC-03 (Booking System) - Booking APIs
- EPIC-04 (Customer Web App) - Feature reference
- EPIC-07 (Reviews & Ratings) - Review APIs
- EPIC-08 (Notifications) - Push notification backend

## Related Items

- **Related Requirements**: 
  - Section 3.1 (Customer Features - All features)
  - Section 5.2 (Phase 2: Mobile Applications)
  - Section 5.2.1 (Month 6-7: Mobile App Development)
- **Blocks**: None (Phase 2 epic)
- **Is Blocked By**: EPIC-01, EPIC-02, EPIC-03, EPIC-04, EPIC-07, EPIC-08
- **Related Confluence Docs**: Mobile App Design Document (to be created)

## Notes

- Mobile app should have feature parity with web app
- Push notifications are critical for mobile experience
- Location services enhance salon discovery
- Offline support improves user experience
- App should follow platform-specific design guidelines (iOS Human Interface Guidelines, Material Design)
- Performance optimization is critical for mobile
- Consider implementing app analytics
- App Store and Play Store submission process should be planned early
- Beta testing with real users before launch
- Consider implementing in-app updates

## History

- 2025-12-12: Epic created

