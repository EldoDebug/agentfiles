## Coding Principles
- **Simplicity First**: Prefer readable code over clever solutions
- **KISS Principle**: Keep solutions as simple as possible and avoid unnecessary complexity
- **User-Friendly & Readable**: Aim for user-friendly, human-readable code and thoughtful design
- **DRY**: Extract common logic, avoid premature abstraction
- **YAGNI**: Implement only what's needed now
- **Single Responsibility**: One function/module does one thing well
- **Fail Fast**: Validate early, return early, error explicitly
- **Explicit over Implicit**: No hidden side effects or magic

## Comments
- Code should be self-documenting
- Comment "why", not "what"
- No obvious comments

## Development Workflow
- **Full Implementation**: Deliver a complete implementation, not an MVP.
- **Git Commits**: Follow **Conventional Commits** and write commit messages in English.
- **When Stuck**: If stuck during implementation, consult `copilot-cli` skill for guidance.
- **Post-Implementation Review**: After completing a medium-to-large implementation:
  1. Run `code-simplifier`
  2. Run `copilot-cli` skill to review the changes (instruct Copilot to run `git diff` itself and ask for a code review)
  3. Fix any critical or moderate issues found, then repeat from step 2 until none remain
- **Minor Fixes**: Skip `code-simplifier` and `copilot-cli` review for small changes (a few lines) after the main implementation is complete.
- **Quality Gate**: Confirm that tests pass and the project builds successfully.
- **Breaking Changes**: During development, breaking changes are allowed by default. If breaking changes should be avoided for a particular task, you will explicitly say so
- **Dependencies**: When adding libraries with CLI-based package managers (e.g., cargo, pip, npm), add them via the command line so versions and lockfiles stay up to date.
- **Staying Current**: If you're unsure because the information may be outdated, use Context7 and/or websearch to verify the latest details.

## Questions
- If you have even the slightest doubt, feel free to ask.
- When asking a question, explain the pros and cons.
