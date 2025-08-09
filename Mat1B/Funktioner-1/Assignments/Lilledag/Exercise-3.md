![[Pasted image 20250207102120.png]]
![[Pasted image 20250207102137.png]]
![[Pasted image 20250207104220.png]]
![[Pasted image 20250207104234.png]]

![[Pasted image 20250207103520.png]]
#### Answer
A quadratic form is uniquely determined if and only if the matrix $A$ in the expression:
$$ q(\mathbf{x}) = \mathbf{x}^T A \mathbf{x} + \mathbf{b}^T \mathbf{x} + c $$
is symmetric. This is because for any quadratic form, the symmetric part of $A$ uniquely defines the expression.
![[Pasted image 20250207104408.png]]
From the Python computations, we obtained the quadratic forms where $q_1(x_1, x_2)$ and $q_2(x_1, x_2)$ have the same expression. But as $A_1 \neq A_2$. This means that different matrices can lead to the same quadratic function, contradicting the uniqueness requirement.
![[Pasted image 20250207105221.png]]
#### Plot of $q_1$
![[Pasted image 20250207105716.png]]
#### Plot of $q_3$
![[Pasted image 20250207105748.png]]
#### Plot of contour $q_1$
![[Pasted image 20250207110950.png]]
#### Plot of contour $q_3$
![[Pasted image 20250207111025.png]]
#### Code for plots:
Note that q1 and q3 have been defined before, but is not shown in the code.
```python
from dtumathtools.dtuplot import plot3d, plot_contour

plot3d(q1, (x1, -10, 10), (x2, -10, 10), title='q1', xlabel='x1', ylabel='x2')

plot3d(q3, (x1, -10, 10), (x2, -10, 10), title='q3', xlabel='x1', ylabel='x2')

plot_contour(q1, (x1, -10, 10), (x2, -10, 10), is_filled=False, title='q1', xlabel='x1', ylabel='x2')

plot_contour(q3, (x1, -10, 10), (x2, -10, 10), is_filled=False, title='q1', xlabel='x1', ylabel='x2')
```
![[Pasted image 20250207111242.png]]
#### Answer
We can answer this by analyzing the contour plots:
- The level curves of $q_1(x_1, x_2)$ form hyperbolas, which indicates that the function does not have a unique minimum.
- The level curves of $q_3(x_1, x_2)$ form ellipses, which suggests that the function has a minimum point.
By observing the ellipse in $q_3$ plot we can determine that the point is about $(2,1)$. For $q_1$ we see that it instead has a saddle point, where the function behaves differently along different directions.