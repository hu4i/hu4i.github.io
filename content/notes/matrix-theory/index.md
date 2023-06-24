---
title: "Matrix Theory Notes"
date: 2023-04-24T09:47:36+08:00
summary: Notes of matrix theory.
draft: true
mermaid: true
---

## Chapter 1 Linear Space and Linear Transformation

### Section 1.1 Linear Space

![Section_1_1](images/section_1_1.i.svg)

#### Linear space and its properties

- (Def. 1.1, p6) Linear space (vector space)
- (Thm. 1.1) Uniqueness of $\mathbf{0}$ and $-\mathbf{x}$
- (Notations)
  - Linear combination
  - Linear independence/dependence
- (Def. 1.2) Dimension $\operatorname{dim}(V) = n$
  - Finite dimensional linear space
  - Infinite dimensional linear space

#### Basis and coordinate

- (Def. 1.3) Basis
- (Def. 1.4) Coordinate
- (Thm. 1.2) Uniqueness of the coordinate with the given bases

#### Change of basis

- (Notation) Transition matrix
  - Transition of bases
  - Transition of coordinates

#### Subspace

- (Def. 1.5) Subspace
  - Nonempty
  - Addition and scalar multiplication
- (Notations)
  - Trivial subspace
    - Zero vector subspace $\{\mathbf{0}\}$, $V$
  - Nontrivial subspace
  - Proper subspace
- Span, $L(\mathbf{x}\_1, \mathbf{x}\_2, \dots, \mathbf{x}\_{n}) = \\{k\_1 \mathbf{x}\_1+ , \dots, + k\_1 \mathbf{x}\_m \\}$
- (Def. 1.6) Range (a.k.a. column space) of matrix $A$, $R(A) = L(\mathbf{a}\_1, \mathbf{a}\_2, \dots, \mathbf{a}\_{n})$
  - Row space $R(A^T)$
  - $\operatorname{Rank}(A) = \operatorname{dim}(R(A)) = \operatorname{dim}(R(A^T))$
- (Def. 1.7) Null space (kernel space) $N(A) = \{ \mathbf{x}\ |\ A \mathbf{x} = \mathbf{0} \}$
  - Nullity $n(A) = \operatorname{dim}(N(A))$
- If $A = (a\_{ij})\_{m\times n}$, then
  - $\operatorname{Rank}(A) + n(A) = n$
  - $n(A) - n(A^T) = n - m$
- (Thm. 1.3) Extension of linear independent vectors to bases.

#### The intersection and sum of subspaces

- (Thm. 1.4) The intersection of subspaces is subspace
  - $V\_1 \cap V_2$ is the largest subspace that is included in both $V\_1$ and $V\_2$
- (Def. 1.8) Addition of subspaces
- (Thm. 1.5) The sum of subspaces is subspace
  - $V\_1 + V_2$ is the smallest subspace that contains both $V\_1$ and $V\_2$
- (Thm. 1.6) $\operatorname{dim}(V\_1) + \operatorname{dim}(V\_2) = \operatorname{dim}(V\_1 + V\_2) + \operatorname{dim}(V\_1 \cap V\_2)$
- (Def. 1.9) Direct sum $A \oplus B$
- (Thm. 1.7) Sum of two subspaces are direct sum iff. ?
  - (Lem. 1) with (Thm. 1.6)
  - (Lem. 1) relation among the bases of these three subspaces.

### Section 1.2 Linear Transformations and Their Matrix Representations

![Seciton_1_2](images/section_1_2.i.svg)

#### Linear transformation and its arithmetic

- (Def. 1.10) Transformation
- (Def. 1.11) Linear transformation
  - map $\mathbf{0}$ to $\mathbf{0}$
  - map inverse to inverse
  - map linear **dependence** to linear **dependence** (not for independence)
- (Def. 1.12) Range $R(T) = \\{ T \mathbf{x}\ |\ \mathbf{x} \in V \\}$ and kernel $N(T) = \\{ \mathbf{x}\ |\ T \mathbf{x} = 0, \mathbf{x} \in V \\}$ of linear transformation
- (Thm. 1.8) $R(T)$ and $N(T)$ are subspaces of $V$
- (Def. 1.13) Rank of $T$ is $\operatorname{dim}(R(T))$ and nullity of $T$ is $\operatorname{dim}(N(T))$
- (Notations)
  - Identity transformation $T\_{e}$ and zero transformation $T\_{0}$
- Arithmetic of linear transformations and its properties
  - Sum and addictive inversion
  - Scalar multiplication
  - Inverse of a transformation
  - Polynomial linear transformation

#### Matrix representation of a linear transformation

- (Def. 1.14) Matrix of a linear transformation
  $T(\mathbf{x}\_1, \mathbf{x}\_2, \dots, \mathbf{x}\_{n}) = (\mathbf{x}\_1, \mathbf{x}\_2, \dots, \mathbf{x}\_{n})A$
- Matrices of special transformations
  - $O$ and $T\_{0}$
  - $I$ and $T\_{e}$
  - $mI$ and $T\_{m}$
- (Example 1.16) If $A$ is the matrix of $T$, then
  - $\operatorname{dim}(R(T)) = \operatorname{dim}(R(A))$
  - $\operatorname{dim}(N(T)) = \operatorname{dim}(N(A))$
  - $\operatorname{dim}(R(T)) + \operatorname{dim}(N(T)) = n$
- (Thm. 1.9) Relation between the arithmetic of linear transformation and that of matrix of linear transformation
  - Polynomial of linear transformation and polynomial of matrix
- (Thm. 1.10) If $A$ is the matrix of linear transformation $T$, for a given set of bases, then the coordinate of $T \mathbf{x}$ equals to $A$ multiply the coordinate of $\mathbf{x}$.
- (Thm. 1.11) Let $T$ be a linear transformation of $V^n$, and $A$ and $B$ are the matrix of $T$ (respectively) with respect to two bases $\mathbf{x}\_1, \mathbf{x}\_2, \dots, \mathbf{x}\_{n}$ and $\mathbf{y}\_1, \mathbf{y}\_2, \dots, \mathbf{y}\_{n}$, and

  $$
  (\mathbf{y}\_1, \mathbf{y}\_2, \dots, \mathbf{y}\_{n}) = (\mathbf{x}\_1, \mathbf{x}\_2, \dots, \mathbf{x}\_{n})C
  $$

  then

  $$
  B = C^{-1} A C
  $$
- (Def. 1.15) Similarity $A \sim B$
  - It is a equivalence relationship
  - Similarity partitions the set $M\_n$ into disjoint equivalence classes
- (Example 1.17) If $f(t)$ is a polynomial on field $K$ and $B = P^{-1}AP$, then $f(B) = P^{-1} f(A) P$

#### Eigenvalues and eigenvectors

- (Def. 1.16) Eigenvalue and eigenvector $T \mathbf{x}= \lambda\_{0} \mathbf{x}$
  - Eigenvalue is uniquely determined by eigenvector, but the inverse doesn't establish
- (Def. 1.17) Characteristic matrix, characteristic polynomial $\phi\_A(\lambda) = \operatorname{det}(\lambda I - A)$
  - (Example 1.18) (the fundamental system of solutions)
  - $V\_{\lambda\_{0}} = \\{ \mathbf{x}\ |\ T \mathbf{\mathbf{x}}= \lambda\_{0} \mathbf{x},\ \mathbf{x} \in V^n  \\}$ is a subspace of $V^n$
- (Def. 1.18) Eigenspace.
- Trace of a matrix $A$, $\operatorname{tr}(A)$ is the sum of its main diagonal entries
  - The sum of all eigenvalues of $A$ is $\operatorname{tr}(A)$
  - The product of all eigenvalues of $A$ is $\operatorname{det}(A)$
- (Thm. 1.12) $\operatorname{tr}(AB) = \operatorname{tr}(BA)$
- (Thm. 1.13) Similar matrixes have the same trace
- (Thm. 1.14) Similar matrixes have the same characteristic matrix and therefore the same eigenvalues
- (Thm. 1.15) If $A = \operatorname{diag}(A\_{1}, A\_{2}, dots, A\_{m})$, then $\operatorname{det}(\lambda I - A)$ is equal to the porduct of $\operatorname{det}(\lambda I\_i - A\_i)$, $i \in \\{ 1 \dots n \\}$
- (Thm. 1.16)(Sylvester) If $A \in R^{m \times n}$, $B \in R^{n \times m}$, then $\lambda^{n}\phi\_{AB}(\lambda) = \lambda^{m}\phi\_{BA}(\lambda)$
- (Thm. 1.17) Every square matrix is similar to triangular matrix.
  - (Example 1.19) Example
- (Thm. 1.18)(Hamilton-Cayley) $n \times n$ matrix $A$ is a root of its characteristic polynomial, that is, if

  $$
  \phi(\lambda) = \operatorname{det}(\lambda I - A) = \lambda^{n} + a\_{1}\lambda^{n-1}+ \cdots + a\_{n-1}\lambda + a\_n
  $$

  then

  $$
  \phi(A) = A^{n} + a\_{1}A^{n-1}+ \cdots + a\_{n-1}A + a\_nI = O
  $$

  - (Example 1.20) Example of application
- (Def. 1.19) Minimal polynomial $m(\lambda)$
- (Thm. 1.19) The minimal polynomial $m(\lambda)$ of $A$ can divide any monic polynomial $\psi(\lambda)$ with root $A$, and $m(\lambda)$ is unique.
  - (Example 1.22) Similar matrixes have the same minimal polynomial.
  - Having the same minimal polynomial is necessary for two matrixes to be similar, but not sufficient.
- (Thm. 1.20) The minimal polynomial and characteristic polynomial of $A$ has the same set of roots.
- (Thm. 1.21) Let $\phi(\lambda)$ be the characteristic polynomial of $n \times n$ square matrix $A$, and $d(\lambda)$ is the greatest common factor of polynomials of all the minors of characteristic matrix $\lambda I - A$. Then the minimal polynomial $m(\lambda)$ is

  $$
  m(\lambda) = \frac{\phi(\lambda)}{d(\lambda)}
  $$
- (Thm. 1.22)If $\lambda\_{1}, \lambda\_{2}, \dots, \lambda\_{s}$ are the distinct eigenvalues of $A$, and $x\_{1}, x\_{2}, \dots, x\_{s}$ are their eigenvectors respectively, then $x\_{1}, x\_{2}, \dots, x\_{s}$ are linear independent.
- (Thm. 1.23)If $\lambda\_{1}, \lambda\_{2}, \dots, \lambda\_{k}$ are the distinct eigenvalues of $A$, and $x\_{i1}, x\_{i2}, \dots, x\_{i r\_{i}}$ are eigenvectors of $\lambda\_i$, then $x\_{11}, \dots, x\_{1 r\_1}, \dots, x\_{k1}, \dots,  x\_{k r\_k}$ are linear independent.

#### Diagonal matrix

- (Thm. 1.24) If $T$ is the linear transformation of $V^n$, and matrix $A$ of $T$ can be a diagonal matrix in some bases iff. $T$ has $n$ linear independent eigenvectors.
- (Thm. 1.25) $A$ is similar to a diagonal matrix iff. $A$ has $n$ linear independent eigenvectors.
- (Thm. 1.26) If $n \times n$ matrix $A$ has $n$ distinct eigenvalues, then it is similar to a diagonal matrix.

#### Invariant subspace

- (Def. 1.20) Invariant subspace
  - The intersection and sum of invariant subspaces are still invariant subspaces
  - Range $R(T)$ and kernel $N(T)$ of linear transformation $T$ is the invariant subspaces of $T$
- (Thm. 1.27) Use invariant subspace to simplify a matrix of linear transformation.
  - (Cor) A matrix $A$ of $T$ is diagonal matrix in some bases iff. $V^n$ can be divided into the sum of $n$ one-dimension characteristic subspaces.
  - (Cor) If $\lambda\_{1}, \lambda\_{2}, \dots, \lambda\_{s}$ are all distinct eigenvalues of $T$, then the matrix of $T$ is diagonal in some bases iff. $\operatorname{dim}(V\_{\lambda\_{1}}) + \operatorname{dim}(V\_{\lambda\_{2}})+ \cdots + \operatorname{dim}(V\_{\lambda\_{s}}) = n$

#### Jordan normal form introduction

- (Thm. 1.28)(Def. 1.21) Jordan normal form
- (Thm. 1.29) A complex matrix $A$ is similar to a matrix $J$ in Jordan normal form
- Polynomial matrix
- Smith normal form of a polynomial matrix
  - Invariant factors $d\_i(\lambda)$
  - I-th determinant divisor $D\_i(\lambda)$

    $$
    d\_i(\lambda) = \frac{D\_i(\lambda)}{D\_{i-1}(\lambda)}, \ \ D\_0(\lambda) = 1 ,\ \ (i = 1,2,\dots,s)
    $$
  - Elementary divisor
  - How to determine?
- How to determine Jordan normal form of a matrix
- (Thm. 1.30) Every $n \times n$ matrix $A$ is similar to a Jordan normal form matrix $J$, $A$ determine the $J$ except for the order of Jordan blocks in it.
- How to calculate $P$ in $P^{-1} A P = J$

### Section 1.3 Euclid space and unitary space

![Seciton_1_3](images/section_1_3.i.svg)

#### Euclid space

- (Def. 1.22) Euclid space (real inner product space)
  - Basic properties
    - $(\sum\_{i=1}^{n} \xi\_i \\mathbf{x}\_{i}, \sum\_{j = 1}^{n} \eta\_j \mathbf{y}\_{j} ) = \sum\_{i,j=1}^{n} \xi\_i \eta\_j (\mathbf{x}\_{i}, \mathbf{y}\_{j})$
  - Gram matrix: symmetric positive definite matrix
    - If $A$ is nonsingular, then $A^t A$ is symmetric positive definite
- (Def. 1.23) Norm in Eculid space
  - Unit vector
  - Unitize (normalize)
  - Cauchy–Bunyakovsky–Schwarz inequality
- (Def. 1.24) The angle $\langle \mathbf{x} , \mathbf{y} \rangle$ between $\mathbf{x}$ and $\mathbf{y}$.

#### Orthogonality

- (Def. 1.25) Orthogonality and perpendicularity
- (Def. 1.26) Orthogonal set of vectors
- (Thm. 1.31) If $\mathbf{x}$ and $\mathbf{y}$ are otrhogonal, then $|\mathbf{x} + \mathbf{y}|^2 = |\mathbf{x}|^2 + |\mathbf{y}|^2$.
- (Thm. 1.32) If $\mathbf{x}\_1, \mathbf{x}\_2, \dots, \mathbf{x}\_{m}$ are set of orthogonal vectors, then the are lineary independent.
- (Def. 1.27) Orthogonal basis and orthonormal basis
  - $\mathbf{x}\_1, \mathbf{x}\_2, \dots, \mathbf{x}\_{n}$ are orthonormal iff. their Gram matrix is unit matrix ($XX^T = I$).
  - Kronecker symbol $\sigma\_{ij}$
  - If $\mathbf{x}\_1, \mathbf{x}\_2, \dots, \mathbf{x}\_{n}$ is a set of basis, and $\mathbf{x} = \xi\_1 \mathbf{x}\_1 + \xi\_2 \mathbf{x}\_2 + \cdots + \xi\_n \mathbf{x}\_n$, then $\xi\_i = (\mathbf{x}\_{i}, \mathbf{x})$
- (Thm. 1.33) The Gram-Schmidt Process
  - Orthogonalization (orthonormalization)
- Property of Eculid space
  - If every vector in $\mathbf{x}\_1, \mathbf{x}\_2, \dots, \mathbf{x}\_{m}$ is orthogonal to $\mathbf{y}$, then the linear combination of $\mathbf{x}\_1, \mathbf{x}\_2, \dots, \mathbf{x}\_{m}$ is orthogonal to $\mathbf{y}$.
  - If $V\_1$ is a subspace of Eculid space $V^n$, then $\mathbf{y} \perp V\_1$  iff. $\mathbf{y}$ is orthogonal to vecotrs in the basis of $V\_1$
- (Thm. 1.34) Every Eculid space $V^n$ is the direct sum of its subspace $V\_1$ and $V\_1^\perp$.
  - Orthogonal complement
  - (Lem.) $\operatorname{dim}(V\_1) + \operatorname{dim}(V\_1^{\perp}) = n$.
- (Thm. 1.35) For any matrix $A = (a\_{ij})\_{m \times n} \in \mathbb{R}^{m \times n}$, we have
  - $R(A)^\perp = N(A^T), R(A) \oplus N(A^T) = \mathbb{R}^{m}$
  - $R(A^T)^\perp = N(A), R(A^T) \oplus N(A) = \mathbb{R}^{n}$
  - If $A = (a\_{ij})\_{m \times n} \in \mathbb{C}^{m \times n}$, it still establishes when replacing $A^T$ with $A^H$

#### Orthogonal transformation and orthogonal matrix

- (Def. 1.28) (In Eculid space) Orthogonal transformation $(\mathbf{x}, \mathbf{x}) = (T \mathbf{x}, T \mathbf{x})$
- (Thm. 1.36) (In Eculid space) $T$ is orthogonal transformation iff. $(\mathbf{x - y}, \mathbf{x - y}) = (T \mathbf{(x-y)}, T \mathbf{(x-y)})$
- (Def. 1.29) Orthogonal matrix $Q^TQ = I$
- (Thm. 1.37) (In Eculid space) $T$ is orthogonal transformation iff. its matrix is orthogonal matrix w.r.t. orthonormal basis.
  - (Lem.) Orthogonal matrix is nonsingular
  - (Lem.) The inverse matrix of orthogonal matrix is still orthogonal matrix
  - (Lem.) The product of two orthogonal matrices are still orthogonal matrix

#### Symmetric transofrmation and symmetric matrix

- (Def. 1.30) (In Eculid space) Symmetric transformation $(T\mathbf{x}, \mathbf{y}) = (\mathbf{x}, T \mathbf{y})$
- (Thm. 1.38) (In Eculid space) $T$ is real symmetric transformation iff. its matrix is real symmetric matrix w.r.t orthonormal basis.
- (Thm. 1.39) The egienvalues of real symmetric matrix are real.
- (Thm. 1.40) The eigenvectors of distinct eigenvalues of real symmetric matrix are orthogonal.

#### Unitary space

- (Def. 1.31) Unitary space (complex inner product space)
  - Eg: $(\mathbf{x}, \mathbf{y}) = \mathbf{x} \mathbf{y}^H$
  - Properties: similarly with those in Eculid space, except:
    - Orthogonal transformation -> unitary transformation
    - $A^TA = I$ (Orthogonal matrix) -> $A^HA = I$ (unitary matrix)
    - Symmetric transformation -> Hermite (Hermitian) transofrmation (unitary symmetric transofrmation)
    - Orthogonal matrix -> Hermite matrix ($A^H = A$)
    - Eigenvalues of Hermite matrix are real, and the eigenvectors of distinct eigenvalues are orthogonal.
- (Thm. 1.41) (Schur)
  - If $A \in \mathbb{C}^{n  \times n}$, then there exists unitary matrix $P$ such that $P^H A P = T$, where $T$ is a triangular matrix with eigenvalues of $A$.
  - If $A \in \mathbb{R}^{n  \times n}$, then there exists orthogonal matrix $P$ such that $P^H A P = T$, where $T$ is a triangular matrix with eigenvalues of $A$.
- (Def. 1.32) $A \in \mathbb{C}^{n  \times n}$, and $A^H A = A A^H$, then $A$ is normal.
  - It's obviously that orthogonal matrix, unitary matrix, diagonal matrix, real symmetric matrix and Hermite matrix are normal.
- (Thm. 1.42)
  - Let $A \in \mathbb{C}^{n  \times n}$, then $A = U^H D U$ (where $U$ is unitary matrix and $D$ is diagonal matrix) iff. $A$ is normal
  - Let $A \in \mathbb{R}^{n  \times n}$, then $A = B^T D B$ (where $B$ is orthogonal matrix and $D$ is diagonal matrix) iff. $A$ is normal.
  - (Cor.) If $A$ is a real symmetric matrix, then $A = B^TDB$ where $B$ is orthogonal matrix.
  - (Cor.) If $T$ is a symmetric transformation in Eculid space $V^n$, then $V^n$ exists a set of orthonormal basis s.t. the matrix of $T$ is diagonal.
- Eigendecomposition (spectral decomposition)

## Chapter 2 Norm

### Section 2.1 Vector norm

#### Vector norm

- (Def. 2.1) Vector norm.
  - norm on $\mathbb{C}^{n}(\mathbb{R}^{n})$
    - 1-norm $\\| \cdot \\|\_2$
    - 2-norm (Eculid norm) $\\| \cdot \\|\_2$
    - $\infty$-norm (Eculid norm) $\\| \cdot \\|\_\infty$
    - $p$-norm ($l\_p$ norm) $\\| \mathbf{x} \\|\_p$
      - $(\sum\_{i=1}^{n} |\xi\_i|^p)^{1/p} (1 \leq p < + \infty)$ (By Holder inequality)
      - Some times 1-norm, 2-norm, $\infty$-norm are called $l\_1$, $l\_2$, $l\_\infty$ norm resepctively.
    - weighted norm $\\| \cdot \\|\_A = (\mathbf{x}^T A \mathbf{x})^{1/2}$
  - For a given linear space $V^n$ and its basis $\mathbf{x}\_1, \mathbf{x}\_2, \dots, \mathbf{x}\_{n}$, and assuming the coordinate of $\mathbf{x} \in V^n$ is $(\xi\_1, \xi\_2, \cdots, \xi\_n)^T$, then
    - $p$-norm: $\\| \cdot \\|\_p = \\| (\xi\_1, \xi\_2, \cdots, \xi\_n)^T \\|\_p \ \ (1 \leq p < + \infty)$

#### The equivalence of vector norms in linear space $V^n$

- (Thm. 2.1) Let $\\| \cdot \\|\_\alpha$ and $\\| \cdot \\|\_\beta$ are two vector norm (not limited to $p$-norm), then there exits two postive const $c\_1$ and $c\_2$ which are independent to $\mathbf{x}$ such that the inequality
  
  $$
  c\_1 \\| \mathbf{x} \\|\_\beta \leq \\| \mathbf{x} \\|\_\alpha \leq c\_2 \\| \mathbf{x} \\|\_\beta \ \ (\forall \mathbf{x} \in V)
  $$

  establishes.

- (Def. 2.2) Two norms satisfying the inequality above are called equivalent.
- Rephrasing (Thm. 2.1): Norms of finite dimensional vector spaces are equivalent.
- (Thm. 2.2) Pass

### Section 2.2 Matrix norm

- (Def. 2.3) Let $A \in C^{m \times n}$, if a real-valued function $\\| A \\|$ satisfies:
  - Nonnegative-valued
  - Absolutely homogeneous
  - Sub-additive or satisfying the triangle inequality
  - Sub-multiplicative
  - If sub-multiplicative is not satisfied, it is called generalized matrix norm or vector norm on matrices.
- (Def. 2.4) For a matrix norm $\\| \cdot \\|\_M$ on $\mathbb{C}^{m \times n}$ and a vector norm with the same rules $\\| \cdot \\|\_V$ on $\mathbb{C}^{m}$ and $\mathbb{C}^{m}$, if
  
  $$
  \\| A \mathbf{x} \\|\_V \leq \\| A \\|\_M \\| \mathbf{x} \\|\_V
  $$

  then they are compatible.

- $F$-norm (Frobenius norm): $\\| A \\|\_F = (\sum\_{i=1}^{m}\sum\_{j=1}^{n} |a\_{ij}|^2)^{1/2} = (\operatorname{tr}(A^HA))^{1/2}$
- (Thm. 2.3) Let $A \in C^{m \times n}$, $P$ and $Q$ be unitary matrix, then $\\| PA \\|\_F = \\| A \\|\_F = \\| AQ \\|\_F$
  - (Cor.) If $B = Q^HAQ$ and $Q$ is unitary matrix, then $\\| A \\|\_F = \\| B \\|\_F$
- (Eg. 2.9) Let $\\| \cdot \\|\_M$ be a matrix norm on $\mathbb{C}^{n \times n}$ and $\mathbf{y}$ be nonzero vector in $\mathbb{C}^{n}$, then the function
  
  $$
  \\| \mathbf{x} \\|\_V = \\| \mathbf{x} \mathbf{y}^H \\|\_M \ \ (\forall \mathbf{x} \in \mathbb{C}^{n})
  $$

  is a vector norm on $\mathbb{C}^{n}$, and $\\| \cdot \\|\_M$ and $\\| \cdot \\|\_V$ are compatible

#### Some common matrix norms

- (Thm. 2.4) For a norm $\\| \cdot \\|$ on $\mathbb{C}^{m}$ and $\mathbb{C}^{n}$, let $A \in C^{m \times n}$, then

  $$
  \\| A \\| = \operatorname{max}\_{\\| \mathbf{x} \\| = 1 } \\| A \mathbf{x} \\|
  $$

  is a norm on $\mathbb{C}^{m \times n}$, and is compatible with the vector norm above.

  - The matrix norm defined above is called the matrix norm induced by vector norm.
- (Thm. 2.5) Let $A \in \mathbb{C}^{m \times n}$, then the three matrix norms induced by the vector norms $\\| \vec{x} \\|\_1$, $\\| \vec{x} \\|\_2$, $\\| \vec{x} \\|\_\infty$ on $\mathbb{C}^{n}$ are (respectively):
  - $\\| A \\|\_1 = \operatorname{max}\_j \sum\_{i=1}^{n} |a\_{ij}|$
  - (Spectral norm) $\\| A \\|\_2 = (\lambda\_1)^{1/2}$, where $\lambda\_1$ is the max eigenvalue of $A^HA$
  - $\\| A \\|\_\infty= \operatorname{max}\_i \sum\_{i=1}^{n} |a\_{ij}|$

### Section 2.3 Application

#### Nonsingular condition

- (Thm. 2.6) Let $A \in \mathbb{C}^{n \times n}$, and $\\| A \\| < 1$ form some matrix norm on $\mathbb{C}^{n \times n}$, then matrix $I-A$ is nonsingular and

  $$
  \\| (I-A)^{-1} \\| \leq \frac{\\| I \\|}{1 - \\| A \\|}
  $$

  - (Thm. 2.7) and

    $$
    \\|I - (I-A)^{-1} \\| \leq \frac{\\| A \\|}{1 - \\| A \\|}
    $$

#### Spectral radius

- (Def. 2.5) Let $\lambda\_1, \lambda\_2, \cdots, \lambda\_n$ be eigenvalues of $A \in \mathbb{C}^{n \times n}$, then

  $$
  \rho(A) = \operatorname{max}\_{i} |\lambda\_i|
  $$

  is called the spectral radius of $A$

- (Thm. 2.9) Let $A \in \mathbb{C}^{n \times n}$, then for any matrix norm $\\| \cdot \\|$ on $\mathbb{C}^{n \times n}$, we have:

  $$
  \rho(A) \leq \\| A \\|
  $$

- (Thm. 2.10) Let $A \in \mathbb{C}^{n \times n}$, then for any positive number $\epsilon$, there exists some matrix norm $\\| \cdot \\|\_M$, such that

  $$
  \\| A \\|\_M \leq \rho(A) + \epsilon
  $$
