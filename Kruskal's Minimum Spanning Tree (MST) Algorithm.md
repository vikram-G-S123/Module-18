# Ex. No: 18B - Kruskal's Minimum Spanning Tree (MST) Algorithm

## AIM:
To write a Python program for **Kruskal's algorithm** to find the Minimum Spanning Tree (MST) of a given connected, undirected, and weighted graph.

## ALGORITHM:

**Step 1**: Sort all the edges of the graph in non-decreasing order of their weights.

**Step 2**: Initialize the `parent[]` and `rank[]` arrays for each vertex to keep track of the disjoint sets.

**Step 3**: Iterate through the sorted edges and pick the smallest edge. Check whether including this edge will form a cycle using the union-find method:
- If the vertices of the edge belong to different sets, include it in the MST.
- Perform a union of these two sets.

**Step 4**: Repeat Step 3 until the MST contains exactly `V-1` edges.

**Step 5**: Print the edges included in the MST and the total minimum cost.

## PYTHON PROGRAM

```
# Name: Vikram GS
# Reg No: 212222060296

edges = [
    (1, 2, 1),
    (2, 3, 2),
    (1, 3, 4),
    (3, 4, 1),
    (2, 4, 5)
]

parent = {}

def find(x):
    if parent[x] == x:
        return x
    return find(parent[x])

def union(x, y):
    parent[find(x)] = find(y)

nodes = {1, 2, 3, 4}
for n in nodes:
    parent[n] = n

edges.sort(key=lambda x: x[2])

mst_cost = 0

for u, v, w in edges:
    if find(u) != find(v):
        union(u, v)
        mst_cost += w

print("MST Cost:", mst_cost)

```

## OUTPUT
`````
MST Cost: 4

`````

## RESULT

Minimum Spanning Tree is constructed successfully using Kruskal’s algorithm.

