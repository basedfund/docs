---
description: What events are typically covered by Bedrock
---

# Covered Events

While Bedrock aims to cover a wide range of events we would prefer to focus on [parametric risks](https://en.wikipedia.org/wiki/Parametric\_insurance) that can be observed by our protocol directly, a group of trusted oracles, or a network of trusted APIs.&#x20;



#### Covered Events

We are starting our V1 by measuring and tracking pricing events, specifically as they relate to Stable coins like USDC, USDT and Dai. These assets are typically designed to be pegged to the value of a currency by being backed by outside assets or other cryptocurrencies at some predetermined ratio.  The first available Bedrock vaults will cover depositors of these assets against a depeg event that would lower the value of the deposited asset against its target currency.&#x20;



#### Example&#x20;

1. A user or protocol deposits Dai from MakerDAO into Bedrock&#x20;
2. 1 month after depositing the value of Dai goes from 1 Dai to 1 USD to 1 Dai for 0.88 USD
3. The depositor may file a claim and our smart contracts will validate that the cryptocurrency did in fact deviate from its stated peg.&#x20;
4. The protocol will enable the user to redeem the value of his assets based on their share of the pool of assets deposited into the protocol.&#x20;

#### Reimbursement Calculation&#x20;

