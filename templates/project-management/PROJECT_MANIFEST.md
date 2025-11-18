# Project Manifest Template

This template provides comprehensive project status and context for maintaining continuity across Claude Code sessions.

## Project Overview
- **Project Name**: [Insert project name]
- **Current Status**: [Development phase: Planning/Implementation/Testing/Deployment]
- **Last Session Date**: [Date of last development session]
- **Current Objective**: [Immediate goal for current/next session]
- **Project Priority**: [High/Medium/Low]
- **Expected Completion**: [Target completion date]

## Architecture Status
- **System Design**: [Current architectural decisions and patterns]
- **Database Schema**: [Current state, recent changes, pending migrations]
- **API Structure**: [Endpoints implemented, planned endpoints, recent modifications]
- **Component Architecture**: [UI/Component organization, design system status]
- **External Integrations**: [Third-party services, APIs, authentication systems]

## Implementation Tracking

### Completed Features
- **[Feature Name]**: [Implementation status and notes]
  - Files modified: [List of key files]
  - Tests added: [Test coverage details]
  - Documentation: [Status of documentation]
  - Quality validation: [Code review and testing status]

### In Progress
- **[Feature Name]**: [Current work and status details]
  - Current stage: [Design/Implementation/Testing/Review]
  - Blockers: [Any current blockers or dependencies]
  - Next steps: [Immediate next actions]
  - Estimated completion: [Timeline estimate]

### Planned Features
- **[Feature Name]**: [Priority and planning status]
  - Dependencies: [Required prerequisite work]
  - Complexity estimate: [High/Medium/Low]
  - Resource requirements: [Skills/tools needed]

### Known Issues
- **[Issue Description]**: [Problem details and current status]
  - Severity: [Critical/High/Medium/Low]
  - Workaround: [Temporary solution if available]
  - Resolution plan: [Planned approach to fix]
  - Assignee: [Who is responsible for resolution]

## Technical Context

### Technology Stack
- **Frontend**: [Framework, version, key libraries]
- **Backend**: [Framework, version, key libraries]
- **Database**: [Type, version, connection details]
- **Testing**: [Frameworks, coverage tools, testing approach]
- **Deployment**: [Platform, CI/CD setup, deployment process]

### Dependencies
- **External Dependencies**: [Third-party libraries and versions]
- **Internal Dependencies**: [Project modules and their relationships]
- **Development Dependencies**: [Build tools, testing tools, development utilities]
- **Environment Dependencies**: [Node version, database requirements, system dependencies]

### Environment Status
- **Development Environment**: [Local setup status and configuration]
- **Testing Environment**: [Test environment status and data]
- **Staging Environment**: [Staging deployment status]
- **Production Environment**: [Production deployment status and health]

## Quality Metrics

### Code Quality
- **Test Coverage**: [Current percentage and target]
- **Code Quality Score**: [Linting, complexity metrics]
- **Technical Debt**: [Current assessment and improvement plan]
- **Performance Metrics**: [Load times, optimization status]

### Security Status
- **Security Audit**: [Last audit date and findings]
- **Vulnerability Assessment**: [Known vulnerabilities and mitigation status]
- **Compliance**: [Regulatory compliance status]
- **Authentication**: [Authentication system status and security measures]

## Context Restoration

### Key Files for Context
- **Core Implementation**: [Primary files containing main logic]
- **Configuration Files**: [Settings, environment, build configuration]
- **Test Files**: [Key test files for understanding functionality]
- **Documentation**: [README, API docs, architecture documentation]

### Recent Changes Summary
- **Last 3 Commits**: [Brief summary of recent changes]
- **Modified Components**: [Recently changed components and rationale]
- **New Dependencies**: [Recently added libraries or tools]
- **Configuration Changes**: [Environment or build configuration updates]

### Current Working Context
- **Active Branch**: [Current git branch and purpose]
- **Modified Files**: [Files currently being worked on]
- **Next Session Goals**: [Specific objectives for next development session]
- **Context Preservation Notes**: [Important context for next session]

## Communication History

### Recent Decisions
- **[Decision Date]**: [Decision description and rationale]
  - Impact: [How this affects the project]
  - Alternatives considered: [Other options evaluated]
  - Follow-up required: [Any follow-up actions needed]

### Command Signal Usage
Document recent command signal usage for pattern tracking:
- **[IMPLEMENT]**: [Recent implementation commands and outcomes]
- **[REVIEW]**: [Recent code reviews and findings]
- **[DEBUG]**: [Recent debugging sessions and resolutions]
- **[TEST]**: [Recent testing activities and results]
- **[CHECKPOINT]**: [Recent checkpoint validations]

## Session Restoration Template

When beginning a new session, use this template:

```markdown
I'm continuing work on [PROJECT_NAME]. Here's the current context:

## Project Status
[Paste relevant sections from PROJECT_MANIFEST.md]

## Recent Work  
[Paste recent commit messages or work summary]

## Current Objective
[Specific goal for this session]

## Context Files
[Reference key project files for context]

## Command Signal
[RESTORE] - Please review this context and confirm your understanding before we continue.
```

## Maintenance Guidelines

### Regular Updates
- Update manifest after each significant development session
- Refresh context restoration files weekly
- Review and clean up completed items monthly
- Validate environment status before major development sessions

### Quality Validation
- Verify all quality metrics are current and accurate
- Ensure all known issues are properly documented
- Validate that context restoration information is complete
- Confirm that architectural decisions are properly recorded

---

*This project manifest template ensures comprehensive context preservation and effective session continuity for AI-assisted development projects.*