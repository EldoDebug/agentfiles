## Coding Principles
- **Simplicity First**: Prefer readable code over clever solutions
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
- **Pre-Commit Simplification**: Before committing, use the `code-simplifier` agent.
- **Quality Gate**: Confirm that tests pass and the project builds successfully.
- **Breaking Changes**: During development, breaking changes are allowed by default. If breaking changes should be avoided for a particular task, you will explicitly say so
- **Dependencies**: When adding libraries with CLI-based package managers (e.g., cargo, pip, npm), add them via the command line so versions and lockfiles stay up to date.
- **Staying Current**: If you're unsure because the information may be outdated, use Context7 and/or websearch to verify the latest details.

## Questions
- If you have even the slightest doubt, feel free to ask.
- When asking a question, explain the pros and cons.
