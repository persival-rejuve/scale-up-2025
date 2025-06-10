# Story 3.2: Token Persistence

## Overview

This story addresses the critical issue of token persistence in the Rejuve Longevity App, ensuring that users' RJV tokens remain accessible across device changes, app reinstallations, and account recoveries. Multiple bug reports have highlighted this as a significant user pain point that must be resolved for a reliable token economy.

## Related Jira Tickets

- **REJUVEL-3447**: Refactoring user service
- **REJUVEL-2583**: After re-installing app via test flight total token of 723 RJV dropped to zero (Won't Do)
- **REJUVEL-2458**: Tokens disappeared after iPhone upgrade (719 RJV) (Won't Do)
- **REJUVEL-2554**: Tokens went from blocked to zero (Won't Do)
- New task: Token storage architecture redesign
- New task: Token backup & recovery mechanisms

## Technical Problems

The current implementation has several identified issues:

1. **Local Storage Dependency**
   - Tokens appear to be stored primarily in local device storage
   - No robust synchronization with backend or blockchain
   - Data loss during app reinstallation or device changes

2. **Token State Management**
   - Issues with blocked tokens disappearing entirely
   - Inconsistent state transitions for tokens
   - No reliable audit trail for token changes

3. **Recovery Mechanisms**
   - Lack of user-accessible recovery options
   - No automated detection of token discrepancies
   - Missing reconciliation process for lost tokens

4. **Synchronization Issues**
   - No cloud backup of token balances
   - Weak identity linking across devices
   - Limited transaction logging for reconciliation

## Technical Solution

### Hybrid Token Storage Architecture

The solution will implement a robust hybrid approach:

1. **Blockchain as Source of Truth**
   - RJV tokens on blockchain serve as ultimate source of truth
   - Smart contract for token balance verification
   - On-chain transaction history for audit purposes
   - Secure claiming mechanism for earned tokens

2. **Cloud-Based Token Ledger**
   - Server-side accounting system for pending/earned tokens
   - User account linking across devices
   - Transaction logging with detailed metadata
   - Automatic reconciliation with blockchain balances

3. **Local Caching Layer**
   - Efficient local cache for performance
   - Encrypted local storage for sensitive data
   - Background synchronization with cloud
   - Offline functionality with pending transaction queue

### User Service Refactoring

The user service will be refactored to:

1. **Identity Management**
   - Robust user identity verification
   - Cross-device account linking
   - Recovery credential management
   - Secure authentication for token operations

2. **Token Management**
   - Token balance aggregation across sources
   - Pending vs. claimed token tracking
   - Transaction history management
   - Token state transitions (earned, pending, claimed, spent)

3. **Synchronization Service**
   - Background sync with blockchain and cloud
   - Conflict resolution algorithms
   - Recovery procedures for detected discrepancies
   - Transaction retry mechanisms

### Recovery Mechanisms

Implementation of comprehensive recovery options:

1. **Automatic Recovery**
   - Detection of balance discrepancies on login
   - Automated reconciliation from server records
   - Blockchain balance verification
   - Transaction replay for consistency

2. **User-Initiated Recovery**
   - Account recovery workflow
   - Historical balance verification
   - Step-by-step recovery guide
   - Support ticket integration for edge cases

3. **Admin Tools**
   - Token audit dashboard for support staff
   - Manual balance adjustment capabilities
   - Transaction investigation tools
   - Batch recovery processing

## Implementation Steps

### Phase 1: Architecture Redesign

1. **Assessment & Planning**
   - Audit current token storage implementation
   - Document failure scenarios and edge cases
   - Design hybrid storage architecture
   - Create data migration strategy

2. **Database Schema Updates**
   - Enhance user profile with token metadata
   - Create transaction history tables
   - Implement state tracking fields
   - Design reconciliation markers

3. **API Design**
   - Create token synchronization endpoints
   - Design recovery API methods
   - Establish blockchain verification endpoints
   - Build transaction logging API

### Phase 2: Core Implementation

1. **User Service Refactoring**
   - Implement new token management logic
   - Build synchronization mechanisms
   - Create account linking functionality
   - Develop recovery procedures

2. **Blockchain Integration**
   - Implement on-chain balance verification
   - Create secure claiming processes
   - Build transaction verification
   - Establish event monitoring

3. **Cloud Services**
   - Develop server-side token ledger
   - Implement reconciliation services
   - Create transaction logging
   - Build admin audit tools

### Phase 3: Client Implementation

1. **Mobile App Updates**
   - Implement local caching layer
   - Create background sync service
   - Build recovery UI
   - Update token display components

2. **Testing & Validation**
   - Conduct migration testing
   - Perform recovery scenario testing
   - Validate cross-device synchronization
   - Test offline capabilities

3. **Monitoring & Analytics**
   - Implement token consistency monitoring
   - Create anomaly detection
   - Build synchronization analytics
   - Develop support dashboards

## Technical Architecture

### Components

1. **TokenLedgerService**
   - Records all token transactions
   - Maintains pending and claimed balances
   - Provides transaction history
   - Handles state transitions

2. **SynchronizationManager**
   - Manages device-to-cloud synchronization
   - Handles blockchain verification
   - Implements retry and conflict resolution
   - Provides sync status reporting

3. **RecoveryEngine**
   - Detects balance discrepancies
   - Implements recovery workflows
   - Handles historical data reconciliation
   - Provides user guidance during recovery

4. **TokenStorageProvider**
   - Abstracts storage mechanisms
   - Handles encryption of sensitive data
   - Manages local caching
   - Provides consistent access patterns

## Acceptance Criteria

1. User tokens persist correctly after app reinstallation
2. Token balances synchronize correctly across multiple devices
3. System detects and resolves token discrepancies automatically
4. Users can initiate recovery process if needed
5. Complete transaction history is maintained and accessible
6. System handles offline token earning with later synchronization
7. No reported token loss incidents after implementation

## Risks & Mitigations

| Risk | Impact | Mitigation |
|------|--------|------------|
| Data migration errors | Critical | Comprehensive testing, backup before migration, rollback plan |
| Synchronization conflicts | High | Strong conflict resolution algorithms, detailed logging |
| Recovery edge cases | High | Extensive testing of recovery scenarios, manual intervention capability |
| User confusion during transition | Medium | Clear communication, guided workflows, support resources |
| Performance impact | Medium | Efficient caching, background processing, optimization |

## Dependencies

- User authentication system
- Cloud storage infrastructure
- Blockchain integration
- App update deployment mechanism

## Related Documentation

- [Token Persistence Architecture](https://confluence.example.com/pages/viewpage.action?pageId=6389789)
- [Token Recovery Procedures](https://confluence.example.com/pages/viewpage.action?pageId=6389790)
- [Data Migration Plan](https://confluence.example.com/pages/viewpage.action?pageId=6389791)

---

*Last Updated: 2025-06-09*
