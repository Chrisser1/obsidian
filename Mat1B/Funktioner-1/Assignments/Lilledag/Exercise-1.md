![[Pasted image 20250207085455.png]]![[Pasted image 20250207085516.png]]
#### Answer
First we will calculate the length of the vectors based on the formula from [[obsidian/Mat1B/Funktioner-1/Inner product and norm]]:
$$ \|\mathbf{x}\| = \sqrt{x_1^2 + x_2^2 + \dots + x_n^2} $$
* $\|\mathbf{v_1}\| = \sqrt{(-10)^2+(-10)^2+(-10)^2} = \sqrt{300}$
* $\|\mathbf{v_2}\| = \sqrt{(-10)^2+(-4)^2+14^2} = \sqrt{312}$
* $\|\mathbf{v_3}\| = \sqrt{(-10)^2+(-8)^2+(-12)^2} = \sqrt{308}$

As we can see the largest vector is $v_2$.

Let's now check for [[Orthogonality (ortogonele)]], we note that two vectors are orthogonal if $\langle \mathbf{x}, \mathbf{y} \rangle = 0$. So let's calculate the inner product to check which can be calculated via the formular:$$ \langle \mathbf{x}, \mathbf{y} \rangle = \mathbf{y}^T \mathbf{x} $$
* $\langle \mathbf{v_1}, \mathbf{v_2} \rangle = (-10)(-10) + (-10)(-4) + (-10)(14) = 0$ 
* $\langle \mathbf{v_1}, \mathbf{v_3} \rangle = (−10)(−10)+(−10)(−8)+(−10)(−12) = 300$
* $\langle \mathbf{v_2}, \mathbf{v_3} \rangle = (−10)(−10)+(−4)(−8)+(14)(−12) = -36$

So only $v_1$ and $v_2$ is orthogonal.  

Lastly we want to find which are the closest to each other which can be done via our knowledge from [[Distance between vectors]] where we use the formulars:
$$ d(\mathbf{x}, \mathbf{y}) = \|\mathbf{x} - \mathbf{y}\| $$$$ \|\mathbf{x} - \mathbf{y}\| = \sqrt{(x_1 - y_1)^2 + (x_2 - y_2)^2 + \dots + (x_n - y_n)^2} $$
* $\|\mathbf{V_1} - \mathbf{V_2}\| = \sqrt{(-10 + 10)^2 + (-10 + 4)^2 + (-10 - 14)^2} = \sqrt{612}$
* $\|\mathbf{V_1} - \mathbf{V_3}\| = \sqrt{(−10+10)^2+(−10+8)^2+(−10+12)^2} = \sqrt{8}$
* $\|\mathbf{V_2} - \mathbf{V_3}\| = \sqrt{(−10+10)^2+(−4+8)^2+(14+12)^2} = \sqrt{692}$
 
The smallest distance is between $v_1$​ and $v_3$​, meaning they are the closest vectors.
