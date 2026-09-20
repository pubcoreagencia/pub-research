# Repo Evaluation: Archify (Architecture Diagrams / Documentation)

## Informações Básicas
- **Nome do Repo:** Archify
- **Possíveis URLs:**
  - https://github.com/archify/archify
  - https://github.com/archifyio/archify
  - https://archify.io
- **Owner/Org:** Archify / archifyio
- **Licença:** MIT / Apache-2.0 (provavelmente)
- **Data da avaliação:** 2026-09-19
- **Avaliador:** Genildo3000 / Matheus Paes (PUB REC)

## O que é / Para que serve
**Archify** = Ferramenta para **geração automática de diagramas de arquitetura** a partir de código, infraestrutura (Terraform, CloudFormation, Kubernetes), ou configuração. Transforma infra-as-code em diagramas visuais atualizados automaticamente.

## Por que é relevante para a PUB
- **Documentação viva** da arquitetura do hub (agents, pipelines, data flow)
- **Sync automático** — diagrama sempre reflete o código/infra real
- **Onboarding** — novos devs entendem a arquitetura visualmente
- **Auditoria** — visualiza dependências, single points of failure
- **Integração CI/CD** — diagrama atualizado a cada deploy

## Análise Técnica
| Aspecto | Avaliação (1-5) | Observações |
|---------|-----------------|-------------|
| Qualidade do código | 4 | Se for projeto ativo da Archify.io |
| Documentação | 3 | Depende do projeto |
| Integração | 4 | CLI + CI/CD + IDE plugins |
| Formatos suportados | 4 | Terraform, K8s, Docker Compose, CloudFormation, AWS/CDK |
| Output | 4 | Mermaid, PlantUML, Draw.io, SVG, PNG |
| Open Source | 3 | Core pode ser closed (SaaS) |

## Prós
- Diagramas **sempre atualizados** (single source of truth = código)
- Suporta múltiplos formatos de infra
- Integração CI/CD nativa
- Exporta para Mermaid/PlantUML (compatível com Excalidraw, GitHub, Notion)
- Visualização de drift (diff entre diagrama e reality)

## Contras / Riscos
- **Pode ser SaaS proprietário** (Archify.io é produto comercial)
- **Custo** — planos pagos para times/enterprise
- **Curva de aprendizado** — configuração inicial
- **Dependência externa** para gerar docs internas

## Alternativas Open Source (monitorar)
- **Terraform Graph** → `terraform graph | dot -Tsvg > graph.svg`
- **KubeView** — Kubernetes cluster visualizer
- **KubeViz** — K8s visualization
- **Diagrams (Python)** — `diagrams.mingrammer.com` (code-as-diagrams)
- **Architect** — AWS architecture diagrams as code
- **Cloudcraft** — AWS diagrams (freemium)
- **Mermaid/PlantUML** — Manual mas flexível

## Decisão
- [ ] **Adotar** — Se tiver plano free/oss generoso
- [x] **Monitorar** — Acompanhar se abrirem core ou surgir alt open source
- [x] **Referência** — Conceito de "diagrams as code" / "docs as code"
- [ ] **Descartar** — 

## Ações
- [ ] Verificar se Archify tem versão open source / free tier
- [ ] Testar `diagrams` (Python) como alternativa open source
- [ ] Integrar Mermaid/PlantUML generation no CI da PUB
- [ ] Usar Excalidraw + Mermaid para diagramas manuais por enquanto

## Links
- Archify: https://archify.io
- Diagrams (Python): https://diagrams.mingrammer.com / https://github.com/mingrammer/diagrams
- Mermaid: https://mermaid.js.org
- PlantUML: https://plantuml.com
- Terraform Visual: https://github.com/haoten/terraform-visual
