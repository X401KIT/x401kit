# ONE EXAMPLE USE CASE

## 1. Token-Gated Custom Data / Business Logic

## Projects can expose any custom data or internal logic only to wallets that meet certain on-chain conditions, such as holds: 


`X amount of the token`



> User tries to fetch  protected data → X401 returns a 401 challenge → user signs → X401 verifies → user receives the gated data/response.



## Why This Matters / What Pain It Solves

> Protects internal APIs without building custom auth
> Developers often expose custom endpoints  and need gating — but building signature verification, token checking, and rule engines is messy.

> X401 converts this into a simple HTTP 401 flow.

> No more duplicating wallet-auth logic across endpoints

> With X401, any endpoint automatically becomes token-gated without rewriting handlers.

> Works every type of data

> X401 doesn’t care what your backend does etc. Everything can be gated with on-chain conditions.

> Prevents API key leaks or sharing

> Instead of managing API keys (which leak constantly), access is tied to wallets.

> A user can’t share their “wallet ownership,” unlike a key.

> Zero infrastructure lift
> No need to maintain:

> Better UX, less friction
> User hits the endpoint → signs once → gets access.
> No OAuth, no account creation, no passwords.

> Open protocol, not vendor lock-in
> Devs can self-host or move providers with zero code changes.