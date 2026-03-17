# Ex. No: 18C - Dijkstra's Single Source Shortest Path Algorithm

## AIM:
To write a Python program for **Dijkstra's single source shortest path algorithm**.

## ALGORITHM:

**Step 1**: Initialize a `distance[]` array with infinity for all vertices except the source, which is set to `0`.  
Create a `sptSet[]` array (shortest path tree set) to keep track of vertices whose shortest distance from the source is finalized.

**Step 2**: Pick the vertex `u` with the minimum distance value from the set of vertices not yet processed.

**Step 3**: For every adjacent vertex `v` of the picked vertex `u`, if the current distance to `v` is greater than the distance to `u` plus the edge weight `(u, v)`, then update the distance of `v`.

**Step 4**: Mark the vertex `u` as processed in `sptSet`.

**Step 5**: Repeat Steps 2–4 until all vertices are processed.

**Step 6**: Print the shortest distances from the source to all other vertices.

## PYTHON PROGRAM

```
# Name: Vikram GS
# Reg No: 212222060296

import heapq

graph = {
    1: [(2, 1), (3, 4)],
    2: [(3, 2), (4, 5)],
    3: [(4, 1)],
    4: []
}

def dijkstra(start):
    pq = [(0, start)]
    dist = {node: float('inf') for node in graph}
    dist[start] = 0

    while pq:
        d, node = heapq.heappop(pq)
        for neighbor, weight in graph[node]:
            if dist[neighbor] > d + weight:
                dist[neighbor] = d + weight
                heapq.heappush(pq, (dist[neighbor], neighbor))

    return dist

print("Shortest paths:", dijkstra(1))

```

## OUTPUT
```
Shortest paths: {1: 0, 2: 1, 3: 3, 4: 4}

```

## RESULT

Shortest path from source to all vertices is calculated successfully.
