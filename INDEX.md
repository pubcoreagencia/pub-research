# 📇 Catálogo do Laboratório — PUB Research

> **Laboratório de Repositórios para Aplicação nos Projetos PUB**  
> Última atualização: 2026-09-20

---

## 🧩 **Componentes por Categoria**

### 🎨 **UI / Design System** (`components/ui/`)
| Componente | Status | Para que serve | Onde aplicar |
|------------|--------|----------------|--------------|
| [shadcn/ui + Radix + Tailwind](components/ui/shadcn-ui-radix-tailwind.md) | ✅ Adotar | Design system copy-paste, acessível, TypeScript | Todos projetos (dashboards, admin, landing) |
| [Lucide Icons + Tailwind Plugins](components/ui/lucide-icons-tailwind-plugins.md) | ✅ Adotar | Icon set padrão + plugins (typography, forms, aspect-ratio) | Todos projetos |
| [Excalidraw](components/ui/excalidraw.md) | ✅ Adotar | Whiteboard/diagrams hand-drawn, embeddable React, Mermaid | pub-records (storyboard), pub-machine (architecture), pub-ia |

### 🤖 **IA / Modelos / Agentes** (`components/ai/`)
| Componente | Status | Para que serve | Onde aplicar |
|------------|--------|----------------|--------------|
| [PUB Neural](components/ai/pub-neural.md) | ✅ Adotar | Cérebro cognitivo, retrieval híbrido, promoção institucional | Base para todos (memory, retrieval, lessons) |
| [PUB Machine](components/ai/pub-machine.md) | ✅ Adotar | Motor prospecção 6 camadas (Signal→Audience→Intent→Lead→Conversion) | pub-machine, pub-machine-2, pub-machine-saas |
| [PUB IA Hub](components/ai/pub-ia.md) | ✅ Adotar | Model registry, fallback chains (4 free OpenRouter), fine-tuning | pub-ia, 9Router, OpenClaw config |
| [PUB ACP Lab](components/ai/pub-acp-lab.md) | ✅ Adotar | ACP Bridge → Antigravity CLI, NDJSON, scoped permissions | pub-acp, PDL integration, Capability Fabric |
| [9Router Cloud](components/ai/pub-9router-cloud.md) | ✅ Adotar | Servidor roteamento modelos 24/7, métricas, fallback, quotas | pub-9router, OpenClaw, PUB IA |
| [PUB Machine 2](components/ai/pub-machine-2.md) | ✅ Adotar | 2ª gen: closed loop, autonomia total, PDL/Neural/ACP/Fabric | pub-machine-2 (próxima geração) |
| [LeadCore](components/ai/leadcore.md) | ✅ Adotar | CRM B2B unificado, enrichment, scoring, LGPD | pub-machine, pub-ecom, pubgrowth |
| [browser-use](components/ai/browser-use.md) | ✅ Adotar | Browser automation para agentes LLM, stealth, visual debug | pub-machine (scout), pub-scrapping, research agents |
| [Crawl4AI](components/scraping/crawl4ai.md) | ✅ Adotar | Crawler otimizado LLMs/RAG, Markdown limpo | pub-scrapping, pub-neural (ingestion), research |
| [pub-scrapping](components/scraping/pub-scrapping.md) | ✅ Adotar | Scrapers Shopee/ML, anti-detection, incremental | pub-machine, pub-ecom, pubgrowth |
| [Automated Agentic Web Agency](components/ai/automated-agentic-ai-web-agency.md) | 📚 Referência | Arquitetura 15 agentes, HITL, queue, dashboard | Referência para pub-machine/PDL architecture |
| [HeyGen Hyperframes](components/ai/heygen-hyperframes.md) | 👀 Monitorar | Avatar/video SaaS, lip-sync estado da arte | pub-records (lyric videos), content automation |
| [Context7](components/ai/context7.md) | 👀 Monitorar | Context management LLMs (RAG, memory, compression) | pub-neural (se escalar), PDL |
| [Archify](components/ai/archify.md) | 👀 Monitorar | Diagramas arquitetura auto-gerados (Terraform, K8s) | pub-core-os, pub-ecom, pub-machine |
| [Grill Me](components/ai/grill-me.md) | 👀 Monitorar | Code review bot com humor, GitHub integration | Todos (CI/CD code review) |

### 🎵 **Audio / Music** (`components/audio/`)
| Componente | Status | Para que serve | Onde aplicar |
|------------|--------|----------------|--------------|
| [PUB Records](components/audio/pub-records.md) | ✅ Adotar | Gravadora, estúdio, Beats marketplace, PUB DAW | pub-records (core) |
| [XP Audio Lab](components/audio/xp-audio-lab.md) | ✅ Adotar | Sound design, VST/WebAudio, WASM DSP, AudioWorklets | pub-records (DAW, plugins), R&D audio |

### 🕷️ **Scraping / Data** (`components/scraping/`)
| Componente | Status | Para que serve | Onde aplicar |
|------------|--------|----------------|--------------|
| [Crawl4AI](components/scraping/crawl4ai.md) | ✅ Adotar | Crawler LLMs/RAG, Markdown limpo, chunking semântico | pub-neural ingestion, pub-scrapping, research |
| [pub-scrapping](components/scraping/pub-scrapping.md) | ✅ Adotar | Scrapers produção (Shopee, ML), anti-detection | pub-machine, pub-ecom, pubgrowth |

### ☁️ **Infra / SaaS / Platform** (`components/infra/`)
| Componente | Status | Para que serve | Onde aplicar |
|------------|--------|----------------|--------------|
| [PUB Core OS](components/infra/pub-core-os.md) | ✅ Adotar | Governança canônica, Git closure, master context template | Todos (governança) |
| [Neural OS](components/infra/neural-os.md) | ✅ Adotar | PUB MASTER MEGA BLASTER CONTEXT (autoridade institucional) | Todos (authority hierarchy) |
| [PUB Dev Loop](components/infra/pub-dev-loop.md) | ✅ Adotar | Prototipação rápida, 3D Office, free model benchmarks | Todos (prototyping, benchmarking) |
| [PUB Ecom](components/infra/pub-ecom.md) | ✅ Adotar | Monorepo e-commerce, catalog worker, browser import actors | pub-ecom |
| [PUB Machine SaaS](components/infra/pub-machine-saas.md) | ✅ Adotar | Multi-tenancy, billing Stripe, white-label | pub-machine-saas |
| [PubGrowth AI](components/infra/pubgrowth-ai-evolution.md) | ✅ Adotar | Cloudflare Workers + Supabase RLS + Banco Inter PIX + mTLS | pubgrowth, template para SaaS |

---

## 🎯 **Integrações por Projeto PUB** (`integrations/`)

| Projeto | Guia de Integração | Componentes-Chave |
|---------|-------------------|-------------------|
| **pub-machine** (v1/v2/SaaS) | `integrations/pub-machine/` | pub-scrapping, Crawl4AI, browser-use, leadcore, 9Router, pub-acp-lab, pub-machine-2 |
| **pub-records** (DAW/Beats/Label) | `integrations/pub-records/` | XP Audio Lab, WebAudio stack, Excalidraw, shadcn/ui, HeyGen (monitor) |
| **pub-ia** (Hub IA) | `integrations/pub-ia/` | 9Router Cloud, OpenRouter free models, Context7 (monitor), fine-tune pipeline |
| **pub-ecom** | `integrations/pub-ecom/` | Monorepo patterns, Catalog worker, Browser import actors, TanStack Start |
| **pubgrowth** | `integrations/pubgrowth/` | Cloudflare Workers, Supabase RLS, Banco Inter PIX, mTLS, AI Continuity |
| **pub-acp** | `integrations/pub-acp/` | ACP Bridge, NDJSON protocol, Antigravity CLI, Scoped permissions |
| **pub-9router** | `integrations/pub-9router/` | Model routing, Metrics dashboard, Encrypted DB, Fallback chains |

---

## ⚖️ **Decisões de Adoção** (`decisions/`)

| Pasta | Descrição |
|-------|-----------|
| `ADOPTED/` | Componentes integrados + guias de uso |
| `ADAPTING/` | Em adaptação + blockers identificados |
| `MONITORING/` | Acompanhando + critérios claros de reavaliação |
| `DISCARDED/` | Avaliados + motivo da não adoção |

---

## 📊 **Benchmarks Reais** (`benchmarks/`)

| Categoria | Benchmarks |
|-----------|------------|
| `models/` | Free vs paid: latency, quality, cost, context |
| `scraping/` | Crawl4AI vs browser-use vs Scrapling vs pub-scrapping |
| `audio/` | WebAudio vs native VST vs WASM DSP |
| `routing/` | 9Router vs OpenRouter vs custom routing |

---

## 📋 **Templates** (`templates/`)

| Template | Uso |
|----------|-----|
| `component-evaluation.md` | Avaliar novo componente |
| `integration-guide.md` | Documentar integração em projeto |
| `benchmark-template.md` | Benchmark comparativo métricas reais |
| `decision-record.md` | ADR-style decision record |

---

## 📈 **Estatísticas**

- **Total componentes:** 27 (10 externos + 17 internos)
- **✅ Adotar:** 22 — Prontos para integração
- **👀 Monitorar:** 4 — Critérios definidos para reavaliação
- **📚 Referência:** 1 — Inspiração arquitetural
- **❌ Descartado:** 0

---

## 🔍 **Navegação Rápida por Tag**

`#ui` `#design-system` `#ai` `#models` `#routing` `#agents` `#acp` `#audio` `#webaudio` `#vst` `#wasm` `#scraping` `#crawling` `#browser-automation` `#saas` `#multi-tenancy` `#cloudflare` `#supabase` `#pix` `#mtls` `#monorepo` `#governance` `#adopted` `#monitoring` `#reference`

---

*Catálogo vivo — atualize ao adicionar/remover componentes ou mudar decisões*
