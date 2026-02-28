---
name: copilot-cli
description: Use GitHub Copilot CLI to consult, review code, or get AI-assisted coding help. Trigger whenever the user wants to ask Copilot something, have code or a diff reviewed, get suggestions on their codebase, or leverage Copilot as a second opinion. Use proactively when the user mentions "Copilot", "copilot review", "ask Copilot", or wants a second AI perspective on their code.
---

# Copilot CLI Skill

Invoke GitHub Copilot CLI (`copilot`) from the shell for AI-assisted consultation and code review.

## Default invocation

```bash
copilot -p "<prompt>" --yolo --silent
```

| Flag | Purpose |
|------|---------|
| `-p <text>` | Run prompt non-interactively and exit on completion |
| `--yolo` | Enable all permissions (file edits, shell commands, URL access) |
| `-s` / `--silent` | Output only the agent response — no stats or headers |

## Usage by use case

### General questions and consultation

```bash
copilot -p "Your question here" --yolo --silent
```

### Code review (specific file)

Include the file content in the prompt.

```bash
copilot -p "Review this code and suggest improvements:\n\n$(cat path/to/file.ts)" --yolo --silent
```

### Git diff review

```bash
copilot -p "Review these changes:\n\n$(git diff HEAD)" --yolo --silent
```

### Codebase-wide questions

Copilot has access to the current directory by default.

```bash
copilot -p "Explain the authentication flow in this repo" --yolo --silent
```

## Handling output

With `--silent`, only the Copilot response body is written to stdout. Present this output directly to the user.

## Notes

- `--yolo` is intended for local development environments. In shared or production environments, prefer scoped permissions via `--allow-tool` and `--allow-url`.
- For large files, extract only the relevant section to improve response quality.
- Copilot CLI requires prior authentication via `copilot login`.

## Steps

1. Understand what the user wants (question, review target, etc.)
2. Read relevant file contents or `git diff` as needed
3. Run `copilot -p "..." --yolo --silent`
4. Present the output to the user and suggest follow-up actions if appropriate
