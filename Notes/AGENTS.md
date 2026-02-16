# NOTES KNOWLEDGE BASE

**Applies to:** `Notes/`

## OVERVIEW
Lecture notes for Algebra 4; compiled from `main.tex` with a shared preamble.

## STRUCTURE
```
Notes/
├── main.tex        # Notes entry point
├── preamble.sty    # Theorem styles, macros, packages
├── chapters/       # Chapter content
├── lectures/       # Lecture drafts (subfiles)
└── figures/        # Figures/assets
```

## WHERE TO LOOK
| Task | Location | Notes |
|------|----------|-------|
| Add or reorder content | `Notes/main.tex` | Inputs chapters and lecture subfiles |
| Lecture draft edits | `Notes/lectures/*.tex` | Subfile format |
| Chapter edits | `Notes/chapters/*.tex` | Main chapter content |
| Theorem styles/macros | `Notes/preamble.sty` | Environments + \cref support |

## CONVENTIONS
- Use `\cref{}` for references.
- Diagrams use `tikz-cd`.
- Lectures are subfiles with `\documentclass[../main.tex]{subfiles}`.

## ANTI-PATTERNS
- Do not edit generated artifacts under `Notes/out/` or `Notes/*/out/`.

## COMMANDS
```bash
cd Notes
latexmk -xelatex main.tex
```
