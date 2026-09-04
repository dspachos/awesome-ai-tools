# Awesome AI Tools — 2026

> A curated, opinionated map of the **user-facing AI-tools landscape (as of 2026-08-16)** — CLI coding agents, OpenClaw-style "always-on" personal assistants, computer-use & browser agents, and agent frameworks / SDKs.
>
> Built from a four-track research survey with a source-verification pass, refreshed weekly. Every entry is sourced. Star counts are point-in-time; 53 of 54 repos verified directly from the GitHub API (the rest marked `≈` / `unverified`). See [Methodology & Caveats](#methodology).

<div align="center">

**79 tools** · **4 overlapping layers** · **Updated 2026-08-16**

</div>

> **Status badges:** ![active](https://img.shields.io/badge/active-brightgreen) · ![GA](https://img.shields.io/badge/GA-brightgreen) · ![beta](https://img.shields.io/badge/beta-orange) · ![announced](https://img.shields.io/badge/announced-blue) · ![maintenance](https://img.shields.io/badge/maintenance-yellow) · ![uncertain](https://img.shields.io/badge/uncertain-yellow) · ![archived](https://img.shields.io/badge/archived-lightgrey) · ![dead](https://img.shields.io/badge/dead-red)

---

## Table of Contents

- [What's New This Week](#this-week)
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
- [Methodology & Caveats](#methodology)
- [License](#license)

---

<a name="this-week"></a>
## 🗓️ What's New This Week

Week of **2026-08-16**.

### 🆕 New & Updated This Week

| Tool | Category | Change | Stars | Note |
|------|----------|--------|-------|------|
| **[Muse Code](https://research.meta.ai/blog/introducing-muse-code-and-muse-spark-1-2)** | CLI coding agent | 🆕 added | — | Meta's terminal coding agent (beta, Aug 5): persistent background subagents, replay-exact event log, Muse Spark 1.2 |
| **[DeepSeek Harness (dsh)](https://github.com/deepseek-ai/deepseek-harness)** | CLI coding agent | 🆕 added | 119.8k★ | DeepSeek's open-source MIT harness: model adapter, tools, session log, agent loop — all swappable plugins. 119.8k★ in 3 days |
| **[Hermes Agent](https://github.com/NousResearch/hermes-agent)** | Always-on assistant | 🔄 updated | 231.2k★ | v0.20.0 'Herald' (Aug 3): streaming voice + barge-in + wake words, A2A v1.0 plugin, signed webhooks, tool ceiling 90→500 |
| **[OpenClaw](https://github.com/openclaw/openclaw)** | Always-on assistant | 🔄 updated | 386.4k★ | 2026.8.1-beta.1 npm train (stable = 2026.7.1-2); Gateway-owned active-session archive; Wear OS app |
| **[Warp](https://github.com/warpdotdev/warp)** | CLI coding agent | 🔄 updated | 64.2k★ | Warp Agent CLI: standalone agent for any terminal with built-in model routing, cloud agents, multi-agent orchestration |
| **[QwenPaw](https://github.com/agentscope-ai/QwenPaw)** | Always-on assistant | 🔄 updated | 33.8k★ | v2.1.0: OS Shell, unified Files workspace, Creator, browser/computer use — on top of the v2.0 AgentScope 2.0 rewrite |
| **[GitHub Copilot CLI](https://github.com/features/copilot/cli)** | CLI coding agent | 🔄 updated | — | VS Code 1.133: Agent Host decoupled, AHP spec open-sourced (MIT), Claude+Copilot models mixable; Sep 1 model deprecations |
| **[Browser Use](https://github.com/browser-use/browser-use)** | Computer-use / browser | 🔄 updated | 109.4k★ | Cloud v4: code-writing web agent, 76.5% internal eval (v3: 67.3%); 109k★ repo |
| **Lethe** | Always-on assistant | ⚠️ shutdown | 125★ | Main repo 404 (deleted/private); author's lethe-website/lethe-app repos remain — status now uncertain |
| **[ChatGPT Work / agent (ex-Operator/CUA)](https://chatgpt.com/features/agent/)** | Computer-use / browser | 🔄 updated | — | Atlas DEAD Aug 9 (bookmarks did not transfer); Codex Computer Use expands to Edge alongside Chrome |

- 🔴 **Meta enters the CLI coding-agent race with Muse Code** · `muse-code` — Meta shipped Muse Code (beta, Aug 5) — its first terminal coding agent, powered by the coding-focused Muse Spark 1.2. The differentiator is persistent multi-agent orchestration: background agents stay alive across a session and maintain a shared context file, while a local event log makes the runtime replay-exact and restart-safe. This moves Meta from model-API vendor into the application layer, directly targeting Claude Code and Codex — with larger models teased.
- 🔴 **DeepSeek Harness hits 119.8k stars in 3 days — the harness layer is commoditizing** · `deepseek-harness` — DeepSeek open-sourced its agent harness (MIT) on Aug 13 and it became the fastest-launching repo this project has ever tracked. 'Everything is a plugin': the model adapter, tool registry, session log, and agent loop are all swappable, and it is model-agnostic across all major providers. Launched alongside V4-Pro GA with Responses API and Codex integration. As models become interchangeable behind standardized interfaces, the harness — not the model — is where differentiation was supposed to live. DeepSeek just gave that layer away for free.
- 🔴 **VS Code open-sources the Agent Host Protocol — agent sessions become infrastructure** · `copilot-cli` — VS Code 1.133 (Aug 12) moved agent sessions into a standalone process and published the Agent Host Protocol spec under MIT, explicitly positioning it alongside LSP and DAP. Sessions now survive window closes, attach across windows, and are reachable over SSH or dev tunnels; Claude sessions can mix Anthropic and Copilot models per turn. Meanwhile JetBrains is rolling out ACP ('the LSP moment for AI agents') across WebStorm, IntelliJ, and PyCharm. There are now two competing open agent-session protocols — watch for fragmentation.
- 🔴 **The August shutdown wave: side-quest and low-code AI products are being culled** — ChatGPT Atlas died Aug 9 (bookmarks did not transfer). GitHub Models was fully retired Jul 30 — agentic workloads likely made free-tier economics untenable. GitHub Spark stops new users now and retires Aug 31, directing builders to Copilot. Flowise public-archived its repo Aug 10, explicitly citing coding agents (Claude Code/OpenClaw) making rigid low-code workflows obsolete. Microsoft killed consumer Copilot features (Group Chats, AI podcasts, Labs, Deep Research) by Aug 18 while merging its two Copilot apps. Consolidation into agent-native surfaces is accelerating.

**What to watch:**
- **OpenAI Assistants API final shutdown Aug 26** (immediate (~10 days)) — /v1/assistants and /v1/threads stop accepting requests permanently after the one-year deprecation window closes. Any production code still on Assistants/Threads/Runs/Messages breaks. Migration target is the Responses API; stored assistants, thread histories, and run logs become inaccessible.
- **GitHub Copilot model deprecations Sep 1 — first big Claude-5 test** (next 2-3 weeks) — Gemini 3.1 Pro, Claude Opus 4.5/4.6, Claude Sonnet 4.5/4.6, and Raptor Mini all deprecate Sep 1. Suggested replacements surface the new generation: Claude Opus 5 / Sonnet 5, Gemini 3.6 Flash, and Microsoft's own MAI-Code-1-Flash. Watch whether Claude 5 changes agent-harness leaderboards and whether Microsoft's first-party model gains Copilot share.
- **AHP vs ACP: two competing agent-protocol standards** (next 1-3 months) — Microsoft's Agent Host Protocol (MIT, from VS Code) and the JetBrains-led ACP are both racing to become 'the LSP for agents.' Grok Build, OpenClaw, and DeepSeek Harness already ship ACP support; VS Code's host uses AHP. If harnesses end up supporting both, integration cost stays low; if vendors pick sides, we get a browser-war-style split. Watch adoption announcements from Cursor, Zed, and the JetBrains registry.

---

<a name="landscape"></a>
## 🧭 The Landscape in One Screen

The clearest mental model: **the CLI coding agents are the substrate; the OpenClaw-style always-on personal assistants are the new application layer that orchestrates them.** As of 2026-08-16, the landscape has consolidated around four overlapping layers, with the headline story being a genuinely new product category — self-hosted, chat-reachable, persistent, proactive, computer-controlling assistants.

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
| Type-safe Python agent framework | **[PydanticAI](https://github.com/pydantic/pydantic-ai)** ![active](https://img.shields.io/badge/active-brightgreen) | FastAPI-feeling, fully typed, model-agnostic with strong OTel/Logfire observability. |
| Multi-agent orchestration (durable graphs) | **[LangGraph](https://github.com/langchain-ai/langgraph)** ![GA](https://img.shields.io/badge/GA-brightgreen) | 1.0 GA durable graph orchestration with first-class human-in-the-loop interrupts + memory. |
| Production agent SDK (OpenAI stack) | **[OpenAI Agents SDK](https://github.com/openai/openai-agents-python)** ![active](https://img.shields.io/badge/active-brightgreen) | Handoffs, sandbox agents, guardrails, tracing, realtime voice — productionized Swarm successor. |
| Best AI-native IDE | **[Cursor](https://cursor.com)** ![active](https://img.shields.io/badge/active-brightgreen) | $100M+ ARR, best @codebase indexing, Composer multi-file edits, Background Agents, BugBot PR review. |
| Fastest editor + zero lock-in | **[Zed](https://github.com/zed-industries/zed)** ![active](https://img.shields.io/badge/active-brightgreen) | Rust-native sub-second cold start, open agent protocol, BYO-key, native multiplayer. 85k+ stars. |

---

<a name="cli"></a>
## ⌨️ CLI Coding Tools

The most mature and crowded segment. Splits into **vendor CLIs** (closed, subscription-tied), **open-source multi-provider agents**, and **AI-native terminals**. **Pricing has converged on subscription-plus-credits**. ⚠️ Gemini CLI was **shut down June 18** — replaced by closed-source Antigravity CLI.

### Vendor CLIs (proprietary)

- **[Claude Code](https://github.com/anthropics/claude-code)** ![active](https://img.shields.io/badge/active-brightgreen) — Reasoning-quality leader. Fully agentic: multi-file edits, sandboxed bash, subagents, MCP, hooks, headless + background agents. Auto-mode safety (blocks destructive git/terraform commands). /rewind recovers conversations after /clear. Aug 2026: `claude agents` Agent view (research preview) groups sessions by state with peek-without-opening and automatic worktree edits — a local-only viewer for now (no remote attach, no socket API). Split-credit pricing (Jun 15, 2026). · `Proprietary` · 141.6k★ *GitHub API, 2026-08-16*
- **[Codex CLI](https://github.com/openai/codex)** ![active](https://img.shields.io/badge/active-brightgreen) — Sandboxed agentic execution; Rust rewrite. Bundled with ChatGPT plans or API-metered. Top vendor CLI on Terminal-Bench. · `Apache-2.0` · Rust · 106.2k★ *GitHub API, 2026-08-16*
- **[Gemini CLI](https://github.com/google-gemini/gemini-cli)** ![dead](https://img.shields.io/badge/dead-red) — DEAD. Shut down June 18, 2026. All consumer accounts (free/Pro/Ultra) received HTTP 410 Gone. Replaced by closed-source Antigravity CLI (agy). 105k-star OSS project orphaned. Enterprise customers retain access via paid Gemini Enterprise Agent Platform API keys. · `Apache-2.0` · TypeScript · 106.5k★ *GitHub API, 2026-08-16*
- **[Antigravity CLI](https://antigravity.google)** ![active](https://img.shields.io/badge/active-brightgreen) — Replaces the dead Gemini CLI. Closed-source Go binary (agy) with async multi-agent orchestration. Shares architecture with Antigravity 2.0 desktop app. Supports Agent Skills, Hooks, Subagents, Extensions. No source code, tighter quotas, no multi-model routing. · `Proprietary (closed source)` · Go
- **[Junie](https://blog.jetbrains.com/junie/2026/06/junie-coding-agent-out-of-beta/)** ![GA](https://img.shields.io/badge/GA-brightgreen) — JetBrains AI coding agent — GA June 2026. Advanced Plan mode (structured doc with PRD/tech design/delivery/testing tabs), PR review with project context, long-running tasks. Uses real JetBrains debugger and project tools. Works in IDE + terminal. · `Proprietary`
- **[Cursor CLI](https://cursor.com/docs/cli/overview)** ![active](https://img.shields.io/badge/active-brightgreen) — Agent / Plan / Ask modes + Cloud Agent handoff. Tightest parity with Cursor editor. Teams pricing refreshed Jun 2026. · `Proprietary`
- **[GitHub Copilot CLI](https://github.com/features/copilot/cli)** ![active](https://img.shields.io/badge/active-brightgreen) — Deepest GitHub-native integration. /fleet parallel subagents, autopilot, AGENTS.md skills, native MCP. Usage-metered AI Credits (Jun 1, 2026). Aug 2026: VS Code 1.133 decouples the Agent Host into a standalone process and open-sources the Agent Host Protocol (AHP, MIT) — sessions survive window closes, attach over SSH/dev tunnels, and Claude sessions can mix Anthropic + Copilot models per turn; 1.132 added /btw side chats and element-level browser comments. Copilot Agent is now stable inside Microsoft Agent Framework (.NET + Python). Sep 1: Gemini 3.1 Pro, Claude Opus 4.5/4.6, Sonnet 4.5/4.6, Raptor Mini deprecate. · `Proprietary`
- **[Kiro CLI](https://kiro.dev/docs/cli/migrating-from-q/)** ![active](https://img.shields.io/badge/active-brightgreen) — Replaces the deprecated OSS Amazon Q Developer CLI (OSS→closed). NL→bash, >500-tool autocomplete, custom agents. First-party AWS/Bedrock/IAM integration. · `Proprietary`
- **[Muse Code](https://research.meta.ai/blog/introducing-muse-code-and-muse-spark-1-2)** ![beta](https://img.shields.io/badge/beta-orange) — Meta's terminal coding agent (beta, Aug 5, 2026). Persistent multi-agent orchestration: specialized background agents stay alive across a session, maintain a shared context file, and decide when to report back — parallel agents work in isolated worktrees. Local event log records every model call, tool run, approval, and edit, making the runtime replay-exact and restart-safe. Powered by Muse Spark 1.2 (coding-focused; third Muse release in four months). macOS/Linux. Meta's move from model-API vendor into the application layer, directly targeting Claude Code and Codex. · `Proprietary`

### Open-source multi-provider agents

- **[Aider](https://github.com/Aider-AI/aider)** ![active](https://img.shields.io/badge/active-brightgreen) — Maturest community OSS tool. Git-integrated pair-programming loop, repo map, auto-commits. Host of the widely-cited LLM coding leaderboard. · `Apache-2.0` · Python · 48.3k★ *GitHub API, 2026-08-16*
- **[Crush](https://github.com/charmbracelet/crush)** ![active](https://img.shields.io/badge/active-brightgreen) — Best-in-class TUI/UX, broadest provider matrix out of the box. · `OSS (verify exact)` · Go · 27.4k★ *GitHub API, 2026-08-16*
- **[Qwen Code](https://github.com/QwenLM/qwen-code)** ![active](https://img.shields.io/badge/active-brightgreen) — Self-described Claude-Code feature-parity: subagents, agent teams, skills/hooks, MCP, plan mode, computer use. Pairs open model + open framework. · `Apache-2.0` · Node.js · 27.1k★ *GitHub API, 2026-08-16*
- **[OpenCode](https://github.com/anomalyco/opencode)** ![active](https://img.shields.io/badge/active-brightgreen) — Highest-traction OSS terminal coding agent. Multi-session parallel agents, desktop beta. Copilot/OpenAI login. · `OSS` · TypeScript · 197.9k★ *GitHub API, 2026-08-16*
- **[Omp (oh-my-pi)](https://github.com/can1357/oh-my-pi)** ![active](https://img.shields.io/badge/active-brightgreen) — Widest feature surface of any OSS terminal coding agent (25.1k★). Fork of the minimalist Pi harness but went the opposite direction: 32 built-in tools, 14 LSP operations, 28 DAP operations, hash-anchored edits, browser automation, subagents, MCP. Rust core (~55k lines) with TypeScript extension layer. Ships as complete-out-of-the-box IDE-in-terminal. · `MIT` · TypeScript, Rust · 25.1k★ *GitHub API, 2026-08-16*
- **[Grok Build](https://github.com/xai-org/grok-build)** ![active](https://img.shields.io/badge/active-brightgreen) — xAI's terminal coding agent and TUI (11k★). Open-sourced Jul 15: fullscreen agent harness, read/edit/search tools, shell execution, headless/CI mode, ACP support, local-first builds. `/goal` remains the autonomous execution loop with built-in verification. External PRs/issues are disabled — source transparency, not community governance. · `Apache-2.0` · Rust · 25.3k★ *GitHub API, 2026-08-16*
- **[DeepSeek Harness (dsh)](https://github.com/deepseek-ai/deepseek-harness)** ![beta](https://img.shields.io/badge/beta-orange) — Open-source agent harness where EVERYTHING is a plugin — the model adapter, tool registry, session log, and the agent loop itself are all swappable (built on the Cordis plugin framework). Four presets: Standard (full coding agent), Minimal (2 tools), Code (generates a TS SDK so the model writes programs — one call replaces five round trips), Creator (preset authoring). Append-only session log powers resume/fork/replay/transcripts. Optional subagent delegation to Claude Code and Codex, MCP client, ACP support, reads AGENTS.md/CLAUDE.md. 119.8k★ in 3 days — fastest launch ever tracked here. Developer preview; breaking changes expected. · `MIT` · TypeScript (Node.js) · 119.8k★ *GitHub API, 2026-08-16 (repo created 2026-08-13)*

### AI-native terminals & legacy

- **[Warp](https://github.com/warpdotdev/warp)** ![active](https://img.shields.io/badge/active-brightgreen) — AI-native terminal — replaces the shell itself (NL→bash, block-based dev env), not a coding agent running inside one. Aug 2026: Warp Agent CLI makes the agent standalone — it now runs in ANY terminal (Ghostty, iTerm2, VS Code, Windows/Mac terminals) with built-in model routing (frontier + US-hosted open-weight models, custom routers), cloud agents, and multi-agent orchestration. Free tier includes CLI access; Build $20/mo with $20 included usage. Also launched Oz (cloud agent platform), open-sourced the Warp client, and added BYO inference. · `Client AGPL-3.0 / server proprietary` · Rust · 64.2k★ *GitHub API, 2026-08-16*
- **[Continue](https://github.com/continuedev/continue)** ![acquired](https://img.shields.io/badge/acquired-blue) — ACQUIRED by Cursor (SpaceX acquired Cursor for $60B). Repo goes read-only July 15, 2026. Code stays public under Apache 2.0 but hosted service and roadmap are dead. Historical: open-source VS Code/JetBrains agent with BYOK completions and local model support. · `Apache-2.0` · TypeScript · 35.5k★ *GitHub API, 2026-08-16*
- **[MiMo Code](https://github.com/XiaomiMiMo/MiMo-Code)** ![active](https://img.shields.io/badge/active-brightgreen) — Xiaomi's open-source terminal coding agent, built on the OpenCode project. Adds long-term memory, specialized working modes, and state management for multi-hundred-step agentic tasks. MIT licensed. Bundled with free limited-time access to MiMo-V2.5 (1M token context). Claims to surpass Claude Code in complex programming benchmarks. · `MIT` · TypeScript · 12.8k★ *GitHub API, 2026-08-16*

> **CLI takeaways:** pricing is converging on subscription-plus-credits. The OSS field has standardized on multi-provider + BYO-key. Discontinuations matter (Q CLI → Kiro OSS→closed; Continue archived; Cody → Amp) — the deprecated tools are best avoided.

---

<a name="assistants"></a>
## 🤖 Always-On Personal AI Assistants — *the focal category*

> The defining new category of 2026: open-source, self-hosted, always-on personal AI assistants — chat-reachable, persistent, proactive, computer-controlling, self-extensible.

A tool qualifies for this category only if it satisfies all seven criteria: (a) self-hosted on user-owned hardware · (b) messaging-first reachability from existing chat apps · (c) persistent cross-session memory · (d) proactive heartbeat/cron behavior · (e) extensible skills with a registry · (f) broad multi-provider + local model routing · (g) computer/tool control.

### The OpenClaw wave (self-hosted OSS)

| Project | License · Lang | Stars | Focus |
|---|---|---|---|
| **[OpenClaw](https://github.com/openclaw/openclaw)** ![active](https://img.shields.io/badge/active-brightgreen) | `MIT` · TypeScript, Swift | 386.4k★ *GitHub API, 2026-08-16* | The reference open-source always-on personal assistant (386k★). Self-hosted Gateway daemon, 20+ chat surfaces, markdown memory, self-hackable SKILL.md skills. … |
| **[Memoh](https://github.com/memohai/Memoh)** ![active](https://img.shields.io/badge/active-brightgreen) | `AGPL-3.0` · Go, Vue, Rust | 2.1k★ *GitHub API, 2026-08-16* | Closest structural peer to OpenClaw. Each agent gets its own containerized 'cloud computer' (FS, desktop, browser, network, memory). Copyleft license. v0.13.1 … |
| **[OwnPilot](https://github.com/ownpilot/ownpilot)** ![active](https://img.shields.io/badge/active-brightgreen) | `MIT` · TypeScript | 423★ *GitHub API, 2026-08-16* | Explicitly OpenClaw-derived ('Claw' naming + SKILL.md). Strongest feature overlap incl. edge/IoT device control, soul agents, crews. |
| **Lethe** ![uncertain](https://img.shields.io/badge/uncertain-yellow) | `MIT` · Rust (~50 MB binary) | ≈125★ *last known 2026-07-16 — repo now 404* | UNCERTAIN — main repo (atemerev/lethe) returned 404 in Aug 2026 (deleted or made private); the author still pushes lethe-website (Jul 16) and lethe-app (Jul 13… |
| **[Hermes Agent](https://github.com/NousResearch/hermes-agent)** ![active](https://img.shields.io/badge/active-brightgreen) | `Apache-2.0` · Python | 231.2k★ *GitHub API, 2026-08-16* | Self-improving always-on agent (231k★). v0.20.0 'Herald' (Aug 3; ~1,400 PRs, 650+ contributors): streaming conversational voice with barge-in and on-device wak… |

### Proprietary equivalents

Recent tech press frames these as the industry's answer to OpenClaw. *(Note: "response" here is press inference — not a confirmed vendor statement that these were built because of OpenClaw.)*

- **[Claude Cowork + Dispatch](https://claude.com/docs/cowork/overview)** ![GA](https://img.shields.io/badge/GA-brightgreen) — GA Apr 9, 2026. Full desktop + browser. Dispatch = persistent session messageable from phone, runs while away. Anthropic's explicit always-on answer (press-framed vs OpenClaw). · `Proprietary`
- **[Perplexity Computer / Personal Computer](https://www.perplexity.ai/hub/blog/everything-is-computer)** ![active](https://img.shields.io/badge/active-brightgreen) — 24/7 digital proxy. Personal Computer GA Mac May 7, 2026 on dedicated Mac mini, mobile remote, kill switch, audit trail. Pitched as 'a more secure OpenClaw'. · `Proprietary`
- **[Gemini Spark / auto-browse](https://blog.google/innovation-and-ai/products/gemini-app/next-evolution-gemini-app/)** ![announced](https://img.shields.io/badge/announced-blue) — Successor to shut-down Project Mariner. auto-browse shipping in Chrome; Gemini Spark = 24/7 personal agent (I/O 2026). WebMCP origin trial in Chrome 149. · `Proprietary`
- **Manus (Meta)** ![uncertain](https://img.shields.io/badge/uncertain-yellow) — Cross-platform chat-reachable autonomous agent; 'My Computer' desktop mode (Mar 2026). Meta moving to UNWIND the deal (Beijing divestiture order, Jun 2026). Future in flux. · `Proprietary`
- **Mistral Vibe (ex-Le Chat)** ![active](https://img.shields.io/badge/active-brightgreen) — Rebranded from Le Chat. Work Mode (agentic enterprise workflows, knowledge search, document synthesis) + Code Mode (GitHub integration, sandboxed sessions, PR workflow) + VS Code extension + CLI with skills/custom modes/subagents/teleport session migration. $14.99/mo Pro, $24.99/user/mo Team. · `Proprietary`
- **[QwenPaw](https://github.com/agentscope-ai/QwenPaw)** ![active](https://img.shields.io/badge/active-brightgreen) — Self-hostable personal AI assistant (33.8k★) from Alibaba's AgentScope team. v2.1.0 (Aug 13): QwenPaw OS Shell, unified Files workspace, QwenPaw Creator, Codex/Qoder agent integration, Browser-use + Computer-use, workspace checkpoints, long-running conversation continuity. v2.0 (Jul 10) was a ground-up AgentScope 2.0 rewrite: Agent OS architecture (Resources/Governance/Sandbox per agent), Loop Engineering, Scroll Context, ReMe self-evolving memory, bundled TUI. Local QwenPaw-Flash models (2B/4B/9B) run with no API key; 14+ cloud providers supported. · `Apache-2.0` · Python, TypeScript · 33.8k★ *GitHub API, 2026-08-16*

### Adjacent (explicitly NOT the same category)

- **[Goose](https://github.com/aaif-goose/goose)** ![active](https://img.shields.io/badge/active-brightgreen) — General-purpose developer/desktop agent, 70+ MCP extensions. Donated by Block to Linux Foundation / AAIF (Jun 2026). v1.38.0 released. NOT messaging-first — adjacent category, not a true OpenClaw peer. · `Apache-2.0` · Rust · 52.8k★ *GitHub API, 2026-08-16*
- **[SuperAGI](https://github.com/TransformerOptimus/SuperAGI)** ![active](https://img.shields.io/badge/active-brightgreen) — 2023-era web-UI autonomous-agent framework. Concurrent agents + toolkits marketplace. Web-UI-centric, not chat-reachable — adjacent, not a peer. · `Apache-2.0` · Python, Next.js · 17.7k★ *GitHub API, 2026-08-16*

---

<a name="computer-use"></a>
## 🖱️ Computer-Use & Browser Agents

Computer-use has stratified into three layers: an **API/builder layer**, a **first-party consumer-agent layer**, and a fast-moving **benchmark story**.

### Builder / API layer

- **[Anthropic Computer Use](https://github.com/anthropics/anthropic-quickstarts/blob/main/computer-use-demo/README.md)** ![beta](https://img.shields.io/badge/beta-orange) — Canonical 'screenshot → coordinate → action' loop in a Docker Linux+X11+VNC container. The de-facto builder starting point. Eligible for Zero Data Retention. · `API proprietary / demo OSS`
- **[Microsoft OmniParser v2](https://github.com/microsoft/OmniParser)** ![active](https://img.shields.io/badge/active-brightgreen) — Not an agent — pure-vision GUI-grounding module that 'tokenizes' screenshots. Paired with OmniTool (dockerized Win11 VM). · `OSS` · Python · 25.3k★ *GitHub API, 2026-08-16*
- **[Simular Agent S3](https://github.com/simular-ai/Agent-S)** ![active](https://img.shields.io/badge/active-brightgreen) — First VENDOR-REPORTED OSWorld crossing: 72.60% (best-of-N; single-pass 66%). Not on independent leaderboards. Full desktop + Android. Raised $21.5M. · `Apache-2.0` · Python · 12.2k★ *GitHub API, 2026-08-16*
- **[Browser Use](https://github.com/browser-use/browser-use)** ![active](https://img.shields.io/badge/active-brightgreen) — Widely-used OSS browser-agent library (109k★, Playwright). Cloud v4 (Aug 7) is a code-writing agent — it writes and executes code across pages for bulk collection and long instructions; 76.5% on its internal 106-task eval (v3: 67.3%, v2: 54.3%). The launch's '$0.03/success' claim reflects a narrow bounded test; production docs show median ~$1.64/success on harder customer tasks. v4 trades speed (~10 min vs ~6 min) for accuracy. 'Box' = 24/7 Claude agent from Telegram/SSH (OpenClaw overlap). · `MIT` · Python · 109.4k★ *GitHub API, 2026-08-16*
- **[Skyvern](https://github.com/Skyvern-AI/skyvern)** ![active](https://img.shields.io/badge/active-brightgreen) — Enterprise browser-RPA replacement. Planner-Agent-Validator, native CAPTCHA + 2FA, SOC2/HIPAA. Workflow engine, not chat-reachable. · `AGPL-3.0` · Python · 22.8k★ *GitHub API, 2026-08-16*
- **[OpenHands](https://github.com/OpenHands/OpenHands)** ![active](https://img.shields.io/badge/active-brightgreen) — Self-hosted 'developer control center'. Runs its own agent OR Claude Code/Codex/Gemini. SDK + CLI + GUI + Agent Canvas (scheduled tasks, Slack/GitHub/Linear). · `MIT (core)` · Python · 84.2k★ *GitHub API, 2026-08-16*

### First-party consumer agents

- **[ChatGPT Work / agent (ex-Operator/CUA)](https://chatgpt.com/features/agent/)** ![active](https://img.shields.io/badge/active-brightgreen) — Operator shut down Aug 31, 2025 → folded into ChatGPT agent mode → ChatGPT Work (Jul 9, 2026). Atlas browser DEAD Aug 9, 2026 — bookmarks did not transfer; browser capabilities live in the unified desktop app + Chrome/Edge extensions. Codex Computer Use expanded to Edge (Aug 6) alongside Chrome. CUA remains exposed via Agents SDK. Work adds scheduled tasks, cloud browser, and long-running projects. · `Proprietary`
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

- **[OpenAI Agents SDK](https://github.com/openai/openai-agents-python)** ![active](https://img.shields.io/badge/active-brightgreen) — Productionized successor to Swarm. Agents, Sandbox Agents, Handoffs, Tools (fn/MCP/hosted), Guardrails, HITL, Sessions, Tracing, Realtime voice agents. · `MIT` · Python, JS/TS · 28.7k★ *GitHub API, 2026-08-16*
- **[Claude Agent SDK](https://github.com/anthropics/claude-agent-sdk-python)** ![active](https://img.shields.io/badge/active-brightgreen) — Renamed Claude Code SDK — programmatic access to the same agent loop/tools/context as Claude Code. · `MIT` · Python, TypeScript · 7.9k★ *GitHub API, 2026-08-16*
- **[Anthropic Agent Skills](https://github.com/anthropics/skills)** ![active](https://img.shields.io/badge/active-brightgreen) — Reference impl of the Agent Skills standard (SKILL.md capability packs). Widely cited as having 'surged past MCP' as the de-facto capabilities layer. · `Apache-2.0 (skills)` · Markdown (SKILL.md) · 169.6k★ *GitHub API, 2026-08-16*
- **[Google ADK 2.0](https://github.com/google/adk-python)** ![active](https://img.shields.io/badge/active-brightgreen) — Code-first build/eval/deploy. ADK 2.0 added graph-based Workflow Runtime (routing, fan-out/fan-in, loops, HITL) + Task API for agent-to-agent delegation. ADK Go 2.0 (Jun 30): graph-based workflow engine with built-in HITL and unified node runtime. Python SDK at v2.7.0 (Aug 13). · `Apache-2.0` · Python, Go, Java, TS · 21.1k★ *GitHub API, 2026-08-16*
- **[Microsoft AutoGen](https://github.com/microsoft/autogen)** ![maintenance](https://img.shields.io/badge/maintenance-yellow) — MAINTENANCE MODE. Event-driven multi-agent. Users directed to Microsoft Agent Framework. · `CC-BY-4.0` · Python, .NET · 60.4k★ *GitHub API, 2026-08-16*
- **[Microsoft Agent Framework](https://github.com/microsoft/agent-framework)** ![GA](https://img.shields.io/badge/GA-brightgreen) — 1.0 GA. Official successor merging AutoGen + Semantic Kernel. Graph workflows, durable/restartable, A2A + MCP interop. Aug: GitHub Copilot Agent integration now stable for .NET + Python — Copilot's harness (planning, shell, files, MCP) as the execution engine inside Agent Framework abstractions, with native tool approval. Go SDK in public preview. Orchestration patterns 1.0 across all languages; Agent Skills stable and released for Python + .NET. · `MIT` · Python, .NET, Go · 12.8k★ *GitHub API, 2026-08-16*
- **[Amazon Bedrock AgentCore](https://aws.amazon.com/bedrock/agentcore/)** ![GA](https://img.shields.io/badge/GA-brightgreen) — GA managed agent platform. Two API calls (CreateHarness + InvokeHarness) to run production agents. Runtime (isolated FS+shell), Memory, Gateway, Browser, Identity, Observability. CloudWatch-traced. MCP support. · `Proprietary` · Python
- **[AgentGateway](https://github.com/agentgateway/agentgateway)** ![active](https://img.shields.io/badge/active-brightgreen) — Open-source AI-native proxy/data plane (3.5k★). One high-performance Rust proxy governs all agent traffic: agent-to-LLM, agent-to-tool (via MCP), and agent-to-agent (via A2A), plus ordinary HTTP/gRPC. Donated to the Linux Foundation (Aug 2025). Contributors from AWS, Cisco, IBM, Microsoft, Red Hat. Handles auth, rate limiting, observability, and policy enforcement across all agent traffic. · `Apache-2.0` · Rust · 4.4k★ *GitHub API, 2026-08-16*

### Orchestration layer

- **[AIWG](https://github.com/jmagly/aiwg)** ![active](https://img.shields.io/badge/active-brightgreen) — Project-owned agents, skills, context, and governed workflows deployed into the native paths used by multiple coding platforms. · `MIT` · TypeScript · 209★ *GitHub API, 2026-09-03*
- **[LangGraph](https://github.com/langchain-ai/langgraph)** ![GA](https://img.shields.io/badge/GA-brightgreen) — 1.0 GA Oct 2025. Low-level stateful/durable graph orchestration with first-class HITL interrupts + memory. Deep Agents harness on top. · `MIT` · Python, JS/TS · 39.8k★ *GitHub API, 2026-08-16*
- **[CrewAI](https://github.com/CrewAIInc/CrewAI)** ![active](https://img.shields.io/badge/active-brightgreen) — Role-based Crews (autonomous agent teams) + deterministic Flows. Standalone since v1.14 (no LangChain dep). Fortune-500 traction claimed. · `MIT` · Python · 57.1k★ *GitHub API, 2026-08-16*
- **[PocketFlow](https://github.com/The-Pocket/PocketFlow)** ![active](https://img.shields.io/badge/active-brightgreen) — Deliberately 100-line minimalist graph framework, zero dependencies. Positioned for 'let Cursor/Claude build agents on top.' · `MIT` · Python, TS, Java, C++, Go · 11.1k★ *GitHub API, 2026-08-16*
- **[PydanticAI](https://github.com/pydantic/pydantic-ai)** ![active](https://img.shields.io/badge/active-brightgreen) — 'FastAPI-feeling,' fully type-safe, model-agnostic. v2.0.0 stable (Jun 23): harness-first design with capabilities as a core primitive — a composable unit bundling tools, hooks, instructions, and model settings. Built-in OpenTelemetry/Logfire observability, AG-UI protocol support. · `MIT` · Python · 19.3k★ *GitHub API, 2026-08-16*
- **[smolagents](https://github.com/huggingface/smolagents)** ![active](https://img.shields.io/badge/active-brightgreen) — Agents that 'think in code' — CodeAgent writes Python (sandboxed via E2B/Modal/Docker) vs JSON ToolCallingAgent. ~1k-line core. · `Apache-2.0` · Python · 28.8k★ *GitHub API, 2026-08-16*
- **[LlamaIndex](https://github.com/run-llama/llama_index)** ![active](https://img.shields.io/badge/active-brightgreen) — RAG-native 'document agent' platform. Multi-agent via AgentWorkflow + custom planners. · `MIT` · Python, TS · 51.7k★ *GitHub API, 2026-08-16*

### Editor-agent runtimes & managed platforms

- **[Cline](https://github.com/cline/cline)** ![active](https://img.shields.io/badge/active-brightgreen) — Pioneer agentic VS Code extension, repositioned as ONE runtime across IDE + terminal + SDK (CLI 3.0 May 2026). 8M+ installs. · `Apache-2.0` · TypeScript · 66.2k★ *GitHub API, 2026-08-16*
- **[Roo Code](https://github.com/RooCodeInc/Roo-Code)** ![archived](https://img.shields.io/badge/archived-lightgrey) — ARCHIVED May 15, 2026 (final v3.54.0). Cline fork w/ custom modes. Team pivoted to 'Roomote' (Slack-first cloud). Successors: Zoo Code, Kilo Code. · `Apache-2.0` · TypeScript · 24.3k★ *GitHub API, 2026-08-16*
- **[Devin / Cognition](https://cognition.ai)** ![active](https://img.shields.io/badge/active-brightgreen) — Managed 'autonomous software engineer.' Devin Desktop (Jun 2026) on Rust 'Devin Local' engine (ACP + third-party agents). 'Managed Devins' = coordinator spawning parallel child agents. · `Proprietary`

---

<a name="desktop"></a>
## 🖥️ Desktop Apps & IDEs

The GUI counterparts to the CLI coding agents. Some are standalone IDEs (Cursor, Windsurf, Zed); others are native desktop wrappers around vendor agent stacks (Claude Desktop, Codex Desktop, GitHub Copilot App). The pattern in 2026: **every major coding agent now ships a desktop app** — the terminal is no longer the only surface.

- **[Claude Desktop](https://claude.ai/download)** ![active](https://img.shields.io/badge/active-brightgreen) — Native macOS + Windows app (no Linux). Three tabs: Chat, Cowork (autonomous agent for local files/tasks), Code (Claude Code GUI). MCP server connections, Desktop Extensions (.mcpb one-click bundles), Computer Use mode. Windows reached full parity Feb 2026. · `Proprietary`
- **[ChatGPT Desktop / Work](https://chatgpt.com)** ![active](https://img.shields.io/badge/active-brightgreen) — Unified Mac + Windows desktop app (Jul 9, 2026). Merges ChatGPT, Codex, and browser workflows: built-in browser, Work mode, scheduled tasks, computer control, cloud browser, Sites, and mobile task handoff. Atlas was sunset Aug 9 in favor of this surface. Aug: Computer Use reached Edge alongside Chrome (via 'More browsers' extension install); on macOS agents run background-parallel, on Windows they take the cursor in the foreground. Developer-mode CDP access and Appshots (full-text window capture) round out the loop. · `Proprietary`
- **[GitHub Copilot App](https://github.com/features/copilot)** ![GA](https://img.shields.io/badge/GA-brightgreen) — GA June 17, 2026 (macOS / Windows / Linux). Agent-native desktop — My Work view across repos, git worktrees for parallel agent sessions, Canvases (bidirectional human-agent surfaces), Cloud Automations (scheduled agent tasks), Agent Merge (CI-to-green). MCP support. AVAILABLE ON ALL PLANS from Jul 7, 2026 — including Copilot Free and GitHub Education. BYOK access for non-subscribers. · `Proprietary`
- **[Cursor](https://cursor.com)** ![active](https://img.shields.io/badge/active-brightgreen) — Leading AI-native IDE ($100M+ ARR). VS Code fork with Composer (multi-file agent edits), Background Agents (parallel cloud sessions), BugBot (PR review). Best @codebase indexing on large repos. Free / $20 Pro / $40 Team. · `Proprietary` · TypeScript
- **[Windsurf](https://codeium.com/windsurf)** ![active](https://img.shields.io/badge/active-brightgreen) — AI IDE acquired by Cognition (absorbing Devin cloud platform). Cascade agent = strongest autonomous multi-file loop in its class. Readable plan view for long sessions. ~$15/mo Pro. VS Code fork. · `Proprietary` · TypeScript
- **[Zed](https://github.com/zed-industries/zed)** ![active](https://img.shields.io/badge/active-brightgreen) — Fastest AI IDE — sub-second cold start, 2ms input latency. Rust-native (not a VS Code fork). v1.0 with open agent protocol. Native real-time multiplayer collaboration. Best-in-class Vim mode. Zero vendor lock-in (BYO key). · `GPL-3.0 / Apache-2.0` · Rust · 88.7k★ *GitHub API, 2026-08-16*
- **[Qt Creator 20](https://github.com/qt-creator/qt-creator)** ![active](https://img.shields.io/badge/active-brightgreen) — Qt Creator 20 (Jun 2026) added ACP Client extension — chat panel for AI coding agents (Claude Code, Codex, Gemini, Copilot). MCP Server extension for tool access. Zen Mode for focus. Major C++/Qt IDE entering the agent era. · `GPL-3.0 / commercial` · C++ · 3.1k★ *GitHub API, 2026-08-16*
- **[GitKraken Kepler](https://www.gitkraken.com/kepler)** ![active](https://img.shields.io/badge/active-brightgreen) — Agentic Development Environment (ADE) — delivery engine for managing parallel AI coding agents. Directs multiple agents, drives output through to merged. Win/Mac/Linux + browser. SSH/WSL support. GitKraken Desktop 12.4 (Aug 4): per-worktree WIP nodes in the commit graph for every running agent session, inline Allow/Deny controls for Claude Code permission requests, agent status surface (Running/Thinking/Waiting) across sessions, and issue-primed agent launches. · `Proprietary`

---

<a name="agent-managers"></a>
## 🐄 Agent Managers & Multiplexers

These tools don't run agents themselves — they manage parallel AI coding agent sessions the way tmux manages terminals. The problem they solve: when you're running 3–10 agents across separate terminals, you lose track of what's blocked, what's done, and what needs input. The category emerged in early 2026 and is moving fast.

- **[cmux](https://github.com/manaflow-ai/cmux)** ![active](https://img.shields.io/badge/active-brightgreen) — The dominant agent multiplexer by traction (22.7k★). Native macOS terminal built on libghostty with agent-state awareness, subagent-to-pane promotion, built-in browser automation pane, iOS app (beta), Unix socket + CLI API, skills system, SSH remote attach. Survives full reboots with session restore. · `MIT` · Swift (AppKit + libghostty) · 26.1k★ *GitHub API, 2026-08-16*
- **[Agent of Empires (AoE)](https://github.com/agent-of-empires/agent-of-empires)** ![active](https://img.shields.io/badge/active-brightgreen) — TUI + web dashboard (PWA) session manager for AI coding agents. Each agent in its own tmux session + git worktree. Docker sandboxing option. Mobile phone access via built-in HTTP server. 104 releases — one of the most actively developed in the category. · `MIT` · Rust · 3.1k★ *GitHub API, 2026-08-16*
- **[dmux](https://github.com/standardagents/dmux)** ![active](https://img.shields.io/badge/active-brightgreen) — Dev agent multiplexer for git worktrees. Each pane gets its own worktree + branch for full isolation. Multi-select agent launches (run different agents per pane). AI-named branches/commits, smart one-step merge, built-in file browser, lifecycle hooks. · `MIT` · TypeScript, Shell · 1.7k★ *GitHub API, 2026-08-16*
- **[Multica](https://github.com/multica-ai/multica)** ![active](https://img.shields.io/badge/active-brightgreen) — Kanban board orchestration for coding agents (37.7k★). Agents get profiles, skills, and assigned issues with statuses — like human teammates in Linear. Vendor-neutral, drives 12+ CLIs. Control plane (Next.js + Go + Postgres) in the cloud, daemon runs agents locally in git worktrees on the user's machine. Uses existing subscriptions, not API keys. · `Apache-2.0` · Go, TypeScript, Next.js · 46.1k★ *GitHub API, 2026-08-16*
- **[Parallel Code](https://github.com/johannesjo/parallel-code)** ![active](https://img.shields.io/badge/active-brightgreen) — GUI desktop app for parallel multi-agent coding. Auto-creates git worktree per task (zero conflict between agents). QR-code phone monitoring over Wi-Fi/Tailscale. Keyboard-first navigation. Merge back to main from sidebar. · `MIT` · TypeScript · 973★ *GitHub API, 2026-08-16*
- **[Agent Deck](https://github.com/asheshgoplani/agent-deck)** ![active](https://img.shields.io/badge/active-brightgreen) — Go-based TUI 'command center' for AI coding agents. 343 releases — most iterated tool in category. Groups, search, session forking, git worktrees, per-agent cost tracking, and a phone-controlled 'Conductor' mode for fleet management. · `MIT` · Go · 725★ *GitHub API, 2026-08-16*
- **[Herdr](https://github.com/ogulcancelik/herdr)** ![active](https://img.shields.io/badge/active-brightgreen) — The reference agent multiplexer — tmux for AI coding agents (14.7k★). Workspaces, tabs, panes with agent-state awareness (blocked/working/done/idle). Detach/reattach over SSH, sessions persist. Unix socket API lets agents orchestrate each other. No GUI, no Electron, runs anywhere you can ssh. Repo moved from mxhm/herdr to ogulcancelik/herdr. · `AGPL-3.0-or-later (dual with commercial)` · Rust · 29.5k★ *GitHub API, 2026-08-16*
- **[Quil](https://quil.cc)** ![active](https://img.shields.io/badge/active-brightgreen) — Reboot-proof terminal multiplexer for AI dev. Snapshots workspace to disk continuously — close laptop, reboot, type 'quil' and everything restores in <30s incl. auto-resuming Claude Code sessions. Built-in MCP server (18 tools) makes your terminal addressable by agents. Typed panes (not generic shells). · `Proprietary` · Rust (single binary)
- **[TUICommander](https://github.com/sstraus/tuicommander)** ![active](https://img.shields.io/badge/active-brightgreen) — AI-native desktop IDE for multi-agent dev. Up to 50 parallel sessions, each in its own git worktree. Rate-limit detection with countdown timers, question/prompt detection, usage tracking with 7-day charts + 52-week heatmaps. Tauri + SolidJS + Rust. · `Apache-2.0` · Rust, SolidJS, Tauri · 117★ *GitHub API, 2026-08-16*
- **[RelayDeck](https://github.com/relaydeck/relaydeck)** ![beta](https://img.shields.io/badge/beta-orange) — Local-first fleet OS for CLI coding agents. Runs vendor CLIs unattended in PTYs. Agents discover peers by purpose/tags with durable peer-to-peer messaging. Plugin-extensible (harnesses, providers, skills, automations). State in local SQLite, secrets in on-host vault. No cloud account, no telemetry. · `MIT` · Go · 64★ *GitHub API, 2026-08-16*
- **[Fleet](https://github.com/nicknisi/fleet)** ![active](https://img.shields.io/badge/active-brightgreen) — Terminal dashboard for managing multiple Claude Code sessions in tmux. Hooks into Claude Code's event system for real-time agent state tracking. 7 agent states sorted by urgency. Send prompts, approve permissions, filter sessions — all from one pane. Compiled Bun binary. · `MIT` · TypeScript (Bun) · 19★ *GitHub API, 2026-08-16*
- **Databricks Omnigent** ![active](https://img.shields.io/badge/active-brightgreen) — Meta-harness over existing AI agents. Encapsulates any agent (terminal-based or SDK-based) in a runner with sandbox session + unified API. Central server provides policies, session management, and sharing. Strict separation of governance from business logic — policies apply across all connected harnesses. Terminal, web UI, macOS app, mobile, and API surfaces. · `Apache-2.0` · Python
- **[Stably Orca](https://github.com/stablyai/orca)** ![active](https://img.shields.io/badge/active-brightgreen) — Agent Development Environment (ADE) for running a fleet of parallel coding agents (8k★). Each agent gets its own git worktree. Design Mode: click any UI element in embedded Chromium and send HTML/CSS/screenshot to an agent's prompt. Diff annotation layer for inline review. GitHub + Linear integration. Mobile companion (iOS/Android) for monitoring. Agents can also drive Orca via Computer Use mode. · `MIT` · TypeScript, Rust · 46.2k★ *GitHub API, 2026-08-16*

---

<a name="shutdowns"></a>
## 🪦 Shutdowns & Archived (avoid)

These tools were once relevant but are now deprecated, archived, or dead. Listed for reference — avoid recommending them.

| Tool | Status | What happened |
|---|---|---|
| **Lethe** | ![uncertain](https://img.shields.io/badge/uncertain-yellow) | UNCERTAIN — main repo (atemerev/lethe) returned 404 in Aug 2026 (deleted or made private); the author still pushes lethe-website (Jul 16) a… |
| **[Gemini CLI](https://github.com/google-gemini/gemini-cli)** | ![dead](https://img.shields.io/badge/dead-red) | DEAD. Shut down June 18, 2026. All consumer accounts (free/Pro/Ultra) received HTTP 410 Gone. Replaced by closed-source Antigravity CLI (ag… |
| **[Continue](https://github.com/continuedev/continue)** | ![acquired](https://img.shields.io/badge/acquired-blue) | ACQUIRED by Cursor (SpaceX acquired Cursor for $60B). Repo goes read-only July 15, 2026. Code stays public under Apache 2.0 but hosted serv… |
| **[Project Mariner](https://labs.google.com/mariner/landing)** | ![dead](https://img.shields.io/badge/dead-red) | SHUT DOWN May 4, 2026. Browser automation proved too brittle (CAPTCHAs, anti-bot, layout drift). Tech folded into Gemini surfaces. |
| **Manus (Meta)** | ![uncertain](https://img.shields.io/badge/uncertain-yellow) | Cross-platform chat-reachable autonomous agent; 'My Computer' desktop mode (Mar 2026). Meta moving to UNWIND the deal (Beijing divestiture … |
| **[Microsoft AutoGen](https://github.com/microsoft/autogen)** | ![maintenance](https://img.shields.io/badge/maintenance-yellow) | MAINTENANCE MODE. Event-driven multi-agent. Users directed to Microsoft Agent Framework. |
| **[Roo Code](https://github.com/RooCodeInc/Roo-Code)** | ![archived](https://img.shields.io/badge/archived-lightgrey) | ARCHIVED May 15, 2026 (final v3.54.0). Cline fork w/ custom modes. Team pivoted to 'Roomote' (Slack-first cloud). Successors: Zoo Code, Kil… |
| [Operator](https://openai.com/index/introducing-operator/) (OpenAI) | ![dead](https://img.shields.io/badge/dead-red) | Folded into ChatGPT as "agent mode" (Aug 31, 2025) |
| [ChatGPT Atlas](https://www.theverge.com/ai-artificial-intelligence/963654/openai-chatgpt-atlas-ai-browser-shut-down-sunset) (OpenAI) | ![dead](https://img.shields.io/badge/dead-red) | AI browser killed Aug 9, 2026 — 9 months after launch; features folded into the ChatGPT desktop app + Chrome/Edge extensions |
| [Amazon Q Developer CLI](https://github.com/aws/amazon-q-developer-cli) (AWS) | ![archived](https://img.shields.io/badge/archived-lightgrey) | Deprecated (security fixes only); replaced by closed-source Kiro (OSS → closed) |
| [GitHub Spark](https://github.blog/changelog/2026-08-04-upcoming-deprecation-of-github-spark-on-github-com/) (GitHub) | ![dead](https://img.shields.io/badge/dead-red) | No new users from Aug 4, 2026; retires Aug 31 — builders directed to the Copilot ecosystem. Its GitHub Models llm() backend was retired Jul 30 |
| [Flowise](https://github.com/FlowiseAI/Flowise) | ![archived](https://img.shields.io/badge/archived-lightgrey) | Shut down; repo public-archived Aug 10, 2026. Team cites coding agents (Claude Code/OpenClaw) making rigid low-code workflows obsolete |
| Sourcegraph Cody CLI | ![maintenance](https://img.shields.io/badge/maintenance-yellow) | Effectively legacy; successor is **Amp** (`@ampcode/cli`) |

---

<a name="trending"></a>
## 📈 Trending Repos Snapshot (2026-08-16)

User-facing focus; star counts point-in-time and *unverified*. Sorted by stars.

| Repo | Stars (≈) | Category | Why notable |
|---|---|---|---|
| [`openclaw/openclaw`](https://github.com/openclaw/openclaw) | ~386.4k | Always-on assistant | The reference open-source always-on personal assistant (386k★). Self-hosted Gateway daemo… |
| [`NousResearch/hermes-agent`](https://github.com/NousResearch/hermes-agent) | ~231.2k | Always-on assistant | Self-improving always-on agent (231k★). v0.20.0 'Herald' (Aug 3; ~1,400 PRs, 650+ contrib… |
| [`anomalyco/opencode`](https://github.com/anomalyco/opencode) | ~197.9k | CLI coding agent | Highest-traction OSS terminal coding agent. Multi-session parallel agents, desktop beta. … |
| [`anthropics/skills`](https://github.com/anthropics/skills) | ~169.6k | Agent framework / SDK | Reference impl of the Agent Skills standard (SKILL.md capability packs). Widely cited as … |
| [`anthropics/claude-code`](https://github.com/anthropics/claude-code) | ~141.6k | CLI coding agent | Reasoning-quality leader. Fully agentic: multi-file edits, sandboxed bash, subagents, MCP… |
| [`deepseek-ai/deepseek-harness`](https://github.com/deepseek-ai/deepseek-harness) | ~119.8k | CLI coding agent | Open-source agent harness where EVERYTHING is a plugin — the model adapter, tool registry… |
| [`browser-use/browser-use`](https://github.com/browser-use/browser-use) | ~109.4k | Computer-use / browser | Widely-used OSS browser-agent library (109k★, Playwright). Cloud v4 (Aug 7) is a code-wri… |
| [`google-gemini/gemini-cli`](https://github.com/google-gemini/gemini-cli) | ~106.5k | CLI coding agent | DEAD. Shut down June 18, 2026. All consumer accounts (free/Pro/Ultra) received HTTP 410 G… |
| [`openai/codex`](https://github.com/openai/codex) | ~106.2k | CLI coding agent | Sandboxed agentic execution; Rust rewrite. Bundled with ChatGPT plans or API-metered. Top… |
| [`zed-industries/zed`](https://github.com/zed-industries/zed) | ~88.7k | Desktop app / IDE | Fastest AI IDE — sub-second cold start, 2ms input latency. Rust-native (not a VS Code for… |
| [`OpenHands/OpenHands`](https://github.com/OpenHands/OpenHands) | ~84.2k | Computer-use / browser | Self-hosted 'developer control center'. Runs its own agent OR Claude Code/Codex/Gemini. S… |
| [`cline/cline`](https://github.com/cline/cline) | ~66.2k | Agent framework / SDK | Pioneer agentic VS Code extension, repositioned as ONE runtime across IDE + terminal + SD… |

---

<a name="methodology"></a>
## 🔬 Methodology & Caveats

Read this before citing anything here. This is a **landscape map, not a benchmark study.**

- **Star counts are popularity, not quality** — point-in-time snapshots that drift within days. 53 of 54 tracked repos were verified directly from the GitHub API on 2026-08-16; the remainder are marked *unverified* (pulled from tracker/repo pages, not re-pulled).
- **The OSWorld "human parity" story is not clean.** Vendor self-reports vary by ~10 points across aggregators (75% / 83.4% / 85%); the only claimed crossing (Agent S3, 72.60%) is vendor-reported, best-of-N (single-pass 66%), and on no independent leaderboard.
- **The OpenClaw "self-hackable / AGI-like" rhetoric is ahead of the verified evidence.** The skill-creator + hot-reload machinery is real and code-confirmed; the reliable in-practice quality of agent-authored skills is **not independently benchmarked.**
- **Vendor causation is not confirmed** — proprietary launches framed as "responses to OpenClaw" are press inference, not vendor statements.
- **Two "OpenCode" lineages need disambiguation:** the major `sst/opencode` → `anomalyco/opencode` (~176k★) vs the project Charm's Crush was claimed to be "rebranded from" (unverified).

---

<a name="license"></a>
## 📄 License

The research and curation in this repository are provided as-is for the community. Individual tools retain their own licenses (noted per entry). Where this README's prose is original to this repo, it is licensed MIT.

<p align="center"><sub>⚠️ <strong>NOTICE.</strong> This README is produced by an automated weekly research pipeline and may contain errors, outdated information, or omissions. Star counts are point-in-time snapshots. Always verify critical details (tool status, pricing, security claims, license terms) against primary sources before relying on them. Last pipeline run: 2026-08-16.</sub></p>
