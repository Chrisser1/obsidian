![[Pasted image 20250207112114.png]]
![[Pasted image 20250207112129.png]]
#### Answer
To do this we note that a matrix $B$ is symmetrical if and only if $B=B^T$, so we just need to calculate the truncated matrix $B^T$.
$$
	B^T = ((A+A^T)/2)^T = 1/2(A^T+(A^T)^T) = 1/2(A^T+A) = (A+A^T)/2
$$
This is the same as $B$, so the matrix $B$ is symmetrical.

![[Pasted image 20250207112859.png]]
#### Answer
$$
x^TBx = x^T(\frac{A+A^T}{2})x
$$
Using the property of transposition:
$$
x^T(A+A^T)x = x^TAx+x^TA^Tx
$$
Since $x^TA^Tx=(x^TAx)^T$, which is a scalar and equates to $x^TAx$, we get:
$$
x^TA^Tx=x^TAx
$$
therefore:
$$
x^T(A+A^T)x=2x^TAx
$$
We can now finish it off by saying
$$
x^TBx=x^T(\frac{A+A^T}{2})x = \frac{1}{2}(2x^TAx) = x^TAx
$$
![[Pasted image 20250207121200.png]]
#### Answer
Any matrix $A$ can be decomposed into a symmetric and a skew-symmetric part:
$$
A = \frac{A+A^T}{2} + \frac{A-A^T}{2}
$$
* As we can see the first term is $B$ which is symmetric.
* The second term $S$ is skew-symmetric, meaning $S^T = -S$

Now if we consider the quadratic form:
$$
x^TAx=x^TBx+x^TSx
$$
* Then we note that as $S$ is skew-symmetric, then $$ x^TSx = 0 $$ as $x^TSx$ is always zero for any skew-symmetric matrix.
This means the quadratic form simplifies two
$$
	x^TAx=x^TBx
$$
Since any quadratic form can always be rewritten in terms of a symmetric matrix $B$, we can always assume that quadratic forms are given by a symmetric matrix. This shows that any quadratic function of the form:
$$
q(x)= x^TAx + b^Tx + c
$$
can always be represented using a symmetric matrix $A$. 