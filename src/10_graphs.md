Prim's Algorithm:
Input: Graph G(V,E) with weights


1. Initialize MST as an empty set
2. Initialize a priority queue (PQ) to store edges with their weights
3. Choose an arbitrary starting node and mark it as visited
4. Add all edges from the starting node to PQ
5. While PQ is not empty:
     a. Extract the edge (u, v) with the smallest weight
     b. If v is not visited:
           i. Add edge (u, v) to MST
          ii. Mark v as visited
         iii. Add all edges from v to PQ that connect to unvisited nodes
6. Return MST

Output: Minimum Spanning Tree (MST)


Kruskal's Algorithm:

Input: Graph G(V,E) with weights

1. Initialize MST as an empty set
2. Sort all edges by weight in ascending order
3. Create a disjoint-set data structure (Union-Find) to manage connected components
4. For each edge (u, v) in sorted order:
     a. If u and v are in different sets:
           i. Add edge (u, v) to MST
          ii. Union the sets of u and v
5. Return MST

Output: Minimum Spanning Tree (MST)