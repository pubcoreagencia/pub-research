# Repo Evaluation: HeyGen Hyperframes (Avatar/Video Generation)

## Informações Básicas
- **Nome do Repo:** HeyGen Hyperframes (provavelmente SDK/API, não repo público open source completo)
- **URL:** https://github.com/heygen (org) / https://docs.heygen.com
- **Owner/Org:** HeyGen
- **Licença:** Proprietário (SaaS) — SDKs podem ser MIT/Apache
- **Data da avaliação:** 2026-09-19
- **Avaliador:** Genildo3000 / Matheus Paes (PUB REC)

## O que é / Para que serve
**HeyGen** = plataforma de geração de vídeo com avatares IA (lip-sync, text-to-video). **Hyperframes** parece ser uma feature/tech nova deles para geração de vídeo de alta qualidade/controlável (possivelmente geração frame-a-frame com consistência temporal).

**Nota:** HeyGen é SaaS proprietário. Não há repo open source completo do core. Eles têm SDKs (Node, Python) e API REST.

## Por que é relevante para a PUB
- **Lyric videos** automatizados com avatar cantando
- **Avatares personalizados** para artistas (digital twin)
- **Video generation** em escala para conteúdo social (Reels, TikTok, Shorts)
- **Localização** — mesmo vídeo em múltiplos idiomas com lip-sync nativo
- **Templates** para produção rápida de conteúdo visual musical

## Análise Técnica
| Aspecto | Avaliação (1-5) | Observações |
|---------|-----------------|-------------|
| Qualidade do vídeo | 5 | Estado da arte em avatar lip-sync |
| API/SDK | 4 | REST + Node/Python SDKs, webhooks |
| Latência | 3 | Geração assíncrona, minutos por vídeo |
| Custo | 2 | Pay-per-video, caro em volume alto |
| Controle criativo | 3 | Templates + alguns parâmetros, não total |
| Integração | 4 | API REST padrão, webhooks, callbacks |

## Dependências / Requisitos
- Conta HeyGen (plano pago para API)
- API Key
- Créditos de geração
- Para avatar custom: vídeo de treino (2 min falando)

## Prós
- Melhor lip-sync do mercado atualmente
- Avatares realistas, expressivos
- Suporte a múltiplos idiomas (30+)
- API bem documentada
- Webhooks para integração assíncrona
- Templates prontos (news, social, education)

## Contras / Riscos
- **Proprietário / SaaS** — vendor lock-in, sem controle do modelo
- **Custo alto** — ~$1-3/minuto de vídeo gerado
- **Latência** — geração assíncrona, não real-time
- **Limites de taxa** — rate limits na API
- **Sem open source** — não pode self-host, auditar, customizar core
- **Dependência de nuvem** — privacidade de dados (avatares, scripts)

## Alternativas Open Source (para monitorar)
- **SadTalker** — Talking face generation (open source)
- **Wav2Lip** — Lip-sync (open source)
- **LivePortrait** — Portrait animation (open source)
- **AnimateDiff** — Video generation (open source)
- **Stable Video Diffusion** — SVD (open source)
- **LTX Video** — Real-time video gen (open source, Lightricks)
- **CogVideoX** — Zhipu AI (open source)

## Decisão
- [ ] **Adotar** — Usar API para projetos específicos (cliente paga)
- [x] **Monitorar** — Acompanhar evolução + alternativas open source
- [x] **Referência** — Benchmark de qualidade para avaliar modelos open source
- [ ] **Descartar** — 

## Ações
- [ ] Testar API HeyGen com 1 vídeo piloto (lyric video)
- [ ] Benchmark: HeyGen vs SadTalker vs LivePortrait vs LTX Video
- [ ] Avaliar custo/benefício para produção em escala
- [ ] Se adotar: criar wrapper skill OpenClaw para HeyGen API

## Links
- HeyGen: https://www.heygen.com
- API Docs: https://docs.heygen.com
- GitHub Org: https://github.com/heygen
- SadTalker: https://github.com/OpenTalker/SadTalker
- LivePortrait: https://github.com/KwaiVGI/LivePortrait
- LTX Video: https://github.com/Lightricks/LTX-Video
