---
title: Handling multicollinearity in Linear Models
date: 2024-05-30
tags:
  - dl
  - revisionNotes
enableToc: true
---

Multicollinearity is a situation in linear regression models where two or more independent variables (predictors) are highly correlated with each other. This can cause issues in the model, such as unstable and unreliable coefficient estimates, inflated standard errors, and difficulty in interpreting the individual effects of the predictor variables.
- detect multicollinearity
  1. correlation matrix
  2. Variance Inflation Factor (VIF) - Calculate the VIF for each predictor. VIF values greater than 5 or 10 indicate high multicollinearity
    $$
    VIF = \frac {1}{1 - {R_j}^2} 
    $$ 
    ${R_j}^2$ is the ${R^2}$-value obtained by regressing the ${j^th}$ predictor on the remaining predictors. 
- removing multicollinearity
  1. Remove Collinear Variables
  2. PCA
  3. L1 and L2 regularisation
  4. combining features
  5. collect more data
  6. mean centering and standardisation