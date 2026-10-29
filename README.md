# EXPERIMENT 2: IMPLEMENT DEPTH FIRST SEARCH TRAVERSAL OF A GRAPH

**Name:** Sanjay A  
**Register Number:** 212225040367

## AIM
To implement Depth First Search (DFS) traversal of a graph using Python 3.

## THEORY
Depth First Search (DFS) is a graph traversal algorithm used to visit all vertices of a graph. It starts from a selected vertex and explores as far as possible along each branch before backtracking. DFS can be implemented using recursion or a stack. A visited array or set is used to avoid visiting the same vertex more than once, especially when the graph contains cycles.

## ALGORITHM
1. Create a graph using an adjacency list.
2. Read the number of vertices and edges.
3. Read the edges and add them to the graph.
4. Select vertex `A` as the starting vertex.
5. Mark the starting vertex as visited and add it to the traversal path.
6. Visit each unvisited neighbouring vertex recursively.
7. Continue until all reachable vertices have been visited.
8. Display the DFS traversal path.

## PROGRAM

```python
from collections import defaultdict

def dfs(graph, start, visited, path):
    visited[start] = True
    path.append(start)

    for neighbour in graph[start]:
        if not visited[neighbour]:
            dfs(graph, neighbour, visited, path)

    return path

graph = defaultdict(list)

n, e = map(int, input().split())

for i in range(e):
    u, v = input().split()
    graph[u].append(v)
    graph[v].append(u)

visited = defaultdict(bool)
path = []

traversedpath = dfs(graph, 'A', visited, path)
print(traversedpath)
```

## SAMPLE INPUT

```text
8 9
A B
A C
B E
C D
B D
C G
D F
G F
F H
```

## SAMPLE OUTPUT

```text
['A', 'B', 'E', 'D', 'C', 'G', 'F', 'H']
```

## OUTPUT SCREENSHOT

<img width="575" height="243" alt="Screenshot 2026-10-29 102306" src="https://github.com/user-attachments/assets/daae769a-8966-4df5-8634-082e43137538" />


## RESULT

Thus, Depth First Search traversal of a graph was successfully implemented using Python 3, and the traversal path was displayed.
