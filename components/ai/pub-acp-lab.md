# Repo Evaluation: PUB ACP Lab (Agent Client Protocol Bridge)

## Informações Básicas
- **Nome do Repo:** pub-acp-lab
- **URL:** https://github.com/pubcoreagencia/pub-acp-lab
- **Owner/Org:** pubcoreagencia
- **Licença:** Proprietário (private repo)
- **Linguagem principal:** JavaScript (Node.js)
- **Último commit:** 2026-09-19
- **Data da avaliação:** 2026-09-20
- **Avaliador:** Genildo3000 / Matheus Paes (PUB REC)

## O que é / Para que serve
**PUB ACP Lab** = Laboratório experimental para orquestração programática entre clientes, **ACP (Agent Client Protocol)** e **Google Antigravity CLI (`agy`)**. Implementa uma ponte de transporte autônoma conectando orquestradores (Node.js, Python, backends, APIs) ao `agy` via protocolo ACP padronizado, sem intervenção humana.

## Arquitetura (do README)
```
CLIENTE ORQUESTRADOR (Node/Python/Backend/API)
        │
   JSON-RPC / NDJSON
        ▼
PUB-ACP-BRIDGE (bridge.js / server.js)
        │
   ACP Protocol v2 (stdio JSON-RPC)
        ▼
ADAPTER ACP (agy-agent-acp / dongitran@a314a06)
        │
   NDJSON bidirecional stdio
        ▼
ANTIGRAVITY CLI (agy.exe) — Processo persistente / Agente IA
        │
   Tool Calls nativos (view_file, replace, run)
        ▼
FILESYSTEM DO WORKSPACE
```

## Componentes Principais
1. **`bridge.js`** — Módulo central `PubAcpBridge`: gerencia lifecycle do processo ACP, handshake `initialize`, cria sessões (`session/new`), despacha prompts (`session/prompt`), mapeia eventos real-time (`chunk`, `tool_call`, `usage`), encerramento gracioso com timeouts.
2. **`server.js`** — Interface CLI NDJSON sobre stdin/stdout para orquestradores desacoplados de qualquer linguagem.
3. **`test-suite.js`** — Suíte automatizada validando multi-turn, leitura/escrita, contexto persistente, correção de bugs, resiliência a falhas.

## Protocolo NDJSON (server.js)
**Entrada (Orquestrador → Bridge):**
- `create_session` — cwd
- `prompt` — sessionId, prompt, streaming callbacks
- `close` — encerramento

**Saída (Bridge → Orquestrador):**
- `ready` — inicialização
- `session_created` — sessionId
- `request_started` — início execução
- `chunk` — streaming chunks
- `tool_call` — notificação tool call (title, toolInput)
- `usage_update` — tokens (input, output, total)
- `prompt_result` — resposta final, stopReason
- `request_finished` — fim lifecycle
- `closed` — encerramento gracioso

## Segurança & Permissões Scoped (v0.2.0+)
- **Não usa `--dangerously-skip-permissions`** — default seguro
- **`settings.json` granular** — `~/.gemini/antigravity-cli/settings.json` com regras restritas ao workspace
- **Bloqueio automático fora do escopo** — comandos não autorizados negados pelo motor antigravity
- **Isolamento total** — confinado ao diretório do POC

## Fases Documentadas
| Fase | Documento | Status |
|------|-----------|--------|
| Phase 3 | `PHASE_3_FINAL_AUDIT.md` | Final audit |
| Phase 4 | `PHASE_4_FINAL_AUDIT.md` | Final audit |
| Phase 5 | `PHASE_5_INTEGRATION_RESEARCH.md` | Integration research |
| Phase 6 | `PHASE_6_CHATGPT_BROWSER.md` | ChatGPT Free Browser Bridge |
| Phase 7 | `PHASE_7_TRANSPORT_READINESS.md` | Transport readiness |
| Sagaz | `SAGAZ_PHASE_0_CHECKPOINT.md` | Checkpoint |

## Fase 6 — ChatGPT Free Browser Bridge (`src/browser-adapter/`)
- **Local SSE/HTTP Server** (`bridge-server.js`) — porta 5000
- **Extension Client** (`browser-client.js`) — protocolo SSE/HTTP
- **End-to-End Orchestrator** (`browser-orchestrator.js`) — fluxo `ChatGPT Free → Browser Extension → Localhost → ACP → AGY → ChatGPT Free`

## Limitação Atual (Platform Integration Blocker)
> O POC comprova transporte programático bidirecional autônomo entre cliente externo local e Antigravity CLI. **Não significa** que conversa web ChatGPT Free possa abrir conexão direta com `localhost` — navegadores não têm acesso a processos locais sem agente intermediário/daemon/túnel seguro.

## Prós
- **Protocolo padrão ACP** — interoperável, não proprietário
- **Segurança scoped** — permissões granulares, sem skip-permissions
- **Multi-linguagem** — NDJSON sobre stdio = qualquer linguagem consome
- **Streaming real-time** — chunks, tool_calls, usage updates
- **Testes automatizados** — multi-turn, contexto, erro, security
- **Bridge para ChatGPT Free** — Fase 6 conecta web UI ↔ local agent

## Contras / Riscos
- Private repo
- **Platform blocker** — web ChatGPT não acessa localhost diretamente
- Dependência do `agy` (Google Antigravity CLI) — binary externo
- Windows paths hardcoded nos exemplos (portabilidade?)
- ACP adapter (`agy-agent-acp`) — fork específico `@ a314a06`

## Decisão
- [x] **Adotar** — Camada ACP da holding (execution control plane)
- [x] **Institucionalizar** — Patterns → pub-research
- [ ] **Open source** — Bridge module, NDJSON protocol, test suite

## Ações de Integração
- [ ] Extrair `bridge.js` → lib `pub-acp-bridge` (npm package)
- [ ] Documentar NDJSON protocol → `tools/acp-ndjson-protocol.md`
- [ ] Documentar security scoped pattern → `tools/scoped-permissions-pattern.md`
- [ ] Fase 6 browser bridge → `workflows/chatgpt-browser-bridge.md`
- [ ] Integrar com PDL (agent runtime) como capability fabric
- [ ] Benchmark: ACP vs MCP vs custom protocols

## Links
- Repo: https://github.com/pubcoreagencia/pub-acp-lab (private)
- Standalone consumer: https://github.com/pubcoreagencia/pub-acp-standalone
- ACP Protocol: https://github.com/agent-client-protocol/agent-client-protocol
- Antigravity CLI: Google internal / agy-agent-acp
