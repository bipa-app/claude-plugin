# Bipa

Ask Claude about your money at Bipa. See balances, transactions, portfolio results, prices, Pix keys and limits. Generate Pix codes to receive money and request Pix, boleto and DDA payments. When supported, Bipa cards show the results in the chat.

## Try asking

- "What's my Bipa balance and my last five transactions?"
- "How did my Bitcoin portfolio do this month?"
- "Help me create a Pix code to receive R$ 100."
- "Help me request a Pix payment and follow its approval."

## You choose the permissions

The connection uses Bipa OAuth at `https://mcp.bipa.app/mcp`. Choose separate permissions for financial data (`financial:read`), account details (`account:read`), payment requests (`payments:request`) and previously authorized trusted-contact Pix (`payments:execute_trusted`). Tools depend on the permissions you grant.

Ordinary Pix, boleto and DDA requests wait for your approval in the Bipa app. Claude cannot approve them for you. A Pix to a previously authorized trusted contact can execute immediately within the existing limits, after your explicit confirmation in chat. A pending or approved request is not proof of payment completion; check its final status.

Account documents are masked. The hosted connector rejects CPF Pix-key inputs; use an email, phone, CNPJ, random key, Bipa tag or existing recipient ID. Registered Pix keys remain complete when read. Do not share passwords, verification codes or identity documents in chat. The personal connector does not buy, sell or convert assets, place investment orders or move savings.

Existing connections to `/readonly/mcp` keep their read-only permissions. Connecting to the full endpoint requires a new authorization. If you do not have a Bipa account, you can open one from Bipa's sign-in page.

## What's inside

- The full Bipa MCP connection in `.mcp.json`.
- The Portuguese `bipa` skill, which explains tool selection, confirmation, payment status, privacy and widgets.

The plugin runs no local code, hooks or scripts. It communicates with the declared Bipa MCP server and its OAuth services.

## Privacy and support

- [Privacy policy](https://suporte.bipa.app/hc/pt-br/articles/36305196684315)
- [Terms of use](https://suporte.bipa.app/hc/pt-br/articles/55072595716507-Termos-de-uso-aplicativo-Bipa)
- [Help center](https://suporte.bipa.app/hc/pt-br)
- [Setup guide](https://agents.bipa.app/docs/claude)

## Em português

Consulte sua conta Bipa no Claude: saldos, extrato, carteira, cotações, chaves Pix e limites. Gere códigos Pix para receber e solicite Pix, boletos e pagamentos DDA. Pedidos comuns aguardam sua aprovação no app Bipa; o Claude não aprova por você. Pix para contatos de confiança previamente autorizados pode executar imediatamente dentro dos limites existentes, após sua confirmação explícita na conversa.

Você escolhe permissões separadas para consultas, pedidos de pagamento e execução para contatos de confiança. Os documentos da conta ficam mascarados e CPF não é aceito como chave de entrada no chat. As chaves Pix consultadas permanecem completas. O conector pessoal não compra, vende ou converte ativos, não cria ordens de investimento nem movimenta o cofrinho.

## Reviewer access

Keep the installed `/mcp` endpoint and OAuth enabled. First sign in at the [private reviewer page](https://mcp.bipa.app/oauth/reviewer) with the supplied credentials, then connect in the same browser within ten minutes and choose **Connect fictional account**. No mobile app or verification code is needed. Normal customer authorization stays separate. See [REVIEWING.md](REVIEWING.md) for the full fictional test flow and policy disclosure. Repository version is not proof of deployment, directory approval or publication.

## License

MIT. See [LICENSE](LICENSE).
