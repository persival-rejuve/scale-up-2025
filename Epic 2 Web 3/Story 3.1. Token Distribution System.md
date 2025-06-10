# Story 3.1: Token Distribution System

## Overview

This story covers the implementation of the RJV token distribution system in the Rejuve Longevity App. It focuses on establishing the mechanisms for token earning, management of partner offerings, and integration of token-based redemption processes.

## Related Jira Tickets

- **REJUVEL-3236**: Single Use Code RJV pricing
- **REJUVEL-3177**: Add isExclusiveRjvpartner field
- **REJUVEL-2866**: Update profiles API for token goals

## Technical Specifications

### Token Earning Mechanisms

The system will support multiple ways for users to earn RJV tokens:

1. **Data Contribution Rewards**
   - Health data sharing incentives
   - Survey completion bonuses
   - Sensor data integration rewards
   - Regular data update incentives

2. **Engagement Activities**
   - App usage streaks
   - Feature exploration bonuses
   - Educational content completion
   - Community participation

3. **Referral Program**
   - New user referral bonuses
   - Multi-tier referral structure
   - Referral tracking and attribution
   - Milestone-based referral rewards

4. **Partner Interactions**
   - Partner service usage rewards
   - Review and feedback bonuses
   - Exclusive partner engagement incentives
   - Promotional event participation

### Partner Classification System

The system will distinguish between different partner types:

1. **Standard RJV Partners**
   - Basic integration with token system
   - Standard redemption options
   - Regular promotional offerings

2. **Exclusive RJV Partners**
   - Premium integration options
   - Special token redemption rates
   - Limited-time exclusive offerings
   - Featured placement in app

### Single-Use Code Redemption

Implementation of token-based code redemption:

1. **Code Management System**
   - Code generation service
   - Validation and redemption tracking
   - Expiration date enforcement
   - Usage limitation enforcement

2. **Token Pricing Structure**
   - Standard pricing (20-30 RJV per code)
   - Dynamic pricing options
   - Bulk discount mechanisms
   - Promotional pricing periods

3. **Redemption Flow**
   - Code entry interface
   - Token balance verification
   - Confirmation process
   - Success/failure handling

### API Enhancements

Updates to existing APIs to support token features:

1. **Store/Products API**
   - Add `is_exclusive_rjv_partner` field
   - Partner type filtering
   - Token price information
   - Redemption availability status

2. **Profiles API**
   - User token goals support
   - Goal progress tracking
   - Goal recommendation system
   - Goal achievement history

3. **Token Transaction API**
   - Transaction history tracking
   - Earning categorization
   - Spending record management
   - Balance calculation

## Implementation Steps

### Phase 1: API Foundations

1. **API Enhancement**
   - Update store/products API with partner fields
   - Add token pricing to product descriptions
   - Implement profiles API token goal support
   - Create token transaction endpoints

2. **Partner Classification**
   - Implement partner type designation system
   - Build partner administration interface
   - Create partner onboarding process
   - Test partner classification display

3. **Backend Services**
   - Develop token accounting service
   - Build redemption tracking system
   - Implement code generation service
   - Create token transaction logging

### Phase 2: Redemption System

1. **Single-Use Code System**
   - Develop code generation algorithms
   - Build validation and verification services
   - Implement redemption processing
   - Create code management dashboard

2. **Token Pricing Implementation**
   - Set up token price configuration
   - Build dynamic pricing rules engine
   - Implement promotional pricing system
   - Create price management interface

3. **UI Components**
   - Design code entry interface
   - Build redemption confirmation flow
   - Create success/failure screens
   - Implement history and tracking views

### Phase 3: Earning Mechanisms

1. **Contribution Tracking**
   - Implement data contribution monitoring
   - Build reward calculation algorithms
   - Create reward disbursement system
   - Develop contribution analytics

2. **Engagement Rewards**
   - Build activity tracking system
   - Implement streak and milestone tracking
   - Create notification system for rewards
   - Develop engagement analytics

3. **Referral System**
   - Create referral code generation
   - Build attribution tracking
   - Implement multi-tier reward calculations
   - Develop referral analytics dashboard

## User Experience Flow

### Token Earning Flow

1. User performs qualifying activity (data contribution, etc.)
2. System calculates reward amount based on activity value
3. User receives notification of earned tokens
4. Token balance updates in real-time
5. Transaction appears in history with source details

### Code Redemption Flow

1. User browses partner offerings
2. Selects desired single-use code
3. Views token price and confirms purchase
4. System verifies sufficient balance
5. Code is generated and displayed/delivered
6. Tokens are deducted from balance
7. Transaction is recorded in history

### Goal Setting Flow

1. User accesses token goals section
2. Views recommended goals based on usage patterns
3. Selects or customizes token earning goal
4. System tracks progress toward goal
5. User receives notifications of progress and completion
6. Achievements are recorded in user profile

## Technical Architecture

1. **Token Ledger Service**
   - Double-entry accounting system
   - Transaction verification
   - Balance calculation
   - History management

2. **Reward Rules Engine**
   - Activity qualification rules
   - Reward calculation formulas
   - Rate limiting and caps
   - Promotional multipliers

3. **Partner Integration Layer**
   - Partner API endpoints
   - Authentication and authorization
   - Rate limiting and quotas
   - Analytics and reporting

4. **Code Management System**
   - Cryptographic code generation
   - Validation algorithms
   - Expiration management
   - Usage tracking

## Acceptance Criteria

1. Partners can be correctly classified as standard or exclusive RJV partners
2. Single-use codes can be purchased with RJV tokens at configured rates
3. Users can set and track token earning goals
4. All token transactions are properly recorded with source information
5. Partner offerings display correct token pricing
6. System enforces token balance requirements for redemptions
7. APIs return all required token-related fields

## Risks & Mitigations

| Risk | Impact | Mitigation |
|------|--------|------------|
| Token balance inconsistencies | High | Robust accounting system with reconciliation |
| Code redemption fraud | Medium | Cryptographic code generation and one-time use enforcement |
| Partner integration issues | Medium | Comprehensive partner onboarding and testing process |
| User confusion about token value | High | Clear documentation and intuitive UX for token features |
| System performance under load | Medium | Performance testing and optimization of token operations |

## Dependencies

- User service refactoring
- Store API infrastructure
- Partner onboarding system
- Notification service

## Related Documentation

- [RJV Token Pricing Strategy](https://confluence.example.com/pages/viewpage.action?pageId=6389786)
- [Partner Classification Guidelines](https://confluence.example.com/pages/viewpage.action?pageId=6389787)
- [Single-Use Code Technical Specifications](https://confluence.example.com/pages/viewpage.action?pageId=6389788)

---

*Last Updated: 2025-06-09*
