# Statistical Research Portfolio

This repository contains two R Markdown research projects focused on Bayesian inference, sequential analysis, and risk-based model selection:

- [Research 1](./Research_1.rmd): exact Bayesian inference for Bernoulli trials using HPD intervals, sequential stopping boundaries, and confidence-interval inversion
- [Research 3](./Research_3.rmd): nonparametric smoothing and adaptive partitioning using covariance penalties, bootstrap optimism, cross-validation, and penalized risk criteria

## Research 1

**Title:** *HPD Intervals, Sequential Stopping, and Exact Confidence Inversion for a Bernoulli Trial*

This project develops a unified Bayesian framework for Bernoulli inference. Starting from a `Beta(1,1)` prior, it constructs exact Highest Posterior Density (HPD) intervals, uses HPD width as a sequential stopping rule, and then inverts the induced stopping distribution to obtain an exact confidence interval.

### Main ideas

- Beta-Binomial posterior updating
- Exact 95% HPD interval construction
- Sequential stopping based on HPD width
- Dynamic programming for boundary-hitting probabilities
- Confidence-test duality through exact inversion

### Selected results

- Fixed-sample `Beta(2,10)` 95% HPD interval
- Sequential stopping boundary for Bernoulli trials
- Exact 95% confidence interval at the observed stopping point `(1359, 2523)`

## Research 3

**Title:** *Risk-Based Model Selection for Fixed and Adaptive Nonparametric Smoothers*

This project studies nonparametric regression and model selection on the motorcycle crash dataset. It compares fixed-bin regressograms, LOWESS smoothing, and adaptive regressograms, all under a common risk-estimation framework motivated in part by Bradley Efron's work on covariance penalties and cross-validation.

### Main ideas

- Fixed-bin regressograms for baseline smoothing
- Covariance-penalty risk estimation
- Bootstrap optimism and Figure 6-like diagnostics
- 7-fold cross-validation
- LOWESS span selection
- Adaptive regressograms via recursive RSS minimization
- Penalized histogram selection on `qer.csv`

### Selected results

- Fixed-bin regressogram selected by covariance penalty and cross-validation
- Bootstrap-based complexity assessment for regressograms
- LOWESS tuning via cross-validation
- Adaptive regressogram with fewer bins but competitive fit
- Penalized histogram selection on a second dataset

## Repository Structure

- [Research_1.rmd](./Research_1.rmd): integrated Bernoulli/Bayesian sequential analysis report
- [Research_3.rmd](./Research_3.rmd): integrated nonparametric smoothing and adaptive partitioning report
- [mct.csv](./mct.csv): motorcycle crash dataset
- [qer.csv](./qer.csv): dataset used for histogram risk selection

## Rendering

To render either report to PDF:

```bash
Rscript -e "rmarkdown::render('Research_1.rmd', output_format='pdf_document')"
Rscript -e "rmarkdown::render('Research_3.rmd', output_format='pdf_document')"
```

Both reports require a working R Markdown + LaTeX setup.
