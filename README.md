# PhD Thesis Template

A cookiecutter template for LaTeX PhD theses formatted for Princeton University's Graduate School requirements.

## Usage

1. Install cookiecutter (see [installation guide](https://cookiecutter.readthedocs.io/en/stable/installation.html))
2. Generate your thesis project:
   ```bash
   cookiecutter path/to/this/template
   ```
3. Fill in the prompted information (thesis title, author name, etc.)
4. Build your thesis:
   ```bash
   cd your_project_directory
   latexmk -pdf your_file_name.tex
   ```

## Features

- Princeton University formatting compliance
- Customizable filename for main LaTeX document
- Mathematical notation and theorem environments
- Example figures, tables, and plots with CSV data
- Bibliography with sample references
- Modular chapter structure
- Comprehensive .gitignore for LaTeX projects

## Template Structure

- `{{cookiecutter.file_name}}.tex` - Main thesis document
- `chapter*.tex` - Individual chapter files
- `definitions.tex` - Mathematical notation and custom commands
- `references.bib` - Bibliography with sample references
- `data/` - Sample CSV files for tables and plots
- `figures/` - Directory for images and figures
- `appendix.tex` - Appendix template