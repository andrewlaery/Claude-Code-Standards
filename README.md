# Claude Code Standards

A comprehensive reference guide for effective Claude Code usage in software development projects.

## 📋 Overview

This repository contains a complete set of standards, best practices, and reference materials for using Claude Code as an AI agent in software development. These standards are based on proven methodologies for treating AI as labor rather than just a coding assistant.

**🆕 Updated for Claude Sonnet 4.5 (September 2025)** - Now includes sandboxing, web interface, and the latest Anthropic engineering best practices.

**Powered by Claude Sonnet 4.5**: State-of-the-art coding model with 30+ hours of autonomous work, 0% code editing errors, and hybrid reasoning capabilities.

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
- **Extended Thinking**: "think" (4K) < "think hard" (10K) < "ultrathink" (32K tokens)
- **Hybrid Reasoning**: Instant responses or deep thinking with visible reasoning
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
│   └── commands/               # Reusable AI commands
│       ├── code-review.md
│       ├── explore-plan-code-commit.md  # NEW: Official pattern
│       ├── tdd-workflow.md              # NEW: Official TDD pattern
│       ├── feature-implementation.md
│       └── integration.md
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

### Extended Thinking Integration
```bash
# Use official thinking levels with specific token budgets:
"think about the best approach for OAuth implementation"      # 4,000 tokens
"think hard about potential security vulnerabilities"         # 10,000 tokens
"ultrathink about the architectural implications"             # 31,999 tokens

# For maximum reasoning on critical decisions:
"use extended thinking with 64,000 token budget for this architectural decision"
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

## 🆕 What's New (2025)

### Latest Updates (November 2025)
- **Claude Sonnet 4.5**: 30+ hours autonomous work, 0% code editing errors, state-of-the-art on SWE-bench
- **Sandboxing**: Filesystem and network isolation, 84% fewer permission prompts (October 2025)
- **Web Interface**: Zero-setup browser-based development with cloud execution (October 2025)
- **VS Code Extension**: Native IDE experience (beta)
- **MCP Code Execution**: Efficient token usage, industry-wide adoption
- **Extended Thinking Budgets**: 4K to 64K token ranges, hybrid reasoning model
- **Multi-Agent Architecture**: Official Anthropic patterns with 90.2% improvement

### 2024-2025 Foundations
- **Official Anthropic Best Practices**: Direct insights from Anthropic engineering teams
- **Extended Thinking Patterns**: Official thinking level mappings with token budgets
- **Workflow Commands**: Explore-Plan-Code-Commit and TDD patterns
- **Multi-Claude Strategies**: Git worktrees and parallel development
- **Production Integration**: Headless mode and CI/CD patterns

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
- [Official Anthropic Best Practices](https://www.anthropic.com/engineering/claude-code-best-practices)
- [Anthropic API Documentation](https://docs.anthropic.com)
- [Prompt Engineering Guide](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview)
- [Claude Sonnet 4.5 Announcement](https://www.anthropic.com/news/claude-sonnet-4-5)

## ⭐ Acknowledgments

Based on comprehensive Claude Code course materials, official Anthropic engineering best practices, and real-world development experience using AI labor for software engineering.

---

**Start building better software with AI today** - these standards will help you unlock Claude Code's full potential as a development team multiplier.