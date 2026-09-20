# Repo Evaluation: PUB Ecom (E-Commerce Monorepo)

## Informações Básicas
- **Nome do Repo:** pub-ecom
- **URL:** https://github.com/pubcoreagencia/pub-ecom
- **Owner/Org:** pubcoreagencia
- **Licença:** Proprietário (private repo)
- **Linguagem principal:** TypeScript
- **Último commit:** 2026-09-19
- **Data da avaliação:** 2026-09-20
- **Avaliador:** Genildo3000 / Matheus Paes (PUB REC)

## O que é / Para que serve
**PUB Ecom** = Monorepo de e-commerce unificado da holding: **Core** (backend), **Hub App** (admin/dashboard), **Catalog Worker** (ingestão/sync catálogo), **Landing Page**. Unifica múltiplos repos arquivados (pub-ecom-catalog-worker, pubecomhub, pub-ecom-landing).

## Estrutura (Monorepo)
```
pub-ecom/
├── apps/
│   ├── landing/           # Landing page (arquivado aqui)
│   ├── catalog-worker/    # Worker catálogo (arquivado aqui)
│   └── hub/               # Admin app + actors
│       └── pub-actors/    # Actors para importação (browser, URL)
├── packages/              # Shared packages (inferred)
├── docs/
│   └── AI_CONTINUITY_PROTOCOL.md
├── MASTER_CONTEXT.md
├── ARCHITECTURE_MAP.md
├── DOMAIN_MAP.md
├── BUSINESS_MODEL.md
├── DATABASE_CONTRACT.md
├── DEPLOYMENT.md
├── SECURITY_MODEL.md
├── COLLABORATION_PROTOCOL.md
├── DEVELOPMENT_RULES.md
├── CHANGE_CONTROL.md
├── PHASE_STATUS.md
└── AGENT_START.md
```

## Actors de Importação (`apps/hub/pub-actors/`)
- `PUB_URL_IMPORT_ENGINE_REPORT.md` — Engine importação via URL
- `PUB_BROWSER_IMPORTER_E2E_REPORT.md` — Importador via browser automation
- `PUB_BROWSER_IMPORT_PUBEcom_E2E_REPORT.md` — E2E browser import
- `PUB_ECOM_URL_IMPORT_INTEGRATION_REPORT.md` — Integração import URL
- `PUB_PROVIDER_CERTIFICATION.md` — Certificação de provedores

## Documentação-chave
- `ARCHITECTURE_MAP.md` — Mapa arquitetural
- `DOMAIN_MAP.md` — Domain-driven design mapping
- `BUSINESS_MODEL.md` — Modelo de negócio
- `DATABASE_CONTRACT.md` — Contratos de banco
- `AI_CONTINUITY_PROTOCOL.md` — Protocolo continuidade IA

## Relevância para Research
- **Monorepo patterns** — Turborepo/Nx? Shared packages, build orchestration
- **Browser import actors** — Automação de importação de catálogo via browser
- **Catalog sync worker** — Ingestão/sync contínuo de produtos
- **Admin dashboard (Hub App)** — Interface de gestão
- **Multi-tenant?** — SaaS para clientes externos?

## Prós
- Unificação de 4 repos arquivados → menos fragmentação
- Actors de importação (URL + browser) = flexibilidade
- Documentação extensa (architecture, domain, database, security)
- TypeScript strict

## Contras / Riscos
- Private repo
- Monorepo complexity (build times, dependencies)
- Catalog worker = critical path, precisa alta disponibilidade
- Browser automation frágil (sites mudam)

## Decisão
- [x] **Adotar** — Core e-commerce da holding
- [x] **Institucionalizar** — Patterns → pub-research
- [ ] **Open source** — Import actors, catalog sync patterns

## Ações de Integração
- [ ] Extrair `ARCHITECTURE_MAP.md` + `DOMAIN_MAP.md` → `workflows/ecom-monorepo-architecture.md`
- [ ] Documentar browser import actors → `tools/browser-import-actors.md`
- [ ] Benchmark: pub-ecom vs Medusa vs Saleor vs Vendure (open source ecom)
- [ ] Catalog worker patterns → `workflows/catalog-sync-worker.md`
- [ ] AI_CONTINUITY_PROTOCOL → `workflows/ai-continuity-protocol.md` (com PUB Records)

## Links
- Repo: https://github.com/pubcoreagencia/pub-ecom (private)
- Archived: pub-ecom-catalog-worker, pubecomhub, pub-ecom-landing
