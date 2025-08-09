Let $L: \mathbb{R}^n \to \mathbb{R}^k$ be a linear function. Then, for any scalars $c, d \in \mathbb{R}$ and vectors $x, y \in \mathbb{R}^n$, we have:
$$
L(c x + d y) = c L(x) + d L(y)
$$
where $L$ preserves addition and scalar multiplication.
### Matrix Representation of $L$
Since $L$ is a linear transformation, there exists a unique **$k \times n$ matrix** $A$ such that for any vector $x \in \mathbb{R}^n$:
$$
L(x) = A x
$$
where:
- $A$ is the **representation matrix** of $L$,

- Each column of $A$ represents the image of a standard basis vector under $L$,

- The transformation is computed using standard matrix-vector multiplication.

Thus, every linear transformation from $\mathbb{R}^n$ to $\mathbb{R}^k$ can be expressed in terms of a matrix multiplication.
### Example: Linear Map $\mathbb{R}^3 \to \mathbb{R}^2$
Given the linear transformation:
$$
L: \mathbb{R}^3 \to \mathbb{R}^2
$$
defined by:
$$
L(x_1, x_2, x_3) =

\begin{bmatrix}

    5x_1 - x_3 \\

    6x_2 + 7x_3

\end{bmatrix}
$$
The matrix representation of $L$ is:
$$
A = [L]_e^e =

\begin{bmatrix}

    5 & 0 & -1 \\

    0 & 6 & 7

\end{bmatrix}

\in \mathbb{R}^{2 \times 3}
$$
where $A$ represents the transformation in standard basis.