# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a LaTeX template for experimental reports at Xidian University (XDU). The template is specifically designed for the School of Electronic Engineering but can be adapted for other departments.

## Key Commands

### Compilation
- `xelatex main.tex` - Compile the main document
- `bibtex main` - Process bibliography
- Complete compilation sequence: `xelatex main.tex` → `bibtex main` → `xelatex main.tex` → `xelatex main.tex`

### File Structure
```
XDUthesis-private
├─ chapter                                  # Chapter content
│    ├─ article.tex                         # Main content of the report
├─ figure                                   # Image files
│    ├─ xdubanner.jpg                       # University banner
│    └─ xdulogo.jpg                         # University logo
├─ code                                     # Source code files
│    └─ demo.c                              # Sample C code
├─ books.bib                                # Bibliography file
├─ main.pdf                                 # Generated PDF output
├─ main.tex                                 # Main LaTeX file
└─ xdureport.cls                            # Custom document class
```

## Architecture

### Document Structure
- `main.tex` - Entry point that imports the custom class and includes content
- `xdureport.cls` - Custom LaTeX class that defines the report format
- `chapter/article.tex` - Main content of the experimental report
- `figure/` - Directory for images and figures
- `code/` - Directory for source code files
- `books.bib` - Bibliography references in BibTeX format

### Key Components in xdureport.cls
- Custom document class based on ctexart
- Page layout and geometry settings
- Header and footer configuration with fancyhdr
- Custom commands for student information (major, name, student ID, college, date, experiment name)
- Cover page generation with \makecover command
- Code listing configuration with listings package
- Custom environments for notes and code blocks

## Development Workflow

1. Edit `main.tex` to update personal information and document metadata
2. Modify `chapter/article.tex` to add experimental content
3. Add images to `figure/` directory and reference them in the document
4. Add source code to `code/` directory and include with \lstinputlisting
5. Update bibliography in `books.bib` as needed
6. Compile using the sequence: `xelatex` → `bibtex` → `xelatex` → `xelatex`

## Customization

### Personal Information
Update the following commands in `main.tex`:
- `\major{}` - Major/Program of study
- `\name{}` - Student name
- `\stuid{}` - Student ID
- `\college{}` - College/Faculty
- `\date{}` - Date of submission
- `\expname{}` - Experiment name

### Code Listings
The template uses the listings package for code highlighting with custom color schemes. Supported languages include C, C++, Java, Python, and MATLAB. Add code files to the `code/` directory and include them with:
```
\lstinputlisting[language=LANGUAGE]{code/filename.ext}
```

### Figures
Add image files to the `figure/` directory and include them with:
```
\includegraphics[width=SIZE]{figure/filename.ext}
```

## Dependencies

- TeX Live 2020 or later
- XeLaTeX engine
- Required packages: ctex, graphicx, geometry, fontspec, fancyhdr, lipsum, zhlipsum, xcolor, listings, algorithm, algorithmic
- Fonts: Times New Roman (main), IBM Plex Mono (monospace)
- Encoding: UTF-8

## Important Notes

- The template is designed for Windows environments with TeX Live and TeXstudio
- Images should be in .jpg or .png format for proper preview
- The template uses relative paths for all included files
- Modifications to the document style should be made in `xdureport.cls`
- Bibliography uses IEEEtran style