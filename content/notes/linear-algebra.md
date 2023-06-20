---
title: "Linear Algebra Notes"
date: 2023-04-13T17:23:06+08:00
summary: Notes of linear algebra.
draft: true
---


Notes of Steven J. Leon's *Linear Algebra with Applications*.

## Ch.1 Matrices and System of Euqations

### Sec.1 Systems of Linear Equations

- Linear equation in $n$ unknowns
  - Inconsistent and consistent system
    - Homogeneous systems (always consistent)
  - Solution set
    - (Def.) Equivalence of systems
- Solving euqations
  - (Def.) Equation in strict triangular form
  - Back substitution
  - Coefficient matrix
  - Argumented matrix $(A | B)$
  - Elementary row operations
    - Interchange
    - Multiply
    - Replace
  - Pivotal row and pivot

### Sec.2 Row Echelon Form

- (Def.) Row echelon form
  - Lead variables and free variables
  - Inconsistent system
- (Def.) Gaussian elimination
  - Overdetermined linear system (Eg.4)
  - Underdetermined linear system (Eg.5)
- (Def.) Reduced row echelon form
  - Gauss–Jordan reduction
  - (Thm. 1.2.1) When will a homogeneous system have nontrivial solutions?

### Sec.3 Matrix Arithmetic

- Notations of matrix
  - Scalar, Column vector, Row vector
  - Diagonal and triangular Matrices
- Matrix Arithmetic
  - (Def.) Equivalence of two matrices
  - (Def.) Scalar Multiplication
  - (Def.) Matrix Addition
  - (Def.) Linear combination
    - $A\mathbf{x}$ can be seen as a linear combination
    - (Thm. 1.3.1) Consistency theorem for linear systems
  - (Def.) Multiplication
  - (Def.) Transpose of a matrix
    - (Def.) Symmetric matrix

### Sec.4 Matrix Algebra

- (Thm. 1.4.1) Algebraic rules for matrix addition and scalar multiplication
- (Def.) Identity matrix
  - Standard vectors ($\mathbf{e}\_i$)
- Matrix inversion
  - (Def.) Nonsingular and singular matrix
  - (Thm. 1.4.2) $A$ and $B$ are nonsigular then $AB$ is also nonsingular
- Algebraic rules
  - For transpose
  - For inversion

### Sec.5 Elementary Matrices

- Elementary matrix
  - Three types
  - Premultiplying and postmultiplying an elementary matrix
  - (Thm. 1.5.1) An elementary matrix $E$ and its inverse are the same type
- (Def.) Row equivalent
  - Reflexive and transitive
  - (Thm. 1.5.2) Equivalent conditions for nonsingularity:
    - $A$ is nonsingular
    - $A\mathbf{x} = \mathbf{0}$ has only the trivial solution $\mathbf{0}$
    - $A$ is row equivalent to $I$
- (Cor. 1.5.3) The system $A\mathbf{x} = \mathbf{b}$ of $n$ linear equations in $n$ unknowns has a unique solution if and only if A is nonsingular
- If A is nonsingular, then A can be factored into a product of elementary matrices
- Triangular Factorization
  - Upper triangular and lower triangular matrix
  - Diagonal matrix
- LU factorization (condition?)
  - Unit lower triangular.

### Partitioned Matrices

- Block and block multiplication (how to)
  - When will the matrix below is nonsingular?

    $$
      \begin{bmatrix}
      A\_{11} & O \\\\
      O & A\_{22}
      \end{bmatrix}
    $$

  - Inner product (scalar product) and outer product
    - Outer product expension

## Determinants

### Determinant of a Matrix

- Determinant
  - Minor, cofactor, cofactor expansion
  - $\text{det}(A)$ can be expressed as a cofactor expansion using any row or column of $A$
  - $\text{det}(A^T) = \text{det}(A)$
  - If $A$ is triangular, $\text{det}(A)$ is the product of all diagonal elements of $A$
  - If $A$:
    - has a row or column consisting entirely of zeros, then $\text{det}(A) = 0$
    - has two identical row or two identical columns, then $\text{det}(A) = 0$

### Properties of Determinants

- Let $\mathbf{r}\_i$ be the $i$th row vector of $A$ and $\mathbf{a}\_i$ be $i$th cofactors of $\mathbf{r}$, then ${\mathbf{r}\_i}^T \times \mathbf{a}\_j = \mathbf{0}$
- Effects of three row operations on the value of the determinant.
- $A$ is singular if and only if $\text{det}(A) = 0$
- When $A$ is reduced to triangular form $T$, the relationship between $T$ and $A$
- $\text{det}(AB) = \text{det}(A)\text{det}(B)$

### Adjoint of a Matrix

- Adjoint of a matrix
  - $A \text{det}(A) = \text{adj}(A)I$ (Use this to calculate inversion)
  - Cramer’s Rule

## Vector Spaces

### Vector space

- Definition
  - 8 axioms
    - Addition
      - Associativity
      - Commutative
      - Zero
      - Addictive inverse
    - Scalar multiplication
      - Two commutative laws
      - Associativity
      - Conversion between $1 * \mathbf{x}$ and $\mathbf{x}$
  - vector, scalar
- Examples
  - Euclidean vector spaces $\mathbb{R}^{n}$
  - Vector space $\mathbb{R}^{m \times n}$
  - $P\_n$: the set of all polynomials of degree less than $n$
- Properties
  - $0 \mathbf{x} = \mathbf{0}$
  - $\mathbf{x} + \mathbf{y}$ implies $\mathbf{y} = - \mathbf{x}$ (additive inverse is unique)
  - $(-1)\mathbf{x} = -\mathbf{x}$

### Subspaces

- Definition
  - Zero Subspaces
  - Proper subspaces
  - How to prove subspaces?
- Null spcace
- Span and spanning set
  - Linear combination
  - If $\mathbf{v}\_{1}, \mathbf{v}\_{2}, \dots, \mathbf{v}\_{n} \in V$, then $\text{Span}(\mathbf{v}\_{1}, \mathbf{v}\_{2}, \dots, \mathbf{v}\_{n})$ is a subspace of $V$
  - If the linear system $A\mathbf{x}=\mathbf{b}$ is consistent and $\mathbf{x}\_{0}$ is a solution, the $\mathbf{y}$ is also a solution iff $\mathbf{y} = \mathbf{x}\_{0} + \mathbf{z}$ where $\mathbf{z} \in N(A)$

### Linear independence

- Observation
  - If $\mathbf{v}\_{1}, \mathbf{v}\_{2}, \dots, \mathbf{v}\_{n}$ spans $V$ and one of these vectors is a linear combination of other vectors, then the other $n - 1$ can also span $v$ (proof)
  - How to formally express that a vector is a combination of another vectors.
- Linear independence
  - Correspondence between linear independence and singularity
  - Any vector $\mathbf{v} \in \text{Span}(\mathbf{v}\_{1}, \mathbf{v}\_{2}, \dots, \mathbf{v}\_{n})$ can be uniquely represented by $\mathbf{v}\_{1}, \mathbf{v}\_{2}, \dots, \mathbf{v}\_{n}$ iff the $\mathbf{v}\_{1}, \mathbf{v}\_{2}, \dots, \mathbf{v}\_{n}$ are linear independent.

### Basis and Dimension

- Basis
  - Standard basis
- Properties
  - If $\{ \mathbf{v}\_{1}, \mathbf{v}\_{2}, \dots, \mathbf{v}\_{n} \}$ is a spanning set for a vector space $V$, then any collection of $m > n$ vector in $V$ are linearly dependent. (a homogeneous system with more unknowns than equations.)
  - If $\mathbf{v}\_1, \mathbf{v}\_2, \dots, \mathbf{v}\_{n}$ and $\mathbf{u}\_1, \mathbf{u}\_2, \dots, \mathbf{u}\_{m}$ are bases for the same vector space, then $m = n$
- Dimension
  - Finite and infinite dimension
  - If $V$ is a vector space of dimension $n$, then:
    - any collection of $n$ linearly independent vectors can span $V$
    - any collection of $n$ vectors that span $V$ are linearly independent
  - If $V$ is a vector space of dimension $n$, then:
    - no set of $m < n$ vectors can span $V$
    - any set o $m < n$ linearly independent vectors can be extended to a basis for $V$
    - any spanning set contains $m > n$ vectors can be pared down to a basis for $V$
- Change of basis
  - Coordinate vector and coordinates
  - Transition matrix (hint: $U \mathbf{x}\_{u} = V \mathbf{x}\_{v}$)
- Row space (subspace of $\mathbb{R}^{1\times n}$) and column space (subspace of $\mathbb{R}^{m}$) of $A$
  - Two row equivalent matrices have the same row space.
  - A linear system $A\mathbf{x}=\mathbf{b}$ is consistent iff. $\mathbf{b}$ is in the column space of $A$
  - Let $A$ be a $m \times n$ matrix, a linear system $A\mathbf{x}=\mathbf{b}$ is consistent for every $\mathbf{b}$ in $\mathbb{R}^{m}$ iff. the column space of $A$ is $\mathbb{R}^{m}$
    - Additionally, $A\mathbf{x}=\mathbf{b}$ has one and only one solution for every $\mathbf{b}$ iff. the column vectors of $A$ are linearly independent
  - An $n \times n$ matrix $A$ is nonsingular iff. the column vectors of $A$ form a basis for $\mathbb{R}^{n}$
- Rank of a matrix
  - If $A$ be a $m \times n$ matrix, then the rank plus the nullity of $A$ equals $n$
  - If $A$ be a $m \times n$ matrix, then the dimension of the row space of $A$ equals the dimension of the column space of $A$

## Linear Transformations

- Definition and its property
- Kernel and image
  - Kernel and image are subspaces
- Matrix representation theorem
- Let $E = \{ \mathbf{u}\_1, \mathbf{u}\_2, \dots, \mathbf{u}\_{n} \}$, $F = \{ \mathbf{b}\_1, \mathbf{b}\_2, \dots, \mathbf{b}\_{m}\}$ be ordered bases for $\mathbb{R}^{n}$ and  $\mathbb{R}^{m}$ respectively. And $L: \mathbb{R}^{n} \rightarrow \mathbb{R}^{m}$ a linear Transformation and $A$ is the matrix representation of $L$ with respect to $E$ and $F$, then
  $$
  \mathbf{a}\_{j} = B ^{-1} L(\mathbf{u}\_{j})
  $$
  - and the reduced echelon form of $(\mathbf{b}\_1, \mathbf{b}\_2, \dots, \mathbf{b}\_{m} | L(\mathbf{u}\_{1}), L(\mathbf{u}\_{2}), \dots, L(\mathbf{u}\_{n}))$ is $(I | A)$

## Orthogonality

### Scalar product

- Scalar product
- Euclidean length
- $\mathbf{x}^T \mathbf{y} = \\| \mathbf{x} \\| \\| \mathbf{y} \\| \operatorname{cos}(\theta)$
- Cauchy-Schwarz Inequality
- Orthogonal $\perp$
- Scalar projection of $\mathbf{x}$ onto $\mathbf{y}$
- Vector projection of $\mathbf{x}$ onto $\mathbf{y}$

### Least squares problems

- Least squares solution $\mathbf{\hat{x}}$ of the system $A\mathbf{x}=\mathbf{b}$
  - Residual $r(\mathbf{x}) = \mathbf{b} - A \mathbf{x}$
- $\mathbf{p}$ is the closest vector in subspace $S$ to a given vector $\mathbf{b}$ iff. $\mathbf{b} - \mathbf{p} \in S^\perp$
- normal equations $A^T A \mathbf{x} = A^T \mathbf{b}$  (derived from $\mathbf{b} - \mathbf{p} \in R(A)^\perp = N(A^T)$)
- If $A$ is an $m \times n$ matrix of rank $n$, then the normal equations have a unique equation
- Projection matrix

### Orthogonal subspaces

- Orthogonality of subspaces
  - concept of orthogonal subspaces does not always agree with our intuitive idea of perpendicularity
- Orthogonal complement
- $N(A) = R(A^T)^\perp$ and $N(A^T) = R(A)^\perp$
- If $S$ is a subspace of $\mathbb{R}^n$, then $\operatorname{dim}(S) + \operatorname{dim}(S^\perp) = n$
  - If $\mathbf{x}\_1, \mathbf{x}\_2, \dots, \mathbf{x}\_{r}$ is a basis for $S$ and $\mathbf{x}\_{r+1}, \mathbf{x}\_{r+2}, \dots, \mathbf{x}\_{n}$, then $\mathbf{x}\_1, \mathbf{x}\_2, \dots, \mathbf{x}\_{r}, \mathbf{x}\_{r+1}, \mathbf{x}\_{r+2}, \dots, \mathbf{x}\_{n}$ is a basis for $\mathbb{R}^n$
- Direct sum
- If $S$ is a subspace of $\mathbb{R}^n$, then $\mathbb{R}^n = S \oplus S^\perp$
- If $S$ is a subspace of $\mathbb{R}^n$, then $(S^\perp)^\perp = S$
  - If $A$ is an $m \times n$ and $\mathbf{b} \in \mathbb{R}^{m}$, then
    - either $\exists \mathbf{x} \in \mathbb{R}^{n}. A \mathbf{x} = \mathbf{b}$
    - or $\exists \mathbf{y} \in \mathbb{R}^{m}.A^T \mathbf{y} = \mathbf{0} \text{ and } \mathbf{y}^T \mathbf{b} \neq 0$
- Every $m \times n$ matrix can be used to establish a one-to--one correspondence between $R(A^T)$ and $R(A)$.

### Inner Product Spaces

- Inner product, Inner product space
- Lenght(norm)
  - Frobenius norm $\\| \cdot  \\|\_F$
- Orthogonal
- Pythagorean Law
- Scalar projection
- Vector projection
  - If $\mathbf{v} \neq \mathbf{0}$ and $\mathbf{p}$ is the vector projection of $u$ onto $v$, then
    - $\mathbf{u} - \mathbf{p}$ and $\mathbf{p}$ are orthogonal
    - $\mathbf{u} = \mathbf{p}$ if and only if $\mathbf{u}$ is a scalar multiple of $\mathbf{v}$
- The Cauchy-Schwarz inequality
- Norm and normed linear space
  - Triangle inequality
- Distance

### Orthonormal Sets

- Orthogonal set of vectors
- Orthogonal set of vectors are linearly independent
- Orthonormal set of vectors
  - Transform from orthogonal set to orthonormal set
  - Let $\\{ \mathbf{u}\_1, \mathbf{u}\_2, \dots, \mathbf{u}\_{n} \\}$ be an orthonormal basis for an inner product space $V$. If $\mathbf{v} = \sum\_{i=1}^n c\_i \mathbf{u}\_{i}$, then $c\_i = \langle\mathbf{v}, \mathbf{u}\_{i} \rangle$
  - Let $\\{ \mathbf{u}\_1, \mathbf{u}\_2, \dots, \mathbf{u}\_{n} \\}$ be an orthonormal basis for an inner product space $V$. If $\mathbf{u} = \sum\_{i=1}^n a\_i \mathbf{u}\_{i}$ and $\mathbf{v} = \sum^{n}\_{i=1} b\_i \mathbf{u}\_{i}$, then $\langle \mathbf{u} , \mathbf{v} \rangle = \sum^{n}\_{i=1} a\_i b\_i$
    - If $\mathbf{v} = \sum\_{i=1}^{n} c\_i \mathbf{u}\_i$, then $\\| \mathbf{v} \\|^2 = \sum\_{i=1}^{n} c\_i^2$
- Orthognal matrix (col. vectors are orthonormal)
  - Properties of orthogonal matrices
    - An $n \times n$ matrix $Q$ is orthogonal if and only if $Q^TQ = I$
    - ...
    - $\langle \mathbf{x} ,  \mathbf{y}\rangle = \langle Q \mathbf{x} , Q \mathbf{y} \rangle$ if $Q$ is orthogonal
- Permutation matrix
- If $A$ is orthogonal, then the solution to the least squares problem is $\mathbf{\hat{\mathbf{x}}} = A^T \mathbf{b}$
- Let $S$ be a subspace of an inner product space $V$ and let $\vec{x} \in V$. Let $\\{ \mathbf{u}\_1, \mathbf{u}\_2, \dots, \mathbf{u}\_{n} \\}$ be an orthonormal basis for $S$. If

  $$
  \mathbf{p} = \sum\_{i=1}^{n} c\_i \mathbf{\mathbf{u}\_{i}}
  $$

  where $c\_{i} = \langle \mathbf{x} , \mathbf{u\_{i}} \rangle$ for each $i$
  then $\mathbf{p} - \mathbf{x} \in S^\perp$
  - $\mathbf{p}$ is the element of $S$ that is closest to $\mathbf{x}$
  - Let $S$ be a nonzero subspace of $\mathbb{R}^{m}$ and let $\mathbf{b} \in \mathbb{R}^{m}$. If $\\{ \mathbf{u}\_1, \mathbf{u}\_2, \dots, \mathbf{u}\_{k} \\}$ is an orthonormal basis for $S$ and $U = (\mathbf{u}\_1, \mathbf{u}\_2, \dots, \mathbf{u}\_{k})$, then the projection $\mathbf{p}$ of $\mathbf{b}$ onto $S$ is given by $\mathbf{p} = U U^T \mathbf{b}$
- If $P$ is a projection matrix corresponding to a subspace $S$ of $\mathbb{R}^{m}$, the projection matrix is unique.

### The Gram-Schmidt Orthogonalization Process

- The Gram-Schmidt Process
  - For a basis $\\{ \mathbf{x}\_1, \mathbf{x}\_2, \dots, \mathbf{x}\_{n} \\}$, we first unify $\mathbf{x}\_{1}$ into unit vector $u\_1$, then for each $i+1$
    - Find a projection $\mathbf{p}$ on space $L(\mathbf{u}\_1, \mathbf{u}\_2, \dots, \mathbf{u}\_{i})$
    - Unify $\mathbf{x}\_{i+1} - \mathbf{p}$ into unit vector $\mathbf{u}\_{i+1}$
- Gram-Schmidt QR Factorization
  - If $A$ is an $m \times n$ matrix of rank $n$, then $A$ can be factored into product $QR$, where
    - $Q$ is $m \times n$ orthogonal matrix
    - $R$ is an upper triangular $n \times n$ matrix whose diagonal entries are all positive ($R$ is thus nonsingular)
  - If $A$ is an $m \times n$ matrix of rank $n$, the least squares solution of $A\mathbf{x}=\mathbf{b}$ is given by $\mathbf{\hat{x}} {R}^{-1} Q^T \mathbf{b}$, and
    - The solution $\mathbf{\hat{x}}$ may be obtained by using back substitution to solve $R \mathbf{x} = Q^T \mathbf{b}$
- Modified Gram-Schmidt Process
- The modified Gram-Schmidt Process

## Eigenvalues

### Eigenvalues and eigenvectors

- Eigenvalue (characteristic value) and eigenvector (characteristic vector)
- Characteristic polynomial, trace, product and sum of the eigenvalues
- Similar matrices have the same characteristic polynomial and, consequently, the same eigenvalues

### Systems of linear differential equations

- Initial value problem

### Diagonalization

- The eigenvectors of all corresponding distinct eigenvalues of a matrix are linearly independent
- Diagonalizable

### Hermitian Matrices

- Complex inner products
  - Length of a complex scalar, length of a vector $\mathbf{z}$ in $\mathbb{C}^{n}$
  - Hermitian conjugate: $\mathbf{z}^H = \bar{\mathbf{z}}^T$
- Complex inner product space
  - In $\mathbb{R}^{n}$: $\langle \mathbf{x} ,  \mathbf{y} \rangle  = \mathbf{y}^T \mathbf{x} = \mathbf{x}^T \mathbf{y}$
  - In $\mathbb{C}^{n}$: $\langle \mathbf{z} ,  \mathbf{w} \rangle  = \mathbf{w}^T \mathbf{z} = \overline{ \mathbf{z}^H \mathbf{w} }$
- Hermitian matrices
  - If a complex matrix $M$ satisfies: $M = A + iB$, in which $A$ and $B$ are both real matrix. Then $\overline{M} = A - iB$
  - $(A^H)^H = A$
  - $(\alpha A + \beta B)^H = \overline{\alpha}A^H + \overline{\beta}B^H$
  - A matrix is Hermitian iff. $M = M^H$
- The eigenvalues of a Hermitian matrix are all real.
  - Furthermore, eigenvectors belonging to distinct eigenvalues are orthogonal.
- Unitary matrix $U$: $U^H U = I$
  - Then $U^{-1} = IU^{-1} = U^H U U^{-1} = U^H$
- If the eigenvalues of a Hermitian matrix are distinct, then there exists a unitary matrix $U$ that diagonalizes $A$.
- Schur’s Theorem: for each $n \times n$ matrix $A$, there exists a unitary matrix $U$ s.t. $U^H A U$ is upper triangular.
  - Schur decomposition $A = U T U^H$, $T$ is upper triangular.
- Spectral Theorem
  - If $A$ is Hermitian, then there exists a unitary matrix that diagonalizes $A$.
  - Express a vector as a linear combination of orthonormal basis elements.
- The Real Schur Decomposition
  - Real Schur form
- Spectral Theorem for Real Symmetric Matrices
  - If $A$ is a symmetric matrix, then there is an orthogonal matrix $Q$ that diagonalizes $A$, that is $Q^T A Q = D$, where $D$ is diagonal.
- Normal matrix $AA^H = A^H A$
  - A matrix $A$ is normal iff. $A$ possesses a complete orthonormal set of egienvectors.

### The Singular Value Decomposition

- Singular value decomposition
  - compact form of the singular value decomposition
- Let $\mathcal{M}$ be the set of all $m \times n$ matrices of rank $k$ or less. Then 
  
  $$
  \\| A - X \\|\_F = \operatorname{min}\_{S \in \mathcal{M}} \\| A - S \\|\_F
  $$
- If $A$ is an $m \times n$ matrix and $Q$ is an $m \times n$ otrhogonal matrix, then

  $$
  \\| QA \\|\_F = \\| A \\|\_F
  $$

  - It follows from SVD theorem that $\\| A \\|\_F = (\sigma^2\_1 + \sigma^2\_2 + \dots + \sigma^2\_n)^{1/2}$
- Let $A = U \Sigam V^T$ be an $m \times n$ matrix, and let $\mathcal{M}$ denote the set of all $m \times n$ matrices of rank $k$ or less, where $0 < k < rank(A)$. If $X$ is a matrix in $\mathcal{M}$ satisfying:
  
  $$
  \\| A - X \\|\_F = \operatorname{min}\_{S \in \mathcal{M}} \\| A - S \\|\_F
  $$

  , then

  $$
  \\| A - X \\|\_F = (\sigma^2\_{k+1} + \sigma^2\_{k+2} + \dots + \sigma^2\_n)^{1/2}
  $$

  - If $A$ is a nonsingular $n \times n$ matrix, then $A'$ is singular and $\\| A - A' \\|\_F = \sigma\_n$. Thus $\sigma\_n$ may be taken as a measure of how close a square matrix is to being singular.

### Quadratic forms

- quadratic equation
  - conic section
  - degenerate conic
  - standard position
  - rotation
- Principal axes theorem
- stationary point
  - definite
  - positive definite
  - negative definite
  - positive semidefinite
  - negative semidefinite
  - indefinite
- Let $A$ be a real symmetric $n \times n$ matrix. Then $A$ is positive definite if and only if all its eigenvalues are positive

### Positive definite matrices

- If $A$ is a symmetric positive definite matrix, then $A$ is nonsingular.
- If $A$ is a symmetric positive definite matrix, then $\operatorname{det}(A) > 0$.
- If $A$ is a symmetric positive definite matrix, then the leading principal submatrices $A\_1, A\_2, \cdots , A\_n$ of $A$ are all positive definite.
- If $A$ is a symmetric positive definite matrix, then $A$ can be reduced to upper triangular form using only row operation 3, and the pivot elements will all be positive.
  - Then $A$ can be factored into a product $LU$.
- LDU factorization, and LDU factorization is unique
  - If $A$ is positive definite, then $LDU = A = A^T = (LDU)^T = U^T D^T L^T$. By the uniqueness of LDU fact., $L^T = U$, then $A = LDL^T$
- If $A$ is a symmetric positive definite matrix, then $A$ can be factored into a product $LDL^T$, where $L$ is lower triangular with 1's along the diagonal and $D$ is a diagonal matrix whose diagonal entries are all positive.
  - Cholesky decomposition $A = LDL^T = LD^{1/2}(D^{1/2})^TL^T = L\_1 L\_1^T$
- If $A$ is a symmetric positive definite matrix, then $A$ can be facotred into a product $LL^T$, where $L$ is lower triangular with positive diagonal elements.
- If $A$ is a symmetric positive definite matrix, the properties above are all equivalent.