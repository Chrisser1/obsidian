**Philip Bille & Inge Li Gørtz**

## Reading

- _Introduction to Algorithms_, 4th edition, by Cormen, Rivest, Leiserson, and Stein (CLRS): Chapter 22.2-22.4
- _Competitive Programmer’s Handbook_, by Laaksonen (CSES): Chapter 13

![[Pasted image 20250424082652.png]]

## Exercises

### 1. Algorithms and Properties

1. **[w]** Consider the graph provided:
    
    - Show a shortest path tree for the graph starting at node 0.
![[Pasted image 20250424090238.png]]
    - Write the length of the shortest path from node 0 to each node.
1: 6
2: 4
3: 10
4: 3
5: 7
6: 12
7: 16
8: 8
9: 8
10: 12
11: 14
2. Give an example of a graph with negative edges but no negative cycles, causing an incorrect output from Dijkstra’s algorithm.
![[Pasted image 20250424090809.png]]
3. Consider a graph G and a tree T rooted at vertex s. Design an algorithm to verify if T is a shortest path tree from s in G.

Start at vertex s, then run Dijkstra’s algorithm throughout the graph and calculate the length of the 
from s to each node and look up if it matches the node in tree T. If it doesn't match it is not a shortest path tree, if it does, it is.
4. Let T be a shortest path tree from node s in a graph G. If a constant c is added to all edge weights in G, is T still a shortest path tree?

No, adding a constant c to all edge weights can change the shortest path tree. Paths with more edges accumulate more extra cost $n \cdot c$, which can make them no longer optimal. 

### 2. Cable Routing (Exam 2012)
The cable TV company AlgoNet broadcasts cable TV to all the houses in AlgoCity. They transmit the TV signals from their base station through a network of cables, where the length of each cable is known in meters. The cables are routed between a series of boxes. There is a box in each of the houses, one at the base station, and no boxes elsewhere. Each box may be connected to many cables. The network has X houses and K cables. Solve the following exercises.

1. Give an algorithm to route signals to maximize quality, considering signal quality decreases proportionally with cable length.

To maximize signal quality (i.e., minimize total cable length from the base station), model the boxes as nodes and cables as weighted edges. Then, run **Dijkstra’s algorithm** from the base station to find the shortest paths to all houses. The resulting paths define how to route the signals with minimal signal loss.
2. Adjust the algorithm for the scenario where signal quality degrades equivalent to 5 meters of cable length each time it passes through a box.

We model the problem as before, but adjust edge weights: for each edge from node u to v, add 5 meters to represent signal degradation through box v. Then, run Dijkstra’s algorithm from the base station using these adjusted weights to find the optimal signal paths.
3. After cuts in government funding, AlgoNet is looking for ways to save money. Currently, they are spending 42 thousand kr. to maintain one meter of cable every year. Give an algorithm that finds a cheapest way to get a TV signal to all the houses in AlgoCity.

To minimize the total maintenance cost (i.e., total cable length), model the network as an undirected weighted graph with boxes as nodes and cables as edges. Then, compute a Minimum Spanning Tree (MST) using Prim’s or Kruskal’s algorithm. The MST ensures all houses receive a signal with the least total cable length—and therefore the lowest yearly cost.
### 3. Longest Paths in DAGs

Design an algorithm to find the longest path in a Directed Acyclic Graph (DAG).

To find the longest path in a DAG, do a topological sort of the graph. Then, process each node in topological order, relaxing edges by maximizing distances instead of minimizing. This works because DAGs have no cycles, so we can safely compute longest paths in linear order.
### 4. [*] Zombie Travel

In the post-apocalyptic zombie world, you need to know the safest way to travel between two cities so that you can hopefully avoid being eaten by the zombies. You are given a graph G where each node represents a city and each edge a road between two cities. Each edge e has a probability $s(e)$,  $0 \leq s(e) \leq 1$ for surviving traveling on that edge without being eaten. The probabilities on each edge are independent and the probability of surving the entire travel along a path P is the product of the probabilities of surviving on each edge of P.

- Compute the safest route between two cities, maximizing the product of survival probabilities along the path.
![[Pasted image 20250424102442.png]]

Example:
- Direct path $2 \to 4$: 50% survival
- Path $2 \to 3 \to 4$: 63% survival    
- Path $2 \to 3 \to 1 \to 4$: 3.5% survival

To solve this we can modify the question. First we note that a way to calculate this is to just take the product for each edge for the 
### 5. Loopy Trees

A loopy tree is a weighted directed graph from a binary tree with additional edges from each leaf to the root, all with non-negative weights.

1. What is the running time of Dijkstra’s algorithm in terms of nn?
    
2. $[*]$ Propose a faster algorithm.