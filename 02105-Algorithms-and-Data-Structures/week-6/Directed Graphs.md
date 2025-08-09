## Reading

- *Introduction to Algorithms, 4th edition*, Cormen, Rivest, Leiserson, and Stein (CLRS): Introduction to Part VI + Chapter 20.1-20.4 + Appendix B.4-B.5  
- *Competitive Programmer’s Handbook*, Laaksonen (CSES): Chapter 11-12.

---

## Exercises

### 1. Representation, Properties, and Algorithms  
Consider the graphs in Figure 1. Solve the following exercises.
![[Pasted image 20250320081334.png]]
#### 1.1 [w]  
Show adjacency lists and adjacency matrices for (a) and (b).

#### 1.2 [w]  
Run DFS or BFS starting in node 4 in (a) and node 5 in (c) by hand.

#### 1.3  
Which of (a) and (c) are DAGs? If the graph is a DAG, find a topological ordering using the recursive algorithm for topological sorting. If the graph is not a DAG, find a cycle.

#### 1.4  
Specify strongly connected components of (a) and (c).

#### 1.5  
How many topological orderings does (b) have?
#### Svar
Der er $2^3 = 8$ løsninger. 
#### 1.6  
How many strongly connected components does a DAG have?
#### Svar
Der kan ikke være nogen, da DAG ikke må gå i ring.

---

## 2. Snakes and Ladders  
Snakes and Ladders is a classic board game. We will look at the following variant:

The game is played on an \( n \times n \) grid with cells numbered from 1 to \( n^2 \) in order. Special pairs of cells are:
- **Snakes** that lead downwards.
- **Ladders** that lead upwards.

A cell can be the endpoint for, at most, one ladder or snake.

**Goal:** Move from cell 1 to cell \( n^2 \) in the fewest possible rounds.  
- A piece starts on cell 1.
- In each round, you can move the piece at most 5 fields forward.
- If the piece lands on the top of a snake, it moves to the bottom of the snake.
- If the piece lands at the bottom of a ladder, it moves to the top.

#### 2.1  
Give an algorithm to compute the fewest number of rounds needed to move a piece from cell 1 to cell \( n^2 \).
#### Svar
To solve this i will assume that each cell in a row is connected until you make it to the side then the connection is with the above row index in the same column. Based on this we can just use breath first seach to find the shortest path.

---

## 3. DAGs and Topological Sorting

#### 3.1  
Professor Tom Opological suggests the following new and simple algorithm to construct a topological ordering:  
*Run BFS from a node s with in-degree 0 and sort the nodes by increasing distance to s.*  
Does the algorithm work?
#### Svar
Nej det vil ikke virke, da hvis der er en forbindelse mellem to noder i samme lag ville dette ikke længere være topological, men det ville algoritmen sige.
#### 3.2  
Give an algorithm that, given a graph \( G \) and an ordering \( S \) of the nodes in \( G \), determines if \( S \) is a topological ordering.
#### Svar
Start on a node in S and mark it, then mark all nodes that has a path to that node and add them to a list. Then take the first node in the list and mark all nodes that point to that node, while doing this check that a node is not present more than once. If a node is present more than once there is a cycle and it is not topological if not then it is. If you at any point have an empty list and there is still nodes not checked just chose another one of does and keep doing the check.
#### 3.3  
Given a DAG \( G \), does there exist a topological ordering of \( G \) that cannot be produced by the recursive algorithm for topological sorting?
#### IDK
#### 3.4 [∗]  
A **Hamiltonian path** is a path that visits all nodes exactly once.  
Give an algorithm that determines if a DAG has a Hamiltonian path.
#### Svar
Start at a node, check if you can follow a path that visit all nodes, if not try the next node. If you find one then a hamiltonian path exists.

---

## 4. [∗†] Course Planning  
Josefine has spent the entire summer deciding what courses she wants to study at *The University of Algorithms*.

- A course takes **one semester** to finish.
- Some courses depend on other courses.
- If course \( i \) depends on course \( j \), Josefine must take \( j \) before \( i \).
- She wants to finish in the **fewest number of semesters**.
- She can take **unlimited** courses per semester.
- No cyclic dependencies exist.

**Input:**  
1. Line 1: Two integers \( N \) and \( M \), where:
   - \( N \) is the number of courses.
   - \( M \) is the number of dependencies.
2. Lines 2 to \( M+1 \): Two integers \( i \) and \( j \), indicating \( i \) depends on \( j \).

**Output:**  
A single line with the fewest number of semesters needed for Josefine to complete her studies.

Give an **algorithm** for this problem and implement it.

---

## 5. [∗] Ethnographers  

You are helping ethnographers analyze oral history data from a village about people who lived over the past 200 years.  

They collected facts about **n people** (\( P_1, P_2, ..., P_n \)) in the form of:

1. **\( P_i \) died before \( P_j \) was born.**
2. **\( P_i \) and \( P_j \) had overlapping lifespans.**

Memories may be **inconsistent**, and you need to check if the collected data is **internally consistent**.

**Goal:**  
Design an efficient algorithm that:
- Either **produces proposed birth and death dates** for all \( n \) people satisfying the facts.
- Or **reports** that no such dates can exist.

---

## 6. Topological Sorting and DAGs  
Show that a directed graph \( G \) is a DAG **if and only if** \( G \) has a topological sorting.  

*Hint: Use the Lemma on the correctness of topological sorting.*

---

## 7. Three Bottles  

You have **three bottles** with capacities **8, 5, and 3 liters**.  
- Initially, the **8-liter bottle is full**, and the **other two are empty**.
- You need to get **exactly 4 liters** in one bottle.
- Water can only be poured until:
  - The bottle being poured from is **empty**.
  - The bottle being poured into is **full**.

### 7.1 [∗]  
Show that it is possible and find the **shortest sequence** of pouring steps.

### 7.2 [∗]  
Now assume **n bottles** with integer capacities \( d_1, d_2, ..., d_n \) and a target of \( x \) liters.

**Goal:**  
Give an algorithm to compute the **shortest sequence of fillings/empties**.  
*Hint: Model the problem as an implicit graph.*

---
