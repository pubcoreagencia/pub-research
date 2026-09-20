# 🧪 PUB Research — Laboratório de Pesquisas da PUB

> **Organização:** [pubcoreagencia](https://github.com/pubcoreagencia)  
> **Propósito:** Descoberta, avaliação e documentação de skills, repositórios open source, IAs, ferramentas e tecnologias para o hub de criação e produção musical da PUB.

---

## 📁 Estrutura do Repositório

```
pub-research/
├── skills/          # Skills descobertas/avaliadas (OpenClaw, Claude Code, etc.)
├── repos/           # Repositórios open source relevantes (forks, mirrors, refs)
├── ias/             # Modelos, provedores, benchmarks de IA
├── tools/           # Ferramentas, CLIs, utilidades
├── workflows/       # Workflows, pipelines, automações testadas
├── docs/            # Documentação interna, guias, decisões
└── references/      # Links, papers, artigos, benchmarks externos
```

---

## 🎯 Objetivos

| Área | Foco |
|------|------|
| **Skills** | Skills OpenClaw, plugins, agents, MCP servers, workflows reutilizáveis |
| **Repositórios** | Projetos open source para fork, estudo, integração ou inspiração |
| **IAs** | Modelos (LLM, diffusion, audio, video), provedores, benchmarks, costs |
| **Tools** | CLIs, SDKs, frameworks, dev tools que aceleram o hub |
| **Workflows** | Pipelines CI/CD, automações, agentes, orquestração |
| **Docs** | ADRs, guias de setup, decisões de arquitetura, checklists |

---

## 🔬 Processo de Descoberta

1. **Descoberta** → Encontra skill/repo/IA/tool relevante
2. **Avaliação** → Testa, faz benchmark, verifica licença, manutenção
3. **Documentação** → Registra em `docs/` ou pasta correspondente com:
   - O que é / pra que serve
   - Como instalar / configurar
   - Prós / contras / limitações
   - Decisão: **adotar** / **monitorar** / **descartar**
4. **Integração** (se adotado) → Move pra produção, cria skill wrapper, etc.

---

## 📋 Templates

- [`docs/templates/skill-evaluation.md`](docs/templates/skill-evaluation.md) — Avaliação de skill
- [`docs/templates/repo-evaluation.md`](docs/templates/repo-evaluation.md) — Avaliação de repositório
- [`docs/templates/ia-benchmark.md`](docs/templates/ia-benchmark.md) — Benchmark de modelo IA
- [`docs/templates/tool-evaluation.md`](docs/templates/tool-evaluation.md) — Avaliação de ferramenta

---

## 🏷️ Tags Comuns

`#skill` `#openclaw` `#mcp` `#agent` `#workflow` `#automation`  
`#llm` `#diffusion` `#audio-gen` `#video-gen` `#multimodal`  
`#open-source` `#fork-candidate` `#integration-ready`  
`#adopted` `#monitoring` `#discarded` `#deprecated`

---

## 🔗 Links Úteis

- [OpenClaw Docs](https://docs.openclaw.ai)
- [ClawHub Skills](https://clawhub.openclaw.ai)
- [Awesome OpenClaw](https://github.com/openclaw/awesome-openclaw)
- [PUB Core Agencia](https://github.com/pubcoreagencia)

---

## 📝 Como Contribuir

1. Abra uma **Issue** com a descoberta (link, descrição, por que é relevante)
2. Use o template correspondente em `docs/templates/`
3. Marque com labels: `discovery`, `evaluation`, `integration`
4. Após avaliação, mova para a pasta correspondente e atualize o status

---

*Mantido pela equipe PUB — Hub de Criação e Produção Musical* 🎧
