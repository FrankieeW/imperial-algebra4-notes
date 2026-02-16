# HW1 Agent Guide

**Applies to**: `Homework/hw1/`

This guide is for coding agents working in Homework 1.
It is intentionally scoped to this folder.

## Inheritance and precedence

Use instructions in this order (nearest wins):
1. `Homework/hw1/AGENTS.md` (this file)
2. `Homework/AGENTS.md`
3. repository root `AGENTS.md`

If rules conflict, prefer the nearest file.

## What exists in this folder

Primary source files:
- `Homework/hw1/main.tex`
- `Homework/hw1/references.bib`

Common generated files:
- `Homework/hw1/out/*`
- `Homework/hw1/*.bak*`
- `Homework/hw1/*.log`, `*.aux`, `*.bcf`, `*.run.xml`, `*.synctex*`

Edit source files only unless explicitly asked otherwise.

## External rule files status

At analysis time:
- `.cursor/rules/`: not found
- `.cursorrules`: not found
- `.github/copilot-instructions.md`: not found

If these files appear later, update this guide.

## Build / lint / test model

This repo is LaTeX-first.
There is no Python/JS-style unit-test framework for hw1.
Verification is compile success plus log sanity.

## Canonical commands

Run from `Homework/hw1`.

### Baseline compile
```bash
latexmk -pdf main.tex
```

### Engine-specific compile (from in-file hints)
```bash
latexmk -xelatex -synctex=1 -shell-escape -interaction=nonstopmode -file-line-error -output-directory=out main.tex
```
```bash
latexmk -lualatex -synctex=1 -shell-escape -interaction=nonstopmode -file-line-error -output-directory=out main.tex
```

### Fast fail check (single pass)
```bash
xelatex -interaction=nonstopmode -halt-on-error -file-line-error -output-directory=out main.tex
```

### Clean generated aux files
```bash
latexmk -c -output-directory=out
```

## "Single test" equivalent

There is no single unit-test command.
Use one-document compile as the single-test equivalent.

Recommended loop:
1. Make one focused edit in `main.tex`.
2. Run one compile command.
3. Confirm success and review `out/main.log` for new errors.

Treat this like "run one test".

## Structural facts you must respect

`main.tex` currently uses a shared class path:
```tex
\documentclass[12pt]{\SharedTexPath/cls/assignment}
```

Do not migrate class-loading strategy unless requested.
`Homework/assignment.cls` defines the class contract.
Prefer content edits in `main.tex` over class-level rewrites.

## Code style guidelines

### Document organization
- Keep metadata macros together near the top.
- Keep section hierarchy stable (`\section`, nested lists).
- Keep related math blocks grouped and readable.

### Imports / package policy
- Prefer packages already provided by `assignment.cls`.
- Do not add new packages in `main.tex` unless necessary.
- If adding one, document why in your final summary.

### Formatting
- Match nearby indentation and spacing.
- Avoid reformatting unrelated blocks.
- Keep edits minimal and local to task scope.

### Naming conventions
- Use descriptive labels and macro names.
- Keep naming consistent with existing notation.
- Avoid introducing short opaque command aliases.

### Types and interfaces (LaTeX analog)
- Treat class macros (`\course`, `\lecturer`, etc.) as stable interfaces.
- Do not change macro signatures in class files for hw1 tasks.
- Prefer argument updates over interface redesign.

### References and citations
- Use stable `\label` keys and avoid unnecessary renames.
- If adding citations, ensure matching entries in `references.bib`.
- Keep bibliography keys deterministic and descriptive.

## Error handling expectations

For this repository, error handling means compile discipline:
- Compile after substantive edits.
- Consider fatal compile errors as blockers.
- Resolve newly introduced broken references/citations.
- If failures are pre-existing, report them explicitly.

Minimum evidence before claiming completion:
1. Compile command ran.
2. Output PDF was produced.
3. No new fatal errors in the log.

## Git and change hygiene

- Do not commit generated build artifacts by default.
- Do not edit `out/*` files manually.
- Do not commit backup files (`main.bak*`) unless explicitly requested.
- Keep diffs focused on requested change only.

## Anti-patterns

- Broad style-only rewrites.
- Unrequested class-level refactors.
- Claiming success without compile verification.
- Inventing tooling that does not exist in this repo.

Keep this guide command-driven and hw1-specific.
Update it if repository conventions change.
