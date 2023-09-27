---
description: Setup Smart Account Wallets
---

# Alchemy

{% embed url="https://www.alchemy.com/account-abstraction" %}

*   #### Bundler APIs

    Submit censorship-resistant transactions to smart contract accounts.
*   #### Gas Manager APIs

    Cover gas costs for your users, and programmatically control gas policies using the Gas Manager Admin APIs.
* **Account Abstraction SDK**

**For Snowball,**

```typescript
export enum AlchemySmartWalletProviderKey {
  goerli
  sepolia
  goerli_gasPolicyId 
  sepolia_gasPolicyId 
}
```

On initializing Snowball, to use Alchemy as your smart wallet provider, initialize `SmartWalletProvider` with api keys for each chain and its respective gas policy id found via their dashboard: [https://dashboard.alchemy.com](https://dashboard.alchemy.com/)

> NOTE: Snowball will handle key generation in our next iteration

<pre class="language-typescript"><code class="lang-typescript"><strong>{
</strong>    name: SmartWalletProvider.alchemy,
    apiKeys: {
        [AlchemySmartWalletProviderKey.goerli]: "key",
        [AlchemySmartWalletProviderKey.goerli_gasPolicyId]: "gasPolicyId",
        [AlchemySmartWalletProviderKey.sepolia]: "key",
        [AlchemySmartWalletProviderKey.sepolia_gasPolicyId]: "gasPolicyId",
    },
}
</code></pre>
