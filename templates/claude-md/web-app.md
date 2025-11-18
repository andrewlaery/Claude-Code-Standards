# Project: [YOUR_PROJECT_NAME]

## Core Principles
**IMPORTANT**: Whenever you write code, it MUST follow SOLID design principles. Never write code that violates these principles. If you do, you will be asked to refactor it.

## Rigorous Quality Enforcement
The implementation must strictly adhere to these **non-negotiable principles**:

### DRY (Don't Repeat Yourself)
- **Zero code duplication will be tolerated**
- Each functionality must exist in exactly one place
- No duplicate files or alternative implementations allowed

### KISS (Keep It Simple, Stupid)
- **Implement the simplest solution that works**
- No over-engineering or unnecessary complexity
- Straightforward, maintainable code patterns

### Clean File System
- **All existing files must be either used or removed**
- No orphaned, redundant, or unused files
- Clear, logical organization of the file structure

### Transparent Error Handling
- **No error hiding or fallback mechanisms that mask issues**
- All errors must be properly displayed to the user
- Errors must be clear, actionable, and honest

## Communication Protocol
Use structured command signals for clear AI coordination:
- **[IMPLEMENT]** - Begin implementation of specified feature
- **[REVIEW]** - Conduct comprehensive code review
- **[DEBUG]** - Investigate and resolve specific issue
- **[TEST]** - Create or execute testing procedures
- **[CHECKPOINT]** - Pause for review and validation
- **[RESTORE]** - Restore context from project manifest

## Context Management
Maintain project continuity with:
- **PROJECT_MANIFEST.md** - Comprehensive project status and context (use template from templates/project-management/)
- **Context Markers** - Use `[CONTEXT:START]` and `[CONTEXT:END]` in code
- **Session Restoration** - Use explicit restoration templates when continuing work
- **Decision Documentation** - Record architectural choices and rationale

## Success Criteria
Implementation will be successful **only if**:
- **Zero Duplication**: No duplicate code or files exist in the codebase
- **Single Implementation**: Each feature has exactly one implementation
- **Complete Functionality**: All features work correctly and completely
- **Transparent Operations**: All errors are properly displayed to users
- **Clean Architecture**: Modular, reusable component structure
- **Consistent Standards**: Implementation follows all established guidelines
- **Full Documentation**: Implementation details are properly documented

## Development Workflow
1. Before making any changes, create and checkout a feature branch named `feature-[brief-description]`
2. **[IMPLEMENT]** - Begin implementation following rigorous quality principles
3. Write comprehensive tests for all new functionality
4. **[TEST]** - Execute testing procedures and validate coverage
5. **[REVIEW]** - Conduct code review against quality standards
6. Compile code and run all tests before committing
7. **[CHECKPOINT]** - Pause for validation before commit
8. Write detailed commit messages explaining the changes and rationale
9. Commit all changes to the feature branch

## Communication Protocol
Use structured command signals for clear AI coordination:
- **[IMPLEMENT]** - Begin implementation of specified feature
- **[REVIEW]** - Conduct comprehensive code review
- **[DEBUG]** - Investigate and resolve specific issue
- **[TEST]** - Create or execute testing procedures
- **[CHECKPOINT]** - Pause for review and validation
- **[RESTORE]** - Restore context from project manifest

## Context Management
Maintain project continuity with:
- **PROJECT_MANIFEST.md** - Comprehensive project status and context
- **Context Markers** - Use `[CONTEXT:START]` and `[CONTEXT:END]` in code
- **Session Restoration** - Explicit templates for continuing work
- **Decision Documentation** - Record architectural choices and rationale

## Architecture Overview
- **Frontend**: Next.js 14 with TypeScript and Tailwind CSS
- **State Management**: Zustand for client state, React Query for server state
- **Backend**: Node.js with Express and Prisma ORM
- **Database**: PostgreSQL
- **Testing**: Jest for unit tests, Playwright for E2E

## Code Standards
- Use TypeScript for all new code with strict type checking
- Follow the existing component structure in `/src/components`
- API routes follow RESTful conventions in `/src/pages/api`
- Use Prisma schema definitions for all database operations
- CSS classes should use Tailwind utilities; custom CSS only when necessary

## Quality Gates
- All code must compile without warnings
- Test coverage must remain above 80%
- All tests must pass before committing
- ESLint and Prettier must pass without errors

## File Organization
- Components: `/src/components/[feature]/[ComponentName].tsx`
- Pages: `/src/pages/[route].tsx`
- Utilities: `/src/lib/[category]/[utility].ts`
- Types: `/src/types/[domain].ts`

## Design Principles
- Follow responsive design patterns for mobile-first development
- Use semantic HTML and proper ARIA labels for accessibility
- Implement proper error boundaries and loading states
- Follow the existing design system and component patterns

## Testing Requirements
- Write unit tests for all business logic
- Include integration tests for API endpoints
- Add E2E tests for critical user workflows
- Mock external dependencies appropriately
- Maintain test isolation and repeatability

## Performance Standards
- Optimize bundle size and loading performance
- Implement proper caching strategies
- Use lazy loading for components and routes
- Monitor and optimize Core Web Vitals
- Implement proper error logging and monitoring