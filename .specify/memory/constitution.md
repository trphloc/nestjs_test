<!--
Sync Impact Report (Constitution v1.0.0)
========================================
Version Change: Template → 1.0.0
Reason: Initial constitution ratification for AI Agent Sandbox (NestJS)

Modified Principles:
- PROJECT_NAME: [placeholder] → AI Agent Sandbox (NestJS)
- Added 5 core principles tailored to sandbox/testing environment
- Added Development Workflow section
- Added Governance rules

Template Sync Status:
✅ plan-template.md - Constitution Check section aligns with principles
✅ spec-template.md - Requirements structure supports constitution gates
✅ tasks-template.md - Task categorization reflects test-driven approach

Follow-up TODOs: None
-->

# AI Agent Sandbox (NestJS) Constitution

## Core Principles

### I. Test-First Development (NON-NEGOTIABLE)

Tests MUST be written before implementation. For any new feature or bug fix:
- Write tests that capture expected behavior
- Verify tests FAIL before implementation
- Implement until tests PASS
- Refactor while keeping tests green

**Rationale**: This is a sandbox for testing AI coding agents. Test-first ensures agents produce verifiable, correct code and provides clear success criteria.

### II. Simplicity & Minimal Dependencies

Keep the codebase simple and dependencies minimal:
- Use built-in NestJS features before adding external libraries
- Each new dependency MUST be justified in PR description
- Prefer standard Node.js/TypeScript patterns over framework-specific magic
- Follow YAGNI (You Aren't Gonna Need It) principle

**Rationale**: A clean, simple codebase is easier for AI agents to understand, modify, and test. Fewer dependencies reduce cognitive load and potential conflicts.

### III. Code Quality Gates

All code MUST pass quality gates before merge:
- Linting: `npm run lint` exits with 0
- Formatting: `npm run format` produces no changes
- Unit tests: `npm test` passes with no failures
- E2E tests: `npm run test:e2e` passes with no failures
- Build: `npm run build` completes successfully

**Rationale**: Automated quality checks ensure consistent code quality and prevent regressions, especially important when AI agents make changes.

### IV. Clear Module Boundaries

Features MUST follow NestJS module structure:
- Each feature gets its own module with clear responsibilities
- Controllers handle HTTP concerns only
- Services contain business logic
- DTOs define explicit input/output contracts
- Modules MUST be independently testable

**Rationale**: Clear boundaries make it easier for agents to understand where to add code and reduce unintended side effects.

### V. Documentation & Examples

Code changes MUST include appropriate documentation:
- Public APIs require JSDoc comments
- Complex logic requires inline comments explaining "why"
- New features update README.md with usage examples
- Environment variables documented in README.md

**Rationale**: AI agents and human developers both benefit from clear documentation. Examples provide concrete patterns to follow.

## Development Workflow

### Feature Implementation Process

1. **Specification**: Create spec in `.specify/` if using structured workflow
2. **Tests**: Write failing tests for the feature
3. **Implementation**: Write minimal code to pass tests
4. **Quality Gates**: Run linting, formatting, all tests
5. **Documentation**: Update README and add code comments
6. **Validation**: Manually test the running application

### Branch Naming

For structured features: `###-feature-name` (where ### is feature number)
For quick changes: descriptive kebab-case names

### Commit Messages

Follow conventional commits format:
- `feat:` for new features
- `fix:` for bug fixes
- `test:` for test-only changes
- `docs:` for documentation
- `refactor:` for code improvements without behavior change
- `chore:` for build/tooling updates

## Technology Constraints

### Required Stack

- **Runtime**: Node.js 18+ (recommend 20+)
- **Framework**: NestJS 11.x
- **Language**: TypeScript 5.x
- **Testing**: Jest (built-in with NestJS)
- **Linting**: ESLint with TypeScript support
- **Formatting**: Prettier

### Prohibited Additions

- No alternative test frameworks (stick with Jest)
- No alternative HTTP frameworks (stick with Express via NestJS)
- No global state or singletons outside NestJS DI
- No database until explicitly needed for a feature

## Governance

### Constitution Authority

This constitution is the source of truth for project practices. All code changes, PR reviews, and feature planning MUST align with these principles.

### Amendment Process

Constitution changes require:
1. Proposed change documented with rationale
2. Version bump following semantic versioning:
   - MAJOR: Breaking governance changes (removing/redefining principles)
   - MINOR: New principles or expanded guidance
   - PATCH: Clarifications, wording, typo fixes
3. Update to LAST_AMENDED_DATE
4. Sync check across all `.specify/templates/*.md` files

### Compliance Review

Before merging any PR:
- Verify all quality gates pass
- Confirm tests were written before implementation
- Check documentation is updated
- Validate no unnecessary dependencies added

Complexity that violates principles MUST be explicitly justified in PR description with explanation of why simpler alternatives were insufficient.

**Version**: 1.0.0 | **Ratified**: 2025-11-06 | **Last Amended**: 2025-11-06
