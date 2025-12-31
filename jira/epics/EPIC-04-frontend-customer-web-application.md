# [frontend] - Customer Web Application

**Jira Key**: [SAL-4](https://techsharif.atlassian.net/browse/SAL-4)
**Type**: Epic
**Status**: To Do
**Priority**: High
**Assignee**: Unassigned
**Labels**: [frontend, customer, web-app, phase1]
**Component**: Frontend
**Phase**: Phase 1 (Month 3)
**Created**: 2025-12-12
**Last Updated**: 2025-12-12

## Description

This epic implements the complete customer-facing web application that allows customers to discover salons, view salon details, book appointments, manage their bookings, and leave reviews. The application must be user-friendly, responsive, and support both English and Bengali languages.

The customer web app is the primary interface for end-users and must provide a seamless booking experience. It includes registration, salon discovery, booking flow, booking management, reviews, and profile management features.

## Scope

### Registration & Authentication UI
- Phone number registration form
- SMS OTP verification interface
- Login flow with OTP
- Profile setup (name, email, photo, language)
- Profile management page

### Salon Discovery & Search
- Salon search by location (GPS-based)
- Search by city or area name
- Search by salon name
- Filter by gender type (Boys/Girls/Unisex)
- Sort by rating or distance
- Map view integration (optional)
- Popular salons display

### Salon Details Page
- Salon photos gallery
- Address and map location
- Contact phone number
- Operating hours display
- Customer reviews and ratings
- Available services with prices
- "Book Now" action

### Booking Flow
- Service selection interface
- Calendar view (30-day window)
- Available time slot selection
- Booking confirmation page
- Booking summary display
- SMS confirmation receipt

### My Bookings Page
- Upcoming appointments list
- Past appointments list
- Cancelled appointments list
- Booking details view
- Cancel booking functionality (2+ hours before)
- Countdown to appointment
- Map directions to salon

### Reviews & Ratings
- Review form (after completed appointment)
- Star rating interface (1-5 stars)
- Review text input
- Photo upload for reviews
- View all salon reviews
- Verified booking badge display

### Language Support
- English interface
- Bengali (Bangla) interface
- Language toggle in settings
- All text translated

## Key Components

- **Registration/Login Pages**: Phone OTP authentication UI
- **Salon Search Page**: Search, filter, and discovery interface
- **Salon Detail Page**: Complete salon information display
- **Booking Flow Pages**: Service selection, calendar, time selection, confirmation
- **My Bookings Page**: Booking management interface
- **Profile Settings Page**: User profile and language settings
- **Review Interface**: Rating and review submission

## Acceptance Criteria

- [ ] Customer can register with phone number and OTP
- [ ] Customer can login with phone number and OTP
- [ ] Customer can search salons by location, name, or city
- [ ] Customer can filter salons by gender type
- [ ] Customer can view salon details with all information
- [ ] Customer can select services and book appointment
- [ ] Calendar shows available dates (30-day window)
- [ ] Time slots clearly show availability (green/gray)
- [ ] Customer can confirm booking and receive SMS
- [ ] Customer can view all bookings (upcoming, past, cancelled)
- [ ] Customer can cancel booking (2+ hours before)
- [ ] Customer can leave review after completed appointment
- [ ] Customer can view all salon reviews
- [ ] Language toggle works (English/Bengali)
- [ ] All UI text properly translated
- [ ] Responsive design works on mobile browsers
- [ ] Map integration working (if implemented)

## Technical Details

### Technology Stack
- React or similar frontend framework
- Responsive CSS framework (MUI as per user rules)
- State management (Context API or Zustand)
- Routing (React Router)
- API integration with backend

### Key User Flows

**Booking Flow:**
1. Search/Find salon
2. View salon details
3. Click "Book Now"
4. Select service(s)
5. Select date from calendar
6. Select time slot
7. Login (if not logged in)
8. Confirm booking
9. Receive SMS confirmation

**Review Flow:**
1. Complete appointment (marked by salon)
2. Receive notification to review
3. Open review form
4. Rate (1-5 stars)
5. Write review (optional)
6. Upload photos (optional)
7. Submit review

### Dependencies
- EPIC-01 (Backend Foundation) - API endpoints
- EPIC-02 (Authentication) - Login/registration APIs
- EPIC-03 (Booking System) - Booking APIs
- EPIC-07 (Reviews & Ratings) - Review APIs
- EPIC-08 (Notifications) - SMS confirmations

## Related Items

- **Related Requirements**: 
  - Section 3.1 (Complete Customer Features)
  - Section 4.1 (Process Flow 1: Customer Booking an Appointment)
  - Section 5.1.3 (Month 3: Customer Web App)
- **Blocks**: EPIC-09 (Customer Mobile App) - Mobile app will reuse web app logic
- **Is Blocked By**: EPIC-01, EPIC-02, EPIC-03, EPIC-07, EPIC-08
- **Related Confluence Docs**: Customer Web App Design Document (to be created)

## Notes

- UI should be intuitive and require minimal learning
- Booking flow should be completable in under 2 minutes
- Calendar should clearly show unavailable dates
- Time slots should be easy to select on mobile devices
- SMS confirmation should include booking reference number
- Language toggle should persist user preference
- Consider implementing booking reminders in UI (in addition to SMS)
- Map integration is optional but recommended for better UX

## History

- 2025-12-12: Epic created

