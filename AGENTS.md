# PROJECT KNOWLEDGE BASE

**Generated:** 2026-02-03 16:32 GMT
**Commit:** 558bcb3
**Branch:** main

## OVERVIEW
LaTeX lecture notes and homework templates for MATH70062 Algebra 4 (Imperial College London).

## STRUCTURE
```
Algebra4/
├── Notes/              # Lecture notes (LaTeX)
│   ├── main.tex        # Notes entry point
│   ├── preamble.sty    # Theorem styles, macros, packages
│   ├── chapters/       # Chapter content
│   ├── lectures/       # Lecture drafts
│   └── figures/        # Figures/assets
└── Homework/           # Homework templates
    ├── assignment.cls  # Homework class
    ├── hw1/            # Example homework
    └── figures/        # Homework figures/assets
```

## WHERE TO LOOK
| Task | Location | Notes |
|------|----------|-------|
| Notes entry point | `Notes/main.tex` | Inputs chapters and lectures |
| Lecture draft | `Notes/lectures/le-temp.tex` | Subfile used by notes |
| Theorem styles/macros | `Notes/preamble.sty` | Environments + \cref support |
| Homework template | `Homework/assignment.cls` | Class used by homework |
| Homework example | `Homework/hw1/main.tex` | Uses assignment class |

## CONVENTIONS
- Theorem environments: theorem, lemma, proposition, corollary, definition, example, remark, notation.
- Use `\cref{}` for references.
- Commutative diagrams use `tikz-cd`.

## UNIQUE STYLES
- Notes use `fontspec` and set monospaced font to `FreeMono`.
- Lectures often live as subfiles under `Notes/lectures/`.

## COMMANDS
```bash
cd Notes
latexmk -xelatex main.tex

cd Homework/hw1
latexmk -pdf main.tex
```

## NOTES
- Build artifacts (e.g., `out/`, `*.aux`, `*.log`) are present in the repo; avoid editing generated files.
- Nearest `AGENTS.md` wins; see `Notes/AGENTS.md` and `Homework/AGENTS.md` for sub-area guidance.
