# Claude Code Standards - Complete Reference Guide

## Table of Contents
1. [Core Principles](#core-principles)
2. [Big Prompt Engineering](#big-prompt-engineering)
3. [AI Labor Methodology](#ai-labor-methodology)
4. [Claude.md Configuration](#claudemd-configuration)
5. [Commands and Context](#commands-and-context)
6. [Version Control Standards](#version-control-standards)
7. [Code Quality and Design](#code-quality-and-design)
8. [Project Structure Guidelines](#project-structure-guidelines)
9. [Feedback and Iteration](#feedback-and-iteration)
10. [Advanced Techniques](#advanced-techniques)

## Core Principles

### 1. Think Big, Not Small
- **DO**: Give Claude Code vision-level instructions that describe outcomes
- **DON'T**: Micromanage individual functions or files
- **Example Good**: "Build a complete expense tracking application with analytics"
- **Example Bad**: "Create component/expense_list.tsx and add functions to display data"

### 2. AI as Labor, Not Tool
- Treat Claude Code as a team of 1000+ developers working in perfect coordination
- Scale your use of AI labor by avoiding micromanagement bottlenecks
- Focus on critical thinking, architecture, and design while Claude handles implementation

### 3. Context is Everything
- Context narrows the target from broad instructions to precise outcomes
- Always provide sufficient context for the specific task at hand
- Balance specificity with creative freedom

### 4. Rigorous Quality Enforcement

The implementation must strictly adhere to these **non-negotiable principles**:

#### DRY (Don't Repeat Yourself)
- **Zero code duplication will be tolerated**
- Each functionality must exist in exactly one place
- No duplicate files or alternative implementations allowed
- Consolidate similar patterns into reusable components

#### KISS (Keep It Simple, Stupid)
- **Implement the simplest solution that works**
- No over-engineering or unnecessary complexity
- Straightforward, maintainable code patterns
- Resist feature creep and scope expansion

#### Clean File System
- **All existing files must be either used or removed**
- No orphaned, redundant, or unused files
- Clear, logical organization of the file structure
- Regular cleanup of deprecated or unused components

#### Transparent Error Handling
- **No error hiding or fallback mechanisms that mask issues**
- All errors must be properly displayed to the user
- Errors must be clear, actionable, and honest
- No silent failures or suppressed exceptions

### 5. Measurable Success Criteria

Implementation will be successful **only if**:
- **Zero Duplication**: No duplicate code or files exist in the codebase
- **Single Implementation**: Each feature has exactly one implementation
- **Complete Functionality**: All features work correctly and completely
- **Transparent Operations**: All errors are properly displayed to users
- **Clean Architecture**: Modular, reusable component structure
- **Consistent Standards**: Implementation follows all established guidelines
- **Full Documentation**: Implementation details are properly documented

## Big Prompt Engineering

### The 1000X Approach
Instead of 5-10X improvements from small prompts, aim for 1000X improvements with comprehensive prompts.

#### Structure of Effective Big Prompts
```markdown
APPLICATION OVERVIEW:
[High-level vision and purpose]

CORE FEATURES:
[Complete feature list with detail]

TECHNICAL REQUIREMENTS:
[Specific technologies, frameworks, patterns]

DESIGN REQUIREMENTS:
[UI/UX specifications, styling approach]

SPECIFIC FUNCTIONALITY:
[Detailed behavioral requirements]
```

#### Example Big Prompt Template
```markdown
I want you to create a modern, professional [APPLICATION TYPE]. Here's my vision:

APPLICATION OVERVIEW:
Build a complete [description] that helps users [primary purpose]. The app should feel modern, intuitive, and professional.

CORE FEATURES:
- [Feature 1 with details]
- [Feature 2 with details]
- [Feature 3 with details]

TECHNICAL REQUIREMENTS:
- [Framework] with [specific version]
- [Language] for type safety
- [Styling approach] for design
- [State management approach]
- [Testing framework and requirements]

DESIGN REQUIREMENTS:
- [Design aesthetic and principles]
- [Responsive requirements]
- [Accessibility standards]

SPECIFIC FUNCTIONALITY:
- [Detailed behavioral requirements]
- [Integration requirements]
- [Performance requirements]

Please create this as a complete, production-ready application. When you're done, provide instructions on how to run and test all features.
```

### Best-of-N Pattern
Leverage AI's speed and cost advantages to explore multiple solutions:

```markdown
Can you go back to the prior branch and repeat this process, but solve the underlying problem in a different and wildly valuable way? Surprise me with your creativity.
```

## AI Labor Methodology

### Scale Through Autonomy
- **Principle**: Give Claude Code big tasks that allow autonomous work
- **Avoid**: Constant approval loops and micromanagement
- **Goal**: Step back and let AI labor scale while you focus on higher-order thinking

### Challenge AI with Bold Requirements
```markdown
# Good Prompting Examples:
- "Act like the typical user of this application, then create different ways of sorting, filtering, and displaying expenses that are incredibly powerful and useful."
- "Look at this list of expenses. How could we make it incredibly bold, beautiful, and modern? Blow my mind with the elegance, simplicity, and beauty of your user interface."
- "When I'm trying to prepare my small business taxes, I find it really hard to gather all relevant expenses. Create something amazing to solve that problem for me."
```

## Claude.md Configuration

The `CLAUDE.md` file provides persistent global context for every interaction. Use the **CONTEXT Framework**:

- **C**lear and Concise Instructions
- **O**perational Processes  
- **N**aming and Standards
- **T**esting and Quality Gates
- **E**xamples and References
- **X**pectations and Boundaries
- **T**ools and Dependencies

### Essential Claude.md Structure

```markdown
# Project: [Project Name]

## Core Principles
**IMPORTANT**: [Critical principles that must ALWAYS be followed]

## Development Workflow
1. Before making any changes, create and checkout a feature branch named `feature-[brief-description]`
2. Write comprehensive tests for all new functionality
3. Compile code and run all tests before committing
4. Write detailed commit messages explaining changes and rationale
5. Commit all changes to the feature branch

## Architecture Overview
- **Frontend**: [Framework and version]
- **Backend**: [Technology stack]
- **Database**: [Database choice]
- **Testing**: [Testing frameworks]

## Code Standards
- [Language-specific standards]
- [Framework conventions]
- [File organization patterns]
- [Naming conventions]

## Quality Gates
- All code must compile without warnings
- Test coverage must remain above [X]%
- All tests must pass before committing
- [Linting tool] must pass without errors

## File Organization
- [Clear directory structure guidelines]
```

### Example: Web Application Claude.md (Enhanced Modular Approach)

```markdown
# Project: TaskFlow Web Application

## Core Configuration
@PRINCIPLES.md          # SOLID principles and core development philosophy
@WORKFLOW.md           # Development workflow and branching strategy
@ARCHITECTURE.md       # System architecture and technology stack
@STANDARDS.md          # Code standards and conventions
@QUALITY.md            # Quality gates and testing requirements
@ORGANIZATION.md       # File organization and project structure
@SUBAGENTS.md          # Sub-agent coordination and usage patterns

## Quick Reference
**IMPORTANT**: Whenever you write code, it MUST follow SOLID design principles. Never write code that violates these principles. If you do, you will be asked to refactor it.

## Intelligent Sub-Agent Coordination
- **Auto-Activation**: Commands automatically engage appropriate specialists
- **Quality Pipeline**: Continuous quality assurance with specialist coordination
- **Complex Features**: Orchestrated development with multi-specialist coordination
- **Troubleshooting**: Automatic diagnostic specialist coordination

## Enhanced Commands Available
- `/workflow` - Intelligent feature implementation with specialist coordination
- `/analyze` - Context-aware analysis with appropriate specialist routing
- `/troubleshoot` - Systematic problem diagnosis with expert coordination
- `/estimate` - Comprehensive project estimation with specialist consultation
```

### Modular Configuration Files

#### @PRINCIPLES.md
```markdown
# Core Development Principles

## SOLID Design Principles
**CRITICAL**: All code must adhere to SOLID principles:
- Single Responsibility Principle
- Open/Closed Principle  
- Liskov Substitution Principle
- Interface Segregation Principle
- Dependency Inversion Principle

## Quality First Approach
- Code quality is never negotiable
- Testing is integral to development, not optional
- Security considerations are built-in from the start
- Performance is designed in, not optimized later

## AI Collaboration Principles
- Leverage sub-agents for specialized expertise
- Use intelligent command routing for efficiency
- Maintain context awareness in all interactions
- Coordinate specialists for comprehensive coverage
```

#### @SUBAGENTS.md
```markdown
# Sub-Agent Coordination Strategy

## Available Specialists
- **code-reviewer**: Code quality, standards, and architecture compliance
- **test-specialist**: Testing strategy, TDD, and quality assurance
- **security-auditor**: Security analysis, vulnerability assessment
- **refactoring-expert**: Performance optimization, architecture improvement
- **documentation-writer**: Technical documentation and knowledge capture

## Auto-Activation Rules
- Security keywords → security-auditor sub-agent
- Testing/TDD → test-specialist sub-agent
- Performance/optimization → refactoring-expert sub-agent
- Quality concerns → code-reviewer sub-agent
- Documentation needs → documentation-writer sub-agent

## Coordination Patterns
- **Simple tasks**: Main context with specialist consultation
- **Complex features**: Multi-specialist coordination with workflow orchestration
- **Quality assurance**: Parallel quality pipeline with all relevant specialists
- **Troubleshooting**: Automatic diagnostic team assembly based on issue type
```

#### @WORKFLOW.md
```markdown
# Development Workflow

## Branch Strategy
1. Create feature branch: `feature-[brief-description]`
2. Implement with continuous quality checks
3. Coordinate with appropriate sub-agents for specialized review
4. Comprehensive testing and validation
5. Quality gate approval from all relevant specialists
6. Merge after all quality criteria met

## Quality Integration
- Continuous code quality monitoring (code-reviewer sub-agent)
- Parallel test development (test-specialist sub-agent)
- Security validation throughout development (security-auditor sub-agent)
- Performance considerations (refactoring-expert sub-agent)
```

## Commands and Context

Commands provide **TARGETED** context for specific, repeatable tasks:

- **T**ask-Specific Instructions
- **A**rguments and Placeholders
- **R**eusable Process Steps
- **G**uided Examples and References
- **E**xplicit Output Requirements
- **T**emplate-Based Naming
- **E**rror Handling and Edge Cases
- **D**ocumentation and Context

### Command Structure
Store commands as markdown files in `.claude/commands/` directory:
- Project-specific: `.claude/commands/` (versioned with project)
- Global commands: `~/.claude/commands/` (available across all projects)

### Example: Code Review Command
`.claude/commands/code-review.md`

```markdown
# Code Review Command

Carefully perform a comprehensive code review of $ARGUMENTS.

## Review Standards
Examples of excellent code that you should match the design/style/conventions of:
- `src/components/UserProfile/UserProfile.tsx` (React components)
- `src/utils/dataValidation.ts` (utility functions)
- `src/hooks/useUserData.ts` (custom hooks)

## Process
1. **First**: Read the example files above to understand our design patterns
2. **Second**: Analyze $ARGUMENTS against these standards
3. **Third**: Create detailed critique covering:
   - Code structure and organization
   - Adherence to established patterns
   - Performance considerations
   - Security implications
   - Maintainability concerns
   - Test coverage gaps

## Output Requirements
- Save review as `ai-code-reviews/{filename}.review.md` for each file reviewed
- Include specific line references for issues
- Provide concrete suggestions for improvements
- Rate overall quality: Excellent/Good/Needs Improvement/Poor
- Estimate refactoring effort: Low/Medium/High

## Review Checklist
- Follows project naming conventions
- Proper error handling implemented
- No hardcoded values or magic numbers
- Appropriate comments and documentation
- Follows existing design principles
- No obvious security vulnerabilities
- Performance optimizations considered
```

## Version Control Standards

### Branch Strategy
Always use feature branches for isolation and easy rollback:

```markdown
## Required in Claude.md:
Before you make any change, create and check out a feature branch named `feature-[brief-description]`. Make all your changes in this branch and commit them.
```

### Branch Naming Conventions
- Feature branches: `feature-[description]`
- AI-created branches: `ai-feature-[description]` (to differentiate from human-created)
- Integration branches: `integration-[description]`
- Bug fixes: `fix-[description]`

### Commit Message Standards
Claude Code excels at detailed commit messages. Example instruction:

```markdown
Write detailed commit messages that include:
- What was changed and why
- Any architectural decisions made
- Breaking changes or migration notes
- Related issue numbers or requirements
```

### Parallel Development with Worktrees
Use Git worktrees for simultaneous feature development:

```bash
# Create worktrees for parallel development
git worktree add ../project-feature1 feature/feature1
git worktree add ../project-feature2 feature/feature2

# Work in separate Claude Code instances
cd ../project-feature1 && claude  # Terminal 1
cd ../project-feature2 && claude  # Terminal 2
```

## Code Quality and Design

### Design Principles Integration
Leverage well-known design principles efficiently:

```markdown
# Token-efficient instructions:
- "Follow SOLID design principles"
- "Use functional programming patterns"
- "Apply Domain-Driven Design principles"
- "Implement clean architecture patterns"
```

### Quality Assurance Process
Always include in Claude.md:

```markdown
## Quality Gates
1. Write tests for all new functionality
2. Compile code and run all tests before committing
3. Run linter and formatter before committing
4. Ensure all tests pass
5. Verify no compilation errors or warnings
```

### Code Review and Evaluation
Use AI to evaluate its own work:

```markdown
After implementing any feature:
1. Run all tests and ensure they pass
2. Perform a self-review of the code
3. Check adherence to project standards
4. Verify proper error handling
5. Confirm documentation is complete
```

## Project Structure Guidelines

### Token-Efficient Organization
Structure projects for immediate AI comprehension:

**Good Structure** (immediately understandable):
```
src/
├── components/
│   ├── expense/
│   ├── dashboard/
│   └── analytics/
├── hooks/
├── utils/
├── types/
└── store/
    ├── slices/
    ├── reducers/
    └── actions/
```

**Poor Structure** (requires exploration):
```
src/
├── stuff/
├── things/
├── misc/
└── code/
```

### Naming Conventions
- Use standard, widely-adopted naming patterns
- Follow framework conventions (Next.js, React, etc.)
- Make directory and file names descriptive and predictable
- Avoid custom or unusual organizational patterns

### File Organization Best Practices
```markdown
## Standard Organization Patterns:
- Components: `/src/components/[feature]/[ComponentName].tsx`
- Utilities: `/src/lib/[category]/[utility].ts`
- Types: `/src/types/[domain].ts`
- Tests: `/src/__tests__/[component].test.ts`
- Hooks: `/src/hooks/use[HookName].ts`
```

## Context Management and Session Continuity

### Proactive Context Management Framework
AI development tools have limited context retention and require structured approaches to maintain project continuity:

#### Project Manifest System
Maintain a comprehensive project manifest to preserve context across sessions:

```markdown
# PROJECT_MANIFEST.md Template

## Project Overview
- **Project Name**: [Name]
- **Current Status**: [Development phase and progress]
- **Last Session Date**: [Date]
- **Current Objective**: [Immediate goal]

## Architecture Status
- **System Design**: [Current architectural decisions]
- **Database Schema**: [Current state and recent changes]
- **API Structure**: [Endpoints and recent modifications]
- **Component Architecture**: [UI/Component organization]

## Implementation Tracking
- **Completed Features**: [List with implementation notes]
- **In Progress**: [Current work with status details]
- **Known Issues**: [Documented problems and workarounds]
- **Testing Status**: [Test coverage and quality metrics]

## Context Restoration
- **Key Files**: [Primary files for context restoration]
- **Recent Changes**: [Summary of recent modifications]
- **Dependencies**: [External dependencies and versions]
- **Environment**: [Development environment specifics]
```

#### Session Restoration Protocol
Use explicit templates for effective session restoration:

```markdown
# Session Restoration Template
"I'm continuing work on [PROJECT_NAME]. Here's the current context:

## Project Status
[Paste PROJECT_MANIFEST.md content]

## Recent Work
[Paste recent commit messages or work summary]

## Current Objective
[Specific goal for this session]

## Context Files
[Attach or reference key project files]

Please review this context and confirm your understanding before we continue."
```

#### Context Preservation Techniques
- **Context Markers**: Use `[CONTEXT:START]` and `[CONTEXT:END]` in code comments
- **Implementation Status**: Document current development stage in comments
- **Decision Log**: Maintain record of architectural decisions and rationale
- **Checkpoint Documentation**: Save context at logical completion points

### Strategic Communication Patterns
Establish clear command signals for effective AI collaboration:

#### Command Signal System
```markdown
# Development Command Signals
[IMPLEMENT] - Begin implementation of specified feature
[REVIEW] - Conduct comprehensive code review
[DEBUG] - Investigate and resolve specific issue
[TEST] - Create or execute testing procedures
[DOCUMENT] - Generate or update documentation
[CHECKPOINT] - Pause for review and validation
[RESTORE] - Restore context from project manifest
```

#### Checkpoint Mechanisms
Structured pause and review cycles at key development points:

```markdown
# Checkpoint Strategy - Pause after:
- Architecture design completion
- Core functionality implementation
- Database schema changes
- API endpoint creation
- UI component development
- Integration testing completion
- Security implementation
- Performance optimization
```

## Feedback and Iteration

### Being Claude's Hands, Eyes, and Ears
When Claude Code cannot automatically test something:

1. **Capture Context**: Screenshot errors, copy error messages
2. **Provide Specificity**: "Clicking add expense creates this error: [error text]"
3. **Close the Loop**: Give Claude the feedback it needs to fix issues
4. **Minimize Manual Testing**: Build automated testing where possible
5. **Use Command Signals**: Apply [DEBUG] or [REVIEW] signals for structured feedback

### Self-Checking Requirements
Include in Claude.md:

```markdown
## Self-Checking Requirements:
Before completing any task:
1. Compile the code and fix any compilation errors
2. Run all tests and ensure they pass
3. Test the functionality manually if no automated tests exist
4. Verify all requirements have been met
5. Check for proper error handling
```

### Think First, Code Second
For complex features, use extended thinking with Claude Sonnet 4.5's hybrid reasoning model:

```markdown
# Thinking Levels (with specific token budgets):
- "think" - Basic analysis (4,000 tokens)
- "think hard" / "megathink" - Deeper evaluation (10,000 tokens)
- "ultrathink" - Maximum thinking budget (31,999 tokens)
- Extended thinking can use up to 64,000 tokens for critical architectural decisions
- With interleaved thinking (beta), full 200K context window available

# Hybrid Reasoning Model (Claude Sonnet 4.5):
- Instant responses for straightforward tasks
- Extended thinking with visible reasoning for complex problems
- System automatically summarizes thinking process in API responses
- Visible thinking blocks show actual internal reasoning, not summaries

# When to Use Each Level:
- **think (4K)**: Standard architectural planning, code reviews, simple refactoring
- **think hard (10K)**: Security analysis, performance optimization, complex debugging
- **ultrathink (32K)**: Critical migrations, systemic problem resolution, new pattern design
- **64K budget**: Major architectural overhauls, framework migrations, system-wide refactoring

# Example:
Think hard about implementing a machine learning expense categorization system.
Analyze the technical challenges, data requirements, ML approaches, privacy concerns,
user experience, edge cases, and deployment strategy. Save the plan to development_plan.txt

# Cost Considerations:
Ultrathink generates disproportionate costs - reserve for major architectural challenges only.
For most tasks, "think" (4K) or "think hard" (10K) provides optimal balance of quality and cost.
```

## Advanced Techniques

### Intelligent Command System
Leverage context-aware commands that automatically coordinate appropriate specialists:

```markdown
# Enhanced Command Categories:
- /workflow: Implementation roadmaps with intelligent specialist coordination
- /analyze: Context-aware analysis with automatic expert routing
- /troubleshoot: Systematic problem diagnosis with appropriate specialist assembly
- /estimate: Comprehensive project estimation with specialist consultation

# Benefits:
- Reduced cognitive load through intelligent automation
- Context-aware specialist selection
- Comprehensive coverage with minimal manual coordination
- Consistent quality assurance across all development activities
```

### Workflow Orchestration Patterns
Advanced coordination patterns for complex, multi-domain development:

```markdown
# Complex Feature Orchestration:
1. Auto-analysis and specialist selection based on feature scope
2. Coordinated planning with appropriate domain experts
3. Multi-stream implementation with continuous quality assurance
4. Integrated validation with comprehensive specialist review
5. Production deployment with monitoring and documentation

# Quality Assurance Pipeline:
1. Pre-development quality planning with specialist input
2. Development-time continuous quality validation
3. Integration quality validation with multi-specialist coordination
4. Pre-production quality certification with full specialist sign-off
5. Post-production quality monitoring and improvement
```

### Multimodal Prompting
Use images, sketches, and screenshots for complex requirements:

```markdown
# Effective for:
- UI/UX design and layout
- Spatial relationships
- Color schemes and visual hierarchy
- Performance profiling results
- Bug reports with visual issues
- Design handoffs from mockups
```

### Sub-Agents and Specialized AI

Sub-agents are specialized AI assistants within Claude Code that handle specific tasks with dedicated configurations and contexts. They provide focused expertise while preserving your main conversation context.

#### What Are Sub-Agents?
- **Specialized AI assistants** with custom system prompts and tool permissions
- **Separate context windows** that don't pollute your main conversation
- **Configurable expertise** for specific domains (testing, security, documentation)
- **Reusable across projects** with consistent behavior patterns

#### When to Use Sub-Agents
```markdown
# Ideal Use Cases:
- Complex codebase exploration requiring focused analysis
- Specialized tasks requiring domain expertise (security audits, performance optimization)
- Parallel development workflows with different concerns
- Tasks requiring different tool permissions or restrictions
- Repetitive processes that benefit from specialized prompting
```

#### Creating Sub-Agents
Use the `/agents` command to create project or user-level sub-agents:

```bash
# Create project-specific sub-agent (stored in .claude/agents/)
/agents

# Choose template or create custom:
Name: test-specialist
Description: Specialized in writing and debugging tests
Tools: Edit, Bash(npm test), Read
System Prompt: You are a testing specialist focused on comprehensive test coverage...
```

#### Sub-Agent Storage Patterns
```markdown
# Project-level (version controlled):
.claude/agents/
├── code-reviewer.md          # Code quality and standards
├── test-specialist.md        # Testing and QA
├── security-auditor.md       # Security analysis
└── refactoring-expert.md     # Code improvement

# User-level (personal preferences):
~/.claude/agents/
├── documentation-writer.md   # Personal documentation style
└── performance-optimizer.md  # Personal optimization patterns
```

#### Invocation Methods

**Automatic Delegation:**
```markdown
# Claude automatically selects appropriate sub-agent:
"Review this authentication system for security vulnerabilities"
# → Automatically delegates to security-auditor sub-agent

"Fix the failing tests in the payment module"
# → Automatically delegates to test-specialist sub-agent
```

**Explicit Invocation:**
```markdown
# Direct sub-agent specification:
"Use the code-reviewer sub-agent to analyze the user authentication module"
"Have the test-specialist sub-agent create comprehensive tests for the API endpoints"
"Ask the security-auditor sub-agent to review this OAuth implementation"
```

#### Sub-Agent Workflow Patterns

**Pattern 1: Specialized Analysis**
```markdown
1. "Use the security-auditor sub-agent to analyze the authentication system"
2. "Have the performance-optimizer sub-agent review the database queries"
3. "Ask the code-reviewer sub-agent to evaluate overall code quality"
4. "Integrate findings from all sub-agents into improvement plan"
```

**Pattern 2: Parallel Development**
```markdown
# Using worktrees with specialized sub-agents:
git worktree add ../feature-frontend feature/frontend
git worktree add ../feature-backend feature/backend

# Terminal 1: Frontend specialist
cd ../feature-frontend && claude
"Use the ui-specialist sub-agent for all frontend development"

# Terminal 2: Backend specialist  
cd ../feature-backend && claude
"Use the api-specialist sub-agent for all backend development"
```

**Pattern 3: Quality Assurance Pipeline**
```markdown
1. Implementation: Main Claude context
2. Testing: "Delegate to test-specialist sub-agent"
3. Security Review: "Use security-auditor sub-agent"
4. Documentation: "Have documentation-writer sub-agent create docs"
5. Final Review: "Code-reviewer sub-agent for final quality check"
```

#### Sub-Agent Best Practices

**Design Principles:**
- **Single Responsibility**: Each sub-agent should have one clear purpose
- **Focused Expertise**: Write detailed system prompts for domain knowledge
- **Appropriate Tools**: Grant only necessary tool permissions
- **Clear Boundaries**: Define what the sub-agent should and shouldn't do

**Configuration Guidelines:**
```markdown
# Effective Sub-Agent System Prompt Template:
You are a [ROLE] specialist focused on [DOMAIN]. Your expertise includes:

CORE RESPONSIBILITIES:
- [Primary responsibility 1]
- [Primary responsibility 2]
- [Primary responsibility 3]

ANALYSIS APPROACH:
- [How to analyze problems in this domain]
- [Key factors to consider]
- [Common patterns to look for]

OUTPUT REQUIREMENTS:
- [Expected format for deliverables]
- [Quality standards to maintain]
- [Integration with other workflows]

BOUNDARIES:
- [What NOT to do]
- [When to escalate to main context]
- [Tool usage limitations]
```

**Team Integration:**
```markdown
# Sub-Agent Naming Conventions:
- {domain}-specialist: test-specialist, security-specialist
- {role}-expert: refactoring-expert, performance-expert  
- {function}-auditor: security-auditor, quality-auditor
- {area}-reviewer: code-reviewer, architecture-reviewer

# Version Control:
- Commit project sub-agents to git for team consistency
- Document sub-agent purposes in project README
- Regular review and updates of sub-agent configurations
```

#### Advanced Sub-Agent Coordination

**Chain of Specialists:**
```markdown
# Complex feature development with sub-agent chain:
1. "Architecture-specialist: Design the user authentication system"
2. "Security-auditor: Review the architectural design for vulnerabilities"  
3. "Implementation-specialist: Build the system following the reviewed design"
4. "Test-specialist: Create comprehensive tests for the implementation"
5. "Documentation-writer: Document the authentication system"
```

**Sub-Agent Performance Considerations:**
- Sub-agents start with clean context (slight latency overhead)
- Use for substantial tasks to justify context initialization
- Consider sub-agent reuse for related tasks in same session
- Monitor performance impact on complex workflows

### Intelligent Auto-Activation Patterns

Inspired by advanced AI frameworks, implement intelligent sub-agent selection that reduces cognitive load through context-aware automation.

#### Context-Aware Auto-Activation
```markdown
# Intelligent routing based on task characteristics:
- Security keywords → security-auditor sub-agent automatically selected
- Testing/TDD mentions → test-specialist sub-agent prioritized
- Performance concerns → refactoring-expert sub-agent activated
- Documentation needs → documentation-writer sub-agent engaged
- Quality focus → code-reviewer sub-agent coordination
```

#### Multi-Domain Auto-Coordination
```markdown
# Complex tasks requiring multiple specialists:
"Implement OAuth2 authentication with comprehensive testing"
→ Auto-activates: security-auditor + test-specialist + code-reviewer sub-agents

"Optimize database performance and add monitoring"
→ Auto-activates: refactoring-expert + code-reviewer + documentation-writer sub-agents
```

#### Intelligent Command Integration
```markdown
# Enhanced commands with auto-activation:
/workflow "Feature implementation" → Activates appropriate specialist combination
/analyze "System component" → Routes to relevant analysis specialists
/troubleshoot "Production issue" → Coordinates appropriate diagnostic specialists
/estimate "Project scope" → Engages planning and assessment specialists
```

#### Adaptive Specialist Selection
```markdown
# Context-driven specialist prioritization:
High Complexity Tasks:
- Primary: Domain expert (security-auditor, test-specialist, etc.)
- Supporting: code-reviewer for quality oversight
- Coordination: refactoring-expert for architecture guidance

Standard Tasks:
- Primary: Relevant domain expert
- Supporting: code-reviewer as needed
- Documentation: documentation-writer for knowledge capture

Simple Tasks:
- Main context with specialist consultation as needed
- Minimal sub-agent activation to avoid overhead
```

### Multi-Agent Architecture (Official Anthropic Patterns)

Based on Anthropic's research and production implementations, multi-agent systems significantly outperform single-agent approaches for complex tasks.

#### Performance Benchmarks
```markdown
# Anthropic Internal Research:
- Multi-agent system (Opus 4 orchestrator + Sonnet 4 workers) vs single-agent Opus 4
- Result: 90.2% improvement on internal research evaluation
- Key insight: Separation of concerns enables thorough, independent investigations

# Architecture Patterns:
- **Orchestrator-Worker**: Lead agent (Opus 4) coordinates specialized workers (Sonnet 4)
- **Wave-Based Generation**: Deploy agents in strategic batches to manage context limits
- **Hierarchical Multi-Tier**: Strategic orchestrator → Domain coordinators → Task specialists
```

#### Implementation Patterns
```markdown
# Simple Queries (2-3 sub-agents):
/workflow "Add user login feature"
→ Security-auditor + Test-specialist + Code-reviewer

# Comprehensive Projects (20-30 agents in waves):
"Implement complete e-commerce checkout system"
→ Wave 1: Architecture-specialist, Security-auditor, Database-expert
→ Wave 2: Frontend-specialist, Backend-specialist, API-expert
→ Wave 3: Test-specialist, Performance-expert, Documentation-writer
→ Wave 4: Integration-specialist, QA-auditor, Deployment-expert

# Benefits:
- Each agent has separate context window (no context pollution)
- Parallel processing of independent concerns
- Specialized expertise for each domain
- Reduced path dependency through independent analysis
```

#### Orchestration Best Practices
```markdown
# Strategic Coordination:
1. **Orchestrator Agent** maintains big picture, sets objectives, allocates resources
2. **Coordinator Agents** manage specific domains (research, analysis, implementation)
3. **Worker Agents** execute focused tasks with specialized expertise

# Context Management:
- Simple queries: 2-3 subagents with minimal coordination overhead
- Complex features: 10-15 agents in 2-3 waves
- Large-scale projects: 20-30 agents in 4-5 coordinated waves

# Performance Considerations:
- Each subagent starts with clean context (slight latency)
- Use for substantial tasks to justify initialization cost
- Monitor context window usage across agent network
- Consider wave-based deployment for managing context limits
```

### Sandboxing and Security (October 2025)

Claude Code introduced filesystem and network isolation features that dramatically improve safety while reducing permission friction.

#### Sandbox Features
```markdown
# Two Security Boundaries:
1. **Filesystem Isolation**: Claude can only access/modify specific directories
2. **Network Isolation**: Claude can only connect to approved servers

# Performance Impact:
- 84% reduction in permission prompts (Anthropic internal usage)
- Same security guarantees across CLI, web, and mobile interfaces
- No performance degradation for normal operations

# Technical Implementation:
- Built on OS-level primitives: Linux bubblewrap, MacOS seatbelt
- Open source implementation available from Anthropic
- Network proxy enforces domain restrictions outside sandbox
- Both boundaries required for complete security
```

#### Safe YOLO Mode with Sandboxing
```markdown
# Updated YOLO Mode Best Practices (2025):
- Primary safety: Sandboxing, not containers
- --dangerously-skip-permissions flag now safer with sandbox isolation
- Filesystem boundaries prevent accidental system modifications
- Network boundaries prevent data exfiltration and malware downloads

# Container Workflows (Still Recommended):
- Dev containers for additional isolation layer
- Docker-based claude-yolo wrappers for production safety
- VM isolation for maximum security in critical environments

# AllowedTools Configuration:
- Whitelist specific safe tools in config (search, tests)
- Prevents dangerous commands even with all permissions bypassed
- Ideal for CI/CD and automated workflows

# Security Vulnerabilities:
- CVE-2025-54794 and CVE-2025-54795 patched
- Update to v0.2.111 (CLI) or v1.0.20 (latest) for security fixes
- Sandboxing prevents exploit impact even if vulnerabilities exist
```

#### Sandbox Configuration
```markdown
# Filesystem Boundaries:
- Restrict Claude to project directory: --sandbox-root /path/to/project
- Prevent access to sensitive directories (~/.ssh, ~/.aws, etc.)
- Explicit permission required for new directory access

# Network Boundaries:
- Approve domains through proxy service
- Block by default, allow on confirmation
- Persistent allow-list for trusted domains
- Prevents prompt injection exfiltration attacks
```

### Web Interface and Deployment Options (October 2025)

Claude Code is now available beyond the CLI, enabling zero-setup development and team collaboration.

#### Claude Code on the Web
```markdown
# Features (Beta - Pro & Max users):
- Zero-setup browser-based development
- Cloud execution in isolated sandbox environments
- GitHub repository integration
- Parallel session support for multiple tasks
- Real-time progress monitoring
- Mobile access via iOS app

# Use Cases:
- Development from any device without local setup
- Team collaboration through URL sharing
- Quick prototyping without environment configuration
- Remote development on Anthropic-managed infrastructure
- Mobile coding and reviews on iOS devices

# Security:
- Every task runs in isolated sandbox (same as CLI)
- Git interactions through secure proxy service
- Filesystem and network isolation enforced
- Available for Claude Pro ($20/month) and Max ($100-200/month) users
```

#### VS Code Extension (Beta)
```markdown
# Native IDE Integration:
- Easy-to-use graphical interface
- No terminal familiarity required
- Available from VS Code marketplace
- Seamless integration with existing workflows
- Full Claude Code capabilities in familiar IDE

# Benefits:
- Lower barrier to entry for non-terminal users
- Native debugging and editor integration
- Side-by-side code comparison
- Integrated git workflows
```

#### Deployment Matrix
```markdown
# Choose Your Interface:
1. **CLI (Terminal)**: Maximum control, Unix philosophy, power users
2. **VS Code Extension**: Native IDE experience, visual workflows
3. **Web Interface**: Zero setup, cross-device, mobile access
4. **MCP Server Mode**: Remote invocation from other tools

# All interfaces provide:
- Same Claude Sonnet 4.5 model capabilities
- Sandboxing with filesystem/network isolation
- Extended thinking and hybrid reasoning
- Sub-agent coordination and specialized workflows
```

### Model Context Protocol (MCP) Updates (2025)

MCP has evolved from Anthropic innovation to industry-wide standard with major ecosystem growth.

#### Industry Adoption
```markdown
# Major Platform Support:
- **OpenAI** (March 2025): MCP support across ChatGPT
- **Google** (April 2025): Gemini MCP integration
- **Development Tools**: Block, Apollo, Zed, Replit, Codeium, Sourcegraph
- **Community**: Thousands of MCP servers built since November 2024
- **SDKs**: Available for all major programming languages

# Impact:
- De facto standard for connecting agents to tools and data
- Unified protocol across AI platforms and development tools
- Massive community-driven server ecosystem
```

#### Code Execution with MCP
```markdown
# Efficiency Improvements:
- Agents can interact with MCP servers more efficiently
- Reduced token usage through code execution
- Handle more tools without context window bloat
- Intermediate results don't pass through context window

# Technical Benefits:
- Execute code to interact with tools (vs loading all definitions)
- Scale to hundreds of connected tools
- Lower latency and reduced costs
- More efficient multi-tool workflows
```

#### Claude Code as MCP Server
```markdown
# Dual Server/Client Capability:
claude mcp serve

# Features:
- Exposes Claude Code's file editing and command execution via MCP
- Other MCP clients (Claude Desktop, Cursor, Windsurf) can invoke remotely
- Enables Claude Code as a service for other AI tools
- Remote automation and integration capabilities

# Popular MCP Integrations:
- Stripe, Figma, GitHub, PostgreSQL, Sentry
- Asana, Atlassian, Google Drive, Slack
- Context7 for documentation integration
- Custom MCP servers for project-specific tools
```

#### MCP Best Practices
```markdown
# Integration Strategy:
1. Start with high-value integrations (GitHub, databases, monitoring)
2. Use official MCP servers when available
3. Build custom servers for project-specific tools
4. Configure permissions carefully in .claude/settings.local.json

# Performance Considerations:
- Code execution reduces token usage significantly
- Batch operations when possible for efficiency
- Monitor context window with many connected tools
- Use MCP server mode for remote automation
```

### In-Context Learning
Teach through examples rather than explicit rules:

```markdown
# Teaching by Example:
"Examples of excellent code that you should match the design/style/conventions of:
- [file1.ts] (component patterns)
- [file2.ts] (utility patterns)  
- [file3.ts] (testing patterns)

Read these files first to understand our style, then implement the new feature following the same patterns."
```

### Process Improvement Focus
When Claude Code makes mistakes:

1. **Don't just fix the code** - update Claude.md or commands
2. **Ask**: "What context was missing that caused this mistake?"
3. **Update**: Add specificity, instructions, or examples to prevent recurrence
4. **Goal**: Build increasingly reliable, repeatable processes

### Integration Commands
Create reusable commands for common workflows:

```markdown
# Example: Parallel Work Integration
`.claude/commands/integrate-parallel-work.md`

I have features developed in parallel worktrees that I need to integrate: $ARGUMENTS

Please help me integrate these features:
1. Create integration branch "integration/parallel-features"
2. Merge each feature branch into integration branch
3. Resolve any merge conflicts
4. Test that all features work together
5. Run all tests to ensure nothing is broken
6. Merge to main and clean up branches when successful
```

## Quick Reference Checklist

### Before Starting Any Project
- [ ] Create comprehensive Claude.md file (consider modular approach with @-references)
- [ ] Set up version control standards and branch strategy
- [ ] Define project structure conventions and organization
- [ ] Create essential commands for common tasks (including intelligent commands)
- [ ] Establish quality gates and testing requirements
- [ ] Configure sub-agent templates for project-specific specialists
- [ ] Set up intelligent command routing and auto-activation patterns

### For Every Feature Request
- [ ] Use big prompt approach with intelligent command coordination
- [ ] Leverage context-aware commands (/workflow, /analyze, /estimate)
- [ ] Allow auto-activation of appropriate specialists based on feature characteristics
- [ ] Specify branch naming and commit requirements
- [ ] Include comprehensive quality assurance with specialist coordination
- [ ] Consider workflow orchestration for complex, multi-domain features

### When Issues Occur
- [ ] Use intelligent troubleshooting with automatic specialist coordination
- [ ] Provide Claude with error context and allow specialist analysis
- [ ] Update Claude.md, commands, or sub-agent configurations to prevent recurrence
- [ ] Focus on process improvement with specialist input
- [ ] Verify comprehensive quality validation before completion

### For Complex Projects
- [ ] Use workflow orchestration patterns for multi-specialist coordination
- [ ] Leverage intelligent command system for reduced cognitive load
- [ ] Implement quality assurance pipeline with continuous specialist validation
- [ ] Consider Best-of-N approach with specialist input for multiple solutions
- [ ] Use "think first" approach with appropriate specialist consultation
- [ ] Plan integration strategy with comprehensive specialist coordination
- [ ] Use worktrees with specialized sub-agent focuses for parallel development

### SuperClaude-Inspired Enhancements
- [ ] Implement context-aware auto-activation for reduced manual coordination
- [ ] Use modular configuration approach for maintainable Claude.md files
- [ ] Leverage intelligent routing to appropriate specialists based on task characteristics
- [ ] Establish workflow orchestration for complex, multi-domain features
- [ ] Create quality assurance pipelines with continuous specialist validation

### Advanced Community Tools and Integrations
- [ ] **Claude Squad**: Multi-workspace agent management for complex projects
- [ ] **Claude Code Flow**: Autonomous code writing and optimization layer
- [ ] **CC Usage**: CLI tool for analyzing Claude Code usage patterns and optimization
- [ ] **Aider AI**: Terminal-based AI pair programming with Git integration
- [ ] **Cursor/Windsurf IDE**: AI-enhanced development environments with context management
- [ ] **Context7 MCP Server**: Advanced documentation and library integration
- [ ] **Nix Configuration**: Declarative Claude Code environment management

---

*This standards document integrates the complete Claude Code course materials with advanced insights from the SuperClaude Framework, representing state-of-the-art best practices for scaling AI labor in software development through intelligent automation and specialist coordination.*