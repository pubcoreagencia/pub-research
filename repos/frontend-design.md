# Repo Evaluation: Frontend Design Resources

## Informações Básicas
- **Nome do Repo:** Vários repos de frontend design (design systems, component libraries, UI kits)
- **Possíveis candidatos:**
  - `shadcn/ui` — Componentes acessíveis, copy-paste, Tailwind + Radix
  - `radix-ui/primitives` — Headless UI primitives
  - `tailwindlabs/tailwindcss` — Framework CSS utility-first
  - `vercel/geist` — Fonte + design system da Vercel
  - `chakra-ui/chakra-ui` — Component library React
  - `mantine-dev/mantine` — React components + hooks
  - `heroui-inc/heroui` — Componentes bonitos, acessíveis
- **Owner/Org:** Diversos
- **Licença:** MIT / Apache-2.0 (maioria)
- **Data da avaliação:** 2026-09-19
- **Avaliador:** Genildo3000 / Matheus Paes (PUB REC)

## O que é / Para que serve
Coleção de repositórios de **design systems, component libraries, UI kits e ferramentas de frontend** para construir interfaces bonitas, acessíveis e consistentes rápido.

## Por que é relevante para a PUB
- Dashboard do hub (monitoramento de agentes, sessões, métricas)
- Interface de cliente (portal de entregas, briefings, aprovações)
- Landing pages de projetos musicais
- Admin panels para gerenciar automações
- Componentes prontos = velocidade + consistência visual

## Análise Técnica (shadcn/ui como referência principal)
| Aspecto | Avaliação (1-5) | Observações |
|---------|-----------------|-------------|
| Qualidade do código | 5 | TypeScript strict, acessível (Radix), bem testado |
| Documentação | 5 | Exemplos claros, guias de migração, componentes individuais |
| Testes | 4 | Testes de regressão visual, a11y |
| Manutenção ativa | 5 | Updates frequentes, community ativa |
| Comunidade | 5 | Muito popular, muitos exemplos/extensions |
| Licença compatível | 5 | MIT |
| Facilidade de integração | 5 | Copy-paste, zero deps runtime, Tailwind-based |

## Dependências Principais (shadcn/ui)
- **React** 18+
- **Tailwind CSS** 3.4+
- **Radix UI** primitives (headless)
- **class-variance-authority** (variants)
- **clsx / tailwind-merge** (utils)
- **lucide-react** (icons)

## Prós (shadcn/ui)
- **Não é uma lib** — você copia o código, é seu, customiza à vontade
- Acessibilidade nativa (Radix primitives)
- Design system coerente out of the box
- Dark mode built-in
- Tree-shaking automático (só usa o que importa)
- Funciona com Next.js, Vite, Remix, Astro, etc.
- Muito usado na indústria — fácil contratar/achar devs que conhecem

## Contras / Riscos
- Requer **Tailwind CSS** (opinião forte, nem todo time gosta)
- "Copy-paste" = você mantém o código (updates manuais)
- Bundle size pode crescer se importar muitos componentes
- Curva de aprendizado se time não conhece Tailwind + Radix patterns

## Decisão
- [x] **Adotar** — shadcn/ui como base para dashboards/admin UIs da PUB
- [x] **Monitorar** — heroui, mantine, chakra como alternativas
- [ ] **Descartar** — 

## Ações de Integração
- [ ] Setup shadcn/ui no repo do dashboard PUB
- [ ] Criar theme customizado (cores PUB, tipografia, border radius)
- [ ] Componentes base: Button, Card, Table, Dialog, Form, Chart, Sidebar, Avatar, Badge, Toast
- [ ] Storybook para documentar componentes internos
- [ ] Design tokens exportáveis (Figma → code sync)

## Links
- shadcn/ui: https://ui.shadcn.com / https://github.com/shadcn-ui/ui
- Radix UI: https://www.radix-ui.com / https://github.com/radix-ui/primitives
- Tailwind CSS: https://tailwindcss.com / https://github.com/tailwindlabs/tailwindcss
- Heroui: https://heroui.com / https://github.com/heroui-inc/heroui
- Mantine: https://mantine.dev / https://github.com/mantine-dev/mantine
