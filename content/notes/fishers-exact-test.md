---
title: Fisher's Exact Test
date: 2024-07-10
tags:
  - math
enableToc: true
---

It is a statistical hypothesis test used to assess the association between two binary variables using a contingency table.

> [!definition] Contingency table shows distribution of one variable in rows and another in columns. It is used to study the correlation between variables.

Fisher's exact test uses contingency table to calculate the probability of observing the data as it is, considering all possible arrangements of observed data. As the variables in this test are binary variables, the contingency table is 2 $\times$ 2 in size. \
This test is useful when working with small sized samples. It is a non parametric test (means that it assumes no distribution of data).

#### Assumptions of Fisher's exact test
1. Both varibles are categorical and binary
2. Data should be randongly selected from independent samples
  > - groups should have no relation among them
  > - observations can only fall into one category at a time
3. One or more value in contingency table is small (less than 5)

#### Hypothesis of Fisher's exact test
Null hypothesis $H_0$ : there is no association between two variables \
Alternate hypothesis $H_1$ : there is an association between two variables (in any direction)
