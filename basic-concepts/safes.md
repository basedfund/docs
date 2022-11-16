---
description: Description of Bedrock Safes
---

# Safes

Bedrock stores assets deposited into the protocol in a Safe. Each Safe has unique criteria that determine what would be considered a claimable event. At the moment the following Safes are supported:&#x20;

* USDC&#x20;
* USDT
* DAI

Each safe will outline at what price point a De-peg event will qualify for a claim. We typically refer to this in our documentation as a hack event and represent it using the letter _**R**_.



Safes may or may not have fees associated to them including:&#x20;



**A deposit fee:** A fee charged to access coverage offered by a Bedrock Safe

**A withdraw parameter:** The withdraw parameter calculates a fee charged to those who require an instant withdrawal when the Safes are unlocked. You can learn more about the withdrawal process [here.](withdrawal.md)&#x20;

**A claim fee:** A fee charged by the protocol to process a claimable event. Typically represented as a percentage of your claim amount.&#x20;

{% hint style="info" %}
<pre><code><strong>A safe may also contain an expiry date after which coverage for a particular
</strong>asset is no longer valid. This is not currently used in any active Safes. </code></pre>
{% endhint %}



