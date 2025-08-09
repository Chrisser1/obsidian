![[Pasted image 20250211161119.png]]
![[Pasted image 20250211161150.png]]
#### Answer
The logarithm can take positive values, therefore we must demand
$$
9-x^2-y^2 > 0
$$
but this can be written as $x^2 + y^2 < 3^2$, therefore the $dom(g)=\{(x,y) \mid x^2+y^2<3^2\}$. This is a open disk with centrum at the origin with radius 3, but where the periphery is not in it. Therefor the amount is open and limited.
![[Pasted image 20250211161932.png]]
#### Answer
This is the graph for a third degree polynomial $p(x) = x^3, x \in [-1.2,1.2]$
![[Pasted image 20250211162210.png]]
#### Answer
$$
dom(h) = [-1.2,1.2] \text{ and co-dom(h)} = \mathbb{R}.
$$
![[Pasted image 20250211162646.png]]
#### Answer
**Direct Differentiation**:
   - The function $h(u)$ is given by $h(u) = g(r(u)) = \ln(9 - u^2 - u^6)$.
   - Differentiating this function with respect to $u$:
$$
h'(u) = \frac{-2u - 6u^5}{9 - u^2 - u^6}.
$$
   - Substituting $ u = 1 $:
$$
h'(1) = \frac{-2(1) - 6(1)^5}{9 - 1 - 1} = \frac{-2 - 6}{7} = \frac{-8}{7}.
$$
**Using the Chain Rule**:
   - We use the chain rule: $h'(u) = g_x(r(u))r_x'(u) + g_y(r(u))r_y'(u)$.
   - Here:
$$
g_x(x, y) = \frac{-2x}{9 - x^2 - y^2}, \quad g_y(x, y) = \frac{-2y}{9 - x^2 - y^2}.
$$
$$
r_x'(u) = 1, \quad r_y'(u) = 3u^2.
$$
   - Substituting $ x = 1 $ and $ y = 1^3 = 1 $:
$$
g_x(1,1) = \frac{-2(1)}{7}, \quad g_y(1,1) = \frac{-2(1)}{7}.
$$
   - So:
$$
h'(1) = \left(\frac{-2}{7}\right)(1) + \left(\frac{-2}{7}\right)(3(1)^2) = \frac{-2}{7} - \frac{6}{7} = \frac{-8}{7}.
$$
Both methods give the same result: $h'(1) = -\frac{8}{7}$.