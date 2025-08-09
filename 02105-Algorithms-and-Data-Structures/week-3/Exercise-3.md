![[Pasted image 20250220092432.png]]
#### Answer
First sort the stones, and then begin by taking the lightest stone add it's weight to a sum and keep going until the sum is larger than $W$ and the count of stones before is then the maximal number of stones she can bring home.

```python
def max_stones(max_weight: float, stones: list[float]) -> int:
    '''
    Returns the maximum number of stones that can be carried
    '''
    stones.sort()
    count = 0
    
    for i in range(n):
        if max_weight >= stones[i]:
            max_weight -= stones[i]
            count += 1
    return count
```

