# Project Management Protocol 

[![DOI](https://zenodo.org/badge/DOI/10.XXXX/zenodo.XXXXXX.svg)](https://doi.org/10.XXXX/zenodo.XXXXXX)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)

**Current version: 3.5**

This document is the official project management protocol for the Netherlands eScience Center. It describes all phases
of a project and the procedures required to successfully complete them.

The scope of this document is the execution of research projects awarded by the eScience Center through calls for
proposals, though other types of projects are also briefly covered. This document gives a detailed description of all
steps, both required and optional, that must or may be taken in the execution of projects, reflecting the so-called
project life cycle. For each step, the document clarifies the responsibilities of the project team members (RSEs) and
other eScience Center employees (e.g. Programme Managers, Finance, Directors Team) involved in the process.

## Table of Contents

- [Overview](#overview)
- [Requirements](#requirements)
- [Installation](#installation)
- [Compiling the Document](#compiling-the-document)
- [Project Structure](#project-structure)
- [Customization](#customization)
- [See Also](#see-also)

## Overview

This document provides a structured approach to project management, covering:
- Project lifecycle management
- Roles and responsibilities of the eScience staff
- Project workflow and communication around it

## Requirements

### Software Dependencies

- **XeLaTeX** (part of TeX Live 2020 or newer recommended)
- **BibTeX** for bibliography management
- **makeindex** for generating the index

### LaTeX Packages

The following packages are required:

```latex
% Page layout and geometry
\usepackage[a4paper,margin=1in,marginparsep=0pt,marginparwidth=0pt]{geometry}

% Graphics and images
\usepackage[xetex]{graphicx}     % Required for inserting images
\usepackage{eso-pic}             % For logos in the background
\usepackage{tikz}                % Drawing and graphics
\usepackage{subcaption}          % Subfigures and subcaptions

% Fonts and typography
\usepackage{fontspec}            % Use of custom fonts
\usepackage{pifont}              % Special symbols and fonts

% Language and localization
\usepackage[dutch,english]{babel} % Multi-language support

% Colors
\usepackage{xcolor}              % Color definitions and usage

% Tables
\usepackage{tabularray}          % Advanced table formatting
\usepackage{ltablex}             % Extended tabular environments
\usepackage{booktabs}            % Professional table formatting
\usepackage{caption}             % Caption customization

% Lists and sections
\usepackage{enumitem}            % Itemize list customization
\usepackage{titlesec}            % Customize look & feel of sections

% Index and references
\usepackage{imakeidx}            % Creating index (load before hyperref)
\usepackage[colorlinks=true,hyperfootnotes=true]{hyperref} % Hyperlinks
\usepackage{xesearch}            % Automatic term searching and highlighting

% Table of contents and appendices
\usepackage[nottoc,notlof,notlot]{tocbibind} % Control TOC entries
\usepackage[title]{appendix}     % Appendix formatting

% Utilities
\usepackage{url}                 % URL formatting
```

### Fonts

- The document uses specific open fonts (Assistant and Nunito) that should be available on your system
- Default fallback fonts are configured if custom fonts are unavailable

## Installation

### Quick Start

1. **Install a complete TeX distribution**:
   ```bash
   # Ubuntu/Debian
   sudo apt-get install texlive-full
   
   # macOS with Homebrew
   brew install --cask mactex
   
   # Windows: Download TeX Live from https://tug.org/texlive/
   ```

2. **Clone this repository**:
   ```bash
   git clone https://github.com/nlescpm/PMP.git
   cd PMP
   ```

3. **Compile the document** (see below)

## Compiling the Document

### Standard Compilation

Run these commands in sequence for a complete build:

```bash
xelatex main.tex 
bibtex main
makeindex main.idx  # if using index
xelatex main.tex 
xelatex main.tex    # final run to resolve all references
```

### Using latexmk (Recommended)

For automated compilation with dependency tracking:

```bash
latexmk -xelatex -interaction=nonstopmode main.tex
```

### Clean Build

To remove auxiliary files:

```bash
latexmk -c
# or manually remove: *.aux *.log *.out *.toc *.bbl *.blg *.idx *.ind *.ilg
```

## Project Structure

```
PMP/
├── main.tex                 # Main document file
├── macros.tex               # Macros file
├── packages.tex             # Packages file
├── references.bib           # Bibliography database
├── tex/                     # Individual sections
│   ├── intro.tex
│   ├── execution.tex
│   └── ...
├── img/                    # Images and figures
├── font/                   # Custom fonts (if any)
├── CITATION.cff            # Citation metadata
├── CONTRIBUTING.md         # Contributing guidelines
├── LICENSE                 # CC BY 4.0 license text
├── .gitattributes          # Git export settings
└── README.md               # This file
```

## Customization

### Adding Content

- **New sections**: Add `.tex` files to the `tex/` directory and include them in `main.tex` with `\input`
- **Images**: Place figures in the `img/` directory
- **Bibliography**: Add references to `references.bib`

### Styling

- **Colors**: Modify color definitions in the preamble
- **Fonts**: Update font specifications in the fontspec configuration
- **Layout**: Adjust page geometry and spacing parameters

### Role Highlighting

The document includes automatic highlighting for key eScience project roles:

- **Lead RSE** (Research Software Engineer)
- **PM** (Programme Manager)
- **TL** (Technical Lead)

## See Also

* [Advice for writing LaTeX documents](https://github.com/dspinellis/latex-advice)
* [LaTeX Project Official Documentation](https://www.latex-project.org/help/documentation/)
* [XeLaTeX Guide](https://www.overleaf.com/learn/latex/XeLaTeX)
* [Bibliography management with biblatex](https://www.overleaf.com/learn/latex/Bibliography_management_with_biblatex)

## License

Copyright © 2025 R. Bakhshi, J. Attema, N. Drost, P. Lopez-Tarifa, C. Bos, J. Maassen, R. van Nieuwpoort, C. Martinez-Ortiz and the Netherlands eScience Center.

This work is licensed under [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/).
You are free to share and adapt both the document content and LaTeX source code with appropriate attribution.


## Acknowledgments
Some LaTeX macros were adapted from examples in a respective LaTeX package documentation.

The README and CONTRIBUTING markdowns have been partially generated using Claude Sonnet 4 (version claude-sonnet-4-20250514). All AI-output has been refined, verified for correctness, accuracy and completeness, adapted where needed, and approved by the contributors of this repository.
