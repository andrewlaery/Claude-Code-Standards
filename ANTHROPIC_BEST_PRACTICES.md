# Official Anthropic Best Practices Integration

This document integrates the latest official best practices from Anthropic's engineering team with our existing Claude Code standards. These practices come directly from Anthropic's internal teams and the broader Claude Code community.

## 📚 Source Integration

This integration incorporates insights from:
- [Anthropic's Official Claude Code Best Practices](https://code.claude.com/docs)
- [How Anthropic Teams Use Claude Code](https://www.anthropic.com/news/how-anthropic-teams-use-claude-code)
- Internal Anthropic engineering workflows

## 🎯 Key Official Patterns

### 1. Advanced CLAUDE.md Management

#### Dynamic CLAUDE.md Updates
Use the `#` key during Claude Code sessions to automatically add instructions to CLAUDE.md:
```bash
# While in Claude Code, press # and type:
# Always run typecheck after making changes
# Use ES modules syntax, not CommonJS
# Prefer single test runs for performance
```

#### CLAUDE.md Optimization Techniques
- **Prompt Improvement**: Run CLAUDE.md files through Anthropic's prompt improver tool
- **Emphasis Tuning**: Add "IMPORTANT" or "YOU MUST" for critical instructions
- **Iterative Refinement**: Experiment with different phrasings to improve instruction following

#### Strategic CLAUDE.md Placement
```
project-root/
├── CLAUDE.md                    # Shared team standards (check into git)
├── CLAUDE.local.md              # Personal preferences (gitignored)
├── ~/.claude/CLAUDE.md          # Global personal settings
└── subdirectory/CLAUDE.md       # Directory-specific context
```

### 2. Adaptive Reasoning (Opus 4.6 / Sonnet 4.6 - February 2026)

#### Adaptive Thinking (4.6 Models)
```markdown
# Opus 4.6 and Sonnet 4.6 use adaptive thinking:
- Claude dynamically allocates reasoning depth per request
- Effort levels: low, medium, high (default), max (Opus 4.6 only)
- Configure via CLAUDE_CODE_EFFORT_LEVEL env var or /model command
- Toggle with Option+T (macOS) / Alt+T (Windows/Linux)
- Keywords like "think hard" or "ultrathink" are regular prompt instructions, NOT token controls
- Interleaved thinking (between tool calls) auto-enabled in adaptive mode

# Effort Level Guide:
- low: Quick answers, simple lookups, straightforward tasks
- medium: Standard code reviews, moderate debugging
- high (default): Complex architecture, security analysis, multi-step debugging
- max (Opus 4.6 only): Critical migrations, system-wide refactoring

# Legacy Models (Sonnet 4.5 and earlier):
- Fixed budget_tokens: thinking: {type: "enabled", budget_tokens: N}
- budget_tokens deprecated on 4.6 models — use effort levels instead
```

#### Adaptive Reasoning Model (Opus 4.6 / Sonnet 4.6)
```markdown
# Adaptive Reasoning:
1. **Low effort**: Quick responses, minimal reasoning
2. **High effort (default)**: Deep analysis with extended reasoning
3. **Max effort (Opus 4.6)**: Maximum reasoning depth for critical decisions

# Thinking Output:
- Claude 4+ models return summarized thinking (not full chain of thought)
- Billed for full thinking tokens, not just the summary
- Interleaved thinking: reasoning happens between tool calls automatically
- Thinking redaction: safety system encrypts flagged reasoning blocks
```

#### When to Use Each Effort Level
```markdown
# By Effort Level (Opus 4.6 / Sonnet 4.6):
- **low**: Standard code lookups, simple questions, quick formatting tasks
- **medium**: Routine code reviews, straightforward debugging, moderate planning
- **high** (default): Complex architecture, security analysis, multi-step debugging
- **max** (Opus 4.6 only): Critical migrations, novel design challenges, system-wide refactoring

# Cost Considerations:
- Higher effort = more thinking tokens = higher cost
- "max" generates the most tokens — reserve for critical decisions
- Default "high" provides optimal quality/cost balance for most tasks
- Thinking tokens billed at full rate even though API returns summaries
```

#### Current Model Capabilities (February 2026)
```markdown
# Model Lineup:
- Opus 4.6 (claude-opus-4-6): Flagship model, released Feb 5, 2026
- Sonnet 4.6 (claude-sonnet-4-6): Default model, released Feb 17, 2026
- Haiku 4.5 (claude-haiku-4-5): Fast model, released Oct 15, 2025
- All prior models (Sonnet 4.5, Opus 4.5, Opus 4.1, Sonnet 4, Opus 4) are now legacy

# Performance Benchmarks:
- Opus 4.6: SWE-bench Verified ~80.8%, OSWorld 72.7%, ARC-AGI-2 68.8%
- Sonnet 4.6: SWE-bench Verified 79.6%, OSWorld 72.5%
- Both models support adaptive thinking and interleaved reasoning

# Context and Output:
- Context window: 200K standard, 1M beta (Opus 4.6 and Sonnet 4.6)
- Max output: 128K tokens (Opus 4.6), 64K tokens (Sonnet 4.6/Haiku 4.5)

# Pricing:
- Opus 4.6: $5/$25 per million tokens (67% cheaper than legacy Opus 4)
- Sonnet 4.6: $3/$15 per million tokens (unchanged from Sonnet 4.5)
- Haiku 4.5: $1/$5 per million tokens
- Available via API, AWS Bedrock, Google Vertex AI, Microsoft Foundry
```

### 3. Official Workflow Patterns

#### Pattern 1: Explore, Plan, Code, Commit
```markdown
# Official Anthropic workflow:
1. **Explore**: "Read the logging files but don't write code yet"
2. **Plan**: "Think hard about the approach and create a plan"
3. **Code**: "Implement the solution following the plan"
4. **Commit**: "Commit with a descriptive message and create PR"

# Use subagents for complex exploration:
"Use subagents to investigate the authentication system before planning"
```

#### Pattern 2: Test-Driven Development (TDD)
```markdown
# Anthropic's favorite workflow:
1. "Write tests for expected input/output - we're doing TDD"
2. "Run tests and confirm they fail - don't write implementation"
3. "Commit the tests when satisfied"
4. "Write code to pass tests - don't modify tests"
5. "Use subagents to verify implementation isn't overfitting"
6. "Commit when all tests pass"
```

#### Pattern 3: Visual Iteration
```markdown
# For UI/UX development:
1. "Take a screenshot of current state"
2. "Compare to this design mock [attach image]"
3. "Implement changes to match the mock"
4. "Take another screenshot and iterate"
5. "Commit when visual match is achieved"
```

### 4. Advanced Tool Management

#### Permission Optimization
```bash
# Strategic allowlist management:
/permissions add Edit                    # Always allow file edits
/permissions add Bash(git commit:*)      # Allow git commits
/permissions add mcp__puppeteer__*       # Allow Puppeteer tools
```

#### Custom Slash Commands with Parameters
`.claude/commands/fix-github-issue.md`:
```markdown
Please analyze and fix the GitHub issue: $ARGUMENTS.

Follow these steps:
1. Use `gh issue view` to get issue details
2. Understand the problem described
3. Search codebase for relevant files
4. Implement necessary changes
5. Write and run tests to verify fix
6. Ensure code passes linting and type checking
7. Create descriptive commit message
8. Push and create PR

Remember to use GitHub CLI (`gh`) for all GitHub-related tasks.
```

Usage: `/project:fix-github-issue 1234`

### 5. Safe YOLO Mode (Official Pattern)

#### Container-Based Safe Automation
```bash
# Use with Docker dev containers for safety:
claude --dangerously-skip-permissions

# Reference implementation:
# https://github.com/anthropics/claude-code/tree/main/.devcontainer
```

#### Ideal Use Cases
- Fixing lint errors
- Generating boilerplate code
- Mass file migrations
- Automated refactoring

### 6. Multi-Claude Workflows (Official Advanced Pattern)

#### Pattern A: Parallel Verification
```bash
# Terminal 1: Implementation
claude # Write the feature

# Terminal 2: Review
claude # Review the code from Terminal 1

# Terminal 3: Integration
claude # Integrate based on feedback from Terminal 2
```

#### Pattern A+: Sub-Agent Enhanced Parallel Verification
```bash
# Terminal 1: Feature Implementation
claude
"Use the test-specialist sub-agent to create comprehensive tests first"
"Implement the feature following TDD workflow"

# Terminal 2: Specialized Review
claude  
"Use the security-auditor sub-agent to review the implementation"
"Have the code-reviewer sub-agent analyze code quality"

# Terminal 3: Integration & Documentation
claude
"Use the refactoring-expert sub-agent to optimize the integration"
"Have the documentation-writer sub-agent create feature documentation"
```

#### Pattern B: Git Worktrees (Official Recommendation)
```bash
# Create worktrees for parallel development:
git worktree add ../project-feature-a feature-a
git worktree add ../project-feature-b feature-b

# Launch Claude in each:
cd ../project-feature-a && claude  # Terminal 1
cd ../project-feature-b && claude  # Terminal 2

# Clean up when done:
git worktree remove ../project-feature-a
```

#### Pattern B+: Sub-Agent Specialized Worktrees
```bash
# Create worktrees with specialized focuses:
git worktree add ../frontend-feature feature/frontend
git worktree add ../backend-feature feature/backend  
git worktree add ../testing-feature feature/testing

# Terminal 1: Frontend with UI specialist
cd ../frontend-feature && claude
"Use specialized UI sub-agents for all frontend development"

# Terminal 2: Backend with API specialist  
cd ../backend-feature && claude
"Use the security-auditor and code-reviewer sub-agents for backend development"

# Terminal 3: Testing with test specialist
cd ../testing-feature && claude
"Use the test-specialist sub-agent to create comprehensive test coverage"
```

#### Pattern C: Headless Automation
```bash
# Fan-out pattern for large migrations:
claude -p "migrate foo.py from React to Vue. Return OK if succeeded, FAIL if failed." \
  --allowedTools Edit Bash(git\ commit:*)

# Pipeline integration:
claude -p "analyze this log for anomalies" --output-format stream-json | next_command
```

### 7. Advanced Data Integration

#### Multiple Input Methods
```bash
# Pipe data directly:
cat error.log | claude "What's causing these errors?"

# Large dataset processing:
tail -f app.log | claude -p "Slack me if anomalies appear"

# URL fetching:
claude "Read https://api.company.com/docs and implement client"
```

#### GitHub CLI Integration
Claude Code has deep `gh` CLI integration:
```bash
# Claude automatically uses gh for:
- Creating issues and PRs
- Reading comments and reviews  
- Fixing failing builds
- Categorizing open issues
- One-shot review comment fixes
```

### 8. Jupyter Notebook Workflows

#### Data Science Integration
```markdown
# Recommended workflow:
1. Open Claude Code and .ipynb side-by-side in VS Code
2. Ask Claude to interpret outputs and images
3. Have Claude clean up notebooks before sharing
4. Use "make this aesthetically pleasing" for visualizations
```

### 9. Context Management (Official Strategies)

#### Active Collaboration Techniques
```bash
# Course correction tools:
1. Ask for plans before coding: "Plan first, don't code yet"
2. Press Escape to interrupt and redirect
3. Double-tap Escape to edit previous prompts
4. Ask Claude to undo changes when needed
```

#### Context Window Management
```bash
# Use /clear frequently between tasks
/clear

# For complex workflows, use external scratchpads:
"Create a checklist in migration-progress.md and work through it item by item"
```

### 10. Production Integration Patterns

#### Issue Triage Automation
```yaml
# GitHub Actions example:
- uses: anthropics/claude-code-action@v1
  with:
    prompt: "Analyze this issue and assign appropriate labels"
    files: ${{ github.event.issue.body }}
```

#### Code Review Automation
```yaml
# Subjective code review beyond traditional linting:
- uses: anthropics/claude-code-action@v1
  with:
    prompt: "Review for typos, stale comments, misleading names"
    files: ${{ github.event.pull_request.changed_files }}
```

## 🔄 Integration with Existing Standards

### Enhanced Claude.md Template
Update your existing Claude.md with these official patterns:

```markdown
# Project: [YOUR_PROJECT_NAME]

## Core Principles
**IMPORTANT**: Follow SOLID design principles. YOU MUST adhere to these patterns.

## Extended Thinking Usage
- Use "think hard" for complex architectural decisions
- Use "ultrathink" for security-critical implementations
- Always plan before coding on complex features

## Official Workflows
1. For TDD: Write tests first, commit tests, then implement
2. For UI: Take screenshots, compare to mocks, iterate visually
3. For complex features: Explore → Plan → Code → Commit

## Tool Permissions
# Add to your allowlist:
- Edit (always allow file editing)
- Bash(git commit:*) (allow git operations)
- Web browsing for documentation

## Sub-Agent Usage (Enhanced)
- Use sub-agents for specialized domain expertise (security, testing, documentation)
- Leverage sub-agents for complex codebase exploration and analysis
- Coordinate sub-agents for comprehensive quality assurance workflows
- Delegate specific tasks to appropriate specialist sub-agents

## Available Sub-Agents
- **code-reviewer**: Comprehensive code quality analysis
- **test-specialist**: Testing strategy, TDD implementation, debugging
- **security-auditor**: Security vulnerability assessment and compliance
- **refactoring-expert**: Code structure improvement and design patterns
- **documentation-writer**: Technical documentation and API docs

## Sub-Agent Coordination Patterns
- **Quality Pipeline**: test-specialist → code-reviewer → security-auditor → documentation-writer
- **Parallel Analysis**: Multiple sub-agents analyzing different aspects simultaneously
- **Specialized Workflows**: Delegate entire workflows to domain-specific sub-agents
```

### Enhanced Commands
Add these official patterns to your `.claude/commands/`:

1. **explore-plan-code.md** - Official Anthropic workflow
2. **tdd-workflow.md** - Test-driven development pattern (enhanced with sub-agent integration)
3. **visual-iteration.md** - UI development with screenshots
4. **multi-claude-review.md** - Parallel verification workflow
5. **code-review.md** - Enhanced with sub-agent delegation options
6. **feature-implementation.md** - Comprehensive feature development with sub-agent coordination

### Enhanced Sub-Agent Templates
Add these specialized sub-agent configurations to your `.claude/agents/`:

1. **code-reviewer.md** - Comprehensive code quality analysis specialist
2. **test-specialist.md** - Testing, TDD, and debugging expert
3. **security-auditor.md** - Security vulnerability assessment specialist
4. **refactoring-expert.md** - Code structure and design pattern improvement
5. **documentation-writer.md** - Technical documentation and API documentation specialist

### 10. Sandboxing and Security (October 2025)

#### Filesystem and Network Isolation
```markdown
# Anthropic's Latest Security Features:
- **Filesystem Isolation**: Claude restricted to specific directories
- **Network Isolation**: Claude connects only to approved domains
- **84% Reduction**: Fewer permission prompts in Anthropic internal usage
- **OS-Level Security**: Built on Linux bubblewrap, macOS seatbelt
- **Open Source**: Implementation open-sourced by Anthropic

# Benefits:
- Dramatically safer YOLO mode with --dangerously-skip-permissions
- Prevents prompt injection data exfiltration attacks
- Blocks unauthorized system modifications
- Same security across CLI, web, and mobile
```

#### Updated YOLO Mode Best Practices
```markdown
# Primary Safety Mechanism (2025):
- Sandboxing is now the primary safety mechanism, not containers
- --dangerously-skip-permissions much safer with sandbox isolation
- Filesystem boundaries prevent system damage
- Network boundaries prevent data leaks

# Container Workflows (Additional Layer):
- Dev containers still recommended for extra isolation
- Docker wrappers for production environments
- VM isolation for maximum security needs

# Security Updates:
- CVE-2025-54794 and CVE-2025-54795 patched
- Update to v2.1.45 minimum
- Sandboxing mitigates exploit impact automatically
```

#### Sandbox Configuration
```bash
# Restrict to project directory:
claude --sandbox-root /path/to/project

# Network domain approval:
# Domains approved through proxy on first use
# Persistent allow-list for trusted domains
# Prevents prompt injection exfiltration

# .claude/settings.local.json example:
{
  "allowedTools": ["Edit", "Bash(git:*)", "Bash(npm:*)"],
  "sandbox": {
    "filesystem": {
      "allowedPaths": ["/path/to/project"]
    },
    "network": {
      "allowedDomains": ["github.com", "npmjs.com"]
    }
  }
}
```

### 11. Web Interface and Deployment Options (October 2025)

#### Claude Code on the Web (Beta)
```markdown
# Zero-Setup Development:
- Browser-based interface for Pro ($20/mo) and Max ($100-200/mo) users
- Cloud execution in Anthropic-managed sandboxed environments
- GitHub repository integration
- Parallel session support for multiple simultaneous tasks
- Real-time progress monitoring
- Mobile access via iOS app

# Use Cases:
- Development from any device without local installation
- Team collaboration through shared URL sessions
- Quick prototyping without environment setup
- Remote development on cloud infrastructure
- Mobile code reviews and emergency fixes

# Security:
- Same sandboxing as CLI (filesystem + network isolation)
- Git through secure proxy service
- Isolated execution per task
```

#### VS Code Extension (Beta)
```markdown
# Native IDE Integration:
- Graphical interface in familiar VS Code environment
- No terminal knowledge required
- Available from VS Code marketplace
- Full Claude Code capabilities
- Seamless git integration

# Benefits for Teams:
- Lower barrier to entry for non-terminal users
- Native debugging integration
- Side-by-side code editing and AI assistance
- Familiar UI/UX for broader adoption
```

#### Deployment Matrix
```markdown
# Choose Your Interface:
1. **CLI (Terminal)**: Maximum control, Unix philosophy, automation
2. **VS Code Extension**: IDE integration, visual workflows
3. **JetBrains Plugin**: IntelliJ, PyCharm, WebStorm integration
4. **Desktop App**: Standalone app for macOS and Windows
5. **Web Interface**: Zero setup, mobile access, cloud execution (claude.ai/code)
6. **Chrome Extension**: Browser automation and UI testing
7. **Slack Integration**: @Claude mentions generate PRs
8. **MCP Server Mode**: Remote invocation from other tools

# All Provide:
- Opus 4.6 and Sonnet 4.6 capabilities
- Sandboxed execution
- Adaptive reasoning with effort levels
- Sub-agent coordination and Agent Teams
```

### 12. Model Context Protocol (MCP) - Industry Adoption (2025)

#### From Anthropic Innovation to Industry Standard
```markdown
# Major Platform Adoption:
- **OpenAI** (March 2025): MCP across ChatGPT platform
- **Google** (April 2025): Gemini MCP integration
- **Development Tools**: Block, Apollo, Zed, Replit, Codeium, Sourcegraph
- **Community Growth**: Thousands of MCP servers since Nov 2024
- **SDKs**: Available for all major programming languages

# Impact:
- De facto standard for agent-tool connections
- Unified protocol across AI platforms
- Massive ecosystem of community servers
```

#### Code Execution with MCP
```markdown
# Efficiency Breakthrough:
- Agents execute code to interact with tools (vs loading definitions)
- Dramatically reduced token usage
- Handle hundreds of connected tools efficiently
- Intermediate results don't bloat context window

# Performance Benefits:
- Lower latency for multi-tool workflows
- Reduced API costs through token efficiency
- Scale to enterprise tool ecosystems
- More efficient agent operations
```

#### Claude Code as MCP Server
```markdown
# Dual Server/Client Mode:
claude mcp serve

# Capabilities:
- Exposes file editing and command execution via MCP
- Other clients (Claude Desktop, Cursor, Windsurf) invoke remotely
- Claude Code as a service for other AI tools
- Remote automation and headless execution

# Popular Integrations:
- Development: GitHub, GitLab, Linear, Jira
- Data: PostgreSQL, MongoDB, Redis, Elasticsearch
- Services: Stripe, Figma, Sentry, Datadog
- Communication: Slack, Discord, Google Drive
- Documentation: Context7 MCP server integration

# MCP Apps (January 2026):
- Interactive UI rendering in chat via sandboxed iframes
- Launch partners: Amplitude, Asana, Box, Canva, Clay, Figma, Hex, monday.com, Slack
- Spec co-developed with OpenAI, Block, VS Code, JetBrains, AWS
- MCP OAuth support: --client-id and --client-secret flags
- MCP Tool Search: auto-activates when tools exceed 10% of context window
- HTTP transport recommended (SSE transport deprecated)
```

### 13. Multi-Agent Architecture (Official Anthropic Research)

#### Performance Breakthrough
```markdown
# Anthropic Internal Research Results:
- Multi-agent (Opus 4.6 orchestrator + Sonnet 4.6 workers) vs single-agent approaches
- **90.2% improvement** on internal research evaluation
- Key insight: Separation of concerns → thorough independent investigations
- Each agent has separate context window (no context pollution)
- **Agent Teams** (native): Enable via CLAUDE_CODE_EXPERIMENTAL_AGENT_TEAMS=1
- Lead delegates to teammates; shared task lists and messaging; research preview

# Architecture Pattern:
- **Agent Teams**: Native multi-agent with automated coordination (recommended)
- **Orchestrator Agent**: Opus 4.6 for strategic coordination
- **Worker Agents**: Sonnet 4.6 for specialized execution
- **Recommended sizing**: 2-5 teammates with 5-6 tasks each
- **Wave-Based Deployment**: Strategic batches to manage context limits
- **Hierarchical Tiers**: Strategic → Domain → Task specialists
```

#### Implementation Patterns
```markdown
# Scale by Complexity:
- **Simple (2-3 agents)**: Single domain feature development
- **Moderate (10-15 agents, 2-3 waves)**: Multi-domain features
- **Complex (20-30 agents, 4-5 waves)**: System-wide implementations

# Example - E-commerce Checkout:
Wave 1: Architecture, Security, Database specialists
Wave 2: Frontend, Backend, API specialists
Wave 3: Testing, Performance, Documentation specialists
Wave 4: Integration, QA, Deployment specialists

# Benefits:
- Parallel processing of independent concerns
- Specialized expertise per domain
- Reduced path dependency
- Thorough analysis from multiple perspectives
```

#### Orchestration Best Practices
```markdown
# Strategic Coordination:
1. **Orchestrator**: Big picture, objectives, resource allocation
2. **Coordinators**: Domain management (research, implementation)
3. **Workers**: Focused task execution with expertise

# Context Management:
- Monitor context usage across agent network
- Wave-based deployment prevents context overflow
- Clean context per agent avoids pollution
- Coordination overhead justified by quality gains
```

## 📊 Official Performance Metrics (Updated 2025)

### From Anthropic's Internal Usage
**Development Velocity:**
- **Onboarding Time**: Significant reduction in ramp-up time
- **Engineer Load**: 90%+ of git interactions handled by Claude
- **Research Time**: 80% reduction (from 1 hour to 10-20 minutes)
- **Incident Response**: 20+ minutes saved during critical outages

**Multi-Agent Performance:**
- **90.2% improvement** with multi-agent vs single-agent architecture
- **84% reduction** in permission prompts with sandboxing
- **Opus 4.6 and Sonnet 4.6** as current-generation models (Feb 2026)

**Code Quality (Current Models):**
- **SWE-bench Verified**: Opus 4.6 ~80.8%, Sonnet 4.6 79.6%
- **OSWorld**: Opus 4.6 72.7%, Sonnet 4.6 72.5%
- **ARC-AGI-2**: Opus 4.6 68.8% (nearly doubled from Opus 4.5's 37.6%)

## 🎯 Next Steps (Updated for 2025)

### Essential Updates
1. **Upgrade to Opus 4.6 or Sonnet 4.6** — all prior models are now legacy
2. **Enable sandboxing** for 84% fewer permission prompts and better security
3. **Update Claude.md** with:
   - Extended thinking token budgets (4K, 10K, 32K)
   - Hybrid reasoning patterns
   - Multi-agent coordination strategies
   - Sandboxing configuration

### Workflow Implementation
4. **Implement official workflows** with sub-agent integration:
   - explore-plan-code-commit.md
   - tdd-workflow.md with automated verification
   - Multi-agent orchestration patterns

5. **Set up sub-agent templates** for specialized expertise:
   - code-reviewer, test-specialist, security-auditor
   - refactoring-expert, documentation-writer
   - Custom domain-specific agents

### Security & Deployment
6. **Configure sandbox security**:
   - Update to v2.1.45+ (latest) for security fixes and latest features
   - Set --sandbox-root for project isolation
   - Configure network domain allowlist

7. **Try new deployment options**:
   - VS Code extension (beta) for IDE integration
   - Web interface for zero-setup development
   - MCP server mode for remote automation

### Advanced Features
8. **Leverage MCP ecosystem**:
   - Install high-value MCP servers (GitHub, databases)
   - Try code execution with MCP for efficiency
   - Experiment with claude mcp serve mode

9. **Implement multi-agent architecture**:
   - Start with 2-3 agents for simple features
   - Scale to wave-based deployment for complex projects
   - Monitor 90.2% improvement potential

### CI/CD Integration
10. **Integrate into pipelines**:
    - Headless mode with sub-agent automation
    - Sandboxed YOLO mode for safe automation
    - MCP server mode for remote invocation

## 🤖 Sub-Agent Integration Benefits

From Anthropic's official recommendations:
- **Specialized Expertise**: Each sub-agent focuses on specific domain knowledge
- **Context Preservation**: Main conversation stays focused while sub-agents handle detailed analysis
- **Quality Assurance**: Multiple specialized reviews ensure comprehensive coverage
- **Scalability**: Coordinate multiple sub-agents for complex, multi-faceted development tasks
- **Consistency**: Reusable sub-agent configurations ensure consistent quality across projects

---

*This integration document ensures your Claude Code standards align with Anthropic's official best practices and internal team workflows.*