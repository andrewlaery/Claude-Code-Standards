# Intelligent Troubleshooting Command

Systematically investigate and resolve: $ARGUMENTS

This command provides intelligent problem diagnosis with automatic expert coordination and context-aware investigation strategies.

## Auto-Diagnostic Intelligence

### Problem Classification System
The troubleshoot command automatically classifies issues and activates appropriate specialists:

```markdown
# Automatic Expert Activation Based on Problem Type:
- Runtime errors/exceptions → code-reviewer + test-specialist sub-agents
- Security incidents/breaches → security-auditor sub-agent (priority)
- Performance degradation → refactoring-expert + code-reviewer sub-agents
- Test failures/flaky tests → test-specialist sub-agent (primary)
- Build/deployment issues → code-reviewer + refactoring-expert sub-agents
- Integration failures → test-specialist + security-auditor sub-agents
```

### Context-Aware Investigation
```markdown
# Intelligent routing based on symptoms:
Error Analysis:
- Stack traces → code-reviewer sub-agent for code path analysis
- Authentication errors → security-auditor sub-agent for security review
- Performance metrics → refactoring-expert sub-agent for optimization
- Test reports → test-specialist sub-agent for coverage and quality
```

## Troubleshooting Methodology

### Phase 1: Problem Assessment and Triage
```markdown
1. **Symptom Analysis**: Parse $ARGUMENTS for error patterns and context clues
2. **Severity Classification**: Critical/High/Medium/Low impact assessment
3. **Expert Selection**: Auto-activate appropriate sub-agent specialists
4. **Investigation Scope**: Define boundaries and potential root causes
```

### Phase 2: Systematic Investigation

#### For Runtime/Logic Errors
```markdown
# Auto-activates: code-reviewer + test-specialist sub-agents
"Coordinate systematic error investigation:"

code-reviewer sub-agent tasks:
- Analyze code path leading to error
- Identify potential logic flaws
- Review error handling patterns
- Assess code quality at error point

test-specialist sub-agent tasks:
- Verify test coverage for failing functionality  
- Identify missing edge case tests
- Analyze test data and scenarios
- Create reproduction test cases
```

#### For Security Issues
```markdown
# Auto-activates: security-auditor sub-agent (priority)
"security-auditor sub-agent for comprehensive security investigation:"

Investigation areas:
- Vulnerability assessment at incident point
- Attack vector analysis
- Data exposure evaluation
- Access control verification
- Audit trail examination
- Compliance impact assessment
```

#### For Performance Problems
```markdown
# Auto-activates: refactoring-expert + code-reviewer sub-agents
"Coordinate performance investigation:"

refactoring-expert sub-agent tasks:
- Algorithm efficiency analysis
- Database query optimization review
- Caching strategy evaluation
- Resource utilization assessment

code-reviewer sub-agent tasks:
- Code-level performance bottlenecks
- Memory leak detection
- Inefficient pattern identification
- Optimization opportunities
```

## Advanced Troubleshooting Patterns

### Pattern A: Multi-Layer Investigation
```markdown
# For complex system issues:
"Auto-activating comprehensive investigation team:"

Layer 1 - Application Analysis:
- code-reviewer: Application logic and flow analysis
- test-specialist: Test failure pattern analysis

Layer 2 - Security Assessment:  
- security-auditor: Security implications and vulnerabilities

Layer 3 - Performance Analysis:
- refactoring-expert: System performance and optimization
```

### Pattern B: Root Cause Analysis Chain
```markdown
# Sequential specialist investigation:
1. test-specialist: "Reproduce issue and identify test coverage gaps"
2. code-reviewer: "Analyze code quality and logic at failure point"  
3. security-auditor: "Assess security implications if applicable"
4. refactoring-expert: "Evaluate architectural and performance factors"
5. Main context: "Synthesize findings and create resolution plan"
```

### Pattern C: Parallel Investigation
```markdown
# Simultaneous multi-domain analysis:
Parallel Sub-Agent Tasks:
- code-reviewer: "Analyze code quality and structure issues"
- test-specialist: "Investigate testing gaps and reproduction steps"
- security-auditor: "Evaluate security aspects and vulnerabilities"

Integration Phase:
- Main context: "Correlate findings and identify primary root cause"
```

## Investigation Framework

### Diagnostic Checklist Template
```markdown
# Systematic Issue Analysis for: $ARGUMENTS

## Immediate Assessment
- [ ] Issue classification and severity
- [ ] Affected systems and components
- [ ] Timeline and reproduction steps
- [ ] Initial impact assessment

## Specialist Investigation

### Code Analysis (code-reviewer sub-agent)
- [ ] Code path analysis leading to issue
- [ ] Logic flow verification
- [ ] Error handling adequacy
- [ ] Code quality at failure point

### Testing Analysis (test-specialist sub-agent)
- [ ] Test coverage for affected functionality
- [ ] Reproduction test case creation
- [ ] Edge case identification
- [ ] Test data validation

### Security Analysis (security-auditor sub-agent)
- [ ] Security implications assessment
- [ ] Vulnerability evaluation
- [ ] Access control verification
- [ ] Data exposure risks

### Performance Analysis (refactoring-expert sub-agent)
- [ ] Performance bottleneck identification
- [ ] Resource utilization review
- [ ] Optimization opportunities
- [ ] Scalability considerations
```

### Resolution Planning
```markdown
## Resolution Strategy

### Immediate Actions (Critical Issues)
- [ ] Incident containment measures
- [ ] Emergency fixes or rollbacks
- [ ] Stakeholder notification

### Short-term Resolution
- [ ] Direct issue fix implementation
- [ ] Additional test coverage
- [ ] Security hardening if applicable
- [ ] Performance optimization

### Long-term Prevention
- [ ] Process improvements
- [ ] Architecture enhancements
- [ ] Monitoring and alerting upgrades
- [ ] Documentation updates
```

## Specialized Troubleshooting Scenarios

### Authentication/Authorization Issues
```markdown
# Auto-activates: security-auditor (primary) + code-reviewer (supporting)
"security-auditor sub-agent investigation focus:"
- Token validation and expiration
- Permission and role verification
- Session management analysis
- OAuth/SSO flow validation
- API endpoint security review
```

### Database Performance Issues
```markdown
# Auto-activates: refactoring-expert (primary) + code-reviewer (supporting)  
"refactoring-expert sub-agent investigation focus:"
- Query optimization analysis
- Index effectiveness review
- Connection pooling assessment
- Caching strategy evaluation
- Database schema efficiency
```

### Integration/API Failures
```markdown
# Auto-activates: test-specialist + security-auditor sub-agents
"Coordinated integration failure analysis:"
- test-specialist: API contract validation and testing
- security-auditor: Authentication and authorization in API calls
- Main context: Network, timeout, and configuration analysis
```

### Build/Deployment Issues
```markdown
# Auto-activates: code-reviewer + refactoring-expert sub-agents
"Build system investigation coordination:"
- code-reviewer: Dependency and configuration analysis
- refactoring-expert: Build optimization and architecture review
- Main context: Environment and deployment pipeline analysis
```

## Resolution Validation

### Quality Assurance Process
```markdown
# Post-resolution verification:
1. test-specialist: "Create comprehensive tests for the fix"
2. security-auditor: "Verify security implications of resolution"
3. code-reviewer: "Review fix quality and integration"
4. refactoring-expert: "Assess performance impact of changes"
```

### Prevention Measures
```markdown
# Future issue prevention:
- Enhanced monitoring and alerting
- Improved test coverage and edge cases
- Security hardening measures
- Performance optimization
- Documentation and runbook updates
```

## Usage Examples

### Production Error Investigation
```markdown
/troubleshoot "500 errors in payment processing API"
# Auto-activates: code-reviewer + security-auditor + test-specialist
```

### Security Incident Response
```markdown
/troubleshoot "Unauthorized access detected in admin panel"
# Auto-activates: security-auditor (priority) + code-reviewer
```

### Performance Degradation
```markdown
/troubleshoot "Dashboard loading time increased 300%"
# Auto-activates: refactoring-expert + code-reviewer
```

### Test Suite Failures
```markdown
/troubleshoot "Integration tests failing intermittently"
# Auto-activates: test-specialist (primary) + code-reviewer
```

Remember: The troubleshoot command orchestrates appropriate specialists to systematically identify root causes and implement comprehensive solutions.