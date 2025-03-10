---
title: Hessian Matrix
date: 2024-05-16
tags:
  - math
enableToc: true
---

## Hessian Matrix

A Hessian matrix is a square matrix of second-order partial derivatives of a scalar-valued function. It describes the local curvature of a function.
For a function f(x, y, ..., z) of several variables, the Hessian matrix H is defined as:

$$
\begin{bmatrix}
\frac{\partial^2 f}{\partial x^2} & \frac{\partial^2 f}{\partial x \partial y} & \cdots & \frac{\partial^2 f}{\partial x \partial z} \\
\frac{\partial^2 f}{\partial y \partial x} & \frac{\partial^2 f}{\partial y^2} & \cdots & \frac{\partial^2 f}{\partial y \partial z} \\
\vdots & \vdots & \ddots & \vdots \\
\frac{\partial^2 f}{\partial z \partial x} & \frac{\partial^2 f}{\partial z \partial y} & \cdots & \frac{\partial^2 f}{\partial z^2}
\end{bmatrix}
$$

The above Hessian is of the the function
𝑓:𝑅′′→𝑅 where all second order partial derivatives of 𝑓 exist and are continuous throughout its domain & the function is $$f(x_1, x_2, x_3, \ldots, x_n)$$

The Hessian matrix plays an important role in optimization, where it is used to find points where the function has a local maximum or minimum. \
\
Specifically:

- If the Hessian is positive definite at a point, then that point is a local minimum of the function.
- If the Hessian is negative definite at a point, then that point is a local maximum of the function.
- If the Hessian is indefinite (has both positive and negative eigenvalues), then the point is a saddle point.

The Hessian is also used for calculating the Newton direction for Newton's method in optimization problems.

### Conditions for Minima, Maxima, Saddle point

The conditions are based on the eigenvalues of the Hessian matrix H:

- _Local Maximum_: If all the eigenvalues of H are negative at a critical point, then the function has a local maximum at that point.
- _Local Minimum_: If all the eigenvalues of H are positive at a critical point, then the function has a local minimum at that point.
- _Saddle Point_: If the eigenvalues of H are both positive and negative at a critical point, then the function has a saddle point at that point.
- _Inconclusive_: If some eigenvalues are zero, then the second derivative test is inconclusive, and higher-order derivatives may need to be considered to determine the nature of the critical point.

### Jacobian v/s Hessian

Hessian matrix is used for scalar-valued functions to analyze local curvature, while the Jacobian matrix is used for vector-valued functions to analyze rate of change.

**Jacobian**

- The Jacobian matrix is used to describe the rate at which a vector-valued function changes with respect to its input variables.
- It is a matrix of first-order partial derivatives of a vector-valued function with respect to its variables.
- If the function is F(x, y, z) = (f1(x, y, z), f2(x, y, z), f3(x, y, z)), then the Jacobian matrix would be a 3x3 matrix where each row represents the gradient of one of the component functions.
- It is used in various fields like physics, engineering, and optimization.

**Hessian Matrix**

- The Hessian matrix is used to describe the local curvature of a scalar-valued function of multiple variables.
- It is a square matrix of second-order partial derivatives of a scalar function with respect to its variables.
- If the function is f(x, y, z), then the Hessian matrix would be a 3x3 matrix where each entry represents a second-order partial derivative.
- It helps in determining whether a critical point is a maximum, minimum, or saddle point.

---

**Further reading :**

1. https://resources.system-analysis.cadence.com/blog/msa2022-all-about-the-hessian-matrix-convexity-and-optimization
2. https://www.khanacademy.org/math/multivariable-calculus/applications-of-multivariable-derivatives/quadratic-approximations/a/the-hessian
3. https://brilliant.org/wiki/hessian-matrix/#:~:text=The%20Hessian%20Matrix%20is%20a,of%20local%20maxima%20or%20minima.
4. https://www.reddit.com/r/mathematics/comments/wwk6ig/upperbound_to_largest_eigenvalue_of_hessian_matrix/
5. https://people.iith.ac.in/ashok/Maths_Lectures/TutorialB/Hessian_Examples.pdf
