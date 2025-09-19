---
description: '5-10% Supply: Dual token rewarder for Launch participants (custom contract)'
---

# believer

### [disclaimer](believer.md#disclaime)

## overview

Believer is the last stage of the launch event and is designed to reward token holders that participated during the launch. Since the Masterchef is designed to reward desired activity during the launch, Believer has been directly coupled to the rewards distributed from that contract.

Believer is a dual token rewarder. Rewards are distributed to depositors at a constant rate proportional to their deposit amounts (similar to the Masterchef). However, Believer adds a constraint on participation with a deposit allowance. The deposit allowance in the Believer can only be increased with WESMOL deposits and is reduced when SMOL is withdrawn.

_Note: WESMOL deposits are disabled for the duration of the Launch. Participants will not be able to wrap their SMOL into WESMOL. WESMOL can only be earned by participating in either the Masterchef or Believer rewarders._

## how it works

The Believer contract operates with two tokens: SMOL and WESMOL.

### deposits

Participants can deposit both SMOL and WESMOL tokens to earn rewards. Each address has a deposit allowance that limits how much SMOL can be deposited.

* **WESMOL Deposits**:
  * No restrictions on deposits.
  * Automatically unwrapped to SMOL upon deposit
  * Increases SMOL deposit allowance by some multiple (parameter)
* **SMOL Deposits**:
  * Restricted by deposit allowance
  * Can be withdrawn at any time

### **rewards**

Rewards are distributed continuously at a fixed daily rate, split proportionally among all depositors based on their deposit amounts. The more a user deposits relative to others, the larger their share of daily rewards.

* **WESMOL Rewards**
  * Accumulate continuously
  * Depositors may claim at any time

### **withdrawals**

Depositors may withdraw their deposits at any time.

* **SMOL Withdrawals:**
  * Deposits are not subject to any lock and are available immediately.
  * Users receive a credit to their deposit allowance upon withdrawal, set by a parameter. The credit will be less than the amount withdrawn, so they will be unable to reach the same deposit level without additional WESMOL deposits.

## participation and timeline

All WESMOL holders may participate in the Believer contract. The Believer contract will be available shortly after the auction ends and WESMOL withdrawals are enabled. There will be a period of overlap with the Masterchef to allow users to continue to earn WESMOL for additional Believer deposits.

Believer is expected to run for approximately 6 weeks. The duration may be adjusted based on participation.

## parameters

* **Daily Reward Rate:** 2,000,000 - 2,500,000 WESMOL distributed per day
* **Deposit Multiplier:** 5x increase to deposit allowance per WESMOL deposited
* **Withdrawal Multiplier:** 0.5x increase to deposit allowance per SMOL withdrawn

_Parameters may be adjusted to ensure optimal participation and fair distribution._
