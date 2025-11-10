# 📋 LaTeX Quick Reference Card

## 🚀 Getting Started

### Create New Project
```powershell
cd latex-exercise3
.\new-project.ps1 "MyProject"
```

### Build Document
```powershell
.\build-latex.ps1
```

## 📝 Document Structure

```latex
\section{Title}              % Main section
\subsection{Subtitle}        % Subsection
\subsubsection{Detail}      % Sub-subsection
```

## 📚 References

### Citing
```latex
\cite{key}                   % (Author, Year)
\citeA{key}                  % Author (Year)
\citeyear{key}              % Year only
```

### BibTeX Entry
```bibtex
@article{author2025,
    title={Title},
    author={Last, First},
    journal={Journal},
    year={2025},
    pages={1--10}
}
```

## 🖼️ Figures

```latex
\begin{figure}[h]
    \centering
    \includegraphics[width=0.8\textwidth]{figures/image.png}
    \caption{Description}
    \label{fig:mylabel}
\end{figure}

Reference: Figure~\ref{fig:mylabel}
```

## 📊 Tables

```latex
\begin{table}[h]
    \centering
    \caption{Description}
    \label{tab:mylabel}
    \begin{tabular}{|l|c|r|}
        \hline
        Col1 & Col2 & Col3 \\
        \hline
        ...  & ...  & ...  \\
        \hline
    \end{tabular}
\end{table}

Reference: Table~\ref{tab:mylabel}
```
