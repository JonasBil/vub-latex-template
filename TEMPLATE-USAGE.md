# 📘 LaTeX Template Usage Guide

This guide explains how to use this LaTeX template for your own projects.

## 🎯 For Quick Start

### Method 1: Use the Template Files

1. **Copy `main-template.tex` to start fresh**:
   ```powershell
   Copy-Item main-template.tex main.tex
   ```

2. **Copy `bib/main-template.bib` for bibliography**:
   ```powershell
   Copy-Item bib\main-template.bib bib\main.bib
   ```

3. **Edit your document**:
   - Open `main.tex`
   - Update the author, date, title
   - Update footer name
   - Update bibliography path if renamed
   - Write your content!

4. **Compile**:
   ```powershell
   latexmk -pdf -interaction=nonstopmode -outdir=build main.tex
   ```

### Method 2: Copy Entire Template Folder

For a completely new project in a different location:

```powershell
# From the parent directory
Copy-Item -Recurse latex-exercise3\ C:\Path\To\Your\New-Project\

cd C:\Path\To\Your\New-Project\

# Rename template files
Rename-Item main-template.tex main.tex
Rename-Item bib\main-template.bib bib\main.bib

# Update the build script path if needed
# Edit build-latex.ps1 to match your new directory name

# Start editing
code main.tex
```

## 📝 Editing Your Document

### Essential Changes

1. **Document Information**:
   ```latex
   %! Author = Your Name
   %! Date = DD/MM/YYYY
   ```
