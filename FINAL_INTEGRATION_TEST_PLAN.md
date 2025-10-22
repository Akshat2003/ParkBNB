# Final Integration Test Plan

## Route Naming Standardization - Verify Fixed Routes

### 1. conversationsController - `/unread/count`
- Old: `GET /api/conversations/unread-count` ❌
- New: `GET /api/conversations/unread/count` ✅

### 2. notificationsController - `/read/all`
- Old: `PUT /api/notifications/read-all` ❌
- New: `PUT /api/notifications/read/all` ✅

### 3. availabilityController - `/check/conflict`
- Old: `POST /api/availability/space/:spaceId/check-conflict` ❌
- New: `POST /api/availability/space/:spaceId/check/conflict` ✅

### 4. ownersController - `/verify/kyc`
- Old: `PUT /api/owners/:id/verify-kyc` ❌
- New: `PUT /api/owners/:id/verify/kyc` ✅

## Cross-Controller Integration Tests

### Test Flow 1: Complete User Booking Journey
1. **authController** - Register user
2. **vehiclesController** - Add vehicle
3. **ownersController** - Register as owner
4. **propertiesController** - Create property
5. **parkingSpacesController** - Create parking space
6. **availabilityController** - Set availability
7. **bookingsController** - Create booking
8. **paymentsController** - Process payment
9. **conversationsController** - Create conversation
10. **messagesController** - Send message
11. **reviewsController** - Add review
12. **refundsController** - Request refund

### Test Flow 2: Admin Management Journey
1. **authController** - Login as admin
2. **adminsController** - Manage admin users
3. **usersController** - Manage users (admin)
4. **bookingsController** - View all bookings
5. **paymentsController** - View all payments
6. **refundsController** - Approve/reject refunds
7. **supportTicketsController** - Manage tickets

### Test Flow 3: Notification & Communication Flow
1. Create booking trigger → notificationsController
2. Payment success → notificationsController
3. Message received → conversationsController + messagesController
4. Review posted → notificationsController

## Individual Controller Tests

All 19 controllers with all 145 functions to be tested systematically.
