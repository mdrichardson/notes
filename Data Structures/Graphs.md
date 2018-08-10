# Graphs

![Graph](https://www.geeksforgeeks.org/wp-content/uploads/undirectedgraph.png)

In the above Graph, the set of vertices `V = {0,1,2,3,4}` and the set of edges `E = {01, 12, 23, 34, 04, 14, 13}`.

* Abstract data type stemming from math's graph theory
* Consists of finite (possibly mutable) set of vertices with a set of unordered pairs of vertices (undirected graph) or a set of ordered pairs (directed graph).
  * Pairs are known as edges, arcs, or lines (undirected) or arrows, directed edges, directed arcs (directed)
* Frequently represents networks

## Adjacency Matrix

* Uses `1` or `0` to represent whether there is a edge between two vertices.
* In above graph:

![Adjacency Matrix](https://cdncontribute.geeksforgeeks.org/wp-content/uploads/adjacencymatrix.png)

* Edges can also be weighted
* Pros: Queries are O(1)
* Cons: Consumes `V^2` space (edges of matrix are `length(V)`)

## Adjacency List

![Adjacency List](https://cdncontribute.geeksforgeeks.org/wp-content/uploads/listadjacency.png)

* Array of linked lists where array is equal to `length(V)`
* Weights of edges can be stored in nodes of linked lists
* Pros: Less space O(V + E)
* Cons: Queries are O(V)