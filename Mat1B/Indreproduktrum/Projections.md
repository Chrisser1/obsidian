A vector can be projected (orthogonally) onto another vector as shown in figure in space $\mathbb{R}^2$ and $\mathbb{R}^3$:
![[Pasted image 20250218100255.png]]
Based on the image and the angle $\theta$ located at the meeting point between $x$ and $y$, we can say that:
$$
||proj_y(x)||=||x||\cdot cos(\theta) = \frac{\langle x,y \rangle}{||y||}
$$as $cos(\theta) = \frac{\langle x,y \rangle}{||x|| \cdot ||y||}$ just like we learned with rectangles.

### Example in $\mathbb{C}^4$
Consider the vector:
$$
y =
\begin{bmatrix}
0 \\
i \\
1 \\
1
\end{bmatrix}
$$
The subspace spanned by \( y \) is:
$$
Y = \text{span}(\{y\}) \subseteq \mathbb{C}^4
$$
The norm squared of \( y \) is:
$$
\|y\|^2 = |0|^2 + |i|^2 + |1|^2 + |1|^2 = 3
$$
The projection of a vector \( x \) onto \( Y \) is:
$$
\text{proj}_Y(x) = \frac{1}{3} \langle x, y \rangle y
$$
For example, consider:
$$
x =
\begin{bmatrix}
1 \\
0 \\
0 \\
0
\end{bmatrix}
\in \mathbb{C}^4
$$
Then, its projection onto $Y$ is:
$$
\text{proj}_Y(x) = \frac{1}{3} \langle x, y \rangle y
$$
Expanding further:
$$
	= \frac{1}{3} (0 - i)
\begin{bmatrix}
0 \\
i \\
1 \\
1
\end{bmatrix}
$$
Thus, we can express it as:

$$
= \frac{1}{3}
\begin{bmatrix}
0 & 1 & -i & -i
\end{bmatrix}^T
$$
