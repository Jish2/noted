---
created: 2024-12-09T14:29
updated: 2024-12-09T14:29
---
#dsa/linked-list #pattern

```python
slow, fast = head, head
while fast and fast.next:
    slow = slow.next
    fast = fast.next.next
```

## odd linked list
```
O -> O -> O -> O -> O
1    2    3                  (slow)
1         2         3        (fast)
```
## even linked list
**the fast pointer will be at second to last node
```
O -> O -> O -> O -> O -> O
1    2    3                  (slow)
1         2         3        (fast)
```
