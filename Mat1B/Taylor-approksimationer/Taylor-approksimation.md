Denne del bygger meget på [[Differentiability]] hvor vi havde, at:
For $f(x)$, we have:
$$
f(x_0 + h) - f(x_0) = L(h) + \varepsilon(h) \| h \|
$$
where:
- $L(h)$ represents the **linear part** of the transformation.
$$
L(h) = \begin{cases}
\nabla f(x_0)^Th & k=1 \\
J_f(x_0)h & k,n \in \mathbb{N} \\
f'(x_0)h & k=1,n=1
\end{cases}
$$
- $\varepsilon(h) \| h \|$ is the **small error term** that vanishes faster than $h$ as $h \to 0$.
- This approximation is valid for small $h$.
Then we can write $f(x_0+h)$ as:
$$
f(x_0 + h) = f(x_0) = J_f(x_0)h + \varepsilon(h) \| h \|
$$
where $h = x - x_0$  as $x_0+h = x$, so we have 
$$
f(x_0 + h) - f(x_0) = J_f(x_0)(x-x_0) + \varepsilon(h) \| h \|
$$
## First-degree Taylor polynomial
![[Pasted image 20250304102212.png]]
## Taylor polynomial of K'th degree
![[Pasted image 20250304102645.png]]
This is the same as:
$$
P_k(x) = \sum_{k=0}^k \frac{f^{(k)}(x_0)}{k!}(x-x_0)^k
$$
### Eks 4.2.1
givet $f:\mathbb{R} \to \mathbb{R}$, $f(x) = e^x$. Vi kan nu vælge $x_0 =0$ og $k \in \mathbb{N}$. Det giver os
$$
f^{(k)}(x_0) = e^{x_0} = e^0 = 1
$$
Vi har nu
$$
P_k(x)=\sum_{k=0}^k \frac{1}{k^1}x^k
$$
Hvad er $e = f(1)$? Vi ved i forvejen at $e = 2.71828$
$$
e \approx p_k(1)=\sum_{k=0}^k \frac{1}{k!}1^k = \sum_{k=0}^k \frac{1}{k!}
$$
Når vi har $k=3$ får vi:
$$
e \approx P_3(1) = \sum_{k=0}^3 \frac{1}{k!} = \frac{1}{1} + \frac{1}{1} + \frac{1}{2} + \frac{1}{6} =  2.66666...
$$
Så det er altså en meget god approximation.
![[Pasted image 20250304104232.png]]
    
![[Pasted image 20250304110631.png]]
### Peano form
![[Pasted image 20250304110646.png]]
## Rest ledet og fejlen
![[Pasted image 20250304110700.png]]
## Taylor polynomier
![[Pasted image 20250304115524.png]]
![[Pasted image 20250304120846.png]]
