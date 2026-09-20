# Repo Evaluation: Excalidraw (Hand-drawn Style Diagrams)

## Informações Básicas
- **Nome do Repo:** Excalidraw
- **URL:** https://github.com/excalidraw/excalidraw
- **Owner/Org:** excalidraw
- **Licença:** MIT
- **Stars/Forks:** ~70k stars / ~6k forks (set/2026)
- **Último commit:** Ativo (set/2026)
- **Linguagem principal:** TypeScript, React
- **Data da avaliação:** 2026-09-19
- **Avaliador:** Genildo3000 / Matheus Paes (PUB REC)

## O que é / Para que serve
Editor de diagramas/whiteboard **estilo mão-livre** (hand-drawn) — sketches, wireframes, flowcharts, mind maps, architecture diagrams com visual orgânico, "feito à mão". Usável como app standalone ou **embutido** em outras aplicações via biblioteca React.

## Por que é relevante para a PUB
- **Diagramas de arquitetura** do hub (agents, pipelines, data flow) com visual leve
- **Whiteboard colaborativo** para sessões de ideação musical/produção
- **Storyboarding** de clipes, vídeos, lyric videos
- **Wireframes** rápidos de UI para dashboards, portais
- **Embeddable** — pode integrar no dashboard PUB como widget
- **Colaboração real-time** (via Liveblocks, Yjs, ou próprio backend)

## Análise Técnica
| Aspecto | Avaliação (1-5) | Observações |
|---------|-----------------|-------------|
| Qualidade do código | 5 | TypeScript strict, bem testado, modular |
| Documentação | 5 | Docs completas, API reference, exemplos |
| Testes | 4 | Unit + integration + visual regression |
| Manutenção ativa | 5 | Core team + community ativa |
| Comunidade | 5 | Muito popular, plugins, extensions |
| Licença compatível | 5 | MIT |
| Facilidade de integração | 5 | Package `@excalidraw/excalidown` + React component |

## Dependências Principais
- **React** 18+
- **@excalidraw/excalidraw** (package principal)
- **Optional:** Liveblocks / Yjs / Socket.io para colaboração
- **Optional:** `@excalidraw/excalidraw` para export/import JSON

## Prós
- Visual único "hand-drawn" — menos intimidante, mais criativo
- **Embeddable** — React component drop-in
- Exporta: PNG, SVG, JSON, .excalidraw (file format)
- Biblioteca de elementos: shapes, arrows, text, images, frames, mermaid
- **Mermaid support** — renderiza diagramas Mermaid dentro do canvas
- Dark mode nativo
- Acessibilidade (keyboard navigation, screen readers)
- Plugins/extensions ecosystem
- Self-hostable (o app web é open source)

## Contras / Riscos
- **Não é diagramming técnico rigoroso** (não substitui draw.io/PlantUML para docs formais)
- Colaboração real-time requer backend separado (Liveblocks pago, ou self-host Yjs)
- Bundle size moderado (~200KB gzipped)
- Mobile UX limitada (melhor desktop/tablet)

## Decisão
- [x] **Adotar** — Integrar no dashboard PUB como widget de whiteboard/diagrams
- [x] **Adotar** — Usar para documentação visual (architecture, flows)
- [ ] **Monitorar** — Liveblocks para colaboração (custo)
- [ ] **Descartar** — 

## Ações de Integração
- [ ] `npm i @excalidraw/excalidraw`
- [ ] Criar wrapper component `ExcalidrawWidget` no dashboard
- [ ] Persistir diagrams no Supabase (JSON + PNG thumbnail)
- [ ] Templates PUB: agent pipeline, music production flow, release checklist
- [ ] Export/Import .excalidraw files
- [ ] Mermaid → Excalidraw sync para docs técnicas

## Links
- Repo: https://github.com/excalidraw/excalidraw
- App: https://excalidraw.com
- Docs: https://docs.excalidraw.com
- Package: https://www.npmjs.com/package/@excalidraw/excalidraw
- Liveblocks: https://liveblocks.io (collab backend)
- Mermaid: https://mermaid.js.org
