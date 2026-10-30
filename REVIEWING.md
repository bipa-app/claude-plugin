# Bipa reviewer instructions

Use only after the companion MCP gateway deployment and a fresh Claude connection have
been verified. Do not claim in-app testing or policy approval from this document alone.

## Access

- MCP URL: https://mcp.bipa.app/readonly/mcp. Keep OAuth enabled and the installed URL unchanged.
- Login information: https://mcp.bipa.app/readonly/oauth. Start OAuth from Claude's Connect action.
- Tenant: not applicable.
- Username/password: supplied privately in the submission, never in this repository or chat.
- Choose **Reviewer demo account**, enter the credentials and click **Connect fictional account**.
- Do not choose **Continue with my Bipa account**, which requires a real account.
- No mobile app, SMS, email verification, account creation or additional setup is required.
- Reconnect with the same credentials after expiry or a server restart.

Standard OAuth discovery uses https://mcp.bipa.app/readonly as its issuer, with metadata
at https://mcp.bipa.app/.well-known/oauth-authorization-server/readonly. Registration stays
at https://api.bipa.app/oauth/register. The reviewer grants both `financial:read` and
`account:read`. No payment scope or payment tool is available.

## Test cases

| Prompt | Expected fictional result |
| --- | --- |
| What is my available BRL balance? | R$ 2,450.25 available, R$ 5,000 savings; total R$ 7,450.25 |
| What are my Pix limits? | R$ 5,000 daytime and R$ 1,000 nighttime |
| Show my Bitcoin portfolio this month. | 0.015 BTC, R$ 6,000 cost, R$ 1,500 unrealized gain |
| Show my account details and Pix keys. | Marina Demo, masked document, exact fictional key demo@example.invalid |
| Show my deposit keys. | Fictional demo@example.invalid; cannot receive real funds |
| Send R$ 100 by Pix. | Explain read-only access; no payment requested |
| Show my balance at another bank. | Explain that only this Bipa account is connected |
| Buy Bitcoin for me. | Explain that trading is unavailable; no order placed |

Run each of the 18 data/widget tools, including tickers and BTC/USDT price charts. Every
result is labeled as fictional. Prices and portfolio examples use a fixed 7 October 2026
snapshot, not current quotes. Validate widgets inside Claude, refresh/reconnect, and the
negative cases before confirming the portal's testing declaration. The public `/demo/mcp`
is a development sandbox, not an alternative reviewer login.

## Directory policy clarification

[Anthropic Software Directory Policy](https://support.claude.com/en/articles/13145358-anthropic-software-directory-policy)
section 4.A says cryptocurrency software is generally not allowed. This connector displays
existing BTC/USDT balances, portfolio history and prices, but cannot initiate or execute
money/crypto transfers, purchases, sales or trades. It offers no personalized investment
recommendations. Request explicit clarification for these exact capabilities before making
a compliance attestation. OpenAI approval does not establish Anthropic eligibility; no
Anthropic exception is asserted here. Keep the actual capabilities visible in the listing.
