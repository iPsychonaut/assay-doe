# ASSAY-DOE

A repository to contain a module centered around design, analysis, and reporting for a randomized factorial assay experiment.

## Status

This is an in-progress repository; all datasets are simulated not measured.

## Methods Demonstrated

Planned scope. Nothing below is implemented yet; this section will be updated as each module lands.

- **Randomized Experimental Design**: Seeded, reproducible allocation of a blocked factorial layout (substrate, strain, colonization time), including a split-plot variant for factors applied at the vertical position during shelf cultivation.
- **Power analysis**: Analytical power for the balanced case, plus Monte Carlo power curves and minimum detectable effect for the mixed and non-normal models where no closed form exists.
- **ANOVA and post hoc contrasts**: Type I, II, and III sums of squares with correct contrast coding, residual diagnostics, and pre-specified treatment contrasts with multiplicity correction.
- **Regression**: Linear models with continuous covariates and interactions compared by AIC and nested F-test, and heteroskedasticity-robust standard errors (HC3).
- **Generalized Linear Models (GLMs)**: Gamma with a log link for the strictly positive concentration data, negative binomial for fruiting body counts, beta regression for the proportional composition response, and linear mixed models for block effects.
- **Bayesian Hierarchical Models**: Partial pooling across strains and explicit handling of measurements left-censored at the limit of quantitation, with posterior predictive checks and Pareto-smoothed importance sampling leave-one-out model comparison.
- **FAIR data packaging**: Machine-readable schema, controlled-vocabulary terms, checksum manifests, provenance ledger, and a versioned release with a DOI.

## Installation

```bash
git clone https://github.com/iPsychonaut/assay-doe.git
cd assay-doe
conda env create -f environment.yml
conda activate assay-doe
pip install -e .
```

## Repository Layout

```
assay-doe/
├── data/
│   ├── raw/        # simulated source data, immutable
│   ├── interim/    # intermediate, regenerable, untracked
│   ├── processed/  # analysis-ready, regenerable, untracked
│   └── metadata/   # data dictionary, ground truth parameters
├── src/assay_doe/  # package source
├── apps/           # Streamlit and Dash applications
├── notebooks/      # narrative analysis
├── reports/        # generated output
└── tests/
```

## Licenses

Code: MIT, see [LICENSE](LICENSE).

Data: CC BY 4.0, see [LICENSE-DATA](LICENSE-DATA).
