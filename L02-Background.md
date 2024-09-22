# Math for Transformers
**Second lecture: Fri Sep 20**  
Scribe: Angelos Poulis

Let $A \in \mathbb{R}^{m \times n}$, then $\text{col}(A)$ is the set of vectors that are linear combinations of the columns of $A$, i.e.,  

$$\text{col}(A) = \{ Ax \mid x \in \mathbb{R}^n \}$$  

It follows that:  

$$Ax + Ay = A(x + y)$$  

The null space of $A$ is defined as:  

$$\text{Nul}(A) = \{x \mid Ax = 0\}$$  

Any vector $y \in \mathbb{R}^n$ can be written as $y = z + c$, where $z \in \text{Nul}(A)$ and $Ac = y$. Thus, the general solution to $Ax = 0$ involves adding any vector from the null space to a particular solution.

## Projections

* $P_H x$ represents the projection of $x$ onto subspace $H$.
* The projection matrix $P$ satisfies:
  $$P^2 = P$$ and $$P(Px) = Px$$
* **Oblique projector**: A projector that is not necessarily orthogonal to the subspace.
* **Orthogonal projector**: A projector where $P$ is symmetric, i.e., $P = P^T$. 
($P_{symm} \leftrightarrow P$ is orthogonal projector.)

### Finding the Orthogonal Projector

**Given a subspace $H$, how do we find the orthogonal projector onto $H$?**   

Describe the subspace using a basis for $H$. For any vector $x$, the projection $\hat{y} \in H$ satisfies $Ay = \hat{y}$. We know that $y - \hat{y} \perp H$, meaning $\hat{y}$ is the projection of $y$ onto $H$. Since $Ay - \hat{y} \perp$ every vector in $H$, we derive:  

$$A^T (y - \hat{y}) = 0$$  

Expanding this:

$$A^T y - A^T A \hat{y} = 0$$  

Solving for $\hat{y}$:  

$$\hat{y} = (A^T A)^{-1} A^T y$$  

Hence, the projection is:  

$$A \hat{y} = A (A^T A)^{-1} A^T y$$

If $A$ is orthonormal, the projection simplifies to:

$$P = AA^T$$

### Decomposing $x$

We can decompose any vector $x$ as:

$$x_s = P_H x$$

$$x_{s^{\perp}} = (I - P_H) x$$

Thus, we have:

$$x = x_s + x_{s^{\perp}}$$

Additionally, it holds:

$$(I - P_H)(I - P_H) = I^2 - 2P_H + P_H^2$$

## Homework

If $P$ is an orthogonal projector, then:

1. Prove that $I - 2P$ is an orthogonal matrix
2. Give geometric intuition

## Spectral Theorem

Let $A$ be a square matrix.

If $A$ is symmetric, then any two eigenvectors of $A$ with distinct eigenvalues are orthogonal.  $A$ can be diagonalized using its eigenvectors:

$$A = E \Lambda E^{-1}$$

where $E$ is the matrix of eigenvectors and $\Lambda$ is the diagonal matrix of eigenvalues.

Let $v_1, v_2$ be eigenvectors of $A$ with distinct eigenvalues $\lambda_1, \lambda_2$. Then the following hold:

$$\lambda_1 v_1^T v_2 = (\lambda_1 v_1)^T v_2 = (A v_1)^T v_2 = v_1^T A^T v_2 = v_1^T A v_2 = v_1^T \lambda_2 v_2 = \lambda_2 v_1^T v_2$$

This implies:

$$v_1^T v_2 = 0$$

Therefore, $v_1$ and $v_2$ are orthogonal.

Then, we can write the diagonalization as:

$$A = E \Lambda E^{-1} = P \Lambda P^T$$

where $P$ is an orthogonal matrix (since for symmetric matrices, $E^{-1} = P^T$).

## Courant-Fisher Theorem

Let $A$ be a symmetric matrix with eigenvalues $\lambda_1 \leq \dots \leq \lambda_n$.

The theorem states that:

$$\max_{\|x\| = 1} x^T A x = \lambda_n$$

where  $x^T A x$ is a bilinear form, and the maximum is taken over all unit vectors $x$. The eigenvalue $\lambda_n$ is the largest eigenvalue of the matrix $A$.

***Why it is an interesting theorem? -It connects Linear Algebra with Optimization.***
