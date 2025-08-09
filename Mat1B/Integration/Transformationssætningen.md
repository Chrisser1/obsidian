![[Pasted image 20250328080149.png]]
![[Pasted image 20250328080200.png]]

## cylinder koordinater
Der er 3 parametre $(\rho, \phi, z)$ som svare til radius, vinkel og højde.
$$
c(\rho, \phi, z) =
\begin{bmatrix}
\rho \cos\phi \\
\rho \sin\phi \\
z
\end{bmatrix}
$$
Givet $\phi \in [0,\infty[, \phi \in [0,2\pi], z \in \mathbb{R}$
$$
J_c(\rho, \phi, z) =
\begin{bmatrix}
\cos\phi & -\rho \sin\phi & 0 \\
\sin\phi & \rho \cos\phi & 0 \\
0 & 0 & 1
\end{bmatrix}
$$
Vi har også at determinanten er:
$$
det(J_c(\rho, \phi, z)) = \rho >0
$$
C er injektiv når $\rho \neq 0$.

### Eksempel
### Eksempel

$$
\Gamma = \left\{ (\rho, \phi, z) \ \middle| \ 
\phi \in [0, 2\pi] \ \land\ z \in [0, h] \land\ 0 \leq \rho \leq \frac{r}{h} z
\right\}
$$

$$
\text{vol}_3(\text{kegle}) = \int_B 1 \, dx
$$

$$
= \int 1 \left| \det J_{\mathcal{C}}(\rho, \phi, z) \right| d(\rho, \phi, z)
$$

$$
= \int_0^h \int_0^{2\pi} \int_0^{\frac{r}{h}z} \rho \, d\rho \, d\phi \, dz
$$

$$
= \int_0^h \int_0^{2\pi} \left[ \frac{1}{2} \rho^2 \right]_{\rho = 0}^{\rho = \frac{r}{h}z} \, d\phi \, dz
$$

$$
= \int_0^h \int_0^{2\pi} \frac{1}{2} \left( \frac{r}{h}z \right)^2 \, d\phi \, dz
$$

$$
= \int_0^h \int_0^{2\pi} \frac{1}{2} \frac{r^2}{h^2} z^2 \, d\phi \, dz
$$

$$
= \int_0^h \left( \frac{1}{2} \frac{r^2}{h^2} z^2 \right) \left[ \phi \right]_{\phi=0}^{2\pi} \, dz
$$

$$
= \int_0^h \left( \frac{1}{2} \frac{r^2}{h^2} z^2 \cdot 2\pi \right) \, dz
$$

$$
= \pi \frac{r^2}{h^2} \int_0^h z^2 \, dz
$$

$$
= \pi \frac{r^2}{h^2} \left[ \frac{1}{3} z^3 \right]_0^h
$$

$$
= \pi \frac{r^2}{h^2} \cdot \frac{1}{3} h^3 = \frac{1}{3} \pi r^2 h
$$
