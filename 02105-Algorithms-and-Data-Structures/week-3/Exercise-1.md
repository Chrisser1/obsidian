![[Pasted image 20250220080055.png]]
#### Answer (1.1)
$$
[31,41,59,26,41,58] \to [26,31,41,59,41,58] \to [26,31,41,41,59,58] \to [26,31,41,41,58,59] 
$$
#### Answer (1.2)
```python
def INSERTIONSORT(A, n):
    '''
    Sorts in non-decreasing order
    '''
    for i in range(1,n):
        j = i
        while j > 0 and A[j] > A[j-1]:
            A[j], A[j-1] = A[j-1], A[j]
            j = j - 1
```
#### Answer(1.3)
$$
[3,41,52,26,38,57,9,49] \to [3,41,52,26] \quad [38,57,9,49] \to [3,41] \quad [52,26] \quad [38,57] \quad [9,49]
$$
$$
\to [3],[41],[52],[26],[38],[57],[9],[49] \to [3,41] \quad [26,52] \quad [38,57] \quad [9,49]
$$
$$
\to [3,26,41,52] \quad [9,38,49,57] \to [3,9,26,38,41,49,52,57]
$$
#### Answer(1.4)
When inserting $A[n-1]$ into the sorted array the worst case scenario requires comparing $A[n-1]$ elements with each of the $n-1$ elements (if $A[n-1]$ is the smallest element). Therefore, the insertion step takes $\mathcal{O}(n)$ time.

We can now say that the recurrence relation for the running time is
$$
T(n) = T(n-1)+\mathcal{O}(n)
$$
with the base case $T(1)=\mathcal{O}(1)$ (since an array with one element is already sorted).

**Solving the Recurrence**
We can solve this recurrence by expanding it:
$$
T(n) = T(n-1)+\mathcal{O}(n)
$$
$$
= (T(n-2)+\mathcal{O}(n-1))+\mathcal{O}(n)
$$
$$
= T(n-2)+\mathcal{O}(n-1)+\mathcal{O}(n)
$$
$$
\vdots
$$
$$
= T(1)+\mathcal{O}(2) + \mathcal{O}(3) + \mathcal{O}(n)
$$
$$
= \mathcal{O}(1) + \sum^n_{k=2}\mathcal{O}(k)
$$
The summation $\sum^n_{k=2}k$ is an arithmetic series that sums to:
$$
\sum^n_{k=2}k = \frac{n(n+1)}{2}-1 = \mathcal{O}(n^2)
$$
thus,
$$
T(n) = \mathcal{O}(n^2)
$$
#### Answer(1.5)
No binary search would not work with insertion sort as the swap needs to be done with all elements larger not just at the index where the element should be at.


