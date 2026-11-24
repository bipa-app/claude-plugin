# Business reviewer access

MCP URL: `https://mcp.bipa.app/business/connector/mcp`. Keep OAuth enabled and this URL unchanged. This is separate from the personal read-only connector and the full Business MCP.

1. Open `https://mcp.bipa.app/business/connector/oauth/reviewer` and enter the credentials supplied privately with the submission.
2. Return to Claude and connect within ten minutes in the same browser.
3. Select **Connect fictional account** for Café Aurora Demo Ltda, or **Connect a fictional company opening its account** for Padaria Aurora Demo Ltda.
4. Sign in on the reviewer page again before each new connection. The reviewer browser permission is consumed by one connection or expires after ten minutes.

No mobile app, verification code, real company or real funds are required. Normal customer OAuth remains separate. The account reviewer grants `financial:read`, `account:read`, `receiving:manage` and `records:write`. Its links and deposit addresses are fictional; Pix charge sends reach no recipient.

## Example checks

- Ask for balances: the fictional account has R$ 48.250,75, 0.12 BTC and 1,500 USDT.
- Ask for pending requests: R$ 3.250,00 to Fornecedor Demo Ltda awaits a person's approval.
- Read payment links and Pix charges: Pedido 1042 is R$ 450,00; Pedido 1043 is R$ 180,00.
- Create and deactivate a fictional R$ 25 Pix payment link, then create and cancel a fictional R$ 10 Pix charge, confirming details first.
- Read documents and payables, change a category, and verify the returned state.
- Ask to pay, approve a payment or convert assets: those operations are unavailable on this listed connector.
- Connect the opening company and ask what remains: the response names each next step and the person who completes it in Bipa Business.

Validate every exposed tool, authentication refresh/reconnect, masked identifiers and refusal cases before attesting that testing is complete. These instructions are not a test result.

## Crypto scope for policy review

The connector reads crypto balances, statements and existing conversion orders. Payment links may receive BTC or USDT, and deposit-address requests return crypto deposit addresses. It exposes no buying, selling, converting, sending or withdrawing crypto. This scope requires Anthropic's assessment under section 4.A of its [Software Directory Policy](https://support.claude.com/en/articles/13145358-anthropic-software-directory-policy). No exception or approval is asserted by this package.
