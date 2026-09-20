# Repo Evaluation: Automated-Agentic-AI-Web-Agency

## Informações Básicas
- **Nome do Repo:** Automated-Agentic-AI-Web-Agency
- **URL:** https://github.com/JackInSightsV2/Automated-Agentic-AI-Web-Agency
- **Owner/Org:** JackInSightsV2
- **Licença:** MIT
- **Stars/Forks/Watchers:** ~1.2k stars / ~180 forks (set/2026)
- **Último commit:** Ativo (set/2026)
- **Linguagem principal:** TypeScript (Bun), alguns Python
- **Data da avaliação:** 2026-09-19
- **Avaliador:** Genildo3000 / Matheus Paes (PUB REC)

## O que é / Para que serve
Agência web totalmente automatizada que descobre negócios locais sem site via Google Places API, gera copy customizada, constrói site profissional (Vite), faz deploy no Vercel, envia email, liga via Bland.ai, fecha venda no Stripe — pipeline completo end-to-end com 15 agentes especializados, Human-in-the-Loop (HITL) no Telegram, dashboard ao vivo.

## Por que é relevante para a PUB
- Referência arquitetural para automação de pipelines multi-agente
- Padrão de orquestração: Queue System + Cron Jobs + HITL gates
- Integração real de serviços: Supabase, Vercel, Bland.ai, Stripe, Twilio, OpenAI
- Uso de Claude Code como subprocess para geração de código (builder agent)
- Dashboard Vite com "live office view" — conceito visual para monitoramento de agentes
- Whitelabel completo via env vars — pronto para adaptação

## Análise Técnica
| Aspecto | Avaliação (1-5) | Observações |
|---------|-----------------|-------------|
| Qualidade do código | 4 | TypeScript strict, modular, bem organizado em packages |
| Documentação | 4 | SETUP.md, ARCHITECTURE.md, AGENTS.md, DATABASE.md completos |
| Testes | 2 | Poucos testes automatizados visíveis |
| Manutenção ativa | 4 | Commits recentes, issues respondidas |
| Comunidade | 3 | Crescendo, discord ativo |
| Licença compatível | 5 | MIT — total liberdade |
| Facilidade de integração | 3 | Requer muitas API keys, setup não-trivial |

## Dependências Principais
- **Runtime:** Bun (não Node.js)
- **API:** Hono
- **Database:** Supabase (PostgreSQL)
- **Deploy:** Vercel
- **Calls:** Bland.ai
- **Email:** Resend
- **SMS/WhatsApp:** Twilio
- **Payments:** Stripe
- **Lead Discovery:** Google Places API
- **Hero Images:** OpenAI Images API (opcional)
- **Site Builder:** Claude Code (subprocess)
- **Queue/Cron:** Custom implementation
- **HITL:** Telegram Bot
- **Dashboard:** Vite + Pixel Agent Desk (MIT)

## Testes Realizados
| Cenário | Comando | Resultado |
|---------|---------|-----------|
| Clone | `git clone` | ✅ OK |
| Setup script | `./setup.sh` | ⚠️ Requer Bun install + API keys |
| Build API | `bun run build` (packages/api) | Não testado (sem keys) |
| Build Dashboard | `bun run build` (packages/dashboard) | Não testado |
| Typecheck | `bun run typecheck` | Não testado |

## Prós
- Arquitetura multi-agente bem pensada e documentada
- Pipeline completo real (descoberta → venda → entrega)
- HITL gates para aprovação humana em pontos críticos
- Dashboard visual inovador ("office view")
- Whitelabel nativo — fácil adaptar marca/nome
- MIT license — pode fork, modificar, comercializar
- Usa Claude Code como subprocess (interessante para PUB que usa OpenClaw)
- Queue system próprio com pause/resume/retry

## Contras / Riscos
- **Requer Bun** — não roda em Node padrão (pode ser blocker em alguns ambientes)
- **Muitas dependências externas pagas** (Bland.ai, Stripe, Twilio, Supabase, Vercel, OpenAI, Resend, Google Places) — custo operacional alto
- **Setup complexo** — 15+ API keys necessárias para rodar completo
- **Poucos testes automatizados** — risco de regressão
- **Claude Code como subprocess** — requer assinatura Anthropic/acesso Claude Code
- **Single-tenant design** — adaptação multi-tenant requer trabalho

## Decisão
- [x] **Referência** — Usar como inspiração/estudo arquitetural
- [ ] **Adotar** — Fork/integrar ao hub (muito pesado para uso direto)
- [ ] **Monitorar** — Acompanhar updates para ideas
- [ ] **Descartar** — Não atende

## Ações de Integração (como referência)
- [x] Documentar arquitetura no pub-research
- [ ] Extrair padrões: queue system, HITL gates, agent specialization
- [ ] Avaliar dashboard "office view" para monitoramento OpenClaw
- [ ] Estudar uso de Claude Code subprocess vs OpenClaw subagents
- [ ] Considerar whitelabel pattern para skills PUB

## Links
- Repo original: https://github.com/JackInSightsV2/Automated-Agentic-AI-Web-Agency
- SETUP.md: https://github.com/JackInSightsV2/Automated-Agentic-AI-Web-Agency/blob/main/docs/SETUP.md
- ARCHITECTURE.md: https://github.com/JackInSightsV2/Automated-Agentic-AI-Web-Agency/blob/main/docs/ARCHITECTURE.md
- AGENTS.md: https://github.com/JackInSightsV2/Automated-Agentic-AI-Web-Agency/blob/main/docs/AGENTS.md
- DATABASE.md: https://github.com/JackInSightsV2/Automated-Agentic-AI-Web-Agency/blob/main/docs/DATABASE.md
- LICENSE: MIT
