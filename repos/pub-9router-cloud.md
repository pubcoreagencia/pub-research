# Repo Evaluation: 9Router Cloud (AI Provider Management Server)

## Informações Básicas
- **Nome do Repo:** pub-9router-cloud
- **URL:** https://github.com/pubcoreagencia/pub-9router-cloud
- **Owner/Org:** pubcoreagencia
- **Licença:** Proprietário (private repo)
- **Linguagem principal:** JavaScript
- **Último commit:** 2026-09-20
- **Data da avaliação:** 2026-09-20
- **Avaliador:** Genildo3000 / Matheus Paes (PUB REC)

## O que é / Para que serve
**9Router Cloud** = Servidor dedicado do 9Router rodando 24/7 com painel oficial de métricas, histórico de uso e gerenciamento de provedores de IA. É a **camada de roteamento de modelos** da holding — gerencia quais provedores/modelos estão disponíveis, fallbacks, custos, quotas.

## Deploy
- **Render.com** — Web Service, Docker, porta 20128
- **Railway.app** — Deploy from GitHub, porta 20128 auto-detectada
- **Porta padrão:** 20128
- **Host:** 0.0.0.0

## Variáveis de Ambiente (Secrets)
| Variável | Descrição | Obrigatório |
|----------|-----------|-------------|
| `DB_SECRET` | Segredo criptográfico para descriptografar `encrypted-db.enc` (SQLite de credenciais) | ✅ Sim — falha com `MISSING_REQUIRED_SECRET` |
| `INITIAL_PASSWORD` | Senha do painel web/admin definida em runtime | ✅ Sim |
| `PORT` | `20128` (padrão 9router) | Opcional |
| `HOST` | `0.0.0.0` | Opcional |

## Relevância para Research
- **Provider abstraction layer** — Centraliza decisão de qual modelo/provedor usar
- **Fallback chains** — Roteamento automático se provedor falha
- **Cost tracking** — Métricas de uso, tokens, custos por provedor
- **Quota management** — Limites por provedor/modelo
- **Metrics dashboard** — Histórico de uso, performance, erros
- **Encrypted credentials DB** — SQLite criptografado para API keys

## Conexão com OpenClaw / PUB IA
- O agente Genildo3000 usa OpenRouter com 4 modelos free (configurado via `pin-openrouter-free-models`)
- 9Router Cloud poderia ser a **camada de roteamento** que o OpenClaw consulta
- Substitui/Complementa `modelPolicy.allow` estático com roteamento dinâmico

## Prós
- **Serverless-ready** — Deploy 1-click Render/Railway
- **Segurança** — Secrets apenas em runtime, DB criptografado
- **Painel web** — Métricas, histórico, gerenciamento visual
- **Porta padrão 20128** — Convenção 9router
- **Docker** — Portável, reprodutível

## Contras / Riscos
- Private repo
- Single point of failure se só 1 instância
- Precisa monitorar saúde (health checks)
- SQLite pode ser bottleneck em alta concorrência

## Decisão
- [x] **Adotar** — Roteamento de modelos centralizado
- [x] **Institucionalizar** — Patterns → pub-research
- [ ] **Open source** — Core router logic poderia ser lib

## Ações de Integração
- [ ] Integrar com OpenClaw (model provider routing)
- [ ] Integrar com PUB IA (model registry + fallback)
- [ ] Documentar API do 9Router → `tools/9router-api.md`
- [ ] Benchmark: 9Router vs OpenRouter vs custom routing
- [ ] Migrar DB SQLite → PostgreSQL (Supabase) para escala
- [ ] Health checks + alerting (Uptime Kuma, etc.)

## Links
- Repo: https://github.com/pubcoreagencia/pub-9router-cloud (private)
- 9Router: https://9router.com (se existir)
- Render: https://render.com
- Railway: https://railway.app
