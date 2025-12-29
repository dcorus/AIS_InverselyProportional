# AIS Inversely Proportional Hypermutations

This repository contains the LaTeX source code and supporting materials for the research paper:

**"Effective Inversely Proportional Hypermutations for Unimodal and Multimodal Optimisation"**

## About

This paper presents research on Artificial Immune Systems (AIS) employing inversely proportional hypermutations (IPH) for optimization problems. The work analyzes dynamic mutation strategies that can achieve speed-ups during the exploitation phase while maintaining effectiveness in escaping local optima.

## Repository Structure

### Main Paper Files
- **`mainTEVC.tex`** - Main paper for IEEE Transactions on Evolutionary Computation (TEVC) submission
- **`main.tex`** - Alternative version of the main paper
- **`preamble.tex`** - Shared LaTeX preamble with custom commands and package imports
- **`references.bib`** - Bibliography file with all citations

### Supporting Content Files
- **`cliffSketchTEVC.tex`** - Cliff function analysis section
- **`cliffAppendix.tex`** - Appendix for cliff function proofs
- **`cliffCutOut.tex`** - Cut content related to cliff functions
- **`ltjSketchTEVC.tex`** - LeadingOnes and Jump analysis section
- **`ltjAppendix.tex`** - Appendix for LeadingOnes/Jump proofs
- **`ltjCutOut.tex`** - Cut content related to LeadingOnes/Jump

### Figures and Images
- `*.png`, `*.eps` - Various figures including:
  - `fig1.png` - First figure
  - `jump.png`, `cliff.png`, `ridge.png` - Problem landscape illustrations
  - `hd.png`, `newhd.png` - Hypermutation diagrams
  - `tm.png`, `tmcl.png` - Additional analysis figures

### Submission Folders
- **`Submission/`** - Previous submission materials and related documents
- **`TEVC-NewSubmission/`** - Current TEVC submission materials

### Additional Files
- **`notes.txt`** - Author notes and TODO items for paper revisions
- **`IEEEtran.cls`** - IEEE Transactions LaTeX class file
- **`.gitignore`** - Git ignore rules (excludes PDF files, LaTeX auxiliary files, logs)

## Prerequisites

To compile this paper, you need:

- **LaTeX Distribution**: TeX Live, MiKTeX, or MacTeX
  - On Ubuntu/Debian: `sudo apt-get install texlive-full`
  - On macOS: Install MacTeX from https://www.tug.org/mactex/
  - On Windows: Install MiKTeX from https://miktex.org/

- **Required LaTeX Packages** (most included in full TeX distributions):
  - IEEEtran
  - amsmath, amsfonts, amssymb
  - algorithmic, algorithm
  - graphicx, epstopdf
  - xcolor
  - thmtools, thm-restate
  - And others listed in `preamble.tex`

## Building the Paper

### Compile Main TEVC Version

```bash
# Basic compilation
pdflatex mainTEVC.tex

# Full compilation with bibliography
pdflatex mainTEVC.tex
bibtex mainTEVC
pdflatex mainTEVC.tex
pdflatex mainTEVC.tex
```

### Compile Alternative Version

```bash
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```

### Using latexmk (Recommended)

If you have `latexmk` installed, you can use it for automatic compilation:

```bash
latexmk -pdf mainTEVC.tex
```

## Key Research Contributions

Based on the paper content and notes, this work covers:

1. **Inversely Proportional Hypermutations (IPH)** - Dynamic mutation strategies
2. **Analysis on benchmark problems**:
   - OneMax
   - LeadingOnes
   - Jump functions
   - Cliff functions
   - Ridge problems
   - TwoMax variants

3. **Algorithm variants**:
   - (1+1) Opt-IA with different selection strategies
   - Linear and exponential hypermutation schedules
   - Ageing mechanisms

4. **Theoretical analysis** including:
   - Runtime bounds
   - Drift analysis
   - Comparison with static and standard bit mutation (SBM)

## Development Notes

The `notes.txt` file contains detailed revision notes including:
- Proof restructuring plans
- Section reorganization
- Results to add or remove
- Clarity improvements needed

## Citation

If you use this work, please cite the published version (to be added upon publication).

## License

Please refer to the paper's copyright and licensing terms. This repository contains research materials intended for academic purposes.

## Contact

For questions about this research, please contact the paper authors through the appropriate academic channels.

---

*This repository represents work submitted to IEEE Transactions on Evolutionary Computation (TEVC).*
