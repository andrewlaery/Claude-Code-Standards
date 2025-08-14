# Intelligent Analysis Command

Perform comprehensive analysis of: $ARGUMENTS

This command provides context-aware analysis with automatic expert selection and intelligent routing to appropriate sub-agents.

## Auto-Activation Intelligence

### Context Detection System
The analyze command automatically detects context and activates appropriate specialists:

```markdown
# Automatic Expert Selection Based on Context:
- Security analysis keywords → security-auditor sub-agent
- Code quality/structure → code-reviewer sub-agent  
- Performance issues → refactoring-expert sub-agent
- Test coverage/quality → test-specialist sub-agent
- Documentation gaps → documentation-writer sub-agent
- Architecture concerns → refactoring-expert sub-agent
```

### Intelligent Routing Patterns

#### Single Domain Analysis
```markdown
# For focused analysis:
"Analyze authentication security" 
→ Auto-activates: security-auditor sub-agent

"Analyze test coverage for payment module"
→ Auto-activates: test-specialist sub-agent

"Analyze code quality in user management system"
→ Auto-activates: code-reviewer sub-agent
```

#### Multi-Domain Analysis
```markdown
# For comprehensive analysis:
"Analyze the entire user authentication system"
→ Auto-activates: security-auditor + code-reviewer + test-specialist sub-agents

"Analyze performance issues in the API layer"
→ Auto-activates: refactoring-expert + code-reviewer sub-agents
```

## Analysis Categories

### 1. Security Analysis
**Auto-Activation Trigger**: Keywords like "security", "vulnerability", "authentication", "authorization", "encryption"

```markdown
# Automatic security-auditor sub-agent activation:
"Use security-auditor sub-agent to analyze $ARGUMENTS for:"
- Authentication and authorization vulnerabilities
- Input validation and injection risks
- Data exposure and privacy concerns
- Cryptographic implementation issues
- API security and rate limiting
- Session management security
```

### 2. Code Quality Analysis  
**Auto-Activation Trigger**: Keywords like "quality", "maintainability", "structure", "patterns", "refactor"

```markdown
# Automatic code-reviewer sub-agent activation:
"Use code-reviewer sub-agent to analyze $ARGUMENTS for:"
- SOLID principle adherence
- Code organization and structure
- Design pattern usage
- Maintainability concerns
- Performance bottlenecks
- Technical debt assessment
```

### 3. Testing Analysis
**Auto-Activation Trigger**: Keywords like "test", "coverage", "quality assurance", "TDD", "debugging"

```markdown
# Automatic test-specialist sub-agent activation:
"Use test-specialist sub-agent to analyze $ARGUMENTS for:"
- Test coverage gaps and quality
- Testing strategy effectiveness
- Test reliability and flakiness
- Edge case coverage
- Integration test completeness
- Performance test requirements
```

### 4. Architecture Analysis
**Auto-Activation Trigger**: Keywords like "architecture", "design", "structure", "scalability", "performance"

```markdown
# Automatic refactoring-expert sub-agent activation:
"Use refactoring-expert sub-agent to analyze $ARGUMENTS for:"
- Architectural patterns and consistency
- Scalability and performance implications
- Dependency management and coupling
- Component organization and separation
- Design pattern opportunities
- Refactoring and improvement recommendations
```

### 5. Documentation Analysis
**Auto-Activation Trigger**: Keywords like "documentation", "docs", "README", "API docs", "comments"

```markdown
# Automatic documentation-writer sub-agent activation:
"Use documentation-writer sub-agent to analyze $ARGUMENTS for:"
- Documentation completeness and accuracy
- API documentation quality
- Code comment effectiveness
- User guide comprehensiveness
- Technical documentation gaps
- Knowledge transfer adequacy
```

## Comprehensive Analysis Workflow

### Phase 1: Context Assessment
```markdown
1. Parse $ARGUMENTS for domain indicators
2. Determine analysis scope (single/multi-domain)
3. Select appropriate sub-agent combination
4. Initialize analysis framework
```

### Phase 2: Specialist Analysis
```markdown
# Coordinated sub-agent analysis:
For each activated sub-agent:
1. Domain-specific deep analysis
2. Issue identification and categorization
3. Risk assessment and prioritization
4. Recommendation generation
```

### Phase 3: Synthesis and Integration
```markdown
# Main context coordination:
1. Collect all sub-agent findings
2. Identify overlapping concerns
3. Prioritize issues by severity and impact
4. Create unified improvement roadmap
5. Generate comprehensive analysis report
```

## Advanced Analysis Patterns

### Pattern A: Layered Security Analysis
```markdown
# For security-critical systems:
"Auto-activating security-auditor sub-agent for multi-layer analysis:"
1. Application layer security review
2. API and endpoint security assessment  
3. Data layer protection analysis
4. Infrastructure security considerations
5. Compliance and regulatory review
```

### Pattern B: Quality Assurance Pipeline
```markdown
# For comprehensive quality analysis:
"Auto-activating coordinated quality analysis:"
1. code-reviewer: Structure and maintainability
2. test-specialist: Testing adequacy and coverage
3. security-auditor: Security implications
4. refactoring-expert: Performance and scalability
5. Main context: Integration and prioritization
```

### Pattern C: Performance Deep Dive
```markdown
# For performance-critical analysis:
"Auto-activating performance analysis team:"
1. refactoring-expert: Algorithmic and structural optimization
2. code-reviewer: Code-level performance issues
3. test-specialist: Performance testing adequacy
4. Main context: Holistic performance assessment
```

## Analysis Output Framework

### Structured Findings Report
```markdown
# Analysis Report for: $ARGUMENTS

## Executive Summary
- Overall health assessment
- Critical issues requiring immediate attention
- Improvement opportunities

## Domain-Specific Findings

### Security Assessment (security-auditor sub-agent)
- Vulnerability summary
- Risk categorization
- Remediation priorities

### Code Quality Assessment (code-reviewer sub-agent)  
- Maintainability score
- Technical debt identification
- Refactoring recommendations

### Testing Assessment (test-specialist sub-agent)
- Coverage analysis
- Test quality evaluation
- Testing strategy recommendations

## Integrated Recommendations
- Cross-domain improvement opportunities
- Prioritized action items
- Implementation roadmap
```

### Priority Matrix
```markdown
# Issue Prioritization Framework:
HIGH PRIORITY:
- Security vulnerabilities (Critical/High)
- System stability risks
- Performance bottlenecks

MEDIUM PRIORITY:
- Maintainability improvements
- Test coverage gaps
- Documentation deficiencies

LOW PRIORITY:
- Code style inconsistencies
- Minor optimization opportunities
- Enhancement suggestions
```

## Usage Examples

### Comprehensive System Analysis
```markdown
/analyze "Entire e-commerce checkout system"
# Auto-activates: security-auditor + code-reviewer + test-specialist + refactoring-expert
```

### Focused Security Review
```markdown
/analyze "Authentication middleware security"
# Auto-activates: security-auditor (primary) + code-reviewer (supporting)
```

### Performance Investigation
```markdown
/analyze "Database query performance in user dashboard"
# Auto-activates: refactoring-expert (primary) + code-reviewer (supporting)
```

### Quality Assessment
```markdown
/analyze "Code quality in payment processing module"
# Auto-activates: code-reviewer (primary) + test-specialist (supporting)
```

Remember: The analyze command intelligently coordinates specialists to provide comprehensive, actionable insights with minimal manual coordination required.