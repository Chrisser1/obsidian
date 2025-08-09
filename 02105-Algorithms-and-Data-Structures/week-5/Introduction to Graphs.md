**Philip Bille, Inge Li Gørtz**
## Reading

- *Introduction to Algorithms*, 4th edition, Cormen, Rivest, Leiserson, and Stein (CLRS): Introduction to Part VI + Chapter 20.1-20.4 + Appendix B.4-B.5.
- *Competitive Programmer’s Handbook*, Laaksonen (CSES): Chapter 11-12.
![[Pasted image 20250313080910.png]]
---

## Exercises

### 1. Representation, Properties, and Algorithms

Consider the graphs in Figure 1. Solve the following exercises:

1.1 **[w]** Show adjacency lists and adjacency matrices for (a) and (c).
$$
a = 
\begin{bmatrix}
0 & 1 & 0 & 0 & 1 & 1 & 0 & 0 & 0 & 0 \\
1 & 0 & 1 & 0 & 0 & 0 & 1 & 0 & 0 & 0 \\
0 & 1 & 0 & 1 & 0 & 0 & 0 & 1 & 0 & 0 \\
0 & 0 & 1 & 0 & 1 & 0 & 0 & 0 & 1 & 0 \\
1 & 0 & 0 & 1 & 0 & 0 & 0 & 0 & 0 & 1 \\
1 & 0 & 0 & 0 & 0 & 0 & 0 & 1 & 1 & 0 \\
0 & 1 & 0 & 0 & 0 & 0 & 0 & 0 & 1 & 1 \\
0 & 0 & 1 & 0 & 0 & 1 & 0 & 0 & 0 & 1 \\
0 & 0 & 0 & 1 & 0 & 1 & 1 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & 1 & 0 & 1 & 1 & 0 & 0 \\
\end{bmatrix}
$$


1.2 **[w]** Simulate DFS on (a) starting at vertex 0. Assume the adjacency lists are sorted. Specify the DFS-tree and discovery and finish times.
$$
0 \to 1 \to 2 \to 3 \to 4 \to 9 \to 6 \to 8 \to 5 \to 7
$$
Discovery time/finish times:
0: 1/20
1: 2/19
2: 3/18
3: 4/17
4: 5/16
5: 9/12
6: 7/14
7: 10/11
8: 8/13
9: 6/15

1.3 **[w]** Simulate BFS on (a) starting at vertex 0. Assume the adjacency lists are sorted. Specify the BFS-tree and the distance for each vertex.
0: 1
1: 2
2: 3
3: 3
4: 2
5: 2
6: 6
7: 3
8: 3
9: 3
1.4 Specify the connected components of (a), (b), and (c).

1.5 Which of (a), (b), and (c) are bipartite?
c) er den eneste der er bipartite, da den kun har en cyklus på et lige antal.

---

### 2. Depth-First Search using a Stack

Explain how to implement DFS without using recursion. *Hint: use an (explicit) stack.*
Start ved en node, tilføj den til stacken. Derefter tjekker du alle naboer og tilføjer den laveste til stacken ved push og bliver ved indtil der ikke er nogle ikke opdaget noder. Når der ikke er nogle uopdaget noder ved den nuværende node popper du stacken en gang og tjekker om der er en uopdaget node hertil hvis der er tilføjer du den til stacken og går videre, hvis ikke popper du igen og tjekker videre. Til sidst popper du stacken så den er tom og du har tjekket alle muligheder.

---

### 3. Find a Cycle

Give an algorithm that determines if a graph is cyclic, i.e., contains a cycle. How fast is your algorithm?
Brug depth first seach, hvis du finder en der allerede er marked, så er der en cycle.
Time:
$$
O(n + \sum_{v\in V} deg(v))
$$

---

### 4. Number of Shortest Paths

Give an algorithm that, given two vertices `s` and `t` in `G`, returns the number of shortest paths between `s` and `t` in `G`.
Brug breath first seach fra s til t. Gå et lag tilbage fra t's og tæl alle forbindelser fra dette lag til t.

---

### 5. Mazes and Grid Graphs (exam 2010)

A `k × k` **grid graph** is a graph where the vertices are arranged in `k` rows each containing `k` vertices. Only vertices that are adjacent in the horizontal or vertical direction may have an edge between them. See Figure 2(a). Solve the following exercises:
#### 5.1 
Let `n` and `m` denote the number of vertices and edges, respectively, in a `k × k` grid graph. Express `n` and `m` as a function of `k` in asymptotic notation.
#### Svar
Det værste scenarie for m følger formlen: $2 \cdot (k-1) + (k-1)k$ som giver os $O(k^2)$. for n er det $k^2$.

![[Pasted image 20250313094213.png]]
A `k × k` **maze** is a square drawing consisting of `k^2` fields arranged in `k` rows each containing `k` fields. Each of the four sides of each field is either a wall or empty.

A **walk** in a maze is a sequence of fields `f1, ..., fj` such that any pair `f, f'` of consecutive fields in the sequence are adjacent in the horizontal or vertical direction and the shared side of `f` and `f'` is empty.

A maze is **happy** if the following conditions hold:

- There is exactly one unique walk in the maze from `begin` to `end`.
- There is a walk from `begin` to any field in the maze.
- There are no circular walks, i.e., walks that start and end in the same field.

A maze that is **not happy** is *unhappy*. See Figure 2(b)-(d).
#### 5.2 
Explain how to model a `k × k` maze as a `k × k` grid graph.

#### 5.3 
Draw the maze in Figure 2(b) as a grid graph.

#### 5.4 
Give an algorithm that, given a `k × k` maze modeled as a `k × k` grid graph, determines if the maze is happy. Argue the correctness of your algorithm and analyze its running time as a function of `k`.
Brug BFS fra start og tjek om du kan nå til slut og tjek samtidig om du nogensinde møder en vertice som du har besøg, hvis ja er den ikke glad, hvis nej er den glad.

---

### 6. Construction Work **[†]**

Alice and Christa are new students at DTU. Due to all the construction work, it’s very difficult to find their way from one building to another between classes. We want to help Alice and Christa by giving an algorithm to compute whether they can get from building `a` to `b` by following paths.

#### **Input**
- Line 1 contains four integers `N`, `M`, `a`, and `b` separated by spaces, where `N` is the number of buildings, `M` is the number of paths between buildings, `a` is the building they start in, and `b` is the building they want to reach.
- Line 2 to `M+1` each contain two integers `u` and `v`, `0 ≤ u, v ≤ N − 1`, indicating that there is a path between building `u` and `v`.

#### **Output**
A single line with `"YES"` if there is a way to get from building `a` to building `b`, and `"NO"` otherwise.
#### Svar
```python
from collections import deque
N,M,a,b = [int(value) for value in input().split()]
graph = [[] for i in range(N)]

for _ in range(M):
    x, y = [int(i) for i in input().split()]
    graph[x].append(y)
    graph[y].append(x)

visited = [False for i in range(N)]  

def bfs(graph, a):
    cue = deque()
    cue.append(a)
    visited[a] = True
    while cue:
        at = cue.popleft()
        for neighbor in graph[at]:
            if not visited[neighbor]:
                visited[neighbor] = True
                cue.append(neighbor)

bfs(graph, a)
if visited[b]:
    print("TRUE")
else:
    print("FALSE")
```

---

### 7. Euler Tours and Euler Paths

Let `G` be a connected graph with `n` vertices and `m` edges. An **Euler tour** in `G` is a cycle that contains all edges in `G` exactly once. An **Euler path** in `G` is a path that contains all edges in `G` exactly once.

#### 7.1
Which of the drawings below can you draw without lifting the pencil? Can you start and end at the same place?
![[Pasted image 20250313112513.png]]
The first and the second one can be drawn without lifting the pencil. Where for the first one we can also end up in the same place. 
#### 7.2 **[∗]**
Show that `G` has an Euler tour *if and only if* all vertices have even degree.

#### 7.3 **[∗]**
Show that `G` has an Euler path *if and only if* `2` or `0` vertices have odd degree.

#### 7.4
Give an `O(n + m)` time algorithm that determines if `G` has an Euler tour.
BFS ville virke, da vi kan tjekke for hver index om alle vertices har en lige grad.
#### 7.5 **[∗]**
Give an `O(n + m)` algorithm that finds an Euler tour in `G` if it exists.

---

### 8. Diameter of Trees

Let `T` be a tree with `n` vertices. The **diameter** of `T` is the longest shortest path between any pair of vertices in `T`. Solve the following exercises:

#### 8.1
Give an algorithm to compute the diameter of `T` in `O(n^2)` time.
For hvert værdi op til n køres BFS og man finder længden af den længste vej, hvis du for et andet n finder en længere vej brug nu den. Til sidst return den længste fundet vej.
#### 8.2 **[∗∗]**
Give an algorithm to compute the diameter of `T` in `O(n)` time.
