![[Pasted image 20250220085751.png]]
#### Answer(2.1)
```python
def has_duplicates(A):
    '''
    Checks if the array has duplicates
    '''
    for i in range(1,len(A)):
        for j in range(0,i):
            if A[i] == A[j]:
                return True
    return False
```
#### Answer(2.2)
To do this we can just use merge sort and check if any of the elements are the same while we sort, this would allow us to do it in $\mathcal{O}(n \cdot log(n))$ time.

#### Answer(2.3)
Again we just sort using merge sort and do a additional linear scan that finds the two closest values. This would have a complexity of $\mathcal{O}(n \cdot log(n)) + \mathcal{O}(n) = \mathcal{O}(n \cdot log(n))$, the overall algorithm meets the required time complexity.