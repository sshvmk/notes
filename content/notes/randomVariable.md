---
title: Random Variable
date: 2024-05-16
tags:
  - math
enableToc: true
---

Random variable is a function which maps the outcome of a simple random experiment to a real number.
denoted by capital italized roman characters like $X$ or $Y$.

Suppose that a coin is tossed twice so that the sample space is $S={HH, HT, TH, TT}$. Let $X$ represent the number of heads that can come up. With each sample point we can associate a number for $X$ as shown below.

| Sample point | HH  | HT  | TH  | TT  |
| ------------ | --- | --- | --- | --- |
| X            | 2   | 1   | 1   | 0   |

### Types of Random Variable

- Discrete
  - can take finite or countably infinite number of values
  - probability distribution PMF :
    $
    \begin{cases}
    P(X=x) &\text{if }  x ∈ Ω \\
    0 &\text{if } x ∉ Ω
    \end{cases}
    $
- Continuous
  - takes on a noncountably infinite number of values
  - probability distribution PDF : $P(a \leq X \leq b) = \int_{a}^{b} f(x) dx$

### Probability Function

A probability function is a mathematical function that provides probabilities for the possible outcomes of the random variable, $X$. It is typically denoted as $f(x)$.

1. **Probability Mass Function** \
   A probability mass function (PMF) is a function that gives the probability that a discrete random variable is exactly equal to a certain value. In other words, it maps each possible outcome of a discrete random variable to its probability of occurrence.\
   If $X$ is discrete, then $f(x) = P(X=x)$. In other words, the PMF for a constant, $x$, is the probability that the random variable $X$ is equal to $x$. \
   Properties of PMF : - ${f(x) ≥ 0}$ for x in sample space otherwise 0. - ${\sum_{x}^{} f(x) = 1}$.

2. **Probability Density Function**\
   If the random variable is a continuous random variable, the probability function is usually called the probability density function (PDF). Contrary to the discrete case, \
   $f(x) \neq P(X=x)$
   Properties of PDF : - ${f(x) ≥ 0}$ for x in sample space otherwise 0. - Area under the curve is equal to 1.

3. **Cumulative Distribution Function**\
   A cumulative distribution function (CDF), usually denoted
   $F(x)$, is a function that gives the probability that the random variable, $X$, is less than or equal to the value $x$.

### Discrete Probability Distributions

Let $X$ be a discrete random variable, and suppose that the possible values that it can assume are given by $x1, x2, x3, . . . ,$ arranged in some order. Suppose also that these values are assumed with probabilities given by:

$$ P(X=x_k) = f(x_k),k = 1, 2, 3, 4,...$$

It is convenient to introduce the probability function, also referred to as probability distribution, given by :

$$P(X=x) = f(x)$$

For $x=x_k$ this reduces to (1) while for other values of $x, f(x) = 0$.
In general, $f(x)$ is a probability function if :

1. ${f(x) ≥ 0}$
2. ${\sum_{x}^{} f(x) = 1}$
   where the sum is taken over all possible values of $x$.

### Expected Value and Variance of a Discrete Random Variable

Expected value or mean of discrete random variable is denoted by $\mu = E(X) = \sum x_i{f(x_i)}$. \
Formula basically says multiply each value by its respective probability and add all of them together.\
\
Variance of a discrete random variable is given by $\sigma = Var(X)=(\sum x_i-\mu)^2{f(x_i)}$
Formula basically says take each value of x, subtract the expected value, square that value and multiply that value by its probability. Then sum all of those values.

---

1. https://www.gs.washington.edu/academics/courses/akey/56008/lecture/lecture4.pdf
2. http://users.stat.umn.edu/~helwig/notes/RandomVariables.pdf
3. http://www.stat.yale.edu/Courses/1997-98/101/ranvar.htm
4. https://www.stat.pitt.edu/stoffer/tsa4/intro_prob.pdf
5. https://byjus.com/maths/random-variable/
6. https://online.stat.psu.edu/stat500/lesson/3/3.1
