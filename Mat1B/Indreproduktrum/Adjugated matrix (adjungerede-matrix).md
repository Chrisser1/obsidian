Given the notation for $A \in M_{n\times m}(\mathbb{C})$. Then the adjugated matrix is given by:
$$
A^*=(\overline{A})^T=A^T \in M_{m \times n}(\mathbb{C})
$$
A adjugated matrix will always for fill that when $A \in M_{n\times m}(\mathbb{F})$:
$$
\langle Ax, y \rangle_{\mathbb{F}^m} = \langle x, A^*y \rangle_{\mathbb{F}^n}
$$
where $x \in \mathbb{F}^n, y \in \mathbb{F}^m$. Then for $\mathbb{F} = \mathbb{R}$ we have that:
$$
Ax \cdot y = x \cdot(A^Ty)
$$
### Specified:
For $$ x \in \mathbb{C}^{n \times 1} = M_{n \times 1}(\mathbb{C}), $$ its conjugate transpose is 
$$ 
x^* = \overline{x}^T = \begin{bmatrix} \overline{x}_1 & \overline{x}_2 & \dots & \overline{x}_n \end{bmatrix}. 
$$
### Example:
Let $$ A \in M_{2 \times 3}(\mathbb{C}) $$ be given by 
$$
A = \begin{bmatrix} 1+i & 2 & 3 \\ 3i & -1 & 1 \end{bmatrix}.
$$ Then, the conjugate transpose of $A$ is 
$$ 
A^* = \begin{bmatrix} 1-i & -3i \\ 2 & i \\ 3 & 1 \end{bmatrix}. 
$$
