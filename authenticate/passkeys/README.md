# Passkeys

Passkeys enable secure passwordless authentication (aka no more usernames or passwords) using cryptography. Typically, an authenticator -- can be your device, password manager, or (edge case locally via) browser -- generates a public-private key pair and sends the public key to the relying party (server) that'll use it to authenticate the user via challenge. For years, Google has been one of its biggest advocates. Apple has finally pushed its ecosystem-wide adoption in iOS 17.&#x20;

#### [passkeys.io](https://www.passkeys.io/),

> A passkey is a **new way to sign in** that works completely **without passwords**. By using the security capabilities of your devices like Touch ID and Face ID, passkeys are way **more secure** and **easier to use** than both passwords and all current 2-factor authentication (2FA) methods.
>
> ...
>
> ### Who’s behind passkeys? <a href="#who-s-behind-passkeys" id="who-s-behind-passkeys"></a>
>
> Passkeys are a joint initiative of Apple, Google, and Microsoft to make authentication better. It’s the consumerization of enterprise security standards [FIDO](https://fidoalliance.org/) and [WebAuthn](https://www.w3.org/TR/webauthn-2/). Passkeys make proven web API [WebAuthn](https://www.w3.org/TR/webauthn-2/) usable in consumer scenarios like e-commerce, banking, and social media as well as prosumer cases like SaaS.

* [WebAuthn](https://www.w3.org/TR/webauthn-2/): standard for public-private authentication
* [FIDO ("Fast IDentity Online") Alliance](https://fidoalliance.org/)
* Passkey demos and resources:
  * Web2: [https://www.passkeys.io/](https://www.passkeys.io/)
  * Web3: [https://passkeys.is/](https://passkeys.is/)
* [Apple docs](https://developer.apple.com/documentation/authenticationservices/public-private\_key\_authentication)
* [Google Security Blog](https://security.googleblog.com/2023/05/making-authentication-faster-than-ever.html) on passkeys versus passwords

Using the [WebAuthn](https://www.w3.org/TR/webauthn-2/) standard, crypto abandons seed phrases, in-wallet browsers, and jumping between your dapp and wallet for authentication and signing. Snowball supports multiple providers each with unique implementations. Read more about each to see which fits your needs best.
