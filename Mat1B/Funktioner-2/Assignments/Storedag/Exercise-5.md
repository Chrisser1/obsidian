![[Pasted image 20250211141208.png]]
#### Answer
We start off by considering the two equations:
1. $f:\mathbb{R}^{2 \times 2} \to \mathbb{R}^{2 \times 2}$
We first check for linearity by verifying that: 
$$
f(X+Y) = f(X) + f(Y) \quad \text{and} \quad f(aX) = af(X)
$$
expanding:
$$
f(X+Y) = C(X+Y)B = CXB+CYB=f(X)+f(Y)
$$
and for multiplicity
$$
f(aX)=C(aX)B=aCXB=af(X).
$$
Thus, $f$ is a linear transformation.

Given the standard basis matrices:

$$
E = \left\{\begin{bmatrix}1 & 0\\0 & 0\end{bmatrix}, \begin{bmatrix}0 & 1\\0 & 0\end{bmatrix}, \begin{bmatrix}0 & 0\\1 & 0\end{bmatrix}, \begin{bmatrix}0 & 0\\0 & 1\end{bmatrix}\right\},
$$

we compute $f(E_i)$ to construct the transformation matrix.

For each basis matrix $E_i$:

$$
f\left(\begin{bmatrix}1 & 0\\0 & 0\end{bmatrix}\right) = C \begin{bmatrix}1 & 0\\0 & 0\end{bmatrix} B = \begin{bmatrix}2 & 2\\0 & 0\end{bmatrix},
$$

$$
f\left(\begin{bmatrix}0 & 1\\0 & 0\end{bmatrix}\right) = C \begin{bmatrix}0 & 1\\0 & 0\end{bmatrix} B = \begin{bmatrix}0 & 2\\0 & 0\end{bmatrix},
$$

$$
f\left(\begin{bmatrix}0 & 0\\1 & 0\end{bmatrix}\right) = C \begin{bmatrix}0 & 0\\1 & 0\end{bmatrix} B = \begin{bmatrix}0 & 0\\1 & 1\end{bmatrix},
$$

$$
f\left(\begin{bmatrix}0 & 0\\0 & 1\end{bmatrix}\right) = C \begin{bmatrix}0 & 0\\0 & 1\end{bmatrix} B = \begin{bmatrix}0 & 0\\0 & 1\end{bmatrix}.
$$

Thus, the transformation matrix is given by:

$$
[T_f]_{E} = \begin{bmatrix}2 & 0 & 0 & 0\\2 & 2 & 0 & 0\\0 & 0 & 1 & 0\\0 & 0 & 1 & 1\end{bmatrix}.
$$
1. $g:\mathbb{R}^{n} \to \mathbb{R}$
This function is not linear because it does not satisfy additivity:
$$
g(x+y) = (x+y)^T A (x+y) \neq x^T A x + y^T A y
$$
Since it contains quadratic terms, g is not a linear mapping.

