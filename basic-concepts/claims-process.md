---
description: An outline of the claims process
---

# Claims Process

If a [claimable event](covered-events.md) for a given vault has occurred then the depositor may proceed to request a claim with the protocol. Claims can be processed directly via interactions with our smart contracts or via our dApp.&#x20;

The following steps summarize the process for most claims:&#x20;

Assume the following

* _**A** _ is the amount of the claim request.
* _**R**_** ** is the hack threshold, or the amount per unit that would validate a De-peg event. Each safe will have a unique value for _**R**_.&#x20;
* _**L**_ is the lock amount, or the amount locked I order to prevent a bank run&#x20;
* **safeXXX** represents a Bedrock safe and xxx would represent an asset like Dai e.g. safe(Dai)
* _**allSafes**_ represents the value across all Bedrock safes
* **f** is the claim fee&#x20;

####

#### Validation and reimbursement&#x20;

1. After a [claimable event ](covered-events.md)occurs such as the the price of a deposited asset decreasing by 50%,  a user can submit a claim request to the Safe holding the asset. &#x20;
2. The protocol will validate the De-peg event by validating price history from the supported protocols essentially checking to see if the an asset like _Dai < **R**_
3. The protocol will then validate that the users wallet is a valid depositor into the Safe.&#x20;
4. Once confirmed the protocol will lock platform assets to calculate a reimbursement amount following a calculation based on his/her deposited assets and all available assets controlled by Bedrock. A sample calculation follows:&#x20;
   1. _**L = A \* (totalSupply(safeDai)/totalSupply(allSafes)**_
5. The reimbursement amount will be a proportional share of the users assets of based on the Total value locked in the protocol minus fees.&#x20;
6. The protocol will calculate and validate that the claimer has **A**+**L** (amount + LockedAmount) and reduce their balance accordingly. The amount is not available immediately and will be subject to a claims lock period presented as _**Pc.**_ The claim lock period is represented in hours.
7. For facilitating a claim Bedrock takes a fee often labeled as _**f**_ currently capped at 5% of the claim value. The fee is sourced from the claim requester and half of this fee goes to a community pool, the other half is earned by the protocol.&#x20;
8. In order to ensure the depositor is not only receiving devalued assets, they will also receive alternative assets controlled by the protocol as compensation. An example would be if 100 Dai is being requested and has been devalued, the protocol will source alternative stable-coins such as USDT and USDC as compensation. This leads to the most common question what I the impact on unhacked depositors, this is best illustrated as follows:&#x20;
   1. An unhacked depositors balance = (A - F) \* (**unhacked user balance** / _**totalSupply(allSafes)**_
   2. _As compensation the users that supplied capital are reimbursed with Bedrock tokens_

