---
description: How Withdrawals work
---

# Withdrawal

Users can deposit and withdraw assets into Bedrock at any time as long as a [claimable event](covered-events.md) is not   occurring. Users must connect their wallet to the dApp , identify the Safe they deposited funds into and choose to Withdraw.&#x20;

In oder to avoid a bank run during a claimable event we have implemented a withdraw delay. The protocol includes a fee free period (labeled as _**Pf**_) and a withdraw delay that helps our contracts understand when to avoid charging a fee.

The values for both are controlled by governance that controls how much the protocol charges to enable an instant withdrawal.&#x20;

The following illustrates how a Withdraw can occur.&#x20;

Assume the following:

* _**A**_ is the amount of the claim request.
* _**D**_ is the amount delay a user is willing to accept to withdraw. A Bedrock user selects this delay as part of the withdraw process.&#x20;
* _**Pf**_ is the fee free period in hours, withdrawing after this time limit incurs no fees &#x20;
* **safeXXX** represents a Bedrock safe and xxx would represent an asset like Dai e.g. safe(Dai)

1. A user sends a withdraw request to safeDai with \[amount A , delay D]
2. safeDai checks the users balance and reduces it by A if the request is valid
3. Depending on the Withdraw delay chosen (_**D**_) the protocol will calculate a fee.
   1. $$fee = A * max(0,Pf-D /Pf)^2$$
   2. If a fee is sourced from the user withdrawing  half of this fee goes to a community pool, the other half is earned by the protocol.&#x20;
4. After **D** hours have passed the user can source the requested withdraw amount which can be summarized as _**A - Fee**_.&#x20;
5. Users who can wait several days to withdraw funds are subject to **zero fees**.&#x20;

{% hint style="info" %}
This is a unique model, but since coverage for some of the products has no expiration date it enables the protocol to earn a fee for providing protection.&#x20;
{% endhint %}

The Gherkin-like summary tries to use an example to explain the impact on the withdrawer.&#x20;

```applescript
FEE_FREE_PERIOD (Pf) is 96 (= 4 days) as a constant value
  If user wants to withdraw 1000 USDC in 24 hours
    withdraw_fee_percent = ((96 - 24) / 96) ^ 2 (56.25%)
    so he will pay 562.5 USDC as a fee and withdraw 437.5 USDC
  If user wants to withdraw 1000 USDC in 48 hours
    withdraw_fee_percent = ((96 - 48) / 96) ^ 2 (25%)
    so he will pay 250 USDC as a fee and withdraw 750 USDC
  If user wants to withdraw 1000 USDC in 72 hours
    withdraw_fee_percent = ((96 - 72) / 96) ^ 2 (6.25%)
    so he will pay 62.5 USDC as a fee and withdraw 937.5 USDC
  If user wants to withdraw 1000 USDC in 96 hours (or longer than it)
    withdraw_fee_percent = 0.00
    so he will pay 0.00 USDC as a fee and withdraw 1000 USDC //(Excluing Gas fees)
```

Users who can wait several days to withdraw are subject to zero fees.&#x20;



