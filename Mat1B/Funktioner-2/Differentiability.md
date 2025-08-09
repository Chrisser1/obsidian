#### Differential coefficient:
$$
f'(x_0)=lim_{h \to 0}\frac{f(x_0+h)-f(x_0)}{h}
$$
Can be written as a matrix on the form:
$$
\underline{f}(\underline{x}) = \begin{bmatrix} f_1(\underline{x}) \\  f_2(\underline{x}) \\ \vdots \\ f_k(\underline{x})\end{bmatrix}
$$
![[Pasted image 20250211111408.png]]
![[Pasted image 20250211112236.png]]
![[Pasted image 20250211112251.png]]
[[Jacobian-matrix]]
![[Pasted image 20250211113017.png]]
If you are interested in the growth of a function you can look at the function above in definition 3.8.1 and we get:
For $f(x)$, we have:
$$
f(x_0 + h) - f(x_0) = L(h) + \varepsilon(h) \| h \|
$$
where:
- $L(h)$ represents the **linear part** of the transformation.
$$
L(h) = \begin{cases}
f(x_0)^Th & k=1 \\
J_f(x_0)h & k,n \in \mathbb{N} \\
f'(x_0)h & k=1,n=1
\end{cases}
$$
- $\varepsilon(h) \| h \|$ is the **small error term** that vanishes faster than $h$ as $h \to 0$.
- This approximation is valid for small $h$.

![[Pasted image 20250211113624.png]]
