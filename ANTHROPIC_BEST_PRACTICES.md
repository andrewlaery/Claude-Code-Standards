# Official Anthropic Best Practices Integration

This document integrates the latest official best practices from Anthropic's engineering team with our existing Claude Code standards. These practices come directly from Anthropic's internal teams and the broader Claude Code community.

## 📚 Source Integration

This integration incorporates insights from:
- [Anthropic's Official Claude Code Best Practices](https://www.anthropic.com/engineering/claude-code-best-practices)
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

### 2. Extended Thinking Integration (Claude Sonnet 4.5 - 2025 Update)

#### Thinking Levels (Official Mapping with Token Budgets)
```markdown
# Mapped directly to specific thinking budgets:
"think" = 4,000 tokens
"think hard" / "megathink" = 10,000 tokens
"ultrathink" = 31,999 tokens
Extended thinking = up to 64,000 tokens
Interleaved thinking (beta) = full 200K context window

# Examples:
- "think about the best approach for this OAuth implementation" (4K tokens)
- "think hard about potential security vulnerabilities" (10K tokens)
- "ultrathink about the architectural implications" (32K tokens)
- "use extended thinking with 64K budget for this critical migration decision"
```

#### Hybrid Reasoning Model (Claude Sonnet 4.5)
```markdown
# Two Modes:
1. **Instant Responses**: Straightforward tasks, no visible thinking
2. **Extended Thinking**: Complex problems with visible reasoning blocks

# Visible Thinking:
- Shows actual internal reasoning process, not summaries
- API returns summary of full thinking process
- Prevents misuse while providing intelligence benefits
- Thinking blocks appear when extended thinking mode enabled
```

#### When to Use Extended Thinking
```markdown
# By Token Budget:
- **4K (think)**: Standard architectural planning, code reviews, simple refactoring
- **10K (think hard)**: Security analysis, performance optimization, complex debugging
- **32K (ultrathink)**: Critical migrations, systemic problem resolution, new pattern design
- **64K budget**: Major architectural overhauls, framework migrations, system-wide refactoring

# Cost Considerations:
- Ultrathink generates disproportionate costs
- Reserve for major architectural challenges only
- Most tasks work well with "think" (4K) or "think hard" (10K)
- Balance quality needs with token efficiency
```

#### Claude Sonnet 4.5 Capabilities (September 2025)
```markdown
# Performance Benchmarks:
- 30+ hours of autonomous work (vs 7 hours for Opus 4)
- 0% error rate on code editing benchmark (vs 9% on Sonnet 4)
- State-of-the-art on SWE-bench Verified evaluation
- 61.4% on OSWorld benchmark (computer use tasks)

# Key Features:
- Hybrid reasoning: instant or extended thinking on demand
- Exceptional edit capabilities with near-perfect accuracy
- Extended autonomous work for complex, multi-step tasks
- Improved alignment: reduced sycophancy, deception, power-seeking

# Pricing:
- Same as Claude Sonnet 4: $3/$15 per million tokens
- Available everywhere including API, AWS, GCP
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
- Update to v0.2.111 or v1.0.20 minimum
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
3. **Web Interface**: Zero setup, mobile access, cloud execution
4. **MCP Server Mode**: Remote invocation from other tools

# All Provide:
- Claude Sonnet 4.5 capabilities
- Sandboxed execution
- Extended thinking and hybrid reasoning
- Sub-agent coordination
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
```

### 13. Multi-Agent Architecture (Official Anthropic Research)

#### Performance Breakthrough
```markdown
# Anthropic Internal Research Results:
- Multi-agent (Opus 4 orchestrator + Sonnet 4 workers) vs single Opus 4
- **90.2% improvement** on internal research evaluation
- Key insight: Separation of concerns → thorough independent investigations
- Each agent has separate context window (no context pollution)

# Architecture Pattern:
- **Orchestrator Agent**: Opus 4 for strategic coordination
- **Worker Agents**: Sonnet 4 for specialized execution
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
- **30+ hours** of autonomous work with Claude Sonnet 4.5

**Code Quality:**
- **0% error rate** on code editing benchmark (Sonnet 4.5)
- **State-of-the-art** on SWE-bench Verified evaluation
- **61.4% score** on OSWorld computer use benchmark

## 🎯 Next Steps (Updated for 2025)

### Essential Updates
1. **Upgrade to Claude Sonnet 4.5** if not already using latest model
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
   - Update to v0.2.111+ or v1.0.20+ for CVE patches
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