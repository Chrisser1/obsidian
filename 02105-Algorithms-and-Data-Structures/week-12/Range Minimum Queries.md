**Philip Bille**  
**Inge Li Gørtz**

## Reading

- Notes on Partial Sums and Dynamic Arrays, Chapter 1, 1.1, and 1.3.

## Exercises

### 1. [w] Segment Trees

Consider the array `A = [2, 7, 1, 8, 0, 6, 3, 6]`.  

- Draw the segment tree for A and write down the array corresponding to the segment tree.  

- Show how the tree and the array look after the following operations:  
  - `ADD(2.5)`  
  - `ADD(6, −2)`
![[Pasted image 20250508090034.png]]

### 2. [w] More Segment Trees

Which of the following arrays is a correct segment tree?

- `A1 = [−, 0, 3, 0, 3, 6, 0, 2, 8, 3, 9, 6, 7, 0, 2, 5]` : Correct
- `A2 = [−, 1, 1, 4, 1, 3, 4, 6, 1, 2, 3, 4, 5, 6, 7, 8]` : Wrong
- `A3 = [−, 1, 1, 1, 1, 1, 5, 7, 1, 4, 7, 4, 1, 5, 7, 7]` : Wrong
![[Pasted image 20250508090546.png]]
### 3. Range Sum Queries

Solve the exercise "sums" from the weekplan on priority queues and heaps  
(no longer any [∗] or [∗∗] on the subexercises).
![[Pasted image 20250508090709.png]]
##### 3.1
To do this we build a matrix containing all sum like so:
Given the array $A=[1,2,3,4]$
$$
\begin{array}{c|cccc}
i \backslash j & 0 & 1 & 2 & 3 \\
\hline
0 & 1 & 3 & 6 & 10 \\
1 &   & 2 & 5 & 9 \\
2 &   &   & 3 & 7 \\
3 &   &   &   & 4 \\
\end{array}
$$
Then we can just index into the matrix to get the sum. This will of course use $O(n^2)$ space and as the lookup is constant it takes $O(1)$ time.
##### 3.2
To do this we will create a cumulative sum array, that can look like so:
Given the array $A=[1,2,3,4]$
$$
Sumarray = [1,3,6,10]
$$
Then if we want a sum(2,3) we just choose the index at 3:
$$
Sumarray[3] - Sumarray[2-1] = 10 - 3 = 7
$$
So the algorithm can be written as
```python
def sum(i,j):
	SArray = Sumarray

	if (i > 0):
		return SArray[j] - SArray[i-1]
	else:
		return SArray[j]
```
##### 3.3
To efficiently support both `SUM(i, j)` and `CHANGE(i, x)` operations in $O(\log n)$ time using $O(n)$ space, we can use a **segment tree**.

A **segment tree** is a binary tree data structure where each node represents a range sum of the array. The tree allows:

- `SUM(i, j)` queries in $O(\log n)$ time.
- `CHANGE(i, x)` updates (i.e., point updates) in $O(\log n)$ time. 

![[Pasted image 20250508092721.png]]
### 4. Pizza Prices

Bob lives on P Street in Algotown. There are `n` buildings on the street, and each house has a pizzeria and an apartment. The pizza price in building `k` is `p_k`, and the prices often change.

#### 4.1

Bob often visits his friends in the other buildings on the street, and when they meet, they always eat pizza. They are tired, so they don’t want to walk too long.

Help Bob by giving a data structure that supports the following operations:

- `UPDATE(k, v)`: change the price `p_k` to `v`.
- `FINDCHEAPPIZZA(k, w)`: return the cheapest pizzeria within `w` buildings of apartment `k`.

#### Answer
We build a segment tree where each node stores the **minimum pizza price** in its corresponding range. The original array $P = [p_0, p_1, ..., p_{n-1}]$ contains the prices at each building.

#### Operations:

- **`UPDATE(k, v)`**:  
    Update the price at building `k` to `v`.  
    This is a **point update** in the segment tree and takes $O(\log n)$.

- **`FINDCHEAPPIZZA(k, w)`**:  
    Find the minimum price in the range `[k - w, k + w]`.  
    This is a **range minimum query**, which also takes $O(\log n)$ time.

#### 4.2 [∗]

It’s the end of the month, and Bob and his friends are low on cash and need to find a pizza that costs no more than `p`. They still want to walk as little as possible.

Help Bob by giving a data structure that can support the following operations:

- `UPDATE(k, v)`: change the price `p_k` to `v`.
- `FINDNEARESTPIZZA(k, p)`: return the nearest pizzeria to apartment `k` with a price of at most `p`.  
  If no such pizzeria exists, return **"No money, no pizza!"**.

#### Answer
We still use a **segment tree**, but we now need to find the **nearest** pizza place to index $k$ such that the price is at most $p$. If no such place exists, we return **"No money, no pizza!"**.
To support this, each segment tree node stores:
- The **minimum pizza price** in its range (as before),
- Optionally, a list of candidate indices or a way to retrieve left/right nearest qualifying indices.
#### Operations:
- **`UPDATE(k, v)`**:  
    Update the pizza price at index $k$ to $v$.  
    This is a point update, done in $O(\log n)$ time.
    
- **`FINDNEARESTPIZZA(k, p)`**:  
    To find the nearest index $j$ such that $|j - k|$ is minimized and $p_j \leq p$:    
    1. Perform a binary search on increasing distances $d = 0, 1, 2, \ldots$
    2. For each distance, check indices $k - d$ and $k + d$ (if in bounds).
    3. Stop at the first index with $p_j \leq p$.
Each check uses a segment tree range query over single elements (or cached values). The worst-case time complexity is $O(\log n \cdot \log n)$, but it's often faster in practice due to early termination.
### 5. [∗] Range Updates

In the range update problem, we want to preprocess an array `A` to support the following operations efficiently:

- `ADD(i, j, k)`: Add `k` to each of the entries `A[i]` to `A[j]`.
- `LOOKUP(i)`: Return the value `A[i]`.

Give an efficient solution to solve the range update problem.
