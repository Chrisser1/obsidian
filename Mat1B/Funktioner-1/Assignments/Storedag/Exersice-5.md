![[Pasted image 20250205104714.png]]

![[Pasted image 20250205104727.png]]

#### Answer
To find the 3 coordinate functions $f$, we need to compute the product $Ax$ where $A$ is the given $3 \times 5$ matrix and $x$ is a column vector in $\mathbb{R}^5$:
$$
x = \begin{bmatrix} x_1 \\ x_2 \\ x_3 \\ x_4 \\ x_5 \end{bmatrix}
$$
We can now compute the matrix-vector product $f(x)=Ax$
$$
	Ax = \begin{bmatrix} 1 & 0 & 2 & 3 & 4 \\ 0 & -1 & 5 & 6 & 7 \\ 0  & 0 & -3 & 8 & 9 \end{bmatrix} \begin{bmatrix} x_1 \\ x_2 \\ x_3 \\ x_4 \\ x_5 \end{bmatrix}
$$
Now we can compute the for each row:
1. First row: $1x_1 + 2x_3 + 3x_4 + 4x5$
2. Second row: $-1x_2 + 5x_3 + 6x_4 + 7x_5$
3. Third row: $-3x_3 + 8x_4 + 9x_5$

Thus, the three coordinate functions of $f$ are:
$$
f_1(x) = 1x_1 + 2x_3 + 3x_4 + 4x5
$$
$$
f_2(x) = -1x_2 + 5x_3 + 6x_4 + 7x_5
$$
$$
f_3(x) = -3x_3 + 8x_4 + 9x_5
$$
![[Pasted image 20250205105917.png]]
#### Answer
To determine the image of $f$, we need to find the column space of the matrix A, which corresponds to the span of its column vectors.

**Rank of A**
The rank of A is the number of linearly independent columns. What we can observe is that the three rows cannot be reduced further, so we can quickly note that the rank is 3, meaning that the column space of $A$ is a **3-dimensional subspace** of $\mathbb{R}^3$.

**Column Space of A**
The column space of $A$, denoted as $col(A)$, is the span of the linearly independent columns of A. Since the rank is 3, three of the five columns form a basis for the column space.

To find a basis, we extract the linearly independent columns of A, but as we noted we could not reduce the matrix further, so the basis vectors are.
$$
\begin{bmatrix} 1 \\ 0 \\ 0 \end{bmatrix}, \begin{bmatrix} 0 \\ -1 \\ 0 \end{bmatrix}, \begin{bmatrix} 2 \\ 5 \\ -3 \end{bmatrix}
$$
Thus, the image of $f$ is the subspace of $\mathbb{R}^3$ spanned by these three vectors. This means:
$$
im(f)=col(A)=span(\begin{bmatrix} 1 \\ 0 \\ 0 \end{bmatrix}, \begin{bmatrix} 0 \\ -1 \\ 0 \end{bmatrix}, \begin{bmatrix} 2 \\ 5 \\ -3 \end{bmatrix})
$$
![[Pasted image 20250205111100.png]]
#### Answer
**Surjectivity (Onto)**
A function $f:\mathbb{R}^5 \to \mathbb{R}^3$ is **surjective** if its image (column space of $A$) covers all of $\mathbb{R}^3$, meaning that:

$$rank(A)= \dim(\mathbb{R}^3) =3$$

From our previous calculation, we found that:

$$rank(A)=3$$
Since the rank of $A$ equals the dimension of $\mathbb{R}^3$, the column space of $A$ spans all of $\mathbb{R}^3$. This means $f$ is **surjective**.

**Injectivity (One-to-One)**

A function $f:\mathbb{R}^5 \to \mathbb{R}^3$ is **injective** if its kernel (null space) contains only the zero vector, meaning:

$$nullity(A)=0$$
Using the **rank-nullity theorem**:

$$rank(A)+nullity(A)=dim(\mathbb{R}^5)$$
$$3+nullity(A)=5$$
$$nullity(A)=2$$
Since the nullity is greater than 0, there exists a non-trivial kernel, meaning there are infinitely many solutions to Ax=0Ax = 0Ax=0. This implies that $f$ is **not injective**.

