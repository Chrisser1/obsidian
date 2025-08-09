#### Definition 
The **distance** between two vectors $\mathbf{x}, \mathbf{y}$ in an inner product space is given by the Euclidean norm of their difference: $$ d(\mathbf{x}, \mathbf{y}) = \|\mathbf{x} - \mathbf{y}\| $$ Using the norm formula: $$ \|\mathbf{x} - \mathbf{y}\| = \sqrt{(x_1 - y_1)^2 + (x_2 - y_2)^2 + \dots + (x_n - y_n)^2} $$
#### Finding the Closest Vectors
To determine which vectors are the closest, we can compute the **cosine similarity**, given by: $$ \cos \theta = \frac{\langle \mathbf{x}, \mathbf{y} \rangle}{\|\mathbf{x}\| \|\mathbf{y}\|} $$The cosine similarity measures how aligned two vectors are, with: 
* $\cos \theta = 1$ meaning the vectors are identical in direction, 
* $\cos \theta = 0$ meaning the vectors are orthogonal, 
* $\cos \theta = -1$ meaning the vectors point in opposite directions.