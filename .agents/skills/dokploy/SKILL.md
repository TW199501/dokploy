```markdown
# dokploy Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches the core development patterns and conventions used in the `dokploy` TypeScript codebase. You'll learn about file naming, import/export styles, commit message conventions, and how to write and run tests. While no specific workflows or frameworks are detected, this guide provides best practices and useful commands to streamline your development process.

## Coding Conventions

### File Naming
- Use **camelCase** for file names.
  - Example: `deployManager.ts`, `userConfig.test.ts`

### Import Style
- Use **relative imports** for modules within the project.
  - Example:
    ```typescript
    import { deployApp } from './deployManager';
    ```

### Export Style
- Use **named exports** rather than default exports.
  - Example:
    ```typescript
    // In deployManager.ts
    export function deployApp() { ... }

    // In another file
    import { deployApp } from './deployManager';
    ```

### Commit Messages
- Follow **conventional commit** format.
- Use the `chore` prefix for routine changes.
  - Example:
    ```
    chore: update dependencies and fix minor issues
    ```

## Workflows

### Commit Changes
**Trigger:** When you make code changes and are ready to commit.
**Command:** `/commit-changes`

1. Stage your changes:
    ```
    git add .
    ```
2. Write a conventional commit message, typically with the `chore` prefix:
    ```
    git commit -m "chore: describe your change"
    ```
3. Push your changes:
    ```
    git push
    ```

### Write and Run Tests
**Trigger:** When you add new features or fix bugs.
**Command:** `/run-tests`

1. Create a test file using the pattern: `*.test.ts`
    - Example: `deployManager.test.ts`
2. Write your tests (framework is unknown; adapt to your preferred test runner).
3. Run your test suite using your chosen test command (e.g., `npm test` or `yarn test`).

## Testing Patterns

- Test files follow the pattern: `*.test.ts`
- Place test files alongside the modules they test or in a dedicated test directory.
- The specific testing framework is not detected; ensure consistency across the codebase.
- Example test file:
    ```typescript
    // deployManager.test.ts
    import { deployApp } from './deployManager';

    describe('deployApp', () => {
      it('should deploy without errors', () => {
        expect(() => deployApp()).not.toThrow();
      });
    });
    ```

## Commands
| Command         | Purpose                                   |
|-----------------|-------------------------------------------|
| /commit-changes | Guide for staging, committing, and pushing changes using conventional commits |
| /run-tests      | Steps to write and run tests              |
```
