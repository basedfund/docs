---
description: Description of Bedrock Strategies
---

# Strategies & Fees

Bedrock stores assets deposited into the protocol in a Safe. Each Safe has a unique strategy it follows to generate returns. At the moment the Safes only support depositing USDC.&#x20;

Bedrock launched with two primary strategies:&#x20;



**Pulse: Market Neutral market making**&#x20;

This strategy mimics the methods used by high frequency market making firms to stay as market neutral as possible and scanning order books for opportunities to provide liquidity on various exchanges.&#x20;

**Navigator: Long / Short Strategy**&#x20;

A long/short methodology used to navigate relatively calm crypto markets by using leverage to extract returns in low frequency trades.





Safes may or may not have fees associated to them including:&#x20;



**A deposit fee:** A fee charged to access a stategy

**Asset fee:**  Strategies may charge a fee to manage the number of assets in a given strategy. This is typically 0.5 - 2% of the assets deposited.&#x20;

**A performance fee:** A fee charged by the strategy that chargs a percentage of the excess return provided to the investor.&#x20;

{% hint style="info" %}
<pre><code><strong>A strategy may also contain an expiry date after which deposits are no longer accepted
</strong>. This is not currently used in any active Safes. 
</code></pre>
{% endhint %}



