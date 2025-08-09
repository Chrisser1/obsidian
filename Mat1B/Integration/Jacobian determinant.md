![[Pasted image 20250325102851.png]]
Find information om [[Jacobian-matrix]].
## Ofte sæt
$$
\Gamma = [a_1, b_1] \times [a_2, b_2]
$$
$$
\Gamma^\circ = \; ]a_1, b_1[ \times ]a_2, b_2[
$$
# Transformationsætningen
![[Pasted image 20250325110733.png]]
---
## Parametriseringen af højre kasse
![[Pasted image 20250325104325.png]]
$$
\mathbf{r}(u, v) = \left( u \cos(v), u \sin(v) \right)
$$
Ud fra billedet kan vi aflæse, at:
$$
(u,v) \in \left[ \frac{1}{2}, 2 \right] \times \left[ \frac{\pi}{4}, \frac{\pi}{2} \right] = \Gamma
$$
Vi kan nu opstille Jacobimatricen:
$$
J_{\mathbf{r}}(u, v) =
\begin{bmatrix}
\frac{\partial r_1}{\partial u} & \frac{\partial r_1}{\partial v} \\
\frac{\partial r_2}{\partial u} & \frac{\partial r_2}{\partial v}
\end{bmatrix}
=
\begin{bmatrix}
\cos(v) & -u \sin(v) \\
\sin(v) & u \cos(v)
\end{bmatrix}
$$
Vi kan nu få Jacobideterminanten som:
$$
\det J_{\mathbf{r}}(u, v)
= u \cos^2(v) - (-u \sin^2(v))
= u (\cos^2(v) + \sin^2(v))
= u \cdot 1 = u
$$
## Eksempel
Givet $B = [0,3] \times [-2,0]$. Lad så $f(x,y)=1$ for $(x,y) \in B$.

Vi kan skrive det som en afbildning:
$$
\mathbf{r} : [0, 1] \times [0, 1] \to B = [0, 3] \times [-2, 0]
$$
Illustration:
![[Pasted image 20250325105841.png]]
Afbildningen defineres som:
$$
\mathbf{r}(u,v) =
\begin{bmatrix}
3u \\
-2v
\end{bmatrix}
$$
Vi kan nu opstille Jacobimatricen og determinanten
$$
J_{\mathbf{r}}(u,v) =
\begin{bmatrix}
\frac{\partial r_1}{\partial u} & \frac{\partial r_1}{\partial v} \\
\frac{\partial r_2}{\partial u} & \frac{\partial r_2}{\partial v}
\end{bmatrix}
=
\begin{bmatrix}
3 & 0 \\
0 & -2
\end{bmatrix}
$$
$$
\det J_{\mathbf{r}}(u,v) = 3 \cdot (-2) - 0 \cdot 0 = -6
$$
Vi kan nu opskrive vores integration for $f(x,y)$ ud fra theorem 6.4.1.
$$
\int_B f(x, y) \, d(x, y) = \int_B 1 \, d(x, y)
$$
Bruger vi substitutionen $\mathbf{r}(u,v) = (3u, -2v)$ med $\det J_{\mathbf{r}}(u,v) = 6$, så får vi:
$$
= \int_0^1 \int_0^1 f(3u, -2v) \cdot \left| \det J_{\mathbf{r}}(u,v) \right| \, dv \, du
= \int_0^1 \int_0^1 1 \cdot 6 \, dv \, du
$$
$$
= \int_0^1 \int_0^1 [u]^1_0 \cdot 6 \, dv \, du
= \int_0^1 6(1 - 0) \, du
= \int_0^1 6 \, du
= 6(1 - 0) = 6
$$

