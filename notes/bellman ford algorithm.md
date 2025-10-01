---
updated: 2025-09-30T16:42
created: 2025-05-23T10:34
---
#dsa/algo
algorithm to find shortest distances of a DAG with negative weights. (related: [[djikstra's algorithm]])

loop `v` times, each time updating every edges shortest distance
### python implementation
```python
def bellman_ford(self, src):
    # Step 1: fill the distance array and predecessor array
    dist = [float("Inf")] * self.V
    dist[src] = 0

    # Step 2: relax edges |V| - 1 times
    for _ in range(self.V - 1):
        for s, d, w in self.graph:
            if dist[s] != float("Inf") and dist[s] + w < dist[d]:
                dist[d] = dist[s] + w

    # Step 3: detect negative cycle
    # if value changes then we have a negative cycle 
    # and we cannot find the shortest distances in the graph
    for s, d, w in self.graph:
        if dist[s] != float("Inf") and dist[s] + w < dist[d]:
            print("Graph contains negative weight cycle")
            return
```
