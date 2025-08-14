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
3. **Consider Sub-Agent Delegation**: For complex reviews, consider using specialized sub-agents:
   - Use `code-reviewer` sub-agent for comprehensive quality analysis
   - Use `security-auditor` sub-agent for security-focused review
   - Use `refactoring-expert` sub-agent for structural improvement suggestions
4. **Third**: Create detailed critique covering:
   - Code structure and organization
   - Adherence to established patterns
   - Performance considerations
   - Security implications
   - Maintainability concerns
   - Test coverage gaps

## Sub-Agent Integration Options
- **Standard Review**: Use main context for straightforward code review
- **Comprehensive Analysis**: `"Use the code-reviewer sub-agent to analyze $ARGUMENTS"`
- **Security Focus**: `"Have the security-auditor sub-agent review $ARGUMENTS for vulnerabilities"`
- **Refactoring Suggestions**: `"Ask the refactoring-expert sub-agent to improve $ARGUMENTS structure"`

## Output Requirements
- Save review as `ai-code-reviews/{filename}.review.md` for each file reviewed
- Include specific line references for issues
- Provide concrete suggestions for improvements
- Rate overall quality: Excellent/Good/Needs Improvement/Poor
- Estimate refactoring effort: Low/Medium/High

## Review Checklist
- Follows project naming conventions
- Proper error handling implemented
- No hardcoded values, secrets, or magic numbers
- Appropriate comments and documentation
- Follows existing design principles and consistent with exemplars
- No obvious security vulnerabilities
- Performance optimizations considered

## Review Format
For each file reviewed, provide:

### File: [filename]
**Quality Rating**: [rating]
**Refactoring Effort**: [effort level]

#### Strengths
- [List positive aspects]

#### Issues Found
- **Line X**: [specific issue with explanation]
- **Line Y**: [specific issue with explanation]

#### Recommendations
- [Concrete improvement suggestions]
- [Performance optimizations]
- [Security considerations]

#### Example Improvements
```[language]
// Before (problematic)
[problematic code]

// After (improved)
[improved code]
```