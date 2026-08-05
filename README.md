# Project Management Protocol

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.17117785.svg)](https://doi.org/10.5281/zenodo.17117785)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)

**Current version: 4.0**

This document is the official project management protocol for the Netherlands eScience Center. It describes all phases
of a project and the procedures required to successfully complete them.

The scope of this document is the execution of research projects awarded by the eScience Center through calls for
proposals, though other types of projects are also briefly covered. This document gives a detailed description of all
steps, both required and optional, that must or may be taken in the execution of projects, reflecting the so-called
project life cycle. For each step, the document clarifies the responsibilities of the project team members (RSEs) and
other eScience Center employees (e.g. Section Heads, Finance, Management Team) involved in the process.

## Table of Contents

- [Overview](#overview)
- [Repository Structure](#repository-structure)
- [Requirements](#requirements)
- [Installation](#installation)
- [Building the Document](#building-the-document)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgements](#acknowledgments)

## Overview

This document provides a structured approach to project management, covering:
- Project lifecycle
- Roles and responsibilities of the eScience staff
- Workflow and communication around a project

## Repository Structure

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
\usepackage{caption}             % For figure and table captions
\usepackage{cite}                % Citation
\usepackage{amssymb}             % Mathematical symbols
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
\usepackage{fancyhdr}

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

## Building the Document

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

## Contributing

Contributions to the Project Management Protocol are welcome.

The protocol is maintained by the Netherlands eScience Center and reflects its project management practices. While
contributions from eScience Center staff form the primary development workflow, suggestions, corrections, and feedback
from the wider community are also appreciated.

Please read CONTRIBUTING.md⁠￼ before opening an issue or submitting a pull request. It describes the contribution
process, repository workflow, and guidelines for preparing and reviewing changes.

## License

Copyright © 2026 The Netherlands eScience Center.

This work is licensed under [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/).
You are free to share and adapt both the document content and LaTeX source code with appropriate attribution.

## Acknowledgments

Generative AI tools, including OpenAI's ChatGPT (GPT-5.5) and Anthropic's Claude Sonnet 4, were used during the 
development and revision of this Project Management Protocol to assist with drafting, editing, language refinement, 
restructuring, and improving the clarity and consistency of the document and its accompanying repository documentation.
All AI-assisted content has been critically reviewed, verified for correctness and completeness, revised where 
necessary, and approved by the contributors before publication.