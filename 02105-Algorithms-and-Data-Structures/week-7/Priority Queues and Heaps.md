## Reading
- **CLRS (Introduction to Algorithms, 4th edition)**: Chapter 6 + Appendix B.5
---
## 1. Heap Properties and Simulation
### 1.1 [w]
Which of the following trees are heaps?
![[Pasted image 20250327080531.png]]
![[Pasted image 20250327080914.png]]
a) Is a heap
b) Is not a head because of 19
c) Is a heap 
### 1.2 [w]
Which of the following arrays are heaps? (Index 0 is unused and marked with `−`)
- A = [−, 9, 7, 8, 3, 4] : Is a heap
	- 9 > 7 & 8
	- 7 > 3 & 4
- B = [−, 12, 4, 7, 1, 2, 10] : Not a heap
	- 12 > 4 & 7
	- 4 > 1 & 2
	- 7 is not larger that 10, so not a heap
- C = [−, 5, 7, 8, 3] : Not a heap
	- 5 is not larger than 7 & 8

### 1.3 [w]
Let `S = 4, 8, 11, 5, 21, *, 2, *` be a sequence of operations where a number corresponds to an **insertion**, and * corresponds to an **EXTRACTMAX** operation.  
Starting with an empty heap H, show how H looks after each operation.

$[] \to [4] \to [8,4] \to [11,4,8] \to [11,5,8,4] \to [21, 11, 8, 4, 5] \to [11,5,8,4] \to [11,5,8,4,2] \to [8,5,2,4]$ 
### 1.4
Is a sorted array a heap?
The array [1,2,3,4,5,6] is not a max-heap, because the root (1) is smaller than its children (2,3). It is also not a min-heap, unless we’re careful about how the array maps to the heap tree.
Heap structure depends on **tree relationships**, not just order of elements. 
### 1.5
Where can the minimum element be found in a (max-)heap?
The minimum element in a **max-heap** is located **somewhere among the leaves**—which are found in the **last level** (and possibly the second-last level if the tree isn’t full).

### 1.6
Show that `INSERT`, `EXTRACTMAX`, and `INCREASEKEY` maintain the heap property.
* `INSERT` work by inserting on the lowest leaf and then bubble up while the new key is greater than it's parent, swap them.

* `EXTRACTMAX`, removes and returns the largest element, then you replace the top element with the last element and removes it. After that you heapify (bubble down) from the root: if the root is smaller than any of its children, swap with the largest child. Repeat until heap property is restored.

* `INCREASEKEY`, increases the value of a node's key. It works by replacing the key with a larger value. Then bubble up: if the new value is greater than the parent, swap upward.
### 1.7 [*]
Suppose we have `k` sorted arrays containing in total `n` elements.  
Show how to merge them into a single sorted array in time **O(n log k)**.

---
## 2. Priority Queue Operations

We now want to extend the set of operations on priority queues.  
We are interested in the following operations:

- `REMOVELARGEST(m)`: remove the `m` largest elements in the priority queue.
- `DELETE(x)`: remove the element `x` from the priority queue.
- `FUSION(x, y)`: remove `x` and `y` from the priority queue and add the element `z` with key `x.key + y.key`.
- `THRESHOLD(k)`: return the elements in the priority queue with key ≥ `k`.
- `EXTRACTMIN`: Remove and return the element with the lowest key.

We want to support these efficiently while maintaining the complexities of standard operations (let `n` be the number of elements):

### 2.1
Extend the priority queue to support `REMOVELARGEST(m)` in **O(m log n)** time.
Use `EXTRACTMAX` `m` times, as we then get a complexity of $O(m) \cdot (O(\log{n}) = O(m \log{n})$
### 2.2
Extend the priority queue to support `DELETE` and `FUSION` in **O(log n)** time.

* `DELETE`, can be supported by swapping the element to delete with the last element. It take $O(\log{n})$ time to find the element. After swapping we remove the last element. Then we bubble the swapped element down which takes $O(\log{n})$ time, meaning the hole `DELETE` takes $O(log{n})$ time.

* `FUSION`, find x then find y and add y to x. Then `DELETE` y and bubble x up. As the steps at no point takes more than $O(\log{n})$ time, that is the time complexity.
### 2.3 [*]
Extend the priority queue to support `THRESHOLD` in **O(m)** time, where `m` is the number of elements with key ≥ `k`.

### 2.4 [*]
Extend the priority queue to support `EXTRACTMIN` in **O(log n)** time.

---

## 3. Satellite Data

Let `A[0..n]` be a heap represented as an array. Each element `x` is at index `i`, and the key is `A[i]`.  
Often, extra information (satellite data) is stored with each element (e.g., age, height, etc.).  
Show how to support access to satellite data in **O(1)** time given the index `i`, while maintaining standard heap operation times.
* For this we can just have another array holding the data where each index matches the one in the first array, so whenever an index changes we do the same for the array.

---

## 4. Heap Properties

Let `T` be a complete binary tree of height `h`.

### 4.1
Show the number of nodes in `T` is $n = 2^{h+1} − 1$.  
*Hint: Use $1 + 2 + 4 + ... + 2^h$ and binary representation.*

Induction hypothesis:
We also know that $2^0 = 1 = 2^{0+1}-1$
Assume that for height $h = k$, the number of nodes is:
$$
n = 2^{k+1} − 1
$$
We want to prove this also holds for $h = k+1$.

Induction start:
We know that a binary tree start with one node and adds an extra of $2^h$  nodes for each new height. This gives us:
$$
1 + 2 + 4 + \dots + 2^h
$$
Induction step:
For a tree of height $k+1$:
- The number of nodes is the number of nodes in a full tree of height $k$ (which is $2^{k+1} - 1$ by the hypothesis)
- Plus **$2^{k+1}$** new nodes at the bottom level
so we have
$$
n = (2^{k+1}-1) + 2^{k+1} = 2^{k+2}-1
$$

What we know is that this can be described as:
$$
\sum_0^h 2^h = 1 + 2 + 4 + \dots + 2^h
$$
This is a geometric series with ratio 2:
$$
\sum^h_{i=0}2^i=2^{h+1}−1
$$
### 4.2
Show:  
`S = (n/4)·1 + (n/8)·2 + (n/16)·3 + (n/32)·4 + ... = Θ(n)`  
*Hint: Calculate `S − S/2`.*

We have that: $S = \frac{n}{4}\cdot 1 + \frac{n}{8}\cdot 2 + \frac{n}{16}\cdot 3 + \frac{n}{32}\cdot 4 + \dots$
Then 
$$
S-\frac{S}{2} = (\frac{n}{4}\cdot 1 + \frac{n}{8}\cdot 2 + \frac{n}{16}\cdot 3 + \dots) - (\frac{n}{8}\cdot 1 + \frac{n}{16}\cdot 2 + \frac{n}{32}\cdot 3 + \dots)
$$
Align the terms and subtract:
$$
S-\frac{S}{2} = (\frac{n}{4}\cdot 1) + (\frac{n}{8}\cdot (2-1)) + (\frac{n}{16}\cdot (3 - 2)) + (\frac{n}{32}\cdot (4-3)) + \dots
$$
$$
S-\frac{S}{2} = \frac{n}{4} + \frac{n}{8} + \frac{n}{16} + \frac{n}{32} + \dots
$$
That’s just a geometric series:
$$
S-\frac{S}{2} = \frac{n}{4}(1 + \frac{1}{2} + \frac{1}{4} + \dots) = \frac{n}{4}(\frac{1}{1-\frac{1}{2}}) = \frac{n}{4} \cdot 2 = \frac{n}{2}
$$
Dette giver os, at
$$
S = n
$$
Therefore $S = \theta(n)$

---

## 5. [†] Task Delegation

Josefine manages task delegation in the student organization. Each task has a unique `id` and `difficulty`.

Operations:
- `NEWTASK(i, d)`: Add task with `id=i`, `difficulty=d`.
- `REQUESTTASK()`: Remove and return the task with the highest difficulty.

### Input
- Line 1: Integer `N` = total number of tasks.
- Line 2 to N+1: Either:
  - `N id diff` (new task), or
  - `R` (task request)

### Output
- Line i: The id of the task given to the i-th `REQUESTTASK`.



---

## 6. Sums

Let `A[0..n−1]` be an array of integers. Support:

- `SUM(i, j)`: compute `A[i] + A[i+1] + ... + A[j]`
- `CHANGE(i, x)`: set `A[i] = x`

### 6.1 [w]
Give a simple data structure that supports `SUM` in **O(1)** time and uses **O(n²)** space.
We can precompute all possible subarray sums and store them in a 2D array.
For `A = [2, 4, 6, 1]`, we build the matrix `S`:

| i\j | 0   | 1   | 2   | 3   |
| --- | --- | --- | --- | --- |
| 0   | 2   | 6   | 12  | 13  |
| 1   |     | 4   | 10  | 11  |
| 2   |     |     | 6   | 7   |
| 3   |     |     |     | 1   |
- `SUM(0, 2) = S[0][2] = 12`
- `SUM(1, 3) = S[1][3] = 11`
### 6.2 [*]
Give a data structure that supports `SUM` in **O(1)** time and uses **O(n)** space.

### 6.3 [**]
Give a data structure that supports both `SUM` and `CHANGE` in **O(log n)** time and uses **O(n)** space.
