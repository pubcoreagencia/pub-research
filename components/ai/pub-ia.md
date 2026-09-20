# Repo Evaluation: PUB IA (Generative & Predictive AI Hub)

## Informações Básicas
- **Nome do Repo:** pub-ia
- **URL:** https://github.com/pubcoreagencia/pub-ia
- **Owner/Org:** pubcoreagencia
- **Licença:** Proprietário (private repo)
- **Último commit:** 2026-09-19
- **Data da avaliação:** 2026-09-20
- **Avaliador:** Genildo3000 / Matheus Paes (PUB REC)

## O que é / Para que serve
**PUB IA** = Hub e orquestrador de inteligência artificial generativa e preditiva da holding. Centraliza modelos, provedores, pipelines de inferência, fine-tuning, RAG, e orquestração multi-modelo para todos os produtos PUB.

## Documentação Identificada
- `MASTER_CONTEXT.md` — Governança e arquitetura
- `AUTONOMOUS_CYCLE.md` — Ciclo autônomo de IA
- `PUB_GIT_CLOSURE_RULE.md` — Regra de fechamento Git

## Relevância para Research
- **Model registry** — Catálogo de modelos (LLM, diffusion, audio, video, embedding)
- **Provider abstraction** — OpenRouter, OpenAI, Anthropic, Google, HuggingFace, Ollama, auto
- **Fallback chains** — Roteamento multi-provedor com quota/custo/latência
- **Fine-tuning pipeline** — Treinamento de modelos especializados (music, business, etc.)
- **RAG orchestration** — Integração com PUB Neural para retrieval
- **Cost tracking** — Monitoring de tokens, custos, latência por modelo/provedor
- **Evaluation/benchmarks** — Comparação contínua de modelos

## Conexão com OpenClaw (atual)
- O agente Genildo3000 usa OpenRouter com 4 modelos free:
  1. `openrouter/deepseek/deepseek-v4-flash-0731:free` (primário)
  2. `openrouter/nex-agi/nex-n2.5-pro:free`
  3. `openrouter/qwen/qwen3.8-27b:free`
  4. `openrouter/nvidia/nemotron-3-super-120b-a12b:free`

## Prós
- Centraliza decisão de modelo/provedor para toda a holding
- Permite swap de provedor sem mudar código dos produtos
- Cost tracking e fallback automático
- Base para fine-tuning de modelos próprios (music, business)

## Contras / Riscos
- Private repo
- Pouca documentação visível (só MASTER_CONTEXT)
- Precisa integração real com PUB Neural (retrieval) e PDL (execution)

## Decisão
- [x] **Adotar** — Hub de IA central da holding
- [x] **Institucionalizar** — Model registry, fallback chains → pub-research
- [ ] **Open source** — Provider abstraction layer poderia ser lib

## Ações de Integração
- [ ] Extrair model registry → `ias/model-registry.md`
- [ ] Documentar fallback chains atuais → `ias/fallback-chains.md`
- [ ] Benchmark modelos free vs pagos → `ias/free-model-benchmark.md`
- [ ] Integrar com OpenClaw config (pin-openrouter-free-models skill)
- [ ] Pipeline fine-tuning para modelos music (PUB Records)

## Links
- Repo: https://github.com/pubcoreagencia/pub-ia (private)
- OpenClaw config: `/Users/user/.openclaw/openclaw.json` (agents.entries.main.modelPolicy.allow)
- Skill: `pin-openrouter-free-models`
