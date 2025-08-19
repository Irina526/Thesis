# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a LaTeX PhD thesis template formatted for Princeton University's Graduate School requirements. The template follows Princeton's dissertation formatting guidelines including:

- Double-spaced main text with specific page numbering
- Title page, copyright page, abstract, acknowledgements, and table of contents
- Support for figures, tables, algorithms, and mathematical content
- Custom mathematical notation and theorem environments

## Architecture

The project consists of several key LaTeX files:

- `main.tex` - Main document that orchestrates the entire thesis structure
- `definitions.tex` - Mathematical notation, custom commands, and theorem environments
- `chapter1.tex`, `chapter2.tex` - Individual chapter files (template examples)
- Template includes space for additional chapters and appendices

The main document uses a two-part structure with `\frontmatter` (unpaginated title/copyright) and `\mainmatter` (paginated content starting from page 3).

## Common Commands

### Building the Document
```bash
pdflatex main.tex
```

For documents with bibliographies or cross-references, run multiple times:
```bash
pdflatex main.tex
bibtex main
pdflatex main.tex  
pdflatex main.tex
```

### Cleaning Build Files
```bash
rm -f *.aux *.log *.bbl *.blg *.toc *.lof *.lot *.out *.fdb_latexmk *.fls *.synctex.gz
```

## Key Features

- **Mathematical Notation**: Extensive custom commands in `definitions.tex` for optimization, machine learning, and mathematical concepts
- **Cross-references**: Uses `\label` and `\ref`/`\eqref` for internal references between chapters
- **Princeton Formatting**: Follows Graduate School requirements for margins, spacing, and front matter
- **Modular Structure**: Each chapter is a separate `.tex` file included via `\include`
- **Theorem Environments**: Pre-configured theorem, lemma, definition, and example environments

## File Organization

When adding new chapters:
1. Create new `.tex` file (e.g., `chapter3.tex`)  
2. Add `\include{chapter3}` to `main.tex`
3. Use `\chapter{Title}` and `\label{chap:shortname}` at the start

When adding mathematical content, leverage existing commands in `definitions.tex` or add new ones following the established patterns.