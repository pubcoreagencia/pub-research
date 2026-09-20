# Repo Evaluation: PUB Machine (Operational Intelligence Engine)

## Informações Básicas
- **Nome do Repo:** pub-machine
- **URL:** https://github.com/pubcoreagencia/pub-machine
- **Owner/Org:** pubcoreagencia
- **Licença:** Proprietário (private repo)
- **Linguagem principal:** TypeScript
- **Último commit:** 2026-09-19
- **Data da avaliação:** 2026-09-20
- **Avaliador:** Genildo3000 / Matheus Paes (PUB REC)

## O que é / Para que serve
**PUB Machine** = Motor de inteligência operacional, prospecção e geração de negócios da holding PUB. Unifica captura de sinais físicos e digitais, enriquecimento de audiência, qualificação de leads, previsão preditiva de conversão e automação de fechamento comercial em **Closed Loop**.

**Regra Canônica:** `PUB SERVER = PUB MACHINE` — não existe "PUB Server" separado.

## Pipeline de Causalidade Canônico
```
RAW SIGNAL → AUDIENCE PROFILE → INTENT BRIDGE → LEAD INTENT → LEAD SCORING → CONVERSION
```

**Regra de Ouro:** `RAW SIGNAL ≠ AUDIENCE PROFILE ≠ INTENT ≠ LEAD`

## Estrutura do Repositório (Camadas Implementadas)

| Camada | Status | Path | Testes |
|--------|--------|------|--------|
| **Camada 1: Signal/Capture Intelligence V0** | ✅ IMPLEMENTADO | `src/signal/` | 11 testes passando |
| **Camada 2: Audience Intelligence & Intent Bridge** | ✅ IMPLEMENTADO | `src/audience/` | 6 testes passando |
| **Integração: Physical → Lead Intent** | ✅ IMPLEMENTADO | `src/audience/physical-intent.adapter.ts` | 8 testes passando |
| **Camada 3: Sinais Multi-Canal & Scoring de Lead** | ✅ IMPLEMENTADO | `src/prospecting/` | - |
| **Camada 4: Conversão, Velocity & Forecasting** | ✅ IMPLEMENTADO | `src/prospecting/` | - |
| **Camada 5: Execução Autônoma (PDL)** | ✅ ESTRUTURAL | `src/autonomous/` | - |
| **Camada 6: Closed Loop Feedback** | 🎯 ARQUITETURA-ALVO | Em andamento | - |

## Componentes Principais

### Signal Layer (`src/signal/`)
- `geo-math.ts` — Cálculos geodésicos puros (Haversine, Ray Casting)
- `geofence-engine.ts` — Engine determinística de transições de geofence
- `presence-intelligence.service.ts` — Permanência, visitas, recência
- `signal-capture.service.ts` — Orquestrador com governança LGPD
- `signal-store.ts` — Contrato `ISignalStore` + `MemorySignalStore`

### Audience Layer (`src/audience/`)
- `audience-profile.store.ts` — Store desacoplado `AudienceProfile`
- `audience-signal-aggregator.ts` — Agregação presença → perfil comportamental
- `behavioral-features.ts` — Extrator determinístico de métricas comportamentais
- `intent-bridge.ts` — Ponte explícita `Audience → BridgeIntentSignal`
- `intent-signal.store.ts` — Store `BridgeIntentSignal`
- `physical-intent.adapter.ts` — Adapter `BridgeIntentSignal → LeadIntentSignal`
- `physical-intent.types.ts` — Taxonomia sinais físicos de intenção
- `segmentation-engine.ts` — Motor determinístico de segmentação declarativa

### Prospecting Layer (`src/prospecting/`)
- `lead-intent-signals.service.ts` — Ingestor cross-channel (digital + físico)
- `lead-scoring.service.ts` — Scoring de leads
- `lead-enrichment.service.ts` — Enriquecimento
- `lead-prioritization-orchestrator.service.ts` — Orquestração priorização
- `deal-probability-forecasting.service.ts` — Forecast probabilidade deal
- `lead-conversion-velocity.service.ts` — Velocity de conversão
- `predictive-deal-velocity.service.ts` — Velocity preditiva

### Autonomous Layer (`src/autonomous/`)
- `architectEngine.ts` — Engine arquitetural
- `machine-saas-automation-tech-leadEngine.ts` — Engine automação SaaS

## Documentação
- `MASTER_CONTEXT.md` — Governança canônica, status, matriz auditoria
- `docs/ARCHITECTURE_UNIFICATION.md` — Documento canônico unificação
- `docs/AUDIENCE_INTELLIGENCE.md` — Spec técnica Audience Intelligence V0
- `docs/SIGNAL_INTELLIGENCE.md` — Spec Signal Capture V0
- `docs/PHYSICAL_INTENT_INTEGRATION.md` — Spec Physical → Lead Intent V0
- `PUB_GIT_CLOSURE_RULE.md` — Regra mandatória fechamento estágios Git

## Prós
- **Arquitetura em camadas bem definida** — separação clara Signal → Audience → Intent → Lead → Conversion
- **Testes unitários reais** — 25+ testes passando nas camadas core
- **Governança LGPD** — built-in no signal capture
- **Determinístico** — geo-math, geofence, behavioral features são pure functions
- **TypeScript strict** — contratos tipados em toda a pipeline
- **Closed Loop** — arquitetura pensada para feedback loop completo

## Contras / Riscos
- **Private repo** — não open source
- **Camada 5/6 em evolução** — autonomous execution e closed loop feedback ainda não totalmente implementados
- **Dependência de infra** — precisa de stores reais (não só memory) para produção
- **Complexidade de domínio** — requer conhecimento profundo de geofence, LGPD, lead scoring

## Decisão
- [x] **Adotar** — Core do business engine da PUB, já implementado V0
- [x] **Institucionalizar** — Patterns → pub-research
- [ ] **Open source parts** — Geo-math, geofence engine, behavioral features poderiam ser libs abertas

## Ações de Integração
- [ ] Extrair `geo-math.ts`, `geofence-engine.ts` → lib open source `pub-geo`
- [ ] Extrair `behavioral-features.ts`, `segmentation-engine.ts` → lib `pub-audience-core`
- [ ] Documentar pipeline causalidade no `workflows/`
- [ ] Benchmark: comparar com alternativas open source (RudderStack, Segment, etc.)
- [ ] Integrar com PUB Neural (promoção de insights de leads)

## Links
- Repo: https://github.com/pubcoreagencia/pub-machine (private)
- MASTER_CONTEXT: `MASTER_CONTEXT.md`
- Architecture: `docs/ARCHITECTURE_UNIFICATION.md`
