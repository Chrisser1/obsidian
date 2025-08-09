![[5
![[Pasted image 20250205131708.png]]
![[Pasted image 20250205131732.png]]
#### Answer
To find the function value of $f(2,-3)$ we need to calculate the following:
$$
f(x_1,x_2) = \begin{bmatrix} ln(x_1) \\ x_1 \cdot x_2^2 + 1 \end{bmatrix}
$$
This can be done via python:
![[Pasted image 20250205132414.png]]

![[Pasted image 20250205132553.png]]
#### Answer

The given function is: $$ f(x_1, x_2) = \begin{bmatrix} \ln(x_1) \\ x_1 \cdot x_2^2 + 1 \end{bmatrix} $$ To determine the **domain** ($\text{dom}(f)$), we analyze the constraints on $x_1$ and $x_2$: - The term $\ln(x_1)$ is only defined for $x_1 > 0$. - The term $x_1 \cdot x_2^2 + 1$ is defined for all $x_1, x_2 \in \mathbb{R}$. Thus, the domain is: $$ \text{dom}(f) = ]0, \infty[ \times \mathbb{R} $$ This means that $x_1$ must be positive, but $x_2$ can be any real number.

![[Pasted image 20250205132957.png]]
#### Answer
To determine the **image/range** of the function: $$ f(x_1, x_2) = \begin{bmatrix} \ln(x_1) \\ x_1 \cdot x_2^2 + 1 \end{bmatrix} $$ we analyze the possible values of $y_1$ and $y_2$.

**Finding the Range of $y_1$** From the first equation: $$ y_1 = \ln(x_1) $$ Since $x_1 > 0$, the natural logarithm function is defined for all positive $x_1$, and its range is: $$ y_1 \in \mathbb{R} $$ **Finding the Range of $y_2$** From the second equation: $$ y_2 = x_1 \cdot x_2^2 + 1 $$ - Since $x_2^2 \geq 0$, we always have $x_1 \cdot x_2^2 \geq 0$. - Adding $1$ ensures that $y_2 \geq 1$. - As $x_2$ varies over all real numbers, $x_2^2$ takes all non-negative values, allowing $y_2$ to take all values in the interval $[1, \infty[$. Thus, the image (range) of $f$ is: $$ \text{im}(f) = \mathbb{R} \times [1, \infty[ $$ This means the function maps to all real numbers in the first coordinate and to the interval $[1, \infty[$ in the second coordinate.