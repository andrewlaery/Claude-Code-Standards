# Standards Update Report
Generated: 2026-02-19
Sources checked: 10 successful / 10 total

## Summary
- 23 outdated model references
- 27 missing features
- 8 changed patterns
- 6 new best practices
- 4 stale URLs
- 9 pricing/limits changes

---

## Outdated Model References

| File | Line | Current Text | Should Be | Confidence |
|------|------|-------------|-----------|------------|
| CLAUDE_CODE_STANDARDS.md | 601 | "Claude Sonnet 4.5's hybrid reasoning model" | "Opus 4.6 and Sonnet 4.6's adaptive reasoning" | high |
| CLAUDE_CODE_STANDARDS.md | 604-608 | Fixed thinking budgets: 4K/10K/32K/64K mapped to keywords | Adaptive thinking with effort levels (low/medium/high/max). Keywords like "think hard" are regular prompt instructions, NOT token-allocation controls | high |
| CLAUDE_CODE_STANDARDS.md | 611 | "Hybrid Reasoning Model (Claude Sonnet 4.5)" | "Adaptive Reasoning (Opus 4.6 / Sonnet 4.6)" | high |
| CLAUDE_CODE_STANDARDS.md | 617-621 | "think (4K)", "think hard (10K)", "ultrathink (32K)", "64K budget" as specific allocations | Effort levels: low, medium, high (default), max (Opus 4.6 only). Fixed budget_tokens deprecated on 4.6 models | high |
| CLAUDE_CODE_STANDARDS.md | 911 | "Opus 4 orchestrator + Sonnet 4 workers" | "Opus 4.6 orchestrator + Sonnet 4.6 workers" (or native Agent Teams) | high |
| CLAUDE_CODE_STANDARDS.md | 916 | "Lead agent (Opus 4) coordinates specialized workers (Sonnet 4)" | "Lead agent (Opus 4.6) coordinates specialized workers (Sonnet 4.6)" | high |
| CLAUDE_CODE_STANDARDS.md | 1002 | "v0.2.111 (CLI) or v1.0.20 (latest)" | "v2.1.45 (latest)" | high |
| CLAUDE_CODE_STANDARDS.md | 1073 | "Same Claude Sonnet 4.5 model capabilities" | "Claude Opus 4.6 and Sonnet 4.6 capabilities" | high |
| ANTHROPIC_BEST_PRACTICES.md | 39 | "Extended Thinking Integration (Claude Sonnet 4.5 - 2025 Update)" | "Adaptive Reasoning (Opus 4.6 / Sonnet 4.6 - February 2026)" | high |
| ANTHROPIC_BEST_PRACTICES.md | 43-47 | Fixed thinking budgets: 4K/10K/32K/64K | Adaptive thinking with effort levels. budget_tokens deprecated on 4.6 models | high |
| ANTHROPIC_BEST_PRACTICES.md | 57 | "Hybrid Reasoning Model (Claude Sonnet 4.5)" | "Adaptive Reasoning Model (Opus 4.6 / Sonnet 4.6)" | high |
| ANTHROPIC_BEST_PRACTICES.md | 85 | "Claude Sonnet 4.5 Capabilities (September 2025)" | "Current Model Capabilities (February 2026)" with Opus 4.6 + Sonnet 4.6 benchmarks | high |
| ANTHROPIC_BEST_PRACTICES.md | 89 | "30+ hours of autonomous work (vs 7 hours for Opus 4)" | Update with Opus 4.6 / Sonnet 4.6 benchmarks (SWE-bench: 80.8%/79.6%, OSWorld: 72.7%/72.5%) | high |
| ANTHROPIC_BEST_PRACTICES.md | 100 | "Same as Claude Sonnet 4: $3/$15 per million tokens" | Sonnet 4.6: $3/$15 per MTok. Opus 4.6: $5/$25 per MTok | high |
| ANTHROPIC_BEST_PRACTICES.md | 436 | "Update to v0.2.111 or v1.0.20 minimum" | "Update to v2.1.45 (latest)" | high |
| ANTHROPIC_BEST_PRACTICES.md | 514 | "Claude Sonnet 4.5 capabilities" | "Opus 4.6 and Sonnet 4.6 capabilities" | high |
| ANTHROPIC_BEST_PRACTICES.md | 576 | "Opus 4 orchestrator + Sonnet 4 workers vs single Opus 4" | "Opus 4.6 orchestrator + Sonnet 4.6 workers" or Agent Teams | high |
| ANTHROPIC_BEST_PRACTICES.md | 582-583 | "Orchestrator Agent: Opus 4" / "Worker Agents: Sonnet 4" | "Orchestrator: Opus 4.6" / "Workers: Sonnet 4.6" | high |
| ANTHROPIC_BEST_PRACTICES.md | 634 | "30+ hours of autonomous work with Claude Sonnet 4.5" | Update to current Opus 4.6 / Sonnet 4.6 benchmarks | high |
| ANTHROPIC_BEST_PRACTICES.md | 637-639 | "0% error rate (Sonnet 4.5)", "61.4% OSWorld" | Sonnet 4.6: SWE-bench 79.6%, OSWorld 72.5%. Opus 4.6: SWE-bench ~80.8%, OSWorld 72.7% | high |
| ANTHROPIC_BEST_PRACTICES.md | 644 | "Upgrade to Claude Sonnet 4.5" | "Upgrade to Opus 4.6 / Sonnet 4.6" | high |
| README.md | 9 | "Updated for Claude Sonnet 4.5 (September 2025)" | "Updated for Opus 4.6 and Sonnet 4.6 (February 2026)" | high |
| README.md | 11 | "Powered by Claude Sonnet 4.5" | "Powered by Claude Opus 4.6 and Sonnet 4.6" | high |

---

## Missing Features

| Feature | Source | Description | Suggested File |
|---------|--------|-------------|---------------|
| Agent Teams | Docs, Blog, Models | Native multi-agent orchestration in Claude Code. Lead agent delegates to teammates with independent context windows. Enable via `CLAUDE_CODE_EXPERIMENTAL_AGENT_TEAMS=1`. Research preview. | CLAUDE_CODE_STANDARDS.md (Multi-Agent section) |
| Skills System | Docs, Blog | `.claude/skills/<name>/SKILL.md` with YAML frontmatter. Invoked via `/skill-name`. Supports `$ARGUMENTS`, `disable-model-invocation`, `allowed-tools`, `model`, `context: fork`. Hot-reload, auto-discovery from nested dirs. | CLAUDE_CODE_STANDARDS.md (new section) |
| Hooks System | Docs, Blog | Deterministic script execution at workflow lifecycle points (SessionStart, PreToolUse, PostToolUse, Stop, etc.). Three types: command, prompt, agent. Configure via `/hooks` or `.claude/settings.json`. | CLAUDE_CODE_STANDARDS.md (new section) |
| Plugins Marketplace | Blog | Bundles of skills, hooks, subagents, and MCP servers. Browse via `/plugin`. Code intelligence plugins provide symbol navigation and error detection. | CLAUDE_CODE_STANDARDS.md (Advanced section) |
| Auto Memory | Blog, Docs | Persistent per-project memory at `~/.claude/projects/<project>/memory/`. MEMORY.md (first 200 lines) loaded per session. Claude automatically saves patterns, debugging insights, preferences. | CLAUDE_CODE_STANDARDS.md (Context section) |
| Modular Rules | Blog | `.claude/rules/*.md` — auto-loaded project rules. Path-scoped via `paths:` YAML frontmatter. Subdirectories and symlinks supported. User-level rules at `~/.claude/rules/`. | CLAUDE_CODE_STANDARDS.md (CLAUDE.md section) |
| Adaptive Thinking | Models, Blog, Docs | Replaces fixed budget_tokens on 4.6 models. Uses `thinking: {type: "adaptive"}` API. Effort levels: low/medium/high/max. Interleaved thinking auto-enabled. `CLAUDE_CODE_EFFORT_LEVEL` env var. | CLAUDE_CODE_STANDARDS.md (Thinking section), ANTHROPIC_BEST_PRACTICES.md |
| Compaction | Blog, Ecosystem | Automatic server-side context summarization. `/compact <instructions>` for manual control. Auto-compaction triggers near context limits. Enables effectively infinite conversations. | CLAUDE_CODE_STANDARDS.md (Context section) |
| Session Management | Blog, Docs | `--continue` / `--resume` / `--from-pr <N>`. `/rename` to name sessions. `/resume` for session picker. Sessions stored per project. Forked sessions grouped under root. | CLAUDE_CODE_STANDARDS.md (new section) |
| Chrome Extension | Blog, Ecosystem | Browser automation from Claude Code terminal. Opens tabs, tests UI, iterates on visual changes. | ANTHROPIC_BEST_PRACTICES.md (Deployment section) |
| Desktop App | Docs, Ecosystem | Standalone app for macOS (universal), Windows x64, Windows ARM64. Visual diff review, rich UI. | ANTHROPIC_BEST_PRACTICES.md (Deployment section) |
| Slack Integration | Blog, Docs | `@Claude` mentions in Slack generate pull requests. Routes bug reports to code changes. | ANTHROPIC_BEST_PRACTICES.md (Integration section) |
| MCP Apps | Ecosystem | Interactive UI rendering in chat via sandboxed iframes. Launched Jan 26, 2026. Partners: Amplitude, Asana, Box, Canva, Clay, Figma, Hex, monday.com, Slack. Spec co-developed with OpenAI, Block, VS Code, JetBrains, AWS. | ANTHROPIC_BEST_PRACTICES.md (MCP section) |
| Plan Mode | Blog, Docs | `Shift+Tab` cycling: Normal → Auto-Accept → Plan → Delegate. `--permission-mode plan` flag. `Ctrl+G` to edit plan in external editor. Read-only exploration mode. | CLAUDE_CODE_STANDARDS.md (Workflow section) |
| Import System | Blog | `@path/to/import` syntax in CLAUDE.md. Relative paths. Recursive imports (max 5 hops). First-time external imports show approval dialog. | CLAUDE_CODE_STANDARDS.md (CLAUDE.md section) |
| Managed Policy | Blog, Docs | Organization-wide CLAUDE.md at system paths. macOS: `/Library/Application Support/ClaudeCode/CLAUDE.md`. Linux: `/etc/claude-code/CLAUDE.md`. Cannot be overridden. | CLAUDE_CODE_STANDARDS.md (CLAUDE.md section) |
| JetBrains Plugin | Docs | IntelliJ IDEA, PyCharm, WebStorm and other JetBrains IDE support. | ANTHROPIC_BEST_PRACTICES.md (Deployment section) |
| /init Command | Blog | Generate starter CLAUDE.md from project structure analysis. | CLAUDE_CODE_STANDARDS.md (CLAUDE.md section) |
| /teleport Command | Blog, Docs | Move sessions between surfaces (terminal → web → desktop). | CLAUDE_CODE_STANDARDS.md (Commands section) |
| /desktop Command | Blog, Docs | Hand off terminal sessions to Desktop app for visual diff review. | CLAUDE_CODE_STANDARDS.md (Commands section) |
| Agent SDK | Engineering Blog | Separate framework for building fully custom agents with Claude Code's tools and capabilities. | ANTHROPIC_BEST_PRACTICES.md (Advanced section) |
| MCP OAuth | Docs, Changelog | `--client-id` and `--client-secret` flags for MCP OAuth 2.0 authentication. Added in v2.1.30. | ANTHROPIC_BEST_PRACTICES.md (MCP section) |
| MCP Tool Search | Docs | Auto-activates when tools exceed 10% of context window. Configurable via `ENABLE_TOOL_SEARCH` env var. | ANTHROPIC_BEST_PRACTICES.md (MCP section) |
| Wildcard Tool Permissions | Docs, Ecosystem | `Bash(*-h*)`, `Edit(./src/**)`, `WebFetch(domain:example.com)` — granular permission patterns. | CLAUDE_CODE_STANDARDS.md (Security section) |
| Auth CLI Subcommands | Changelog | `claude auth login`, `claude auth status`, `claude auth logout`. Added in v2.1.41. | CLAUDE_CODE_STANDARDS.md (Commands section) |
| CI/CD Integrations | Docs, Engineering Blog | GitHub Actions and GitLab CI/CD support. `anthropics/claude-code-action@v1`. | ANTHROPIC_BEST_PRACTICES.md (Production section) |
| Interview Pattern | Blog | For larger features: have Claude interview you via AskUserQuestion. Minimal description → technical deep-dive → generate SPEC.md → fresh session to implement. | CLAUDE_CODE_STANDARDS.md (Workflow section) |

---

## Changed Patterns

| Pattern | File | Current | Updated | Source |
|---------|------|---------|---------|--------|
| Thinking model | CLAUDE_CODE_STANDARDS.md:604-631, ANTHROPIC_BEST_PRACTICES.md:39-83 | Fixed token budgets (4K/10K/32K/64K) mapped to "think"/"think hard"/"ultrathink" keywords | Adaptive thinking with effort levels (low/medium/high/max). Keywords are regular prompt instructions, NOT token-allocation controls. `budget_tokens` deprecated on 4.6 models | Blog, Docs, Models |
| Best practices location | ANTHROPIC_BEST_PRACTICES.md:8 | anthropic.com/engineering/claude-code-best-practices | code.claude.com/docs (308 permanent redirect) | Blog |
| Docs URL | README.md:229-230 | docs.anthropic.com/en/docs/... | code.claude.com/docs and platform.claude.com | Docs |
| Commands → Skills | CLAUDE_CODE_STANDARDS.md:312-315 | `.claude/commands/` as primary system for custom workflows | Skills system (`.claude/skills/`) is now primary. Commands merged into skills — if both exist, skill takes precedence | Docs |
| NPM installation | Not mentioned | npm-based install | Deprecated as of v2.1.15. Native install recommended: `curl -fsSL https://claude.ai/install.sh \| bash` | Changelog |
| Multi-agent orchestration | CLAUDE_CODE_STANDARDS.md:904-958 | Manual orchestration with separate terminal sessions | Native Agent Teams feature with shared task lists, messaging, and automated coordination | Docs, Ecosystem |
| MCP transport | ANTHROPIC_BEST_PRACTICES.md (MCP section) | SSE transport for MCP servers | HTTP transport recommended. SSE is deprecated | Docs |
| Attribution settings | Not mentioned | `includeCoAuthoredBy` boolean | Replaced by `attribution.commit` and `attribution.pr` templates | Docs |

---

## New Best Practices

| Practice | Source | Description | Suggested Location |
|----------|--------|-------------|-------------------|
| Verification-first approach | Blog | Providing tests, screenshots, and expected outputs is the "single highest-leverage thing" for Claude Code quality. Chrome extension enables visual verification. | ANTHROPIC_BEST_PRACTICES.md (Workflow section) |
| Four-phase workflow with Plan Mode | Blog | Explore (Plan Mode) → Plan (Ctrl+G to edit) → Implement (Normal Mode) → Commit. Skip planning for small tasks. `Shift+Tab` to toggle modes. | CLAUDE_CODE_STANDARDS.md (Workflow section) |
| Anti-patterns to avoid | Blog | "Kitchen sink session" (mixing tasks without /clear), "Correcting over and over" (>2 corrections → restart), "Over-specified CLAUDE.md", "Trust-then-verify gap", "Infinite exploration" | CLAUDE_CODE_STANDARDS.md (new section) |
| Start fresh on failed autonomy | Teams Blog | RL Engineering team recommendation: when autonomous attempts fail, start fresh rather than debugging — avoids compounding errors | ANTHROPIC_BEST_PRACTICES.md (Workflow section) |
| Agent team sizing | Engineering Blog | Recommended: 2-5 teammates with 5-6 tasks each. Test quality is critical for multi-agent work — verifier must be near-perfect. | CLAUDE_CODE_STANDARDS.md (Multi-Agent section) |
| Git worktree memory isolation | Blog | Each worktree gets independent auto memory directory. Recommended for parallel Claude Code sessions to prevent context cross-contamination. | CLAUDE_CODE_STANDARDS.md (Parallel Development section) |

---

## Stale URLs

| File | Line | URL | Status |
|------|------|-----|--------|
| ANTHROPIC_BEST_PRACTICES.md | 8 | `https://www.anthropic.com/engineering/claude-code-best-practices` | 308 redirect → code.claude.com/docs |
| README.md | 228 | `https://www.anthropic.com/engineering/claude-code-best-practices` | 308 redirect → code.claude.com/docs |
| README.md | 229 | `https://docs.anthropic.com` | Redirects to platform.claude.com |
| README.md | 230 | `https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview` | Redirects to platform.claude.com |

---

## Pricing & Limits Changes

| Item | Current Value | Updated Value | Source |
|------|-------------|---------------|--------|
| Latest Sonnet model | Claude Sonnet 4.5 ($3/$15 per MTok) | Claude Sonnet 4.6 ($3/$15 per MTok) — same pricing, new model | Models, Pricing |
| Opus pricing | Not documented (legacy Opus 4 was $15/$75) | Opus 4.6: $5/$25 per MTok (67% reduction from legacy Opus) | Models, Pricing |
| Haiku pricing | Not documented | Haiku 4.5: $1/$5 per MTok | Pricing |
| Context window | 200K standard only | 200K standard / 1M beta for Opus 4.6 and Sonnet 4.6 (requires `context-1m-2025-08-07` header) | Models |
| Max output tokens | Implied 32K-64K | Opus 4.6: 128K tokens. Sonnet 4.6: 64K tokens | Models |
| Fast mode pricing | Not documented | Opus 4.6 fast mode: $30/$150 per MTok | Pricing |
| Long context pricing | Not documented | >200K tokens: Opus 4.6 $10/$37.50, Sonnet 4.6 $6/$22.50 per MTok | Pricing |
| Team Premium seat | Not documented | $150/seat/month — includes Claude Code access | Pricing |
| Web search tool | Not documented | $10 per 1,000 searches (plus token costs) | Pricing |

---

## Per-File Change Checklist

### CLAUDE_CODE_STANDARDS.md

- [ ] Line 601: Replace "Claude Sonnet 4.5's hybrid reasoning model" with "Opus 4.6/Sonnet 4.6 adaptive reasoning"
- [ ] Lines 604-631: Rewrite entire thinking section — replace fixed token budgets with adaptive thinking and effort levels
- [ ] Line 611: Update "Hybrid Reasoning Model (Claude Sonnet 4.5)" header
- [ ] Lines 617-621: Remove token-to-keyword mapping, document effort levels instead
- [ ] Lines 911-919: Update multi-agent section — replace Opus 4/Sonnet 4 references with Opus 4.6/Sonnet 4.6 and document Agent Teams
- [ ] Line 1002: Replace "v0.2.111 (CLI) or v1.0.20 (latest)" with "v2.1.45"
- [ ] Line 1073: Replace "Same Claude Sonnet 4.5 model capabilities" with current models
- [ ] Lines 312-315: Add note that commands are being superseded by the skills system
- [ ] Add new section: Skills system (.claude/skills/, SKILL.md, YAML frontmatter)
- [ ] Add new section: Hooks system (lifecycle events, command/prompt/agent types)
- [ ] Add new section: Auto memory and compaction
- [ ] Add new section: Session management (--continue, --resume, --from-pr, /rename)
- [ ] Add new section: Plan mode (Shift+Tab, --permission-mode plan)
- [ ] Update CLAUDE.md Configuration section: add modular rules (.claude/rules/), import system (@path), managed policy, /init command
- [ ] Update multi-agent section: add Agent Teams feature and team sizing guidance
- [ ] Add new section: Common anti-patterns to avoid
- [ ] Update deployment matrix: add Desktop app, JetBrains plugin, Chrome extension, Slack integration
- [ ] Add wildcard tool permission syntax examples

### ANTHROPIC_BEST_PRACTICES.md

- [ ] Line 8: Update URL from anthropic.com/engineering/... to code.claude.com/docs
- [ ] Line 39: Update header from "Claude Sonnet 4.5 - 2025 Update" to "Opus 4.6/Sonnet 4.6 - February 2026"
- [ ] Lines 43-83: Rewrite entire extended thinking section for adaptive thinking and effort levels
- [ ] Line 85: Update "Claude Sonnet 4.5 Capabilities (September 2025)" to current models
- [ ] Lines 87-102: Replace Sonnet 4.5 benchmarks with Opus 4.6/Sonnet 4.6 benchmarks (SWE-bench 80.8%/79.6%, OSWorld 72.7%/72.5%, ARC-AGI-2 68.8%)
- [ ] Line 100: Add Opus 4.6 pricing ($5/$25 per MTok)
- [ ] Line 436: Update CLI version from "v0.2.111 or v1.0.20" to "v2.1.45"
- [ ] Line 514: Replace "Claude Sonnet 4.5 capabilities" with current models
- [ ] Lines 576-584: Update multi-agent section model references from Opus 4/Sonnet 4 to Opus 4.6/Sonnet 4.6
- [ ] Lines 634-639: Update performance metrics to current model benchmarks
- [ ] Line 644: Replace "Upgrade to Claude Sonnet 4.5" with "Upgrade to Opus 4.6/Sonnet 4.6"
- [ ] Line 665: Update CLI version recommendation
- [ ] Update deployment matrix (section 11): add Desktop app, JetBrains, Chrome extension, Slack
- [ ] Update MCP section (section 12): add MCP Apps, MCP OAuth, MCP Tool Search, HTTP transport (SSE deprecated)
- [ ] Add verification-first approach as a best practice
- [ ] Add "start fresh on failed autonomy" pattern
- [ ] Add skills system, hooks, plugins documentation

### README.md

- [ ] Line 9: Replace "Updated for Claude Sonnet 4.5 (September 2025)" with "Updated for Opus 4.6 and Sonnet 4.6 (February 2026)"
- [ ] Line 11: Replace "Powered by Claude Sonnet 4.5" with current models
- [ ] Line 90: Replace thinking level token budgets with adaptive thinking description
- [ ] Lines 157-166: Update extended thinking examples to reflect adaptive reasoning
- [ ] Lines 185-194: Update "What's New" section with 2026 updates (Agent Teams, Skills, Hooks, Adaptive Thinking, etc.)
- [ ] Line 188: Update Sonnet 4.5 benchmarks to current model benchmarks
- [ ] Line 228: Update blog URL (or note redirect)
- [ ] Line 229: Update docs URL from docs.anthropic.com to platform.claude.com
- [ ] Line 230: Update prompt engineering URL
- [ ] Line 231: Replace Sonnet 4.5 announcement link with Opus 4.6/Sonnet 4.6 links
- [ ] Add Skills, Hooks, Plugins to "What's Included" section
- [ ] Update project structure example to include `.claude/skills/` and `.claude/rules/`

---

## Source Fetch Log

| Source | URL | Status | Key Facts Extracted |
|--------|-----|--------|-------------------|
| Claude Code Best Practices Blog | anthropic.com/engineering/claude-code-best-practices | success (308 redirect to code.claude.com/docs) | 45+ |
| How Anthropic Teams Use Claude Code | anthropic.com/news/how-anthropic-teams-use-claude-code | partial (reconstructed from alternatives) | 30+ |
| Claude Code Documentation | docs.anthropic.com/en/docs/claude-code | success (redirects to code.claude.com/docs) | 80+ |
| Claude Code Changelog | docs.anthropic.com/en/docs/claude-code/changelog | success | 30+ |
| Claude Code Sandboxing | anthropic.com/engineering/claude-code-sandboxing | success | 12 |
| Prompt Engineering Overview | docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview | success (redirects to platform.claude.com) | 15+ |
| Model Announcements | WebSearch | success | 25+ |
| Engineering Blog Posts | WebSearch | success | 15+ |
| Pricing and Plans | WebSearch | success | 20+ |
| Feature and Ecosystem Updates | WebSearch | success | 20+ |

---

## Current Model Reference (February 2026)

For quick reference when applying updates:

| Model | ID | Pricing (Input/Output per MTok) | Context | Max Output | Status |
|-------|----|---------------------------------|---------|------------|--------|
| Claude Opus 4.6 | `claude-opus-4-6` | $5 / $25 | 200K (1M beta) | 128K | Current flagship |
| Claude Sonnet 4.6 | `claude-sonnet-4-6` | $3 / $15 | 200K (1M beta) | 64K | Current default |
| Claude Haiku 4.5 | `claude-haiku-4-5` | $1 / $5 | 200K | 64K | Current fast |
| Claude Sonnet 4.5 | `claude-sonnet-4-5` | $3 / $15 | 200K | 64K | Legacy |
| Claude Opus 4.5 | `claude-opus-4-5` | $5 / $25 | 200K | 64K | Legacy |
| Claude Opus 4 | `claude-opus-4-0` | $15 / $75 | 200K | 32K | Legacy |
| Claude Sonnet 4 | `claude-sonnet-4-0` | $3 / $15 | 200K | 32K | Legacy |

## Key Version Info

| Item | Value |
|------|-------|
| Claude Code CLI | v2.1.45 (Feb 17, 2026) |
| Opus 4.6 release | Feb 5, 2026 |
| Sonnet 4.6 release | Feb 17, 2026 |
| Haiku 4.5 release | Oct 15, 2025 |
| Docs URL | code.claude.com/docs |
| API Docs URL | platform.claude.com |
