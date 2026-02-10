## Coding Principles
- **Simplicity First**: Prefer readable code over clever solutions
- **User-Friendly & Readable**: Aim for user-friendly, human-readable code and thoughtful design
- **DRY**: Extract common logic, avoid premature abstraction
- **YAGNI**: Implement only what's needed now
- **Single Responsibility**: One function/module does one thing well
- **Fail Fast**: Validate early, return early, error explicitly
- **Explicit over Implicit**: No hidden side effects or magic

## Module Boundaries
- Avoid mixing concerns in a single file/module (SRP violations).
- Keep module/file responsibilities cohesive and split them when concerns start to diverge.

## Comments
- Code should be self-documenting
- Comment "why", not "what"
- No obvious comments

## Development Workflow
- **Full Implementation**: Deliver a complete implementation, not an MVP.
- **Git Commits**: Follow **Conventional Commits** and write commit messages in English.
- **Quality Gate**: Confirm that tests pass and the project builds successfully.
- **Breaking Changes**: During development, breaking changes are allowed by default. If breaking changes should be avoided for a particular task, you will explicitly say so
- **Dependencies**: When adding libraries with CLI-based package managers (e.g., cargo, pip, npm), add them via the command line so versions and lockfiles stay up to date.
- **Staying Current**: If you're unsure because the information may be outdated, use Context7 and/or websearch to verify the latest details.

## Questions
- When in plan mode and there is no existing code, propose multiple API designs, explain pros and cons, and ask questions before implementation.
- If you have even the slightest doubt, feel free to ask.
- When asking a question, explain the pros and cons.

## Sub Agents
- **Usage Policy**: Use sub agents proactively whenever they can improve speed, clarity, or task parallelization.
- **Execution Principle**: If a task can be split into clear sub-problems, delegate early and in parallel where reasonable.

## Response Language
Please respond in Japanese
