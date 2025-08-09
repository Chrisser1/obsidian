## Riemann-integralet
### Riemann-summer: $f:[a,b] \to \mathbb{R}$
Inddel $[a,b]$ i $J$ del-intervaller. Vi definerer inddelingen:
$$
a = x_0 < x_1 < x_2 < \dots < x_{J-1} < x_J = b
$$
hvor hvert delinterval har en bredde givet ved:
$$
\Delta x_j = x_j - x_{j-1}
$$
for $j \in \mathbb{N}$.
### Riemann-sum
Lad
$$
Q_j = [x_{j-1}, x_j]
$$
Vælg
$$
\hat{x}_j \in Q_j \quad \text{(tilfældigt)}
$$
Definér Riemann-summen:
$$
S_J = \sum_{j=1}^{J} \Delta x_j \cdot f(\hat{x}_j)
$$
eller skrevet ud:
$$
S_J = \Delta x_1 f(\hat{x}_1) + \Delta x_2 f(\hat{x}_2) + \dots + \Delta x_J f(\hat{x}_J)
$$
![[Pasted image 20250318102938.png]]
![[Pasted image 20250318102953.png]]
#### Bemærk:
Hvis $f:[a,b] \to \mathbb{R}$ er riemann-intergrabel, så kan $\int_a^b f(x) dx = I$, findes ved $\Delta x_j = \frac{b-a}{J}$ og $\xi$ kan vælges som venstre, midt eller højre endepunkt.
![[Pasted image 20250318103317.png]]

![[Pasted image 20250318111442.png]]
![[Pasted image 20250318111451.png]]

![[Pasted image 20250318103810.png]]

![[Pasted image 20250318111327.png]]