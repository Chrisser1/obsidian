## Parametrisering af en linje
![[Pasted image 20250325112204.png]]
Lad $\mathbf{z}_0, \mathbf{z}_1 \in \mathbb{R}^n$. Vi ønsker at beskrive linjestykket mellem disse to punkter.
Vi indfører en parameter $t \in [0, 1]$, og definerer en funktion:
$$
\mathbf{r}(t) = (1 - t) \mathbf{z}_0 + t \mathbf{z}_1
$$
Dette kan også skrives som:
$$
\mathbf{r}(t) = \mathbf{z}_0 + t (\mathbf{z}_1 - \mathbf{z}_0)
$$
- Når $t = 0$, får vi $\mathbf{r}(0) = \mathbf{z}_0$

- Når $t = 1$, får vi $\mathbf{r}(1) = \mathbf{z}_1$

- Når $t = \frac{1}{2}$, får vi midtpunktet på linjestykket

- Når $t = \frac{1}{4}$, er vi 1/4 af vejen fra $\mathbf{z}_0$ mod $\mathbf{z}_1$

Billedet af $\mathbf{r}$
$$
\mathbf{r} : [0,1] \to \mathbb{R}^n
$$
Billedet (mængden af punkter) er:
$$
\text{im}(\mathbf{r}) = \mathbf{r}([0,1]) = r \cdot [0,1] \to \mathbb{R}^n
$$
Det er altså linjestykket mellem $\mathbf{z}_0$ og $\mathbf{z}_1$ i $\mathbb{R}^n$.
#### Eksempel 2
![[Pasted image 20250325112547.png]]
Lad os betragte området:
$$
B = \left\{ (x, y) \in \mathbb{R}^2 \ \middle| \ -x \leq y \leq x^2 \ \wedge \ 0 \leq x \leq 1 \right\}
$$
Dette område er afgrænset af:
- Nederst: $y = -x$

- Øverst: $y = x^2$

- Lodret fra $x = 0$ til $x = 1$

Parametrisering af området
Vi vil transformere enhedskvadratet $\Gamma = [0,1] \times [0,1] \subset \mathbb{R}^2$ til området $B$.
Lad os definere afbildningen $\mathbf{r}(u,v)$ som følger:
$$
x = u
$$
$$
\mathbf{r}(u,v) =
\begin{bmatrix}
u \\
- u
\end{bmatrix}
+ v \cdot
\left(
\begin{bmatrix}
0 \\
u^2
\end{bmatrix}
-
\begin{bmatrix}
0 \\
- u
\end{bmatrix}
\right)
$$
Udregning:
$$
=
\begin{bmatrix}
u + v \cdot 0 \\
- u + v \cdot (u^2 + u)
\end{bmatrix}
=
\begin{bmatrix}
u \\
- u + v u^2 + v u
\end{bmatrix}
= \mathbf{r}(u, v)
$$
Jacobimatricen for $\mathbf{r}(u,v)$
$$
J_{\mathbf{r}}(u,v) =
\begin{bmatrix}
\frac{\partial r_1}{\partial u} & \frac{\partial r_1}{\partial v} \\
\frac{\partial r_2}{\partial u} & \frac{\partial r_2}{\partial v}
\end{bmatrix}
=
\begin{bmatrix}
1 & 0 \\
u^2 + u & u^2 + u
\end{bmatrix}
$$
Dens determinant er:
$$
\det J_{\mathbf{r}}(u,v) = (1)(u^2 + u) - (0)(u^2 + u) = u^2 + u > 0
$$
for alle $(u,v) \in \Gamma^\circ = \; ]0,1[ \times ]0,1[$

**Bemærkning om injektivitet**
Afbildningen $\mathbf{r}$ er injektiv på det åbne område $\Gamma^\circ$, men kan have problemer i hjørnet $(u=0, v \in [0,1])$, fordi $r(u,v)$ kollapser mod ét punkt når $u \to 0$.

Omformning af integral
Givet $f(x,y)$, og området $B$ defineret tidligere, gælder:
$$
\int_B f(x, y) \, d(x, y) =
\int_0^1 \int_0^1
f(r_1(u,v), r_2(u,v)) \cdot \left| \det J_{\mathbf{r}}(u,v) \right| \, dv \, du
$$
hvor:
- $r_1(u,v) = u$

- $r_2(u,v) = -u + vu^2 + vu$

- $\left| \det J_{\mathbf{r}}(u,v) \right| = u^2 + u$

Vi har:
$$
\int_0^1 \int_0^1
\left( -u^2 + vu^3 + vu^2 \right)(u^2 + u) \, dv \, du
$$
Først multiplicerer vi ud og integrerer mht. \( v \):
$$
= \int_0^1 \int_0^1
\left( -u^2 + vu^3 + vu^2 \right)(u^2 + u) \, dv \, du
$$
$$
= \int_0^1 (u^2 + u) \left[ -u^2 v + \frac{u^3 v^2}{2} + \frac{u^2 v^2}{2} \right]_{v=0}^{v=1} \, du
$$
$$
= \int_0^1 (u^2 + u) \left( -u^2 + \frac{1}{2}u^3 + \frac{1}{2}u^2 \right) \, du
$$
$$
= \int_0^1 (u^2 + u) \left( \frac{1}{2}u^3 - u^2 + \frac{1}{2}u^2 \right) \, du
= \int_0^1 (u^2 + u) \left( \frac{1}{2}u^3 - \frac{1}{2}u^2 \right) \, du
$$
$$
= \frac{1}{2} \int_0^1 (u^2 + u)(u^3 - u^2) \, du
$$
$$
= \frac{1}{2} \int_0^1 \left( u^5 + u^4 - u^4 - u^3 \right) \, du
= \frac{1}{2} \int_0^1 \left( u^5 - u^3 \right) \, du
$$
Vi er nu klar til at beregne værdien:
$$
= \frac{1}{2} \left[ \frac{u^6}{6} - \frac{u^4}{4} \right]_0^1
= \frac{1}{2} \left( \frac{1}{6} - \frac{1}{4} \right)
= \frac{1}{2} \left( \frac{-1}{12} \right)
= -\frac{1}{24}
$$
