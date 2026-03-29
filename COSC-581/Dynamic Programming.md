Data Structures Review - See Text
Good Examples to Review
- Stacks vs Queues
- Heaps vs Binary Search Trees
- Hash Table Collisions and Linear Probing

**Dynamic Programming**: an old term, meaning to solve by tabulation. 

It is a Multi-Stage Decision Process
- n is the number of stages
- d decision choices per stage
- Complexity of $O(d^n)$ 

Classic examples
- Job sequences
- Tape Utilization

The Knapsack Problem
- Given a list of items and a knapsack capacity
- Each item has a value and a size
- pack to maximize value while respecting capacity
- A simple greedy algorithm suffices 

Consider the 0/1 version of this problem. 
- Fractional items are not permitted. 
- Algorithms 
	- Which goes first, then second, etc ... O(n!)
	- Item 1 yes/no, item 2 yes/no, etc ... ($2^n$)
		- view each item as a stage
		- each stage has but two options
		- its a multistage decision process

Issues
- How do we set up the DP formulation
- How do we keep up of partial solutions
- How do we ensure all possibilities are considered?
- How do we keep from looping?
- How to do all this efficiently?

Answer
- Keep a DP table for each stage
- Avoid consideration of non-optimal sub-solutions
- Avoid re-computation of optimal sub-solutions
- trade space for time

Variables
- at stage i
	- $s_i$ = state variable
	- $d_i$ = decision variable
	- $r_i$ = return variable
- Where a * superscript denotes optimization

Who is Richard Bellman
What is the principle of Optimality

Richard Bellman and the principle of optimality: An optimum decision sequence must have the property that, for stage i, no matter how we've chose s_i and d_i, the subsequence decisions d_i+1, d_i+2, ... d_n will be best possible s_i and d_i. 

IF YOU MAKE THE RIGHT DECISION OVERALL, YOU WILL MAKE THE RIGHT DECISION IN THE PREVIOUS STAGE. 