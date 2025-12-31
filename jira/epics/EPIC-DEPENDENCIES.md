# Epic Dependencies & Critical Path

This document outlines the dependencies between epics and identifies the critical path for development.

## Dependency Overview

### Phase 1 Dependencies

```
EPIC-01 (Backend Foundation)
    ↓
    ├── EPIC-02 (Authentication)
    ├── EPIC-03 (Booking System)
    ├── EPIC-08 (Notifications)
    └── All other Phase 1 epics

EPIC-02 (Authentication)
    ↓
    ├── EPIC-04 (Customer Web App)
    ├── EPIC-05 (Salon Manager Web App)
    └── EPIC-06 (Admin Portal)

EPIC-03 (Booking System)
    ↓
    ├── EPIC-04 (Customer Web App)
    ├── EPIC-05 (Salon Manager Web App)
    └── EPIC-07 (Reviews & Ratings)

EPIC-08 (Notifications)
    ↓
    ├── EPIC-02 (Authentication - OTP)
    ├── EPIC-04 (Customer Web App - Booking confirmations)
    ├── EPIC-05 (Salon Manager Web App - Booking alerts)
    └── EPIC-06 (Admin Portal - Approval notifications)

EPIC-07 (Reviews & Ratings)
    ↓
    └── EPIC-04 (Customer Web App - Review UI)
```

### Phase 2 Dependencies

```
All Phase 1 Epics
    ↓
    ├── EPIC-09 (Customer Mobile App)
    └── EPIC-10 (Salon Manager Mobile App)
```

### Phase 3 Dependencies

```
All Phase 1 & Phase 2 Epics
    ↓
    ├── EPIC-11 (Stylist Management)
    ├── EPIC-12 (Payment Integration)
    └── EPIC-13 (Advanced Analytics)
```

## Critical Path

The critical path for MVP (Phase 1) is:

1. **EPIC-01** (Backend Foundation) - **MUST START FIRST**
   - Duration: Months 1-2
   - Blocks: All other epics

2. **EPIC-02** (Authentication) - **CRITICAL PATH**
   - Duration: Months 1-2 (parallel with EPIC-01 after foundation)
   - Blocks: All frontend epics

3. **EPIC-08** (Notifications) - **CRITICAL PATH**
   - Duration: Months 1-5 (spans entire Phase 1)
   - Required for: Authentication OTP, Booking confirmations

4. **EPIC-03** (Booking System) - **CRITICAL PATH**
   - Duration: Months 1-2
   - Blocks: Customer and Salon Manager apps

5. **EPIC-04** (Customer Web App) - **CRITICAL PATH**
   - Duration: Month 3
   - Depends on: EPIC-01, EPIC-02, EPIC-03, EPIC-08

6. **EPIC-05** (Salon Manager Web App) - **CRITICAL PATH**
   - Duration: Month 4
   - Depends on: EPIC-01, EPIC-02, EPIC-03, EPIC-08

7. **EPIC-06** (Admin Portal) - **CRITICAL PATH**
   - Duration: Month 4
   - Depends on: EPIC-01, EPIC-02, EPIC-05, EPIC-08

8. **EPIC-07** (Reviews & Ratings) - **NON-CRITICAL PATH**
   - Duration: Month 5
   - Can be developed in parallel with testing

## Dependency Matrix

| Epic | Depends On | Blocks |
|------|-----------|--------|
| EPIC-01 | None | All other epics |
| EPIC-02 | EPIC-01 | EPIC-04, EPIC-05, EPIC-06 |
| EPIC-03 | EPIC-01, EPIC-02 | EPIC-04, EPIC-05, EPIC-07 |
| EPIC-04 | EPIC-01, EPIC-02, EPIC-03, EPIC-07, EPIC-08 | EPIC-09 |
| EPIC-05 | EPIC-01, EPIC-02, EPIC-03, EPIC-06, EPIC-08 | EPIC-10 |
| EPIC-06 | EPIC-01, EPIC-02, EPIC-03, EPIC-05, EPIC-08 | None |
| EPIC-07 | EPIC-01, EPIC-02, EPIC-03 | EPIC-04 |
| EPIC-08 | EPIC-01 | EPIC-02, EPIC-04, EPIC-05, EPIC-06 |
| EPIC-09 | All Phase 1 epics | None |
| EPIC-10 | All Phase 1 epics | None |
| EPIC-11 | All Phase 1 & 2 epics | None |
| EPIC-12 | All Phase 1 & 2 epics | None |
| EPIC-13 | All Phase 1 & 2 epics | None |

## Parallel Development Opportunities

### Month 1-2 (Foundation)
- EPIC-01 and EPIC-02 can be developed in parallel after EPIC-01 database structure is defined
- EPIC-03 can start once EPIC-01 database schema is ready
- EPIC-08 can start early for OTP functionality

### Month 3-4 (Web Apps)
- EPIC-04, EPIC-05, and EPIC-06 can be developed in parallel after dependencies are met
- EPIC-07 can be developed in parallel with web apps

### Month 5 (Testing & Polish)
- EPIC-07 completion
- Testing across all Phase 1 epics
- Bug fixes and optimization

## Risk Areas

### High Risk Dependencies
1. **EPIC-01 → All epics**: If backend foundation is delayed, entire project is delayed
2. **EPIC-02 → All frontend epics**: Authentication is required for all user-facing features
3. **EPIC-08 → Multiple epics**: SMS notifications are critical for user experience

### Mitigation Strategies
1. Start EPIC-01 immediately and prioritize completion
2. Begin EPIC-08 early for OTP functionality (needed for EPIC-02)
3. Design APIs early to allow frontend development to start in parallel
4. Implement mock services for testing while dependencies are being developed

## Notes

- EPIC-08 (Notifications) spans the entire Phase 1 as it's needed throughout
- EPIC-07 (Reviews) can be developed later as it's not critical for MVP launch
- Phase 2 epics (mobile apps) can only start after Phase 1 is complete
- Phase 3 epics are enhancements and can be prioritized based on business needs

