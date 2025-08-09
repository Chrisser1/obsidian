The **Gram-Schmidt Algorithm** is a method used to convert a set of linearly independent vectors into an **orthonormal** basis for a subspace in an inner product space. 
## **Algorithm** 
Given a set of linearly independent vectors $v_1, v_2, \dots, v_k$ in an inner product space $V$, the algorithm constructs an **orthonormal basis** $u_1, u_2, \dots, u_k$ as follows: 
1. **Initialization**: 
Set the first orthogonal vector as: $$ u_1 = \frac{v_1}{\|v_1\|} $$ 
2. **Orthogonalization**: 
For each subsequent vector $v_i$, subtract its projection onto the previously computed orthonormal vectors: $$ w_i = v_i - \sum_{j=1}^{i-1} \text{proj}_{u_j} (v_i) $$ where the projection is given by: $$ \text{proj}_{u_j} (v_i) = \frac{\langle v_i, u_j \rangle}{\langle u_j, u_j \rangle} u_j $$
3. **Normalization**: 
Normalize the resulting vector: $$ u_i = \frac{w_i}{\|w_i\|} $$
### **Example in $\mathbb{C}^4$** 
From the image, a subspace of $\mathbb{C}^4$ is considered with the given basis vectors:

$$
v_1 = \begin{bmatrix} 2i \\ 0 \\ 0 \\ 1 \end{bmatrix} , \quad v_2 = \begin{bmatrix} i \\ 1 \\ 1 \\ 0 \end{bmatrix} , \quad v_3 = \begin{bmatrix} 0 \\ i \\ 1 \\ 1 \end{bmatrix}
$$Applying Gram-Schmidt to these vectors will yield an orthonormal basis $u_1, u_2, u_3$ for the subspace. 
