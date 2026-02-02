# PROJECT KNOWLEDGE BASE

**Course:** Algebra 4
**Code:** MATH70062
**Term:** Spring 2025

## OVERVIEW

Imperial College MSc course notes and homework.

## STRUCTURE

```
Algebra4/
├── Notes/
│   ├── main.tex          # Main lecture notes
│   ├── preamble.sty      # Shared style
│   ├── chapters/         # Chapter files
│   └── figures/          # Diagrams
└── Homework/
    ├── assignment.cls    # Homework template class
    ├── figures/          # Imperial logo
    └── hw1/              # Individual assignments
```

## LECTURER

- **Name**: TBD
- **Office Hours**: TBD

## SYLLABUS

TBD - Add topics as course progresses

## CONVENTIONS

- Theorem environments: theorem, lemma, proposition, corollary, definition, example, remark
- References: Use `\cref{}` (cleveref)
- Diagrams: tikz-cd for commutative diagrams

## COMMANDS

```bash
# Compile notes
cd Notes && latexmk -pdf main.tex

# Compile homework
cd Homework/hw1 && latexmk -pdf main.tex
```
