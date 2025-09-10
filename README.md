# Project Management Protocol 

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.XXXXXX.svg)](https://doi.org/10.5281/zenodo.XXXXXX)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)

**Current version: 3.5**

A project management protocol of the Netherlands eScience Center. This is a document providing guidelines, best practices, and standardized procedures for effective project execution of the eScience projects.

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
- Team roles and responsibilities
- Communication workflow

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
├── LICENSE                 # License file
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

The document includes automatic highlighting for key roles such as:
- **Lead RSE** (Research Software Engineer)
- **PM** (Programme Manager)  
- **TL** (Technical Lead)

## See Also

* [Advice for writing LaTeX documents](https://github.com/dspinellis/latex-advice)
* [LaTeX Project Official Documentation](https://www.latex-project.org/help/documentation/)
* [XeLaTeX Guide](https://www.overleaf.com/learn/latex/XeLaTeX)
* [Bibliography management with biblatex](https://www.overleaf.com/learn/latex/Bibliography_management_with_biblatex)
