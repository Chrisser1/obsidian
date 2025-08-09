![[Pasted image 20250211114225.png]]
![[Pasted image 20250211114235.png]]
#### Definition of an Open Set
A subset $M \subseteq \mathbb{R}^n$ is **open** if:
$$
\forall x_0 \in M, \quad \exists r > 0 : B(x_0, r) \subseteq M
$$
where:
- $B(x_0, r)$ represents an **open ball** centered at $x_0$ with radius $r$.
- This means that for every point in $M$, we can find a small enough **neighborhood** (ball) that is completely contained within $M$.
#### Definition of a Closed Set
A subset $M \subseteq \mathbb{R}^n$ is **closed** if its complement $\mathbb{R}^n \setminus M$ is **open**, meaning:
$$
M \text{ is closed if } \mathbb{R}^n \setminus M \text{ is open}.
$$
- This implies that a closed set contains all its **limit points**.
- The complement $\mathbb{R}^n \setminus M$ must satisfy the open set condition.
#### Summary:
- **Open sets** contain a small ball around each point inside them.
- **Closed sets** contain all their boundary points.
- The complement of an **open set** is **closed**, and vice versa.