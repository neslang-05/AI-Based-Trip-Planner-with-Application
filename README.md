# AI-Based Trip Planner Web Application — LaTeX Thesis

This repository contains the complete LaTeX thesis project for the **AI-Based Trip Planner Web Application**, submitted in partial fulfillment of the requirements for the award of the Bachelor of Technology degree at **Manipur Technical University**.

## Authors

| Name                    | Registration Number |
|-------------------------|---------------------|
| Oinam Dinibash Singh    | 2201CS0105          |
| Laba Moirangthem        | 2201CS0104          |
| Deemson Pukhrambam      | 2201CS0118          |
| Mathiuthailiu Panmei    | 2301CS0302          |

**Supervisor**: Mr. Golmei Shaheamlung, Assistant Professor, CSE, MTU

---

## Project Structure

```
.
├── main.tex                          # Master document
├── README.md                         # This file
├── .gitignore                        # LaTeX build artifact exclusions
├── assets/
│   └── logo.png                      # Manipur Technical University logo
├── images/                           # Figures and diagrams
├── bibliography/
│   └── references.bib                # BibLaTeX reference database
└── chapters/
    ├── title-page.tex                 # Title page
    ├── dedication.tex                 # Dedication page
    ├── bonafide-certificate.tex       # Bonafide certificate
    ├── decleration-OinamDinibash.tex  # Declaration – Oinam Dinibash Singh
    ├── decleration-LabaMoreirangthem.tex  # Declaration – Laba Moirangthem
    ├── decleration-DeemsonPukhrambam.tex  # Declaration – Deemson Pukhrambam
    ├── decleration-MathiuthailluPanmei.tex # Declaration – Mathiuthailiu Panmei
    ├── acknowledgement.tex            # Acknowledgement
    ├── abstract.tex                   # Abstract
    ├── abbreviations.tex              # Symbols and Acronyms (nomenclature)
    ├── chapter1.tex                   # Chapter 1: Introduction
    ├── chapter2.tex                   # Chapter 2: Literature Review
    ├── chapter3.tex                   # Chapter 3: System Analysis and Design
    ├── chapter4.tex                   # Chapter 4: Machine Learning Implementation
    ├── chapter5.tex                   # Chapter 5: Web Application Development
    ├── chapter6.tex                   # Chapter 6: User Interface and Experience
    ├── chapter7.tex                   # Chapter 7: Testing and Evaluation
    └── conclusion.tex                 # Chapter 8: Conclusion and Future Scope
```

---

## Prerequisites

Ensure the following are installed on your system:

- **TeX Live** (full installation recommended) or **MiKTeX**
- **Biber** (for bibliography processing with BibLaTeX)
- **latexmk** (optional, for automated compilation)
- Required LaTeX packages (all included in TeX Live full):
  - `fontenc`, `courier`, `geometry`, `setspace`, `indentfirst`, `microtype`
  - `graphicx`, `float`, `tikz` (with libraries)
  - `array`, `longtable`, `tabularx`, `booktabs`, `multirow`, `makecell`, `caption`, `subfig`
  - `amsmath`, `amssymb`, `amsfonts`, `nicefrac`, `ulem`, `seqsplit`, `relsize`
  - `listings`, `algorithm`, `algorithmic`, `tcolorbox`
  - `fontawesome`, `pifont`, `enumitem`, `titlesec`, `fancyhdr`, `nomencl`, `tocbibind`
  - `biblatex` (with IEEE style), `xurl`, `hyperref`

Install on Ubuntu/Debian:

```bash
sudo apt-get install texlive-full biber latexmk
```

---

## Compilation Instructions

### Standard Compilation (Manual)

Run the following commands in sequence from the project root:

```bash
# Step 1: Initial compile to generate auxiliary files
pdflatex -interaction=nonstopmode main.tex

# Step 2: Generate bibliography
biber main

# Step 3: Compile to incorporate bibliography
pdflatex -interaction=nonstopmode main.tex

# Step 4: Final compile to resolve all cross-references
pdflatex -interaction=nonstopmode main.tex

# Step 5: Generate nomenclature (symbols and acronyms)
makeindex main.nlo -s nomencl.ist -o main.nls

# Step 6: Final compile with nomenclature
pdflatex -interaction=nonstopmode main.tex
```

### Automated Compilation with latexmk

```bash
# Compile with latexmk (handles all compilation steps automatically)
latexmk -pdf main.tex

# Continuous compilation (watches for file changes)
latexmk -pdf -pvc main.tex

# Clean build artifacts
latexmk -C
```

### Using the Makefile (if available)

```bash
make          # Full compilation
make clean    # Remove build artifacts
```

---

## Adding University Logo

Place the Manipur Technical University logo at:

```
assets/logo.png
```

The logo is referenced in:
- `chapters/title-page.tex`
- `chapters/bonafide-certificate.tex`
- All four declaration files

---

## Adding Figures

Place figure image files in the `images/` directory and reference them in chapter files:

```latex
\begin{figure}[H]
    \centering
    \includegraphics[width=0.8\textwidth]{images/your-figure.png}
    \caption{Your Figure Caption}
    \label{fig:your-label}
\end{figure}
```

---

## Common Compilation Issues

| Issue | Solution |
|-------|----------|
| `biber` not found | Install via `sudo apt-get install biber` |
| Missing packages | Run `sudo apt-get install texlive-full` |
| Nomenclature not appearing | Run `makeindex main.nlo -s nomencl.ist -o main.nls` then recompile |
| Hyperref conflicts | Ensure `hyperref` is loaded last in preamble |
| Font warnings | Install `texlive-fonts-extra` |

---

## Output

After successful compilation, the PDF thesis will be generated as `main.pdf` in the project root directory.
