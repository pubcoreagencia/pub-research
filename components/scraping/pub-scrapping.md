# Repo Evaluation: PUB Scrapping (Scrapers & Data Ingestion Engineering)

## Informações Básicas
- **Nome do Repo:** pub-scrapping
- **URL:** https://github.com/pubcoreagencia/pub-scrapping
- **Owner/Org:** pubcoreagencia
- **Licença:** Proprietário (private repo)
- **Último commit:** 2026-09-19
- **Data da avaliação:** 2026-09-20
- **Avaliador:** Genildo3000 / Matheus Paes (PUB REC)

## O que é / Para que serve
**PUB Scrapping** = Engenharia de scrapers e ingestores de dados para plataformas como Shopee, Mercado Livre, etc. Foco em extração estruturada, resiliente e escalável de dados de e-commerce/marketplaces.

## Documentação Identificada
- `MASTER_CONTEXT.md` — Governança e arquitetura
- `AUTONOMOUS_CYCLE.md` — Ciclo autônomo
- `PUB_GIT_CLOSURE_RULE.md` — Regra de fechamento Git

## Relevância para Research
- **Scraper patterns** — Arquitetura para scrapers manuteníveis (não spaghetti)
- **Anti-detection** — Rotación de user-agent, proxy, headers, behavior mimicry
- **Rate limiting** — Respeito a limites, backoff exponencial, circuit breaker
- **Data validation** — Schema validation, quality checks, deduplication
- **Incremental crawling** — Só o que mudou, hash-based change detection
- **Queue management** — Priorização, retry, dead letter queue
- **Targets conhecidos:** Shopee, Mercado Livre (pode expandir)

## Conexão com Research Externo (pub-neural)
- **Scrapling** — Benchmark como scraping/browser extraction engine
- **Google Maps Scraper Kit** — Prototype local scraper path
- **Buscando 1 Milhão** — Autonomous prospecting patterns
- **Crawl4AI** (já no pub-research) — Crawler otimizado para LLMs/RAG

## Prós
- Foco em engenharia de scrapers (não apenas scripts)
- Targets de alto valor (e-commerce BR)
- Integração com pipeline de dados da holding

## Contras / Riscos
- Private repo
- Pouca documentação visível
- Manutenção contínua necessária (sites mudam)
- Riscos legais/ToS (scraping pode violar termos)

## Decisão
- [x] **Adotar** — Infra de scraping necessária para PUB Machine, PUB Leads, PUB Ecom
- [x] **Institucionalizar** — Patterns → pub-research
- [ ] **Open source** — Framework base de scraper poderia ser lib

## Ações de Integração
- [ ] Extrair arquitetura base → `tools/scraper-framework.md`
- [ ] Documentar anti-detection patterns → `tools/anti-detection-patterns.md`
- [ ] Benchmark: pub-scrapping vs Crawl4AI vs Scrapling vs browser-use
- [ ] Integrar com Crawl4AI (adotado no pub-research) para RAG ingestion
- [ ] Criar skill OpenClaw: `scrape_ecommerce(platform, query) -> structured_data`

## Links
- Repo: https://github.com/pubcoreagencia/pub-scrapping (private)
- Crawl4AI: https://github.com/unclecode/crawl4ai (já em pub-research)
- Scrapling: https://scrapling.readthedocs.io
- browser-use: https://github.com/browser-use/browser-use (já em pub-research)
