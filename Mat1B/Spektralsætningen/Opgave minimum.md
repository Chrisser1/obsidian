![[Pasted image 20250225111304.png]]
![[Pasted image 20250225111311.png]]

## Optimering: Minimum for $g$
### Problemformulering:
Find minimum for funktionen $q: \mathbb{R}^2 \to \mathbb{R}$:
$$
q(x_1, x_2) = x_1^2 - 2x_1x_2 + x_2^2 + x_1 - x_2 + 2
$$
## Kvadratisk form:
Funktionen kan skrives på matrixform:
$$
q(x_1, x_2) =
\begin{bmatrix} x_1 & x_2 \end{bmatrix}
A
\begin{bmatrix} x_1 \\ x_2 \end{bmatrix}
+ \begin{bmatrix} x_1 & x_2 \end{bmatrix} b + c
$$
hvor:
- $A$ er en $2 \times 2$ matrix
- $b$ er en $2 \times 1$ vektor
- $c$ er en konstant
#### Symmetri:
Ifølge teori (sætning 2.8.7) kan matrixen $A$ altid vælges **symmetrisk**. Derudover husk at $A = \frac{1}{2}H_q$ ([[Hessian matrix]])
$$
A = \begin{bmatrix} 1 & -1 \\ -1 & 1 \end{bmatrix}, \quad b = \begin{bmatrix} -1 \\ -1 \end{bmatrix}
$$
skrift til til $q$-basis:. Hvad er Q:
$$
0 = \det \begin{bmatrix} 1 - \lambda & -1 \\ -1 & 1 - \lambda \end{bmatrix} = (1-\lambda)^2-(-1)^2 \Leftrightarrow (1-\lambda)^2 = 1
$$
Vi har nu
$$
\lambda_1 = 0 \quad \lor \quad \lambda_2 = 2
$$
Vi kan nu se, at:
$$
\text{am}(\lambda_1) = \text{am}(\lambda_2) = 1
$$
Vi har nu egenvektorne:
$$
A v_k = \lambda_k v_k \Leftrightarrow (A - \lambda_k I) v_k = 0
$$
Beregning for $\lambda_1 = 0$
$$
\begin{bmatrix}
1 & -1 \\
-1 & 1
\end{bmatrix}
\begin{bmatrix}
x_1 \\
x_2
\end{bmatrix}
=
0
$$
Skrives som den homogene ligning:
$$
\begin{bmatrix}
1 & -1 | 0 \\
-1 & 1 | 0
\end{bmatrix}
\to
\begin{bmatrix}
1 & -1 | 0 \\
0 & 0 | 0
\end{bmatrix}
$$
Løsning:
$$
x_1 - x_2 = 0
$$
Altså:
$$
x_1 = x_2 = t, \quad t \in \mathbb{R}
$$
Egenvektoren kan skrives som:
$$
\begin{bmatrix}
x_1 \\
x_2
\end{bmatrix}
=
t \begin{bmatrix} 1 \\ 1 \end{bmatrix}, \quad t \in \mathbb{R} \setminus \{0\}
$$
Dette viser, at egenvektoren til $\lambda_1 = 0$ er en skalar multipel af $[1,1]$.
#### Nem løsnings metode
$$
q(\tilde{x}_1, \tilde{x}_2) = x_q^T \Lambda_q x_q + x_q^T Q^T b + c
$$
hvor:
- $x_q$ er koordinaterne i $g$-basis
- $\Lambda_q$ er en diagonal matrix med egenværdier
- $Q$ er en ortogonal matrix fra egenvektorer
- $b$ er en vektor
- $c$ er en konstant
Denne omskrivning gør det muligt at analysere funktionen i en ny basis.