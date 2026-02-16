# HOMEWORK KNOWLEDGE BASE

**Applies to:** `Homework/`

## OVERVIEW
Homework templates and examples built on the custom `assignment` class.

## STRUCTURE
```
Homework/
├── assignment.cls  # Homework class
├── hw1/            # Example homework
└── figures/        # Homework figures/assets
```

## WHERE TO LOOK
| Task | Location | Notes |
|------|----------|-------|
| Update template styling | `Homework/assignment.cls` | Class and metadata macros |
| Edit a specific homework | `Homework/*/main.tex` | Uses assignment class |
| Bibliography setup | `Homework/*/references.bib` | Example in hw1 |

## CONVENTIONS
- Use `\documentclass{assignment}` for homework documents.
- Set metadata with class macros (`\title`, `\author`, `\studentid`, `\course`, `\lecturer`).

## ANTI-PATTERNS
- Do not edit generated artifacts (e.g., `*.aux`, `*.log`) in homework folders.

## COMMANDS
```bash
cd Homework/hw1
latexmk -pdf main.tex
```
