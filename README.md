<div align="center">

# ModelAtlas - the open-source AI model directory (2026 edition)

### Every important open-weight and open-source AI model in one directory: LLMs, MoE, reasoning, coding, vision, image, video, audio, TTS/ASR, embeddings, 3D, agents, licenses, VRAM guides, benchmarks - plus free API tiers and one-command local installs

[![License: CC BY 4.0](https://img.shields.io/badge/Document-CC--BY--4.0-lightgrey.svg)](LICENSE)
![Last updated](https://img.shields.io/badge/Last%20updated-2026--09--09-2ea44f)
![Models covered](https://img.shields.io/badge/Models%20covered-101-2ea44f)
![Version](https://img.shields.io/badge/Version-2026.09-blue)
[![Hugging Face](https://img.shields.io/badge/Models-Hugging%20Face-yellow)](https://huggingface.co)
[![Ollama](https://img.shields.io/badge/Run-Ollama-2ea44f)](https://ollama.com/library)
[![Arena](https://img.shields.io/badge/Elo-Arena%20Leaderboard-blue)](https://arena.ai/leaderboard)

**A student-teacher fellowship project.** We are a small group of students and teachers who keep a public, living list of open AI models - what exists, which one to pick, and how to run it. Last full pass: 2026-09-09. Compare, decide, download, run, ship.

**New here?** Start with the [Quick answers](#quick-answers) below, or read [who we are and why this exists](#1-about-modelatlas-and-the-team-behind-it). Programs can read the same content via [`llms.txt`](llms.txt) and [`data/models.json`](data/models.json).

</div>

---

## Quick answers

> **What is the best open-source AI model right now (Sept 2026)?**
> — **DeepSeek V4-Pro** (1.6T MoE / 49B active, MIT, 1M context, open weights since Aug 2026) and **Qwen3.8-2.4T-A95B** (Alibaba's 2.4T open-weight flagship) lead the overall frontier. **GLM-5.2** (744B, MIT, 1M ctx) and **Kimi K2.6** (1T, Modified MIT) lead coding/agents. On a single GPU: **Gemma 4 31B**, **Qwen3.8-27B**. On a laptop: **Phi-4-mini**, **gpt-oss-20b**, **Gemma 4 E4B**.

> **Can I run an LLM for free, locally?** Yes — Ollama one-liners for every model here (§17). CPU-only works for 1B–8B models.
> **Where can I get free AI APIs?** Google AI Studio, Groq, Cerebras, GitHub Models, Cloudflare Workers AI, OpenRouter's `:free` models and Hugging Face Inference all have real free tiers - the [full table with links](#where-to-get-free-ai-apis-sept-2026) is right below the Table of contents.

> **Which open models are safe for commercial products?** Apache 2.0 (Qwen, Gemma 4, gpt-oss, Mistral, Wan, Z-Image, FLUX.2 klein…) and MIT (DeepSeek, GLM, Phi, Kimi*). Always read the license — §20 explains every trap (MAU caps, revenue clauses, NC-only weights).

---

## Table of contents

| § | Section | § | Section |
|---|---|---|---|
| [1](#1-about-modelatlas-and-the-team-behind-it) | About & how to read | [13](#13-embeddings-rerankers-and-rag) | Embeddings, rerankers & RAG |
| [2](#2-the-2026-open-model-landscape-in-one-page) | 2026 landscape at a glance | [14](#14-3d-generation) | 3D generation |
| [3](#3-quick-picks-by-need) | Quick picks by need | [15](#15-agents-frameworks-fine-tuning-and-tooling) | Agents, fine-tuning & tooling |
| [4](#4-frontier-llm-families) | Frontier LLM families (A–Z) | [16](#16-hardware-vram-and-ram-quantization-guide) | Hardware, VRAM & RAM |
| [5](#5-reasoning-models) | Reasoning models | [17](#17-how-to-download-and-run-locally) | Download & run locally |
| [6](#6-coding-and-agentic-models) | Coding & agentic models | [18](#18-which-model-should-you-use-decision-guides) | Decision guides |
| [7](#7-vision-language-models) | Vision-language models | [19](#19-where-to-explore-models-hubs-and-leaderboards) | Hubs & leaderboards |
| [8](#8-image-generation) | Image generation | [20](#20-open-source-licenses-explained) | Licenses explained |
| [9](#9-video-generation) | Video generation | [21](#21-glossary-of-ai-model-terms) | Glossary |
| [10](#10-audio-and-music-generation) | Audio & music generation | [22](#22-faq-frequently-asked-questions) | FAQ |
| [11](#11-text-to-speech-and-voice) | Text-to-speech & voice | [23](#23-resources-and-references) | Resources & references |
| [12](#12-speech-to-text-asr) | Speech-to-text / ASR | [24](#24-disclaimer-version-notes-and-contributing) | Disclaimer & version notes |

**Appendices:** [A. Benchmarks & methodology](#appendix-a-benchmarks-and-methodology-explained) · [B. Repo engineering](#appendix-b-how-this-guide-is-organized-and-kept-current) · [C. Realtime voice & omni](#appendix-c-realtime-voice-omni-and-speech-to-speech-models) · [D. Document AI & OCR](#appendix-d-document-ai-ocr-and-pdf-tools) · [E. Free API tiers](#appendix-e-free-and-low-cost-api-tiers-for-testing-open-models) · [F. GPU buying guide](#appendix-f-gpu-and-hardware-buying-guide) · [G. Changelog](#appendix-g-changelog)

**Jump to:** [Free AI APIs](#where-to-get-free-ai-apis-sept-2026) · [Browse by category](#categories-covered-14-categories-101-models) · [Summer 2026 release wave](#summer-2026-release-wave-by-category) · [Who is behind this](#1-about-modelatlas-and-the-team-behind-it)

---

## Where to get free AI APIs (Sept 2026)

Every few weeks someone in the group asks which AI APIs are actually free, so we keep this table instead of answering the same question five times. These are the tiers we could sign up for **without a card** (or with a small one-time trial) as of September 2026 — limits move often, so the link in the last column is the official pricing page, not our memory of it.

| Provider | What you get free | Rough limits (Sept 2026, verify) | Official page |
|---|---|---|---|
| **Google AI Studio** (Gemini API) | Gemini Flash-class models, generous free tier for developers | daily rate caps, vary by model | [aistudio.google.com](https://aistudio.google.com) |
| **OpenRouter** | `:free` models from many providers (Llama, Qwen, DeepSeek R1, etc.) | ~20 req/min, ~50 req/day without credits | [openrouter.ai](https://openrouter.ai) |
| **Groq** | Llama 3.x, Qwen, gpt-oss and others on LPU hardware | ~30 RPM, thousands of requests/day (varies) | [console.groq.com](https://console.groq.com) |
| **Cerebras** | Llama-class models on the CS-3 wafer cluster | similar free caps | [cloud.cerebras.ai](https://cloud.cerebras.ai) |
| **GitHub Models** | Playground + sandboxed API for open models (gpt-oss, Llama, Mistral, Qwen) | rate-limited, no production use | [github.com/marketplace/models](https://github.com/marketplace/models) |
| **Cloudflare Workers AI** | Llama/Qwen serverless inference at the edge | ~10,000 neurons/day free | [developers.cloudflare.com/workers-ai](https://developers.cloudflare.com/workers-ai/) |
| **Hugging Face Inference** | Serverless endpoints for small open models | small monthly credit (~$0.10) | [huggingface.co/pricing](https://huggingface.co/pricing) |
| **Mistral (La Plateforme)** | Free Codestral developer key | ~30 req/min on coding models | [console.mistral.ai](https://console.mistral.ai) |
| **NVIDIA NIM** | Hosted open-model APIs (Llama, Nemotron, Qwen) | developer credits on sign-up | [build.nvidia.com](https://build.nvidia.com) |
| **Cohere** | Trial key for Command / RAG experiments | roughly 1,000 calls/month | [dashboard.cohere.com](https://dashboard.cohere.com) |
| **Together / Fireworks** | One-time trial credits (~$1) | limited, then pay-as-you-go | [together.ai](https://www.together.ai) · [fireworks.ai](https://fireworks.ai) |
| **DeepSeek** | No permanent free tier (occasional promos) | pay-as-you-go, cheapest frontier tokens | [platform.deepseek.com](https://platform.deepseek.com) |

**Also free, per category:**
- **Embeddings:** Google (via AI Studio) and Cohere trial keys; open ones run free locally — [Qwen3-Embedding / BGE-M3 §13](#13-embeddings-rerankers-and-rag).
- **Speech (ASR/TTS):** Groq and HF Inference serve Whisper-class models on the free tier; [Kokoro §11](#11-text-to-speech-and-voice) runs on a laptop.
- **Images:** HF Inference free tier covers small diffusion models; big ones need a GPU ([§16](#16-hardware-vram-and-ram-quantization-guide)).

**Three honest caveats.** (1) Free tiers are for development, not production — rate caps and uptime are not guaranteed. (2) Some free tiers train on your data or store prompts; check the terms before sending anything sensitive (we mark the ones we know about in [§20](#20-open-source-licenses-explained)). (3) The actually-unlimited option is still local: every model marked 🦙 in [§17](#17-how-to-download-and-run-locally) runs on your own machine for $0 per token.

---

## 1. About ModelAtlas and the team behind it
ModelAtlas is an open, **single-file reference to the entire open-weight AI ecosystem** — maintained so that anyone — developer, student, CTO, researcher, hobbyist — can answer three questions in minutes:

1. **What exists?** Every important open model family, with links to canonical sources.
2. **Which one for my job?** Decision guides by task, hardware, license and budget (§3, §18).
3. **How do I get it running?** Copy-paste Ollama/llama.cpp/vLLM commands (§17), VRAM math (§24), and production notes (§6, §15).

**Scope:** open-weight and open-source generative AI: language, reasoning, coding, vision, image, video, audio/music, speech, embeddings, 3D, and the agent stack around them. Proprietary APIs are referenced only as comparison points.

### Who we are

ModelAtlas is written by a **student-teacher research fellowship** — students who like open models, and teachers who make sure we do not embarrass ourselves. We have no company, no sponsors, and nothing to sell; we built this because we needed it for our own projects and coursework. You can read the longer version on the [About page](ABOUT.md), and the short version is: a rotating pair of student editors runs each weekly review, and a teacher checks the work before it is published. If something is wrong, tell us — the issue tracker is the fastest way to make this page better.

### How we check our facts

- Every model links to its **original source** — model card, repository, or paper — and the link is tested when we add it.
- A number we have **not** re-measured ourselves is labelled *vendor-reported* `(v.r.)`. When a vendor score looks too good, we say so.
- Every snapshot carries a date, and the [changelog](CHANGELOG.md) records what changed between versions.
- Student editors draft, a mentor reviews, a different student spot-checks links — nothing ships on a single pair of eyes.

### About this edition

This is the **2026 edition (version 2026.09)** — a single-file directory with machine-readable twins, published under CC-BY-4.0 (each model keeps its own license). We plan one full review pass per week; the automated reminder lives in [`.github/workflows/refresh.yml`](.github/workflows/refresh.yml).

### Features at a glance

- **101 models tracked** in a machine-readable registry ([`data/models.json`](data/models.json) + `.csv`), across **14 categories** and 20+ families — every major open release with org, params, context, license, release date, canonical links and Ollama tags.
- **Chapters 1-24 plus seven appendices**, ordered so the broad answer comes first and headings read like real questions.
- **Comparison tables** everywhere a list of specs beats a paragraph — and every number we did not measure ourselves is marked `(v.r.)`.
- **One-command local install** for every Ollama-served model (§17), GGUF/VRAM sizing per tier, plus vLLM/SGLang/llama.cpp production notes (§15).
- **License fast-pass** (§20): commercial use, MAU caps, revenue triggers and NC-only weights, with a license column on every model table.
- **VRAM & RAM calculator, GPU matrix and decision guides** by task, hardware and budget (§3, §16, §18, Appendix F).
- **Free AI API tiers** with sign-up links — [see the table](#where-to-get-free-ai-apis-sept-2026).
- **Plain-data copies:** `llms.txt` for AI assistants, JSON/CSV registry with per-category breakdown, [changelog](CHANGELOG.md), weekly refresh workflow, and a short [About page](ABOUT.md).

### Categories covered (14 categories · 101 models)

| Category | Models | Registry tag | Deep dive | What's inside |
|---|--:|---|---|---|
| Frontier LLMs (dense + MoE) | 33 | `llm` | [§4](#4-frontier-llm-families) | DeepSeek V4 family, Qwen3.5/3.6/3.8, GLM-5.2/4.7, Kimi K2.6/K2.7, Llama 4, Mistral Large 3, Gemma 4, gpt-oss, MiniMax M2.5, Hunyuan Hy3, MiMo-V2, Seed-OSS, Phi-4, Granite, OLMo, SmolLM, Falcon, Sarvam, MiniCPM5 |
| Reasoning models | 7 | `reasoning` | [§5](#5-reasoning-models) | DeepSeek-R1 + distills, gpt-oss-120b/20b, Phi-4-Reasoning, Magistral Small, Seed-OSS-36B |
| Coding & agentic models | 4 | `coding` | [§6](#6-coding-and-agentic-models) | Kimi K2.7-Code, Qwen3-Coder family, Devstral Small 2, GLM-4.7 |
| Vision-language models | 6 | `vlm` | [§7](#7-vision-language-models) | Qwen3-VL / 2.5-VL, DeepSeek V4-Flash-Vision, MiniMax M2, UI-TARS, InternVL3, Llama 4 |
| Image generation | 7 | `image` | [§8](#8-image-generation) | Qwen-Image-2512, FLUX.2 [dev/klein], Z-Image-Turbo, GLM-Image, SD 3.5, HunyuanImage |
| Video generation | 7 | `video` | [§9](#9-video-generation) | Wan 2.2/2.5, LTX-2.5, MiniMax H3 (Hailuo 3.0), HunyuanVideo 1.5, CogVideoX, Mochi, Open-Sora |
| Music & audio generation | 3 | `music` | [§10](#10-audio-and-music-generation) | MusicGen, Stable Audio Open, ACE-Step 1.5 |
| Text-to-speech & voice | 7 | `tts` | [§11](#11-text-to-speech-and-voice) | Qwen3-TTS, Kokoro, Chatterbox, CosyVoice 3, F5-TTS, Piper, VibeVoice |
| Speech-to-text / ASR | 7 | `asr` | [§12](#12-speech-to-text-asr) | Whisper large-v3/turbo, Qwen3-ASR, Parakeet, Canary, Moonshine, Vosk, WhisperX |
| Embeddings, rerankers & RAG | 8 | `embedding` + `reranker` | [§13](#13-embeddings-rerankers-and-rag) | Qwen3-Embedding, BGE-M3, NV-Embed, nomic, gte-Qwen3, mxbai, rerankers (BGE, Qwen3) |
| 3D generation | 5 | `model3d` | [§14](#14-3d-generation) | Hunyuan3D 2.x, TRELLIS.2, TripoSR, Stable Fast 3D, SAM 3D |
| Realtime voice / omni (speech-to-speech) | 5 | `omni` | [Appendix C](#appendix-c-realtime-voice-omni-and-speech-to-speech-models) | Qwen2.5-Omni, GLM-4-Voice, Kimi-Audio, Step-Audio, MiniCPM-o |
| Document AI & OCR | 2 | `ocr` | [Appendix D](#appendix-d-document-ai-ocr-and-pdf-tools) | olmOCR, GOT-OCR2 (tools: MinerU, Marker, Surya, ColPali…) |
| Agents, frameworks & tooling | — | — | [§15](#15-agents-frameworks-fine-tuning-and-tooling) | MCP, OpenHands, LangGraph, vLLM/SGLang/llama.cpp serving stack |

> Counts auto-generated from `data/models.json` (registry 101 models); the 14 registry tags are `llm, reasoning, coding, vlm, image, video, music, tts, asr, embedding, reranker, model3d, omni, ocr`.

### How this page is structured

- **Headline answer first:** the broadest answer is at the top (§2), the detail follows — a quick skim is enough for most readers.
- **Headings read like questions people actually ask** ("What is the best open-source LLM in 2026?", "How much VRAM do I need?") — skimming the headings already answers most of them.
- **Numbers live in tables**, not paragraphs — a grid of specs is easier to compare than prose.
- **Original sources first:** every model links to its card, repository or paper; anything we could not verify ourselves is marked *vendor-reported* `(v.r.)`.
- **The same content for programs:** [`llms.txt`](llms.txt) for AI assistants, [`data/models.json`](data/models.json) + [`data/models.csv`](data/models.csv) for dashboards, and a [repo map](docs/README.md) for maintainers.

### Versioning and freshness

| Field | Value |
|---|---|
| Edition | 2026 Edition (version 2026.09) |
| Last verified | 2026-09-09 |
| Next scheduled refresh | automated weekly via [GitHub Actions](.github/workflows/refresh.yml) |
| Snapshot policy | the field moves monthly; this is a point-in-time snapshot, vendor numbers are vendor numbers |

---

## 2. The 2026 open-model landscape in one page

Rankings below are **vendor-reported + public leaderboard snapshots** (Arena Elo, Artificial Analysis, SWE-bench Verified, MTEB) — see [Appendix A](#appendix-a-benchmarks-and-methodology-explained) for methodology and §19 for live boards. **Always verify on the live leaderboard before a big bet.**

### Top open-weight LLMs (Sept 2026 snapshot)

| Model (family) | Org | Params (total / active) | Context | License | Standout |
|---|---|---|---|---|---|
| **DeepSeek V4-Pro 0813** | DeepSeek | 1.6T / 49B MoE | 1M | MIT | Overall frontier king (Aug 2026 GA, open weights) |
| **Qwen3.8-2.4T-A95B** | Alibaba (Qwen) | 2.4T / 95B MoE | 262K–1M | Qwen3.8-Max license | Largest open release; open twin of Qwen3.8-Max |
| **Kimi K2.6** | Moonshot AI | 1T / 32B MoE | 262K | Modified MIT | Long-horizon agents, image+video input |
| **Kimi K2.7 Code** | Moonshot AI | 1T / 32B MoE | 256K | Modified MIT | Coding specialist: +21.8% Kimi Code Bench v2, -30% reasoning tokens (Jun 2026) |
| **GLM-5.2** | Z.ai (Zhipu) | 744B MoE | 1M | MIT | Coding + 1M-ctx agentic engineering |
| **Qwen3.5** | Alibaba (Qwen) | 397B / 17B MoE | 1M | Apache 2.0 | Agentic flagship (Feb 2026); image+video native |
| **Qwen3.6-35B-A3B** | Alibaba (Qwen) | 35B / 3B MoE | 256K | Apache 2.0 | Apr 2026 open release, vision included |
| **Mistral Large 3** | Mistral | 675B / 41B MoE | 256K | Apache 2.0 | Best open multilingual+multimodal from Europe |
| **Llama 4 Maverick** | Meta | 402B MoE | 1M | Llama 4 Community | Meta's flagship (Behemoth still training) |
| **Llama 4 Scout** | Meta | 109B / 17B MoE | 10M | Llama 4 Community | World-record context, single-GPU MoE |
| **DeepSeek V3.2 / V3.2-Speciale** | DeepSeek | 685B MoE | 128K | MIT | Proven workhorse, huge ecosystem |
| **Qwen3-235B-A22B** | Alibaba (Qwen) | 235B / 22B MoE | 128K+ | Apache 2.0 | The best-documented MoE to self-host |
| **Gemma 4 31B** | Google | 31B dense | 128K+ | Apache 2.0 | Frontier quality on one GPU (~18 GB Q4) |
| **MiniMax M2.5** | MiniMax | ~200B MoE | ~200K | MiniMax license | Feb 2026; SWE-bench ~80 (v.r.) |
| **Hunyuan Hy3** | Tencent | 295B / 21B MoE | 256K | Apache 2.0 | Open-weight reasoning/agents (Jul 2026) |
| **MiMo-V2-Flash** | Xiaomi | MoE | 256K | MIT | Surprise efficiency leader |
| **gpt-oss-120b** | OpenAI | 117B / 5.1B MoE | 131K | Apache 2.0 | OpenAI's open reasoning model |
| **Sarvam 105B** | Sarvam AI | 105B MoE | 128K | Sarvam license | India's Indic-language frontier |
| **Seed-OSS-36B** | ByteDance | 36B dense | 32K | Apache 2.0 | ByteDance's open thinking model (Aug 2025) |
| **GLM-4.7** | Z.ai | 355B / 32B MoE | 128K+ | MIT | Production-proven coding/agent MoE |

### Fastest movers this quarter (Apr-Sep 2026 timeline)

| Date | Event |
|---|---|
| 2026-02-03 | Qwen3-Coder-Next (open, agentic SWE) |
| 2026-02-16 | Qwen3.5 (397B, Apache 2.0, 1M ctx, agentic) |
| 2026-04-02 | Gemma 4 family (Apache 2.0; E2B→31B) |
| 2026-04-16 | Qwen3.6 open release (Apache 2.0) |
| 2026-04-20 | Kimi K2.6 open weights (Modified MIT) |
| 2026-06-12 | Kimi K2.7-Code open weights (1T, Modified MIT, coding-specialist) |
| 2026-06-13 | GLM-5.2 (744B, MIT, 1M ctx) — open within a week of preview |
| 2026-07-06 | Hunyuan Hy3 open weights (295B MoE, Apache 2.0) |
| 2026-07-23 | LTX-2.5 open weights (22B video+audio, 4K/20s) |
| 2026-07-31 | DeepSeek V4-Flash open weights (MIT) |
| 2026-08-03 | Qwen3.8-Max announcement; Qwen3.8-27B (Apache 2.0) |
| 2026-08-12 | Qwen3.8-2.4T-A95B open weights |
| 2026-08-13 | DeepSeek V4-Pro-0813 GA + open weights (1.6T, MIT, 1M ctx) |
| 2026-08-31 | DeepSeek V4-Flash-Vision-Exp weights (305B multimodal MoE, MIT) |

> ℹ️ **Missing from many lists:** Google's Gemma 4 went **Apache 2.0** (a big license step up from Gemma 3), and OpenAI's **gpt-oss** family remains its only open line (no "gpt-oss-2" as of this snapshot).

### Summer 2026 release wave, by category

What actually shipped open-weight between June and August 2026, grouped by category (deep dives in the linked sections). Dates verified against release notes; scores are `(v.r.)`.

| Category | Release | Date | License | Why it matters |
|---|---|---|---|---|
| **Frontier LLM / MoE** | **GLM-5.2** (744B, 1M ctx) | Jun 13 | MIT | Coding/agent frontier open within a week of preview; 282-shard release |
| **Frontier LLM / MoE** | **Kimi K2.7-Code** (1T/32B) | Jun 12 | Modified MIT | Coding specialist: +21.8% Kimi Code Bench v2, −30% reasoning tokens (v.r.) |
| **Frontier LLM / MoE** | **Hunyuan Hy3** (295B/21B) | Jul 6 | Apache 2.0 | Tencent's open reasoning/agent MoE with `reasoning_effort` control |
| **Frontier LLM / MoE** | **DeepSeek V4-Flash** | Jul 31 | MIT | Fast/cheap tier of the V4 family open-weighted |
| **Frontier LLM / MoE** | **Qwen3.8-Max** family: **27B** (Aug 3) + **2.4T-A95B** (Aug 8) | Aug | Apache (27B) / custom (2.4T) | Alibaba's largest-ever open release |
| **Frontier LLM / MoE** | **DeepSeek V4-Pro-0813** (1.6T/49B act.) | Aug 13 | MIT | GA refresh + open weights, 1M ctx |
| **Vision-language** | **DeepSeek V4-Flash-Vision-Exp** (305B MoE) | Aug 31 | MIT | Open multimodal sibling of V4-Flash |
| **Video + audio** | **LTX-2.5** (22B) | Jul 23 | LTX Community | 4K/20s generation with native audio in one DiT |
| **Image generation** | — | — | — | Quiet quarter: Qwen-Image-2512 and FLUX.2 [klein] stayed the open picks (v.r.) |
| **TTS / voice** | — | — | — | Ecosystem matured around Qwen3-TTS / Kokoro / Chatterbox; no new top-tier release (v.r.) |
| **Edge / on-device** | **MiniCPM5-1B** (May 21) and **MiniCPM5-2B** (Sep 6) | May–Sep | Apache 2.0 | OpenBMB edge family now 1B–2B with tool calling |
| **Document AI / OCR** | incremental | Jun–Aug | — | olmOCR/MinerU pipelines kept pace (v.r.); no frontier-scale drop |

**Ecosystem context (Aug 14, 2026, HF State-of-Open-Models report):** 178 open releases above 20B params came from Chinese labs in 2026 so far — 59% Apache-2.0, 22% MIT — while a new wave of license restrictions appeared on the largest releases (Kimi K3 terms, Qwen3.8-2.4T revenue share). Details in [§20](#20-open-source-licenses-explained) and the [full changelog](CHANGELOG.md).

---

## 3. Quick picks by need

| If you need… | Pick | Why |
|---|---|---|
| Best overall, self-hosted | **DeepSeek V4-Pro** · **Qwen3.8-2.4T** | Frontier reasoning + coding at open cost |
| Best license-friction-free | **Qwen3.8-27B** · **Gemma 4 31B** · **gpt-oss-120b** | Apache 2.0, no strings |
| Best coding / agentic | **GLM-5.2** · **Kimi K2.6** · **DeepSeek V4** · **Qwen3-Coder** | SWE-bench Verified + tool-use leaders |
| Deep chain-of-thought | **DeepSeek R1 / R1-0528** · **Qwen3** · **Magistral Small** | Self-correcting math/reasoning |
| Massive context (docs/repos) | **Llama 4 Scout (10M)** · **GLM-5.2 / DeepSeek V4 (1M)** | Longest windows |
| Multilingual product | **Mistral Large 3** · **Qwen3** · **Sarvam** | 100+/201 languages |
| One consumer GPU (24 GB) | **Qwen3.8-27B** · **Gemma 4 31B** | Q4 fits ~18–22 GB |
| Laptop / edge / CPU | **Phi-4-mini** · **gpt-oss-20b** · **Gemma 4 E4B** · **SmolLM3** | 3–21B, low RAM |
| Local coding agent | **Devstral** · **Qwen3-Coder** · **Cline/OpenHands stack** | Agentic SWE workflows |
| GDPR / EU residency | **Mistral Large 3** · **Qwen3** | Apache + EU provider options |
| Fully open (data+code+weights) | **OLMo 2** · **SmolLM3** · **Pythia** | Open-everything research lineage |
| Best free image gen | **Qwen-Image-2512** (Apache 2.0) | Leader of open arena, clean license |
| Best free video gen | **Wan 2.2** (Apache 2.0) | No license caps |
| Best open TTS | **Kokoro** (CPU!) · **Qwen3-TTS** (clone, 3 s) | Speed + voice cloning |
| RAG embeddings | **Qwen3-Embedding-8B** · **BGE-M3** | MTEB leaders, self-host |
| 3D assets | **Hunyuan3D 2.x** · **TRELLIS.2** | Best open mesh/PBR pipelines |

---

## 4. Frontier LLM families

> Every family links to its canonical **Hugging Face org / GitHub**. Numbers marked *(v.r.)* = vendor-reported. Full machine-readable registry: [`data/models.json`](data/models.json).

### 4.1 DeepSeek (China 🇨🇳 · MIT) - [GitHub](https://github.com/deepseek-ai) · [HF](https://huggingface.co/deepseek-ai) · [API](https://platform.deepseek.com)

The lab that reset open-AI economics in 2025 (R1) and kept going. V4 generation went fully open in summer 2026.

| Model | Type | Params | Context | License | Notes |
|---|---|---|---|---|---|
| **V4-Pro-0813** | MoE | 1.6T / 49B act. | 1M | MIT | GA Aug 13 2026; open weights on HF; 384K max output; reasoning efforts low/high/max |
| **V4-Flash-0731** | MoE | open-weight tier | 128K+ | MIT | Jul 31 2026; cheap fast tier; API in beta at release |
| **V4-Flash-Vision-Exp** | Multimodal MoE | 305B | — | MIT | First V4 vision model; weights Aug 31 2026 (FP8) |
| **V3.2 / V3.2-Speciale** | MoE | 685B | 128K | MIT | Production workhorse of 2025–26 |
| **R1-0528** | MoE (reasoning) | 671B / 37B | 128K | MIT | Open reasoning legend; the model that broke pricing |
| **R1-Distill (Qwen/Llama)** | Dense distills | 1.5B–70B | 128K | MIT | Run reasoning on a laptop |

- **API (hosted):** among the cheapest frontier APIs; prices change with time-of-day since Aug 2026 (~$0.66–1.32/M in, $1.98–3.96/M out, provider-dependent, cache ~$0.02–0.35/M). Data routes through China — check TOS for sensitive workloads (§24 caveats).
- **Vibe:** MIT + open weights + published training tech (MLA, DSA sparse attention, FP8) — the "open by default" lab.

### 4.2 Qwen (Alibaba 🇨🇳 · Apache 2.0) - [GitHub](https://github.com/QwenLM) · [HF](https://huggingface.co/Qwen) · [ModelScope](https://modelscope.cn/organization/qwen) · [Bailian API](https://www.alibabacloud.com/product/bailian)

The most prolific open lab on earth — language, coder, vision, image, video, audio, embeddings, TTS/ASR. Qwen3.5/3.6 (Apache 2.0) then the Qwen3.8 generation (Aug 2026): 27B under Apache 2.0, 2.4T under a custom license.

| Model | Type | Params | Context | License | Notes |
|---|---|---|---|---|---|
| **Qwen3.8-2.4T-A95B** | MoE | 2.4T / 95B act. (512 experts) | 262K–1M | Qwen3.8-Max license | Open twin of Qwen3.8-Max; hybrid Gated-DeltaNet attention; 92 layers |
| **Qwen3.8-27B** | Dense | 27B | 262K+ | Apache 2.0 | Flagship-per-GPU; `ollama pull qwen3.8:27b` |
| **Qwen3.8-Flash / Next** | MoE | — | 1M | custom / Apache | Speed-optimized tiers (API-first) |
| **Qwen3.6-35B-A3B** | MoE | 35B / 3B act. | 256K | Apache 2.0 | Apr 2026; small flagship, image/video input |
| **Qwen3.5-397B-A17B** | MoE | 397B / 17B | 1M | Apache 2.0 | Agentic era: visual computer-use; image+video input; HF: `Qwen/Qwen3.5-397B-A17B` |
| **Qwen3.5-9B / 4B** | Dense | 4B-9B | 256K | Apache 2.0 | Small multimodal agentic models (Mar 2026) |
| **Qwen3** | Dense+MoE | 0.6B–235B (A22B) | 32K–256K | Apache 2.0 | 201 languages, thinking mode, 128K base — the safest default in this list |
| **Qwen3-Coder / Next** | MoE | 30B–480B | 256K | Apache 2.0 | Open coding/agent family; "Next" added IDE-grade tool use |
| **Qwen2.5 legacy** | Dense | 0.5B–72B | 128K | Apache 2.0 | Still the most-fine-tuned family on HF |

- **Vibe:** Apache 2.0 everywhere possible; flagship scale open weeks after API; huge ecosystem (GGUF everywhere, fine-tunes by the thousand).

### 4.3 Z.ai / Zhipu GLM (China 🇨🇳 · MIT) - [GitHub](https://github.com/zai-org) · [HF](https://huggingface.co/zai-org) · [API](https://z.ai)

China's oldest LLM lab (since 2019) and the team that open-sourced GLM-4.7 (2025) then GLM-5/5.2 (2026).

| Model | Type | Params | Context | License | Notes |
|---|---|---|---|---|---|
| **GLM-5.2** | MoE | 744B | 1M | MIT | Jun 13 2026; open weights BF16+FP8 same week; 1M-ctx agentic coding; API + Coding Plan |
| **GLM-5** | MoE | ~745B | 200K–1M | MIT | Feb 2026; frontier reasoning/agent claims; Ascend-trained (US-independent supply chain) |
| **GLM-5-Flash** | MoE | — | 128K+ | MIT | Cheap/fast tier |
| **GLM-4.7** | MoE | 355B / 32B | 128K | MIT | The proven 2025–26 agentic workhorse |
| **GLM-4.5/4.6** | MoE | 355B | 128K | MIT | Earlier open gens |
| **GLM-4.5V / 4.6V** | VLM | 40B+ | 128K | MIT | Document/UI vision agents |

- **Vibe:** MIT (maximally permissive) + day-one open weights + aggressive API pricing (Flash tier ~$0.11/M out-class at points in 2026).

### 4.4 Moonshot Kimi (China 🇨🇳 · Modified MIT) - [GitHub](https://github.com/MoonshotAI) · [HF](https://huggingface.co/moonshotai) · [API](https://platform.moonshot.ai)

| Model | Type | Params | Context | License | Notes |
|---|---|---|---|---|---|
| **Kimi K2.7-Code** | MoE | 1T / 32B act. | 256K | Modified MIT | Jun 12 2026; coding-specialist; +21.8% Kimi Code Bench v2, ~30% fewer reasoning tokens (v.r.); ~595GB weights; ships with the Kimi Code terminal agent |
| **Kimi K2.6** | MoE | 1T / 32B act. | 262K | Modified MIT | Apr 20 2026; native multimodal (text+image+video); ties/beats GPT-5.5-class on SWE-bench Pro (v.r.); 300-agent "swarm" research |
| **Kimi K2.5 / K2-0905** | MoE | 1T / 32B | 256K | Modified MIT | 2025's trillion-parameter agent champion |
| **Kimi K2** | MoE | 1T / 32B | 128K | Modified MIT | Jul 2025 original; MuonClip optimizer; 15.5T tokens |
| **Kimi K1.5 / K1** | — | — | — | — | Earlier reasoning/vision gens |

- **License nuance:** below revenue thresholds K2.x behaves like MIT (self-host + fine-tune OK). Community-documented: serving by companies with >$20M revenue needs Moonshot authorization; large MaaS resale triggers the "Kimi K3"-style revenue-share agreement — read §20. Kimi K3 (reported ~2.8T MoE, 1M ctx) ships under that new revenue-share license.
- **Vibe:** agentic-first design (tool use, computer use, swarm orchestration) rather than chat-first.

### 4.5 Meta Llama (USA 🇺🇸 · Llama Community License) - [GitHub](https://github.com/meta-llama/llama-models) · [HF](https://huggingface.co/meta-llama)

| Model | Type | Params | Context | License | Notes |
|---|---|---|---|---|---|
| **Llama 4 Behemoth** | MoE | 2T-class | — | (announced) | Still training — teacher model for the family |
| **Llama 4 Maverick** | MoE | 402B / 17B | 1M | Llama 4 Community | Flagship; multimodal (image+text in); native tool use |
| **Llama 4 Scout** | MoE | 109B / 17B | **10M** | Llama 4 Community | Long-context record; runs on one 80 GB GPU (Q4 ~55 GB) |
| **Llama 3.3 70B** | Dense | 70B | 128K | Llama 3.3 Community | 2024-25's most-deployed open 70B |
| **Llama 3.1 8B** | Dense | 8B | 128K | Llama 3.1 Community | The classic single-GPU default |

- **License:** free below 700M MAU (Llama 4) — above that, enterprise license. Not OSI-"open source" (EU/scale restrictions). Source code in llama-models repo is MIT-ish but weights carry the community license.
- **Vibe:** the reason "open weights" became mainstream; huge fine-tune ecosystem; 10M-context Scout is unmatched for whole-repo/document dumps.

### 4.6 Mistral (France 🇪🇺 · Apache 2.0) - [GitHub](https://github.com/mistralai) · [HF](https://huggingface.co/mistralai) · [API](https://mistral.ai)

| Model | Type | Params | Context | License | Notes |
|---|---|---|---|---|---|
| **Mistral Large 3** | MoE | 675B / 41B act. (incl. 2.5B vision enc.) | 256K | Apache 2.0 | Dec 2 2025; largest open-weight MoE from a Western lab; 40–100+ langs; text+image |
| **Mistral Small 4** | Dense/MoE | ~30B | 128K+ | Apache 2.0 | Configurable reasoning, best cost/capability ratio |
| **Magistral Small** | Reasoning | ~30B | — | Apache 2.0 | Self-hosted reasoning line |
| **Devstral Small 2** | Coding agent | 24B | 128K | Apache 2.0 | Open SWE-agent default (Ollama-friendly) |
| **Ministral 3** | Dense | 3B/8B/14B | 128K | Apache 2.0 | Edge family |
| **Mixtral 8x7B / 8x22B** | MoE | 47B / 141B | 32K–64K | Apache 2.0 | The MoE that made sparse famous (2024) |
| **Voxtral** | Audio/ASR | ~7B | — | Mistral license | Call analytics, audio understanding |

- **Vibe:** Apache 2.0 + EU/GDPR-friendly; enterprise distribution via Azure/AWS/IBM watsonx.

### 4.7 Google Gemma (USA 🇺🇸 · Apache 2.0 since Gemma 4) - [GitHub](https://github.com/google-gemma) · [HF](https://huggingface.co/google) · [Kaggle](https://www.kaggle.com/models/google/gemma)

| Model | Type | Params | Context | License | Notes |
|---|---|---|---|---|---|
| **Gemma 4 31B** | Dense | 31B | 128K+ | Apache 2.0 | Flagship (Apr 2 2026); ~2.5× more token-efficient than peers (AA, v.r.); vision in all variants; free on AI Studio |
| **Gemma 4 26B-A4B** | MoE | 26B / 4B act. | 128K+ | Apache 2.0 | MoE efficiency sweet spot |
| **Gemma 4 E4B / E2B** | Dense (edge) | 8B / 5.1B | 128K | Apache 2.0 | Phone/laptop-ready; audio input on E2B/E4B (v.r.) |
| **Gemma 3** | Dense | 1B–27B | 32K–128K | Gemma Terms | Previous gen (non-compete clause for foundation models) |
| **Gemma 3n** | MoE | 8B (1.4B act.) | 32K | Gemma Terms | 2025 efficiency experiment |

- **License note:** Gemma 4 moved to **Apache 2.0** — a deliberate Google strategy shift; Gemma 3 and earlier keep the older "Gemma Terms of Use" (no competitor foundation models).
- **Vibe:** frontier-dense efficiency; phones-to-servers sizing; >10M first-week downloads (v.r.).

### 4.8 OpenAI gpt-oss (USA 🇺🇸 · Apache 2.0) - [HF](https://huggingface.co/openai) · [GitHub](https://github.com/openai/openai-open-models) · [site](https://openai.github.io/openai-open-models)

| Model | Type | Params | Context | License | Notes |
|---|---|---|---|---|---|
| **gpt-oss-120b** | MoE | 117B / 5.1B | 131K | Apache 2.0 | Reasoning + coding; fits one 80 GB GPU (FP8/MXFP4) |
| **gpt-oss-20b** | MoE | 21B / 3.6B | 131K | Apache 2.0 | ~16 GB VRAM; the laptop reasoning pick |
| **gpt-oss-safeguard** | MoE | 20b/120b | 131K | Apache 2.0 | Safety reasoning research preview |

- **Caveats:** not served via OpenAI API/ChatGPT; text-only reasoning models; Apache 2.0 + usage policy (fine-tune OK, no hostile-use fine-tunes etc.).
- **Vibe:** proof that even OpenAI ships open weights when the strategy demands it.

### 4.9 Also important families (registry: [data/models.json](data/models.json))

| Family | Org | Best known open model | License | Notes |
|---|---|---|---|---|
| **MiniMax M2.5** | MiniMax | ~200B MoE, ~200K ctx | Apache 2.0 | Strong SWE-bench Verified (~80 v.r.); M2/01-lineage |
| **MiMo** | Xiaomi | MiMo-V2-Flash | MIT | Surprise open performer, 256K ctx |
| **Phi** | Microsoft | Phi-4-mini 3.8B, Phi-4-Reasoning 14B | MIT | The edge/research default; tiny and MIT |
| **Sarvam** | Sarvam AI | Sarvam 105B / 30B | Sarvam license | Indic-language frontier (22 Indian langs) |
| **OLMo 2** | AI2 | OLMo 2 7B/13B/32B | Apache 2.0 | Fully open: weights+code+data |
| **SmolLM3** | HF | 3B | Apache 2.0 | Fully open edge line; 3B trains on a single GPU |
| **Pythia / Amber** | EleutherAI | 12B | Apache 2.0 | Fully-open research lineages |
| **IBM Granite** | IBM | Granite 3.x / Granite Speech | Apache 2.0 | Enterprise governance, instruct+code |
| **Falcon** | TII | Falcon 3 (1B–235B) | Apache 2.0 | UAE; Mamba-hybrid variants |
| **Hunyuan Hy3** | Tencent | 295B / 21B MoE, 256K | Apache 2.0 | Open-weight reasoning/agents (Jul 6 2026); reasoning_effort knob |
| **Seed-OSS-36B** | ByteDance | 36B dense | Apache 2.0 | ByteDance rare open release; dense thinking model |
| **InternLM3 / MiniCPM** | Shanghai AI Lab / OpenBMB | 1B-20B | Apache / open | Edge and community favorites (MiniCPM5-1B, MiniCPM5-2B Sep 2026, MiniCPM-V 4.6 1.3B) |
| **OpenClaw / community** | — | abliterated/fine-tuned variants | varies | Qwable & thousands of HF derivate models |

> ⚠️ Watch-outs: several "open" families above (Llama, Sarvam, Qwen3.8-2.4T, MiniMax-H video, LTX, FLUX.2 [dev]) carry usage caps or custom terms — every license is decoded in §20.

---

---

## 5. Reasoning models

"Reasoning" models spend extra inference tokens on an internal chain-of-thought before answering — they self-correct, and they dominate math/code/agent benchmarks. All the frontier labs now ship them (or a "thinking mode" toggle).

| Model | Org | Params | License | Reasoning style | Best at |
|---|---|---|---|---|---|
| **DeepSeek R1-0528 / R1** | DeepSeek | 671B/37B | MIT | Long CoT (R1-style RL) | Math, logic, coding; the reference open reasoner |
| **DeepSeek V4-Pro (max effort)** | DeepSeek | 1.6T/49B | MIT | Effort dial: low/high/max | Frontier reasoning + 1M ctx |
| **Qwen3 (thinking mode)** | Qwen | 4B–235B | Apache 2.0 | Hybrid: think/no-think per query | Cheap controllable reasoning (QwQ lineage) |
| **Qwen3.8 / Qwen3.5** | Qwen | up to 2.4T | Apache/custom | Reasons every request (3.8) | Agentic + reasoning at scale |
| **Kimi K2.6** | Moonshot | 1T/32B | Mod. MIT | Agentic CoT + tool loops | Long-horizon tasks, HLE-with-tools (v.r.) |
| **GLM-5.2 / GLM-5** | Z.ai | 744B | MIT | Two reasoning modes | Coding/agent + math |
| **Magistral Small** | Mistral | ~30B | Apache 2.0 | Configurable reasoning | Self-hosted reasoning, EU/GDPR |
| **gpt-oss-120b / 20b** | OpenAI | 117B/21B | Apache 2.0 | Reasoning (o-series distilled) | Local reasoning + coding |
| **Gemma 4 31B** | Google | 31B | Apache 2.0 | Efficient dense reasoning | Single-GPU reasoning, token-efficient |
| **MiniMax M2.5** | MiniMax | ~200B | Apache 2.0 | Hybrid reasoning | Math/SWE |
| **Phi-4-Reasoning** | Microsoft | 14B | MIT | Long-form CoT | Edge reasoning research |
| **DeepSeek R1-Distill (1.5B–70B)** | DeepSeek | 1.5B–70B | MIT | Distilled CoT | Laptop/edge reasoning |

**Practical notes**

- A "reasoning" model is ~2–10× more token-expensive per query; gate it behind hard tasks or a thinking toggle (Qwen3-style) to control cost.
- Small distills (R1-Distill 7B/14B, Qwen3 4B think) are shockingly good at math for their size — start there on laptops.
- Benchmarks to compare reasoning models: AIME 2024/2025/2026 (math olympiad), GPQA Diamond (PhD science), HLE (Humanity's Last Exam), ARC-AGI-2. See §25.

---

## 6. Coding and agentic models

The most commercially fought-over category in 2026. "Coding models" are fine-tunes for code; "agentic models" are trained for tool-calling loops (edit files, run commands, browse, use apps) — which is what SWE-bench Verified/Pro actually measures.

| Model | Org | Size | License | SWE-bench Ver. (v.r.) | Notes |
|---|---|---|---|---|---|
| **Kimi K2.7-Code** | Moonshot | 1T/32B | Mod. MIT | +21.8% Kimi Code Bench v2 (v.r.) | Coding specialist; -30% reasoning tokens; Kimi Code agent |
| **Kimi K2.6** | Moonshot | 1T/32B | Mod. MIT | ~58 Pro (ties GPT-5.5-class, v.r.) | Long-horizon agent champion; swarm research |
| **DeepSeek V4-Pro** | DeepSeek | 1.6T/49B | MIT | ~84 (v.r.) | Coding + everything |
| **GLM-5.2** | Z.ai | 744B | MIT | high 70s–80 (v.r.) | 1M-ctx agentic engineering; Codex/Claude rival claims |
| **Qwen3.5 / Qwen3.8** | Qwen | 397B–2.4T | Apache/custom | mid 60s–70s (v.r.) | Computer-use / agentic OS operation |
| **GLM-4.7** | Z.ai | 355B/32B | MIT | ~74 (v.r.) | Production favorite of 2025–26 |
| **Mistral Large 3** | Mistral | 675B/41B | Apache 2.0 | ~92 HumanEval (v.r.) | Enterprise-safe coding |
| **Qwen3-Coder-Next** | Qwen | up to 480B | Apache 2.0 | high (v.r.) | IDE-grade tool use |
| **Qwen3-Coder (30B)** | Qwen | 30B | Apache 2.0 | strong | The best open 30B coder to self-host |
| **Devstral Small 2** | Mistral | 24B | Apache 2.0 | strong at size | Default local SWE-agent brain |
| **MiniMax M2.5** | MiniMax | ~200B | Apache 2.0 | ~80 (v.r.) | Best quality-per-dollar coding API |
| **gpt-oss-120b** | OpenAI | 117B/5.1B | Apache 2.0 | o-series level (v.r.) | OpenAI-open coding |
| **Llama 4 Maverick** | Meta | 402B | Llama Comm. | ~56–62 (v.r.) | Multimodal + tool use |
| **Phi-4-mini** | Microsoft | 3.8B | MIT | modest | Tiny agent brains for edge |

**Open coding-agent stacks that consume these models** (see also §15)

| Tool | Type | License | Notes |
|---|---|---|---|
| **OpenHands** | Autonomous agent platform | MIT | Visual workspace, 100+ model providers, air-gapped capable |
| **Cline** | VS Code agent | Apache 2.0 | Most-installed open IDE agent; MCP; 30+ providers |
| **Aider** | Terminal pair programmer | Apache 2.0 | Git-native, reviewable AI commits |
| **OpenCode** | Terminal TUI agent | MIT | 75+ providers, local-first |
| **Goose (Block)** | Desktop/CLI runtime | Apache 2.0 | Deep MCP integration |
| **Kilo Code** | VS Code/JetBrains | Apache 2.0 | 500+ model support |
| **Tabby** | Self-hosted completions | Apache 2.0 | Air-gapped autocomplete |

**How to choose a local coding agent model**

1. ≤24 GB VRAM → Devstral 24B or Qwen3-Coder-30B (Q4).
2. One 80 GB GPU → gpt-oss-120b, GLM-4.7 Q4, Qwen3-Coder-Next Q4.
3. Multi-GPU/API → Kimi K2.6, GLM-5.2, DeepSeek V4 — or their cheap hosted APIs.

---

## 7. Vision-language models

VLMs read images, screenshots, documents, video frames, and (increasingly) audio. Every 2026 flagship is natively multimodal — the "pure text LLM" is going extinct at the frontier.

| Model | Org | Size | Modalities | License | Notes |
|---|---|---|---|---|---|
| **DeepSeek V4-Flash-Vision-Exp** | DeepSeek | 305B MoE | image+text | MIT | Aug 31 2026; first V4 vision weights (FP8) |
| **Gemma 4 (all)** | Google | E2B–31B | image (+audio on edge variants) | Apache 2.0 | Vision across the whole family |
| **Qwen3.5-397B-A17B / Qwen3.6-35B-A3B / Qwen3.8-27B** | Qwen | 27B-397B | image+video+text | Apache 2.0 | Open Qwen3.5+ weights are natively multimodal; computer-use agents; Qwen3.8-2.4T is text-only |
| **Qwen2.5-VL / Qwen3-VL** | Qwen | 3B–72B | image+video | Apache 2.0 | Document/UI champion; tons of GGUF |
| **Llama 4 (Maverick/Scout)** | Meta | 109B–402B | image in, text out | Llama Comm. | Native vision MoE |
| **Mistral Large 3** | Mistral | 675B/41B | image+text | Apache 2.0 | 2.5B vision encoder |
| **GLM-4.6V / GLM-5 (multimodal)** | Z.ai | 40B–355B | image | MIT | Strong document & GUI agents |
| **Kimi K2.6 / K2.7 Code** | Moonshot | 1T/32B | image+video+text | Mod. MIT | Native multimodal agentic (video placeholder in chat template) |
| **MiniMax M2 (VLM)** | MiniMax | ~200B | image | Apache 2.0 | — |
| **Pixtral (legacy)** | Mistral | 12B | image | Apache 2.0 | Still fine for OCR pipelines |

**Vision benchmarks:** MMMU, Vibe-Eval, DocVQA, ScreenSpot, OSWorld (computer use), BabyVision (v.r. for Qwen3.8 claims). When choosing: decide whether you need **OCR/docs** (small VLMs fine), **UI/computer-use agents** (frontier only), or **general understanding** (Gemma 4/Qwen sweet spots).

---

## 8. Image generation

| Model | Org | Params | VRAM (min) | License | Best for |
|---|---|---|---|---|---|
| **Qwen-Image-2512** | Qwen | 20B+ | ~24 GB | Apache 2.0 | **Open #1 overall** (10k+ blind arena rounds, v.r.); multilingual text (incl. Arabic RTL) |
| **FLUX.2 [dev]** | BFL | 32B | ~24 GB | FLUX.2 [dev] Non-Commercial | Photorealism + prompt fidelity (license paid above $100k revenue) |
| **FLUX.2 [klein]** | BFL | 4B/9B | ~13 GB | FLUX.2 [dev]-style | Real-time/edge, commercial below thresholds |
| **Z-Image-Turbo** | Tongyi/Z.ai | 6B | ~16 GB | Apache 2.0 | Throughput-per-dollar; bilingual text; turbo speed |
| **GLM-Image** | Z.ai | 9B+7B | ~20 GB | MIT | Best typography/poster/infographic text |
| **HiDream-O1** | HiDream | 8B | ~13 GB | MIT | Param-efficient quality |
| **HunyuanImage 3.0** | Tencent | 80B/13B act. | 40 GB+ | Community | Long complex prompts, knowledge-heavy scenes |
| **SD 3.5 Large / SDXL** | Stability | 8B / 3.5B | 8–16 GB | Stability Comm. | The LoRA/fine-tune ecosystem kings |
| **Stable Diffusion 1.5** | Stability | 0.9B | 4 GB | CreativeML OpenRAIL | Legacy community (still huge for LoRAs) |
| **Qwen-Image-Lightning** | Qwen | — | — | Apache 2.0 | Fast steps |

**Rules of thumb (2026)**

- Clean license + top quality → **Qwen-Image-2512** (Apache 2.0).
- Photorealism ceiling → **FLUX.2 [dev]** (read the revenue cap!).
- Text/typography (posters, UI, Arabic/CJK) → **GLM-Image** or **Qwen-Image**.
- Real-time/batch commercial → **Z-Image-Turbo** or **FLUX.2 [klein]**.
- Community LoRA styles → SDXL/SD3.5 remains the modding hub.
- Finetuning: LoRA on SDXL/Qwen-Image; see §16.

---

## 9. Video generation

| Model | Org | Size | Max out | Audio | License | Best for |
|---|---|---|---|---|---|---|
| **Wan 2.2** | Qwen/Tongyi | 1.3B–14B | 1080p · ~10 s (4K preview) | ✅ (2.5) | Apache 2.0 | **Cleanest commercial license**; local 14B |
| **LTX-2.5** | Lightricks | 22B | 4K · 20 s | ✅ native | Free < $10M ARR | Local 4K + synced audio; speed king |
| **MiniMax H3 (Hailuo 3.0)** | MiniMax | 33.1B | 768p open · 2K API | ✅ stereo | Community < $20M rev | Reference-heavy scenes (faces, sets, cues) |
| **HunyuanVideo 1.5** | Tencent | 13B | 720p · 15 s | ✅ | Community (100M MAU cap) | Cinematic motion, modest hardware |
| **SkyReels V2** | SkyWork | — | 8+ s (long-form) | — | Apache 2.0 (check) | Long-form consistency |
| **CogVideoX / X1.5** | Zhipu | 5B | 10 s | — | CogVideoX license | Open video pioneer line |
| **Mochi-1** | Genmo | 10B | 5 s | — | Apache 2.0 | Open baseline research |
| **Open-Sora 2.0** | HPC-AI | — | 15 s | — | MIT (code); check weights | Fully open pipeline ambitions |
| **LTX-2.3** | Lightricks | — | — | ✅ | LTX Community | Prior gen, still solid |

**Quick picks**

- Ship commercially with zero license friction → **Wan 2.2** (Apache 2.0).
- Best local quality-per-second + audio → **LTX-2.5** (mind the $10M ARR cap).
- Highest open ceiling with reference control → **MiniMax H3** API/self-host.
- Long cinematic shots on one 24 GB GPU → **HunyuanVideo 1.5** (13B).
- Video benchmarks: VBench, VBench-2, ChronoMagic; watch for "audio sync" claims — always spot-check.

---

## 10. Audio and music generation

| Model | Org | Size | License | Notes |
|---|---|---|---|---|
| **ACE-Step 1.5** | ACE/FunAudio | open | open weights (check) | Text→full songs, 50+ langs, covers, vocal-to-BGM, 10-min pieces; consumer GPUs/Mac |
| **MusicGen** | Meta | 1.5B | code MIT · weights CC-BY-NC | The classic open music baseline |
| **Stable Audio Open** | Stability | — | Stability Community | SFX/music stems from text |
| **YuE** | — | 7B | Apache 2.0 (check) | Song generation w/ vocals |
| **AudioLDM 2** | — | — | — | Research-grade text-to-audio |
| **Stable Sound / Audio APIs** | Stability | — | — | SFX niche |

**SFX:** Stable Audio Open is the common open default; for 2026 "music that ships," ACE-Step 1.5 is the community favorite (runs on one consumer GPU, 10-minute generations, cover/remix controls). MusicGen remains the research baseline.

---

## 11. Text-to-speech and voice

| Model | Org | Params | VRAM | Cloning | Langs | License | Notes |
|---|---|---|---|---|---|---|---|
| **Kokoro** | Hexgrad | 82M | CPU/2 GB | No (54 presets) | EN (+ few) | Apache 2.0 | ~200× real-time on a 4090; the CPU default |
| **Qwen3-TTS** | Qwen | 0.6B/1.7B | 4–8 GB | ✅ 3 s | 10 | Apache 2.0 | 5M+ hrs training (v.r.); NL emotion control; streaming 97 ms |
| **Chatterbox (Turraa)** | Resemble AI | 0.35–1.2B | 6 GB | ✅ 5–10 s | 23 (multiling.) | MIT | Emotional, zero-shot cloning |
| **CosyVoice 3.0** | FunAudioLLM | 0.5B | ~4 GB | ✅ zero-shot | multi | Apache 2.0 | 150 ms streaming |
| **IndexTTS-2** | IndexTeam | — | — | ✅ zero-shot | multi | open (check) | Emotion + duration control |
| **F5-TTS** | — | ~0.3B | ~4 GB | ✅ | EN/zh | MIT | Fast (33× Fast variant) |
| **Piper** | Rhasspy | tiny | CPU/RPi | No | 20+ | MIT | Edge TTS for IoT |
| **Fish Speech / OpenAudio S2** | fishaudio | 1.5B–4B | 12–24 GB | ✅ 10–30 s | 80+ | Research license | Commercial via paid API |
| **Voxtral TTS** | Mistral | — | — | ✅ 3 s | multi | Open-weight (check) | EU option |
| **VibeVoice** | Microsoft | 3B–7B | 12–20 GB | multi-speaker | EN/zh | MIT (research terms) | Podcast/long-form dialogue |
| **Dia / Orpheus (legacy)** | — | 1.6–3B | 10 GB | — | EN | — | Older community picks |

**Voice-cloning legal note:** clone only voices you have rights to; several jurisdictions require consent disclosure. For commercial-safe cloning: Qwen3-TTS (Apache) or Chatterbox (MIT). For CPU-only: Kokoro. For 2026 "podcast from text": VibeVoice.

---

## 12. Speech-to-text / ASR

| Model | Org | Params | Langs | License | Notes |
|---|---|---|---|---|---|
| **Whisper large-v3 / turbo** | OpenAI | 1.55B / 0.8B | 99 | MIT | The reference; fastest ecosystem (faster-whisper, whisper.cpp, WhisperX) |
| **Qwen3-ASR** | Qwen | 0.6B/1.7B | 52 | Apache 2.0 | Strong Mandarin/Asian + multilingual |
| **NVIDIA Parakeet TDT** | NVIDIA | ~0.6B | EN | Apache 2.0 | Fastest batch; ~1.4% WER EN (v.r.) |
| **NVIDIA Canary-Qwen 2.5B** | NVIDIA | 2.5B | EN/ES/DE/FR | CC-BY-4.0 | English accuracy leader on Open ASR LB (v.r.) |
| **Moonshine** | Useful Sensors | ~60M | EN | Apache 2.0 | On-device/low-latency edge |
| **Vosk** | Alpha Cephei | tiny | 20+ | Apache 2.0 | Embedded/offline, low power |
| **IBM Granite Speech** | IBM | ~1B | multi | Apache 2.0 | Enterprise governance |
| **MMS** | Meta | — | 1000+ | CC-BY-NC (weights) | Low-resource coverage research |
| **SpeechBrain** | SpeechBrain | — | many | Apache 2.0 | Toolkit: diarization, ASR, embeddings |

**Pipeline picks:** batch transcription → faster-whisper or Parakeet; streaming English → Parakeet TDT/Moonshine; multilingual streaming → Qwen3-ASR; speaker diarization → WhisperX/SpeechBrain + pyannote. WER leaderboard: HF Open ASR Leaderboard (link in §19).

---

---

## 13. Embeddings, rerankers and RAG

RAG (Retrieval-Augmented Generation) is how you bolt your private knowledge onto an LLM: chunk docs → embed → vector search → rerank → generate. In 2026 open-source embedders beat hosted API models on MTEB (§25).

### Embedding models (ranked by MTEB, open subset - v.r.)

| Model | Org | Dims | MTEB | License | Notes |
|---|---|---|---|---|---|
| **Qwen3-Embedding-8B** | Qwen | 4096 | ~70.6 | Apache 2.0 | Open leader: multilingual + code retrieval |
| **NV-Embed-v2** | NVIDIA | 4096 | ~72 (EN) | NVIDIA Open Model (check terms) | Max English accuracy |
| **BGE-M3** | BAAI | 1024 | ~67 | MIT | Hybrid dense+sparse; production multilingual default |
| **gte-Qwen3-8B** | Alibaba | 4096 | ~68 | Apache 2.0 | Long-context retrieval |
| **nomic-embed-v2 / text** | Nomic | 768 | ~61–62 | Apache 2.0 | Laptop pick via Ollama (`ollama pull nomic-embed-text`) |
| **Mxbai-embed-large** | Mixedbread | 1024 | ~65 | Apache 2.0 | Best sub-500M retrieval |
| **Jina Embeddings v3** | Jina | 8192 | ~63 | Apache 2.0 | Long docs, task LoRAs |
| **all-MiniLM-L6-v2** | SBERT | 384 | ~56 | Apache 2.0 | 23M params, edge/CPU |

### Rerankers (second-stage precision)

| Model | Org | Notes |
|---|---|---|
| **BGE-reranker-v2-m3** | BAAI | Default production reranker (MIT) |
| **Qwen3-Reranker** | Qwen | Apache 2.0, multilingual |
| **Jina Reranker v2** | Jina | API/open hybrid |
| **Cohere Rerank** | Cohere | API (not open) |

### Vector databases (open)

| DB | License | Notes |
|---|---|---|
| **Qdrant** | Apache 2.0 | Rust; filters + quantization |
| **Milvus / Zilliz** | Apache 2.0 | Billion-scale, GPU indexing |
| **Weaviate** | BSD-3 | Hybrid search built-in |
| **Chroma** | Apache 2.0 | Simplest Python local default |
| **pgvector** | PostgreSQL license | Add vectors to your existing Postgres |
| **LanceDB** | Apache 2.0 | Embedded, serverless-ish |

### RAG frameworks and orchestration

| Tool | License | Notes |
|---|---|---|
| **LlamaIndex** | MIT | Data framework for RAG |
| **Haystack** | Apache 2.0 | Production NLP pipelines |
| **LangChain / LangGraph** | MIT | Chains → agent graphs |
| **RAGFlow** | Apache 2.0 | Deep-document understanding RAG |
| **Dify** | Dify Open Source (Apache-based) | Visual LLM app platform |
| **n8n** | Fair-code | Workflow automation w/ AI nodes |

**Golden RAG stack (2026):** Ollama-able chat model (Qwen3.8-27B / Gemma 4) + Qwen3-Embedding-8B or BGE-M3 + Qdrant/pgvector + BGE-reranker-v2-m3 + LlamaIndex/LangGraph. Chunk at ~512 tokens with overlap, embed with metadata, rerank top-50→top-5, and always cite sources in prompts.

---

## 14. 3D generation

| Model | Org | Speed | VRAM | License | Best for |
|---|---|---|---|---|---|
| **Hunyuan3D 2.x** | Tencent | 3–8 min | 24 GB+ | Community (region caps) | **Best open mesh + texture quality**, full weights + training code |
| **TRELLIS.2** | Microsoft | 1–3 min | 16 GB+ | MIT | Native PBR to 4K, clean license, image→3D fidelity |
| **TripoSR** | Stability+Tripo | <1 s | 8 GB+ | Apache 2.0 (check) | Real-time single-image reconstruction |
| **Stable Fast 3D** | Stability | <1 s (H100) | 24 GB+ | Stability Comm. | Sub-second textured mesh pipelines |
| **SPAR3D** | Stability | ~10 s | 16 GB+ | Stability (rev. cap) | Single-photo mesh |
| **SAM 3D** | Meta | — | — | SAM license | Single photo → Gaussian splat + mesh (objects/people) |
| **InstantMesh** | community | ~1 min | 16 GB+ | MIT (check) | Balanced workflow |
| **TripoSG** | VAST-AI | — | — | open (check) | Shape generation 1.5B |

**Rules:** clean commercial license → TRELLIS.2; absolute quality ceiling + you can live with caps → Hunyuan3D; real-time apps → TripoSR / Stable Fast 3D; games assets pipeline = Hunyuan3D/TRELLIS mesh → UniRig auto-rig → animation. Formats: GLB/OBJ/PLY + PBR maps.

---

## 15. Agents, frameworks, fine-tuning and tooling

2026 is the agent era: LLM → tool calls → actions. Open source owns this stack end-to-end.

### Orchestration frameworks

| Framework | Org | License | Notes |
|---|---|---|---|
| **LangGraph** | LangChain | MIT | Graph-based durable agents; the most-deployed orchestration layer |
| **Microsoft Agent Framework (MAF)** | Microsoft | MIT | AutoGen + Semantic Kernel merged (1.0 GA Apr 2026); .NET + Python; CodeAct; hosted agents; Copilot SDK backend |
| **OpenAI Agents SDK** | OpenAI | MIT | Lightweight multi-agent (successor to Swarm) |
| **CrewAI** | crewAI | MIT | Role-based crews, flows |
| **Pydantic AI** | Pydantic | MIT | Type-safe agents |
| **AutoGen (legacy)** | Microsoft | MIT | Research multi-agent (now folded into MAF) |
| **Google ADK** | Google | Apache 2.0 | Agent Development Kit |
| **AgentScope / MetaGPT / CAMEL** | community | Apache/MIT | Multi-agent research frameworks |

### The universal glue: MCP

**MCP (Model Context Protocol)** — the open standard (originally Anthropic) that lets any agent call any tool/server. By 2026 it's supported by virtually every frontier model provider, IDE agent, and framework. Registry: [mcp.so](https://mcp.so) / [github.com/modelcontextprotocol](https://github.com/modelcontextprotocol).

### Memory, evals, observability

| Tool | Purpose | License |
|---|---|---|
| **Mem0** | Long-term agent memory | Apache 2.0 |
| **Langfuse** | LLM observability/eval | MIT (core) |
| **OpenTelemetry GenAI** | Tracing standard | Apache 2.0 |
| **AgentOps / Phoenix** | Agent tracing/eval | Apache 2.0 |
| **DeepEval / Ragas** | Eval frameworks | Apache 2.0 |
| **Promptfoo** | Prompt/red-team testing | MIT |
| **Braintrust** | Eval platform | Apache 2.0 (OSS core) |

### Browser / computer-use agents (open)

| Tool | Notes | License |
|---|---|---|
| **Skyvern** | Browser agent for workflows | Apache 2.0 |
| **Browser Use** | LLM browser control lib | Apache 2.0 |
| **OpenHands** | Full autonomous dev env | MIT |
| **Qwen3.5/GUI agents** | Model-level computer use | Apache 2.0 |
| **UI-TARS (ByteDance)** | GUI agent model | Apache 2.0 (weights check) |

### Serving and inference infra (production)

| Engine | License | Best for |
|---|---|---|
| **vLLM** | Apache 2.0 | High-throughput OpenAI-compatible serving; PagedAttention |
| **SGLang** | Apache 2.0 | RadixAttention; multi-modal; agent workloads |
| **llama.cpp** | MIT | CPU/edge GGUF inference; bindings everywhere |
| **TensorRT-LLM** | NVIDIA license | Max perf on NVIDIA GPUs |
| **TGI** | Apache 2.0 | HF's Text Generation Inference |
| **Ollama** | MIT | Local dev UX, one command |
| **KTransformers** | MIT | Run big MoE on limited hardware (expert offload) |
| **vLLM + DSpark** | — | DeepSeek's speculative decoding for V4 |

---

### 15.1 Fine-tuning and quantization (customizing models)

### Fine-tuning ladder (cheapest → most powerful)

| Method | What changes | Cost | When |
|---|---|---|---|
| **Prompt/RAG** | nothing | $0 | First answer: retrieve instead of retrain |
| **LoRA / QLoRA** | small adapters (0.1–1% params) | 1 GPU | Style, format, domain, tool behavior |
| **DoRA / LoRA-XS** | refined adapters | 1 GPU | Better rank/quality trade-offs |
| **Full fine-tune** | all weights | 4–64 GPUs | Major domain shift / new language |
| **RLHF / DPO / GRPO / R1-V RL** | reward-optimized | big | Reasoning & safety alignment; how R1-style models are made |
| **Distillation** | student from teacher | 1–8 GPUs | Shrink a model, keep behavior |

### Tools

| Tool | License | Notes |
|---|---|---|
| **Unsloth** | Apache 2.0 | 2–5× faster LoRA/QLoRA/full FT; free & pro tiers |
| **HF TRL** | Apache 2.0 | SFT + DPO/GRPO/ORPO at scale |
| **Axolotl** | Apache 2.0 | YAML-config fine-tuning |
| **PEFT** | Apache 2.0 | LoRA family library |
| **LLaMA-Factory** | Apache 2.0 | All-in-one web-UI fine-tuner |
| **bitsandbytes** | MIT | QLoRA NF4 4-bit base |
| **GPTQ / AWQ** | MIT / MIT | 4-bit weight compression for GPUs |
| **llama.cpp quantize** | MIT | GGUF Q4/Q5/Q6/Q8 + imatrix |
| **torchtune** | Apache 2.0 | PyTorch-native fine-tuning |
| **Nanotron / Megatron-LM** | Apache 2.0 | Pre-training at scale |

### Quantization cheat sheet (GGUF / bits)

| Level | Bits | Quality | Use |
|---|---|---|---|
| Q2_K | ~2.5 | poor | last-resort fit |
| Q4_K_M | ~4.5 | good | **default local sweet spot** |
| Q5_K_M | ~5.5 | better | quality-critical single GPU |
| Q6_K / Q8_0 | 6–8 | near-lossless | big VRAM, RAG backends |
| FP8 (native) | 8 | lossless-ish | data-center serving (V4-era standard) |
| MXFP4 / FP4 | 4 | good (MoE) | gpt-oss, V4-Flash native formats |

**Golden rule:** Q4_K_M for local, FP8 for serving, FP16/BF16 for training. VRAM formula in §24. Fine-tune with LoRA at Q4 base via Unsloth; merge and quantize to GGUF; serve via llama.cpp/Ollama/vLLM.

---

---

## 16. Hardware, VRAM and RAM - Quantization Guide

### The only formula you need

> **Model file size ≈ `params × bits ÷ 8`** (+ ~10–20 % overhead for context/KV cache & runtime)

| Precision | Bits | 3.8B | 8B | 14B | 27B | 70B | 235B MoE (22B act.) |
|---|---|---|---|---|---|---|---|
| FP16/BF16 | 16 | 7.6 GB | 16 GB | 28 GB | 54 GB | 140 GB | 470 GB |
| FP8 | 8 | 3.8 GB | 8 GB | 14 GB | 27 GB | 70 GB | 235 GB |
| Q6_K | ~6.5 | 3.1 GB | 6.5 GB | 11.4 GB | 22 GB | 57 GB | 191 GB |
| **Q4_K_M (default)** | ~4.5 | **2.2 GB** | **4.9 GB** | **8.5 GB** | **16.5 GB** | **42 GB** | **132 GB** |
| Q3_K / Q2_K | 3–2.5 | 1.6 GB | 3.5 GB | 6 GB | 12 GB | 30 GB | 95 GB |
| 1.58-bit (V4-era) | ~1.6 | — | — | — | — | — | ~40 GB (2.4T needs ~400 GB at 1-bit) |

### Context / KV-cache memory (rough)

KV cache ≈ `2 × layers × kv_heads × head_dim × ctx_tokens × bytes`. Practically: for 8B models ≈ **0.5–1 GB per 32K tokens**; for 235B MoE ≈ 1–2 GB per 32K (varies by architecture — MLA/Gated-DeltaNet/linear-attention models cut this massively; that's why DeepSeek V4 & Qwen3.8 handle 1M context). Use `ollama ps` after warm-up for real numbers.

### GPU / VRAM decision table

| Hardware | Fits comfortably (Q4) | Pick |
|---|---|---|
| **CPU only (laptop, no GPU)** | 1B–8B, slow but works | Phi-4-mini, SmolLM3, Qwen3:4b, Kokoro TTS |
| **4–6 GB VRAM** (old GPU) | ≤3B, heavy offload | Gemma 4 E2B/E4B-Q4, Phi-3.5-mini, Qwen3:1.7b |
| **8 GB VRAM** (RTX 3060/4060) | 7–8B Q4 + partial 14B | Qwen3:8b, Llama 3.1 8B, gpt-oss-20b (tight) |
| **12 GB VRAM** (4070/3060 12G) | 14B Q4 | Qwen3:14b, Gemma 4 E4B, Phi-4 |
| **16 GB VRAM** (4080/4090 laptop) | 20–24B MoE Q4 | gpt-oss-20b, Qwen3-Coder-30B (tight), Devstral 24B |
| **24 GB VRAM** (4090/3090) | 27–32B Q4 | Qwen3.8-27B, Gemma 4 31B, Mistral Small 4 |
| **48 GB** (2×4090 / A6000) | 70B Q4 (split) | Llama 3.3 70B, DeepSeek-R1-Distill-70B |
| **80 GB** (H100/A100/MI300X) | 117B MoE FP8 | gpt-oss-120b, GLM-4.7 Q4, Llama 4 Scout-Q4 (55 GB) |
| **Multi-GPU node** | 400B–2.4T | DeepSeek V4, Qwen3.8-2.4T, GLM-5.2, Kimi K2.6 |

### RAM (no GPU) - llama.cpp / Ollama rules of thumb

Model must fit in **RAM + swap**; expect **1–4 tok/s** at 8B on a modern laptop CPU (more with Metal/AVX-512 + big context). 8B Q4 ≈ 5 GB RAM + ~2 GB overhead → 16 GB RAM laptops are fine. 14B Q4 ≈ 9 GB → 32 GB RAM recommended. MoE models are the CPU sleeper: only active experts run, so 235B-A22B Q4 (~132 GB file) is not CPU-feasible, but **gpt-oss-20b / Qwen3-30B-A3B** (3B active) run surprisingly well on 32 GB RAM machines.

### Mac (Apple Silicon)

Unified memory = VRAM: 16 GB Mac → 8B Q4 comfortable (Metal acceleration via Ollama/llama.cpp); 32–64 GB → 27–31B dense Q4; 128 GB+ → 70B Q4. Memory-bound, fast. Note: some stacks (e.g., Qwen3-TTS MPS) lack Apple acceleration — check per-model notes.

### Quantization cheat sheet

| Format | Where | Use for |
|---|---|---|
| **GGUF Q4_K_M** | llama.cpp/Ollama/LM Studio | Local default — best quality-per-GB |
| **GGUF Q5_K_M / Q6_K** | same | Quality-critical single-GPU |
| **AWQ / GPTQ** | vLLM/Transformers | GPU serving with 4-bit |
| **bitsandbytes NF4** | Transformers/QLoRA | Train LoRA on a 4-bit base |
| **FP8 (E4M3)** | vLLM/SGLang datacenter | Native-lossless-ish serving; the V4-era standard |
| **MXFP4/FP4** | native (gpt-oss, V4-Flash) | Offload-friendly native formats — don't re-quantize |
| **IMatrix GGUF** | llama.cpp | Improve Q4 quality on your corpus |

### Inference engines by hardware (full list in §15)

Ollama (easiest) · llama.cpp (CPU/edge) · LM Studio (GUI) · vLLM (GPU serving) · SGLang (agents/multimodal) · KTransformers (mega-MoE on small RAM) · TensorRT-LLM (NVIDIA max perf).

---

---

## 17. How to Download and Run Locally

### The easiest way - Ollama (recommended for most people)

```bash
# 1. Install (Linux/macOS)
curl -fsSL https://ollama.com/install.sh | sh

# 2. Pull a model (auto-downloads)
ollama pull qwen3:8b

# 3. Chat
ollama run qwen3:8b

# Useful management commands
ollama list                    # installed models
ollama show <model>            # params / Modelfile / sizes
ollama rm <model>              # free disk space
ollama ps                      # running models + GPU usage
```

**Popular pull commands**

```bash
ollama pull llama3.3:70b       # big, ~42GB VRAM
ollama pull gemma4:e4b         # edge, ~3GB
ollama pull deepseek-r1:14b    # reasoning, ~9GB
ollama pull qwen3-coder:30b    # code
ollama pull mixtral            # 8x7B MoE
ollama pull nomic-embed-text   # embeddings for RAG
```

**OpenAI-compatible local API** (use any OpenAI SDK)

```bash
curl http://localhost:11434/v1/chat/completions \
  -H "Content-Type: application/json" \
  -d '{"model":"qwen3:8b","messages":[{"role":"user","content":"Hello!"}]}'
```

```python
from openai import OpenAI
client = OpenAI(base_url="http://localhost:11434/v1", api_key="ollama")
resp = client.chat.completions.create(
    model="qwen3:8b",
    messages=[{"role": "user", "content": "What is machine learning?"}]
)
print(resp.choices[0].message.content)
```

### Hugging Face (transformers / fine-tuning)

```bash
pip install transformers huggingface-hub

# Download only
huggingface-cli download meta-llama/Llama-4-Scout-17B-16E-Instruct

# Load and run in Python
from transformers import AutoTokenizer, AutoModelForCausalLM
model = AutoModelForCausalLM.from_pretrained("Qwen/Qwen3-8B", device_map="auto")
tok = AutoTokenizer.from_pretrained("Qwen/Qwen3-8B")
out = model.generate(**tok(["Hello"], return_tensors="pt").to(model.device))
```

### Other inference engines

| Engine | Best for | Example |
|---|---|---|
| **vLLM** | Scalable production OpenAI-API | `vllm serve Qwen/Qwen3-235B-A22B-Instruct` |
| **llama.cpp** | CPU / low-end GPU (GGUF) | `./build/bin/llama-server -hf unsloth/gpt-oss-120b-GGUF:UD-Q4_K_XL` |
| **SGLang** | High-throughput serving | `python -m sglang.launch_server` |
| **KTransformers** | Run mega-MoE on limited hardware | `ktransformers qwen3-235b-a22b` |
| **LM Studio** | GUI, no-code | Download & chat in the app |
| **Text Generation WebUI (oobabooga)** | Local GUI | Load GGUF/safetensors |
| **ComfyUI** | Image/video workflows | Node-based generation |
| **Ollama Container** | Docker, single command | `docker run -d -v ollama:/root/.ollama -p 11434:11434 ollama/ollama` |

---

## 18. Which Model Should You Use? (Decision Guides)

### By task

| If you need… | Start with | Why |
|---|---|---|
| **Best overall frontier (self-hosted)** | DeepSeek V4-Pro · Qwen3.8-2.4T | Top reasoning + coding at scale |
| **Best clean commercial license** | Qwen3 · Gemma 4 · gpt-oss | Apache 2.0, no strings |
| **Best coding / agentic** | Kimi K2.6 · GLM-5.2 · DeepSeek V4 | Long-horizon SWE + tool use |
| **Deep chain-of-thought reasoning** | DeepSeek R1 · Qwen3 | Self-correcting, high AIME |
| **Massive context (docs/repos)** | Llama 4 Scout (10M) · DeepSeek V4 (1M) | Longest windows |
| **Multilingual product** | Qwen3 (201 langs) · Mistral Large 3 (80+) | Language coverage |
| **Single consumer GPU** | Gemma 4 · Qwen3.8-27B | Fits 24GB at Q4 |
| **Laptop / edge** | Phi-4-mini · gpt-oss-20b · SmolLM3 | 3.8B–21B, low RAM |
| **Local coding agent** | Devstral · Qwen3-Coder · Qwen3-Coder-Next | Agentic SWE workflows |
| **GDPR / EU residency** | Mistral Large 3 · Qwen3 | Apache + EU provider |
| **Fully open training data** | OLMo 2 · SmolLM3 | Weights + code + data open |

### By hardware

| Hardware | Pick | Command |
|---|---|---|
| **CPU only (laptop)** | Phi-4-mini, SmolLM3, Kokoro TTS | `ollama pull phi4-mini` |
| **8GB VRAM** | Qwen3 8B, Llama 3.1 8B | `ollama pull qwen3:8b` |
| **12GB VRAM** | Qwen3 14B, Gemma 3 12B | `ollama pull qwen3:14b` |
| **16GB VRAM** | gpt-oss-20b, Mistral Small 24B | `ollama pull gpt-oss:20b` |
| **24GB VRAM** | Qwen3.8-27B, Gemma 4 26B | `ollama pull qwen3.8:27b` |
| **48GB+** | Llama 3.3 70B | `ollama pull llama3.3:70b` |
| **Multi-GPU** | DeepSeek V4, GLM-5.2, Qwen3.5 | `ollama pull deepseek-v4-flash` |

### By return-on-investment (best quality per dollar)

- **Best budget:** DeepSeek V4-Flash ($0.28/1M out) · Qwen3-Coder-Next ($0.11/1M in).
- **Best free (self-host):** Qwen3 / Gemma 4 after hardware cost.
- **Best for a tiny budget:** phi4-mini, qwen3:8b, gpt-oss:20b.

---

---

## 19. Where to Explore Models - Hubs and Leaderboards

| Platform | What it is | Link |
|---|---|---|
| **Arena (LM Arena)** | Human-preference Elo leaderboard (blind battles), all categories | https://arena.ai/leaderboard · https://lmarena.ai |
| **Arena leaderboard (HF Space)** | Same leaderboard on Hugging Face | https://huggingface.co/spaces/lmarena-ai/arena-leaderboard |
| **Hugging Face 🤗** | Model weights, datasets, demo spaces | https://huggingface.co |
| **Hugging Face Open LLM Leaderboard** | Automated benchmark leaderboard | https://huggingface.co/spaces/open-llm-leaderboard/open_llm_leaderboard |
| **Hugging Face Open ASR Leaderboard** | Speech-to-text WER rankings | https://huggingface.co/spaces/hf-audio/open_asr_leaderboard |
| **Hugging Face Open Reranker Leaderboard** | Reranker quality rankings | https://huggingface.co/spaces/mteb/leaderboard |
| **GitHub 🐙** | Source code, training/inference repos | https://github.com |
| **Ollama 🦙** | One-command local models library | https://ollama.com/library |
| **ModelScope** | Chinese ML model hub (Qwen, etc.) | https://modelscope.cn |
| **OpenRouter** | Unified API for many open models | https://openrouter.ai |
| **Artificial Analysis** | Independent quality/speed/price index | https://artificialanalysis.ai |
| **Together AI** | Hosted open-model inference | https://www.together.ai |
| **Fireworks AI** | Fast open-model inference | https://fireworks.ai |
| **DeepSeek Platform** | Official DeepSeek API | https://platform.deepseek.com |
| **Z.ai** | Official GLM API | https://z.ai |
| **Moonshot Platform** | Official Kimi API | https://platform.moonshot.ai |
| **Alibaba Cloud Bailian** | Qwen hosted API | https://www.alibabacloud.com/product/bailian |
| **LM Studio** | Desktop GUI for local models | https://lmstudio.ai |
| **Vellum Open LLM Leaderboard** | Ranking comparison | https://www.vellum.ai/open-llm-leaderboard |
| **ComfyUI** | Node-based image/video workflows | https://comfy.org |
| **llm-stats.com** | Cross-reference benchmarks | https://llm-stats.com |
| **MCP registry** | Agent tools/protocol servers | https://mcp.so |

---

## 20. Open-Source Licenses Explained

**Read your model's license before shipping.** This is the single biggest "gotcha" in open-source AI.

| License | Commercial use? | Fine-tune? | Notes / examples |
|---|---|---|---|
| **Apache 2.0** | ✅ Unrestricted | ✅ | Patent grant, most permissive. Qwen, Gemma 4, gpt-oss, Mistral, FLUX.2 klein, Wan, OLMo, Phi (mini), BGE, Z-Image. |
| **MIT** | ✅ Unrestricted | ✅ | Minimal requirements. DeepSeek, GLM, Kimi K2.x*, Phi, Kokoro, CosyVoice, BGE-M3. |
| **Modified MIT** | ✅ Mostly | ✅ | Kimi K2.x (self-host + fine-tune ok; revenue-triggered terms for resale above thresholds). |
| **Llama Community License** | ✅ but MAU cap | ✅ | 700M MAU cap for Llama 4 → enterprise license above; not OSI "open source". |
| **Gemma Terms of Use** | ✅ | ⚠️ no competitor foundation models | Gemma 3 and earlier. (Gemma 4 → Apache 2.0.) |
| **Kimi K3 License** | ✅ with revenue terms | ✅ | Revenue-triggered MaaS resale; also applies in spirit to K2.x serving by >$20M-revenue companies. |
| **Qwen3.8-Max license (2.4T)** | ⚠️ conditions | ✅ | Non-commercial/revenue-share terms reported for the 2.4T open release (HF license:other); 27B sibling stays Apache 2.0. |
| **CC-BY-NC** | ❌ Non-commercial | ✅ | Command R+, NV-Embed v1, F5-TTS weights, MusicGen weights, Meta MMS. |
| **BigCode OpenRAIL-M** | ✅ but use-based | ✅ | StarCoder 2 (harmful-use restrictions). |
| **Stability Community / Databricks / NVIDIA** | ⚠️ conditions | ✅ | DBRX, StableLM, Nemotron, SD3.5, Stable Audio Open. |
| **Tencent Hunyuan Community** | ✅ below 100M MAU | ✅ | HunyuanVideo, HunyuanImage, Hy3. |
| **LTX / MiniMax Community** | ✅ below revenue threshold | ✅ | LTX-2.5 (<$10M ARR), MiniMax H3 (<$20M), MiniMax M2.5 (custom LICENSE-MODEL). |
| **FLUX.2 [dev] Non-Commercial** | ✅ <$100k revenue | ✅ | BFL's dev license for FLUX.2 [dev] (pro/enterprise above). |
| **Sarvam license** | ✅ mostly | ✅ | Indic models; read caps for large-scale resale. |

> **TL;DR:** For zero license friction on a commercial product, pick **Apache 2.0** (Qwen, Gemma 4, gpt-oss, Mistral, Wan, Z-Image, BGE) or **MIT** (DeepSeek, GLM, Phi, Kokoro, CosyVoice). Avoid **CC-BY-NC** unless your use is internal/non-commercial. Always read the license file of the exact model card you download — variants differ (e.g., NV-Embed v1 NC vs v2 NVIDIA Open Model).

---

## 21. Glossary of AI Model Terms

| Term | Definition |
|---|---|
| **LLM** | Large Language Model — trained on massive text to generate/understand language. |
| **SLM** | Small Language Model — 1B–30B, runs on consumer hardware. |
| **MoE (Mixture-of-Experts)** | Activates only a fraction of parameters per token (e.g. 1.6T total / 49B active). Faster & cheaper at scale. |
| **Active parameters** | The subset of a MoE model actually used for each token. Smaller = faster, less memory. |
| **Context window** | Max tokens the model can see at once (128K, 1M, 10M…). Bigger = longer documents. |
| **Token** | Unit of text a model processes (~¾ of a word in English). See "128K context" = ~96K words. |
| **Fine-tuning** | Continuing training on your data to specialize the model. LoRA is a cheap way. |
| **LoRA** | Low-Rank Adaptation — efficient fine-tuning that trains a small adapter instead of all weights. |
| **QLoRA** | LoRA on a 4-bit quantized base — fine-tune big models on one GPU. |
| **Quantization** | Shrinking model weights (e.g. F16 → Q4) to cut memory and speed up inference. |
| **GGUF** | File format for running quantized models on CPU (llama.cpp/CPU inference). |
| **Safetensors** | Safe+fast weight format used by Hugging Face. |
| **VLM** | Vision-Language Model — understands images + text. |
| **RAG** | Retrieval-Augmented Generation — combine a vector DB + LLM to answer from your docs. |
| **Embedding** | Converts text to a vector; enables semantic search / RAG. |
| **Reranker** | Re-scores retrieved chunks for higher-precision RAG. |
| **MTEB** | The benchmark for embedding model quality. |
| **KV cache** | Memory holding prior tokens' keys/values; grows with context. |
| **MoE / dense** | Dense runs every parameter per token; MoE routes each token to a few experts. |
| **Arena Elo** | Human-preference ranking from blind pairwise votes. |
| **Self-hosted** | Running a model on your own hardware/infra vs. a hosted API. |
| **Open-weight vs open-source** | Open-weight = weights released; open-source = weights + code + data. |
| **MMDiT** | Multimodal Diffusion Transformer — common image/video architecture. |
| **TTS / ASR** | Text-to-Speech / Automatic Speech Recognition. |
| **MCP** | Model Context Protocol — open standard for agent tool connections. |
| **Agent** | LLM loop that plans, calls tools, observes results, iterates. |
| **SWE-bench** | Benchmark: can the model fix real GitHub issues? |
| **AIME / GPQA / HLE** | Math-olympiad / PhD-science / expert-knowledge reasoning benchmarks. |
| **CoT (chain-of-thought)** | The internal step-by-step reasoning a model produces before answering. |
| **Distillation** | Training a small model to imitate a big one's behavior. |

---

## 22. FAQ - Frequently Asked Questions

### What is the best open-source AI model in 2026?
It depends on your task. **DeepSeek V4-Pro** and **Qwen3.8-2.4T** lead overall. **Kimi K2.6** and **GLM-5.2** are best for coding/agentic work. **Gemma 4** and **Qwen3.8-27B** are best on a single GPU. **Phi-4-mini** and **gpt-oss-20b** are best for laptops. [See the decision guides →](#18-which-model-should-you-use-decision-guides)

### What is the best free local LLM?
For most people **Qwen3:8b** (Apache 2.0). For weak hardware, **Phi-4-mini** (3.8B, MIT). For a single strong GPU, **Gemma 4 31B**. For open reasoning on a laptop, **gpt-oss-20b**. All are free to self-host.

### Which open-source models can I use commercially?
Anything on **Apache 2.0** (Qwen, Gemma 4, gpt-oss, Mistral, Wan, Z-Image, BGE) or **MIT** (DeepSeek, GLM, Phi, Kokoro, CosyVoice, Chatterbox). Avoid **CC-BY-NC** models (Command R+, MusicGen weights, F5-TTS weights) for commercial products.

### Can I run an LLM without a GPU?
Yes. **Ollama** runs 1B–8B models on CPU/RAM. **Phi-4-mini** (3.8B) and **SmolLM3-3B** are CPU-friendly. For speech, **Kokoro** (82M) runs faster than real-time on CPU.

### What's the difference between total and active parameters?
In **MoE** models (DeepSeek V4 = 1.6T total / 49B active), only a fraction of the network runs per token. Active params determine **speed** and **memory**, while total params reflect overall capacity. That's why a "1T" model can still be fast.

### Where do I download open-source AI models?
**Hugging Face** (weights), **GitHub** (source code), **Ollama** (`ollama pull <model>`), **ModelScope** (Chinese hub), and model-specific sites. See [§19](#19-where-to-explore-models-hubs-and-leaderboards).

### What is the best open-source model for coding?
**Kimi K2.6**, **GLM-5.2**, and **DeepSeek V4** top SWE-bench/Terminal-Bench. For local coding agents, try **Devstral** (24B) or **Qwen3-Coder**.

### What is the best open-source image generation model?
**Qwen-Image-2512** (Apache 2.0) is the safest all-rounder. **FLUX.2 [dev]** is best for photorealism (revenue-capped license). **Z-Image-Turbo** is best for speed under Apache 2.0. **GLM-Image** is best for typography.

### What is the best open-source video generation model?
**Wan 2.2** (Apache 2.0, no limits) for commercial use. **LTX-2.5** for local 4K with synced audio. **HunyuanVideo 1.5** for cinematic motion.

### What is the best open-source TTS / voice model?
**Kokoro** (82M, Apache 2.0) for speed and zero GPU. **Chatterbox** or **Qwen3-TTS** for commercial-safe voice cloning. **Piper** for edge devices.

### How much VRAM do I need?
Model file ≈ `params × bits / 8`. A **4-bit (Q4)** 8B model needs ~5GB VRAM; a 70B needs ~42GB; a 235B MoE needs ~132GB. See [§16](#16-hardware-vram-and-ram-quantization-guide).

### Is open source as good as GPT-4/Claude?
For many real-world tasks, open models reach **~95%** of frontier proprietary models on benchmarks like SWE-bench, MTEB, and Arena — at **zero per-token cost**. The absolute quality ceiling (hardest reasoning) still favors closed frontier models, but the gap is small and closing (2026: open models beat GPT-4.5/Claude-3.5-era closed models outright on most benches).

### What is the difference between open-source and open-weight?
**Open-weight** = weights are released, but training data/code may be closed (Llama, Gemma, Kimi, DeepSeek). **Open-source** = weights + code + data are all public (OLMo 2, SmolLM3, Pythia, Amber).

### Which model has the longest context?
**Llama 4 Scout** at 10M tokens (109B MoE, single-GPU). Next tier: **Qwen3.8/GLM-5.2/DeepSeek V4** at ~1M. Qwen3.8-2.4T claims up to 1M via providers.

### Can I test open models for free without my own GPU?
Yes — free tiers that routinely cover open models: **Groq** (fast Llama/Qwen/gpt-oss endpoints, ~14.4K req/day), **Cerebras** (fast Llama, similar caps), **OpenRouter `:free`** models (20 RPM / 50 RPD without credits), **Google Gemini API free tier** (proprietary but generous), **DeepSeek signup grant**, **Mistral Codestral free key** (30 RPM), **Hugging Face serverless** for <10B models, and **GitHub Models**. Full table in [Appendix E](#appendix-e-free-and-low-cost-api-tiers-for-testing-open-models).

### Which open models are natively multimodal in 2026?
**Qwen3.5/3.6/3.8** open weights handle image+video (Qwen3.8-2.4T is text-only), **Gemma 4** (all sizes), **Kimi K2.6/K2.7 Code** (image+video), **Llama 4**, **Mistral Large 3**, **MiniMax M2**, and **DeepSeek V4-Flash-Vision-Exp**. GLM-5.2 is text-first with the GLM-4.6V vision sibling.

### Who made ModelAtlas?
ModelAtlas is maintained by a **student-teacher research fellowship** — a small group of students who draft the reviews and teachers who check them. Nobody is paid, nobody is sponsored, and we are not affiliated with any model lab. The full story is in [§1](#1-about-modelatlas-and-the-team-behind-it) and on the [About page](ABOUT.md).

### Where can I get free AI APIs?
A dozen providers still give developers genuinely free tiers — Google AI Studio, Groq, Cerebras, GitHub Models, Cloudflare Workers AI, OpenRouter's `:free` models, Hugging Face Inference, Mistral's Codestral key, NVIDIA NIM and Cohere. The table with sign-up links and current limits is in the [free AI API section](#where-to-get-free-ai-apis-sept-2026), with per-category notes (embeddings, speech, images) below it.

### What categories and features does ModelAtlas cover?
ModelAtlas tracks **101 models in 14 registry categories** — `llm` (33), `reasoning` (7), `coding` (4), `vlm` (6), `image` (7), `video` (7), `music` (3), `tts` (7), `asr` (7), `embedding`/`reranker` (6+2), `model3d` (5), `omni` (5), `ocr` (2) — each with its own table section, plus agents/frameworks/tooling (§15). Feature-wise: license fast-pass (§20), VRAM/GPU guides (§16, Appendix F), free API tiers (Appendix E), decision guides (§18), FAQ + glossary (§21–22) and machine-readable twins ([`llms.txt`](llms.txt), [`data/models.json`](data/models.json)). Start from the [category index](#categories-covered-14-categories-101-models).

### What changed in open-source AI this summer (2026)?
GLM-5.2 (Jun 13), Kimi K2.7-Code (Jun 12), Hunyuan Hy3 under Apache 2.0 (Jul 6), LTX-2.5 video+audio (Jul 23), DeepSeek V4-Flash weights (Jul 31) and V4-Pro GA+weights (Aug 13), Qwen3.8 generation (Aug), Gemma 4 staying hot (10M+ first-week downloads). Full log: [CHANGELOG.md](CHANGELOG.md).

### What about DeepSeek data-routing concerns?
Self-hosted open weights never leave your infra. Hosted DeepSeek/Z.ai/Kimi APIs route through China — check provider TOS before sending sensitive data. See §24.

---

---

## 23. Resources and References

### Official docs and hubs
- 🌍 **Arena leaderboard (live):** https://arena.ai/leaderboard
- 🤗 **Hugging Face:** https://huggingface.co · **Open LLM Leaderboard:** https://huggingface.co/spaces/open-llm-leaderboard/open_llm_leaderboard
- 🦙 **Ollama library:** https://ollama.com/library
- 🐙 **Awesome Open-Source LLM list:** https://github.com/Hannibal046/Awesome-LLM
- 🧪 **llama.cpp (GGUF/CPU):** https://github.com/ggerganov/llama.cpp
- 🚀 **vLLM (inference engine):** https://github.com/vllm-project/vllm
- **SGLang:** https://github.com/sgl-project/sglang · **KTransformers:** https://github.com/kvcache-ai/ktransformers
- **MCP (agent protocol):** https://modelcontextprotocol.io · https://github.com/modelcontextprotocol

### Read more
- **LLM selection guide (iternal.ai):** https://iternal.ai/llm-selection-guide
- **Run models locally (Hugging Face blog):** https://huggingface.co/blog/daya-shankar/open-source-llm-models-to-run-locally
- **Open-source LLMs (Hugging Face blog):** https://huggingface.co/blog/daya-shankar/open-source-llms
- **Ollama VRAM requirements:** https://localllm.in/blog/ollama-vram-requirements-for-local-llms
- **What is LLM quantization:** https://huggingface.co/blog/merve/quantization

### Primary sources - peer-reviewed technical reports (arXiv, open access)

| Model / work | Paper / report | Reference |
|---|---|---|
| **DeepSeek-R1** | DeepSeek-R1: Incentivizing Reasoning Capability in LLMs via RL | [arXiv:2501.12948](https://arxiv.org/abs/2501.12948) · DeepSeek-AI, 2025 |
| **Qwen3** | Qwen3 Technical Report | [arXiv:2505.09388](https://arxiv.org/abs/2505.09388) · Qwen Team, 2025 |
| **Mistral 7B** | Mistral 7B | [arXiv:2310.06825](https://arxiv.org/abs/2310.06825) · Jiang et al., 2023 |
| **Mixtral 8x7B** | Mixtral of Experts (sparse MoE) | [arXiv:2401.04088](https://arxiv.org/abs/2401.04088) · Jiang et al., 2024 |
| **Llama 4 (Scout/Maverick)** | Llama 4 Technical Report | [arXiv:2504.15006](https://arxiv.org/abs/2504.15006) · Meta, 2025 |
| **DeepSeek-V3** | DeepSeek-V3 Technical Report | [arXiv:2412.19437](https://arxiv.org/abs/2412.19437) · DeepSeek-AI, 2024 |
| **Qwen2.5** | Qwen2.5 Technical Report | [arXiv:2412.15115](https://arxiv.org/abs/2412.15115) · Qwen Team, 2024 |
| **GLM-4** | GLM-4 Technical Report | [arXiv:2406.12793](https://arxiv.org/abs/2406.12793) · GLM Team, 2024 |
| **Kimi K1.5** | Kimi K1.5: Scaling Reinforcement Learning with LLMs | [arXiv:2501.12599](https://arxiv.org/abs/2501.12599) · Moonshot AI, 2025 |
| **DeepSeek V4** | DeepSeek V4 family technical report | [arXiv:2606.19348](https://arxiv.org/abs/2606.19348) · DeepSeek-AI, 2026 |
| **Kimi K2.6** | K2.6 report (MoE, agents, multimodal) | [arXiv:2602.02276](https://arxiv.org/abs/2602.02276) · Moonshot AI, 2026 |
| **GLM-5.x** | GLM-5/5.2 reports | [arXiv:2602.15763](https://arxiv.org/abs/2602.15763) · [arXiv:2603.12201](https://arxiv.org/abs/2603.12201) · Z.ai, 2026 |
| **Qwen3-TTS** | Qwen3-TTS technical report | [arXiv:2601.15621](https://arxiv.org/abs/2601.15621) · Qwen Team, 2026 |
| **Qwen3-Embedding** | Qwen3-Embedding technical report | [arXiv:2506.05176](https://arxiv.org/abs/2506.05176) · Qwen Team, 2025 |
| **Gemma 4** | Gemma 4 report | [arXiv:2607.02770](https://arxiv.org/abs/2607.02770) · Google DeepMind, 2026 |
| **TRELLIS.2** | TRELLIS.2 (image-to-3D) | [arXiv:2512.14692](https://arxiv.org/abs/2512.14692) · Microsoft, 2025 |
| **Stable Audio Open** | Stable Audio Open | [arXiv:2407.14358](https://arxiv.org/abs/2407.14358) · Evans et al., 2024 |
| **MusicGen** | Simple and Controllable Music Generation | [audiocraft](https://github.com/facebookresearch/audiocraft) · Copet et al., 2023 |

> Primary sources for other 2025–26 families are published by the model vendors on their model cards / GitHub repositories (linked throughout each section). Where a peer-reviewed paper is not publicly archived, the canonical vendor repository or model card is cited instead so the link always resolves.

### Model repos mentioned
- Llama: https://github.com/meta-llama/llama-models · https://huggingface.co/meta-llama
- Qwen: https://github.com/QwenLM · https://huggingface.co/Qwen
- DeepSeek: https://github.com/deepseek-ai · https://huggingface.co/deepseek-ai
- Kimi: https://github.com/MoonshotAI/Kimi-K2 · https://huggingface.co/moonshotai
- GLM: https://github.com/zai-org/GLM-5 · https://huggingface.co/zai-org
- Mistral: https://github.com/mistralai · https://huggingface.co/mistralai
- Gemma: https://github.com/google-gemma · https://huggingface.co/google
- Phi / gpt-OSS: https://huggingface.co/microsoft · https://huggingface.co/openai/gpt-oss-20b
- **This repo:** https://github.com/Amitmishra98/.p

---

## 24. Disclaimer, Version Notes and Contributing

### Disclaimer - read before relying on this page

- **Fast-changing data:** Model names, parameters, context sizes, licenses, and benchmark numbers change quickly. This page is a snapshot (last updated **2026-09-14**) and may lag the newest releases.
- **Benchmarks are vendor-reported** and run on different harnesses. They are **not directly comparable** across models. Always verify on a live leaderboard and test on your own data.
- **"Open source" ≠ "open weight."** Many models here release *weights* but keep training data/code partially closed (Llama, Gemma, Kimi, DeepSeek). Only `OLMo 2`, `SmolLM3`, `Pythia`, and `Amber` are fully open (data + code + weights).
- **License caps & revenue terms:** Llama 4 (700M MAU), Kimi K3, Qwen3.8-2.4T, Hunyuan (100M MAU), LTX (<$10M ARR), MiniMax H3 (<$20M), and FLUX.2 [dev] all have conditions. **Read the license.**
- **Hosted API caveats:** Some APIs (e.g., DeepSeek) route through China; model license and API TOS can differ. Check before using sensitive data.

### Formatting conventions

ModelAtlas is one **single document** on purpose: the broadest answer comes first and the details follow. Concretely, our conventions are:

- A short **"Quick answers"** block up front, so a new reader understands the scope in one glance.
- **Section headings phrased as real questions** (`What is the best open-source AI model in 2026?`, `How much VRAM do I need?`).
- **Comparison tables** wherever the content is a list of numbers — a grid beats prose when you are comparing twenty models.
- A **glossary** and an **FAQ** for terminology and for the questions we are asked most often.
- **Original sources first:** every model links to its card, repository or paper; numbers we have not checked ourselves are labelled vendor-reported `(v.r.)`.
- **Plain-data copies of the same content:** [`llms.txt`](llms.txt) for AI assistants, [`data/models.json`](data/models.json) + [`data/models.csv`](data/models.csv) as a structured registry — see [Appendix B](#appendix-b-how-this-guide-is-organized-and-kept-current).

> The model landscape is dynamic. To keep this reference accurate, the "Last updated" date, version number, and vendor links should be refreshed on each revision — this repo does it automatically via [GitHub Actions](.github/workflows/refresh.yml).

### Contributing

This is a **living directory**. To add or update a model:

1. Fork this repo and edit `README.md`.
2. Add/replace the model's section with accurate links and numbers (cite the source).
3. Keep the table columns consistent — and update the same row in `data/models.json`.
4. Open a pull request against the repository's default branch.

See [CONTRIBUTING.md](CONTRIBUTING.md) for the full guide.

---

## Appendix A - Benchmarks and methodology explained

Because "which model is best?" is meaningless without a benchmark, here is what each number actually measures.

### Reasoning and knowledge
| Benchmark | What it measures | Typical open leaders (2026) |
|---|---|---|
| **MMLU-Pro** | Broad knowledge + reasoning (multi-step, 10 choices) | DeepSeek V4 (88+), Qwen3.8 (v.r.) |
| **GPQA Diamond** | PhD-level science (Google-proofed) | DeepSeek V4 (~88), Qwen3.6 |
| **AIME 2024/25/26** | Competition math | DeepSeek R1, Qwen3, Kimi K2.6 |
| **HLE (Humanity's Last Exam)** | Expert-level, tool-augmented | Kimi K2.6 (54 with tools, v.r.) |
| **ARC-AGI-2** | Novel problem solving (cheap-o-meter) | frontier MoEs only |
| **MATH-500** | Math word problems | many ≥93 (saturated) |

### Coding
| Benchmark | What it measures | Leaders |
|---|---|---|
| **SWE-bench Verified** | Real GitHub issue fixing (agentic, needs tools) | DeepSeek V4 (~84 v.r.), Kimi K2.6, GLM-5.2 |
| **SWE-bench Pro** | Harder, multi-file real issues | Kimi K2.6 (~58 Pro, ties GPT-5.5-class v.r.) |
| **Terminal-Bench** | Terminal/CLI operations | Kimi, GLM, Devstral |
| **LiveCodeBench** | Fresh competitive programming (leak-resistant) | frontier MoEs |
| **HumanEval** | Function completion (saturated — ignore alone) | everything ≥90 |
| **CodeArena** | Agentic coding arena | Qwen3.8 ranked #4 (v.r.) |

### Instruction / preference / agents
| Benchmark | What it measures | Notes |
|---|---|---|
| **Arena Elo (LM Arena)** | Blind human preference | The most "real-world" signal; open top ≈ 1450+ in 2026 |
| **Artificial Analysis IQ** | Aggregated intelligence index | Independent, token-efficiency aware |
| **Chatbot Arena** | Human battles | https://lmarena.ai |
| **OSWorld / OSWorld-like** | Computer-use agents | Qwen3.5/3.8 & Kimi lead open (v.r.) |
| **PaperBench / BabyVision** | Research + vision-agent tasks | v.r. marketing claims — verify |

### Embeddings / retrieval
| Benchmark | What it measures | Open leaders |
|---|---|---|
| **MTEB (multilingual)** | 8 tasks: retrieval, rerank, classification, STS… | Qwen3-Embedding-8B (~70.6), NV-Embed-v2 (~72 EN) |
| **Open ASR Leaderboard** | Speech WER | Canary-Qwen-2.5B, Parakeet TDT |

### How to read vendor numbers safely
1. **Prefer independent aggregators** (Artificial Analysis, Arena Elo, MTEB) over model cards.
2. **Match the harness:** SWE-bench scores depend on the agent scaffold, not just the model.
3. **Test on your own data.** Benchmarks leak, saturate, and skew to English/code.
4. **Watch context:** a 1M-context score at 8K context is not comparable.
5. Check the date of the eval — 2025 numbers are not 2026 numbers.

---

## Appendix B - How this guide is organized and kept current

A directory only helps if people can actually find and reuse it, so we made two structural decisions and stuck to them:

1. **Everything lives in one document.** The whole directory is `README.md` — no blog posts, no pagination, no copy-paste drift between pages. Deep links (anchors) go straight to the section a reader wants.
2. **The same content is published in plain-data formats.** [`llms.txt`](llms.txt) is a one-page index that AI assistants read; [`data/models.json`](data/models.json) and [`data/models.csv`](data/models.csv) are the same tables for scripts and dashboards.

### Our conventions

1. **Headings read like questions** — "How much VRAM do I need?", "Which license lets me sell this?" — because that is how people (and search) actually look things up.
2. **Comparisons live in tables** — model, org, params, license, context: one row per model. Tables are also the easiest format to regenerate from `data/models.json`, which is exactly what the [generator script](../scripts/generate_registry.py) does.
3. **Freshness is automated.** [`.github/workflows/refresh.yml`](.github/workflows/refresh.yml) reminds us weekly to re-verify links and bump the "Last updated" date; the [changelog](CHANGELOG.md) records what each pass changed.
4. **Sources are linked, always.** If a number comes from a vendor press release and we could not reproduce it, it says so right next to the number.

### Machine-readable copies

| File | What it is |
|---|---|
| [`llms.txt`](llms.txt) | One-page index of this directory for AI assistants (llmstxt.org convention) |
| [`data/models.json`](data/models.json) | Every model as structured data: org, params, context, license, category, links, Ollama tag |
| [`data/models.csv`](data/models.csv) | Same registry as a CSV (generated from the JSON) |
| [`docs/README.md`](docs/README.md) | Repo map and maintenance notes for contributors |

### Repository metadata (set once, on GitHub)

- Topics: `ai`, `llm`, `open-source`, `machine-learning`, `deep-learning`, `large-language-models`, `ollama`, `huggingface`, `moE`, `rag`, `benchmarks`, `generative-ai`, `fine-tuning`, `local-llm`
- Description: "ModelAtlas — the open-source AI model directory: every open-weight LLM, MoE, reasoning, coding, vision, image, video, TTS/ASR, embedding and agent model compared, with licenses, VRAM guides, benchmarks, free API tiers and one-command local install (2026)."
- The README header and footer carry version/date/license metadata.

> **Try it:** `git clone https://github.com/Amitmishra98/.p` — the whole directory renders on the GitHub page itself; there is no build step.

## Appendix C - Realtime Voice, Omni and Speech-to-Speech Models

2026's hottest category: talk to a model out loud and hear it answer in under 300 ms — no text in the middle. Two architectures: **cascaded** (ASR → LLM → TTS) and **native speech-to-speech** (one model, one latency). Everything below is open-weight.

| Model | Org | Size | Style | License | Notes |
|---|---|---|---|---|---|
| **Kimi-Audio** | Moonshot AI | 7B | Native audio LLM (understand+generate+converse) | Code MIT/Apache 2.0 mix (check weights) | 13M+ hrs training (v.r.); unified audio tasks; [GitHub](https://github.com/MoonshotAI/Kimi-Audio) |
| **Qwen2.5-Omni-7B** | Qwen | 7B | Native speech-to-speech (Thinker-Talker) | Apache 2.0 | The open omni reference; HF: `Qwen/Qwen2.5-Omni-7B` |
| **GLM-4-Voice** | Z.ai | 9B | Native + flow-matching decoder | Apache 2.0 | Streaming; emotional control; HF: `zai-org/glm-4-voice-9b` |
| **Step-Audio / Step-Audio-2** | StepFun | 1.6B-11B | Speech-to-speech | Apache 2.0 | Step-Audio-Chat, 2-mini, R1.1 variants on HF; any-to-any |
| **MiniCPM-o 2.6** | OpenBMB | 8B | Omni (audio+vision+text) | Apache 2.0 (check) | All-in-one edge omni |
| **LLaMA-Omni / Mini-Omni / Freeze-Omni** | community | 1B-8B | Speech-to-speech research | MIT/Apache | Reference architectures |
| **CSM-1B** | Sesame | 1B | Conversational TTS | Apache 2.0 | The "voice presence" demo model |
| **Higgs Audio V3** | Higgs | — | Speech/audio | open (check) | Served via SGLang-Omni |
| **Voxtral 4B TTS / MOSS-TTS / VoxCPM2** | Mistral / community | 0.5-4B | Streaming TTS | open | New streaming TTS wave |

**Serving stacks for voice AI (open):** [vLLM-Omni](https://github.com/vllm-project/vllm) (production streaming/batching; serves Qwen3-TTS, fishaudio S2, CosyVoice3, Voxtral…) · SGLang-Omni (Higgs Audio, Fish S2 Pro) · llama.cpp-omni (GGUF on CPU/Metal) · LocalAI (many TTS engines behind one server).

**Build notes:** latency budget = ASR chunk + TTFT + streaming synthesis; for <500 ms total prefer native S2S (Qwen2.5-Omni/GLM-4-Voice) over cascades; voice-clone consent is a legal requirement in many jurisdictions, not a feature toggle.

---

## Appendix D - Document AI, OCR and PDF Tools

Every RAG pipeline eventually hits PDFs. In 2026 the open stack reads anything: scans, tables, math, handwriting-adjacent, multi-page.

| Tool / model | Org | License | Best at |
|---|---|---|---|
| **olmOCR** | Allen AI | Apache 2.0 | LLM-based OCR + document understanding (vLLM-servable) |
| **GOT-OCR2** | StepFun | Apache 2.0 | Plain/formatted text, tables, formulas, music notation (~580M) |
| **InternVL3 (8B-78B)** | OpenGVLab | Apache 2.0 (8B/14B/38B); check 78B | OCR + multilingual document VQA at scale |
| **Qwen2.5-VL (3B-72B)** | Qwen | Apache 2.0 | Docs, charts, screenshots, video frames |
| **Granite 4.0 3B Vision** | IBM | Apache 2.0 | Compact governed document vision |
| **Florence-2-Large** | Microsoft | MIT | Region detection + captioning + OCR (~0.8B) |
| **Nougat** | Meta | CC-BY-NC | PDF→LaTeX for scientific papers (research-only!) |
| **Chandra (~3B)** | Datalab | Apache 2.0 | Layout + markdown + structured blocks, local/vLLM |
| **MinerU 2.5** | OpenDataLab | AGPL 3.0 | Best table extraction pipeline (AGPL: comply or buy) |
| **Surya** | Datalab | GPL + commercial | Multilingual layout + reading order |
| **Marker** | Datalab | GPL + commercial | PDF→Markdown pipeline with the biggest user base |
| **DocLayout-YOLO** | — | AGPL 3.0 | Layout detection only (50M) |
| **ColPali v1.3 / ColQwen2** | Vidore/ILLU | MIT / Apache | Page-level retrieval *without OCR* (visual embeddings) |
| **LightOnOCR / MonkeyOCR / OCRFlux / RolmOCR** | community | Apache/MIT mix | Fast or specialized OCR variants |

**License trap:** Marker/Surya/MinerU are (A)GPL — great locally, but a SaaS wrapper needs the commercial license. Apache/MIT picks: olmOCR, GOT-OCR2, Chandra, Qwen2.5-VL.

---

## Appendix E - Free and Low-Cost API Tiers for Testing Open Models

Want to try before you buy a GPU? (Numbers move — verify in each dashboard; sources: provider docs, June-July 2026 surveys.)

| Provider | Free tier (approx) | Notable models | Card needed? |
|---|---|---|---|
| **Google Gemini API / AI Studio** | ~1,500 req/day tier, generous free tokens | Gemini 2.5 Flash-class (proprietary) | No |
| **Groq** | 30 RPM / ~14.4K req/day | Llama 3.3 70B, Qwen, gpt-oss, Kimi K2 | No |
| **Cerebras** | ~30 RPM / 14.4K req/day | Llama variants (very fast) | No |
| **OpenRouter** | `:free` models: ~20 RPM, 50 RPD (more with $10 credits) | DeepSeek R1, Qwen3-Coder-480B, Llama 4 Scout and 28+ more | No |
| **DeepSeek API** | signup grant (historically ~5M tokens) | DeepSeek V4 / V3.2 | No |
| **Mistral (La Plateforme)** | Codestral free key (30 RPM); limited tiers | Codestral, Devstral | Eventually |
| **Hugging Face Inference** | serverless few-hundred req/hr (<10B models); $0.10/mo credit | any small open model | No |
| **GitHub Models** | playground + rate-limited API | gpt-oss, Llama, Qwen, Mistral | No (GH account) |
| **Cohere** | 1,000 calls/month | Command R+ (not fully open) | Yes |
| **Together / Fireworks** | $1 one-time credit each | 200+ open models | Yes |

**Playbook:** OpenRouter for breadth with one key → Groq/Cerebras when latency matters → DeepSeek/GLM/ Qwen official APIs for the cheapest frontier tokens → HF serverless to test any new small model. Treat free tiers as dev-only: rate caps and data-use terms make them unsuitable for production customer data.

---

## Appendix F - GPU and Hardware Buying Guide

VRAM is destiny (§16). Approx. 2026 street prices — check locally, they move.

| GPU | VRAM | Fits (Q4) | Approx. price | Verdict |
|---|---|---|---|---|
| RTX 5090 | 32 GB | 27-31B dense, up to ~70B with offload | ~$2,000-2,600 | The consumer king; huge bandwidth |
| RTX 4090 / 3090 Ti | 24 GB | 27-31B dense | $1,500-2,200 (used 3090 ~$800-1,000) | Best 24GB buys; 3090 used = value king |
| RTX 5080 / 5070 Ti | 16 GB | 14B, 20-24B MoE | $750-1,100 | New-gen 16GB sweet spot |
| RTX 5060 Ti 16 GB | 16 GB | same | ~$430 | Cheapest new 16GB |
| Intel Arc B580 | 12 GB | 14B tight | ~$250 | Budget pick if software support suffices |
| RTX 3060 12GB / 4060 Ti 16GB | 12-16 GB | 8-14B | $300-500 | Entry local AI |
| RTX 5070 (12 GB) / 4060 (8 GB) | 8-12 GB | ≤8B | $300-550 | Fine for 8B |
| H100 / H200 / B200 | 80-192 GB | 120B+ MoE, training | cloud/$25k+ | Data center; rent, don't buy |
| Apple M4/M5 Max/Ultra (Mac Studio) | 64-512 GB unified | 70B+ dense at Q4 (memory-bound, ~20-40 tok/s) | $4k-10k | Best single-box big-context option |
| Used datacenter (P100 16GB / A6000 48GB) | 16-48 GB | up to 70B splits | varies | e-waste bargains with caveats (no FP16 on P100 etc.) |

**Budget build recipes (2026):**
- **$0 extra** — you already own it: Ollama + Qwen3:4b/8B on CPU (16GB RAM) or gpt-oss-20b.
- **~$1,500 new** — RTX 5070 Ti 16GB or 5060 Ti×2 (NVLink not needed; use tensor-split via llama.cpp/vLLM) → 14-32B models.
- **~$2,500 new** — RTX 5090 32GB → 27-31B dense fast + MoE 70B-class at Q4 with offload.
- **~$1,000 used** — 2× used RTX 3090 (24GB each, 48GB total) → 70B Q4 with tensor parallelism; the community favorite.
- **Rent instead** — RunPod/Vast/Together for anything ≥120B: $/hr GPU beats $/week idle.
- **Mac users** — 64GB+ M-series unified memory runs 30-70B Q4 comfortably; MLX tooling is excellent.

**Buying rules:** (1) VRAM > speed > brand; (2) check bandwidth (5090 ~1.8TB/s, 4090 ~1TB/s); (3) 2× smaller GPUs beat 1× bigger for MoE; (4) never buy <12GB new in 2026; (5) for training buy compute-hours, for inference buy VRAM.

---

## Appendix G - Changelog

Full history in [CHANGELOG.md](CHANGELOG.md).

| Date | Version | What changed |
|---|---|---|
| 2026-09-09 | 2026.09 (this refresh) | Link-audit pass: verified ~40 Hugging Face ids/orgs live (fixed Qwen3.5→`Qwen3.5-397B-A17B`, Mistral Large 3, Wan 2.2, TRELLIS.2, Gemma 4 case, Qwen3-TTS, removed dead ids); fixed GitHub-anchor links across 56 heading renames; added Kimi K2.7-Code, Hunyuan Hy3, Seed-OSS-36B, Qwen3.5-9B/4B, Qwen3.6-35B-A3B; corrected multimodality of Qwen3.5/3.6/3.8 and Kimi K2.6; license corrections (MiniMax M2.5, Moonshot >$20M term, Qwen3.8-2.4T terms); new Appendices C-G (voice/omni, document AI, free tiers, GPU buying, changelog); new arXiv references; registry 88 → 101 models; features-at-a-glance panel; browse-by-category index (14 categories); Summer 2026 release wave by category; per-category breakdown added to data/models.json |
| 2026-09-09 | 2026.09 (branding) | Repo renamed on the page to "ModelAtlas — the open-source AI model directory (2026 edition)"; new About section (§1) and [ABOUT.md](ABOUT.md) with the student-teacher fellowship story; new top-level section "Where to get free AI APIs (Sept 2026)" with sign-up links; AI-flavoured wording removed (Quick answers, §24, Appendix B, Colophon rewritten in a plainer voice); badge count 101; links re-verified |
| 2026-09-09 | 2026.09 (initial) | Full ModelAtlas rebuilt: sections 1-24 + appendices A-B, llms.txt, structured registry, weekly refresh workflow |

## Colophon

*ModelAtlas: the open-source AI model directory (2026 edition)* is compiled by the **ModelAtlas fellowship** — students who write, teachers who check, nobody who profits (see [§1](#1-about-modelatlas-and-the-team-behind-it) and [ABOUT.md](ABOUT.md)). It lives in the public GitHub repository [`Amitmishra98/.p`](https://github.com/Amitmishra98/.p), with machine-readable copies in [`llms.txt`](llms.txt), [`data/models.json`](data/models.json) and [`data/models.csv`](data/models.csv).

**Cite this work:**
> ModelAtlas Fellowship. *ModelAtlas: the open-source AI model directory (2026 edition)*. Version 2026.09, September 2026. https://github.com/Amitmishra98/.p

**Our rules, short version:** every model links to its original source; numbers we did not measure ourselves are marked *(v.r.)*; every snapshot is dated; and when we get something wrong we fix it fast. Corrections are welcome as issues — see [CONTRIBUTING.md](CONTRIBUTING.md).

**Where the numbers come from:** model cards on [Hugging Face](https://huggingface.co), official GitHub releases, arXiv papers, vendor documentation, and the live leaderboards we link to in [§19](#19-where-to-explore-models-hubs-and-leaderboards) — [Arena](https://arena.ai/leaderboard), [Artificial Analysis](https://artificialanalysis.ai), SWE-bench and MTEB. How we interpret them is explained in [Appendix A](#appendix-a-benchmarks-and-methodology-explained).

**Useful?** Star the repo, open an issue with a correction, or point your classmates here — that is how a volunteer project stays alive.

**Arrived from a search engine?** You are probably looking for one of these, and all of them are answered above: *best open-source LLM 2026 · open-source AI models list · free AI model download · run AI locally · free AI API tiers · VRAM requirements · open-source AI licenses · AI agent frameworks · best local LLM · MoE models explained · realtime voice AI open source · open-source OCR document AI · best GPU for local LLM · Qwen3.8 · Kimi K2.7 · GLM-5.2 · DeepSeek V4 · Hunyuan Hy3.*

---

*Maintained by the ModelAtlas fellowship (students and teachers) · Version 2026.09 · Last verified 2026-09-14 · Document text CC-BY-4.0 — every model keeps its own license.*
