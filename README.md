# Bipa

See your Bipa finances in Claude: BRL, BTC and USDT balances, account details, Pix and deposit keys, Pix transfer limits, portfolio summaries and market prices. The connection is read-only. It cannot request payments, send Pix, generate charges or place trades.

## What the plugin contains

- **Connector:** the remote MCP server `https://mcp.bipa.app/readonly/mcp` (Streamable HTTP), declared in `.mcp.json`. Claude connects to it with OAuth; you sign in with Bipa and choose which read permissions to grant: `financial:read` (balances, limits, portfolio, prices) and `account:read` (account details, Pix and deposit keys).
- **Skill:** `bipa-readonly`, in Portuguese, which tells Claude which tool answers each question, how to present results (including Bipa's interactive cards where the app supports them) and what this connection cannot do.

The plugin runs no local code, hooks or scripts, and sends nothing anywhere other than the Bipa connector above. Claude only calls the connector when a question needs Bipa data.

## Tools

Nine data tools, each with a matching `_widget` tool that shows the same result as an interactive card: `bipa_balance`, `bipa_account`, `bipa_pix_keys`, `bipa_deposit`, `bipa_limits`, `bipa_portfolio`, `bipa_tickers`, `bipa_btc_prices` and `bipa_usdt_prices`. Account document fields (CPF/CNPJ) are masked; Pix keys are returned exactly as registered, including document-based keys. Transaction history, statements, DDA bills and other banks are not available in this connection.

## Try it without an account

A public demo with fictional data needs no sign-in: `https://mcp.bipa.app/demo/mcp`. Instructions: <https://mcp.bipa.app/demo>.

## Privacy and support

- Privacy policy: <https://suporte.bipa.app/hc/pt-br/articles/36305196684315>
- Terms of use: <https://suporte.bipa.app/hc/pt-br/articles/55072595716507-Termos-de-uso-aplicativo-Bipa>
- Support: <https://suporte.bipa.app/hc/pt-br>
- Documentation: <https://agents.bipa.app/docs/claude-readonly>

---

## Em português

Consulte suas finanças da Bipa no Claude: saldos em reais, Bitcoin e USDT, dados da conta, chaves Pix e de depósito, limites de Pix, resumo da carteira e cotações. A conexão é somente leitura: não solicita pagamentos, não envia Pix, não gera cobranças e não compra nem vende ativos.

O plugin contém o conector MCP remoto `https://mcp.bipa.app/readonly/mcp`, autenticado por OAuth com as permissões de leitura que você escolher, e a skill `bipa-readonly`. Ele não executa código local, hooks nem scripts e não envia dados a nenhum destino além desse conector. Os campos de CPF/CNPJ dos dados da conta aparecem mascarados; as chaves Pix aparecem completas, como cadastradas.

Para testar sem conta, use a demonstração com dados fictícios em `https://mcp.bipa.app/demo/mcp`.

## License

MIT. See [LICENSE](LICENSE).
