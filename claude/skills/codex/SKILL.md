---
name: codex
description: Use OpenAI Codex CLI to consult, review code, or get AI-assisted coding help. Trigger whenever the user wants to ask Codex something, have code or a diff reviewed, get suggestions on their codebase, or leverage Codex as a second opinion. Use proactively when the user mentions "Codex", "codex review", "ask Codex", or wants a second AI perspective on their code.
---

# Codex CLI Skill

Invoke OpenAI Codex CLI (`codex`) from the shell for AI-assisted consultation and code review.

## Default invocation (general questions)

```bash
codex exec "<prompt>" --full-auto -o /dev/stdout
```

| Flag | Purpose |
|------|---------|
| `exec` | Run Codex non-interactively |
| `--full-auto` | Low-friction sandboxed execution (`-a on-request --sandbox workspace-write`) |
| `-o /dev/stdout` | Write the agent's last message to stdout |

## Usage by use case

### General questions and consultation

```bash
codex exec "Your question here" --full-auto -o /dev/stdout
```

### Code review — uncommitted changes (staged + unstaged + untracked)

```bash
codex review --uncommitted
```

### Code review — changes since a base branch

```bash
codex review --base main
```

### Code review — a specific commit

```bash
codex review --commit <SHA>
```

### Code review with custom instructions

```bash
codex review --uncommitted "Focus on security issues and error handling"
```

### File content review

Include the file content in the prompt.

```bash
codex exec "Review this code and suggest improvements:

$(cat path/to/file.ts)" --full-auto -o /dev/stdout
```

### Git diff review

```bash
codex exec "Review these changes:

$(git diff HEAD)" --full-auto -o /dev/stdout
```

### Codebase-wide questions

Codex has access to the current directory by default.

```bash
codex exec "Explain the authentication flow in this repo" --full-auto -o /dev/stdout
```

## Handling output

- `codex review` outputs formatted review results directly to the terminal.
- `codex exec ... -o /dev/stdout` writes the agent's final response to stdout. Present this output directly to the user.

## Notes

- `--full-auto` enables sandboxed execution with `workspace-write` access. Safe for local development.
- For read-only consultation (no file writes needed), use `--sandbox read-only` instead of `--full-auto`.
- Codex CLI requires prior authentication. Run `codex login` if not yet authenticated.
- For large files, extract only the relevant section to improve response quality.

## Steps

1. Understand what the user wants (question, review target, etc.)
2. Choose the right subcommand: `codex review` for git-based reviews, `codex exec` for questions and custom prompts
3. Read relevant file contents or `git diff` as needed for `exec` prompts
4. Run the appropriate command and capture the output
5. Present the output to the user and suggest follow-up actions if appropriate
