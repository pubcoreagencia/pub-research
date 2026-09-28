# 🧠 PUB Research — Research Intelligence Engine

> **Propósito:** infraestrutura de pesquisa, captura, extração, análise, qualificação e persistência de inteligência para todo o ecossistema PUB e, progressivamente, para a holding.

PUB Research mantém o laboratório de componentes e integrações reutilizáveis, mas seu papel canônico agora inclui o Research Engine multicanal.

## O que é

- Research Engine multicanal
- Camada de inteligência para todo o ecossistema PUB
- Evidência bruta separada de interpretação de IA
- Arquitetura baseada em source adapters
- Destino-agnóstico

Não é um scraper específico de Instagram, uma fonte exclusiva para PP/PDL ou um arquivo morto de links.

## Primeira aplicação

Instagram é o primeiro caso de uso porque corresponde ao fluxo atual de pesquisa humana: encontrar algo relevante e compartilhar o post em um grupo dedicado. Isso não limita o sistema.

Fontes previstas: Instagram, GitHub, YouTube, Reddit, Web/Search, News, Documentation e futuras fontes aprovadas.

## Fluxo canônico

```
SOURCE → CAPTURE → EXTRACT → NORMALIZE → ANALYZE → QUALIFY → PERSIST
→ PUB NEURAL / ECOSYSTEM CONSUMERS
→ SUGGESTION / DECISION / IMPLEMENTATION
→ OBSERVED RESULT → NEW RESEARCH SIGNAL
```

Pesquisa humana e pesquisa autônoma convergem para o mesmo Research Engine.

## Pesquisa multimodal

Quando legitimamente acessível, a captura pode preservar texto, caption, hashtags, mentions, autor, timestamp, tipo de publicação, imagens, carrosséis, vídeo/reels, áudio, transcrição, OCR, descrição visual, entidades, produtos, marcas, ofertas, CTAs, links e metadados visíveis.

A evidência original deve permanecer distinguível da interpretação derivada por IA.

## Proveniência

```
SOURCE URL → CAPTURE → RAW EVIDENCE → OCR / TRANSCRIPTION
→ AI ANALYSIS → QUALIFICATION → DOWNSTREAM SUGGESTION
→ IMPLEMENTATION / VALIDATION
```

Credenciais, cookies, tokens de sessão e outros segredos não pertencem aos Research Items. O sistema deve respeitar permissões e limites de acesso e não contornar autenticação, CAPTCHA ou outros controles.

## Research Item

Contrato conceitual: source, source_type, url, author, timestamp, raw_content, media, transcript, ocr, entities, topics, claims, products, brands, insights, opportunities, relevance, qualification, provenance e downstream_candidates.

Idempotência deve usar identificador estável da fonte quando disponível, com URL normalizada como fallback.

Estados: RECEIVED → OPENING → CAPTURED → EXTRACTING → ANALYZING → QUALIFYING → COMPLETED, com PARTIAL / BLOCKED / FAILED / RETRYING para exceções.

## Source Adapters

```
Research Engine
├── Instagram Adapter
├── GitHub Adapter
├── YouTube Adapter
├── Reddit Adapter
├── Web/Search Adapter
├── News Adapter
├── Documentation Adapter
└── Future approved adapters
```

Cada adapter traduz a fonte para o contrato comum de Research Item e preserva evidências específicas da fonte.

## Destino-agnóstico

Uma descoberta pode alimentar PUB Neural, PP / Prototype, PDL / Dev Loop, PUB Ecom, PUB Leads, PUB IA, PUB ACP, PUB 9Router, PUB Machine, PUB Records, marcas da holding, infraestrutura compartilhada ou novos produtos e ventures.

PUB Research é uma camada de inteligência do ecossistema, não um pipeline de um produto específico.

## Autonomia progressiva

MVP: compartilhar uma fonte → captura automática → extração multimodal → persistência de Research Item completo e rastreável.

Depois: missão → descoberta → captura → extração → análise → qualificação → persistência → novas perguntas.

Governança: Evidence → Research → Qualification → Suggestion → Human / governed authorization → Implementation → Validation.

## Feedback loop

Research → Suggestion → Implementation → Production Result → Observed Outcome → New Research Signal → Research.

## Estrutura

```
pub-research/
├── components/
├── integrations/
├── decisions/
├── benchmarks/
├── templates/
├── docs/
└── INDEX.md
```

O contexto canônico está em docs/INSTAGRAM-RESEARCH-AUTONOMY-MASTER-CONTEXT.md.

## Governança

1. Evidência e interpretação devem ser distinguíveis.
2. Descobertas importantes devem manter proveniência.
3. Segredos não devem ser persistidos como pesquisa.
4. Acesso automatizado deve respeitar os limites legítimos da fonte.
5. Decisões de adoção permanecem rastreáveis.
6. Pesquisa pode alimentar qualquer parte do ecossistema.
7. Autonomia deve crescer de forma governada e auditável.
8. O Research Engine deve privilegiar evidência verificável.

*PUB Research — inteligência de pesquisa para o ecossistema PUB e, progressivamente, para a holding.*