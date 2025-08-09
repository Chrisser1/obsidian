**Philip Bille**  
**Inge Li Gørtz**

## Reading

- *Introduction to Algorithms*, 4th edition, Cormen, Rivest, Leiserson, and Stein (CLRS): Chapter 12  
- *Algorithms*, 4th edition, Sedgewick and Wayne: Chapter 3.3

## Exercises

### 1. Basics of Binary Search Trees
![[Pasted image 20250501085507.png]]
**1.1 [w]** Which of the following trees are binary search trees?

The only one that is a binary tree is b)

**1.2 [w]** Where are the elements with the smallest and largest key located in a binary search tree?

The smallest element is found be following the left nodes all the way to the end. For the largest you just go right. 

**1.3 [w]** Consider the set of keys `{1, 4, 5, 10, 16, 17, 21}`.  
Draw binary search trees of height 2, 3, 4, 5, and 6 containing these keys.

**1.4 [w]** Specify the preorder, inorder, or postorder sequence of keys for the tree in (b).

Inorder: {1,2,7,8,9,10,13,17,18}
preorder: {9,7,2,1,8,17,13,10,18}
postorder: {1,2,8,7,10,13,18,17,9}

**1.5** Compare the heap property and the search tree properties.
- **Heap Property**:  
  In a min-heap, each parent node is ≤ its children (max-heap: ≥). No ordering between left and right children.

- **Binary Search Tree (BST) Property**:  
  For each node, all keys in the left subtree are < the node, and all keys in the right subtree are > the node.

| Feature       | Heap                     | Binary Search Tree (BST)         |
|---------------|--------------------------|----------------------------------|
| Ordering      | Partial (parent vs child)| Total (left < root < right)      |
| Search Time   | O(n)                     | O(log n) in balanced BST         |
| Use Case      | Priority queues          | Efficient searching/sorting      |

**1.6 [w]** Write pseudo-code for computing the inorder traversal of a binary search tree.

```Python
def inorder_traversal(self):  
    result = []  
    def _inorder(node):  
        if node:  
            _inorder(node.left)  
            result.append(node.key)  
            _inorder(node.right)  
    _inorder(self.root)  
    return result
```

**1.7** Show that if a node `v` in a binary search tree has 2 children, then:
- The node with the smallest key > `v.key` has no left child.
- The node with the largest key < `v.key` has no right child.  
_Assume that all keys are distinct. Hint: prove it by contradiction._

**1.7** Proof (by contradiction):

- Let `s` be the node with the **smallest key > v.key** (the **successor** of `v`).  
  If `s` had a left child, say `x`, then `x.key < s.key` but `x.key > v.key`, contradicting that `s` is the smallest key > `v.key`.  
  `s` has **no left child**.

- Let `p` be the node with the **largest key < v.key** (the **predecessor** of `v`).  
  If `p` had a right child, say `y`, then `y.key > p.key` but `y.key < v.key`, contradicting that `p` is the largest key < `v.key`.  
  `p` has **no right child**.

---

### 2. Basics of 2-3 Trees

![[Pasted image 20250501100059.png]]

**2.1 [w]** Consider the following 2-3 tree.  
Insert the sequence of keys `4, 10, 1`. Show the resulting tree after each step.
![[Pasted image 20250501192826.png]]

![[Pasted image 20250501192838.png]]


![[Pasted image 20250501192851.png]]

**2.2** Consider a 2-3 tree `T` with `n` items.  
What is the maximum height and the minimum height of `T`?  
Conclude that the height of `T` is always Θ(log n).

Maximum height: when all nodes are 2-nodes  
Height = log₂(n)

Minimum height: when all nodes are 3-nodes  
Height = log₃(n)

Conclusion:  
The height of `T` lies between log₃(n) and log₂(n),  
so the height is Θ(log n)

---

### 3. Queries on Balanced Search Trees

Consider the following queries on 2-3 trees `T`:

- **PREDECESSOR(k):** return the element with the largest key in `T` that is ≤ `k`.
- **RANGEREPORT(k1, k2):** return the set of elements with keys in the range `[k1, k2]`.
- **RANGECOUNT(k1, k2):** return the number of elements with keys in the range `[k1, k2]`.

Examples for the small tree in Exercise 2.1:
- `PREDECESSOR(3)` → 2  
- `PREDECESSOR(7)` → 6  
- `PREDECESSOR(6)` → 6  
- `RANGEREPORT(3, 8)` → {5, 6}  
- `RANGECOUNT(3, 8)` → 2

**3.1** Give an algorithm that supports PREDECESSOR in O(log n) time.
As we traverse from root to leaf:
- We **track the best candidate** seen so far that is $\leq$ `k`.
- At each node, we compare `k` with the keys in the node and decide which child to follow.

**3.2** Give an algorithm that supports RANGEREPORT in O(log n + occ) time, where `occ` is the number of elements in the output.
This is similar to an **in-order traversal**, but **pruned** to only explore relevant subtrees:
- Traverse **only parts of the tree that intersect [k1, k2]**.
- At each node, check:
    - If `key < k1`: go right.
        
    - If `key > k2`: go left.
        
    - If `k1 ≤ key ≤ k2`: report the key, and explore both children.

This gives:
- **O(log n)** to reach the range start.
- **O(occ)** to output matching elements.


**3.3** Give an algorithm that supports RANGECOUNT in O(log n) time.  
Here you will need to store and maintain some additional information in the data structure.
To compute `RANK(k)`:
1. Traverse from root to leaf.
2. At each node:
    - If `k < key[0]`: go left
    - If `k ≥ key[0]`: add:
        - Left subtree size
        - Plus 1 if key[0] ≤ k
        - Recurse to the middle or right child
    - For 2-key nodes, similar logic extends to key[1]
---

### 4. Inventory Management

Suppose you are running a business that sells recycled single socks.  
Each sock is identified by a **size** and a **color**, both integers.  
You want to maintain a database `D` of socks that supports:

- **NEW(s, c):** Add a new sock of size `s` and color `c` to `D`.
- **SELL(s, c):** Remove a sock of size `s` and color `c`. Return `"unavailable"` if there is no such sock in `D`.
- **UNIQUE:** Return the total number of distinct socks in `D` (i.e., different `(s, c)` pairs).
- **MAXFREQUENT:** Return the most frequent sock in `D`. If multiple, return any of them.

**4.1** Give an efficient data structure that supports NEW, SELL, and UNIQUE.

**4.2 [∗]** Give an efficient data structure that supports all operations.

