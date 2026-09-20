# Repo Evaluation: PUB Neural (Cognitive Brain / Multi-Agent Orchestrator)

## Informações Básicas
- **Nome do Repo:** pub-neural
- **URL:** https://github.com/pubcoreagencia/pub-neural
- **Owner/Org:** pubcoreagencia
- **Licença:** Proprietário (private repo)
- **Linguagem principal:** Python
- **Último commit:** 2026-09-19
- **Data da avaliação:** 2026-09-20
- **Avaliador:** Genildo3000 / Matheus Paes (PUB REC)

## O que é / Para que serve
**PUB Neural** = Cérebro cognitivo, memória episódica/semântica e orquestrador multiagente da holding PUB. É a camada de **memória institucional**, **retrieval híbrido (vector + graph)**, **promoção de conhecimento** (CAPTURED → OBSERVED → EXTRACTED → CANDIDATE → VALIDATED → ADOPTED → INSTITUTIONAL) e **pesquisa inteligente**.

## Por que é relevante para a PUB
- **Core da arquitetura PUB** — "institutional cognition and memory"
- Memória de longo prazo para todos os agentes (PDL, Machine, IA, Records, etc.)
- Retrieval híbrido com proveniência de embedding (crítico para integridade)
- Pipeline research-to-skill: Open Notebook → Book to Skill → Skill institucionalizada
- Governança de conhecimento: evidência, abstention, validação, promoção
- Benchmarks de capacidade agentica (PP_AGENTIC_CAPABILITY_BENCHMARK)

## Documentos-chave no Repo
| Documento | Descrição |
|-----------|-----------|
| `research/2026-09-16-agent-ecosystem-research.md` | Registry de 50+ projetos externos auditados (Paperclip, Hermes, Maestri, ECC, etc.) |
| `research/external/2026-09-17-hkuds-agent-ecosystem-audit.md` | Auditoria de 8 projetos HKUDS (LightRAG, DeepTutor, nanobot, OpenHarness, etc.) |
| `docs/PUB_RESEARCH_INTELLIGENCE_PROTOCOL.md` | Protocolo de pesquisa institucional |
| `docs/HYBRID_RETRIEVAL_V0_1.md` | Retrieval híbrido vector+graph |
| `docs/VECTOR_INDEXING_V0_1.md` | Indexação vetorial |
| `docs/GRAPH_EXTRACTION_WORKERS_V0_1.md` | Workers de extração de grafo |
| `docs/INGESTION_V0_1_HARDENING_REPORT.md` | Hardening de ingestão |
| `docs/ADR-003-strict-tristate-evidence-gate.md` | ADR: evidence gate tristrito |
| `docs/PUB_SYSTEM_ARCHITECTURE.md` | Arquitetura do sistema PUB |
| `docs/ROADMAP_HOLDING_2026.md` | Roadmap 2026 |
| `benchmarks/` | Benchmarks adversariais, agentic capability, evidence abstention |
| `src/ingestion/` | Pipeline de ingestão de documentos |

## Arquitetura (síntese do HKUDS audit)
```
PUB Neural = Institutional Cognition & Memory
    ├── Memory (episódica/semântica)
    ├── Evidence & Provenance
    ├── Hybrid Retrieval (vector + graph)
    ├── Research Corpus
    ├── Lessons & Patterns
    ├── Decisions & Rules
    └── Institutional Promotion Pipeline
```

## Separação Canônica PUB (do HKUDS audit)
| Camada | Responsabilidade |
|--------|------------------|
| **PUB Neural** | Memória, evidência, retrieval, grafo, pesquisa, promoção institucional |
| **PDL** | Agent runtime, planning, tool execution, closed-loop, skills, sessions |
| **PUB ACP** | Dispatch, project registry, workspace, safety gates, execution context, observability |
| **Capability Fabric** | Typed adapters, CLI/MCP capabilities, API integrations, domain tools |

## Research Externo Registrado (50+ projetos)
**High Priority para PDL:**
- Paperclip (org chart, governance, heartbeats)
- Hermes Bot Mode (persistent specialist bots)
- Maestri (visual multi-agent workspace)
- Agency Agents (specialist personas, role taxonomy)
- Vibe Coding Toolkit (subagent orchestration)
- Headroom (token compression, cross-agent memory)
- Graft (code context graph)
- ECC (skills, memory, security, research-first)
- teamai-cli (portable team skills, MCP configs)
- Ponytail (minimal-change coding agent)
- Omni Route (multi-provider routing, fallback)
- Open Notebook (private research workspace)
- Book to Skill (knowledge-to-skill crystallization)

**Para PUB Neural:**
- codebase-memory-mcp (code knowledge graph)
- MiroFish (simulation/multi-agent world modeling)
- God's Eye View (spatial intelligence)

**Para PUB Leads:**
- Google Maps Scraper Kit
- Scrapling
- Buscando 1 Milhão
- OpenSEO

## Prós
- **Arquitetura madura** — separação clara de responsabilidades (Neural/PDL/ACP/Fabric)
- **Governança rigorosa** — promotion pipeline com evidência
- **Proveniência de embedding** — não mistura vector spaces incompatíveis
- **Research-first** — protocolo SOURCE → OBSERVATION → EVIDENCE → PATTERN → DECISION
- **Benchmarks reais** — adversarial, capability, abstention calibration
- **Institucionalização** — não só RAG, mas memory promotion

## Contras / Riscos
- **Private repo** — não open source (vendor lock-in interno)
- **Python only** — stack principal PUB é TypeScript/Bun (precisa bridge)
- **Complexidade alta** — múltiplas camadas, workers, pipelines
- **Manutenção pesada** — requer team dedicada

## Decisão
- [x] **Adotar** — Core da arquitetura PUB, já em produção
- [x] **Institucionalizar** — Research findings → pub-research (este repo)
- [ ] **Open source** — Avaliar liberar partes (retrieval, promotion pipeline)

## Ações de Integração
- [x] Auditar research docs → pub-research (em andamento)
- [ ] Extrair agent ecosystem research → entries em `repos/` e `skills/`
- [ ] Extrair HKUDS audit → entries em `repos/` (LightRAG, DeepTutor, nanobot, OpenHarness, CLI-Anything, AI-Researcher)
- [ ] Benchmark patterns → `ias/` e `workflows/`
- [ ] Promoção pipeline → documentar em `docs/` ou `workflows/`

## Links
- Repo: https://github.com/pubcoreagencia/pub-neural (private)
- Research doc: `research/2026-09-16-agent-ecosystem-research.md`
- HKUDS audit: `research/external/2026-09-17-hkuds-agent-ecosystem-audit.md`
