# Claude Code Standards

A comprehensive reference guide for effective Claude Code usage in software development projects.

## 📋 Overview

This repository contains a complete set of standards, best practices, and reference materials for using Claude Code as an AI agent in software development. These standards are based on proven methodologies for treating AI as labor rather than just a coding assistant.

**🆕 Updated for Opus 4.6 and Sonnet 4.6 (February 2026)** - Now includes Agent Teams, Skills, Hooks, adaptive reasoning, and the latest Anthropic engineering best practices.

**Powered by Claude Opus 4.6 and Sonnet 4.6**: Current-generation models with SWE-bench Verified scores of 80.8% and 79.6%, adaptive reasoning, 128K output tokens, and 1M context window (beta).

## 🎯 Core Philosophy

- **Think Big, Not Small**: Use vision-level instructions instead of micromanaging individual functions
- **AI as Labor**: Treat Claude Code as a team of 1000+ developers working in perfect coordination  
- **Context is Everything**: Provide the right context at the right time for maximum effectiveness

## 📚 What's Included

### [📖 Complete Standards Guide](CLAUDE_CODE_STANDARDS.md)
The comprehensive reference covering:
- Big Prompt Engineering techniques
- AI Labor methodology 
- Claude.md configuration
- Commands and context management
- Version control standards
- Code quality and design principles
- Project structure guidelines
- Feedback and iteration processes
- Advanced techniques

### [🏢 Official Anthropic Best Practices](ANTHROPIC_BEST_PRACTICES.md) **UPDATED 2025!**
Direct insights from Anthropic's engineering teams:
- Official workflow patterns (Explore-Plan-Code-Commit)
- Extended thinking with specific token budgets (4K to 32K tokens)
- Multi-Claude workflows and git worktrees
- **NEW**: Sandboxing with 84% fewer permission prompts
- **NEW**: Web interface for zero-setup development
- **NEW**: VS Code extension (beta)
- Advanced CLAUDE.md management
- Production automation patterns

### 📂 Template Files
- [Claude.md templates](templates/claude-md/) for different project types
- [Command examples](templates/commands/) for common development tasks
- [Official workflow commands](templates/commands/) based on Anthropic patterns

### 🛠️ Quick Start Examples
- [Web Application Setup](examples/web-app-setup.md)
- [API Development Standards](examples/api-development.md)
- [Mobile App Configuration](examples/mobile-app-config.md)

## 🚀 Quick Start

1. **Clone this repository**:
   ```bash
   git clone https://github.com/andrewlaery/Claude-Code-Standards.git
   cd Claude-Code-Standards
   ```

2. **Copy the appropriate Claude.md template** to your project:
   ```bash
   cp templates/claude-md/web-app.md /your/project/CLAUDE.md
   ```

3. **Set up essential commands**:
   ```bash
   mkdir -p /your/project/.claude/commands
   cp templates/commands/* /your/project/.claude/commands/
   ```

4. **Customize for your project**:
   - Edit CLAUDE.md with your specific requirements
   - Modify commands to match your workflow
   - Adjust project structure guidelines

## 📖 Key Concepts

### The 1000X Approach
Instead of 5-10X improvements from small prompts, these standards help you achieve 1000X improvements through:
- Comprehensive big prompts
- Autonomous AI labor management
- Systematic quality processes
- Scalable development workflows

### Official Anthropic Patterns
- **Explore-Plan-Code-Commit**: Official workflow for complex features
- **Test-Driven Development**: Anthropic's favorite pattern for verifiable changes
- **Adaptive Reasoning**: Effort levels (low/medium/high/max) replace fixed token budgets on 4.6 models
- **Interleaved Thinking**: Reasoning between tool calls, auto-enabled in adaptive mode
- **Multi-Claude Workflows**: Parallel development with git worktrees
- **Sandboxed Execution**: Filesystem and network isolation for safety (October 2025)
- **Web Interface**: Zero-setup browser-based development (October 2025)

### Best-of-N Pattern
Leverage AI's speed to explore multiple solutions:
- Generate 3-5 different implementations
- Compare and evaluate approaches
- Combine the best elements
- Learn from variations

### Context Management
Balance specificity with creative freedom:
- Global context via Claude.md
- Targeted context via commands
- In-context learning through examples
- Progressive context building

## 🏗️ Project Structure Best Practices

```
your-project/
├── CLAUDE.md                    # Global AI context
├── .claude/
│   ├── commands/               # Legacy reusable commands (superseded by skills)
│   │   ├── code-review.md
│   │   └── tdd-workflow.md
│   ├── skills/                 # Skills system (February 2026)
│   │   └── my-skill/
│   │       └── SKILL.md
│   ├── rules/                  # Modular project rules
│   │   ├── code-style.md
│   │   └── api-conventions.md
│   ├── agents/                 # Sub-agent definitions
│   │   └── code-reviewer.md
│   └── settings.json           # Project settings
├── src/
│   ├── components/            # Clear, standard naming
│   ├── utils/
│   ├── types/
│   └── __tests__/
└── docs/
    ├── architecture.md
    └── development-guide.md
```

## 🎯 Usage Examples

### Big Prompt Example
```markdown
I want you to create a modern expense tracking application. Here's my vision:

APPLICATION OVERVIEW:
Build a complete expense tracking web app that helps users manage personal finances...

CORE FEATURES:
- Add expenses with date, amount, category, description
- Dashboard with spending summaries and analytics
- Filter expenses by date range and category
...
```

### Official Workflow Commands
```bash
# In Claude Code - Official Anthropic patterns:
/explore-plan-code-commit implement user authentication system
/tdd-workflow add expense categorization feature
/code-review src/components/ExpenseList.tsx
/integrate-parallel-work budget-tracking notifications
```

### Adaptive Reasoning (Opus 4.6 / Sonnet 4.6)
```bash
# Configure effort level for reasoning depth:
# CLAUDE_CODE_EFFORT_LEVEL=low    — quick lookups, simple tasks
# CLAUDE_CODE_EFFORT_LEVEL=medium — routine reviews, moderate debugging
# CLAUDE_CODE_EFFORT_LEVEL=high   — complex architecture, security analysis (default)
# CLAUDE_CODE_EFFORT_LEVEL=max    — critical migrations (Opus 4.6 only)

# Toggle thinking: Option+T (macOS) / Alt+T (Windows/Linux)
# Keywords like "think hard" are regular prompt instructions, not token controls
```

## 📋 Quality Standards

### Essential Requirements
- ✅ All code must compile without warnings
- ✅ Test coverage above 80%
- ✅ All tests must pass before committing
- ✅ Follow established design principles
- ✅ Use feature branches for all changes

### AI Labor Guidelines
- 🎯 Give vision-level instructions
- 🔄 Use Best-of-N for complex features
- 📊 Leverage subagents for parallel work
- 🔍 Think first, code second for architecture
- 📝 Document processes for repeatability
- 🏢 Follow official Anthropic workflow patterns

## 🆕 What's New (2026)

### Latest Updates (February 2026)
- **Opus 4.6 + Sonnet 4.6**: Current-generation models (SWE-bench 80.8%/79.6%, OSWorld 72.7%/72.5%)
- **Adaptive Reasoning**: Effort levels (low/medium/high/max) replace fixed token budgets
- **Agent Teams**: Native multi-agent orchestration with shared tasks and messaging (research preview)
- **Skills System**: `.claude/skills/` with YAML frontmatter, hot-reload, forked context
- **Hooks System**: Deterministic lifecycle event handlers (SessionStart, PreToolUse, Stop, etc.)
- **Plugins Marketplace**: Bundles of skills, hooks, subagents, and MCP servers
- **Auto Memory**: Persistent per-project memory, compaction for infinite conversations
- **Plan Mode**: Read-only exploration with `Shift+Tab` toggle
- **Desktop App**: Standalone app for macOS and Windows
- **Chrome Extension**: Browser automation and UI testing
- **MCP Apps**: Interactive UI rendering in chat (Jan 2026, with Figma, Slack, Canva, etc.)
- **Opus 4.6 pricing**: $5/$25 per MTok (67% cheaper than legacy Opus 4)

### 2025 Foundations
- **Sandboxing**: Filesystem and network isolation, 84% fewer permission prompts
- **Web Interface**: Zero-setup browser-based development with cloud execution
- **VS Code Extension**: Native IDE experience
- **Official Anthropic Best Practices**: Explore-Plan-Code-Commit, TDD patterns
- **Multi-Claude Strategies**: Git worktrees and parallel development
- **Production Integration**: Headless mode, CI/CD patterns, GitHub Actions

## 🤝 Contributing

This is a living document that improves through real-world usage. Contributions welcome:

1. Fork the repository
2. Create a feature branch
3. Add your improvements or examples
4. Submit a pull request

### Types of Contributions Needed
- Additional project type templates
- More command examples based on official patterns
- Real-world case studies
- Integration patterns
- Quality improvement techniques

## 📄 License

MIT License - feel free to use and adapt for your projects.

## 🔗 Related Resources

- [Claude Code Documentation](https://code.claude.com/docs)
- [Claude Code Sandboxing](https://www.anthropic.com/engineering/claude-code-sandboxing)
- [Claude Code on the Web](https://www.anthropic.com/news/claude-code-on-the-web)
- [Official Claude Code Best Practices](https://code.claude.com/docs)
- [Anthropic API Documentation](https://platform.claude.com)
- [Prompt Engineering Guide](https://platform.claude.com/docs/build-with-claude/prompt-engineering/overview)
- [Claude Opus 4.6 Announcement](https://www.anthropic.com/news/claude-opus-4-6)
- [Claude Sonnet 4.6 Announcement](https://www.anthropic.com/news/claude-sonnet-4-6)

## ⭐ Acknowledgments

Based on comprehensive Claude Code course materials, official Anthropic engineering best practices, and real-world development experience using AI labor for software engineering.

---

**Start building better software with AI today** - these standards will help you unlock Claude Code's full potential as a development team multiplier.