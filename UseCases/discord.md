# ONE EXAMPLE USE CASE
### 1. Holder-Only Alpha / Private Discord Servers

### Projects running private Discord servers can allow access only to wallets that hold:



```X amount of the token```



> User clicks “Join Discord” → X402 checks wallet → generates a one-time Discord invite → user joins.


## Why This Matters / What Pain It Solves

> No backend complexity  devs don’t need to run a server that issues invites, verifies signatures, checks balances, and revokes links. X401 handles the verification logic with a simple 401 challenge → dev just plugs in the rule.

> Standard HTTP behavior, not custom auth flows instead of inventing yet another “signature endpoint”  X401 uses a normal 401 Unauthorized challenge making it cleaner

> Eliminates bot abuse  Discord invite links normally leak or get stolen.

> A one-time invite generated only after wallet verification removes 90% of bot/spam problems for gated communities.


> Works with any token logic  devs can gate with token balance

> No rewriting checks across different platforms.

> No new accounts, no forms, no friction.

> Auditable and portable because X401 is a protocol, not a SaaS lock-in, devs can swap providers, self-host, or extend it without breaking clients.
