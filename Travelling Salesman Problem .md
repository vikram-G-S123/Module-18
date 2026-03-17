# Ex. No: 18D - Travelling Salesman Problem (TSP)

## AIM:
To write a Python program to find the shortest possible route that visits every city exactly once and returns to the starting point using the **Travelling Salesman Problem (TSP)** approach.

## ALGORITHM:

**Step 1**: Start the program.

**Step 2**: Input the number of cities and the distance matrix.

**Step 3**: Set the starting city (e.g., city `0`).

**Step 4**: Generate all possible permutations of the remaining cities.

**Step 5**: For each permutation:
- Calculate the total cost of traveling through the permutation starting and ending at city `0`.
- Keep track of the **minimum cost** and the corresponding route.

**Step 6**: Return the **route** and the **minimum cost**.

**Step 7**: End the program.

## PYTHON PROGRAM

```
# Name: Vikram GS
# Reg No: 212222060296

from itertools import permutations

graph = [
    [0, 10, 15],
    [10, 0, 20],
    [15, 20, 0]
]

n = len(graph)
cities = list(range(n))

min_path = float('inf')

for perm in permutations(cities[1:]):
    cost = 0
    k = 0
    for j in perm:
        cost += graph[k][j]
        k = j
    cost += graph[k][0]

    min_path = min(min_path, cost)

print("Minimum travelling cost:", min_path)

```

## OUTPUT
```
Minimum travelling cost: 45

```

##RESULT

Optimal path for Travelling Salesman Problem is found successfully.
