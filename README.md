# Thesis Template

A LaTeX thesis template based on [latex-mimosis](https://github.com/Pseudomanifold/latex-mimosis), with a basic chapter structure and student guidance built in.

<a href="../../blob/pdf/thesis.pdf?raw=true">
<img src="https://img.shields.io/badge/View-PDF-red?style=flat-square&logo=adobeacrobatreader&logoColor=white" alt="View the thesis PDF"/>
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
2. Set your title, author, and thesis type in `thesis.tex`:
   ```latex
   \masterthesistrue  % or \bachelorthesistrue — leave both false for project reports
   \title{Your Thesis Title}
   \subtitle{Your Subtitle}
   \author{Your Name}
   ```
3. Replace `resources/logoipsum-354.pdf` with your institution's logo
4. Set up the build environment and compile:
   ```bash
   micromamba env create -f environment.yml
   micromamba activate thesis
   tectonic -X compile thesis.tex
   ```

The thesis is also built automatically on every push via GitHub Actions.
