$$
f: I \to \mathbb{R}
$$

Where $I$ can be intervals of the types $]-\infty, a[$, $]a,b[$, $]b,\infty[$, or $\mathbb{R}$.

### Poor Concept
$f$ is continuous at $x_0 \in I$ if and only if
$$
\begin{aligned}
f(x) \to f(x_0) & \quad\text{for}\quad x\to x_0 \\
|f(x) - f(x_0)| \to 0 & \quad\text{for}\quad |x - x_0| \to 0 \\
\end{aligned}
$$

### Better Concept
Consider the function
$$
f: I \to \mathbb{R}
$$

$f$ is continuous at $x_0 \in I$ if and only if:
For every $\epsilon > 0$, there exists a $\delta > 0$ such that
$$
|x - x_0| < \delta \implies |f(x) - f(x_0)| < \epsilon.
$$

Also written as:
$$
\forall\epsilon > 0\,\, \exists\delta > 0\,\, \forall x \in I : |x - x_0| < \delta \implies |f(x) - f(x_0)| < \epsilon.
$$
