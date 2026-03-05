# Standards Update Report
Generated: 2026-03-06
Previous report: 2026-03-05
Sources checked: 10 successful / 10 total

## Summary
- 5 outdated version references
- 22 missing features (8 new since Mar 5, 14 carried forward)
- 9 changed patterns (4 new, 5 carried forward)
- 6 new best practices (3 new, 3 carried forward)
- 1 stale URL pattern
- 1 pricing/limits change

**Note**: The Mar 5 report's items remain **unapplied** (no `--apply` was run). This report covers the delta from v2.1.68→v2.1.69 plus all unapplied items. Items carried forward from Mar 5 are marked (CF). Items carried forward from Feb 23 are marked (CF2).

---

## Outdated Version References

| File | Current Text | Should Be | Confidence |
|------|-------------|-----------|------------|
| CLAUDE_CODE_STANDARDS.md ~L1143 | "Update to v2.1.45 (latest)" | "Update to v2.1.69 (latest)" | high |
| ANTHROPIC_BEST_PRACTICES.md ~L447 | "Update to v2.1.45 minimum" | "Update to v2.1.69 minimum" | high |
| ANTHROPIC_BEST_PRACTICES.md ~L692 | "Update to v2.1.45+ (latest)" | "Update to v2.1.69+ (latest)" | high |
| CODEBASE_STRUCTURE.md ~L9 | "integrates Claude Sonnet 4.5 and 2025 best practices" | "integrates Opus 4.6 and Sonnet 4.6 (February 2026)" | medium (CF2) |
| ANTHROPIC_BEST_PRACTICES.md ~L8 | URL `https://code.claude.com/docs` | Docs now at `https://code.claude.com/docs` (confirmed correct, but old URL `docs.anthropic.com` still referenced in some places) | medium |

---

## Missing Features

### New Since Mar 5 (v2.1.69)

| Feature | Source | Description | Suggested File |
|---------|--------|-------------|---------------|
| `/claude-api` skill | Changelog (2.1.69) | Bundled skill for building apps with the Claude API and Anthropic SDK | CLAUDE_CODE_STANDARDS.md |
| Voice mode (`/voice`) | Changelog (2.1.69), Ecosystem | Voice STT shipped 2026-03-03; now supports 20 languages. Gradual rollout. | CLAUDE_CODE_STANDARDS.md |
| `/teleport` command | Docs | Pull web or iOS session into terminal for cross-device handoff | CLAUDE_CODE_STANDARDS.md |
| `/desktop` command | Docs | Hand off terminal session to Desktop app for visual diff review | CLAUDE_CODE_STANDARDS.md |
| `sandbox.enableWeakerNetworkIsolation` | Changelog (2.1.69) | macOS setting for TLS cert verification with custom MITM proxy | ANTHROPIC_BEST_PRACTICES.md |
| `InstructionsLoaded` hook event | Changelog (2.1.69) | New hook event fired when CLAUDE.md/skills are loaded | CLAUDE_CODE_STANDARDS.md |
| Agent SDK | Docs | Published at platform.claude.com/docs/en/agent-sdk/overview — build custom agents with Claude Code's tools | ANTHROPIC_BEST_PRACTICES.md |
| `includeGitInstructions` setting | Changelog (2.1.69) | Remove built-in commit/PR workflow instructions from context | CLAUDE_CODE_STANDARDS.md |

### Carried Forward from Mar 5 (Still Unapplied)

| Feature | Source | Description | Suggested File |
|---------|--------|-------------|---------------|
| `/simplify` bundled skill (CF) | Changelog (2.1.63) | Reviews recently changed files for quality; spawns 3 parallel review agents; applies fixes automatically | CLAUDE_CODE_STANDARDS.md |
| `/batch` bundled skill (CF) | Changelog (2.1.63) | Orchestrates large-scale changes; decomposes into 5-30 units; spawns one background agent per unit in isolated worktree; each opens a PR | CLAUDE_CODE_STANDARDS.md |
| `/copy` command (CF) | Changelog (2.1.59) | Interactive code block picker with "always copy full response" option | CLAUDE_CODE_STANDARDS.md |
| `/debug` bundled skill (CF) | Best Practices | Troubleshoots current session by reading debug log | CLAUDE_CODE_STANDARDS.md |
| Auto-memory (`/memory`) (CF) | Changelog (2.1.59) | Claude auto-saves context between sessions; manage with `/memory` command | CLAUDE_CODE_STANDARDS.md |
| HTTP hooks (CF) | Changelog (2.1.63) | POST JSON to URL as alternative to shell command hooks; `type: "http"` in config | CLAUDE_CODE_STANDARDS.md |
| `claude remote-control` (CF) | Changelog (2.1.51) | Subcommand for remote control sessions; `--remote` flag creates web session. v2.1.69 adds optional `name` argument. | CLAUDE_CODE_STANDARDS.md |
| LSP tool (CF) | Changelog (2.1.50+) | Code intelligence: go-to-definition, find-references, hover docs | CLAUDE_CODE_STANDARDS.md |
| Plugin marketplace (CF) | Best Practices | `/plugin` command; `/reload-plugins` (v2.1.69); `git-subdir` source type (v2.1.69); custom npm registries + version pinning | CLAUDE_CODE_STANDARDS.md |
| Managed settings (CF) | Changelog (2.1.51) | macOS plist or Windows Registry for org-wide settings. `allowManagedHooksOnly`, `pluginTrustMessage` (v2.1.69). | CLAUDE_CODE_STANDARDS.md |
| Opus 4/4.1 removed (CF) | Changelog (2.1.68) | Fully removed from first-party API; users auto-migrated to Opus 4.6 | ANTHROPIC_BEST_PRACTICES.md |
| Claude Cowork (CF) | Ecosystem | Enterprise task automation via MCP. Research preview late Jan 2026. Runs locally in isolated VM. Included in Max plan. | ANTHROPIC_BEST_PRACTICES.md |
| MCP Apps (CF) | Ecosystem | Interactive UI rendered inside chat via `ui://` scheme. SDK: `@modelcontextprotocol/ext-apps`. | ANTHROPIC_BEST_PRACTICES.md |

### Carried Forward from Feb 23 (CF2)

| Feature | Source | Description | Suggested File |
|---------|--------|-------------|---------------|
| `--worktree` / `-w` flag (CF2) | Changelog (2.1.49) | Start Claude in isolated git worktree; agents support `isolation: "worktree"` | CLAUDE_CODE_STANDARDS.md |
| `background: true` agents (CF2) | Changelog (2.1.49) | Agent definitions support `background: true` to run as background tasks | CLAUDE_CODE_STANDARDS.md |
| New hook events (CF2) | Changelog (2.1.49-69) | `WorktreeCreate`, `WorktreeRemove`, `ConfigChange` (2.1.49-50), `InstructionsLoaded` (2.1.69) | CLAUDE_CODE_STANDARDS.md |
| `claude agents` CLI (CF2) | Changelog (2.1.50) | CLI command to list configured agents | CLAUDE_CODE_STANDARDS.md |
| `CLAUDE_CODE_DISABLE_1M_CONTEXT` (CF2) | Changelog (2.1.50) | Env var to disable 1M context window | CLAUDE_CODE_STANDARDS.md |

---

## Changed Patterns

| Pattern | File | Current | Updated | Source | Confidence |
|---------|------|---------|---------|--------|------------|
| Opus 4.6 default effort (CF) | ANTHROPIC_BEST_PRACTICES.md ~L55 | "high (default)" | Medium is now default in Claude Code for Max/Team (v2.1.68). `ultrathink` keyword forces high effort for one turn. | Changelog, Best Practices | high |
| Commands → Skills migration (CF) | CLAUDE_CODE_STANDARDS.md | Commands (`.claude/commands/`) as primary | Skills (`.claude/skills/<name>/SKILL.md`) preferred. `disable-model-invocation`, `context: fork`, `${CLAUDE_SKILL_DIR}`, per-skill hooks. | Best Practices, Docs | high |
| Prefilled assistant turns (CF) | Not documented | Not mentioned | Deprecated in 4.6 models. Migration: format control → structured outputs; preambles → system prompt; continuations → user turn. | Prompt Engineering docs | high |
| `--dangerously-skip-permissions` deprecated | ANTHROPIC_BEST_PRACTICES.md ~L186-189 | Recommended in containers | Now explicitly deprecated in favour of `/sandbox`. Only safe in containers without internet. | Best Practices blog | high |
| CLAUDE.md `@import` syntax | Not documented | Not mentioned | `@path/to/file` within CLAUDE.md pulls in external files. Child-directory CLAUDE.md loaded on demand. | Best Practices blog | high |
| Docs URL migration | Multiple files | `docs.anthropic.com/en/docs/claude-code` | Now `code.claude.com/docs` (old URL redirects) | Docs | high |
| Sonnet 4.6 API effort default | Not documented | Not mentioned | Sonnet 4.6 defaults to `high` effort in API (unlike Sonnet 4.5 which had no effort param). Must set explicitly for predictable cost/latency. | Prompt Engineering docs | high |
| BashTool login shell (CF) | Not documented | Not mentioned | Skips login shell by default (v2.1.51). Previously opt-in via `CLAUDE_BASH_NO_LOGIN`. | Changelog | medium |
| Tool result persistence (CF) | Not documented | Not mentioned | Threshold lowered from 100K to 50K chars for disk persistence (v2.1.51) | Changelog | low |

---

## New Best Practices

| Practice | Source | Description | Suggested Location |
|----------|--------|-------------|-------------------|
| Anti-laziness prompting causes overtriggering | Prompt Engineering | Aggressive system prompt language ("CRITICAL: You MUST") that worked on older models causes overtriggering on 4.6. Dial back aggressive language. Opus 4.6 is more responsive to system prompts. | ANTHROPIC_BEST_PRACTICES.md (Prompt Patterns) |
| Opus 4.6 subagent overtriggering | Prompt Engineering | Opus 4.6 proactively delegates to subagents without prompting — but overtriggers. Add explicit guidance about when subagents are/aren't warranted. | ANTHROPIC_BEST_PRACTICES.md (Multi-Agent) |
| Anti-overengineering system prompt | Prompt Engineering | Opus 4.5 and 4.6 have overengineering tendency. Add explicit anti-overengineering block to constrain scope, docs, defensive coding, and abstractions. | ANTHROPIC_BEST_PRACTICES.md (Prompt Patterns) |
| Verification-first development (CF) | Best Practices blog | Single highest-leverage practice: always provide verification criteria (tests, screenshots, expected outputs). | CLAUDE_CODE_STANDARDS.md (Core Principles) |
| "Interview me" pattern (CF) | Best Practices blog | For larger features: ask Claude to interview you, write spec to SPEC.md, start fresh session to implement. | CLAUDE_CODE_STANDARDS.md (Workflow Patterns) |
| Five named failure patterns (CF) | Best Practices blog | Kitchen sink session, repeated corrections, over-specified CLAUDE.md, trust-then-verify gap, infinite exploration. | CLAUDE_CODE_STANDARDS.md (Anti-Patterns) |

---

## Stale URLs

| File | Line | URL | Status |
|------|------|-----|--------|
| ANTHROPIC_BEST_PRACTICES.md | L8 | `https://code.claude.com/docs` | Working, but some internal references may still use `docs.anthropic.com` which 308-redirects |

---

## Pricing & Limits Changes

| Item | Current Value | Updated Value | Source | Confidence |
|------|-------------|---------------|--------|------------|
| Opus 4.6 Fast Mode | Not documented | $30/$150 per MTok, ≤200K context, research preview | Pricing search | medium |
| Opus 4.6 1M context | "1M beta" | May be GA (not just beta) — multiple sources describe it without "beta" qualifier | Docs, Model search | medium |

Core pricing unchanged:

| Model | Input/Output per MTok | Context | Max Output |
|-------|----------------------|---------|------------|
| Opus 4.6 | $5 / $25 | 200K (1M beta/GA?) | 128K |
| Opus 4.6 Fast | $30 / $150 | 200K | 128K |
| Sonnet 4.6 | $3 / $15 | 200K (1M beta) | 64K |
| Haiku 4.5 | $1 / $5 | 200K | 64K |

Additional confirmed facts (unchanged):
- Batch API: 50% discount on all models
- Prompt caching: 90% discount on repeated context
- Max plan: Pro $20/mo, Max 5x $100/mo, Max 20x $200/mo
- Claude Code bundled in Max at no extra charge
- 7-day rolling usage reset (not monthly)

---

## Per-File Change Checklist

### CLAUDE_CODE_STANDARDS.md

- [x] Update CLI version from "v2.1.45" to "v2.1.69"
- [x] Add `/claude-api`, `/simplify`, `/batch`, `/copy`, `/debug` bundled skills documentation
- [x] Add voice mode (`/voice`) — 20 languages, shipped 2026-03-03
- [x] Add `/teleport` and `/desktop` cross-surface handoff commands
- [x] Add `/rewind` partial compaction from checkpoint
- [x] Add auto-memory feature and `/memory` command
- [x] Add HTTP hooks (`type: "http"`) alongside shell command hooks
- [x] Add `InstructionsLoaded` hook event
- [x] Add `claude remote-control` subcommand with optional `name` argument
- [x] Add LSP tool (code intelligence: go-to-definition, find-references, hover)
- [x] Add plugin marketplace: `/plugin`, `/reload-plugins`, `git-subdir` source, npm registries, version pinning
- [x] Update Commands section to reference Skills as preferred approach (`.claude/skills/<name>/SKILL.md`)
- [x] Add `${CLAUDE_SKILL_DIR}` variable for skills
- [x] Add `disable-model-invocation: true` skill frontmatter
- [x] Add CLAUDE.md `@import` syntax (`@path/to/file`)
- [x] Add `includeGitInstructions` setting
- [x] Add managed settings documentation (macOS plist, Windows Registry, `allowManagedHooksOnly`, `pluginTrustMessage`)
- [x] Add `Ctrl+G` to edit plan in external editor
- [x] Add subagent `model:` frontmatter field (per-agent model selection)
- [x] Add verification-first development as core practice
- [x] Add "interview me" pattern for feature development
- [x] Add five named failure patterns (anti-patterns section)
- [x] (CF2) Add `--worktree` / `-w` flag and `isolation: worktree` for agents
- [x] (CF2) Add `background: true` agent support
- [x] (CF2) Add `WorktreeCreate`, `WorktreeRemove`, `ConfigChange` hook events
- [x] (CF2) Add `claude agents` CLI command
- [x] (CF2) Add `CLAUDE_CODE_DISABLE_1M_CONTEXT` env var

### ANTHROPIC_BEST_PRACTICES.md

- [x] Update CLI version refs from "v2.1.45" to "v2.1.69"
- [x] Update Opus 4.6 default effort: medium in Claude Code Max/Team. `ultrathink` for forcing high effort.
- [x] Add Sonnet 4.6 API effort default: `high` — must set explicitly for predictable cost
- [x] Note Opus 4/4.1 fully removed from first-party API
- [x] Add Agent SDK (platform.claude.com/docs/en/agent-sdk/overview)
- [x] Add Claude Cowork (research preview, isolated VM, MCP integrations, Max plan)
- [x] Add MCP Apps (interactive UI, `ui://` scheme, SDK)
- [x] Add prefilled assistant turns deprecation note with migration paths for 4.6 models
- [x] Add BashTool login shell default change (v2.1.51)
- [x] Add anti-laziness prompting guidance (dial back aggressive language on 4.6)
- [x] Add Opus 4.6 subagent overtriggering guidance
- [x] Add anti-overengineering system prompt recommendation
- [x] Update `--dangerously-skip-permissions` to note deprecation; recommend `/sandbox`
- [x] Add Opus 4.6 Fast Mode pricing ($30/$150/MTok, research preview)
- [x] Add `sandbox.enableWeakerNetworkIsolation` setting (macOS)
- [x] Update docs URL references from `docs.anthropic.com` to `code.claude.com`
- [x] (CF2) Add SDK model capability fields (`supportsEffort`, `supportsAdaptiveThinking`)
- [x] (CF2) Add Opus 4.6 fast mode 1M context note

### CODEBASE_STRUCTURE.md

- [x] (CF2) Update "Claude Sonnet 4.5 and 2025" references to "Opus 4.6 and Sonnet 4.6 (2026)"

### templates/claude-md/web-app.md

- [x] (CF2) Replace "Claude Sonnet 4.5" references with current models

---

## Changelog Summary (v2.1.68 → v2.1.69)

| Version | Date | Key Changes |
|---------|------|------------|
| 2.1.69 | ~Mar 5 | `/claude-api` skill; Voice STT 20 languages; `sandbox.enableWeakerNetworkIsolation`; `includeGitInstructions` setting; `/reload-plugins`; `git-subdir` plugin source; `${CLAUDE_SKILL_DIR}`; `InstructionsLoaded` hook; `agent_id`/`agent_type`/`worktree` in hook events; `pluginTrustMessage`; `pathPattern` regex for marketplaces; `oauth.authServerMetadataUrl` for MCP; effort level in logo/spinner; agent name in title; one-time Desktop prompt |

### Prior Versions (v2.1.50 → v2.1.68, from Mar 5 report)

| Version | Date | Key Changes |
|---------|------|------------|
| 2.1.68 | Mar 4 | Opus 4.6 defaults medium effort (Max/Team); ultrathink re-introduced; Opus 4/4.1 removed |
| 2.1.66 | Mar 2 | Reduced spurious error logging |
| 2.1.63 | Feb 28 | `/simplify`, `/batch` bundled skills; HTTP hooks; auto-memory; MCP OAuth URL paste; `ENABLE_CLAUDEAI_MCP_SERVERS=false` |
| 2.1.62 | Feb 27 | Prompt suggestion cache fix |
| 2.1.61 | Feb 26 | Windows config concurrent write fix |
| 2.1.59 | Feb 26 | Auto-memory (`/memory`); `/copy` command; MCP OAuth token refresh fix |
| 2.1.58 | Feb 25 | Remote Control expanded |
| 2.1.56 | Feb 24 | VS Code crash fix |
| 2.1.55 | Feb 23 | Windows BashTool EINVAL fix |
| 2.1.53 | Feb 22 | UI flicker fix; `--worktree` first-launch fix; Windows WASM crash fix |
| 2.1.52 | Feb 21 | VS Code Windows crash fix |
| 2.1.51 | Feb 20 | `remote-control` subcommand; plugin npm registries + version pinning; BashTool skips login shell default; tool results >50K to disk; managed settings (plist/registry); account/email/org env vars; statusLine/fileSuggestion security fix |

---

## New Environment Variables (Since v2.1.50)

| Variable | Version | Purpose |
|----------|---------|---------|
| `CLAUDE_CODE_ACCOUNT_UUID` | 2.1.51 | Provide account UUID synchronously |
| `CLAUDE_CODE_USER_EMAIL` | 2.1.51 | Provide user email synchronously |
| `CLAUDE_CODE_ORGANIZATION_UUID` | 2.1.51 | Provide org UUID synchronously |
| `ENABLE_CLAUDEAI_MCP_SERVERS` | 2.1.63 | `false` to disable claude.ai MCP servers (default: true) |
| `SLASH_COMMAND_TOOL_CHAR_BUDGET` | 2.1.63 | Override skill description budget (fallback: 16K chars) |

---

## Prompt Engineering Updates (New Section)

Key guidance from Anthropic's prompt engineering docs for Claude 4.6 models:

| Topic | Guidance | Confidence |
|-------|----------|------------|
| Effort parameter | Sonnet 4.6 defaults `high` in API — set explicitly. Recommended: `medium` for most apps, `low` for high-volume. | high |
| Adaptive thinking | Opus 4.6 uses `thinking: {type: "adaptive"}`. Outperforms extended thinking in internal evals. | high |
| Prefill migration | Deprecated on 4.6. Format control → structured outputs. Preambles → system prompt. Continuations → user turn. | high |
| Anti-laziness | Remove "CRITICAL: You MUST" language — causes overtriggering on 4.6. Use measured instructions. | high |
| Subagent control | Opus 4.6 proactively spawns subagents. Add explicit when-to/when-not-to guidance. | high |
| Anti-overengineering | Add explicit scope constraints — 4.5/4.6 tend to over-abstract, over-document, over-defend. | high |
| Action bias tuning | `<default_to_action>` or `<do_not_act_before_instructions>` system prompt blocks | medium |
| Investigate first | `<investigate_before_answering>` block reduces hallucination in agentic coding | medium |
| Frontend aesthetics | `<frontend_aesthetics>` system prompt block prevents "AI slop" generic designs | medium |
| Vision improvements | Opus 4.5/4.6 better on multi-image. Crop tool/skill improves performance. | medium |
| Opus LaTeX default | Opus 4.6 defaults to LaTeX for maths — suppress with explicit instruction | low |

---

## Upcoming / Rumoured

| Item | Source | Status | Confidence |
|------|--------|--------|------------|
| Sonnet 5 ("Fennec") | Vertex AI logs, rumour sites | Expected Feb-Mar 2026. Reportedly surpasses Opus 4.5 on coding/maths. ~50% cheaper than Opus 4.5. | low |
| Vercept acquisition | News (Feb 25, 2026) | Anthropic acquired Vercept for improved computer use capabilities | medium |

---

## Source Fetch Log

| Source | URL | Status | Key Facts |
|--------|-----|--------|-----------|
| Best Practices Blog | code.claude.com/docs/en/best-practices | success (via redirect) | 50+ |
| Anthropic Teams Blog | claude.com/blog/how-anthropic-teams-use-claude-code | success (via redirect) | 25+ |
| Claude Code Docs | code.claude.com/docs | success (via redirect) | 40+ |
| Changelog | code.claude.com/docs/en/changelog | success | v2.1.69 found |
| Sandboxing Blog | anthropic.com/engineering/claude-code-sandboxing | success | 12 |
| Prompt Engineering | platform.claude.com/docs/en/build-with-claude/prompt-engineering | success | 30+ |
| Model Announcements | WebSearch | success | 15+ |
| Engineering Blog | WebSearch | partial | 12+ |
| Pricing & Plans | WebSearch | success | 15+ |
| Ecosystem Updates | WebSearch | success | 20+ |

---

## Current Model Reference (March 2026)

| Model | ID | Pricing (In/Out per MTok) | Context | Max Output | Status |
|-------|----|--------------------------|---------|------------|--------|
| Opus 4.6 | `claude-opus-4-6` | $5 / $25 | 200K (1M beta/GA?) | 128K | Current flagship |
| Opus 4.6 Fast | `claude-opus-4-6` | $30 / $150 | 200K | 128K | Research preview |
| Sonnet 4.6 | `claude-sonnet-4-6` | $3 / $15 | 200K (1M beta) | 64K | Current default |
| Haiku 4.5 | `claude-haiku-4-5-20251001` | $1 / $5 | 200K | 64K | Current fast |
| Sonnet 4.5 | `claude-sonnet-4-5-20250929` | $3 / $15 | 200K | 64K | Legacy |
| Opus 4.5 | `claude-opus-4-5-20251101` | $5 / $25 | 200K | 64K | Legacy |
| Opus 4.1 | `claude-opus-4-1-20250805` | — | — | — | **Removed** (first-party API) |
| Opus 4 | `claude-opus-4-20250514` | — | — | — | **Removed** (first-party API) |
| Sonnet 5 "Fennec" | TBD | ~50% of Opus 4.5? | TBD | TBD | **Rumoured** (imminent) |

## Key Version Info

| Item | Value |
|------|-------|
| Claude Code CLI | v2.1.69 (latest as of Mar 6, 2026) |
| Opus 4.6 release | Feb 5, 2026 |
| Sonnet 4.6 release | Feb 17, 2026 |
| Haiku 4.5 release | Oct 15, 2025 |
| Claude 3 Haiku deprecation | Apr 19, 2026 |
| Docs URL | code.claude.com/docs |
| API Docs URL | platform.claude.com |
| Best Practices | code.claude.com/docs/en/best-practices |
| Changelog | code.claude.com/docs/en/changelog |
| Agent SDK | platform.claude.com/docs/en/agent-sdk/overview |
