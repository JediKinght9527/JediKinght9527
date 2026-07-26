# Hi, I'm 龙虎山大师兄 👋

I build **AI tools that act on the real world** — not just chatbots. Two things I care about:

- 🔒 **Privacy infrastructure for the LLM era** — your code and secrets shouldn't leak just because you use AI tools
- 🎮 **AI-native game-engine tooling** — natural language as a first-class interface to Unreal Engine

## 🚀 Projects

### [DataVeil](https://github.com/JediKinght9527/dataveil)

[![CI](https://github.com/JediKinght9527/dataveil/actions/workflows/ci.yml/badge.svg)](https://github.com/JediKinght9527/dataveil/actions/workflows/ci.yml)

Privacy-first local gateway for LLM APIs. Sits between your AI tools (Claude Code, Cursor, Codex) and LLM providers — detects API keys, internal domains, JWTs, SSH keys and PII in your prompts, swaps them for semantic placeholders, and rehydrates the response in real time (including SSE streams). Your secrets never leave your machine.

`Python` `FastAPI` `AES-256-GCM vault` `SSE stream rehydration` `MCP server`

### [Cindra (灰星)](https://github.com/JediKinght9527/cindra)

Natural-language control for Unreal Engine 5. One sentence — in Chinese or English — edits scenes, answers UE questions via RAG, writes project-style C++, or builds Blueprint graphs. An agent loop plans → calls engine tools → **reads back actual engine state to verify**, instead of assuming success. Mock/real dual backend: logic verified offline on a Mac, then driven against a live UE 5.5 editor on Windows by swapping only the transport layer.

`Python` `Claude agent loop` `UE5 remote execution` `RAG` `Blueprint codegen`

## 🛠️ How I work

- **Verify, don't assume** — agents read back real state after acting; CI runs lint + types + tests on every push
- **Mock-first, engine-second** — deterministic offline validation before touching a live engine
- **Local-first** — privacy tooling with no servers, no telemetry

## 📊 Stats

![GitHub Stats](https://github-readme-stats.vercel.app/api?username=JediKinght9527&show_icons=true&theme=default&hide_rank=true)

---

<details>
<summary><b>中文简介</b></summary>

<br>

我做**能对真实世界产生动作的 AI 工具**，不只是聊天机器人：

- **[DataVeil](https://github.com/JediKinght9527/dataveil)** — LLM API 隐私网关。挡在 AI 编程工具和大模型之间，自动检测并替换 prompt 里的密钥、内网域名、PII，流式响应实时还原。你的秘密不出本机。
- **[Cindra (灰星)](https://github.com/JediKinght9527/cindra)** — 自然语言操控 UE5。一句话改场景、问 UE、写 C++、搭蓝图；agent 操作后读回引擎真实状态自检，而非"自信地以为成了"。

工作方式：mock 先行离线验证 → 真实引擎联调；CI 全绿；本地优先、零遥测。

</details>
