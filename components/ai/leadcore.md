# Repo Evaluation: LeadCore (Unified B2B Contacts & CRM Intelligence)

## Informações Básicas
- **Nome do Repo:** leadcore
- **URL:** https://github.com/pubcoreagencia/leadcore
- **Owner/Org:** pubcoreagencia
- **Licença:** Proprietário (private repo)
- **Último commit:** 2026-09-19
- **Data da avaliação:** 2026-09-20
- **Avaliador:** Genildo3000 / Matheus Paes (PUB REC)

## O que é / Para que serve
**LeadCore** = Core de inteligência e base unificada de contatos e CRM B2B. Centraliza dados de leads, enriquecimento, scoring, segmentação e histórico de interações para toda a holding.

## Documentação Identificada
- `MASTER_CONTEXT.md` — Governança e arquitetura
- `PUB_GIT_CLOSURE_RULE.md` — Regra de fechamento Git

## Relevância para Research
- **Unified contact database** — Single source of truth para contatos B2B
- **Enrichment pipeline** — Dados externos → perfil completo (empresa, cargo, tecnologias, sinais)
- **Scoring/segmentation** — Lead scoring unificado, segmentação declarativa
- **CRM integration** — HubSpot, Pipedrive, Close, etc. via adapters
- **Cross-product** — Alimenta PUB Machine (prospecting), PUB Ecom (clientes), PUB Media (audiências)
- **LGPD compliance** — Consentimento, opt-out, data retention

## Conexão com PUB Machine
- PUB Machine `src/prospecting/lead-intent-signals.service.ts` → ingere sinais multi-canal
- LeadCore = camada de persistência e inteligência por trás
- `lead-scoring.service.ts`, `lead-prioritization-orchestrator.service.ts` consomem LeadCore

## Prós
- Centraliza ativo mais valioso: contatos/leads
- Elimina silos de dados entre produtos
- Base para automação de vendas/marketing

## Contras / Riscos
- Private repo
- Pouca documentação visível
- CRM sync = complexidade contínua (APIs mudam, rate limits)
- Data quality = desafio constante (dedup, merge, stale data)

## Decisão
- [x] **Adotar** — Core de dados B2B da holding
- [x] **Institucionalizar** — Patterns → pub-research
- [ ] **Open source** — Contact enrichment adapters, scoring logic

## Ações de Integração
- [ ] Documentar schema de contato unificado → `tools/unified-contact-schema.md`
- [ ] Documentar enrichment pipeline → `workflows/lead-enrichment-pipeline.md`
- [ ] Benchmark: LeadCore vs Apollo vs Clearbit vs ZoomInfo vs open source (Crmble, etc.)
- [ ] Integrar com PUB Machine prospecting layer
- [ ] LGPD compliance patterns → `docs/governance/lgpd-compliance.md`

## Links
- Repo: https://github.com/pubcoreagencia/leadcore (private)
- PUB Machine: https://github.com/pubcoreagencia/pub-machine
