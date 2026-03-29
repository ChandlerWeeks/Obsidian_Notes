# Intro to greedy algorithms 
**Greedy algorithms pursues local optima at each step with the hopes of finding a global optimum at its conclusion.**

We use them all the time, in real life too. An example is loading a trunk, the biggest items go first. It also works for the fractional knapsack problem. 

They're not as applicable to dynamic problems; a dynamic program is one that receives data in real time; for example, don't just schedule the program that requires the most resources. 

The book material is way too long winded; just skim through it. Focus on section 16.3, Huffman Coding. (429-430). Particularly the tables. 

We can encode letters a-f as 

a   b   c   d   e   f
000 001 010 011 100 101

we can reduce the number of bits by coding the variables used more with less bits

a   b   c  d  e  f
0 101 100 111 1101 1100 

*This works when a is more common, but e and f are used least commonly*

Look at the trees on p*430* to see the trees used to help encode. 

To construct the trees, look at *p432*. We just combine parts of the code, that produce the lowest value. Know how to do this, using Huffman trees. The more skewed the distributions, the more skewed the Huffman tree. 

# Simple Graph Algorithms 

Common representations of Graphs include. Kaplidev time
1 - 2
1- 3 
2 - 3
2- 4

- adjacency matrix
	- Contains nxn matrix, where each row and column (only upper triangle matters). 
	- fill 1 where there is a edge, and 0 when there isn't an edge between vertices. 
	- Great because they're directly accessed, but require more space. Most frequent representation. 

|     | 1   | 2   | 3   | 4   |
| --- | --- | --- | --- | --- |
| 1   | 0   | 1   | 1   | 0   |
| 2   | 1   | 0   | 1   | 1   |
| 3   | 1   | 1   | 0   | 0   |
| 4   | 0   | 1   | 0   | 0   |

- adjacency list
	- Map which values are connected
		- 1 -> <2, 3>
		- 2 -> <1,3,4>
		- 3-> <1, 2>
		- 4-> <2>
	- Primarily used to save space, but does not have direct access. 
	- Very useful for dense (many edges and vertices) graphs
- incidence matrix 
	- Use nxm table, where n is the number of vertices, and m is the number of edges.
	- Useful for sparse matrixes (useful for avoiding links)
	- REVIEW THESE

| 1   | 1   | 1   | 0   | 0   | 0   |
| --- | --- | --- | --- | --- | --- |
| 2   | 0   | 1   | 1   | 0   | 1   |
| 3   | 1   | 0   | 0   | 1   | 1   |
| 4   | 0   | 0   | 1   | 1   | 0   |
The discrete math center at rutgers (NSF) -> lost funding :(fuck ice and donald trump). Developed a way of sharing graphs, just store each vertex and edge. 

Common search techniques 
DFS - check deepest path first
BFS  - check nearest neighbors first

Topological Sorting
- Input: DAG 
- Output: vertex list satisfying $v_i -> v_j => v_i$. preceeds $v_j$.
- Straightforward use of DFS. See description in text. 

# Minimum Spanning Tree
Finite, simple, undirected, edge weighted graph. 
G = <V, E>, with |V| = n (graph of order n). 

Kruskal's Method
- Start with a forest of n subtrees (all isolated vertices) 
- Sort edges by weight
- iteratively add a smallest-weighted edge as long as it creates no cycle
- O(EV), but book shows a way to get it to O(ElogV)
- NOT GOING TO HOLD YOU ACOUNTABLE FOR THE TIME COMPLEXITY AT ALL. 

Prim's Method
- Start with as ingle tree (just a isolated vertex)
- Iteratively add a new leaf using a smallest-weighted edge, as long as it creates no cycle
- Also O(EV), but feasible to get to O(E+VLogV). 


Next time: Network Flow