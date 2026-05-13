# Development Log – The Torchbearer

**Student Name:** __Beigehon Talebzadeh_________________________
**Student ID:** _________824866530__________________

> Instructions: Write at least four dated entries. Required entry types are marked below.
> Two to five sentences per entry is sufficient. Write entries as you go, not all in one
> sitting. Graders check that entries reflect genuine work across multiple sessions.
> Delete all blockquotes before submitting.


## Entry 1 – [May 11, 2026]: Initial Plan

> Required. Write this before writing any code. Describe your plan: what you will
> implement first, what parts you expect to be difficult, and how you plan to test.

_The input is a python dictionary where the keys are strings representing each node, S for source, T for terminal, 
and the rest. The value of each key is a list of nodes that are adjacent to the key node, and the associated costs to traverse the edge. This is a list of tuple pairs, (string, int). My first step will be to make a Djikstras algorithm for each pair of nodes in this data structure. The input will be the same as the problem input.  The output will be a python dictionary where the keys are pairs ofstrings representing 
each pair of nodes, the values will be a pair with the cost of the shortest path, and a list of strings representing that path in total, this would be an n^2 size table, where n is the number of nodes. The output is a tuple: (cost, order) cost will be an int, order will be a list of strings, each string  representing a node. After making the djikstras table, I will run BFS on the graph to find the shortest path with all nodes._



---

## Entry 2 – [May 11, 2026]: [Dijkstra's difficulty]

> Required. At least one entry must describe a bug, wrong assumption, or design change
> you encountered. Describe what went wrong and how you resolved it.

_When implementing the Dijkstra's algorithm, I followed the pseudocode from the wikipedia entry that used a priority queue. I imported Python's heapq module. Unfortunately, this module does not have a built in way to nicely decrease a node's priority. To solve this, I had ot implement this functionality manually, by searching through the nodes, inserting a new node with updated priority, and popping the old node. This takes linear time, but I suspect that for such a complex problem, it won't be a bottleneck._

---

## Entry 3 – [May 13, 2026]: [We fixed a couple of bugs in the code.]

_We fixed a couple of bugs in the code. We implemented the solve() method. We ran tests (all passing!).
We went back and implemented a basic version of explore() with no heuristics. Then we completely re-implemented
find_optimal_route to use explore() instead of manually iterating through all permutations. Then we implemented
a simple heuristic in explore() to prune unnecessary paths._

---

## Entry 4 – [May 13, 2026]: Post-Implementation Reflection

> Required. Written after your implementation is complete. Describe what you would
> change or improve given more time.

_Think of a better heuristic that could prune more paths while still guaranteeing correctness. Add more tests for larger and
more complex graphs._

---

## Final Entry – [May 13, 2026]: Time Estimate

> Required. Estimate minutes spent per part. Honesty is expected; accuracy is not graded.

| Part | Estimated Hours |
|---|---|
| Part 1: Problem Analysis | 1 hour|
| Part 2: Precomputation Design | 2 hours |
| Part 3: Algorithm Correctness | 1.5 hours |
| Part 4: Search Design | 1 hour |
| Part 5: State and Search Space | 10 hours |
| Part 6: Pruning | 10 hours |
| Part 7: Implementation | 2 days |
| README and DEVLOG writing | 2 days |
| **Total** | 2 days, spent all day working on it.|
