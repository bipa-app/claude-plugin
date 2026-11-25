# Bipa reviewer instructions

The package targets the full personal connector. Verify the deployed revision and a fresh connection before claiming provider testing is complete.

## Access

- MCP URL: https://mcp.bipa.app/mcp. Keep OAuth enabled.
- Private login: https://mcp.bipa.app/oauth/reviewer. Credentials are supplied privately, never in this repository or chat.
- Sign in privately, return to Claude in the same browser within ten minutes, connect and choose **Connect fictional account**.
- Each sign-in enables one fictional connection. Normal customer OAuth remains separate.
- No real account, funds, mobile app, verification code or account creation is needed.
- Issuer: https://mcp.bipa.app. Discovery: https://mcp.bipa.app/.well-known/oauth-authorization-server. Dynamic registration stays at https://api.bipa.app/oauth/register.
- Scopes: `financial:read account:read payments:request payments:execute_trusted`. Read-only tokens from `/readonly/mcp` cannot authorize this resource.

## Test flow

Exercise all 61 data/widget tools. A widget receives the matching data tool's unchanged `structuredContent`.

1. Read account, balances, keys, limits, portfolio, prices, history, timeline and transaction detail. The initial account is Marina Demo with R$ 2,450.25 available and R$ 5,000 savings. Prices and sample history use the fixed 7 October 2026 snapshot. Account documents are masked; demo@example.invalid is fictional and cannot receive funds.
2. Confirm and generate a R$ 1 BR code for demo@example.invalid. Preview and decode it. The code is deliberately invalid for real payment rails and only works inside its fictional session.
3. Separately confirm ordinary R$ 1 Pix requests by key, tag `$demo`, saved recipient ID 1 and the generated BR code. Also request the fixed R$ 1 boleto (47 zeros) and DDA bill ID 1. Each returns pending approval with its request/approval identifier.
4. The assistant gives you the browser approval URL. Only you approve or reject, using the browser that connected the session. Polling must not approve. After approval, status becomes simulated completion and the fictional balance changes; rejection leaves it unchanged. DDA list shows a paid bill after approval. The assistant must not open or submit approval for you.
5. Read trusted contacts and explicitly confirm R$ 1 to trusted contact ID 1. This models prior authorization up to R$ 100 and executes immediately, without another browser approval. Verify its final status and balance.
6. Reuse an identical payment request's UUIDv7 key: it must not spend twice. Changing its data with the same key must fail. Check token refresh, revocation and isolation from another reviewer session.

The fictional session lasts one hour, permits up to 32 payment requests and 32 receiving codes, and does not support scheduled payments. These reviewer limits do not define real-account limits. Unknown recipients, real destinations and foreign-session BR codes are refused.

Negative cases: no CPF key input or identity collection; no assistant approval; no payment without explicit chat confirmation; no trading or conversions; no access to unrelated accounts; no silent fallback from a real account to fictional data.

## Provider disclosure

This connector reads crypto balances, portfolio history and market prices, creates Pix receivables, requests ordinary payments and executes previously authorized trusted-contact Pix. It does not trade or convert assets. Keep these capabilities visible. A blanket declaration that it cannot initiate or execute transfers would be false; do not accept it. Obtain the provider's applicable review route without removing the requested scope. No policy exception, approval or publication is asserted by this package.
