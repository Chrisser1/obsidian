![[Pasted image 20250211133818.png]]
#### Answer
Let $L: \mathbb{R}^n \to \mathbb{R}$ be a linear mapping. By definition of linearity, we know that for any vector $x \in \mathbb{R}^n$, the mapping $L$ satisfies:
$$L(a x + b y) = a L(x) + b L(y)$$
for all $x, y \in \mathbb{R}^n$ and all scalars $a, b \in \mathbb{R}$.

**Expressing $L(x)$ in terms of basis vectors**
Let $e_1, e_2, \dots, e_n$ be the standard basis of $\mathbb{R}^n$. Since $L$ is linear, we can express $L$ in terms of its action on these basis vectors:

$$L(e_i) = c_i, \quad i = 1, 2, \dots, n$$
for some scalars $c_1, c_2, \dots, c_n \in \mathbb{R}$.
Now, any vector $x \in \mathbb{R}^n$ can be written as a linear combination of the basis vectors:
$$x = x_1 e_1 + x_2 e_2 + \dots + x_n e_n.$$
Applying the linearity of $L$, we get:
$$L(x) = L(x_1 e_1 + x_2 e_2 + \dots + x_n e_n).$$
Using linearity, this simplifies to:
$$L(x) = x_1 L(e_1) + x_2 L(e_2) + \dots + x_n L(e_n).$$
Substituting $L(e_i) = c_i$, we obtain:
$$L(x) = x_1 c_1 + x_2 c_2 + \dots + x_n c_n.$$
 **Expressing  $L(x)$ using Inner Product Notation**
Rewriting in vector notation, let 
$$c = \begin{bmatrix} c_1 \\ c_2 \\ \vdots \\ c_n \end{bmatrix} \in \mathbb{R}^n, \quad x = \begin{bmatrix} x_1 \\ x_2 \\ \vdots \\ x_n \end{bmatrix} \in \mathbb{R}^n.$$
Then we can express $L(x)$ as:
$$L(x) = c^T x,$$
which is precisely the standard inner product notation:
$$L(x) = \langle x, c \rangle.$$
### Conclusion
We have shown that there exists a unique column vector $c \in \mathbb{R}^n$ such that:

$$L(x) = \langle x, c \rangle,$$
which completes the proof.
