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

- `{{cookiecutter.file_name}}.tex` - Main document that orchestrates the entire thesis structure (customizable filename)
- `definitions.tex` - Mathematical notation, custom commands, and theorem environments
- `chapter1.tex`, `chapter2.tex` - Individual chapter files (template examples)
- Template includes space for additional chapters and appendices

The main document uses a two-part structure with `\frontmatter` (unpaginated title/copyright) and `\mainmatter` (paginated content starting from page 3).

## Common Commands

### Building the Document
Recommended approach using latexmk (handles bibliography and cross-references automatically):
```bash
latexmk -pdf {{cookiecutter.file_name}}.tex
```

Alternative manual approach:
```bash
pdflatex {{cookiecutter.file_name}}.tex
bibtex {{cookiecutter.file_name}}
pdflatex {{cookiecutter.file_name}}.tex  
pdflatex {{cookiecutter.file_name}}.tex
```

### Cleaning Build Files
Using latexmk:
```bash
latexmk -c  # Clean auxiliary files
latexmk -C  # Clean all generated files including PDF
```

Manual cleanup:
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
2. Add `\include{chapter3}` to `{{cookiecutter.file_name}}.tex`
3. Use `\chapter{Title}` and `\label{chap:shortname}` at the start

When adding mathematical content, leverage existing commands in `definitions.tex` or add new ones following the established patterns.