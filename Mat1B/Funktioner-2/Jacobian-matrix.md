The Jacobian matrix $J_f$ is a $k \times n$ matrix given by $J_f(x_0) \in \mathbb{R}^{k \times n}$:
$$
J_f = \begin{bmatrix} \frac{\partial f_1}{\partial x_1}(\mathbf{x}) & \frac{\partial f_1}{\partial x_2}(\mathbf{x}) & \cdots & \frac{\partial f_1}{\partial x_n}(\mathbf{x}) \\ \frac{\partial f_2}{\partial x_1}(\mathbf{x}) & \frac{\partial f_2}{\partial x_2}(\mathbf{x}) & \cdots & \frac{\partial f_2}{\partial x_n}(\mathbf{x}) \\ \vdots & \vdots & \ddots & \vdots \\ \frac{\partial f_k}{\partial x_1}(\mathbf{x}) & \frac{\partial f_k}{\partial x_2}(\mathbf{x}) & \cdots & \frac{\partial f_k}{\partial x_n}(\mathbf{x}) \end{bmatrix}
$$
This can also be written as:
$$
J_f(\mathbf{x}) = \begin{bmatrix} \nabla f_1(\mathbf{x})^T \\ \nabla f_2(\mathbf{x})^T \\ \vdots \\ \nabla f_k(\mathbf{x})^T \end{bmatrix} \in \mathbb{R}^{k \times n}
$$
$$
k = 1, \quad f: U \to \mathbb{R}, \quad U \subset \mathbb{R}^n \quad (\text{skalar})
$$
$$
J_f(\mathbf{x}_0) = \nabla f(\mathbf{x}_0)^T
$$
#### E.g. 3.7.1
In this example $k = 1, \quad n = 1$, so we will have $J_f(x_0) = [f'(x_0)]$.
$$
f: \mathbb{R} \to \mathbb{R}^2, \quad f(x) = \begin{bmatrix} \sin(x) \\ \cos(x) \end{bmatrix}
$$
$$
g: \mathbb{R}^2 \to \mathbb{R}, \quad g(y_1, y_2) = y_1^2 + y_2
$$
$$
h = g \circ f, \quad k = f \circ g
$$
$$
h(x) = (g \circ f)(x) = g(f(x))
$$
$$
= g\left( \begin{bmatrix} \sin(x) \\ \cos(x) \end{bmatrix} \right) = g(y_1, y_2)
$$
$$
= (\sin(x))^2 + \cos(x)
$$
$$
k(y) = k(y_1, y_2) = f(g(y_1, y_2))
$$$$ 
= f(y_1^2 + y_2)
$$$$
= \begin{bmatrix} \sin(y_1^2 + y_2) \\ \cos(y_1^2 + y_2) \end{bmatrix}
$$
Now we want to calculate the different Jacobian-matrixes
$$
J_f(x) = \begin{bmatrix} f_1'(x) \\ f_2'(x) \end{bmatrix} = \begin{bmatrix} \cos(x) \\ -\sin(x) \end{bmatrix} \in \mathbb{R}^{2 \times 1}
$$
$$
J_g(x) = \nabla g(x_i)^T = \begin{bmatrix} 2y_1 & 1 \end{bmatrix} \in \mathbb{R}^{1 \times 2}
$$
$$
J_h(x_i) = h'(x_i) = 2\sin(x) \cos(x) - \sin(x) \in \mathbb{R}^{1 \times 1}
$$
$$
(\sin(x_i^2))' = 2\sin(x) \cos(x)
$$
$$
(x^2)' = 2x
$$
$$
g'(f(x_i)) = g_j'(f(x_i)) f_j'(x)
$$
![[Pasted image 20250211103618.png]]

Based on the theorem we get:
$$
J_k(y_i) = \begin{bmatrix} \cos(x) \\ -\sin(x) \end{bmatrix} \begin{bmatrix} 2y_1 & 1 \end{bmatrix} = \begin{bmatrix} 2y_1 \cos(x) & \cos(x) \\ -2y_1 \sin(x) & -\sin(x) \end{bmatrix}
$$
$$
x = y_1^2 + y_2
$$
$$
= \begin{bmatrix} 2y_1 \cos(y_1^2 + y_2) & \cos(y_1^2 + y_2) \\ -2y_1 \sin(y_1^2 + y_2) & -\sin(y_1^2 + y_2) \end{bmatrix} \quad \text{where} \quad y = \begin{bmatrix} y_1 \\ y_2 \end{bmatrix} \in \mathbb{R}^2
$$
