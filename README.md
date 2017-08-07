# Algorithms

Karger’s algorithm for Minimum Cut
Given an undirected and unweighted graph, find the smallest cut (smallest number of edges that disconnects the graph into two components).
The input graph may have parallel edges.

A Simple Solution use Max-Flow based s-t cut algorithm to find minimum cut. Consider every pair of vertices as source ‘s’ and sink ‘t’, and call minimum s-t cut algorithm to find the s-t cut. Return minimum of all s-t cuts. Best possible time complexity of this algorithm is O(V5) for a graph. [How? there are total possible V2 pairs and s-t cut algorithm for one pair takes O(V*E) time and E = O(V2)].

Below is simple Karger’s Algorithm for this purpose. Below Karger’s algorithm can be implemented in O(E) = O(V2) time.

1)  Initialize contracted graph CG as copy of original graph
2)  While there are more than 2 vertices.
      a) Pick a random edge (u, v) in the contracted graph.
      b) Merge (or contract) u and v into a single vertex (update 
         the contracted graph).
      c) Remove self-loops
3) Return cut represented by two vertices.


Karger’s algorithm is a Monte Carlo algorithm and cut produced by it may not be minimum. For example, the following diagram shows that a different order of picking random edges produces a min-cut of size 3.

Karger1
