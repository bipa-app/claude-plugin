# Bipa Business

Ask Claude about your company's Bipa Business account. Read balances in reais, Bitcoin and USDT, statement entries and monthly statements, payment requests waiting for approval, payment links, Pix charges, received documents, payables, savings and Pix limits.

Create and stop payment links, create, send and cancel Pix charges, request deposit addresses, and organize documents, categories and payables. Before the company's account opens, follow its status and the links where each member completes the next step in Bipa Business.

## Try asking

- “Quanto a empresa tem em caixa?”
- “Quais pedidos de pagamento estão esperando aprovação?”
- “Solicite um Pix de R$ 10 para maria.souza@example.invalid.”
- “Crie um link de pagamento de R$ 450 por Pix para o pedido 1042, para um pagamento.”
- “Quais contas a pagar estão em aberto?”
- “O que falta para abrir a conta da empresa e quem precisa fazer cada etapa?”

## Connection and permissions

A company member signs in with Bipa OAuth, chooses the account and grants the permissions needed: `financial:read`, `account:read`, `payments:request`, `conversions:execute`, `receiving:manage`, `savings:manage` and/or `records:write`. A connection for an account that is still opening exposes only its opening status and next-step links. Identity capture, selfies, terms and signatures remain in Bipa Business.

The connection is limited by the member's current permissions. It can be revoked in Bipa Business under Settings, Agents. Reconnect when the host asks; never paste passwords, authentication codes, API keys or tokens into a conversation.

The connector can preview, create, cancel and follow payment requests. Member confirmation and the company’s approval policy remain in Bipa Business; the agent cannot approve or directly execute those payments. Conversions, accepted target orders and savings moves execute immediately with the required permissions and explicit confirmation. A Pix charge can store an optional customer name without collecting CPF; email and phone delivery are separate confirmed send operations. Its payment links, Pix charges and deposit addresses receive money; links that convert on receipt require conversions:execute. Recording a payable as paid records an external payment; it does not pay the bill.

## Data sent to Bipa

The plugin connects only to `https://mcp.bipa.app/business/connector/mcp`, using the host's OAuth integration. Bipa receives the authorization token and tool arguments needed for the requested operation, such as dates, an asset, a payment-link title, an amount, a document identifier, a category, or a Pix charge delivery address. It does not receive the conversation as a whole. Results contain the requested company financial information. Structured personal identifiers and Pix delivery contacts are masked; company CNPJ values remain visible.

The package contains a remote MCP declaration and the `bipa-business` skill. It has no local executable code, hooks, scripts, dependencies or API keys.

## Reviewer access

Reviewers use the private fictional-company sign-in described in [REVIEWING.md](REVIEWING.md). No credentials are included in this repository. Fictional reviewer operations reach no real account, send no message and move no real money. Provider testing and directory approval must be verified separately; package validation does not establish either.

## Links

- [Documentation](https://agents.bipa.app/docs/business)
- [Privacy policy](https://suporte.bipa.app/hc/pt-br/articles/36305196684315)
- [Terms of use](https://suporte.bipa.app/hc/pt-br/articles/55072595716507-Termos-de-uso-aplicativo-Bipa)
- [Support](https://suporte.bipa.app/hc/pt-br)

## License

MIT. See [LICENSE](LICENSE).
