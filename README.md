# Bipa

Ask Claude about your money at Bipa. See your balance in reais, Bitcoin and USDT, how your portfolio did today, this month or this year, Bitcoin and USDT prices on Bipa with charts, your Pix limits, and your Pix and deposit keys when you need to share them. Balances, portfolio results and prices show up as Bipa cards right in the chat.

## Try asking

- "What's my Bipa balance?"
- "How did my Bitcoin portfolio do this month?"
- "How is Bitcoin trading on Bipa today?"
- "What are my Pix limits?"

## Your money stays put

Claude can only look at your data. It can't send Pix, pay bills or buy and sell crypto. When you connect, you sign in with Bipa and choose what Claude can see: your financial data, your account details, or both. Your CPF or CNPJ is masked in your account details. Transaction history and statements aren't included.

You need a Bipa account to connect. To look around first, a demo with a fictional account needs no sign-in: <https://mcp.bipa.app/demo>.

## What's inside

- **A connection to Bipa's read-only server**, `https://mcp.bipa.app/readonly/mcp`, declared in `.mcp.json`. You sign in with Bipa (OAuth) and grant `financial:read` (balances, limits, portfolio, prices), `account:read` (account details, Pix and deposit keys) or both.
- **The `bipa-readonly` skill**, in Portuguese, which tells Claude which Bipa tool answers each question and how to present the result.

The plugin runs no local code, hooks or scripts. It sends nothing anywhere except that Bipa server, and only when you ask about your Bipa account.

## Privacy and support

- Privacy policy: <https://suporte.bipa.app/hc/pt-br/articles/36305196684315>
- Terms of use: <https://suporte.bipa.app/hc/pt-br/articles/55072595716507-Termos-de-uso-aplicativo-Bipa>
- Help center: <https://suporte.bipa.app/hc/pt-br>
- Setup guide: <https://agents.bipa.app/docs/claude-readonly>

---

## Em português

Pergunte ao Claude sobre o seu dinheiro na Bipa. Veja seu saldo em reais, Bitcoin e USDT, o desempenho da sua carteira hoje, no mês ou no ano, as cotações de Bitcoin e USDT na Bipa com gráficos, seus limites de Pix e suas chaves Pix e de depósito quando precisar compartilhá-las.

Experimente perguntar:

- "Qual é o meu saldo na Bipa?"
- "Como foi minha carteira de Bitcoin neste mês?"
- "Quanto está o Bitcoin na Bipa hoje?"
- "Quais são meus limites de Pix?"

O Claude só consulta os seus dados: não envia Pix, não paga contas e não compra nem vende criptomoedas. Ao conectar, você entra com a sua conta Bipa e escolhe o que ele pode ver: dados financeiros, dados da conta ou ambos. O CPF ou CNPJ aparece mascarado nos dados da conta. Extratos e histórico de transações não estão incluídos.

O plugin conecta apenas ao servidor somente leitura da Bipa (`https://mcp.bipa.app/readonly/mcp`) e não executa código local, hooks nem scripts.

## License

MIT. See [LICENSE](LICENSE).
