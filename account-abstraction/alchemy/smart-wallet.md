# Smart Wallet



{% code overflow="wrap" lineNumbers="true" %}
```typescript
sendUserOperation(targetAddress: Address, data: Address, sponsorGas: Boolean) => Promise<{ hash: string; }>
getAddress: () => Promise<Address>;
waitForUserOperationTransaction: (hash: Hash) => Promise<Hash>;
getUserOperationByHash: (hash: Hash) => Promise<UserOperationResponse>;
getUserOperationReceipt: (hash: Hash) => Promise<UserOperationReceipt>;
```
{% endcode %}

#### Needs testing,

```typescript
sendTransaction: (request: RpcTransactionRequest) => Promise<Hash>;
```

```typescript
sendTransactions: (request: RpcTransactionRequest[]) => Promise;
```

Converts eth transaction(s) to user ops&#x20;

@param request - a {@link RpcTransactionRequest} Array representing a traditional ethereum transaction

@returns the transaction hash

```typescript
request(args: { method: string; params?: any[] }): Promise<any>;
```

EIP-1193

@param args - object containing the method and params to execute

@returns the result of the method call

```typescript
signMessage: (msg: string | Uint8Array) => Promise<Hash>;
```

@param msg - message to be signed

@returns the signed hash for the message passed

```typescript
signTypedData: (params: SignTypedDataParameters) => Promise<Hash>;
```

sign typed data as per ERC-712

@param params - {@link SignTypedDataParameters}

@returns the signed hash for the message passed

```typescript
signMessageWith6492(msg: string | Uint8Array | Hex): Promise<Hex>;
```

If the account is not deployed, it will sign the message and then wrap it in 6492 format

@param msg - the message to sign

@returns ths signature wrapped in 6492 format

```typescript
signTypedDataWith6492(params: SignTypedDataParams): Promise<Hash>;
```

If the account is not deployed, it will sign the typed data blob and then wrap it in 6492 format

@returns the signed hash for the params passed in wrapped in 6492 format
