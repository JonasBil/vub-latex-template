# LaTeX Project Template - VUB Style

A clean, organized LaTeX project template for academic reports using the VUB (Vrije Universiteit Brussel) style.

## 📁 Project Structure

```
latex-exercise3/
├── main.tex                 # Main LaTeX document
├── main.pdf                 # Compiled PDF output
├── vub_logo_cmyk.pdf        # VUB official logo
├── README.md                # This file
├── bib/                    # Bibliography directory
│   └── main.bib            # BibTeX bibliography file
├── styles/                 # Custom style files
│   └── vubprivate.sty      # VUB private styling
└── build/                  # Build artifacts (auto-generated, git-ignored)
    ├── main.aux            # Auxiliary file
    ├── main.bbl            # Bibliography output
    ├── main.blg            # Bibliography log
    ├── main.fdb_latexmk    # Latexmk database
    ├── main.fls            # File list
    ├── main.log            # Compilation log
    ├── main.synctex.gz     # SyncTeX for editor sync
    └── main.toc            # Table of contents
```

## 🚀 Quick Start

### Prerequisites
- **MiKTeX** or **TeX Live** LaTeX distribution
- **Perl** (required by latexmk) - [Install Strawberry Perl](http://strawberryperl.com/)
- **VS Code** (optional) with LaTeX Workshop extension

### Building the Document

#### Option 1: Automated Build Script (Recommended)
From the project root directory:
```powershell
.\build-latex.ps1
```

This script:
- Navigates to the latex-exercise3/ directory
- Sets up the TEXINPUTS environment for style files
- Cleans previous build artifacts
- Compiles the document with latexmk
- Copies the final PDF to latex-exercise3/main.pdf
- Keeps all build artifacts in build/ folder

#### Option 2: Manual Compilation
From the `latex-exercise3/` directory:
```bash
latexmk -pdf -interaction=nonstopmode -outdir=build main.tex
```

#### Option 3: VS Code LaTeX Workshop
With the LaTeX Workshop extension installed:
- Press `Ctrl+Alt+B` to build
- Or click the green play button in the top right
