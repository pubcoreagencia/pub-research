# Repo Evaluation: PUB Machine SaaS (Multi-tenant SaaS Version)

## Informações Básicas
- **Nome do Repo:** pub-machine-saas
- **URL:** https://github.com/pubcoreagencia/pub-machine-saas
- **Owner/Org:** pubcoreagencia
- **Licença:** Proprietário (private repo)
- **Linguagem principal:** TypeScript
- **Último commit:** 2026-09-19
- **Data da avaliação:** 2026-09-20
- **Avaliador:** Genildo3000 / Matheus Paes (PUB REC)

## O que é / Para que serve
**PUB Machine SaaS** = Versão multi-tenant SaaS da PUB Machine para clientes externos. Transforma o motor de prospecção/geração de negócios em produto vendível (B2B SaaS).

## Documentação Identificada
- `MASTER_CONTEXT.md` — Governança e arquitetura
- `AUTONOMOUS_CYCLE.md` — Ciclo autônomo
- `PUB_GIT_CLOSURE_RULE.md` — Regra de fechamento Git

## Relevância para Research
- **Multi-tenancy patterns** — Isolamento de dados, configuração por tenant
- **Billing/subscription** — Stripe, planos, quotas, usage-based pricing
- **Onboarding flow** — Self-service signup, configuração inicial
- **White-label** — Customização de marca, domínio, emails
- **Admin panel** — Gestão de tenants, métricas, saúde
- **API para clientes** — Public API para integração

## Prós
- Monetização direta do core engine
- Reutiliza toda arquitetura v1/v2
- SaaS metrics built-in

## Contras / Riscos
- Private repo
- Multi-tenancy = complexidade significativa (isolation, noisy neighbor, migrations)
- Suporte a clientes externos = SLA, support, onboarding
- Compliance (LGPD, SOC2?) para dados de terceiros

## Decisão
- [x] **Adotar** — Produto SaaS da holding
- [x] **Institucionalizar** — Multi-tenancy patterns → pub-research
- [ ] **Open source** — Tenant isolation patterns

## Ações de Integração
- [ ] Documentar multi-tenancy architecture → `workflows/multi-tenancy-patterns.md`
- [ ] Billing integration (Stripe) → `workflows/saas-billing-stripe.md`
- [ ] White-label config → `tools/white-label-config.md`
- [ ] Tenant onboarding flow → `workflows/tenant-onboarding.md`

## Links
- Repo: https://github.com/pubcoreagencia/pub-machine-saas (private)
- v1: https://github.com/pubcoreagencia/pub-machine
- v2: https://github.com/pubcoreagencia/pub-machine-2
