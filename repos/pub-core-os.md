# Repo Evaluation: PUB Core OS (Institutional Operating System)

## Informações Básicas
- **Nome do Repo:** pub-core-os
- **URL:** https://github.com/pubcoreagencia/pub-core-os
- **Owner/Org:** pubcoreagencia
- **Licença:** Proprietário (private repo)
- **Último commit:** 2026-09-19
- **Data da avaliação:** 2026-09-20
- **Avaliador:** Genildo3000 / Matheus Paes (PUB REC)

## O que é / Para que serve
**PUB Core OS** = Sistema operacional institucional e unificador de governança da holding PUB Core Holding. É a camada de **governança, padrões, protocolos e contratos** que une todos os produtos/repos da holding.

## Documentação Identificada
- `MASTER_CONTEXT.md` — Governança e arquitetura
- `PUB_GIT_CLOSURE_RULE.md` — Regra mandatória de fechamento de estágios Git

## Relevância para Research
- **Governança canônica** — Regras que todos os repos PUB devem seguir
- **Git closure rule** — Protocolo obrigatório para commits/PRs/merges
- **Padrões arquiteturais** — Convenções de camadas, naming, estrutura
- **Contratos entre produtos** — Como Machine, Neural, IA, Records, Ecom se comunicam
- **Institutional memory** — Single source of truth para decisões transversais

## Princípios (inferidos dos outros repos)
1. **Canonical naming** — `PUB SERVER = PUB MACHINE` (não existe PUB Server)
2. **Git closure** — Todo estágio deve fechar com commit + docs + testes
3. **Layer separation** — Signal → Audience → Intent → Lead → Conversion (Machine)
4. **Neural/PDL/ACP/Fabric separation** — Cognitive layers (Neural audit)
5. **Autonomous cycle** — Todo produto tem ciclo autônomo documentado
6. **Master context** — Cada repo tem MASTER_CONTEXT.md como entry point

## Decisão
- [x] **Adotar** — Governança central da holding
- [x] **Institucionalizar** — Extrair regras → pub-research/docs/governance/
- [ ] **Open source** — Governance framework poderia ser template para outras orgs

## Ações de Integração
- [ ] Extrair `PUB_GIT_CLOSURE_RULE.md` → `docs/governance/git-closure-rule.md`
- [ ] Documentar naming conventions → `docs/governance/naming-conventions.md`
- [ ] Documentar layer separation → `docs/governance/layer-separation.md`
- [ ] Criar template `MASTER_CONTEXT.md` para novos repos
- [ ] Auditar compliance dos 50 repos contra Core OS rules

## Links
- Repo: https://github.com/pubcoreagencia/pub-core-os (private)
