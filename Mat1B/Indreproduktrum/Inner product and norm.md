![[Pasted image 20250218101057.png]]
### The Standard Inner Product
For $V = \mathbb{F}^n$ (either $\mathbb{R}^n$ or $\mathbb{C}^n$), the inner product is defined as:
$$

\langle x, y \rangle = \sum_{k=1}^{n} x_k \overline{y_k} = x_1 \overline{y_1} + x_2 \overline{y_2} + \dots + x_n \overline{y_n}

$$
- For $V = \mathbb{C}^n$, this is written using matrix notation as:
$$
\langle x, y \rangle = y^* x =

\begin{bmatrix} \overline{y_1} & \overline{y_2} & \dots & \overline{y_n} \end{bmatrix}

\begin{bmatrix} x_1 \\ x_2 \\ \vdots \\ x_n \end{bmatrix}
$$
- For $V = \mathbb{R}^n$, where all entries are real $(\overline{y_k} = y_k)$, the inner product simplifies to:
$$

\langle x, y \rangle = y^T x =

\begin{bmatrix} y_1 & y_2 & \dots & y_n \end{bmatrix}

\begin{bmatrix} x_1 \\ x_2 \\ \vdots \\ x_n \end{bmatrix}
$$
This notation highlights that in the real case, the conjugate transpose $y^*$ is simply the transpose $y^T$, making it a straightforward dot product.

![[Pasted image 20250218103955.png]]
![[Pasted image 20250218104148.png]]
![[Pasted image 20250218104420.png]]
### The Derived Norm of the Standard Inner Product
The derived norm of the standard inner product is given by:
For $x \in \mathbb{F}^n$,
$$
\|x\| = \sqrt{\langle x, x \rangle} = \sqrt{|x_1|^2 + |x_2|^2 + \dots + |x_n|^2}
$$
![[Pasted image 20250218110657.png]]
![[Pasted image 20250218110710.png]]
