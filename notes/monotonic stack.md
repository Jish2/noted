---
created: 2024-04-12T17:23
updated: 2025-09-30T16:09
---
#dsa/stack
stack that contains elements in increasing or decreasing order

pops all elements until new element is greater / less than or equal to top

## Psuedo Code
```python
num = [1,5,3,6,4]
stack = []
for num in nums:
  while stk and stk[-1] > num:`
    stk.pop()`
  stk.append(num)
```

## Related Problems
- [[402. Remove K Digits]]