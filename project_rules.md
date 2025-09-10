
## Philosophy

## Core philosophy

- **Incremental progress is better than overnight ** - Make small changes that compile and pass tests
- **Learn from existing code** - Research and plan before implementation
- **Pragmatic rather than dogmatic** - Adapt to the realities of the project
- **Clear intent is better than clever code** - Strive for simplicity and straightforwardness


## Simplicity means

- Single responsibility per function/class
- Avoid premature abstraction
- Don't be clever, choose simple and clear solutions
- If you need to explain it, it's too complicated

## Process

## 1. Planning and preparation

If the work is extremely clear and simple it can be implemented without the need for tedious planning, but if the work is more complex it needs to be broken down into 3 - 5 phases and documented in `PLAN.md`:

```
## Stage N: [name].
**Objective**: [Specific Deliverable].
**Success Criteria**: [Testable Results]
**Tests**: [Specific Test Cases]
**Status**: [not started | in progress | completed] 
```
- Update status as progress is made
- Delete `PLAN.md` file when all phases are complete

## 2. Implementation process

1. **Understand** - Study existing patterns in the code base
2. **Test** - write tests first (red)
3. **Implementation** - Minimum amount of code to pass tests (green)
4. **Refactoring** - Organize if tests pass
5. **Commit** - attach clear information related to the plan

## 3. When in trouble (after 3 attempts)

1. **Document what failed**:
   - What you tried
   - Specific error messages
   - Why you think it failed 
2. **Research alternatives**.
   - Find 2 - 3 similar implementations
   - Document the different approaches used 
3. **Problem Basis**:
   - Is this the appropriate level of abstraction?
   - Can this be broken down into smaller problems?
   - Is there a simpler approach at all?
4. **Try different perspectives**:
   - Different library/framework features?
   - Different library/framework features? Different architectural patterns?
   - Should abstractions be removed rather than added?

## 2. Code standards

## Architecture principles

- **Explicit is better than implicit** - Clear data flow and dependencies
- **Adopt test-driven development as much as possible** - Never disable tests, fix them instead

## Code quality

- **Every commit must**:
  - Compile successfully
  - Follow project format/code check rules
- **Before committing**:
  - Run formatter/code check tools
  - Self-review changes
  - Ensure commit message explains "why"

## Error handling

- Fail quickly and give descriptive information
- Include context for debugging
- Handle errors at the appropriate level
- Never silently ignore exceptions

# Decision framework

When there are multiple possible approaches, choose based on the following factors:

- **Testability** - Can I easily test this?
- **Readability** - Will a person 6 months from now be able to understand this?
- **Consistency** - Does this match the project patterns?
- **Simplicity** - Is this the simplest possible solution?
- **Reversibility** - How difficult will it be to change in the future?

# Project integration

## Learning the code base

- Identify 3 similar features/components
- Recognize common patterns and conventions
- Use the same libraries/tools where possible
- Follow existing test patterns

## Tools

- Use the project's existing build system
- Use the project's testing framework
- Set up the project's formatter/code check tools
- Do not introduce new tools without a good reason

# Code standards

## Development specification

### Code structure

- Business modules follow a consistent structure:：
  ```
  modules/{module-name}/
  ├── components/    # Module-specific components
  ├── services/      # Module service abstractions
  ├── hooks/         # Custom React hooks
  ├── utils/         # Utility functions
  ├── constants.ts   # Module constants
  └── types.ts       # TypeScript type definitions
  ```

### File naming

- All files must use **2 spaces** for indentation
- File names should use `kebab-case` format
- React component file names should match the component name in `kebab-case` format

### Naming conventions

- Variables/functions should use camelCase format
- Classes/interfaces/enums/generic parameters should use PascalCase format
- React components should use PascalCase format
- Constants should use UPPER_SNAKE_CASE format
- CSS class name selectors should use kebab-case format
- Boolean variables should use `is/has/should` prefix
- Event handlers should use `handle` prefix + [element name] + event verb
- React component event attributes should use `on` prefix + [element name] + event verb

### TypeScript conventions

- Strict TypeScript, no use of `any` type
- React component props interface names should be `I{ComponentName}Props`
- Use `import type` for type imports when only used for typing
- Explicit type assertions must use `as` syntax

### React patterns

- Use function components, with each file containing only one React component
- Component props must have an interface or type declaration, named `[ComponentName]Props`
- Component style files must use the same name as the component file, with a `.module.scss` suffix
- `useCallback`/`useEffect`/`useMemo` must explicitly declare all external dependencies


# Important Reminder

## Don't

- Use `--no-verify` to bypass commit hooks
- Commit code that cannot be compiled
- Do actions unrelated to the task

## Must

- Try not to have too many comments, keep only the necessary ones
- Submit running code incrementally
- Update the plan document during the progress
- Learn patterns from existing code implementations
- Stop and re-evaluate after 3 failed attempts
