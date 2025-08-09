### Eksempel med cylinder flade

![[Pasted image 20250404082220.png]]
Vi kan opskrive dette set som:
$$
\{(x, y, z) \in \mathbb{R}^3 \mid z \in [0, H] \land x^2 + y^2 = R^2 \}
$$
**Parameterizing**:
$$
\mathbf{r}(\theta, z) =
\begin{bmatrix}
R \cos\theta \\
R \sin\theta \\
z
\end{bmatrix}
$$
Hvor
$$
\Gamma = [0, 2\pi] \times [0, H]
$$
**Tangentvektorer:**
$$
\frac{\partial \mathbf{r}}{\partial \theta} =
\begin{bmatrix}
-R \sin \theta \\
R \cos \theta \\
0
\end{bmatrix}
$$
$$
\frac{\partial \mathbf{r}}{\partial z} =
\begin{bmatrix}
0 \\
0 \\
1
\end{bmatrix}
$$
Vi har:
$$
\frac{\partial \mathbf{r}}{\partial \theta} \times \frac{\partial \mathbf{r}}{\partial z} =
\begin{bmatrix}
R \cos \theta \\
R \sin \theta \\
0
\end{bmatrix}
$$
Normen af krydsproduktet:
$$
\left\| \frac{\partial \mathbf{r}}{\partial \theta} \times \frac{\partial \mathbf{r}}{\partial z} \right\| = \sqrt{(R \cos \theta)^2 + (R \sin \theta)^2 + 0^2}
$$
$$
= R > 0, \quad \cos^2(\theta) + \sin^2(\theta) = 1
$$
**Egenskaber:**
a. $\mathbf{r}$ er $\mathcal{C}^{\infty}$ (glat uendeligt mange gange differentiabel)
b. $\mathbf{r}$ er injektiv **pånær** når $\theta = 0 \quad \text{og} \quad \theta = 2\pi$ for $r(0,z)=r(2\pi,z)$
c. Da Jacobianen $(\theta, z) = R > 0$ er $\mathbf{r}$ regulær.
  
**Udregn integralet:**
Lad
$$
f : \mathbb{R}^3 \to \mathbb{R}, \quad f(x, y, z) = |x| \, z
$$
Med parameteriseringen:
$$
\begin{bmatrix}
x \\ y \\ z
\end{bmatrix}
=
\begin{bmatrix}
R \cos \theta \\
R \sin \theta \\
z
\end{bmatrix}
$$
så gælder:
$$
\int_B f(x, y, z) \, dS = \int_{\Gamma} f(\mathbf{r}(\theta, z)) \, \text{Jacobianen}(\theta, z) \, d(\theta, z)
$$
Vi fortsætter med udregningen:
$$
= \int_0^H \int_0^{2\pi} |R \cos \theta| \, z \, R \, d\theta \, dz
$$
$$
= \int_0^H R^2 z \left( \int_0^{2\pi} |\cos \theta| \, d\theta \right) dz
$$
Betragt:
$$
\int_0^{2\pi} |\cos \theta| \, d\theta
$$
Fra symmetrien og grafen af \(|\cos \theta|\), får vi:
$$
= 4 \int_0^{\frac{\pi}{2}} \cos \theta \, d\theta
$$
$$
= 4 \left[ \sin \theta \right]_0^{\frac{\pi}{2}} = 4 (1 - 0) = 4
$$
Så vi får:
$$
= \int_0^H 4 R^2 z \, dz
$$
Intergrallet bliver
$$
= 4 R^2 \left[ \frac{1}{2} z^2 \right]_0^H
$$
$$
= 4 R^2 \times \frac{1}{2} H^2
$$
$$
= 2 R^2 H^2
$$


  

