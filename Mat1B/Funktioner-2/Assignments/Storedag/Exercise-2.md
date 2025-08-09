![[Pasted image 20250211123347.png]]
![[Pasted image 20250211123421.png]]
#### Answer
1. $f(x_1,x_2,x_3) = x_1^2x_2+2x_3$
We start off by calculating the [[Jacobian-matrix]]. To do this we calculate the [[Partial differential]] for all x.
**For $x_1$:**
$$
\frac{df}{dx_1} = 2x_1x_2
$$
**For $x_2$:**
$$
\frac{df}{dx_2} = x_1^2
$$
**For $x_3$:**
$$
\frac{df}{dx_3} = 2
$$
**Setup of Jacobian matrix**
$$
J_f(x) = 
\begin{bmatrix} 
2x_1x_2 & x_1^2 & 2
\end{bmatrix}
$$
**Evaluation at $x=(1,-1,3)$**
$$
J_f(1,-1,3) = 
\begin{bmatrix} 
2 \cdot 1 \cdot -1 & 1 & 2
\end{bmatrix} =
\begin{bmatrix} 
-2 & 1 & 2
\end{bmatrix}
$$
Since $f(x_1, x_2, x_3)$ is a scalar function, the Jacobian matrix only has one row, confirming that the Jacobian for a scalar function of multiple variables is always a row vector.
1. $f(x) = (3x,x^2,sin(2x))$
Since this is a function of one variable $x$, the Jacobian matrix is a column vector of derivatives:
$$
J_f(x)=
\begin{bmatrix}
\frac{d}{dx}(3x) \\
\frac{d}{dx}(x^2) \\
\frac{d}{dx}(sin(2x))
\end{bmatrix} = 
\begin{bmatrix}
3 \\
2x \\
2 \cdot cos(2x)
\end{bmatrix}
$$
**At $x=2$**
$$
J_f(2) = \begin{bmatrix}
3 \\
4 \\
2 \cdot cos(4)
\end{bmatrix}
$$
1. $f(x_1,x_2)=(x_1^2,-3x_2,12x_1)$
$$
J_f(x)=
\begin{bmatrix}
\frac{d}{dx_1}(x_1^2) & \frac{d}{dx_2}(x_1^2) \\
\frac{d}{dx_1}(-3x_2) & \frac{d}{dx_2}(-3x_2) \\
\frac{d}{dx_1}(12x_1) & \frac{d}{dx_2}(12x_1)
\end{bmatrix} = 
\begin{bmatrix}
2x_1 & 0 \\
	0 & -3 \\
12 & 0
\end{bmatrix}
$$
**At $(x_1,x_2)= (2,0)$
$$
J_f(2,0) = 
\begin{bmatrix}
2 \cdot 2 & 0 \\
	0 & -3 \\
12 & 0
\end{bmatrix} =
\begin{bmatrix}
4 & 0 \\
	0 & -3 \\
12 & 0
\end{bmatrix}
$$
1. $f(x_1​,x_2​,x_3​) = (x_2sin(x_3),3x_1x_2ln(x_3)$
$$
J_f(x) =
\begin{bmatrix}
\frac{d}{dx_1}(x_2sin(x_3)) & \frac{d}{dx_2}(x_2sin(x_3)) & \frac{d}{dx_3}(x_2sin(x_3)) \\
\frac{d}{dx_1}(3x_1x_2ln(x_3)) & \frac{d}{dx_2}(3x_1x_2ln(x_3)) & \frac{d}{dx_3}(3x_1x_2ln(x_3))\\
\end{bmatrix}
$$
$$
= 
\begin{bmatrix}
0 & sin(x_3) & x_2cos(x_3) \\
3x_2ln(x_3)) & 3x_1ln(x_3)) & \frac{3x_1x_2}{x_3}\\
\end{bmatrix}
$$
**At $(-1,3,2)$**
$$
J_f(-1,3,2) = 
\begin{bmatrix}
0 & sin(2) & 3cos(2) \\
9ln(2)) & -3ln(2)) & \frac{-9}{2}\\
\end{bmatrix}
$$
1. $f(x_1,x_2,x_3) = (x_1e^{x_2},3x_2sin(x_2),-x_1^2ln(x_2 + x_3))$
$$
J_f(x) =
\begin{bmatrix}
\frac{d}{dx_1}(x_1e^{x_2}) & \frac{d}{dx_2}(x_1e^{x_2}) & \frac{d}{dx_3}(x_1e^{x_2}) \\
\frac{d}{dx_1}(3x_2sin(x_2)) & \frac{d}{dx_2}(3x_2sin(x_2)) & \frac{d}{dx_3}(3x_2sin(x_2)) \\
\frac{d}{dx_1}(-x_1^2ln(x_2 + x_3)) & \frac{d}{dx_2}(-x_1^2ln(x_2 + x_3)) & \frac{d}{dx_3}(-x_1^2ln(x_2 + x_3))
\end{bmatrix}
$$
$$
=
\begin{bmatrix}
e^{x_2} & x_1e^{x_2} & 0 \\
0 & 3sin(x_2)+ 3x_2cos(x_2)) & 0 \\
-2x_1ln(x_2 + x_3)) & \frac{-x_1^2}{x_2 + x_3} & \frac{-x_1^2}{x_2 + x_3}
\end{bmatrix}
$$
**At $(1,0,1)$
$$
J_f(1,0,1) =
\begin{bmatrix}
e^{0} & 1e^{0} & 0 \\
0 & 3sin(0)+ 3 \cdot 0 \cdot cos(0)) & 0 \\
-2ln(0 + 1)) & \frac{-1^2}{0 + 1} & \frac{-1^2}{0 + 1}
\end{bmatrix} =
\begin{bmatrix}
1 & 1 & 0 \\
0 & 0 & 0 \\
0 & -1 & -1
\end{bmatrix}
$$
![[Pasted image 20250211131801.png]]
#### Answer
All the given functions in the previous questions are composed of elementary functions (polynomials, exponentials, logarithms, and trigonometric functions). Since these functions are all continuously differentiable in their respective domains, they are differentiable everywhere their domain is well-defined.

To formally argue differentiability:

- **Polynomial functions** are infinitely differentiable.
- **Exponential and trigonometric functions** are also infinitely differentiable.
- **Logarithmic functions** are differentiable where their arguments are positive.

Thus, all the given functions are differentiable in their respective domains.

**When is the Hessian Defined?**
The **Hessian matrix** is only defined for **scalar functions** (i.e., functions mapping $\mathbb{R}^n \to \mathbb{R}$), since it consists of the second-order partial derivatives.

From the given problems:

1. $f(x) = (3x, x^2, \sin(2x))$ (**Vector function**, $\mathbb{R} \to \mathbb{R}^3$) → **No Hessian**

2. $f(x_1, x_2) = (x_1^2, -3x_2, 12x_1)$ (**Vector function**, $\mathbb{R}^2 \to \mathbb{R}^3$) → **No Hessian**

3. $f(x_1, x_2, x_3) = (x_2 \sin(x_3), 3x_1 x_2 \ln(x_3))$ (**Vector function**, $\mathbb{R}^3 \to \mathbb{R}^2$) → **No Hessian**

4. $f(x_1, x_2, x_3) = (x_1 e^{x_2}, 3x_2 \sin(x_2), -x_1^2 \ln(x_2 + x_3))$ (**Vector function**, $\mathbb{R}^3 \to \mathbb{R}^3$) → **No Hessian**

Only the **scalar function**
$$
f(x_1, x_2, x_3) = x_1^2 x_2 + 2x_3
$$
is eligible for Hessian computation.
$$
H_f = \begin{bmatrix} \frac{\partial^2 f}{\partial x_1^2} & \frac{\partial^2 f}{\partial x_1 \partial x_2} & \frac{\partial^2 f}{\partial x_1 \partial x_3} \\ \frac{\partial^2 f}{\partial x_2 \partial x_1} & \frac{\partial^2 f}{\partial x_2^2} & \frac{\partial^2 f}{\partial x_2 \partial x_3} \\ \frac{\partial^2 f}{\partial x_3 \partial x_1} & \frac{\partial^2 f}{\partial x_3 \partial x_2} & \frac{\partial^2 f}{\partial x_3^2} \end{bmatrix}
$$
Now, differentiating again:

- $\frac{\partial^2 f}{\partial x_1^2} = 2x_2$
- $\frac{\partial^2 f}{\partial x_1 \partial x_2} = \frac{\partial^2 f}{\partial x_2 \partial x_1} = 2x_1$
- $\frac{\partial^2 f}{\partial x_1 \partial x_3} = \frac{\partial^2 f}{\partial x_3 \partial x_1} = 0$
- $\frac{\partial^2 f}{\partial x_2^2} = 0$
- $\frac{\partial^2 f}{\partial x_2 \partial x_3} = \frac{\partial^2 f}{\partial x_3 \partial x_2} = 0$
- $\frac{\partial^2 f}{\partial x_3^2} = 0$
Thus, the **Hessian matrix** is:
$$
H_f(x_1, x_2, x_3) =
\begin{bmatrix}
2x_2 & 2x_1 & 0 \\
2x_1 & 0 & 0 \\
0 & 0 & 0
\end{bmatrix}
$$
$$
H_f(1, -1, 3) = 
\begin{bmatrix} 
2(-1) & 2(1) & 0 \\ 
2(1) & 0 & 0 \\ 
0 & 0 & 0 
\end{bmatrix} = 
\begin{bmatrix} 
-2 & 2 & 0 \\ 
2 & 0 & 0 \\ 
0 & 0 & 0 
\end{bmatrix}
$$