# Route Naming Convention Audit

## Date: 2025-10-17

## Inconsistencies Found

### 1. Unread Count Routes
| Controller | Current Route | Should Be | Status |
|---|---|---|---|
| messagesController | `/unread/count` | `/unread/count` | ✅ Correct |
| conversationsController | `/unread-count` | `/unread/count` | ❌ FIX NEEDED |
| notificationsController | `/unread/count` | `/unread/count` | ✅ Correct |

### 2. Bulk Action Routes
| Controller | Current Route | Should Be | Status |
|---|---|---|---|
| notificationsController | `/read-all` | `/read/all` | ❌ FIX NEEDED |
| availabilityController | `/check-conflict` | `/check/conflict` | ❌ FIX NEEDED |

### 3. Owner Routes
| Controller | Current Route | Should Be | Status |
|---|---|---|---|
| ownersController | `/verify-kyc` | `/verify/kyc` | ❌ FIX NEEDED |

## Standardization Rules

**Rule 1:** Use forward slashes (`/`) for all multi-word endpoints
- ✅ `/unread/count`
- ❌ `/unread-count`

**Rule 2:** Resource actions should use the pattern `/:id/action`
- ✅ `/refunds/:id/approve`
- ✅ `/payments/:id/verify`
- ✅ `/bookings/:id/cancel`

**Rule 3:** Collection-level actions should use `/action` or `/action/detail`
- ✅ `/read/all`
- ✅ `/unread/count`

## Files To Update

1. `/backend/src/routes/conversationRoutes.js` - Line 16
2. `/backend/src/routes/notificationRoutes.js` - Line 19
3. `/backend/src/routes/availabilityRoutes.js` - Line 33
4. `/backend/src/routes/ownerRoutes.js` - Line 50

## Impact Analysis

- **Breaking Change:** YES - existing API clients will need to update their endpoints
- **Controllers Affected:** 4 out of 19
- **Routes Affected:** 4 routes total
- **Tests Affected:** Integration tests for these 4 endpoints

## Recommendation

1. Update route definitions
2. Add deprecation warnings to old routes (optional)
3. Update API documentation
4. Re-test affected controllers
5. Update any frontend/client code using these endpoints
