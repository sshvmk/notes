---
title: Matrix, Determinant, Rank (and a little more)
date: 2024-05-17
tags:
  - math
enableToc: true
---

Matrix is a rectangular array of numbers, symbols, or expressions, arranged in rows and columns. The elements of a matrix are usually enclosed in square or round brackets.

$$
A = \begin{bmatrix}
a_{11} & a_{12} & a_{13} \\
a_{21} & a_{22} & a_{23} \\
a_{31} & a_{32} & a_{33}
\end{bmatrix}
$$

The numbers (or functions) are called the **elements** or the entries of the matrix.\
The horizontal lines of elements are said to constitute rows of the matrix and the
vertical lines of elements are said to constitute columns of the matrix. \
A matrix is denoted by a capital letter. If the matrix is $A$ then it's elements are $a_{ij}$ where $i$ is row and $j$ is column.

If a matrix has $m$ rows and $n$ columns then the **dimension** of a matrix is $m$ x $n$.

## Special Types of Matrices

1. Row matrix - A matrix with only one row.
2. Column matrix - A matrix with only one column.
3. Square matrix - A matrix with the same number of rows and columns $n$ x $n$.
4. Diagonal matrix - A square matrix $B = {[b_{ij}]}_{{n}\times{n}}$ where all off-diagonal elements are zero i.e. $b_{ij} = 0$ when $i \neq j$.
5. Scalar matrix - A diagonal matrix where all diagonal elements are equal, i.e. $b_{ij} = 0$ when $i \neq j$ and $b_{ij} = k$ when $i = j$ for some constant $k$.
6. Identity matrix - A diagonal matrix where all diagonal elements are 1.
7. Upper triangular matrix - A square matrix where all elements below the main diagonal are zero.
   $$
   A = \begin{bmatrix}
   a_{11} & a_{12} & a_{13} \\
   0 & a_{22} & a_{23} \\
   0 & 0 & a_{33}
   \end{bmatrix}
   $$
8. Lower triangular matrix - A square matrix where all elements above the main diagonal are zero.
   $$
   A = \begin{bmatrix}
   a_{11} & 0 & 0 \\
   a_{21} & a_{22} & 0 \\
   a_{31} & a_{32} & a_{33}
   \end{bmatrix}
   $$
9. Symmetric matrix - A square matrix that is equal to its transpose. In other words, $B = {[b_{ij}]}_{{n}\times{n}}$ is symmetric when $b_{ij} = b_{ji}$
10. Skew symmetric matrix - A square matrix that is equal to the negative of its transpose. In other words, $B = {[b_{ij}]}_{{n}\times{n}}$ is symmetric when $b_{ij} = -b_{ji}$
11. Zero matrix - A matrix where all elements are zero. We denote zero matrix by O.

## Determinant

The determinant of a matrix is a scalar value that is computed from a square matrix and encapsulates certain properties of the matrix.
Let $A = {[a_{ij}]}_{{n}\times{n}}$ be a square matrix of order $n$ , then the number $|A|$ is called determinant of the matrix $A$.

#### Calculation for determinant

1. For a ${2 \times 2}$ matrix:
   $
A = \begin{bmatrix}
a & b \\
c & d
\end{bmatrix}
$
   , \
    determinant $|A|$ is = $ad - bc$
   <br>

2. For a ${3 \times 3}$ matrix:
   $
A = \begin{bmatrix}
a & b & c\\
d & e & f\\
g & h & i
\end{bmatrix}
$
   , \
    determinant $|A|$ is = $a(ei-fh) - b(di - fg) + c(dh - eg)$.
   <br>

> [!general]
> For a $n \times n$ matrix\
> General formula using first row expansion :
> $$ \det A = \displaystyle\sum*{j=1}^n (-1)^{i+j}a*{1j} \det (A*{1j})$$ \
> where $(A*{1j})$ is the $(n-1) \times (n-1)$ submatrix obtained by removing the first row and $j^{th}$ column of $A$.

> [!important]
> If $A$ is square matrix of order $n$, then $A$ is called singular matrix when $|A|=0$ and nonsingular otherwise.

### Minor, Cofactors and Adjoin matrix

Let $A = {[a_{ij}]}_{{n}\times{n}}$ is a square matrix. Then $M_{ij}$ denotes a sub matrix of $A$ with order $(n-1) \times (n-1)$ obtained by deleting its $i^{th}$ row and $j^{th}$ column. \
Determinant of $ |M*{ij}|$ is called **minor** of the element $a*{ij}$ of $A$.

The **cofactor** of $a_{ij}$ denoted by $A_{ij}$ and is equal to $(-1)^{i+j}|M_{ij}|$.

The transpose of the matrix of cofactors of the element $a_{ij}$ of A denoted by $adj A$ is called **adjoin** of matrix A.

## Rank

It is defined as the maximum number of linearly independent rows or columns in the matrix. In other words, the rank tells you the dimension of the vector space spanned by its rows or columns.\
Denoted by $rank (A)$ or $\rho (A)$

### Key points about rank

- $rank(A)≤min(m,n)$ where m and n are matrix row and columns.
- A zero matrix has a rank of 0, as all its rows/columns are linearly dependent (filled with zeros).
- An identity matrix has a rank equal to its dimension, as all its rows/columns are linearly independent.

> [!note]
> If the rank of a matrix is equal to the smaller of the number of rows or columns, the matrix is said to have **full rank**. For a $m \times n$ matrix:
>
> - if $rank(A)=m$ and $m≤n$, then the matrix has full row rank.
> - if $rank(A)=m$ and $n≤m$, then the matrix has full row rank.

---

## References :

1. https://ncert.nic.in/pdf/publication/exemplarproblem/classXII/mathematics/leep203.pdf
2. https://uom.lk/sites/default/files/math/files/MATRICES-COMPLETE_LECTURE_NOTE.pdf
