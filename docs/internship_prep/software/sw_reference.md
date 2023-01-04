# Software Reference

## Data Structures & Algorithms

### Notes

My notes on the topics listed in the Google Technical Internships Interview Preparation guide.
Most of these notes are based off my [CPSC 221](https://courses.students.ubc.ca/cs/courseschedule?pname=subjarea&tname=subj-course&dept=CPSC&course=221)
notes.

#### Merge sort vs quicksort

Comparing two popular sorting algorithms.

| Basis for comparison         | Merge sort                                    | Quicksort                                                                                                             |
| ---------------------------- | --------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- |
| Definition                   | Merges two sorted lists of equal size         | Concatenates two sorted lists with elements that are less and greater than the pivot                                  |
| Space complexity             | $O(n)$                                        | $O(1)$ (in place)                                                                                                     |
| Time complexity (worst case) | $O(n\log n)$                                  | $O(n^2)$, random pivot minimizes chance of worst case                                                                 |
| Efficiency for large $n$     | Efficient for larger arrays, consistent speed | Inefficient for larger arrays, but fast for small $n$                                                                 |
| Dependency of speed on $n$   | Consistent for any $n$                        | Faster for small $n$, slower for large $n$                                                                            |
| Preferred for                | Linked Lists                                  | Arrays, because, quicksort requires lots of random access which arrays can do in $O(1)$ since elements are contiguous |

For more, see [GeeksforGeeks Quick Sort vs Merge Sort article](https://www.geeksforgeeks.org/quick-sort-vs-merge-sort/).

#### Min/Max heaps

A min heap is a complete tree where all paths from root to leaf are non-decreasing.
Since the root node is always the minimum element, min heaps are useful for problems that require accessing or removing
the minimum element efficiently. Similarly, max heaps are used to access or remove the maximum element efficiently.

| Heap function | Definition                                                                                                        |
| ------------- | ----------------------------------------------------------------------------------------------------------------- |
| Insert        | At leftmost spot in last level and heapify up in $O(h)=O(\log n)$                                                 |
| Remove min    | Root in min; swap leftmost spot in last level with root and heapify down in $O(h)=O(\log n)$                      |
| Build         | Heapify down from root in $O(n)$                                                                                  |
| Heap sort     | Build, remove min $n$ times makes non-ascending order in $O(n\log n)$; could reverse to make non-descending order |

#### Adjacency list vs matrix

Comparing two popular graph representations.

Characteristics of these graphs:

- $n$ vertices
- $m$ edges
- no parallel edges
- no self-loops

| Basis for comparison      | Adjacency list                                     | Adjacency matrix            |
| ------------------------- | -------------------------------------------------- | --------------------------- |
| Definition                | Linked list of neighbors for each edge             | Rows and cols are the edges |
| Space complexity          | $\Theta(n+m)$                                      | $\Theta(n^2)$               |
| incidentEdges($v$)        | $\text{deg}(v)$                                    | $\Theta(n)$                 |
| areAdjacent($v$, $w$)     | $\text{min}(\text{deg}(v), \text{deg}(w))$         | $\Theta(1)$                 |
| insertVertex($o$)         | $\Theta(1)$                                        | $\Theta(n)$ amortized       |
| insertEdge($v$, $w$, $o$) | $\Theta(1)$                                        | $\Theta(1)$                 |
| removeVertex($v$)         | $\text{deg}(v)$                                    | $\Theta(n)$ amortized       |
| removeEdge($e$)           | $\Theta(1)$                                        | $\Theta(1)$                 |
| removeEdge($v$, $w$)      | $\Theta(\text{min}(\text{deg}(v), \text{deg}(w)))$ | $\Theta(1)$                 |

#### Breadth-first vs depth-first search

Comparing two popular search algorithms.

| Basis for comparision | Bread-first search                    | Depth-first search |
| --------------------- | ------------------------------------- | ------------------ |
| Edge types            | Discovery and cross                   | Discovery and back |
| Implemented using     | Queue                                 | Stack              |
| Used for              | Shortest path from root to any vertex | Topological sort   |

Common features:

- Discovery edges make a spanning tree
- Can be used to detect cycles and count components

#### Miscellaneous algorithms

- Kruskal: find MST using min heap of edge weights in $O(m\log n)$
- Prim: find MST of undirected graph
    - Checks `w(u, v)` for being less than `D(v)` in RELAX.
- Dijkstra: finds shortest path of directed graph with nonnegative edge weights
    - Checks `D(u) + w(u, v)` for being less `D(v)` in RELAX.

#### NP-complete

Definitions:

- P: all decision problems that can be solved in polynomial time
- NP: all decision problems for which the instances where the answer is "yes" have proofs that can be verified in
  [nondeterministic] polynomial time
    - Has an efficient verifier, but **may not** have an efficient solver
- NP-complete: all problems in NP which can be reduced to any other NP problem in polynomial time
    - Has an efficient verifier, but **does not** have an efficient solver
- NP-hard: all problems that are reducible to a known NP-complete problem (like boolean satisfiability, SAT)
    - Any NP-complete problem can be reduced to any NP-hard problem in polynomial time ->
      all NP-complete problems can be reduced to any NP-hard problem in polynomial time ->
      if there is a solution to one NP-hard problem in polynomial time, there is a solution all NP problems in
      polynomial time

For more details, see [this StackOverflow answer](https://stackoverflow.com/a/1857342).

Proving a problem $P$ is NP-complete:

1. Prove that $P$ is in NP
    - Show what kind of proof for instances where the answer is "yes" can be checked in polynomial time
2. Prove that $P$ can be reduced to a NP problem in polynomial time
    - Give a polynomial time algorithm that transforms instances of a known NP-complete problem into instances of $P$
      with the same answer

Popular problems:

- Traveling salesman: Given a list of cities and the distances between each pair of cities,
  what is the shortest possible route that visits each city exactly once and returns to the origin city?
- Knapsack: Given a set of items, each with a weight and a value,
  determine the number of each item to include in a collection so that the total weight is less than or equal to
  a given limit and the total value is as large as possible

## Concepts

Be able to explain concepts in your own words and give examples of you applying them.

### Agile software development

- Iterative software development
    - Purpose: rapid delivery of high quality software
- Documenting and resolving issues
- Kanban vs Scrum

![Agile vs Waterfall Development](../../assets/agile_vs_waterfall.png)

### DevOps

- CI/CD
- Docker, Kubernetes

### Testing

- Test-driven development
- Black vs white box testing
- How to develop a test plan
- Types of tests: unit, integration, functional, regression
- Fault injection
- Corner cases
- Root-cause analysis
- Parts of a good bug report

--8<-- "includes/abbreviations.md"
