# Repo Evaluation: XP Audio Lab (Sound Design / VST / WebAudio Lab)

## Informações Básicas
- **Nome do Repo:** xp-audio-lab
- **URL:** https://github.com/pubcoreagencia/xp-audio-lab
- **Owner/Org:** pubcoreagencia
- **Licença:** Proprietário (private repo)
- **Linguagem principal:** TypeScript
- **Último commit:** 2026-09-19
- **Data da avaliação:** 2026-09-20
- **Avaliador:** Genildo3000 / Matheus Paes (PUB REC)

## O que é / Para que serve
**XP Audio Lab** = Laboratório de design de som experimental e plugins VST/WebAudio. Braço de R&D de áudio da PUB, conectado com PUB Records (DAW, beats, produção).

## Documentação Identificada
- `MASTER_CONTEXT.md` — Governança e arquitetura
- `PUB_GIT_CLOSURE_RULE.md` — Regra de fechamento Git

## Relevância para Research
- **WebAudio / Audio Worklets** — Audio processing no browser (baixa latência)
- **VST plugins** — Plugin development (JUCE, C++, VST3, CLAP)
- **WebAssembly audio** — DSP em WASM para performance
- **Sound design experimental** — Síntese, processamento, efeitos
- **DAW integration** — Bridge entre VST nativo e WebAudio (PUB DAW)
- **Audio plugins para produção musical** — EQ, compressão, saturação, spatial

## Tech Stack Provável (TypeScript + WebAudio)
- **Web Audio API** — AudioContext, AudioWorklet, AudioParam
- **WebAssembly** — Rust/C++ compilado para WASM (DSP pesado)
- **Worklet processors** — Thread separada para audio (não bloqueia main)
- **MIDI** — Web MIDI API para controllers
- **VST3 SDK** — Para plugins nativos (JUCE framework)

## Prós
- Foco em R&D de áudio (diferencial competitivo)
- Conexão direta com PUB Records/DAW
- WebAudio + WASM = performance nativa no browser
- TypeScript para tooling/UI, WASM para DSP

## Contras / Riscos
- Private repo
- Áudio no browser ainda tem limitações (latência, sample rate, buffer)
- VST development = C++/JUCE (stack diferente do TypeScript)
- Audio Worklets não suportados em todos browsers (Safari limitado)

## Decisão
- [x] **Adotar** — R&D de áudio core para PUB Records/DAW
- [x] **Institucionalizar** — Patterns → pub-research
- [ ] **Open source** — WebAudio utilities, WASM DSP helpers

## Ações de Integração
- [ ] Documentar WebAudio stack → `tools/webaudio-stack.md`
- [ ] Benchmark: WebAudio vs native VST vs JUCE
- [ ] Extrair AudioWorklet patterns → `tools/audio-worklet-patterns.md`
- [ ] WASM audio DSP → `tools/wasm-audio-dsp.md`
- [ ] Integrar com music_generate (OpenClaw) para stems/processing

## Links
- Repo: https://github.com/pubcoreagencia/xp-audio-lab (private)
- PUB Records: https://github.com/pubcoreagencia/pub-records
