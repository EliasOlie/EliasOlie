## Hi, I'm Elias 👋

**Senior Software Engineer · AI agents (MCP, RAG) · Legacy ERP integration · Payments**
TypeScript · Python · Go · Rust — Pernambuco, Brazil 🇧🇷 · open to remote work (US/EU time zones)

I build the parts that let AI agents work safely inside real businesses: identity and permissions, read-only gateways over legacy databases, idempotent queues, and an audit trail for everything they do.

### What I'm doing now

First dedicated engineer at a retail & wholesale food distribution group in northeast Brazil, reporting to the board. In 5 months I replaced a low-code stack with **12 in-house components running in production**:

- **Central identity service**: refresh-token reuse detection, Argon2, rate limiting. Each consuming service decides authorization itself, never the identity layer.
- **Read-only gateway over a legacy Oracle ERP**, exposed as REST + MCP, with SQL validated at the AST level (sqlglot) and pagination enforced on every query.
- **Pix (instant payments) at every checkout**: a DLL proxy in pure C (WinINet, built with Zig) attached to the POS, plus a payments microservice with mTLS, webhooks and idempotent refunds.
- **Knowledge base for agents** (MCP + pgvector), where every fact records its source, when it was valid and when to re-check it, with an append-only audit log.
- **WhatsApp operations assistant on Claude**: tool use with a double permission check against prompt injection, and proactive monitors.
- **Self-hosted platform**: Coolify, Caddy, CI/CD with rollback by tag, Prometheus/Loki/Grafana, 450+ automated tests.

### Open-source versions of that work

| Project | What it shows |
|---|---|
| [**readonly-sql-mcp**](https://github.com/EliasOlie/readonly-sql-mcp) | Give agents SQL access without a way to break anything: AST guard, forced pagination, scoped auth, hash-chained audit log. Python, REST + MCP, CI. |
| [**agyh**](https://github.com/EliasOlie/agyh) | One searchable index of every coding-agent session (Antigravity, Claude Code, Codex): projects, resume, TUI, and approvals of risky commands from Telegram/WhatsApp, where the first answer wins. Go, SQLite FTS5. |
| [**edge-webhook-relay**](https://github.com/EliasOlie/edge-webhook-relay) | Verify, de-duplicate and reliably deliver webhooks (WhatsApp Cloud API, Stripe, GitHub) at the edge: Durable Objects, Queues + DLQ, D1 audit trail, replay API. TypeScript, Cloudflare Workers. |
| [**mcp-platform-go**](https://github.com/EliasOlie/mcp-platform-go) | Ed25519 identity service + a unified MCP gateway where agents only *see* the tools their scopes allow + hybrid RAG (pgvector HNSW + full-text search + RRF). Go. |
| [**vpsql-control-plane**](https://github.com/EliasOlie/vpsql-control-plane) | Single-node Postgres control plane: multi-tenant provisioning, least-privilege roles, PgBouncer, Go CLI, Next.js dashboard, OpenAI-compatible AI gateway. |
| [**cozy-curses**](https://github.com/EliasOlie/cozy-curses) · [**eleicoes-ipst**](https://github.com/EliasOlie/eleicoes-ipst) | For fun and for my community: a Rust + Bevy game, and an election app for a local church. |

### Principles I build by

- **Agents should never see a tool they can't use**, so a prompt injection has nothing to call.
- **Identity is central, authorization is local.**
- **Every write is idempotent, and every agent action leaves a trace.**
- **Read-only first** when touching systems the business can't afford to lose.

### Stack

`TypeScript` `Bun` `Hono` `Next.js` · `Python` `FastAPI` · `Go` `Fiber` `Bubble Tea` · `Rust` `Bevy` · `C` `Zig` · `PostgreSQL` `pgvector` `SQLite FTS5` `Redis` `BullMQ` `Oracle` · `MCP` `Claude API` `WhatsApp Cloud API` · `Docker` `Coolify` `Caddy` `Cloudflare Workers` `Durable Objects` `Queues` `D1` `Prometheus` `Loki` `Grafana`

### Contact

[LinkedIn](https://linkedin.com/in/eliasolie) · contato.eliasolie@gmail.com

<details>
<summary>🇧🇷 Em português</summary>

Engenheiro de software sênior em Pernambuco. Construo a infraestrutura que permite que agentes de IA trabalhem com segurança dentro de empresas reais: identidade e permissões centralizadas, gateways somente leitura sobre ERPs legados (Oracle), filas idempotentes, Pix no PDV e assistentes no WhatsApp com Claude. Hoje sou o primeiro engenheiro dedicado de um grupo de varejo e atacado no interior do Nordeste. Aberto a vagas remotas no Brasil e no exterior.

</details>
