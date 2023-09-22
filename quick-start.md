---
description: Create a dapp using Snowballs SDK
---

# Quick Start

## Lit Protocol and Alchemy AA

{% code overflow="wrap" lineNumbers="true" %}
```typescript
import { Snowball, LitAuth, AlchemyAA, Chain, CHAINS } from "@snowballtools/snowball-ts-auth";

const litAuth = new LitAuth(LIT_RELAY_API_KEY, CHAINS.goerli);
const smartWallet = new AlchemyAA(
  litAuth,
  ALCHEMY_GOERLI_API_KEY,
  ALCHEMY_GOERLI_GAS_POLICY_ID
);
export const snowball = new Snowball(smartWallet);
```
{% endcode %}

## Turnkey and Alchemy AA

## Lit Protocol  and Fun.xyz

...
