# 📇 PUB Research — Research Intelligence Engine

> Research Engine multicanal + laboratório de componentes e integrações reutilizáveis.
> Última atualização: 2026-09-28

## Papel canônico

PUB Research é a camada de pesquisa e inteligência de fontes do ecossistema PUB.

Capacidades complementares:
1. Research Engine — captura, extração, normalização, análise, qualificação e persistência.
2. Research Lab — componentes, integrações, benchmarks e decisões reutilizáveis.

O Research Engine é destino-agnóstico: uma descoberta pode servir PUB Neural, PP, PDL, Ecom, Leads, IA, ACP, 9Router, Machine, Records, holding ou novos produtos.

## Source Adapters

| Fonte | Papel | Estado |
|---|---|---|
| Instagram | Primeiro caso de uso; pesquisa humana via grupo + browser autenticado | MVP |
| GitHub | Repositórios, código, issues, releases e documentação | Planejado |
| YouTube | Vídeos, canais, transcrições e descrições | Planejado |
| Reddit | Discussões, experiências e sinais de comunidade | Planejado |
| Web / Search | Pesquisa geral e descoberta | Planejado |
| News | Notícias e sinais temporais | Planejado |
| Documentation | Documentação técnica e de produto | Planejado |
| Future adapters | Fontes aprovadas | Extensível |

Decisão arquitetural: não criar scrapers isolados. Cada adapter alimenta o contrato comum de Research Item e preserva a proveniência específica.

## Pipeline

SOURCE → CAPTURE → EXTRACT → NORMALIZE → ANALYZE → QUALIFY → PERSIST → ECOSYSTEM CONSUMERS → SUGGESTION / DECISION / IMPLEMENTATION → RESULT → NEW SIGNAL.

Entradas humanas e autônomas convergem no mesmo pipeline.

## Caso inicial: Instagram

Pesquisar → encontrar conteúdo → compartilhar no grupo → browser autenticado detecta URL → abrir com a mesma sessão autorizada → capturar → extrair multimodalmente → persistir Research Item.

Suporta, quando acessível: imagem, carrossel, vídeo/reel, conteúdo misto, caption, hashtags, mentions, autor, timestamp, links, metadados visíveis, OCR, descrição visual, transcrição, cenas/segmentos, produtos, marcas, ofertas e CTAs.

Credenciais, cookies e tokens não pertencem ao Research Item.

## Research Item e proveniência

Campos conceituais: source, source_type, url, author, timestamp, raw_content, media, transcript, ocr, entities, topics, claims, products, brands, insights, opportunities, relevance, qualification, provenance e downstream_candidates.

Cadeia: SOURCE URL → CAPTURE → RAW EVIDENCE → OCR / TRANSCRIPTION → AI ANALYSIS → QUALIFICATION → DOWNSTREAM SUGGESTION → IMPLEMENTATION / VALIDATION.

## Consumidores

| Consumidor | Uso possível |
|---|---|
| PUB Neural | conhecimento, retrieval e memória institucional |
| PP / Prototype | descoberta de produtos e oportunidades |
| PDL / Dev Loop | sinais técnicos e oportunidades de implementação |
| PUB Ecom | produtos, ofertas e inteligência de mercado |
| PUB Leads | sinais de mercado e oportunidades |
| PUB IA | modelos, ferramentas e infraestrutura |
| PUB ACP | ferramentas e capacidades para automação |
| PUB 9Router | modelos, providers e routing |
| PUB Machine | sinais de mercado e automação |
| PUB Records | tendências, ferramentas e referências |
| Holding / ventures | oportunidades reutilizáveis |

Nenhum consumidor é proprietário exclusivo da pesquisa.

## Autonomia

MVP: compartilhar → capturar → extrair → analisar → persistir.

Evolução: missão → descoberta → captura → extração → análise → qualificação → persistência → novas perguntas.

Governança: Evidence → Research → Qualification → Suggestion → Human / governed authorization → Implementation → Validation.

## Laboratório de componentes

| Categoria | Conteúdo |
|---|---|
| UI / Design System | shadcn/ui, Radix, Lucide, Excalidraw |
| IA / Modelos / Agentes | PUB Neural, PUB IA, 9Router, browser-use, ACP |
| Audio / Music | PUB Records, XP Audio Lab |
| Scraping / Data | Crawl4AI, pub-scrapping, browser automation |
| Infra / SaaS | PUB Core OS, Neural OS, PDL, Ecom, Machine SaaS |
| Governance | Git closure, autoridade e proveniência |

## Integrações

- PUB Machine: integrations/pub-machine/
- PUB Records: integrations/pub-records/
- PUB IA: integrations/pub-ia/
- PUB Ecom: integrations/pub-ecom/
- PubGrowth: integrations/pubgrowth/
- PUB ACP: integrations/pub-acp/
- PUB 9Router: integrations/pub-9router/

## Decisões

- decisions/ADOPTED/
- decisions/ADAPTING/
- decisions/MONITORING/
- decisions/DISCARDED/

Arquitetura multicanal: docs/INSTAGRAM-RESEARCH-AUTONOMY-MASTER-CONTEXT.md

## Benchmarks

Models, scraping, routing e research devem ser avaliados com testes reais, incluindo quando aplicável latência, qualidade, custo, completude de captura, OCR, transcrição e qualidade de análise.

## Templates

- templates/component-evaluation.md
- templates/integration-guide.md
- templates/benchmark-template.md
- templates/decision-record.md

## Tags

#research-engine #research #multimodal #source-adapters #instagram #github #youtube #reddit #web #news #documentation #provenance #ai #agents #browser-automation #scraping #pub-neural #autonomy #governance

*Catálogo vivo — atualize ao adicionar fontes, componentes, integrações, benchmarks ou decisões.*