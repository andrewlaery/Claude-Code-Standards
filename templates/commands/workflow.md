# Workflow Implementation Command

Create a comprehensive implementation roadmap for: $ARGUMENTS

This command creates structured workflows with intelligent sub-agent coordination for complex development tasks.

## Intelligent Analysis Phase

### Auto-Activation Logic
```markdown
# The command automatically activates appropriate experts based on task analysis:
- If security-related keywords detected → security-auditor sub-agent
- If testing/TDD mentioned → test-specialist sub-agent  
- If architecture/design focus → refactoring-expert sub-agent
- If documentation needed → documentation-writer sub-agent
- If quality concerns → code-reviewer sub-agent
```

### Context Analysis
1. **Task Complexity Assessment**: Analyze scope and determine resource requirements
2. **Domain Detection**: Identify primary technical domains involved
3. **Risk Assessment**: Evaluate potential challenges and blockers
4. **Resource Planning**: Determine required sub-agents and tool integrations

## Workflow Planning Phase

### Phase 1: Discovery and Architecture
```markdown
# Auto-activated sub-agents based on task analysis:
- Architecture planning: refactoring-expert sub-agent for system design
- Security considerations: security-auditor sub-agent for threat modeling
- Quality planning: code-reviewer sub-agent for standards definition
```

### Phase 2: Implementation Strategy
```markdown
# Coordinate implementation approach:
1. Break down $ARGUMENTS into manageable components
2. Identify dependencies and critical path
3. Plan testing strategy with test-specialist sub-agent
4. Define quality gates and acceptance criteria
5. Create timeline with realistic milestones
```

### Phase 3: Execution Coordination
```markdown
# Multi-agent coordination pattern:
- Core implementation: Main context with specialist consultation
- Quality assurance: Continuous code-reviewer sub-agent integration
- Testing: Parallel test-specialist sub-agent for comprehensive coverage
- Documentation: documentation-writer sub-agent for real-time docs
```

## Intelligent Sub-Agent Coordination

### Context-Aware Activation
Based on $ARGUMENTS content, automatically determine and activate:

**For Security-Critical Features:**
```markdown
"Auto-activating: security-auditor sub-agent for threat analysis"
"Coordinating: code-reviewer sub-agent for secure coding patterns"
```

**For Complex UI/UX Features:**
```markdown
"Auto-activating: refactoring-expert sub-agent for component architecture"
"Coordinating: documentation-writer sub-agent for user experience documentation"
```

**For API/Backend Features:**
```markdown
"Auto-activating: security-auditor sub-agent for API security"
"Coordinating: test-specialist sub-agent for comprehensive API testing"
```

### Collaborative Workflow Patterns

#### Pattern A: Sequential Specialist Chain
```markdown
1. refactoring-expert: "Design architecture for $ARGUMENTS"
2. security-auditor: "Review architecture for security implications"
3. test-specialist: "Create testing strategy based on reviewed architecture"
4. Main context: "Implement following specialist guidance"
5. code-reviewer: "Final quality assessment and optimization suggestions"
```

#### Pattern B: Parallel Analysis Coordination
```markdown
# Simultaneous specialist analysis:
Parallel Sub-Agent Tasks:
- security-auditor: "Analyze security requirements for $ARGUMENTS"
- test-specialist: "Plan comprehensive testing approach for $ARGUMENTS"  
- refactoring-expert: "Design optimal code structure for $ARGUMENTS"

Integration Phase:
- Main context: "Synthesize specialist recommendations into implementation plan"
```

## Implementation Roadmap Template

### Milestone 1: Foundation
- [ ] Architecture design (refactoring-expert sub-agent)
- [ ] Security assessment (security-auditor sub-agent)
- [ ] Testing strategy (test-specialist sub-agent)
- [ ] Quality standards definition (code-reviewer sub-agent)

### Milestone 2: Core Implementation
- [ ] Core functionality development
- [ ] Continuous quality checks (code-reviewer sub-agent)
- [ ] Security validation (security-auditor sub-agent)
- [ ] Test implementation (test-specialist sub-agent)

### Milestone 3: Integration & Polish
- [ ] System integration testing
- [ ] Performance optimization (code-reviewer sub-agent)
- [ ] Security hardening (security-auditor sub-agent)
- [ ] Documentation completion (documentation-writer sub-agent)

### Milestone 4: Delivery
- [ ] Final quality assurance
- [ ] Security audit completion
- [ ] Documentation review
- [ ] Deployment readiness validation

## Quality Gates and Checkpoints

### Automated Quality Checkpoints
At each milestone, automatically engage relevant sub-agents:

```markdown
# Quality Gate Pattern:
1. code-reviewer sub-agent: "Assess code quality and standards compliance"
2. security-auditor sub-agent: "Validate security implementation"
3. test-specialist sub-agent: "Verify test coverage and quality"
4. Main context: "Integration testing and final validation"
```

### Success Criteria
- [ ] All quality gates passed with sub-agent approval
- [ ] Security audit completed without critical issues
- [ ] Test coverage meets project standards
- [ ] Documentation is comprehensive and accurate
- [ ] Performance meets specified requirements

## Workflow Orchestration Features

### Dynamic Sub-Agent Selection
The workflow command intelligently selects sub-agents based on:
- **Keywords in $ARGUMENTS**: Security, testing, performance, documentation
- **Project context**: Existing codebase patterns and requirements
- **Complexity analysis**: Simple tasks vs. complex multi-domain features
- **Risk assessment**: High-risk changes require additional specialist review

### Adaptive Planning
```markdown
# Example adaptive responses:
- High complexity detected → Extended planning phase with multiple specialists
- Security keywords found → Mandatory security-auditor sub-agent involvement
- Legacy code integration → refactoring-expert sub-agent for modernization strategy
- API development → Enhanced test-specialist sub-agent for integration testing
```

## Usage Examples

### Simple Feature
```markdown
/workflow "Add user profile editing functionality"
# Auto-activates: code-reviewer + test-specialist sub-agents
```

### Complex Security Feature
```markdown
/workflow "Implement OAuth2 authentication with PKCE flow"
# Auto-activates: security-auditor + code-reviewer + test-specialist + documentation-writer sub-agents
```

### Architecture Change
```markdown
/workflow "Migrate from REST to GraphQL API"
# Auto-activates: refactoring-expert + security-auditor + test-specialist + documentation-writer sub-agents
```

Remember: The workflow command reduces cognitive load by automatically coordinating the right specialists for your specific development challenge.