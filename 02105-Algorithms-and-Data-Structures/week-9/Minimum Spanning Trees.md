*Philip Bille*  
*Inge Li Gørtz*

## Reading
- **Introduction to Algorithms**, 4th edition, Cormen, Rivest, Leiserson, and Stein (CLRS): Chapter 21.1–21.4
- **Competitive Programmer’s Handbook**, Laaksonen (CSES): Chapter 15.

## Exercises

![Figure 1: Graph for the exercises.](path/to/figure1.png)  
*(Note: Add the correct path to the image file.)*

### 1. Algorithms and Properties
Look at the graph G in Figure 1.
![[Pasted image 20250410083547.png]]
#### 1.1 [w]
Run Kruskal’s algorithm on G by hand.
$5 \to 6$ : 1
$6 \to 7$ : 2
$2 \to 4$ : 2
$2 \to 7$ : 4
$0 \to 1$ : 4
$4 \to 6$ : 6 - cycle so not included
$4 \to 5$ : 7 - cycle so not included 
$2 \to 3$ : 7
$0 \to 5$ : 8
$1 \to 2$ : 8 - cycle so not included
$3 \to 8$ : 9 
#### 1.2
Run Prim’s algorithm on G starting in node 0 by hand. Show the contents of the priority queue during the execution.
![[Pasted image 20250410092005.png]]
Que:
$[(0,1 \to 4), (0,5 \to 8)]$ : 1
$[(0,5 \to 8), (1,2 \to 8), (1,5\to11)]$ : 2
$[(5,6\to1),(5,4\to7),(1,2 \to 8), (1,5\to11)]$ : 3
$[(6,7\to2),(6,4\to6),(5,4\to7),(1,2 \to 8), (1,5\to11)]$ : 4
$[(7,2\to4),(6,4\to6),(5,4\to7),(1,2 \to 8), (7,8\to10), (1,5\to11), (7,3\to14)]$ : 5
$[(2,4\to2),(6,4\to6),(2,3\to7),(5,4\to7),(1,2 \to 8), (7,8\to10), (1,5\to11), (7,3\to14)]$ : 6
$[(6,4\to6),(2,3\to7),(5,4\to7),(1,2 \to 8), (7,8\to10), (1,5\to11), (7,3\to14)]$ : is connected
$[(2,3\to7),(5,4\to7),(1,2 \to 8), (7,8\to10), (1,5\to11), (7,3\to14)]$ : 7
$[(5,4\to7),(1,2 \to 8), (3,8\to9) (7,8\to10), (1,5\to11), (7,3\to14)]$ : is connected
$[(1,2 \to 8), (3,8\to9) (7,8\to10), (1,5\to11), (7,3\to14)]$ : is connected
$[(3,8\to9) (7,8\to10), (1,5\to11), (7,3\to14)]$ : 8
#### 1.3
Show all the minimum spanning trees of G.
The one from 1.2 and the same one just where $(0,5\to8)$ is connected. 
#### 1.4
Give an efficient algorithm to find a spanning tree.
Prims algorithm without checking for weights.

---

### 2. Reverse Deletion
Consider the following algorithm to compute a MST:
- Start with a weighted connected graph G.
- Look at the edges of G in order from the heaviest to the lightest edge.
- For each edge, determine if the removal of that edge disconnects the graph.
- If not, remove it; otherwise, leave it.
- Return the final set of remaining edges.

#### 2.1
Run the algorithm on the graph in Figure 1 by hand.
![[Pasted image 20250410093410.png]]
#### 2.2
Argue why the algorithm finds a MST of G.

The Reverse Deletion algorithm finds a MST because it only removes edges that are not essential for connectivity. By removing heavier redundant edges first, it minimizes the total weight while ensuring the final graph remains connected and acyclic, satisfying the definition of a minimum spanning tree.

---

### 3. Properties of MSTs
Let G be a weighted graph.

#### 3.1
Show that the lightest edge in a graph G is in a MST for G. How about the heaviest?
By the cut property, the lightest edge in a graph must be part of some MST because it is the lightest across some cut. However, the heaviest edge is not necessarily in a MST since lighter alternative edges may exist to maintain connectivity while minimizing total weight.

#### 3.2
Assume we scale all the edge weights in G by multiplying them with some value \( c > 0 \). How will the MST look for the new graph?
Multiplying all edge weights by a positive constant c does not change the structure of the MST because the relative order of edges remains the same. Only the total weight of the MST is scaled by c.
#### 3.3
Show that if all edge weights in G are distinct, then there is a unique MST of G.  
*Hint: recall the properties of MSTs.*

When all edge weights are distinct, the lightest edge across every cut is unique. By the Cut Property, this edge must be included in the MST. Since no choices or ties are possible, the MST is unique.

---

### 4. [†] Fiber Optic Cables
The University of Algorithms has N buildings (numbered 1, 2, ..., N). Alice is responsible for ensuring they are all interconnected with the newest fiber optic cables. Two buildings \( i \) and \( j \) can be connected by a fiber optic cable for a certain price.

Alice has been given a list of M prices for pairwise connecting two buildings (buildings not in this list cannot be directly connected). The buildings are said to be all interconnected if and only if there is a path of fiber optic cables between any two buildings (not necessarily direct cables).

#### Task
Give an algorithm that, given the list of prices, determines the lowest total price, ensuring the buildings are interconnected.  
You can assume the buildings can always be interconnected. Implement the algorithm.

#### Input
- Line 1 contains the integers \( N \) and \( M \).
- Line 2..M+1 contains three integers \( i, j, p \) indicating that building \( i \) and \( j \) can be connected for a price of \( p \).

#### Output
- A single integer containing the lowest total price for interconnecting all the buildings.

---

### 5. Maximal Spanning Tree
Given a weighted graph G, give an algorithm to compute a maximal spanning tree of G, i.e., a spanning tree with maximum total weight.  
*Hint: transform the problem.*

We use prims algorithm but choose the largest weight instead of the smallest.

---

### 6. MSTs on Graphs with Non-Distinct Weights

#### 6.1
Show that the cut and cycle properties are also true for graphs where the edge weights do not need to be distinct (the properties must be reformulated accordingly).

When edge weights are not distinct, the cut property says that some minimum-weight edge across any cut must belong to some MST, and the cycle property says that any edge strictly heavier than all others in a cycle cannot belong to any MST.
#### 6.2
Conclude that Prim’s and Kruskal’s algorithms also work in this case.

Since the cut and cycle properties still apply when edge weights are not distinct, Prim’s and Kruskal’s algorithms continue to work correctly and produce an MST. The resulting MST may not be unique due to ties.

#### 6.3
Kruskal’s algorithm can return different MSTs for a graph G depending on how we break ties when sorting the edges.  
Show that for any minimum spanning tree \( T \) in \( G \), there is a way to sort the edges in \( G \) such that Kruskal’s algorithm returns \( T \).

For any minimum spanning tree T of G, we can order the edges so that all edges of T come earlier among edges with equal weight. Then, Kruskal’s algorithm will always pick edges of T when possible, and thus return T.

---

### 7. [∗] MSTs with Small Edge Weights
Let G be a weighted graph with \( n \) nodes and \( m \) edges such that all edge weights are values from {1, 2, ..., 10}.  
Give an efficient algorithm to compute a MST.
