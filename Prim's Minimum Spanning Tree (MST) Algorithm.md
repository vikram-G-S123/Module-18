# Ex. No: 18A - Prim's Minimum Spanning Tree (MST) Algorithm

## AIM:
To write a Python program for **Prim's Minimum Spanning Tree (MST)** algorithm.

## ALGORITHM:

**Step 1**: Initialize the `key[]` array to infinity, set the first vertex's key to `0`, and create `mstSet[]` and `parent[]` arrays.

**Step 2**: Select the vertex with the smallest key value not yet included in `mstSet`.

**Step 3**: Add the selected vertex to `mstSet`.

**Step 4**: For all adjacent vertices:
- If the edge weight is smaller than their current key value, and the vertex is not in `mstSet`, then:
  - Update their key value
  - Update their parent to the current vertex

**Step 5**: Repeat Steps 2–4 until all vertices are included in the MST.

**Step 6**: Print the resulting Minimum Spanning Tree using the `parent[]` array.

## PYTHON PROGRAM

```
# Name: Vikram GS
# Reg No: 212222060296

import heapq

graph = {
    1: [(2, 1), (3, 4)],
    2: [(1, 1), (3, 2), (4, 5)],
    3: [(1, 4), (2, 2), (4, 1)],
    4: [(2, 5), (3, 1)]
}

def prim(start):
    visited = set()
    pq = [(0, start)]
    cost = 0

    while pq:
        weight, node = heapq.heappop(pq)
        if node not in visited:
            visited.add(node)
            cost += weight
            for neighbor in graph[node]:
                heapq.heappush(pq, neighbor)

    return cost

print("MST Cost:", prim(1))

```

## OUTPUT

```
MST Cost: 4

```


## RESULT

Minimum Spanning Tree is constructed successfully using Prim’s algorithm.


