---
description: Create a dapp using Snowballs SDK
---

# Quick Start

## Lit Protocol and Alchemy AA

> NOTE: Snowball will handle key generation in our next iteration

{% code overflow="wrap" lineNumbers="true" %}
```typescript
import {
  Snowball,
  CHAINS,
  AuthProvider,
  SmartWalletProvider,
  AlchemySmartWalletProviderKey,
} from "@snowballtools/snowball-ts-sdk";
import {
  ALCHEMY_GOERLI_API_KEY,
  ALCHEMY_GOERLI_GAS_POLICY_ID,
  ALCHEMY_SEPOLIA_API_KEY,
  ALCHEMY_SEPOLIA_GAS_POLICY_ID,
} from "./env";

export const snowball = new Snowball(
  "snowball-test",
  CHAINS.goerli,
  {
    name: AuthProvider.lit,
  },
  {
    name: SmartWalletProvider.alchemy,
    apiKeys: {
      [AlchemySmartWalletProviderKey.ethereumGoerli]: ALCHEMY_GOERLI_API_KEY,
      [AlchemySmartWalletProviderKey.ethereumGoerli_gasPolicyId]:
        ALCHEMY_GOERLI_GAS_POLICY_ID,
      [AlchemySmartWalletProviderKey.ethereumSepolia]: ALCHEMY_SEPOLIA_API_KEY,
      [AlchemySmartWalletProviderKey.ethereumSepolia_gasPolicyId]:
        ALCHEMY_SEPOLIA_GAS_POLICY_ID,
    },
  }
);
```
{% endcode %}

Methods:

{% code overflow="wrap" lineNumbers="true" %}
```typescript
register(username: string): Promise<void>; // passkey
authenticate(): Promise<void>; // passkey
getEthersWallet(): Promise<PKPEthersWallet>;
changeChain(chain: Chain): void;
sendUserOperation(targetAddress: Address, data: Address, sponsorGas: Boolean): Promise<{ hash: string; }>
getAddress(): Promise<Address>; // smart wallet (incl counterfactual)
waitForUserOperationTransaction(hash: Hash): Promise<Hash>;
getUserOperationByHash(hash: Hash): Promise<UserOperationResponse>;
getUserOperationReceipt(hash: Hash): Promise<UserOperationReceipt>;
```
{% endcode %}

Possible errors:[​](https://developer.litprotocol.com/v3/migration/overview/#using-nextjs)

If you are using **Next.js ^12**, you may encounter the following [error](https://github.com/vercel/next.js/issues/28774):

```sh
Module build failed: UnhandledSchemeError: Reading from "node:buffer" is not handled by plugins (Unhandled scheme).
```

Implement the [following workaround](https://github.com/vercel/next.js/issues/28774#issuecomment-1264555395) in your `next.config.js` file:

```javascript
module.exports = {
  // Your Next.js config
  // ...
  webpack: (config, options) => {
    config.plugins.push(
      new webpack.NormalModuleReplacementPlugin(/^node:/, (resource) => {
        resource.request = resource.request.replace(/^node:/, "");
      })
    );
    return config;
  },
};
```
