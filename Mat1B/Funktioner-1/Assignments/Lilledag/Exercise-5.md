![[Pasted image 20250207122116.png]]
![[Pasted image 20250207122136.png]]
#### Answer
**Derivation of the Level Curve Equation**
We are given:
$$
f(x,y) = x^2-2y
$$
Setting this equal to $c$ gives us:
$$
x^2-2y = c
$$
now when we solve for $y$ we get:
$$
y = \frac{x^2-c}{2}
$$
We can now plot this via the python code:
```python
import numpy as np
import matplotlib.pyplot as plt

# Define the function f(x, y) = x^2 - 2y
def f(x, y):
    return x**2 - 2*y

# Define the level curve equation y = g_c(x) derived from f(x, y) = c
def g_c(x, c):
    return (x**2 - c) / 2

# Define the x-values range
x_vals = np.linspace(-3, 3, 400)

# Define level values for c
c_values = [-2, -1, 0, 1, 2]

# Plot level curves
plt.figure(figsize=(8, 6))
for c in c_values:
    y_vals = g_c(x_vals, c)
    plt.plot(x_vals, y_vals, label=f'c = {c}')

# Labels and legend
plt.xlabel("x")
plt.ylabel("y")
plt.title("Level Curves of f(x, y) = x² - 2y")
plt.axhline(0, color='black', linewidth=0.5)
plt.axvline(0, color='black', linewidth=0.5)
plt.legend()
plt.grid()

# Show the plot
plt.show()

```

![[output.png]]
![[Pasted image 20250207131433.png]]
#### Answer 
To show this we input the values $P$ into the equation:
$$
x^2-2y = 2
$$
this gives us a left side:
$$
2^2-2\cdot1 = 4 - 2 = 2
$$
Since this holds true, the point $P$ lies on the level curve for $c=2$.

**Finding a Parametric Representation**
We have the level curve equation defined as:
$$
y = \frac{x^2-c}{2}
$$
a natural parametric form is:
$$
x = t, y = \frac{t^2-2}{2}, t \in \mathbb{R}
$$
where $t$ is a free parameter representing $x$, and $y$ is expressed in terms of $t$. Can also be written as:
$$
r(t)=(t,\frac{1}{2}t^2-1)
$$![[Pasted image 20250207132051.png]]
**Compute the Tangent Vector** 
We already have the parametric representation: $$ \mathbf{r}(t) = \left( t, \frac{1}{2} t^2 - 1 \right) $$ The tangent vector is found by differentiating: $$ \mathbf{r}'(t) = \left( \frac{dx}{dt}, \frac{dy}{dt} \right) $$ Computing the derivatives: $$ \frac{dx}{dt} = 1, \quad \frac{dy}{dt} = t $$ So the tangent vector is: $$ \mathbf{r}'(t) = \begin{bmatrix} 1 \\ t \end{bmatrix} $$ At $P = (2,1)$, we substitute $u = 2$: $$ \mathbf{r}'(2) = \begin{bmatrix} 1 \\ 2 \end{bmatrix} $$ **Compute the Gradient of** $f$
The function is: $$ f(x, y) = x^2 - 2y $$ The gradient is: $$ \nabla f = \begin{bmatrix} \frac{\partial f}{\partial x} \\ \frac{\partial f}{\partial y} \end{bmatrix} $$ Computing the partial derivatives: $$ \frac{\partial f}{\partial x} = 2x, \quad \frac{\partial f}{\partial y} = -2 $$ At $P = (2,1)$: $$ \nabla f(2,1) = \begin{bmatrix} 2(2) \\ -2 \end{bmatrix} = \begin{bmatrix} 4 \\ -2 \end{bmatrix} $$**Check for Orthogonality** 
Two vectors are orthogonal if their dot product is zero: $$ \mathbf{r}'(2) \cdot \nabla f(2,1) = \begin{bmatrix} 1 \\ 2 \end{bmatrix} \cdot \begin{bmatrix} 4 \\ -2 \end{bmatrix} $$ Computing the dot product: $$ (1)(4) + (2)(-2) = 4 - 4 = 0 $$ Since the dot product is **zero**, the tangent vector is **orthogonal** to the gradient. 
**Final Conclusion**
* The tangent vector at $P$ is: $$ \mathbf{r}'(2) = \begin{bmatrix} 1 \\ 2 \end{bmatrix} $$
* The gradient at $P$ is: $$ \nabla f(2,1) = \begin{bmatrix} 4 \\ -2 \end{bmatrix} $$
* Since $\mathbf{r}'(2) \cdot \nabla f(2,1) = 0$, the tangent vector is orthogonal to the gradient.
![[Pasted image 20250207132924.png]]
```python
from sympy import symbols, diff
from dtumathtools.dtuplot import plot_vector, plot_contour

# Define symbolic variables
x, y = symbols('x y')

# Define the function f(x, y)
f = x**2 - 2*y

# Compute the gradient of f
grad_f = [diff(f, x), diff(f, y)]

# Plot the contour levels (level curves) of f
p1 = plot_contour(f, (x, -3, 3), (y, -3, 3), show=False)

# Plot the gradient vector field over the contours
p2 = plot_vector(grad_f, (x, -3, 3), (y, -3, 3), use_cm=False, show=False)

# Display the combined plot
(p1 + p2).show()
```
![[Pasted image 20250207133659.png]]