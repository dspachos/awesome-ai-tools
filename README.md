# Awesome AI Tools — 2026

> A curated, opinionated map of the **user-facing AI-tools landscape (as of 2026-06-19)** — CLI coding agents, OpenClaw-style "always-on" personal assistants, computer-use & browser agents, and agent frameworks / SDKs.
>
> Built from a four-track research survey with a source-verification pass, refreshed weekly. Every entry is sourced. Star counts are point-in-time; 37 of 40 repos verified directly from the GitHub API (the rest marked `≈` / `unverified`). See [Methodology & Caveats](#methodology).

<div align="center">

**69 tools** · **4 overlapping layers** · **Updated 2026-06-19**

</div>

> **Status badges:** ![active](https://img.shields.io/badge/active-brightgreen) · ![GA](https://img.shields.io/badge/GA-brightgreen) · ![beta](https://img.shields.io/badge/beta-orange) · ![announced](https://img.shields.io/badge/announced-blue) · ![maintenance](https://img.shields.io/badge/maintenance-yellow) · ![uncertain](https://img.shields.io/badge/uncertain-yellow) · ![archived](https://img.shields.io/badge/archived-lightgrey) · ![dead](https://img.shields.io/badge/dead-red)

---

## Table of Contents

- [The Landscape in One Screen](#landscape)
- [Quick Picks](#quick-picks)
- [CLI Coding Tools](#cli)
- [Always-On Personal AI Assistants](#assistants)
- [Computer-Use & Browser Agents](#computer-use)
- [Agent Frameworks & SDKs](#frameworks)
- [Desktop Apps & IDEs](#desktop)
- [Agent Managers & Multiplexers](#agent-managers)
- [Shutdowns & Archived](#shutdowns)
- [Trending Repos Snapshot](#trending)
- [This Week](#this-week)
- [Methodology & Caveats](#methodology)
- [License](#license)

---

<a name="landscape"></a>
## 🧭 The Landscape in One Screen

The clearest mental model: **the CLI coding agents are the substrate; the OpenClaw-style always-on personal assistants are the new application layer that orchestrates them.** As of 2026-06-19, the landscape has consolidated around four overlapping layers, with the headline story being a genuinely new product category — self-hosted, chat-reachable, persistent, proactive, computer-controlling assistants.

| # | Layer | Key fact | State of play |
|---|-------|----------|---------------|
| 1 | **CLI coding agents** | Table-stakes layer | Vendor CLIs (Claude Code, Codex, Antigravity CLI [replaces dead Gemini CLI], Cursor, Copilot, Kiro) + OSS (Aider, Crush, Qwen Code, OpenCode ~176k★). Gemini CLI shut down Jun 18. Pricing converged on subscription-plus-credits. |
| 2 | **OpenClaw-style always-on assistants** ⭐ | The new category | OpenClaw (~370k★) defined it: self-hosted, chat-reachable, persistent, proactive, self-hackable. Direct OSS peers: Memoh, OwnPilot, Lethe. Proprietary answers: Claude Cowork+Dispatch, Perplexity Computer, Gemini Spark. |
| 3 | **Computer-use / browser agents** | Crossing human parity (self-reported) | Simular Agent S3 first vendor-reported OSWorld crossing (72.60%, best-of-N). Standalone browser agents absorbed into assistants — Mariner dead, Operator→ChatGPT agent. Browser Use (~99k★) is the dominant OSS primitive. |
| 4 | **Agent frameworks / SDKs** | Three-vendor race | OpenAI Agents SDK, Anthropic Agent SDK + Skills (~152k★, 'surged past MCP'), Google ADK 2.0. AutoGen→Microsoft Agent Framework 1.0 GA. LangGraph 1.0, CrewAI, Cline (~63k★). |

**Three macro-trends cut across all four layers:**

1. **Absorption** — standalone browser-agent products are being folded into first-party assistants (Operator → ChatGPT agent; Project Mariner → Gemini Spark).
2. **"Skills" becoming the standard capability interface** — Anthropic Agent Skills, OpenClaw `SKILL.md`, and Cline/Cursor/Google formats are converging on the same capability-pack shape.
3. **A self-hosted-vs-managed split** — OSS offers data sovereignty + self-hackability at the cost of setup and real security risk; proprietary offerings add polish + a kill switch but data lives on vendor infra.

---

<a name="quick-picks"></a>
## ⚡ Quick Picks

Looking for a specific use case? These are the top picks across each category:

| Use case | Recommended | Why |
|---|---|---|
| Best reasoning-quality CLI coding agent | **[Claude Code](https://github.com/anthropics/claude-code)** ![active](https://img.shields.io/badge/active-brightgreen) | Top-tier reasoning; fully agentic with subagents, hooks, MCP, headless + background agents. |
| Best free / open-source CLI | **[Qwen Code](https://github.com/QwenLM/qwen-code)** ![active](https://img.shields.io/badge/active-brightgreen) | Claude-Code feature-parity (subagents, skills, plan mode) on open models — fully free with BYO-key. |
| Mature OSS pair-programmer | **[Aider](https://github.com/Aider-AI/aider)** ![active](https://img.shields.io/badge/active-brightgreen) | Battle-tested git-integrated loop; hosts the widely-cited LLM coding leaderboard. |
| Self-hosted always-on personal assistant | **[OpenClaw](https://github.com/openclaw/openclaw)** ![active](https://img.shields.io/badge/active-brightgreen) | The category reference: 20+ chat surfaces, persistent memory, proactive heartbeats, self-hackable skills. |
| Browser automation library | **[Browser Use](https://github.com/browser-use/browser-use)** ![active](https://img.shields.io/badge/active-brightgreen) | Dominant OSS Playwright-based primitive (~100k★); commercial 'Box' adds 24/7 cloud runs. |
| Type-safe Python agent framework | **[PydanticAI](https://github.com/pydantic/pydantic-ai)** ![beta](https://img.shields.io/badge/beta-orange) | FastAPI-feeling, fully typed, model-agnostic with strong OTel/Logfire observability. |
| Multi-agent orchestration (durable graphs) | **[LangGraph](https://github.com/langchain-ai/langgraph)** ![GA](https://img.shields.io/badge/GA-brightgreen) | 1.0 GA durable graph orchestration with first-class human-in-the-loop interrupts + memory. |
| Production agent SDK (OpenAI stack) | **[OpenAI Agents SDK](https://github.com/openai/openai-agents-python)** ![active](https://img.shields.io/badge/active-brightgreen) | Handoffs, sandbox agents, guardrails, tracing, realtime voice — productionized Swarm successor. |
| Best AI-native IDE | **[Cursor](https://cursor.com)** ![active](https://img.shields.io/badge/active-brightgreen) | $100M+ ARR, best @codebase indexing, Composer multi-file edits, Background Agents, BugBot PR review. |
| Fastest editor + zero lock-in | **[Zed](https://github.com/zed-industries/zed)** ![active](https://img.shields.io/badge/active-brightgreen) | Rust-native sub-second cold start, open agent protocol, BYO-key, native multiplayer. 85k+ stars. |

---

<a name="cli"></a>
## ⌨️ CLI Coding Tools

The most mature and crowded segment. Splits into **vendor CLIs** (closed, subscription-tied), **open-source multi-provider agents**, and **AI-native terminals**. **Pricing has converged on subscription-plus-credits**. ⚠️ Gemini CLI was **shut down June 18** — replaced by closed-source Antigravity CLI.

### Vendor CLIs (proprietary)

- **[Claude Code](https://github.com/anthropics/claude-code)** ![active](https://img.shields.io/badge/active-brightgreen) — Reasoning-quality leader (v2.1.183). Fully agentic: multi-file edits, sandboxed bash, subagents, MCP, hooks, headless + background agents. Auto-mode safety (blocks destructive git/terraform commands). Split-credit pricing (Jun 15, 2026). · `Proprietary` · ≈133.3k★ *GitHub API, 2026-06-19*
- **[Codex CLI](https://github.com/openai/codex)** ![active](https://img.shields.io/badge/active-brightgreen) — Sandboxed agentic execution; Rust rewrite. Bundled with ChatGPT plans or API-metered. Top vendor CLI on Terminal-Bench. · `Apache-2.0` · Rust · ≈92.1k★ *GitHub API, 2026-06-19*
- **[Gemini CLI](https://github.com/google-gemini/gemini-cli)** ![dead](https://img.shields.io/badge/dead-red) — DEAD. Shut down June 18, 2026. All consumer accounts (free/Pro/Ultra) received HTTP 410 Gone. Replaced by closed-source Antigravity CLI (agy). 105k-star OSS project orphaned. Enterprise customers retain access via paid Gemini Enterprise Agent Platform API keys. · `Apache-2.0` · TypeScript · ≈105.4k★ *GitHub API, 2026-06-19 — SHUT DOWN Jun 18*
- **[Antigravity CLI](https://antigravity.google)** ![active](https://img.shields.io/badge/active-brightgreen) — Replaces the dead Gemini CLI. Closed-source Go binary (agy) with async multi-agent orchestration. Shares architecture with Antigravity 2.0 desktop app. Supports Agent Skills, Hooks, Subagents, Extensions. No source code, tighter quotas, no multi-model routing. · `Proprietary (closed source)` · Go
- **[Junie](https://blog.jetbrains.com/junie/2026/06/junie-coding-agent-out-of-beta/)** ![GA](https://img.shields.io/badge/GA-brightgreen) — JetBrains AI coding agent — GA June 2026. Advanced Plan mode (structured doc with PRD/tech design/delivery/testing tabs), PR review with project context, long-running tasks. Uses real JetBrains debugger and project tools. Works in IDE + terminal. · `Proprietary`
- **[Cursor CLI](https://cursor.com/docs/cli/overview)** ![active](https://img.shields.io/badge/active-brightgreen) — Agent / Plan / Ask modes + Cloud Agent handoff. Tightest parity with Cursor editor. Teams pricing refreshed Jun 2026. · `Proprietary`
- **[GitHub Copilot CLI](https://github.com/features/copilot/cli)** ![active](https://img.shields.io/badge/active-brightgreen) — Deepest GitHub-native integration. /fleet parallel subagents, autopilot, AGENTS.md skills, native MCP. Usage-metered AI Credits (Jun 1, 2026). · `Proprietary`
- **[Kiro CLI](https://kiro.dev/docs/cli/migrating-from-q/)** ![active](https://img.shields.io/badge/active-brightgreen) — Replaces the deprecated OSS Amazon Q Developer CLI (OSS→closed). NL→bash, >500-tool autocomplete, custom agents. First-party AWS/Bedrock/IAM integration. · `Proprietary`

### Open-source multi-provider agents

- **[Aider](https://github.com/Aider-AI/aider)** ![active](https://img.shields.io/badge/active-brightgreen) — Maturest community OSS tool. Git-integrated pair-programming loop, repo map, auto-commits. Host of the widely-cited LLM coding leaderboard. · `Apache-2.0` · Python · ≈46.5k★ *GitHub API, 2026-06-19*
- **[Crush](https://github.com/charmbracelet/crush)** ![active](https://img.shields.io/badge/active-brightgreen) — Best-in-class TUI/UX, broadest provider matrix out of the box. · `OSS (verify exact)` · Go
- **[Qwen Code](https://github.com/QwenLM/qwen-code)** ![active](https://img.shields.io/badge/active-brightgreen) — Self-described Claude-Code feature-parity: subagents, agent teams, skills/hooks, MCP, plan mode, computer use. Pairs open model + open framework. · `Apache-2.0` · Node.js · ≈25.4k★ *GitHub API, 2026-06-19*
- **[OpenCode](https://github.com/anomalyco/opencode)** ![active](https://img.shields.io/badge/active-brightgreen) — Highest-traction OSS terminal coding agent. Multi-session parallel agents, desktop beta. Copilot/OpenAI login. · `OSS` · TypeScript · ≈176.2k★ *GitHub API, 2026-06-19*

### AI-native terminals & legacy

- **[Warp](https://github.com/warpdotdev/warp)** ![active](https://img.shields.io/badge/active-brightgreen) — AI-native terminal — replaces the shell itself (NL→bash, block-based dev env), not a coding agent running inside one. · `Client AGPL-3.0 / server proprietary` · Rust · ≈62.0k★ *GitHub API, 2026-06-19*
- **[Continue](https://github.com/continuedev/continue)** ![archived](https://img.shields.io/badge/archived-lightgrey) — ARCHIVED after final 2.0.0 release (VS Code ext, cn CLI, JetBrains plugin). Historical: PR-checks agents. · `Apache-2.0` · TypeScript

> **CLI takeaways:** pricing is converging on subscription-plus-credits. The OSS field has standardized on multi-provider + BYO-key. Discontinuations matter (Q CLI → Kiro OSS→closed; Continue archived; Cody → Amp) — the deprecated tools are best avoided.

---

<a name="assistants"></a>
## 🤖 Always-On Personal AI Assistants — *the focal category*

> The defining new category of 2026: open-source, self-hosted, always-on personal AI assistants — chat-reachable, persistent, proactive, computer-controlling, self-extensible.

A tool qualifies for this category only if it satisfies all seven criteria: (a) self-hosted on user-owned hardware · (b) messaging-first reachability from existing chat apps · (c) persistent cross-session memory · (d) proactive heartbeat/cron behavior · (e) extensible skills with a registry · (f) broad multi-provider + local model routing · (g) computer/tool control.

### The OpenClaw wave (self-hosted OSS)

| Project | License · Lang | Stars | Focus |
|---|---|---|---|
| **[OpenClaw](https://github.com/openclaw/openclaw)** ![active](https://img.shields.io/badge/active-brightgreen) | `MIT` · TypeScript, Swift | ≈379.4k★ *GitHub API, 2026-06-19* | The reference open-source always-on personal assistant: self-hosted Gateway daemon, 20+ chat surfaces, markdown memory, 30-min heartbeats, self-hackable SKILL.… |
| **[Memoh](https://github.com/memohai/Memoh)** ![active](https://img.shields.io/badge/active-brightgreen) | `AGPL-3.0` · Go, Vue, Rust | — | Closest structural peer to OpenClaw. Each agent gets its own containerized 'cloud computer' (FS, desktop, browser, network, memory). Copyleft license. |
| **[OwnPilot](https://github.com/ownpilot/ownpilot)** ![active](https://img.shields.io/badge/active-brightgreen) | `MIT` · TypeScript | — | Explicitly OpenClaw-derived ('Claw' naming + SKILL.md). Strongest feature overlap incl. edge/IoT device control, soul agents, crews. |
| **[Lethe](https://github.com/atemerev/lethe)** ![active](https://img.shields.io/badge/active-brightgreen) | `MIT` · Rust (~50 MB binary) | — | Most architecturally distinctive: brain-inspired multi-actor design, self-modifying loop (per README). Narrower channel surface (Telegram + HTTP/SSE only). Bor… |
| **[Hermes Agent](https://github.com/NousResearch/hermes-agent)** ![active](https://img.shields.io/badge/active-brightgreen) | `Apache-2.0` · Python | ≈197.5k★ *GitHub API, 2026-06-19* | Self-improving always-on agent (launched Feb 2026). After each task, evaluates outcome and writes reusable skill files. `hermes claw migrate` imports OpenClaw … |

### Proprietary equivalents

Recent tech press frames these as the industry's answer to OpenClaw. *(Note: "response" here is press inference — not a confirmed vendor statement that these were built because of OpenClaw.)*

- **[Claude Cowork + Dispatch](https://claude.com/docs/cowork/overview)** ![GA](https://img.shields.io/badge/GA-brightgreen) — GA Apr 9, 2026. Full desktop + browser. Dispatch = persistent session messageable from phone, runs while away. Anthropic's explicit always-on answer (press-framed vs OpenClaw). · `Proprietary`
- **[Perplexity Computer / Personal Computer](https://www.perplexity.ai/hub/blog/everything-is-computer)** ![active](https://img.shields.io/badge/active-brightgreen) — 24/7 digital proxy. Personal Computer GA Mac May 7, 2026 on dedicated Mac mini, mobile remote, kill switch, audit trail. Pitched as 'a more secure OpenClaw'. · `Proprietary`
- **[Gemini Spark / auto-browse](https://blog.google/innovation-and-ai/products/gemini-app/next-evolution-gemini-app/)** ![announced](https://img.shields.io/badge/announced-blue) — Successor to shut-down Project Mariner. auto-browse shipping in Chrome; Gemini Spark = 24/7 personal agent (I/O 2026). WebMCP origin trial in Chrome 149. · `Proprietary`
- **Manus (Meta)** ![uncertain](https://img.shields.io/badge/uncertain-yellow) — Cross-platform chat-reachable autonomous agent; 'My Computer' desktop mode (Mar 2026). Meta moving to UNWIND the deal (Beijing divestiture order, Jun 2026). Future in flux. · `Proprietary`
- **Mistral Vibe (ex-Le Chat)** ![active](https://img.shields.io/badge/active-brightgreen) — Rebranded from Le Chat. Work Mode (agentic enterprise workflows, knowledge search, document synthesis) + Code Mode (GitHub integration, sandboxed sessions, PR workflow) + VS Code extension + CLI with skills/custom modes/subagents/teleport session migration. $14.99/mo Pro, $24.99/user/mo Team. · `Proprietary`

### Adjacent (explicitly NOT the same category)

- **[Goose](https://github.com/aaif-goose/goose)** ![active](https://img.shields.io/badge/active-brightgreen) — General-purpose developer/desktop agent, 70+ MCP extensions. Donated by Block to Linux Foundation / AAIF (Jun 2026). v1.38.0 released. NOT messaging-first — adjacent category, not a true OpenClaw peer. · `Apache-2.0` · Rust · ≈49.8k★ *GitHub API, 2026-06-19*
- **[SuperAGI](https://github.com/TransformerOptimus/SuperAGI)** ![active](https://img.shields.io/badge/active-brightgreen) — 2023-era web-UI autonomous-agent framework. Concurrent agents + toolkits marketplace. Web-UI-centric, not chat-reachable — adjacent, not a peer. · `Apache-2.0` · Python, Next.js · ≈15k★ *approx (class)*

---

<a name="computer-use"></a>
## 🖱️ Computer-Use & Browser Agents

Computer-use has stratified into three layers: an **API/builder layer**, a **first-party consumer-agent layer**, and a fast-moving **benchmark story**.

### Builder / API layer

- **[Anthropic Computer Use](https://github.com/anthropics/anthropic-quickstarts/blob/main/computer-use-demo/README.md)** ![beta](https://img.shields.io/badge/beta-orange) — Canonical 'screenshot → coordinate → action' loop in a Docker Linux+X11+VNC container. The de-facto builder starting point. Eligible for Zero Data Retention. · `API proprietary / demo OSS`
- **[Microsoft OmniParser v2](https://github.com/microsoft/OmniParser)** ![active](https://img.shields.io/badge/active-brightgreen) — Not an agent — pure-vision GUI-grounding module that 'tokenizes' screenshots. Paired with OmniTool (dockerized Win11 VM). · `OSS` · Python · ≈24.9k★ *GitHub API, 2026-06-19*
- **[Simular Agent S3](https://github.com/simular-ai/Agent-S)** ![active](https://img.shields.io/badge/active-brightgreen) — First VENDOR-REPORTED OSWorld crossing: 72.60% (best-of-N; single-pass 66%). Not on independent leaderboards. Full desktop + Android. Raised $21.5M. · `Apache-2.0` · Python · ≈11.9k★ *GitHub API, 2026-06-19*
- **[Browser Use](https://github.com/browser-use/browser-use)** ![active](https://img.shields.io/badge/active-brightgreen) — Widely-used OSS browser-agent library (Playwright). Rust-backed beta (0.13.0). Commercial 'Browser Use Box' = 24/7 Claude agent from Telegram/SSH (OpenClaw overlap). · `MIT` · Python · ≈99.5k★ *GitHub API, 2026-06-19*
- **[Skyvern](https://github.com/Skyvern-AI/skyvern)** ![active](https://img.shields.io/badge/active-brightgreen) — Enterprise browser-RPA replacement. Planner-Agent-Validator, native CAPTCHA + 2FA, SOC2/HIPAA. Workflow engine, not chat-reachable. · `AGPL-3.0` · Python · ≈21.9k★ *GitHub API, 2026-06-19*
- **[OpenHands](https://github.com/OpenHands/OpenHands)** ![active](https://img.shields.io/badge/active-brightgreen) — Self-hosted 'developer control center'. Runs its own agent OR Claude Code/Codex/Gemini. SDK + CLI + GUI + Agent Canvas (scheduled tasks, Slack/GitHub/Linear). · `MIT (core)` · Python · ≈77.7k★ *GitHub API, 2026-06-19*

### First-party consumer agents

- **[ChatGPT agent (ex-Operator/CUA)](https://chatgpt.com/features/agent/)** ![active](https://img.shields.io/badge/active-brightgreen) — Operator shut down Aug 31, 2025 → folded into ChatGPT 'agent mode'. CUA exposed via Agents SDK. Workspace Agents (Apr 2026) add Slack + scheduled/cloud persistence. · `Proprietary`
- **[Apple Siri AI](https://www.apple.com/newsroom/)** ![beta](https://img.shields.io/badge/beta-orange) — Deliberately NOT vision-based computer use — acts via structured App Intents, not pixel clicks. Always-on cross-device, privacy-first. WWDC26. · `Proprietary`
- **[Project Mariner](https://labs.google.com/mariner/landing)** ![dead](https://img.shields.io/badge/dead-red) — SHUT DOWN May 4, 2026. Browser automation proved too brittle (CAPTCHAs, anti-bot, layout drift). Tech folded into Gemini surfaces. · `Proprietary`

> Always-on consumer agents (Claude Cowork+Dispatch, Perplexity Computer, Gemini Spark, Manus) are listed under [Always-On Personal Assistants](#assistants).

### ⚠️ Benchmark reality check (OSWorld)

The headline numbers are moving fast and **almost entirely vendor-self-reported**, and the aggregators disagree with each other by ~10 points:

| Source | Top entry | Top score | Notes |
|---|---|---|---|
| **[AwesomeAgents](https://awesomeagents.ai/leaderboards/computer-use-leaderboard/)** | GPT-5.4 | **75.0%** | Fable/Mythos not listed |
| **[Steel.dev](https://leaderboard.steel.dev/leaderboards/osworld/)** | Claude Opus 4.8 | **83.4%** | No entry exceeds 85%; Opus 4.6 marked *self-reported* |
| **[BenchLM](https://benchlm.ai/benchmarks/osWorldVerified)** | Fable 5 / Mythos 5 | **~85%** | Fable/Mythos reportedly government-suspended mid-Jun 2026 |
| Human baseline ([OSWorld paper](https://os-world.github.io/)) | — | **72.36%** | The original benchmark |
| **[Simular Agent S3](https://www.simular.ai/articles/simulars-computer-use-agent-outperforms-humans)** (vendor) | Agent S3 | **72.60%** | Best-of-N; **single-pass 66%**; not on any independent leaderboard |

> **Bottom line:** computer-use has reached human-baseline *territory*, but no single clean, independently-verified, currently-accessible number establishes that it has *surpassed* humans. Read all OSWorld-Verified figures as vendor self-reports that vary by ~10 points across aggregators.

---

<a name="frameworks"></a>
## 🧩 Agent Frameworks & SDKs

### The three-vendor SDK race

- **[OpenAI Agents SDK](https://github.com/openai/openai-agents-python)** ![active](https://img.shields.io/badge/active-brightgreen) — Productionized successor to Swarm. Agents, Sandbox Agents, Handoffs, Tools (fn/MCP/hosted), Guardrails, HITL, Sessions, Tracing, Realtime voice agents. · `MIT` · Python, JS/TS · ≈27.3k★ *GitHub API, 2026-06-19*
- **[Claude Agent SDK](https://github.com/anthropics/claude-agent-sdk-python)** ![active](https://img.shields.io/badge/active-brightgreen) — Renamed Claude Code SDK — programmatic access to the same agent loop/tools/context as Claude Code. · `MIT` · Python, TypeScript · ≈7.3k★ *approx/unverified (py)*
- **[Anthropic Agent Skills](https://github.com/anthropics/skills)** ![active](https://img.shields.io/badge/active-brightgreen) — Reference impl of the Agent Skills standard (SKILL.md capability packs). Widely cited as having 'surged past MCP' as the de-facto capabilities layer. · `Apache-2.0 (skills)` · Markdown (SKILL.md) · ≈152.6k★ *GitHub API, 2026-06-19*
- **[Google ADK 2.0](https://github.com/google/adk-python)** ![active](https://img.shields.io/badge/active-brightgreen) — Code-first build/eval/deploy. ADK 2.0 added graph-based Workflow Runtime (routing, fan-out/fan-in, loops, HITL) + Task API for agent-to-agent delegation. · `Apache-2.0` · Python, Go, Java, TS · ≈20.2k★ *GitHub API, 2026-06-19*
- **[Microsoft AutoGen](https://github.com/microsoft/autogen)** ![maintenance](https://img.shields.io/badge/maintenance-yellow) — MAINTENANCE MODE. Event-driven multi-agent. Users directed to Microsoft Agent Framework. · `CC-BY-4.0` · Python, .NET · ≈59.1k★ *GitHub API, 2026-06-19*
- **[Microsoft Agent Framework](https://github.com/microsoft/agent-framework)** ![GA](https://img.shields.io/badge/GA-brightgreen) — 1.0 GA. Official successor merging AutoGen + Semantic Kernel. Graph workflows, durable/restartable, A2A + MCP interop. · `MIT` · Python, .NET · ≈11.5k★ *GitHub API, 2026-06-19*
- **[Amazon Bedrock AgentCore](https://aws.amazon.com/bedrock/agentcore/)** ![GA](https://img.shields.io/badge/GA-brightgreen) — GA managed agent platform. Two API calls (CreateHarness + InvokeHarness) to run production agents. Runtime (isolated FS+shell), Memory, Gateway, Browser, Identity, Observability. CloudWatch-traced. MCP support. · `Proprietary` · Python

### Orchestration layer

- **[LangGraph](https://github.com/langchain-ai/langgraph)** ![GA](https://img.shields.io/badge/GA-brightgreen) — 1.0 GA Oct 2025. Low-level stateful/durable graph orchestration with first-class HITL interrupts + memory. Deep Agents harness on top. · `MIT` · Python, JS/TS · ≈35.2k★ *GitHub API, 2026-06-19*
- **[CrewAI](https://github.com/CrewAIInc/CrewAI)** ![active](https://img.shields.io/badge/active-brightgreen) — Role-based Crews (autonomous agent teams) + deterministic Flows. Standalone since v1.14 (no LangChain dep). Fortune-500 traction claimed. · `MIT` · Python · ≈53.9k★ *GitHub API, 2026-06-19*
- **[PocketFlow](https://github.com/The-Pocket/PocketFlow)** ![active](https://img.shields.io/badge/active-brightgreen) — Deliberately 100-line minimalist graph framework, zero dependencies. Positioned for 'let Cursor/Claude build agents on top.' · `MIT` · Python, TS, Java, C++, Go · ≈10.8k★ *GitHub API, 2026-06-19*
- **[PydanticAI](https://github.com/pydantic/pydantic-ai)** ![beta](https://img.shields.io/badge/beta-orange) — 'FastAPI-feeling,' fully type-safe, model-agnostic. Tight OTel/Logfire observability. v2.0 beta. · `MIT` · Python · ≈17.9k★ *GitHub API, 2026-06-19*
- **[smolagents](https://github.com/huggingface/smolagents)** ![active](https://img.shields.io/badge/active-brightgreen) — Agents that 'think in code' — CodeAgent writes Python (sandboxed via E2B/Modal/Docker) vs JSON ToolCallingAgent. ~1k-line core. · `Apache-2.0` · Python · ≈27.9k★ *GitHub API, 2026-06-19*
- **[LlamaIndex](https://github.com/run-llama/llama_index)** ![active](https://img.shields.io/badge/active-brightgreen) — RAG-native 'document agent' platform. Multi-agent via AgentWorkflow + custom planners. · `MIT` · Python, TS · ≈50.2k★ *GitHub API, 2026-06-19*

### Editor-agent runtimes & managed platforms

- **[Cline](https://github.com/cline/cline)** ![active](https://img.shields.io/badge/active-brightgreen) — Pioneer agentic VS Code extension, repositioned as ONE runtime across IDE + terminal + SDK (CLI 3.0 May 2026). 8M+ installs. · `Apache-2.0` · TypeScript · ≈63.5k★ *GitHub API, 2026-06-19*
- **[Roo Code](https://github.com/RooCodeInc/Roo-Code)** ![archived](https://img.shields.io/badge/archived-lightgrey) — ARCHIVED May 15, 2026 (final v3.54.0). Cline fork w/ custom modes. Team pivoted to 'Roomote' (Slack-first cloud). Successors: Zoo Code, Kilo Code. · `Apache-2.0` · TypeScript · ≈24.2k★ *GitHub API, 2026-06-19*
- **[Devin / Cognition](https://cognition.ai)** ![active](https://img.shields.io/badge/active-brightgreen) — Managed 'autonomous software engineer.' Devin Desktop (Jun 2026) on Rust 'Devin Local' engine (ACP + third-party agents). 'Managed Devins' = coordinator spawning parallel child agents. · `Proprietary`

---

<a name="desktop"></a>
## 🖥️ Desktop Apps & IDEs

The GUI counterparts to the CLI coding agents. Some are standalone IDEs (Cursor, Windsurf, Zed); others are native desktop wrappers around vendor agent stacks (Claude Desktop, Codex Desktop, GitHub Copilot App). The pattern in 2026: **every major coding agent now ships a desktop app** — the terminal is no longer the only surface.

- **[Claude Desktop](https://claude.ai/download)** ![active](https://img.shields.io/badge/active-brightgreen) — Native macOS + Windows app (no Linux). Three tabs: Chat, Cowork (autonomous agent for local files/tasks), Code (Claude Code GUI). MCP server connections, Desktop Extensions (.mcpb one-click bundles), Computer Use mode. Windows reached full parity Feb 2026. · `Proprietary`
- **[Codex Desktop](https://openai.com/codex)** ![active](https://img.shields.io/badge/active-brightgreen) — Mac + Windows desktop agent. 5M+ weekly active users (up 6× since Feb 2026 desktop launch). Computer Use (screen reading, mouse/keyboard control), scheduled Skills (natural-language cron), 90+ plugins, Chrome extension, Chronicle (ambient memory). 20% of users are non-developer knowledge workers. · `Proprietary`
- **[GitHub Copilot App](https://github.com/features/copilot)** ![GA](https://img.shields.io/badge/GA-brightgreen) — GA June 17, 2026 (macOS / Windows / Linux). Agent-native desktop — My Work view across repos, git worktrees for parallel agent sessions, Canvases (bidirectional human-agent surfaces), Cloud Automations (scheduled agent tasks), Agent Merge (CI-to-green). MCP support. · `Proprietary`
- **[Cursor](https://cursor.com)** ![active](https://img.shields.io/badge/active-brightgreen) — Leading AI-native IDE ($100M+ ARR). VS Code fork with Composer (multi-file agent edits), Background Agents (parallel cloud sessions), BugBot (PR review). Best @codebase indexing on large repos. Free / $20 Pro / $40 Team. · `Proprietary` · TypeScript
- **[Windsurf](https://codeium.com/windsurf)** ![active](https://img.shields.io/badge/active-brightgreen) — AI IDE acquired by Cognition (absorbing Devin cloud platform). Cascade agent = strongest autonomous multi-file loop in its class. Readable plan view for long sessions. ~$15/mo Pro. VS Code fork. · `Proprietary` · TypeScript
- **[Zed](https://github.com/zed-industries/zed)** ![active](https://img.shields.io/badge/active-brightgreen) — Fastest AI IDE — sub-second cold start, 2ms input latency. Rust-native (not a VS Code fork). v1.0 with open agent protocol. Native real-time multiplayer collaboration. Best-in-class Vim mode. Zero vendor lock-in (BYO key). · `GPL-3.0 / Apache-2.0` · Rust · ≈85.6k★ *GitHub API, 2026-06-19*
- **[Qt Creator 20](https://github.com/qt-creator/qt-creator)** ![active](https://img.shields.io/badge/active-brightgreen) — Qt Creator 20 (Jun 2026) added ACP Client extension — chat panel for AI coding agents (Claude Code, Codex, Gemini, Copilot). MCP Server extension for tool access. Zen Mode for focus. Major C++/Qt IDE entering the agent era. · `GPL-3.0 / commercial` · C++ · ≈3.0k★ *GitHub mirror; primary hosting at code.qt.io*
- **[GitKraken Kepler](https://www.gitkraken.com/kepler)** ![active](https://img.shields.io/badge/active-brightgreen) — Agentic Development Environment (ADE) — delivery engine for managing parallel AI coding agents. Directs multiple agents, drives output through to merged. Win/Mac/Linux + browser. SSH/WSL support. · `Proprietary`

---

<a name="agent-managers"></a>
## 🐄 Agent Managers & Multiplexers

These tools don't run agents themselves — they manage parallel AI coding agent sessions the way tmux manages terminals. The problem they solve: when you're running 3–10 agents across separate terminals, you lose track of what's blocked, what's done, and what needs input. The category emerged in early 2026 and is moving fast.

- **[cmux](https://github.com/manaflow-ai/cmux)** ![active](https://img.shields.io/badge/active-brightgreen) — The dominant agent multiplexer by traction (22.7k★). Native macOS terminal built on libghostty with agent-state awareness, subagent-to-pane promotion, built-in browser automation pane, iOS app (beta), Unix socket + CLI API, skills system, SSH remote attach. Survives full reboots with session restore. · `MIT` · Swift (AppKit + libghostty) · ≈22.7k★ *GitHub API, 2026-06-19*
- **[Agent of Empires (AoE)](https://github.com/agent-of-empires/agent-of-empires)** ![active](https://img.shields.io/badge/active-brightgreen) — TUI + web dashboard (PWA) session manager for AI coding agents. Each agent in its own tmux session + git worktree. Docker sandboxing option. Mobile phone access via built-in HTTP server. 104 releases — one of the most actively developed in the category. · `MIT` · Rust · ≈2.6k★ *GitHub API, 2026-06-19*
- **[dmux](https://github.com/standardagents/dmux)** ![active](https://img.shields.io/badge/active-brightgreen) — Dev agent multiplexer for git worktrees. Each pane gets its own worktree + branch for full isolation. Multi-select agent launches (run different agents per pane). AI-named branches/commits, smart one-step merge, built-in file browser, lifecycle hooks. · `MIT` · TypeScript, Shell · ≈1.7k★ *GitHub API, 2026-06-19*
- **[Parallel Code](https://github.com/johannesjo/parallel-code)** ![active](https://img.shields.io/badge/active-brightgreen) — GUI desktop app for parallel multi-agent coding. Auto-creates git worktree per task (zero conflict between agents). QR-code phone monitoring over Wi-Fi/Tailscale. Keyboard-first navigation. Merge back to main from sidebar. · `MIT` · TypeScript · ≈744★ *GitHub API, 2026-06-19*
- **[Agent Deck](https://github.com/asheshgoplani/agent-deck)** ![active](https://img.shields.io/badge/active-brightgreen) — Go-based TUI 'command center' for AI coding agents. 343 releases — most iterated tool in category. Groups, search, session forking, git worktrees, per-agent cost tracking, and a phone-controlled 'Conductor' mode for fleet management. · `MIT` · Go · ≈352★ *GitHub API, 2026-06-19*
- **[Herdr](https://github.com/mxhm/herdr)** ![active](https://img.shields.io/badge/active-brightgreen) — The reference agent multiplexer — tmux for AI coding agents. Workspaces, tabs, panes with agent-state awareness (blocked/working/done/idle). Detach/reattach over SSH, sessions persist. Unix socket API lets agents orchestrate each other. No GUI, no Electron, runs anywhere you can ssh. · `MIT` · Rust
- **[Quil](https://quil.cc)** ![active](https://img.shields.io/badge/active-brightgreen) — Reboot-proof terminal multiplexer for AI dev. Snapshots workspace to disk continuously — close laptop, reboot, type 'quil' and everything restores in <30s incl. auto-resuming Claude Code sessions. Built-in MCP server (18 tools) makes your terminal addressable by agents. Typed panes (not generic shells). · `Proprietary` · Rust (single binary)
- **[TUICommander](https://github.com/sstraus/tuicommander)** ![active](https://img.shields.io/badge/active-brightgreen) — AI-native desktop IDE for multi-agent dev. Up to 50 parallel sessions, each in its own git worktree. Rate-limit detection with countdown timers, question/prompt detection, usage tracking with 7-day charts + 52-week heatmaps. Tauri + SolidJS + Rust. · `Apache-2.0` · Rust, SolidJS, Tauri · ≈87★ *GitHub API, 2026-06-19*
- **[RelayDeck](https://github.com/relaydeck/relaydeck)** ![beta](https://img.shields.io/badge/beta-orange) — Local-first fleet OS for CLI coding agents. Runs vendor CLIs unattended in PTYs. Agents discover peers by purpose/tags with durable peer-to-peer messaging. Plugin-extensible (harnesses, providers, skills, automations). State in local SQLite, secrets in on-host vault. No cloud account, no telemetry. · `MIT` · Go · ≈60★ *GitHub API, 2026-06-19*
- **[Fleet](https://github.com/nicknisi/fleet)** ![active](https://img.shields.io/badge/active-brightgreen) — Terminal dashboard for managing multiple Claude Code sessions in tmux. Hooks into Claude Code's event system for real-time agent state tracking. 7 agent states sorted by urgency. Send prompts, approve permissions, filter sessions — all from one pane. Compiled Bun binary. · `MIT` · TypeScript (Bun) · ≈10★ *GitHub API, 2026-06-19*

---

<a name="shutdowns"></a>
## 🪦 Shutdowns & Archived (avoid)

These tools were once relevant but are now deprecated, archived, or dead. Listed for reference — avoid recommending them.

| Tool | Status | What happened |
|---|---|---|
| **[Gemini CLI](https://github.com/google-gemini/gemini-cli)** | ![dead](https://img.shields.io/badge/dead-red) | DEAD. Shut down June 18, 2026. All consumer accounts (free/Pro/Ultra) received HTTP 410 Gone. Replaced by closed-source Antigravity CLI (ag… |
| **[Continue](https://github.com/continuedev/continue)** | ![archived](https://img.shields.io/badge/archived-lightgrey) | ARCHIVED after final 2.0.0 release (VS Code ext, cn CLI, JetBrains plugin). Historical: PR-checks agents. |
| **[Project Mariner](https://labs.google.com/mariner/landing)** | ![dead](https://img.shields.io/badge/dead-red) | SHUT DOWN May 4, 2026. Browser automation proved too brittle (CAPTCHAs, anti-bot, layout drift). Tech folded into Gemini surfaces. |
| **Manus (Meta)** | ![uncertain](https://img.shields.io/badge/uncertain-yellow) | Cross-platform chat-reachable autonomous agent; 'My Computer' desktop mode (Mar 2026). Meta moving to UNWIND the deal (Beijing divestiture … |
| **[Microsoft AutoGen](https://github.com/microsoft/autogen)** | ![maintenance](https://img.shields.io/badge/maintenance-yellow) | MAINTENANCE MODE. Event-driven multi-agent. Users directed to Microsoft Agent Framework. |
| **[Roo Code](https://github.com/RooCodeInc/Roo-Code)** | ![archived](https://img.shields.io/badge/archived-lightgrey) | ARCHIVED May 15, 2026 (final v3.54.0). Cline fork w/ custom modes. Team pivoted to 'Roomote' (Slack-first cloud). Successors: Zoo Code, Kil… |
| [Operator](https://openai.com/index/introducing-operator/) (OpenAI) | ![dead](https://img.shields.io/badge/dead-red) | Folded into ChatGPT as "agent mode" (Aug 31, 2025) |
| [Amazon Q Developer CLI](https://github.com/aws/amazon-q-developer-cli) (AWS) | ![archived](https://img.shields.io/badge/archived-lightgrey) | Deprecated (security fixes only); replaced by closed-source Kiro (OSS → closed) |
| Sourcegraph Cody CLI | ![maintenance](https://img.shields.io/badge/maintenance-yellow) | Effectively legacy; successor is **Amp** (`@ampcode/cli`) |

---

<a name="trending"></a>
## 📈 Trending Repos Snapshot (2026-06-19)

User-facing focus; star counts point-in-time and *unverified*. Sorted by stars.

| Repo | Stars (≈) | Category | Why notable |
|---|---|---|---|
| [`openclaw/openclaw`](https://github.com/openclaw/openclaw) | ~379.4k | Always-on assistant | The reference open-source always-on personal assistant: self-hosted Gateway daemon, 20+ c… |
| [`NousResearch/hermes-agent`](https://github.com/NousResearch/hermes-agent) | ~197.5k | Always-on assistant | Self-improving always-on agent (launched Feb 2026). After each task, evaluates outcome an… |
| [`anomalyco/opencode`](https://github.com/anomalyco/opencode) | ~176.2k | CLI coding agent | Highest-traction OSS terminal coding agent. Multi-session parallel agents, desktop beta. … |
| [`anthropics/skills`](https://github.com/anthropics/skills) | ~152.6k | Agent framework / SDK | Reference impl of the Agent Skills standard (SKILL.md capability packs). Widely cited as … |
| [`anthropics/claude-code`](https://github.com/anthropics/claude-code) | ~133.3k | CLI coding agent | Reasoning-quality leader (v2.1.183). Fully agentic: multi-file edits, sandboxed bash, sub… |
| [`google-gemini/gemini-cli`](https://github.com/google-gemini/gemini-cli) | ~105.4k | CLI coding agent | DEAD. Shut down June 18, 2026. All consumer accounts (free/Pro/Ultra) received HTTP 410 G… |
| [`browser-use/browser-use`](https://github.com/browser-use/browser-use) | ~99.5k | Computer-use / browser | Widely-used OSS browser-agent library (Playwright). Rust-backed beta (0.13.0). Commercial… |
| [`openai/codex`](https://github.com/openai/codex) | ~92.1k | CLI coding agent | Sandboxed agentic execution; Rust rewrite. Bundled with ChatGPT plans or API-metered. Top… |
| [`zed-industries/zed`](https://github.com/zed-industries/zed) | ~85.6k | Desktop app / IDE | Fastest AI IDE — sub-second cold start, 2ms input latency. Rust-native (not a VS Code for… |
| [`OpenHands/OpenHands`](https://github.com/OpenHands/OpenHands) | ~77.7k | Computer-use / browser | Self-hosted 'developer control center'. Runs its own agent OR Claude Code/Codex/Gemini. S… |
| [`cline/cline`](https://github.com/cline/cline) | ~63.5k | Agent framework / SDK | Pioneer agentic VS Code extension, repositioned as ONE runtime across IDE + terminal + SD… |
| [`warpdotdev/warp`](https://github.com/warpdotdev/warp) | ~62.0k | CLI coding agent | AI-native terminal — replaces the shell itself (NL→bash, block-based dev env), not a codi… |

---

<a name="this-week"></a>
## 🗓️ This Week

Week of **2026-06-19**.

- 🔴 **Gemini CLI is DEAD — shut down June 18, replaced by closed-source Antigravity CLI** · `gemini-cli` — Google killed Gemini CLI for all consumer accounts (free/Pro/Ultra). The 105k-star OSS project's replacement, Antigravity CLI (agy), is a closed-source Go binary with async multi-agent orchestration. CI/CD pipelines calling `gemini` broke immediately. Enterprise users retain access. This is the biggest tool death in the CLI coding-agent category this year.
- 🔴 **Fable 5 / Mythos 5 suspended by US government directive** — Anthropic confirmed via primary source that the US government issued an export control directive suspending all access to Fable 5 and Mythos 5 (citing a jailbreak/national security concern). All customers affected. This means the OSWorld-Verified >85% scores citing these models are now non-reproducible.
- 🔴 **Three notable new entrants: Antigravity CLI, Junie GA, Mistral Vibe** · `antigravity-cli` — Google's Antigravity CLI replaces Gemini CLI. JetBrains' Junie coding agent left beta (GA) with advanced Plan mode + PR review. Mistral rebranded Le Chat → Vibe with Work Mode + Code Mode + VS Code extension + CLI with skills/subagents/teleport.
- 🟡 **OpenClaw star count confirmed at 379,442 from GitHub API** · `openclaw` — The self-reported ~370k+ figure was accurate — now confirmed via API. OpenClaw also shipped v2026.6.8 stable with release-evidence verification.

**What to watch:**
- **Antigravity CLI adoption vs migration away from Google** (next 2-4 weeks) — Google forced the entire Gemini CLI community to either adopt a closed-source replacement or switch to a provider-independent tool (Codex CLI, Aider, Claude Code). TheRouter frames this as a 'forcing function' toward multi-model routing. Watch whether OpenCode/Codex CLI see a star surge from Gemini CLI refugees.
- **OpenAI platform consolidation (Agent Builder + Evals + Pulse sunsetting)** (Q3-Q4 2026) — OpenAI is retiring Agent Builder, Evals, and Pulse — pushing users to the Agents SDK and Workspace Agents. This consolidates the OpenAI agent stack around fewer surfaces. Teams using these have deadlines (Nov 30 for Agent Builder/Evals).
- **Agent Skills standard adoption accelerating** (ongoing) — 32+ tools now read the same SKILL.md format (incl. Antigravity CLI). Published Dec 2025; adopted by Microsoft+OpenAI within 48h. This is becoming the de-facto interop layer for agent capabilities.

---

<a name="methodology"></a>
## 🔬 Methodology & Caveats

Read this before citing anything here. This is a **landscape map, not a benchmark study.**

- **Star counts are popularity, not quality** — point-in-time snapshots that drift within days. 37 of 40 tracked repos were verified directly from the GitHub API on 2026-06-19; the remainder are marked *unverified* (pulled from tracker/repo pages, not re-pulled).
- **The OSWorld "human parity" story is not clean.** Vendor self-reports vary by ~10 points across aggregators (75% / 83.4% / 85%); the only claimed crossing (Agent S3, 72.60%) is vendor-reported, best-of-N (single-pass 66%), and on no independent leaderboard.
- **The OpenClaw "self-hackable / AGI-like" rhetoric is ahead of the verified evidence.** The skill-creator + hot-reload machinery is real and code-confirmed; the reliable in-practice quality of agent-authored skills is **not independently benchmarked.**
- **Vendor causation is not confirmed** — proprietary launches framed as "responses to OpenClaw" are press inference, not vendor statements.
- **Two "OpenCode" lineages need disambiguation:** the major `sst/opencode` → `anomalyco/opencode` (~176k★) vs the project Charm's Crush was claimed to be "rebranded from" (unverified).

---

<a name="license"></a>
## 📄 License

The research and curation in this repository are provided as-is for the community. Individual tools retain their own licenses (noted per entry). Where this README's prose is original to this repo, it is licensed MIT.

<p align="center"><sub>⚠️ <strong>NOTICE.</strong> This README is produced by an automated weekly research pipeline and may contain errors, outdated information, or omissions. Star counts are point-in-time snapshots. Always verify critical details (tool status, pricing, security claims, license terms) against primary sources before relying on them. Last pipeline run: 2026-06-19.</sub></p>
