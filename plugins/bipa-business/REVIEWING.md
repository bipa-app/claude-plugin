# Business reviewer access

MCP URL: `https://mcp.bipa.app/business/connector/mcp`. Keep OAuth enabled and this URL unchanged. This is separate from the personal read-only connector and the full Business MCP.

1. Open `https://mcp.bipa.app/business/connector/oauth/reviewer` and enter the credentials supplied privately with the submission.
2. Return to Claude and connect within ten minutes in the same browser.
3. Select **Connect fictional account** for Café Aurora Demo Ltda, or **Connect a fictional company opening its account** for Padaria Aurora Demo Ltda.
4. Sign in on the reviewer page again before each new connection. The reviewer browser permission is consumed by one connection or expires after ten minutes.

No mobile app, verification code, real company or real funds are required. Normal customer OAuth remains separate. The account reviewer grants the seven account permissions: `financial:read`, `account:read`, `payments:request`, `conversions:execute`, `receiving:manage`, `savings:manage` and `records:write`. Its links and deposit addresses are fictional; Pix charge sends reach no recipient.

## Example checks

- Ask for balances: the fictional account has R$ 48.250,75, 0.12 BTC and 1,500 USDT.
- Ask for pending requests: R$ 3.250,00 to Fornecedor Demo Ltda awaits a person's approval.
- Read payment links and Pix charges: Pedido 1042 is R$ 450,00; Pedido 1043 is R$ 180,00.
- Create and deactivate a fictional R$ 25 Pix payment link, then create and cancel a fictional R$ 10 Pix charge, confirming details first.
- Read documents and payables, change a category, and verify the returned state.
- Request a R$ 10 Pix to maria.souza@example.invalid after preview and confirmation: the request stays pending and balances remain unchanged. Cancel it and read back its status.
- Ask to approve a payment: the agent must direct approval to Bipa Business.
- Quote a conversion or read savings, then confirm a simulated move with the issued key and matching amount. Verify the fictional balances and statement, and that missing or mismatched confirmation is refused.
- Connect the opening company and ask what remains: the response names each next step and the person who completes it in Bipa Business.

Validate every exposed tool, authentication refresh/reconnect, masked identifiers and refusal cases before attesting that testing is complete. These instructions are not a test result.

- Create a R$ 10 Pix charge for Cliente Demo with `contact_name`, without a payer tax ID. Read it back, then send it to cliente@example.invalid after confirmation. Creation alone sends nothing; reviewer delivery reaches no real recipient.

## Crypto scope for policy review

The connector reads crypto balances, statements and existing conversion orders. Payment links may receive BTC or USDT, and deposit-address requests return crypto deposit addresses. With explicit permissions and confirmation it also exposes conversions and target orders. Outgoing Pix and boleto requests await confirmation and approval in Bipa Business, while conversions and savings moves execute immediately. This full scope needs assessment under Anthropic’s [Software Directory Policy](https://support.claude.com/en/articles/13145358-anthropic-software-directory-policy). No exception or approval is asserted by this package.
