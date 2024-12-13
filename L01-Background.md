# Lecture 1. Background of Linear Algebra

September 13, 2024

Scribe: Gabriel Franco

### Notation

$x$, $y$, $u$ and $v$ are vectors, $a$, $b$, $c$ are constants. $A$, $B$, $U$ are matrices.

Vectors $x_i$ are assumed to be column vectors.

$\mathbb{R}^{d}$ is the set of all vectors having $d$ components.

## Span

$\text{Span} \{ v_1, \cdots, v_p\}$ is the set of all linear combinations of $v_1, \cdots, v_p$: $a_1v_1 + \cdots + a_pv_p$.

## Subspaces

A subspace $H \in \mathbb{R}^d$ is a set of points with the following properties:
1) $0 \in H$ (origin is in the subspace)
2) $u, v \in H \to u + v \in H$ 
3) $a \in \mathbb{R}, u \in H \to au \in H$

Subspaces have the "Vegas" property: what happens in $H$, stays in $H$.

## Basis

We say that $\{v_1, \cdots, v_p\}$ form a __linearly independent__ set iff $\nexists\, a_1, \cdots, a_p$, not all zero, such that $a_1v_1 + \cdots + a_pv_p = 0$.

A basis for a subspace $H$ is a set of **linearly independent** vectors $v_1, \cdots, v_p \in H$ where $Span\{v_1, \cdots, v_p\} = H$.

Being a basis doesn't mean that the vectors are **orthogonal**.

### Dimension

It can be shown that any basis for a subspace has the same number of dimensions as any other.   

For example, any basis for $\mathbb{R}^2$ has two vectors.

The number of vectors in the basis for a subspace is called the _dimension_ of the subspace.

### Standard basis

The axes in a drawing of $\mathbb{R}^2$ are the standard basis for $\mathbb{R}^2$. We can write any two-dimensional points as a combination of $[0, 1]^T$ and $[1, 0]^T$ vectors.


## Linear independence

If $\{v_1, \cdots, v_p\}$ is a **dependent** set (not linearly independent), then $\exists v_i$ s.t. $v_i$ is a linear combination of the others.  Note that this holds for at least one vector, but not necessarily all of them.

## Inner Product

Given vectors $v_1 \in \mathbb{R}^d$ and $v_2 \in \mathbb{R}^d$:

$$v_1 \cdot v_2 = \sum_i^d v_{1, i} \cdot v_{2, i} = v_1^Tv_2$$

Then, we have that:

$\cos \theta = \frac{v_1^Tv_ 2}{||v_1||_2 \cdot ||v_2||_2}$, where $||v||_2 = \sqrt{v^Tv}$ (Euclidean length of the vector).

This implies that $v_1 \perp v_2 \leftrightarrow v_1^Tv_2 = 0$. That is, when inner product is zero, the vectors are __orthogonal__ (= perpendicular) and vice-versa.

## Orthonormal and Orthogonal Matrices 

Consider a set of orthogonal vectors $\{u_1, \cdots, u_p \,|\, u_i^Tu_j = 0, i \neq j\}$, where $||u_i|| = 1$, $u_i \in \mathbb{R}^d$, and $p \leq d$, $\forall i$. Then, let $U = [u_1, \cdots, u_p]$ be a matrix constructed by these vectors, where each column of this matrix is one of these vectors. Then, we have that $U^TU = I$. We call $U$ an **orthonormal matrix**. When U is square, this matrix is called **orthogonal matrix**.

Let $x, y \in \mathbb{R}^p$ be two vectors where $x^Ty = a$. Also let $U \in \mathbb{R}^{d \times p}$ be a **orthonormal matrix**. Then, we have that $x^TU^TUy = x^Ty = a$. 

So, multiplying the points by the **orthonormal matrix** does not change lengths of vectors (distance of points from origin) or the distance and angles between the vectors. 

However, this does not mean that the new points are **exactly** the same. For one thing, if $U$ is not square, then the new points are in a higher dimensional space.  And in the case that $U$ is **orthogonal** (orthonormal and square), it means that $U$ is rotating the points and possibly reflecting some of the axes.   In other words, the only operations that can be done to a set of points that do not change distances between the points are rotation and reflection.