**Philip Bille**  
**Inge Li Gørtz**

## Reading

- *Introduction to Algorithms*, 4th edition, Cormen, Rivest, Leiserson, and Stein (CLRS): Chapter 19.1–19.4  
- *Algorithms*, 4th edition, Sedgewick and Wayne: Chapter 3.3

---

## Exercises

### 1. Run Union Find by Hand

Look at the following sequence of operations:  
`INIT(7), UNION(3, 4), UNION(5, 0), UNION(4, 5), UNION(4, 3), UNION(0, 1), UNION(2, 6), UNION(0, 4), UNION(6, 0)`
#### 1.1 [w]
Run the sequence using **quick find** by hand. Show the contents of the `id` array after every step.  
Assume `UNION(i, j)` updates `id` for the set given by `i`.

- INIT(7):        [0, 1, 2, 3, 4, 5, 6]
- UNION(3, 4):    [0, 1, 2, 4, 4, 5, 6]
- UNION(5, 0):    [0, 1, 2, 4, 4, 0, 6]
- UNION(4, 5):    [0, 1, 2, 0, 0, 0, 6]
- UNION(4, 3):    [0, 1, 2, 0, 0, 0, 6]
- UNION(0, 1):    [1, 1, 2, 1, 1, 1, 6]
- UNION(2, 6):    [1, 1, 6, 1, 1, 1, 6]
- UNION(0, 4):    [1, 1, 6, 1, 1, 1, 6]
- UNION(6, 0):    [1, 1, 1, 1, 1, 1, 1]
#### 1.2 [w]
Run the sequence using **quick union** by hand. Show the trees after every step.  
Assume `UNION(i, j)` sets the **root of the tree given by `i`** to be a **child of the root of the tree given by `j`**.
![[Pasted image 20250402151028.png]]
#### 1.3
Run the sequence using **weighted quick union** by hand. Show the trees after every step.  
Assume `UNION(i, j)` sets the root of the tree given by `i` to be a child of the root of the tree given by `j` when the sizes of the two trees are equal.

#### 1.4
Show the result of **path compression** after a `FIND(x)` operation, where `x` is:
- a leaf,
- an internal node of depth 1,
- and an internal node of height 1  
in one of the trees from the above exercises.
![[Pasted image 20250402154141.png]]
#### 1.5
Give a sequence of operations that results in a tree of **maximal depth** using **quick union**.
* INIT(7)
* UNION(0, 1)
* UNION(1, 2)
* UNION(2, 3)
* UNION(3, 4)
* UNION(4, 5)
* UNION(5, 6)
#### 1.6
Give a sequence of operations that results in a tree of **maximal depth** using **weighted quick union**.
- INIT(7)
- UNION(0, 1)
- UNION(2, 3)
- UNION(1, 3)
- UNION(4, 5)
- UNION(3, 5)
- UNION(6, 3)

Final root: 3  
Max depth: 3
#### 1.7
Write pseudocode for an algorithm to do **path compression**.  
Hint: traverse the path twice.
``` python
function FIND(x)
    root ← x
    while root ≠ id[root] do
        root ← id[root]
    
    // Second pass: path compression
    while x ≠ id[x] do
        parent ← id[x]
        id[x] ← root
        x ← parent
    
    return root
```
---

### 2. Alternative to the Quick Find Algorithm

One student suggests the following variant of quick find `UNION`.  
Does it work?

```plaintext
UNION(i, j)
if FIND(i) ≠ FIND(j) then
  for k = 0 to n - 1 do
    if id[k] == id[i] then
      id[k] = id[j]
    end if
  end for
end if
```

The student’s version **modifies the id array during the loop**, while still using the **original `id[i]`** as the comparison.

But here’s the subtle issue:
- `id[i]` **can change during the loop** if `i == k`
- So you’re comparing against a **moving target**

Let’s say:
```python
id = [0, 0, 2, 3] 
i = 0, j = 2 
FIND(i) = 0 
FIND(j) = 2
```
Now when we run this line-by-line:
```python
for k = 0 to 3:
	if id[k] == id[i]: # remember: id[i] is 0 initially     
		id[k] = id[j]  # id[j] is 2
```
**Step 1** 
- `id[0] == 0` → match → `id[0] = 2`
- Now `id[i]` (i = 0) is `2`
**Step 2: k = 1**
- `id[1] == 0` **(false)** ← but it should have matched!

### 3. Dynamic Connected Components and Graph Search
Using graph search (DFS or BFS) we can find the connected components of a graph. Give a simple solution for dynamic connected component using graph search and compare the complexity with the solutions based on union find.

Using DFS or BFS, we can check if two nodes are connected.
```python
def isConnected(A, B, adj):
    visited = [False] * len(adj)
    dfs(A, visited)
    return visited[B]

def dfs(v, visited):
    visited[v] = True
    for u in adj[v]:
        if not visited[u]:
            dfs(u, visited)
```
$$
\begin{matrix}
Operation & Graph Search & Union Find \\
CONNECTED(A, B) & O(N + M) & O(α(N)) \\
ADD EDGE(A, B) & O(1) & O(α(N)) via UNION \\
\text{Good for} & \text{Static graph} & \text{Dynamic graph} \\
\end{matrix}
$$
### 4 [†] Computer Network
Josefine is setting up a new computer network at The University of Algorithms. The network consists of N computers numbered from 0 to N −1 that are initially not connected at all. She builds the network by adding network cables between pairs of computers one at a time. Two computers, A and B, are connected if there is at least one series of cables that leads from computer A to computer B. As other students need to use connected computers while setting up the network, she needs to be able to answer if two specific computers are connected at a specific time. More precisely, we want to support the following operations:

* ADDCABLE(A, B): Add a cable between computers A and B. 
* CONNECTED(A, B): Return "Yes" if there is a series of cables that leads from computer A to computer B and "No" otherwise. 
Give a data structure for this problem and implement it.

**Input** 
Line 1 contains integers N and M, where N is the number of computers and M is the total number of ADDCABLE/CONNECTED operations. Line 2 . . . M + 1 can be either an ADDCABLE operation indicated by the letter A followed by two integers specifying the two computers or a CONNECTED operation indicated by the letter C also followed by two integers specifying two computers. 

**Output** Line i is result of the ith CONNECTED operation.

```python
class UnionFind:
    def __init__(self, n):
        self.parent = list(range(n))
        self.size = [1] * n

    def find(self, x):
        # Path compression
        if self.parent[x] != x:
            self.parent[x] = self.find(self.parent[x])
        return self.parent[x]

    def union(self, x, y):
        # Weighted union
        root_x = self.find(x)
        root_y = self.find(y)

        if root_x == root_y:
            return

        if self.size[root_x] < self.size[root_y]:
            self.parent[root_x] = root_y
            self.size[root_y] += self.size[root_x]
        else:
            self.parent[root_y] = root_x
            self.size[root_x] += self.size[root_y]

    def connected(self, x, y):
        return self.find(x) == self.find(y)

def process_network():
    import sys
    input = sys.stdin.read
    data = input().splitlines()

    # Parse input
    N, M = map(int, data[0].split())
    uf = UnionFind(N)

    results = []

    for line in data[1:]:
        parts = line.split()
        op, a, b = parts[0], int(parts[1]), int(parts[2])

        if op == 'A':
            uf.union(a, b)
        elif op == 'C':
            results.append("Yes" if uf.connected(a, b) else "No")

    # Print output for CONNECTED queries
    for result in results:
        print(result)

process_network()
```

### 5 [∗] Zombie Invasion 
In the post apocalyptic zombie world you and a small group of survivors have barricaded yourself in a small building. The only thing keeping the brutal zombies from eating you is a strong fortification. The fortification consists of a k × k grid of walls. Here illustrated by a 6 × 6 grid of walls. 
![[Pasted image 20250403094625.png]]
In the top of the grid the zombies are waiting to come in, and you and your group is located in the bottom. Unfortunately, the walls are weak and collapse regularly. If a path of walls between the top and the bottom of the grid is collapsed the zombies can get in and eat you. In order to start evacuation you want to monitor if there currently is a path through the fortification (from top to bottom). Give a data structure that can efficiently keep track of this while the walls are collapsing one by one.

Data Structure: Union-Find:

### 6 [∗] Recursive Path Compression
Write pseudo code for a recursive algorithm for path compression. Hint: it can be done with only few lines of code.

### 7 Union Find using Linked Lists and Weights
We want to implement a variant of quick find using linked lists in the following way. Each set is represented by a singly linked list. The representative for a set is the first element in the list and each element in the list has a pointer to the representative. Furthermore we maintain a pointer to the tail of the list. For instance, the data structure for the set {1, 4, 7, 8, 14} with representative 7 could look like this:
![[Pasted image 20250403094712.png]]

* 7.1 Using the representation, show how to implement INIT(n) in O(n) time, FIND(i) in O(1) time and UNION(i, j) in O(|S(i)|) time, where S(i) is the set containing i. 

* 7.2 Show how to extend the solution such that INIT and FIND runs in the same time as the previous exercise, but the time for UNION(i, j) is O(min(|S(i)|,|S(j)|)). Hint: maintain a little extra information. 

* 7.3 [∗] Show that for p FIND and m UNION operations on n elements the above solution gives the running time O(p + m log n).