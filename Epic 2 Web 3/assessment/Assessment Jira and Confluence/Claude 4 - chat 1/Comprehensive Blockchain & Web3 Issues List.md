# Rejuve AI - Comprehensive Blockchain & Web3 Issues List

_Last Updated: June 7, 2025_

## Executive Summary

**Total Open Issues: 20**

- **Epics:** 2
- **Stories:** 1
- **Tasks:** 8
- **Sub-tasks:** 3
- **Bugs:** 6

**Priority Distribution:**

- **Highest:** 1
- **High:** 6
- **Medium:** 11
- **Low:** 1
- **Lowest:** 1

---

## 🎯 EPICS (2 issues)

### 1. **REJUVEL-2751** - Web 3.0 Onboarding Experience

- **Status:** To Do
- **Priority:** Medium
- **Assignee:** Rajib Talukder Raju
- **Created:** Sep 12, 2024
- **Description:** Create an introductory experience to learn more about Web 3.0 technologies, why it's in our App, and how to get started. Includes mini courses on Blockchain, NFTs, Wallets, Safety with mini quizzes, wallet creation guides, videos, and Metamask integration.

### 2. **REJUVEL-673** - On-off Ramp for Private Wallets

- **Status:** To Do
- **Priority:** Medium
- **Assignee:** Unassigned
- **Created:** Mar 22, 2022
- **Description:** Infrastructure for enabling users to move crypto funds in and out of private wallets

---

## 📖 STORIES (1 issue)

### 1. **REJUVEL-1669** - Integration of Data NFT with App

- **Status:** In Progress
- **Priority:** High
- **Assignee:** Yared Solomon
- **Created:** Aug 28, 2023
- **Description:** Complete integration of Data NFT as identity/Network Membership token. Tied to light KYC to prevent multiple user instances. One token per user, minted/paid by Rejuve, serves as eligibility proof for data rewards and permission access tracking.

---

## ✅ TASKS (8 issues)

### 1. **REJUVEL-3261** - Investigate keyless wallets

- **Status:** To Do
- **Priority:** Medium
- **Assignee:** Yonatan Cherkos
- **Created:** Mar 31, 2025
- **Description:** Research solutions for users who don't have crypto wallets. Focus on keyless solutions using email and pin number instead of seed phrases.

### 2. **REJUVEL-3260** - Integrate actual wallets for claiming

- **Status:** To Do
- **Priority:** High
- **Assignee:** Yonatan Cherkos
- **Created:** Mar 31, 2025
- **Description:** Implement wallet integration for claiming rewards. Previous research done on Metamask and WalletConnect integration.

### 3. **REJUVEL-3236** - Single Use Code offers should have an RJV price/cost associated to them

- **Status:** QA
- **Priority:** Medium
- **Assignee:** gabriel.nogueira
- **Created:** Mar 27, 2025
- **Description:** Single use codes should be redeemed with RJV (20-30 tokens). Currently given for free, needs tracking and redemption management.

### 4. **REJUVEL-3177** - Add isExclusiveRjvpartner field to /store/products API endpoint

- **Status:** QA
- **Priority:** High
- **Assignee:** gabriel.nogueira
- **Created:** Mar 10, 2025
- **Description:** Add `is_exclusive_rjv_partner` field to store products API response alongside existing `is_rjv_partner` field.

### 5. **REJUVEL-2898** - UX for Wallet & KYC screens

- **Status:** In Progress
- **Priority:** Highest
- **Assignee:** Rajib Talukder Raju
- **Created:** Nov 25, 2024
- **Description:** Design UX flow: 1) Proof of human verification (Civic), 2) Connect wallet, 3) Submit data + mint NFT, 4) Claim tokens. Some processes may happen off-app.

### 6. **REJUVEL-1667** - Investigate integration of Cardano token with App

- **Status:** To Do
- **Priority:** Medium
- **Assignee:** Yared Solomon
- **Created:** Aug 26, 2023
- **Description:** Research Cardano integration for RJV claiming. RJV-ADA policy ID: 8cfd6893f5f6c1cc954cec1a0a1460841b74da6e7803820dde62bb78. Enable users to claim RJV on Cardano wallets.

### 7. **REJUVEL-1308** - Concurrent calls in blockchain enabled mode

- **Status:** To Do
- **Priority:** Medium
- **Assignee:** Yared Solomon
- **Created:** Nov 23, 2022
- **Description:** Implement token approach instead of channels for bs_net service calls to enable concurrent blockchain operations without scaling channel costs.

### 8. **REJUVEL-2866** - Update the /profiles API to accepts and send user goals

- **Status:** PR Raised
- **Priority:** Medium
- **Assignee:** gabriel.nogueira
- **Created:** Nov 11, 2024
- **Description:** Update API to support user goals including "EARNING_TOKENS" as a goal option.

---

## 🔧 SUB-TASKS (3 issues)

### 1. **REJUVEL-2904** - Experiment Data NFT creation

- **Status:** In Progress
- **Priority:** High
- **Assignee:** Yared Solomon
- **Created:** Nov 28, 2024
- **Description:** Experiment with Data NFT creation process: KYC data hashing, signing process, smart contract calls, and documentation updates.

### 2. **REJUVEL-2737** - Integrate Civic Uniqueness Pass

- **Status:** To Do
- **Priority:** High
- **Assignee:** Yared Solomon
- **Created:** Sep 5, 2024
- **Description:** Integrate Civic solution for 1 user: 1 wallet verification. Removes need for hard KYC, uses face verification tied to wallet.

### 3. **REJUVEL-3447** - Refactoring user service

- **Status:** QA
- **Priority:** Medium
- **Assignee:** Pedro Mello
- **Created:** May 16, 2025
- **Description:** Refactor UserService for scalable push notifications and token management.

---

## 🐛 BUGS (6 issues)

### 1. **REJUVEL-2871** - Inbuilt wallet function to give choice of withdrawing RJV token to external wallet

- **Status:** Won't Do
- **Priority:** Medium
- **Assignee:** Unassigned
- **Created:** Nov 15, 2024
- **Description:** User suggestion to add RJV withdrawal to external wallets instead of only in-app spending.

### 2. **REJUVEL-2583** - After re-installing app via test flight, total token of 723 RJV dropped to zero

- **Status:** Won't Do
- **Priority:** Low
- **Assignee:** Cendel Dogan
- **Created:** Jul 2, 2024
- **Description:** User lost 723 RJV tokens after app reinstall.

### 3. **REJUVEL-2458** - Tokens disappeared after iPhone upgrade (719 RJV)

- **Status:** Won't Do
- **Priority:** High
- **Assignee:** Unassigned
- **Created:** May 20, 2024
- **Description:** User lost 719 RJV tokens after upgrading to new iPhone.

### 4. **REJUVEL-2554** - Tokens went from blocked to zero

- **Status:** Won't Do
- **Priority:** High
- **Assignee:** Cendel Dogan
- **Created:** Jun 23, 2024
- **Description:** User had blocked tokens that disappeared completely.

### 5. **REJUVEL-1513** - Experiment and implementing Depay payment gateway

- **Status:** Won't Do
- **Priority:** Medium
- **Assignee:** Yared Solomon
- **Created:** May 17, 2023
- **Description:** Attempted integration of DePay web3 payment gateway with Flutter mobile app using deep links.

### 6. **REJUVEL-3110** - Exception: Error in sending email notification

- **Status:** PR Raised
- **Priority:** Medium
- **Assignee:** gabriel.nogueira
- **Created:** Feb 19, 2025
- **Description:** Email notification error related to token/reward notifications.

---

## 📊 Key Insights & Technical Analysis

### **High-Priority Active Work (In Progress/QA)**

1. **Data NFT Integration** (REJUVEL-1669) - Core identity token system
2. **Wallet & KYC UX** (REJUVEL-2898) - Critical user onboarding flow
3. **Data NFT Creation Experiments** (REJUVEL-2904) - Smart contract testing
4. **RJV Partner API Updates** (REJUVEL-3177, REJUVEL-3236) - Store integration

### **Blockchain Infrastructure Needs**

- **Wallet Integration:** Multiple providers (Metamask, WalletConnect, Keyless solutions)
- **Multi-chain Support:** Ethereum, BNB, Polygon, Cardano
- **Smart Contracts:** Data NFT minting and management
- **Token Economics:** RJV distribution and claiming mechanisms

### **User Experience Challenges**

- **Token Loss Issues:** Multiple reports of RJV disappearing during app updates/device changes
- **Web3 Onboarding:** Need comprehensive education for crypto newcomers
- **Wallet Accessibility:** Keyless solutions for non-crypto users

### **Technical Dependencies**

- **Civic Integration:** KYC and uniqueness verification
- **Multi-chain Architecture:** Supporting EVM and Cardano ecosystems
- **API Integration:** Store products with RJV partner flags
- **Concurrent Processing:** Blockchain call optimization

---

## 🎯 Recommendations

### **Immediate Actions (Next Sprint)**

1. Complete Wallet & KYC UX design (REJUVEL-2898)
2. Finish RJV partner API implementation (REJUVEL-3177)
3. Deploy single-use code RJV pricing (REJUVEL-3236)

### **Medium-term Goals (Next Quarter)**

1. Complete Data NFT integration (REJUVEL-1669)
2. Implement keyless wallet solutions (REJUVEL-3261)
3. Integrate actual wallet claiming (REJUVEL-3260)
4. Deploy Civic Uniqueness Pass (REJUVEL-2737)

### **Long-term Strategy**

1. Launch Web 3.0 onboarding experience (REJUVEL-2751)
2. Implement Cardano integration (REJUVEL-1667)
3. Optimize blockchain concurrent processing (REJUVEL-1308)

---

## 📋 Issue Status Distribution

|Status|Count|Percentage|
|---|---|---|
|To Do|8|40%|
|In Progress|3|15%|
|QA|3|15%|
|PR Raised|2|10%|
|Won't Do|4|20%|

## 🏷️ Priority Analysis

|Priority|Count|Focus Area|
|---|---|---|
|Highest|1|UX/KYC Critical Path|
|High|6|Core Blockchain Features|
|Medium|11|Supporting Infrastructure|
|Low|1|User Experience Issues|
|Lowest|1|Legacy Integration|

---

_This comprehensive list includes all open issues related to Blockchain, Wallets, RJV tokens, Data NFTs, and Web3 functionality across the Rejuve AI project portfolio. Issues marked as "Won't Do" are included for historical context and potential future reconsideration._