# JediKinght9527

Python · FastAPI · SQLite · Claude/MCP · Unreal Engine 5

I build measurement and control tools: instruments that measure LLM infrastructure honestly, and agents that drive a real engine and read state back to verify it.

## precision-bench

[![CI](https://github.com/JediKinght9527/precision-bench/actions/workflows/ci.yml/badge.svg)](https://github.com/JediKinght9527/precision-bench/actions/workflows/ci.yml)
[![coverage](https://img.shields.io/codecov/c/github/JediKinght9527/precision-bench?label=coverage)](https://github.com/JediKinght9527/precision-bench)
[![release](https://img.shields.io/github/v/release/JediKinght9527/precision-bench?label=release)](https://github.com/JediKinght9527/precision-bench/releases)

Load testing, prompt-cache verification, and degradation detection for LLM relay APIs. Sends real traffic at a channel, measures latency from the SSE stream (TTFT / TPOT / ITL / E2E, P50–P99.9), and normalizes cache usage across OpenAI, Anthropic, DeepSeek, Kimi, Qwen, GLM, and Gemini.

- open-loop mode with **coordinated-omission correction** (the wrk2 / k6 methodology)
- active fixed-prefix cache probe: catches relays that report cached tokens without serving them faster
- eight scored quality dimensions with per-channel baseline and output-fingerprint comparison
- goodput against SLO targets, cost split across input / output / cache-read / cache-write
- SQLite (WAL) storage, CSV/JSON/Markdown export, one-click channel verification report
- 88 tests, 63.6% coverage, CI green, non-root Docker image

`Python` `FastAPI` `ECharts` `SQLite` `Docker` `SSE`

## ue5-ai-commander

Natural-language control for Unreal Engine 5.7. One sentence — Chinese or English — edits scenes, answers engine questions over RAG, writes project-style C++, or assembles Blueprint graphs. 43 MCP tools, Tripo3D text-to-3D bridge, cinematic camera control.

The agent loop is **plan → act → read back actual engine state** rather than assuming success. Mock/real dual backend: logic is verified offline on a Mac against a mock, then driven against a live editor on Windows by swapping only the transport layer. 103 self-checks.

`Python` `C++` `MCP` `RAG` `PCG`

## Principles

- Measure before claiming. Percentiles from a monotonic clock, formulas documented and recomputable from raw samples.
- Verify, don't assume. After acting, read the real state back.
- Mock first, engine second. Deterministic offline validation before touching a live system.
- Least surprise. No telemetry, no hidden network calls, secrets never written to disk.

---

<details>
<summary>中文</summary>

做**测量工具**与**控制系统**：一边是能把 LLM 渠道真实性能测准的检定台，一边是能驱动真实引擎、并读回状态自检的 agent。

- **[precision-bench](https://github.com/JediKinght9527/precision-bench)** — LLM 中转 API 压测 / 缓存验真 / 降智检测。SSE 打点测 TTFT、TPOT、ITL、E2E 与 P50–P99.9；定频模式带 coordinated omission 修正；固定长前缀主动探缓存，揪出「上报命中但不加速」的假缓存；八个维度判分 + 渠道基线对比。88 测试、63.6% 覆盖率、CI 全绿、非 root 镜像。
- **[ue5-ai-commander](https://github.com/JediKinght9527/ue5-ai-commander)** — 自然语言操控 UE 5.7。一句话改场景、问引擎、写 C++、搭蓝图；43 个 MCP 工具。agent 循环是「计划 → 执行 → 读回引擎真实状态自检」，而不是「自信地以为成了」。mock / 真实双后端，103 项自检。

工作原则：先测量再下结论；执行后读回真实状态；mock 先行离线验证；不埋点、不偷偷联外网、密钥不落盘。

</details>
