# Soc-25: On-Chain Crowdfunding

This project demonstrates a complete on-chain crowdfunding system implemented and tested using Python, Web3.py, EthereumTester, and Solidity smart contracts compiled via py-solc-x. The entire workflow is designed to run in Google Colab.

---

## Week-wise Progress

### Week 1
- Set up the Python environment using Web3, EthereumTester, and py-solc-x.
- Installed Solidity 0.8.0 and compiled the contract using `compile_source`.
- Deployed a basic `Crowdfunding` contract using EthereumTesterProvider in Python.

### Week 2
- Defined a `Campaign` struct inside the Solidity contract, with fields like `owner`, `title`, `goal`, `deadline`, `raised`, `withdrawn`, and a mapping for `contributions`.
- Used a global `campaignCount` and mapping to track all campaigns.
- Added `createCampaign()` to let users start new campaigns with a title, funding goal, and deadline duration.

### Week 3
- Implemented `contribute()` function allowing users to send Ether to a campaign.
- Used `msg.value` and `msg.sender` to track contribution values and contributors.
- Emitted a `Contributed` event and updated the raised amount.

### Week 4
- Added `withdrawFunds()` to allow campaign owners to withdraw funds if the goal is met and the deadline has passed.
- Added `refund()` to allow contributors to reclaim funds if the goal was not met by the deadline.
- Used `require`, `block.timestamp`, and `noReentrant` modifier to enforce logic and prevent attacks.

### Week 5
- Introduced events: `CampaignCreated`, `Contributed`, `FundsWithdrawn`, and `Refunded`.
- Each major state change now logs information useful for indexing and frontend apps.

### Week 6
- Simulated contributions and refunds using multiple Ethereum test accounts.
- Waited for deadlines using `time.sleep()` in Colab.
- Queried smart contract state using `getCampaign()` and `getContribution()`.

### Week 7
- A basic frontend was considered using Ethers.js for interacting with the contract.
- Features like listing campaigns, displaying contribution status, and live funding progress were outlined.
- Deployment target: Netlify or Vercel.

### Week 8 
- Project was packaged and documented with complete testing scripts.
- Final state and logic validated in Python notebook using EthereumTester.
- Ready for testnet deployment and community demo.

---

## How to Run

> Designed to run in a Google Colab notebook.

1. Install dependencies:
```python
!pip install web3 py-solc-x eth-tester==0.9.0b1 py-evm==0.7.0a2
