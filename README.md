# VUB LaTeX Template

A LaTeX template for academic reports using the VUB (Vrije Universiteit Brussel) official style with modular section files.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## ✨ Features

- **VUB Branding**: VUB logo, colors, and fonts (TeX Gyre Adventor)
- **Modular Structure**: Separate section files for easy organization
- **VS Code Integration**: One-click compilation with green run button
- **Build Automation**: Organized build artifacts in dedicated folder
- **Comprehensive Documentation**: All-in-one README
- **Ready to Use**: Just clone and start writing!

## 📁 Project Structure

```
latex-template/
├── main.tex                   # Main LaTeX document
├── vub_logo_cmyk.pdf          # VUB official logo
├── README.md                  # This file
├── LICENSE                    # MIT License
├── .vscode/
│   └── settings.json          # VS Code LaTeX Workshop configuration
├── bib/
│   └── main.bib               # BibTeX bibliography file
├── styles/
│   └── vubprivate.sty         # VUB custom styling (colors, fonts, triangle)
├── sections/
│   ├── 01-introduction.tex    # Introduction section
│   ├── 02-methods.tex         # Methods section
│   ├── 03-results.tex         # Results section
│   ├── 04-discussion.tex      # Discussion section
│   └── 05-conclusion.tex      # Conclusion section
└── build/                     # Build artifacts (auto-generated, git-ignored)
    ├── main.aux               # Auxiliary file
    ├── main.bbl               # Bibliography output
    ├── main.blg               # Bibliography log
    ├── main.fdb_latexmk       # Latexmk database
    ├── main.fls               # File list
    ├── main.log               # Compilation log
    ├── main.pdf               # Final PDF output
    ├── main.synctex.gz        # SyncTeX for editor sync
    └── main.toc               # Table of contents
```

---

## 🚀 Quick Start

### Prerequisites

- **LaTeX Distribution**: [MiKTeX](https://miktex.org/) (Windows) or [TeX Live](https://www.tug.org/texlive/) (Linux/Mac)
- **Perl**: Required by latexmk - [Strawberry Perl](http://strawberryperl.com/) (Windows)
- **VS Code** (recommended): With [LaTeX Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop) extension

### Using This Template

#### Option 1: Clone and Start Writing (Recommended)

```bash
# Clone this repository
git clone https://github.com/JonasBil/vub-latex-template.git my-project
cd my-project

# Open in VS Code
code .

# Edit main.tex and section files, then press Ctrl+Alt+B to compile
```

#### Option 2: Manual Compilation

```bash
cd my-project
latexmk -pdf -interaction=nonstopmode -outdir=build main.tex
```

The compiled PDF will be in `build/main.pdf`.

---

## � Recommended VS Code Extensions

To enhance your LaTeX workflow, install these extensions:

### Essential Extensions

1. **LaTeX Workshop** (James-Yu.latex-workshop) - Already recommended
   - One-click compilation (`Ctrl+Alt+B`)
   - Live PDF preview
   - Syntax highlighting and IntelliSense
   - Auto-completion for LaTeX commands

2. **Code Spell Checker** (streetsidesoftware.code-spell-checker)
   - Real-time spell checking
   - LaTeX-aware (ignores commands)
   - Right-click for suggestions

3. **LaTeX Utilities** (tecosaur.latex-utilities)
   - Live word count in status bar
   - Enhanced formatting
   - Paste images from clipboard
   - TikZ preview

### Helpful Extensions

4. **Markdown All in One** (yzhang.markdown-all-in-one)
   - Better README editing
   - Live preview (`Ctrl+Shift+V`)
   - Auto-formatting for markdown

5. **Git Graph** (mhutchie.git-graph)
   - Visual git history
   - See commits, branches, and changes
   - Click the graph icon in status bar

### Installation

Install extensions via:
1. Press `Ctrl+Shift+X` to open Extensions
2. Search for extension name
3. Click Install

Or use command line:
```bash
code --install-extension streetsidesoftware.code-spell-checker
code --install-extension tecosaur.latex-utilities
code --install-extension yzhang.markdown-all-in-one
code --install-extension mhutchie.git-graph
```

---

## 📏 Enable Word Wrap

Long lines in LaTeX can extend beyond your screen. Enable word wrap to make them wrap automatically:

**Quick method:** Press `Alt+Z` (toggles word wrap on/off)

**Permanent setting:**
1. Press `Ctrl+,` to open Settings
2. Search for "word wrap"
3. Change **Editor: Word Wrap** to `on`

---

## 📚 Zotero Integration

Connect Zotero for easy citation management:

### Step 1: Install Better BibTeX in Zotero
1. In Zotero: **Tools** → **Add-ons**
2. Search for "Better BibTeX for Zotero"
3. Install and restart Zotero

### Step 2: Export Your Library
1. In Zotero, right-click your library or collection
2. Select **Export Library/Collection...**
3. Format: **Better BibTeX**
4. ✅ Check **Keep updated** (auto-syncs!)
5. Save as `bib/main.bib` in your project folder

### Step 3: Use in VS Code
- Type `\cite{` and see autocomplete from your Zotero library
- Search by author, title, or citation key
- Compile LaTeX to see formatted citations

### Configure Citation Keys (Optional)
In Zotero:
1. **Tools** → **Better BibTeX** → **Preferences**
2. Set **Citation key format**: `[auth][year]`
   - Creates keys like `Smith2025` instead of random strings

**Workflow:**
1. Add paper to Zotero
2. Zotero auto-updates `bib/main.bib` (if "Keep updated" enabled)
3. Type `\cite{` in VS Code → see your references
4. Compile → citations appear!

---

## �📝 Writing Your Document

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
