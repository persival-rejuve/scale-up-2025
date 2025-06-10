// Comprehensive Blockchain & Web3 Issues Data Structure
// All open issues related to Blockchain, Wallets, RJV, and Data NFT
// Last Updated: June 7, 2025

const blockchainIssuesData = {
  metadata: {
    totalIssues: 20,
    lastUpdated: "2025-06-07",
    searchTerms: ["blockchain", "wallet", "RJV", "NFT", "ethereum", "crypto", "token", "mint"],
    projects: ["REJUVEL"],
    statusFilter: "NOT (Done OR Closed)"
  },

  summary: {
    byType: {
      Epic: 2,
      Story: 1,
      Task: 8,
      "Sub-task": 3,
      Bug: 6
    },
    byPriority: {
      Highest: 1,
      High: 6,
      Medium: 11,
      Low: 1,
      Lowest: 1
    },
    byStatus: {
      "To Do": 8,
      "In Progress": 3,
      "QA": 3,
      "PR Raised": 2,
      "Wont Do": 4
    }
  },

  epics: [
    {
      key: "REJUVEL-2751",
      id: "12724",
      title: "Web 3.0 Onboarding Experience",
      status: "To Do",
      priority: "Medium",
      assignee: "Rajib Talukder Raju",
      reporter: "Rajib Talukder Raju",
      created: "2024-09-12T03:14:59.630-0300",
      updated: "2024-09-12T03:15:03.756-0300",
      description: "Create an introductory experience to learn more about Web 3.0 technologies, why it's in our App, and how to get started. This includes: mini course with subjects like Blockchain, NFTs, Wallets, Safety with mini quizzes, guide for wallet creation, videos, Metamask integration, content friendliness for all ages.",
      tags: ["web3", "onboarding", "education", "blockchain", "nft", "wallet", "metamask"]
    },
    {
      key: "REJUVEL-673",
      id: "11468",
      title: "On-off Ramp for Private Wallets",
      status: "To Do",
      priority: "Medium",
      assignee: null,
      reporter: "Jasmine Smith",
      created: "2022-03-22T19:03:42.063-0300",
      updated: "2023-08-26T17:35:15.873-0300",
      description: "Infrastructure for enabling users to move cryptocurrency funds in and out of private wallets",
      tags: ["wallet", "infrastructure", "crypto", "private-wallet"]
    }
  ],

  stories: [
    {
      key: "REJUVEL-1669",
      id: "10574",
      title: "Integration of Data NFT with App",
      status: "In Progress",
      priority: "High",
      assignee: "Yared Solomon",
      reporter: "Jasmine Smith",
      created: "2023-08-28T10:29:24.513-0300",
      updated: "2025-06-03T23:48:14.872-0300",
      description: "Complete the full design of the App/research program for data contribution in exchange for rewards. Users must obtain a Data NFT as identity/Network Membership token. Tied to light KYC to prevent multiple user instances. One token per user, minted by Rejuve, proves eligibility for data rewards and tracks research initiatives.",
      tags: ["data-nft", "identity", "kyc", "rewards", "smart-contract", "membership"]
    }
  ],

  tasks: [
    {
      key: "REJUVEL-3261",
      id: "13474",
      title: "Investigate keyless wallets",
      status: "To Do",
      priority: "Medium",
      assignee: "Yonatan Cherkos",
      reporter: "Jasmine Smith",
      created: "2025-03-31T10:07:33.907-0300",
      updated: "2025-05-12T09:49:26.048-0300",
      description: "Research solutions for users who don't have crypto wallets. Focus on keyless solutions using email and pin number instead of seed phrases.",
      tags: ["keyless-wallet", "user-experience", "crypto", "onboarding"]
    },
    {
      key: "REJUVEL-3260",
      id: "12716",
      title: "Integrate actual wallets for claiming",
      status: "To Do",
      priority: "High",
      assignee: "Yonatan Cherkos",
      reporter: "Jasmine Smith",
      created: "2025-03-31T10:06:21.016-0300",
      updated: "2025-05-12T09:49:25.758-0300",
      description: "Implement wallet integration for claiming rewards. Previous research done on Metamask and WalletConnect integration.",
      tags: ["wallet-integration", "metamask", "walletconnect", "claiming", "rewards"]
    },
    {
      key: "REJUVEL-3236",
      id: "10578",
      title: "Single Use Code offers should have an RJV price/cost associated to them",
      status: "QA",
      priority: "Medium",
      assignee: "gabriel.nogueira",
      reporter: "Jasmine Smith",
      created: "2025-03-27T09:45:07.782-0300",
      updated: "2025-05-29T09:20:21.911-0300",
      description: "Single use codes should be redeemed with RJV (20-30 tokens). Currently implementation gives everything for free. Need tracking and ensure one code per user.",
      tags: ["rjv", "single-use-code", "pricing", "token-economics"]
    },
    {
      key: "REJUVEL-3177",
      id: "13251",
      title: "Add isExclusiveRjvpartner field to /store/products API endpoint",
      status: "QA",
      priority: "High",
      assignee: "gabriel.nogueira",
      reporter: "Yonatan Cherkos",
      created: "2025-03-10T18:05:59.365-0300",
      updated: "2025-05-29T09:20:21.915-0300",
      description: "Add is_exclusive_rjv_partner field to store products API response alongside existing is_rjv_partner field.",
      tags: ["api", "rjv", "store", "partner", "exclusive"]
    },
    {
      key: "REJUVEL-2898",
      id: "13104",
      title: "UX for Wallet & KYC screens",
      status: "In Progress",
      priority: "Highest",
      assignee: "Rajib Talukder Raju",
      reporter: "Rajib Talukder Raju",
      created: "2024-11-25T17:01:39.094-0300",
      updated: "2025-06-03T23:48:14.361-0300",
      description: "Design UX flow: 1) Verify proof of human (Civic), 2) Connect wallet, 3) Submit data + mint NFT, 4) Claim tokens. Some processes may happen off-app.",
      tags: ["ux", "wallet", "kyc", "civic", "nft-minting", "user-flow"]
    },
    {
      key: "REJUVEL-1667",
      id: "12874",
      title: "Investigate integration of Cardano token with App",
      status: "To Do",
      priority: "Medium",
      assignee: "Yared Solomon",
      reporter: "Jasmine Smith",
      created: "2023-08-26T17:35:15.786-0300",
      updated: "2025-04-14T23:38:37.458-0300",
      description: "Research Cardano integration for RJV claiming. RJV-ADA policy ID: 8cfd6893f5f6c1cc954cec1a0a1460841b74da6e7803820dde62bb78. Enable users to claim RJV on Cardano wallets.",
      tags: ["cardano", "rjv", "multi-chain", "claiming", "ada"]
    },
    {
      key: "REJUVEL-1308",
      id: "12531",
      title: "Concurrent calls in blockchain enabled mode",
      status: "To Do",
      priority: "Medium",
      assignee: "Yared Solomon",
      reporter: "Jasmine Smith",
      created: "2022-11-23T03:59:12.070-0300",
      updated: "2025-05-07T20:47:17.092-0300",
      description: "Implement token approach instead of channels for bs_net service calls to enable concurrent blockchain operations without scaling channel costs.",
      tags: ["blockchain", "concurrent", "optimization", "bs_net", "channels"]
    },
    {
      key: "REJUVEL-2866",
      id: "12104",
      title: "Update the /profiles API to accepts and send user goals",
      status: "PR Raised",
      priority: "Medium",
      assignee: "gabriel.nogueira",
      reporter: "Yonatan Cherkos",
      created: "2024-11-11T02:07:47.961-0300",
      updated: "2025-05-29T09:20:16.106-0300",
      description: "Update API to support user goals including EARNING_TOKENS as a goal option.",
      tags: ["api", "user-goals", "earning-tokens", "profiles"]
    }
  ],

  subtasks: [
    {
      key: "REJUVEL-2904",
      id: "12555",
      title: "Experiment Data NFT creation",
      status: "In Progress",
      priority: "High",
      assignee: "Yared Solomon",
      reporter: "Yared Solomon",
      created: "2024-11-28T05:23:37.912-0300",
      updated: "2025-05-12T09:20:22.676-0300",
      description: "Experiment with Data NFT creation process: KYC data hashing, signing process, smart contract calls, and documentation updates.",
      tags: ["data-nft", "experiment", "smart-contract", "kyc", "hashing"]
    },
    {
      key: "REJUVEL-2737",
      id: "12589",
      title: "Integrate Civic Uniqueness Pass",
      status: "To Do",
      priority: "High",
      assignee: "Yared Solomon",
      reporter: "Jasmine Smith",
      created: "2024-09-05T10:25:35.870-0300",
      updated: "2025-06-03T23:48:15.347-0300",
      description: "Integrate Civic solution for 1 user: 1 wallet verification. Removes need for hard KYC, uses face verification tied to wallet.",
      tags: ["civic", "kyc", "verification", "uniqueness", "face-scan"]
    },
    {
      key: "REJUVEL-3447",
      id: "10522",
      title: "Refactoring user service",
      status: "QA",
      priority: "Medium",
      assignee: "Pedro Mello",
      reporter: "Pedro Mello",
      created: "2025-05-16T17:52:37.810-0300",
      updated: "2025-05-29T09:28:25.338-0300",
      description: "Refactor UserService for scalable push notifications and token management.",
      tags: ["refactoring", "user-service", "notifications", "tokens"]
    }
  ],

  bugs: [
    {
      key: "REJUVEL-2871",
      id: "12134",
      title: "Inbuilt wallet function to give choice of withdrawing RJV token to external wallet",
      status: "Wont Do",
      priority: "Medium",
      assignee: null,
      reporter: "Andrew Selivanov",
      created: "2024-11-15T11:30:59.236-0300",
      updated: "2024-11-23T08:54:13.538-0300",
      description: "User suggestion to add RJV withdrawal to external wallets instead of only in-app spending.",
      tags: ["rjv", "withdrawal", "external-wallet", "user-suggestion"]
    },
    {
      key: "REJUVEL-2583",
      id: "13528",
      title: "After re-installing app via test flight, total token of 723 RJV dropped to zero",
      status: "Wont Do",
      priority: "Low",
      assignee: "Cendel Dogan",
      reporter: "Persival Ballesté",
      created: "2024-07-02T12:13:44.999-0300",
      updated: "2025-04-25T11:09:06.563-0300",
      description: "User lost 723 RJV tokens after app reinstall via TestFlight.",
      tags: ["rjv", "token-loss", "app-reinstall", "testflight"]
    },
    {
      key: "REJUVEL-2458",
      id: "13285",
      title: "Tokens disappeared after iPhone upgrade (719 RJV)",
      status: "Wont Do",
      priority: "High",
      assignee: null,
      reporter: "Persival Ballesté",
      created: "2024-05-20T10:02:01.573-0300",
      updated: "2024-07-11T09:53:53.219-0300",
      description: "User lost 719 RJV tokens after upgrading to new iPhone.",
      tags: ["rjv", "token-loss", "device-upgrade", "iphone"]
    },
    {
      key: "REJUVEL-2554",
      id: "11720",
      title: "Tokens went from blocked to zero",
      status: "Wont Do",
      priority: "High",
      assignee: "Cendel Dogan",
      reporter: "Persival Ballesté",
      created: "2024-06-23T09:54:24.853-0300",
      updated: "2025-04-25T11:09:06.513-0300",
      description: "User had blocked tokens that disappeared completely.",
      tags: ["rjv", "token-loss", "blocked-tokens"]
    },
    {
      key: "REJUVEL-1513",
      id: "10605",
      title: "Experiment and implementing Depay payment gateway",
      status: "Wont Do",
      priority: "Medium",
      assignee: "Yared Solomon",
      reporter: "Yonatan Cherkos",
      created: "2023-05-17T03:11:08.499-0300",
      updated: "2023-08-31T16:47:16.242-0300",
      description: "Attempted integration of DePay web3 payment gateway with Flutter mobile app using deep links.",
      tags: ["depay", "payment-gateway", "web3", "flutter", "deep-links"]
    },
    {
      key: "REJUVEL-3110",
      id: "11496",
      title: "Exception: Error in sending email notification",
      status: "PR Raised",
      priority: "Medium",
      assignee: "gabriel.nogueira",
      reporter: "Yared Solomon",
      created: "2025-02-19T18:54:53.824-0300",
      updated: "2025-05-29T09:20:21.968-0300",
      description: "Email notification error related to token/reward notifications.",
      tags: ["email", "notification", "error", "tokens"]
    }
  ],

  // Helper functions for data manipulation
  utilities: {
    getIssuesByStatus: function(status) {
      return this.getAllIssues().filter(issue => issue.status === status);
    },

    getIssuesByPriority: function(priority) {
      return this.getAllIssues().filter(issue => issue.priority === priority);
    },

    getIssuesByAssignee: function(assignee) {
      return this.getAllIssues().filter(issue => issue.assignee === assignee);
    },

    getIssuesByTag: function(tag) {
      return this.getAllIssues().filter(issue => 
        issue.tags && issue.tags.includes(tag)
      );
    },

    getAllIssues: function() {
      return [
        ...blockchainIssuesData.epics,
        ...blockchainIssuesData.stories,
        ...blockchainIssuesData.tasks,
        ...blockchainIssuesData.subtasks,
        ...blockchainIssuesData.bugs
      ];
    },

    getActiveIssues: function() {
      return this.getAllIssues().filter(issue => 
        !['Wont Do', 'Done', 'Closed'].includes(issue.status)
      );
    },

    getHighPriorityIssues: function() {
      return this.getAllIssues().filter(issue => 
        ['Highest', 'High'].includes(issue.priority)
      );
    },

    getInProgressWork: function() {
      return this.getAllIssues().filter(issue => 
        ['In Progress', 'QA', 'PR Raised'].includes(issue.status)
      );
    },

    searchIssues: function(searchTerm) {
      const term = searchTerm.toLowerCase();
      return this.getAllIssues().filter(issue =>
        issue.title.toLowerCase().includes(term) ||
        issue.description.toLowerCase().includes(term) ||
        (issue.tags && issue.tags.some(tag => tag.toLowerCase().includes(term)))
      );
    },

    getIssuesByDateRange: function(startDate, endDate) {
      const start = new Date(startDate);
      const end = new Date(endDate);
      return this.getAllIssues().filter(issue => {
        const created = new Date(issue.created);
        return created >= start && created <= end;
      });
    },

    getStatistics: function() {
      const allIssues = this.getAllIssues();
      const activeIssues = this.getActiveIssues();
      
      return {
        total: allIssues.length,
        active: activeIssues.length,
        completed: allIssues.length - activeIssues.length,
        highPriority: this.getHighPriorityIssues().length,
        inProgress: this.getInProgressWork().length,
        byAssignee: this.getAssigneeStats(),
        recentActivity: this.getRecentActivity()
      };
    },

    getAssigneeStats: function() {
      const assigneeCount = {};
      this.getActiveIssues().forEach(issue => {
        const assignee = issue.assignee || 'Unassigned';
        assigneeCount[assignee] = (assigneeCount[assignee] || 0) + 1;
      });
      return assigneeCount;
    },

    getRecentActivity: function() {
      const thirtyDaysAgo = new Date();
      thirtyDaysAgo.setDate(thirtyDaysAgo.getDate() - 30);
      
      return this.getAllIssues()
        .filter(issue => new Date(issue.updated) > thirtyDaysAgo)
        .sort((a, b) => new Date(b.updated) - new Date(a.updated));
    },

    exportToCSV: function() {
      const issues = this.getAllIssues();
      const headers = ['Key', 'Title', 'Type', 'Status', 'Priority', 'Assignee', 'Created', 'Updated'];
      const rows = issues.map(issue => [
        issue.key,
        `"${issue.title}"`,
        this.getIssueType(issue.key),
        issue.status,
        issue.priority,
        issue.assignee || 'Unassigned',
        issue.created.split('T')[0],
        issue.updated.split('T')[0]
      ]);
      
      return [headers, ...rows].map(row => row.join(',')).join('\n');
    },

    getIssueType: function(key) {
      if (blockchainIssuesData.epics.find(i => i.key === key)) return 'Epic';
      if (blockchainIssuesData.stories.find(i => i.key === key)) return 'Story';
      if (blockchainIssuesData.tasks.find(i => i.key === key)) return 'Task';
      if (blockchainIssuesData.subtasks.find(i => i.key === key)) return 'Sub-task';
      if (blockchainIssuesData.bugs.find(i => i.key === key)) return 'Bug';
      return 'Unknown';
    }
  },

  // Predefined queries for common use cases
  queries: {
    criticalPath: function() {
      return blockchainIssuesData.utilities.getAllIssues().filter(issue =>
        ['REJUVEL-2898', 'REJUVEL-1669', 'REJUVEL-2904', 'REJUVEL-3260'].includes(issue.key)
      );
    },

    walletRelated: function() {
      return blockchainIssuesData.utilities.getIssuesByTag('wallet')
        .concat(blockchainIssuesData.utilities.getIssuesByTag('wallet-integration'))
        .concat(blockchainIssuesData.utilities.getIssuesByTag('keyless-wallet'));
    },

    rjvTokenIssues: function() {
      return blockchainIssuesData.utilities.getIssuesByTag('rjv');
    },

    dataNftWork: function() {
      return blockchainIssuesData.utilities.getIssuesByTag('data-nft')
        .concat(blockchainIssuesData.utilities.getIssuesByTag('nft-minting'));
    },

    kycAndVerification: function() {
      return blockchainIssuesData.utilities.getIssuesByTag('kyc')
        .concat(blockchainIssuesData.utilities.getIssuesByTag('civic'))
        .concat(blockchainIssuesData.utilities.getIssuesByTag('verification'));
    },

    userExperienceIssues: function() {
      return blockchainIssuesData.utilities.getAllIssues().filter(issue =>
        issue.tags && (
          issue.tags.includes('user-experience') ||
          issue.tags.includes('ux') ||
          issue.tags.includes('onboarding')
        )
      );
    },

    infrastructureWork: function() {
      return blockchainIssuesData.utilities.getAllIssues().filter(issue =>
        issue.tags && (
          issue.tags.includes('infrastructure') ||
          issue.tags.includes('api') ||
          issue.tags.includes('blockchain') ||
          issue.tags.includes('smart-contract')
        )
      );
    }
  }
};

// Export for use in other contexts
if (typeof module !== 'undefined' && module.exports) {
  module.exports = blockchainIssuesData;
}

// Global access for browser environments
if (typeof window !== 'undefined') {
  window.blockchainIssuesData = blockchainIssuesData;
}

// Example usage and demonstrations
console.log('=== Blockchain Issues Data Structure Loaded ===');
console.log('Total Issues:', blockchainIssuesData.metadata.totalIssues);
console.log('Active Issues:', blockchainIssuesData.utilities.getActiveIssues().length);
console.log('High Priority Issues:', blockchainIssuesData.utilities.getHighPriorityIssues().length);

// Example queries
console.log('\n=== Example Queries ===');
console.log('Critical Path Issues:', blockchainIssuesData.queries.criticalPath().map(i => i.key));
console.log('Wallet Related Issues:', blockchainIssuesData.queries.walletRelated().map(i => i.key));
console.log('RJV Token Issues:', blockchainIssuesData.queries.rjvTokenIssues().map(i => i.key));
console.log('Data NFT Work:', blockchainIssuesData.queries.dataNftWork().map(i => i.key));

// Assignee workload
console.log('\n=== Assignee Workload ===');
console.log(blockchainIssuesData.utilities.getAssigneeStats());