# Thesis Template

A LaTeX thesis template based on [latex-mimosis](https://github.com/Pseudomanifold/latex-mimosis), with a basic chapter structure and student guidance built in.

<a href="https://raw.githubusercontent.com/thealanjason/thesis-template/pdf/thesis.pdf">
<img src="https://img.shields.io/badge/View-PDF_(Tectonic)-red?style=flat-square&logo=adobeacrobatreader&logoColor=white" alt="View the thesis PDF (Tectonic)"/>
</a>
<a href="https://raw.githubusercontent.com/thealanjason/thesis-template/pdf-tinytex/thesis.pdf">
<img src="https://img.shields.io/badge/View-PDF_(TinyTeX)-red?style=flat-square&logo=adobeacrobatreader&logoColor=white" alt="View the thesis PDF (TinyTeX)"/>
</a>
<a href="https://github.com/thealanjason/thesis-template/actions/workflows/compat.yml">
<img src="https://img.shields.io/github/actions/workflow/status/thealanjason/thesis-template/compat.yml?label=Compatibility%3A%20Linux%20%7C%20macOS%20%7C%20Windows&style=flat-square" alt="Compatibility: Linux | macOS | Windows"/>
</a>

## Structure

```
thesis.tex                  # Main file — configure title, author, and thesis type here
sources/
  title.tex                 # Title page
  abstract.tex              # Abstract
  acknowledgements.tex      # Acknowledgements
  declarationofownwork.tex  # Declaration of own work + AI tool usage
  conventions.tex           # Notation and writing conventions
  introduction.tex          # Chapter 1
  relatedwork.tex           # Chapter 2
  ownwork.tex               # Chapter 3 — your contribution
  evaluation.tex            # Chapter 4
  summaryandfuturework.tex  # Chapter 5
  appendix.tex              # Appendix
resources/
  logoipsum-354.pdf         # Replace with your institution's logo
  declarationofacademicintegrity.pdf  # Required for Master's and Bachelor's theses at RWTH Aachen University
images/                     # Place your figures here
data/                       # Place your datasets here
scripts/                    # Python scripts to generate plots, with their conda environments
thesis.bib                  # Bibliography
```

## Getting started

1. Click **Use this template** on GitHub to create your own repository
2. Update the PDF badge link in this README to point to your own repository (replace `thealanjason/thesis-template` with your username/repo)
3. Set your title, author, and thesis type in `thesis.tex`:
   ```latex
   \masterthesistrue  % or \bachelorthesistrue — leave both false for project reports
   \title{Your Thesis Title}
   \subtitle{Your Subtitle}
   \author{Your Name}
   ```
4. Replace `resources/logoipsum-354.pdf` with your institution's logo
5. Set up the build environment and compile. Two build options are available:

   ```bash
   micromamba env create -f environment.yml
   micromamba activate thesis
   ```

   Then choose how to build:

   **Tectonic** (auto-downloads packages on first run):
   ```bash
   tectonic -X compile thesis.tex
   ```

   **TinyTeX + latexmk**:
   ```bash
   python thesis.py setup --tinytex
   python thesis.py build
   ```
   `setup --tinytex` installs TinyTeX (one-time). `build` auto-installs any missing LaTeX packages and produces `thesis.pdf`. For subsequent builds, `latexmk` is sufficient.

   Both tools also work with [LaTeX Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop) in VS Code — run `python thesis.py setup` (or `setup --tinytex` for latexmk support) once and the recipes will work out of the box.

The thesis is built automatically on every push via GitHub Actions using both options.
