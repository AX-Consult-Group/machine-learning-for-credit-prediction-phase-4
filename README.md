# Machine Learning for Credit Prediction: Phase 4
## The Evolution of Credit Scoring Under SR 26-2 

---

### Background and Aim 

The recent issuance of SR 26-2 (April 2026), which revises and supersedes the previous SR 11-7 framework, introduces a more risk-based and proportionate approach to Model Risk Management (MRM). While core expectations for governance, validation, and effective challenge remain firmly in place, the updated guidance provides banking organizations with greater flexibility. This represents a meaningful evolution from the more uniform expectations under SR 11-7, enabling responsible innovation in the use of advanced statistical and non-generative AI and ML techniques.

In this context, the aim of the fourth and final phase of this project is to explore how psychometric signals can be transformed into a regulator-ready decision layer while simultaneously maintaining the feature richness typically associated with advanced ML techniques. By applying hybrid methodologies, this phase demonstrates a practical way to balance predictive power, interpretability, and regulatory compliance in line with the principles outlined in SR 26-2.

---

### Methods

To address the core challenge of balancing feature richness (from the ML discovery phase) with model stability and regulatory explainability, Phase 4 applied a structured sequence of statistical transformations and modelling techniques to the psychometric DRA higher-order factors and their interactions.

The following approaches were tested and evaluated:

1. Standardisation (centering and scaling) of all DRA factors to improve numerical stability and facilitate safe creation of interaction terms.

2. Residualisation (orthogonalisation) — evaluated as an alternative (or complementary) technique to reduce multicollinearity between correlated psychometric dimensions.

3. Interaction Discovery — using XGBoost for feature importance and SHAP interaction values to identify high-value pairwise interactions, followed by careful shortlisting and testing.

4. Weight of Evidence (WOE) Binning — diagnostically evaluated on both main effects and interactions to assess potential benefits in monotonicity and interpretability.

5. Penalised Logistic Regression to handle remaining multicollinearity while performing automatic feature selection.

6. Bayesian Logistic Regression — fitted as a robustness check using weakly informative priors to validate coefficient stability and provide credible intervals.

7. PD Calibration and Scorecard Development — Platt scaling followed by conversion to a 0–1000 points-based scorecard with six risk rating bands (A to F).

--- 

### Data

This analysis uses real **psychometric assessment data**. The scores have been scaled such that risk reduces as the score increases. 

To protect intellectual property, the names of the DRA variables have been generalized or renamed in this public version. The underlying constructs and relationships remain representative of the actual assessment. All financial data (accounts, arrears, age on book, bad outcome) is simulated to match realistic distributions, correlations, and patterns from the original analysis (based on a South African thin-file population). No real candidate or client information is included.

---

## How to view the report

The full rendered report is available via **GitHub Pages**: 

xxx

---

### Technologies used
The analysis was conducted in R using the following packages:

### Analysis
- xgboost
- shapviz
- scorecard
- glmnet
- pROC
- brms
- scales

---
