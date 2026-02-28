---
name: gemini
description: Use Google Gemini CLI to consult, review code, or get AI-assisted coding help. Trigger whenever the user wants to ask Gemini something, have code or a diff reviewed, get suggestions on their codebase, or leverage Gemini as a second opinion. Use proactively when the user mentions "Gemini", "gemini review", "ask Gemini", or wants a second AI perspective on their code.
---

# Gemini CLI Skill

Invoke Google Gemini CLI (`gemini`) from the shell for AI-assisted consultation and code review.

## Default invocation

```bash
gemini -p "<prompt>" --yolo
```

| Flag | Purpose |
|------|---------|
| `-p <text>` | Run non-interactively (headless) and exit on completion |
| `--yolo` | Automatically accept all actions |

## Usage by use case

### General questions and consultation

```bash
gemini -p "Your question here" --yolo
```

### Code review (specific file)

Include the file content in the prompt.

```bash
gemini -p "Review this code and suggest improvements:

$(cat path/to/file.ts)" --yolo
```

### Git diff review

```bash
gemini -p "Review these changes:

$(git diff HEAD)" --yolo
```

### Uncommitted changes review

```bash
gemini -p "Review these uncommitted changes:

$(git diff HEAD && git diff --cached)" --yolo
```

### Codebase-wide questions

Gemini has access to the current directory by default.

```bash
gemini -p "Explain the authentication flow in this repo" --yolo
```

## Output format

Use `-o text` for plain text output (default), or `-o json` for structured JSON output.

```bash
gemini -p "Your question" --yolo -o text
```

## Notes

- `--yolo` automatically accepts all tool actions. Intended for local development environments.
- For a more conservative mode with edit-only auto-approval, use `--approval-mode auto_edit` instead of `--yolo`.
- Gemini CLI requires prior authentication via `gemini` (first launch) or OAuth.
- For large files, extract only the relevant section to improve response quality.

## Steps

1. Understand what the user wants (question, review target, etc.)
2. Read relevant file contents or `git diff` as needed
3. Run `gemini -p "..." --yolo`
4. Present the output to the user and suggest follow-up actions if appropriate
