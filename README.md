# VUB LaTeX Template# LaTeX Project Template - VUB Style



A clean, organized LaTeX template for academic reports using the VUB (Vrije Universiteit Brussel) official style with modular section files.A clean, organized LaTeX project template for academic reports using the VUB (Vrije Universiteit Brussel) style.



[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)## 📁 Project Structure



## ✨ Features```

latex-exercise3/

- **VUB Official Branding**: VUB logo, colors, and fonts (TeX Gyre Adventor)├── main.tex                 # Main LaTeX document

- **Modular Structure**: Separate section files for easy organization├── main.pdf                 # Compiled PDF output

- **VS Code Integration**: One-click compilation with green run button├── vub_logo_cmyk.pdf        # VUB official logo

- **Build Automation**: Organized build artifacts in dedicated folder├── README.md                # This file

- **Comprehensive Documentation**: All-in-one README├── bib/                    # Bibliography directory

- **Ready to Use**: Just clone and start writing!│   └── main.bib            # BibTeX bibliography file

├── styles/                 # Custom style files

## 📁 Project Structure│   └── vubprivate.sty      # VUB private styling

└── build/                  # Build artifacts (auto-generated, git-ignored)

```    ├── main.aux            # Auxiliary file

latex-template/    ├── main.bbl            # Bibliography output

├── main.tex                    # Main LaTeX document    ├── main.blg            # Bibliography log

├── vub_logo_cmyk.pdf          # VUB official logo    ├── main.fdb_latexmk    # Latexmk database

├── README.md                  # This file    ├── main.fls            # File list

├── .vscode/    ├── main.log            # Compilation log

│   └── settings.json          # VS Code LaTeX Workshop configuration    ├── main.synctex.gz     # SyncTeX for editor sync

├── bib/    └── main.toc            # Table of contents

│   └── main.bib               # BibTeX bibliography file```

├── styles/

│   └── vubprivate.sty         # VUB custom styling (colors, fonts, triangle)## 🚀 Quick Start

├── sections/

│   ├── 01-introduction.tex    # Introduction section### Prerequisites

│   ├── 02-methods.tex         # Methods section- **MiKTeX** or **TeX Live** LaTeX distribution

│   ├── 03-results.tex         # Results section- **Perl** (required by latexmk) - [Install Strawberry Perl](http://strawberryperl.com/)

│   ├── 04-discussion.tex      # Discussion section- **VS Code** (optional) with LaTeX Workshop extension

│   └── 05-conclusion.tex      # Conclusion section

└── build/                     # Build artifacts (auto-generated, git-ignored)### Building the Document

```

#### Option 1: Automated Build Script (Recommended)

---From the project root directory:

```powershell

## 🚀 Quick Start.\build-latex.ps1

```

### Prerequisites

This script:

- **LaTeX Distribution**: [MiKTeX](https://miktex.org/) (Windows) or [TeX Live](https://www.tug.org/texlive/) (Linux/Mac)- Navigates to the latex-exercise3/ directory

- **Perl**: Required by latexmk - [Strawberry Perl](http://strawberryperl.com/) (Windows)- Sets up the TEXINPUTS environment for style files

- **VS Code** (recommended): With [LaTeX Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop) extension- Cleans previous build artifacts

- Compiles the document with latexmk

### Using This Template- Copies the final PDF to latex-exercise3/main.pdf

- Keeps all build artifacts in build/ folder

#### Option 1: Clone and Start Writing (Recommended)

#### Option 2: Manual Compilation

```bashFrom the `latex-exercise3/` directory:

# Clone this repository```bash

git clone https://github.com/JonasBil/vub-latex-template.git my-projectlatexmk -pdf -interaction=nonstopmode -outdir=build main.tex

cd my-project```



# Open in VS Code#### Option 3: VS Code LaTeX Workshop

code .With the LaTeX Workshop extension installed:

- Press `Ctrl+Alt+B` to build

# Edit main.tex and section files, then press Ctrl+Alt+B to compile- Or click the green play button in the top right

```

#### Option 2: Manual Compilation

```bash
cd my-project
latexmk -pdf -interaction=nonstopmode -outdir=build main.tex
```

The compiled PDF will be in `build/main.pdf`.

---

## 📝 Writing Your Document

### 1. Update Document Information

Edit the preamble in `main.tex`:

```latex
%! Author = Your Name
%! Date = DD/MM/YYYY

\title{Your Document Title}
\faculty{Sciences and Bio-Engineering Sciences}  % Your VUB faculty
\author{Your Name}
```

Also update the footer:
```latex
\fancyfoot[LO, RE]{Your Name}  % Change to your name
```

### 2. Edit Section Files

Write your content in the separate section files:

- **`sections/01-introduction.tex`**: Introduction, background, research questions
- **`sections/02-methods.tex`**: Methodology, data, analysis
- **`sections/03-results.tex`**: Findings, figures, tables
- **`sections/04-discussion.tex`**: Interpretation, limitations, implications
- **`sections/05-conclusion.tex`**: Summary, contributions, future work

These files are automatically included in `main.tex` via:
```latex
\input{sections/01-introduction}
\input{sections/02-methods}
% ... etc
```

### 3. Add References

Add your references to `bib/main.bib`:

```bibtex
@article{author2025,
    title={Article Title},
    author={Last, First and Second, Author},
    journal={Journal Name},
    year={2025},
    volume={10},
    pages={123--145}
}
```

Cite in your text:
```latex
As shown by \cite{author2025}...
Or: \citeA{author2025} demonstrated that...
```

---

## 📚 LaTeX Quick Reference

### Document Structure

```latex
\section{Title}              % Main section
\subsection{Subtitle}        % Subsection
\subsubsection{Detail}       % Sub-subsection
```

### Figures

```latex
\begin{figure}[h]
    \centering
    \includegraphics[width=0.8\textwidth]{figures/image.png}
    \caption{Your caption here}
    \label{fig:mylabel}
\end{figure}

% Reference it:
As shown in Figure~\ref{fig:mylabel}...
```

### Tables

```latex
\begin{table}[h]
    \centering
    \caption{Table caption}
    \label{tab:data}
    \begin{tabular}{|l|c|r|}
        \hline
        Column 1 & Column 2 & Column 3 \\
        \hline
        Data 1 & Data 2 & Data 3 \\
        \hline
    \end{tabular}
\end{table}

% Reference it:
See Table~\ref{tab:data} for details.
```

### Math

```latex
% Inline math
The equation $E = mc^2$ is famous.

% Display math
\begin{equation}
    \int_0^\infty e^{-x^2} dx = \frac{\sqrt{\pi}}{2}
\end{equation}
```

### Lists

```latex
% Bulleted list
\begin{itemize}
    \item First item
    \item Second item
\end{itemize}

% Numbered list
\begin{enumerate}
    \item First step
    \item Second step
\end{enumerate}
```

### Citations

```latex
\cite{key}                   % (Author, Year)
\citeA{key}                  % Author (Year)
\citeyear{key}              % Year only
```

---

## 🛠️ Building Your Document

### VS Code (Recommended)

1. Open `main.tex` in VS Code
2. Press **`Ctrl+Alt+B`** or click the green **▶** button
3. PDF opens automatically in VS Code

### Command Line

```bash
# Full build with bibliography
latexmk -pdf -interaction=nonstopmode -outdir=build main.tex

# Clean build artifacts
latexmk -C -outdir=build

# Continuous preview (recompiles on save)
latexmk -pdf -pvc -interaction=nonstopmode -outdir=build main.tex
```

---

## 🎨 VUB Styling

This template includes VUB official branding:

### Colors

```latex
\textcolor{vubbleu}{Blue text}      % VUB blue (CMYK: 1,.8,.16,.03)
\textcolor{vuboranje}{Orange text}  % VUB orange (CMYK: 0,.78,1.,0)
```

### Fonts

The template uses **TeX Gyre Adventor** (similar to Avenir), the official VUB font. It works automatically with both pdfLaTeX and XeLaTeX/LuaLaTeX.

### Logo and Triangle

The VUB logo and orange triangle are automatically added to the title page via `\maketitle`.

---

## 🐛 Troubleshooting

### Common Issues

**Problem**: `File 'vub.sty' not found`
- **Solution**: Ensure the path `../archive/Latex/texlive-vub-v3.0.1/vub` exists, or update the path in `main.tex` line 11

**Problem**: `perl: command not found`
- **Solution**: Install [Strawberry Perl](http://strawberryperl.com/) and restart your terminal

**Problem**: Undefined references
- **Solution**: Compile twice. LaTeX needs two passes to resolve cross-references

**Problem**: Bibliography not showing
- **Solution**: Ensure you have at least one `\cite{}` command in your document

**Problem**: Fonts look wrong
- **Solution**: Install TeX Gyre Adventor fonts or they'll fall back to Computer Modern

---

## 📖 Additional Resources

### LaTeX Tutorials
- [Overleaf Documentation](https://www.overleaf.com/learn)
- [LaTeX Wikibook](https://en.wikibooks.org/wiki/LaTeX)
- [The Not So Short Introduction to LaTeX](https://tobi.oetiker.ch/lshort/lshort.pdf)

### Bibliography Management
- [Google Scholar](https://scholar.google.com/) - Export BibTeX citations
- [JabRef](https://www.jabref.org/) - Reference management software
- [Zotero](https://www.zotero.org/) - Bibliography manager with BibTeX export

### VS Code Extensions
- [LaTeX Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop) - Essential for LaTeX in VS Code
- [LTeX](https://marketplace.visualstudio.com/items?itemName=valentjn.vscode-ltex) - Grammar/spell checking

---

## 📄 License

This template is licensed under the [MIT License](LICENSE).

### VUB Style Package

The VUB style (`texlive-vub-v3.0.1`) is provided by VUB. Check the original repository for its license.

---

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

### Areas for Contribution
- Additional section templates
- More examples (figures, tables, algorithms)
- Multilingual support
- Additional documentation
- Bug fixes

---

## 👤 Author

**Jonas Bil**
- GitHub: [@JonasBil](https://github.com/JonasBil)

---

## 🙏 Acknowledgments

- VUB for the official style package
- LaTeX Workshop team for the excellent VS Code extension
- The LaTeX community for continuous support

---

**Happy Writing! 📝✨**
