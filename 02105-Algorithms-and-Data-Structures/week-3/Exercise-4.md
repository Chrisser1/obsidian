![[Pasted image 20250220093717.png]]
## Base Case
- **When $n = 1$:**
  An array with a single element is trivially sorted. Thus, merge sort returns the array as is, which is sorted.
## Inductive Hypothesis
- **Assumption:**
  Assume that merge sort correctly sorts any array of length less than $n$. That is, for any array $A$ with $k$ elements, where $k < n$, merge sort produces a sorted array.
## Inductive Step
- **For an array $A$ with $n$ elements:**
  1. **Divide:**
     The algorithm divides the array $A$ into two subarrays:
     - $L$: the left half of $A$
     - $R$: the right half of $A$
     The sizes of $L$ and $R$ are both less than $n$ (i.e., $|L| \leq \lceil n/2 \rceil$ and $|R| \leq \lfloor n/2 \rfloor$).
  2. **Conquer:**
     By the inductive hypothesis, merge sort correctly sorts these two subarrays.
     - Let $L'$ be the sorted version of $L$.
     - Let $R'$ be the sorted version of $R$.
  3. **Combine:**
     The `merge` function is then used to combine $L'$ and $R'$ into a single sorted array. By our assumption, `merge` correctly merges two sorted arrays.
- **Result:**
  Since both $L'$ and $R'$ are sorted and the merging step produces a sorted array from them, the final output of merge sort is a correctly sorted array of $n$ elements.