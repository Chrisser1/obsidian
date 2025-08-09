![[Pasted image 20250318112829.png]]
![[Pasted image 20250318113846.png]]

## Eksempel 1
Givet $B = [0,3] \times [-2,0]$. Lad så $f(x,y)=1$ for $(x,y) \in B$. Dette giver os:
$$
\int_B f(x,y) d(x,y) = \int_0^3 \int_{-2}^0 f(x,y)dydx
$$
Vi kan nu skrive arealet som:
$$
areal(B)=\int_B 1 \space d(x,y) = \int_0^3 \int_{-2}^0 1 \space dydx
$$
$$
= \int_0^3 [y]_{-2}^0 dx = \int_0^3 (0-(-2))dx = \int_0^3 2 \space dx
$$
$$
[2x]^3_0 = (2\cdot3 - 2\cdot0) = 6
$$
#### Eksempel 2
Lad
$$
B = \left\{ (x, y) \in \mathbb{R}^2 \mid -x \leq y \leq x^2 \ \wedge\ 0 \leq x \leq 1 \right\}
$$
og lad $f : B \rightarrow \mathbb{R}$, $f(x, y) = x y$
Vi vil beregne
$$
\int_B f(x, y) \, d(x, y)
$$
Ved at skrive om som itereret integral:
$$
\int_B f(x, y) \, d(x, y) = \int_0^1 \int_{-x}^{x^2} f(x, y) \, dy \, dx
$$
$$
= \int_0^1 \int_{-x}^{x^2} x y \, dy \, dx
$$
$$
= \int_0^1 x \left[ \frac{y^2}{2} \right]_{y = -x}^{y = x^2} \, dx
$$
$$
= \int_0^1 x \left( \frac{(x^2)^2}{2} - \frac{(-x)^2}{2} \right) \, dx
= \int_0^1 x \left( \frac{x^4 - x^2}{2} \right) \, dx
= \frac{1}{2} \int_0^1 \left( x^5 - x^3 \right) \, dx
$$
$$
= \frac{1}{2} \left[ \frac{1}{6} x^6 - \frac{1}{4} x^4 \right]_0^1
= \frac{1}{2} \left( \frac{1}{6} - \frac{1}{4} \right)
= \frac{1}{2} \left( \frac{2}{12} - \frac{3}{12} \right)
= -\frac{1}{24}
$$
