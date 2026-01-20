# Garment Factory Productivity: Regression Inference & Resampling
## Overview
This project analyzes garment factory productivity using multiple linear regression and a suite of statistical inference techniques, including asymptotic tests, bootstrap and jackknife resampling, permutation tests, and diagnostic-driven transformations. The goal is to assess which operational factors meaningfully explain actual productivity and to validate conclusions using both classical and simulation-based methods.

## Dataset
The dataset (productivity.txt) contains observations from garment production lines with the response variable:

 - actual_productivity – realized production efficiency
 - and predictors including:
 - targeted_productivity
 - smv (standard minute value)
 - over_time
 - incentive
 - idle_time
 - idle_men
 - no_of_style_change
 - no_of_workers

## Methods
### 1. Linear Regression Modeling
- Fit a full multiple linear regression model with actual_productivity as the response.
- Interpreted coefficient estimates and standard errors under classical OLS assumptions.

### 2. Linear Hypothesis Testing
- Tested linear constraints on regression coefficients using a Wald F-test.
- Implemented an “exact” bootstrap test under the null hypothesis to compare with asymptotic results.

### 3. Resampling-Based Uncertainty Estimation
- Jackknife standard errors for regression coefficients.
- Nonparametric bootstrap standard errors.
- Constructed bootstrap confidence intervals (percentile, normal, and basic).

### 4. Permutation Tests
- Permutation-based overall F-test for model significance.
- Permutation test for the incentive coefficient, comparing empirical and theoretical p-values.

### 5. Model Diagnostics & Transformations
- Residual diagnostics including:
  - Residual vs fitted plots
  - Normal Q–Q plots with confidence envelopes
  - Shapiro–Wilk normality tests
- Box–Cox analysis suggested a square transformation of the response.
- Log transformations applied to selected predictors (e.g., log(over_time + 1), log(incentive + 1)).
- Refit transformed models and reassessed assumptions.

## Key Findings
- The overall regression model is highly significant, confirmed by both theoretical and permutation-based F-tests.
- The effect of incentives on productivity is marginal, with p-values near common significance thresholds across multiple inference approaches.
- Diagnostic checks motivated response and covariate transformations, improving normality and variance behavior of residuals.
- Resampling-based inference closely aligned with asymptotic results, increasing confidence in conclusions.
