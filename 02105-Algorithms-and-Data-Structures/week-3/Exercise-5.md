![[Pasted image 20250220094725.png]]
#### Answer (5.1)
```python
def two_sum(A:list[float]) -> bool:
    '''
    Returns True if there are two numbers in the list that add up to 0
    '''
    
    for i in range(len(A)):
        for j in range(i,len(A)):
            if A[i] + A[j] == 0:
                return True
    # If no such pair exists return False
    return False
```
#### Answer (5.2)
```python
def two_sum(A:list[float]) -> bool:
    '''
    Returns True if there are two numbers in the list that add up to 0
    '''
    A.sort() # Resume that we use binary search
  
    for i in range(len(A)):
        target = -A[i]
        if binary_search(A, target, i):
            return True
	# If no such pair exists return False
    return False
```
