---
description: How Withdrawals work
---

# Withdrawal

Users can deposit and withdraw assets into Bedrock at any time as long as a claimable event is not   occurring. Users must connect their wallet to the dApp , identify the Vault they deposited funds into and choose to Withdraw.&#x20;

In oder to avoid a bank run during a claimable event  we have implemented a withdraw delay. The protocol includes a&#x20;

```
Withdraw _parameter
```

The withdraw parameter is a value controlled by governance that controls how much the protocol charges to enable an instant withdrawal.&#x20;



```applescript
WITHDRAW_FEE_PARAM is 0.05 as a constant value
  If a user wants to withdraw 1000 USDC in one day
    withdraw_fee_percent = 0.05 / 1 (5%)
    so he will pay 50 USDC as a fee and withdraw 950 USDC
  If user wants to withdraw 1000 USDC in two days
    withdraw_fee_percent = 0.05 / 2 (2.5%)
    so he will pay 25 USDC as a fee and withdraw 975 USDC
  If user wants to withdraw 1000 USDC in three days
    withdraw_fee_percent = 0.05 / 3 (1.667%)
    so he will pay 16.67 USDC as a fee and withdraw 983.33 USDC
  If user wants to withdraw 1000 USDC in four days
    withdraw_fee_percent = 0.00
    so he will pay 0.00 USDC as a fee and withdraw 1000 USDC //(Excluing Gas fees)
```

Users who can wait several days to withdraw are subject to zero fees.&#x20;
