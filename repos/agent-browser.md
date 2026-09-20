# Repo Evaluation: Agent Browser / Browser Automation for Agents

## Informações Básicas
- **Nome do Repo:** Provavelmente `browser-use` ou `agent-browser` ou `stagehand`
- **Principais candidatos open source:**
  - `browser-use/browser-use` — Browser automation for AI agents (muito popular)
  - `browserbase/stagehand` — Browser automation framework for agents
  - `puppeteer/puppeteer` — Headless Chrome (base)
  - `playwright/playwright` — Cross-browser automation (Microsoft)
  - `seleniumhq/selenium` — Legacy, mas ainda usado
- **Owner/Org:** Diversos
- **Licença:** MIT / Apache-2.0
- **Data da avaliação:** 2026-09-19
- **Avaliador:** Genildo3000 / Matheus Paes (PUB REC)

## O que é / Para que serve
Ferramentas para **agentes de IA controlarem navegadores** — navegar, clicar, preencher formulários, extrair dados, fazer login, interagir com SPAs, etc. Essencial para agentes que precisam acessar web "real" (não só APIs).

## Por que é relevante para a PUB
- **Scout agent** — descoberta de leads via Google Places, redes sociais, sites
- **Content research** — scraping de referências musicais, trends, playlists
- **Social media automation** — postar, interagir, monitorar
- **Testing** — testar dashboards, portais, landing pages
- **Data extraction** — métricas de streaming, charts, analytics

## Análise Técnica (browser-use como referência principal)
| Aspecto | Avaliação (1-5) | Observações |
|---------|-----------------|-------------|
| Qualidade do código | 5 | Python, bem estruturado, Pydantic, async |
| Documentação | 4 | README bom, exemplos, mas API reference limitada |
| Facilidade de uso | 5 | `Agent(task="...").run()` — muito simples |
| Integração LLM | 5 | Funciona com OpenAI, Anthropic, Ollama, custom |
| Stealth/anti-detect | 4 | Undetected-chromedriver, user-agent rotation |
| Manutenção ativa | 5 | Muito ativo, releases frequentes |
| Comunidade | 5 | 20k+ stars, Discord ativo |

## Dependências Principais (browser-use)
- **Python** 3.10+
- **Playwright** (browser engine)
- **LangChain** / **LangGraph** (opcional, para orchestration)
- **Pydantic** (schemas)
- **OpenAI/Anthropic/Ollama** (LLM)

## Prós (browser-use)
- **Feito para agentes** — API simples: `Agent(task="...").run()`
- **LLM-native** — o LLM decide ações, não scripts rígidos
- **Visual debugging** — grava vídeo, screenshots, DOM snapshots
- **Stealth mode** — evita detecção de bot
- **Multi-tab** — gerencia múltiplas abas
- **Human-in-the-loop** — pode pausar para intervenção humana
- **Open source** — MIT, self-hostable, sem vendor lock-in

## Contras / Riscos
- **Python only** — se stack PUB é TypeScript/Bun, precisa bridge
- **Resource heavy** — Chrome headless consome RAM/CPU
- **Fragilidade** — sites mudam, seletores quebram
- **Rate limits** — sites bloqueiam scraping agressivo
- **Legal/ToS** — scraping pode violar termos de uso

## Decisão
- [x] **Adotar** — `browser-use` para agentes de research/scraping (via Python subprocess ou service)
- [x] **Monitorar** — `stagehand` (TypeScript native) como alternativa TS
- [ ] **Descartar** — 

## Ações de Integração
- [ ] Criar serviço Python `browser-agent` (FastAPI) que expõe `/run-task`
- [ ] Wrapper skill OpenClaw: `browser_task(task: string) -> result`
- [ ] Definir tasks padrão: `scout_leads`, `research_artist`, `monitor_social`, `extract_metrics`
- [ ] Rate limiting + proxy rotation (residencial)
- [ ] Persistir sessões (cookies, localStorage) para login persistente

## Links
- browser-use: https://github.com/browser-use/browser-use
- Stagehand: https://github.com/browserbase/stagehand
- Playwright: https://playwright.dev / https://github.com/microsoft/playwright
- Puppeteer: https://pptr.dev / https://github.com/puppeteer/puppeteer
- Undetected ChromeDriver: https://github.com/ultrafunkamsterdam/undetected-chromedriver
