# Development Log – The Torchbearer

**Student Name:** ___________________________
**Student ID:** ___________________________

> Instructions: Write at least four dated entries. Required entry types are marked below.
> Two to five sentences per entry is sufficient. Write entries as you go, not all in one
> sitting. Graders check that entries reflect genuine work across multiple sessions.
> Delete all blockquotes before submitting.

---

## Entry 1 – [Date]: Initial Plan

> Required. Write this before writing any code. Describe your plan: what you will
> implement first, what parts you expect to be difficult, and how you plan to test.

_The input is a python dictionary where the keys are strings representing each node, S for source, T for terminal, 
and the rest. The value of each key is a list of nodes that are adjacent to the key node, and the associated costs to traverse the edge. This is a list of tuple pairs, (string, int). My first step will be to make a Djikstras algorithm for each pair of nodes in this data structure. The input will be the same as the problem input.  The output will be a python dictionary where the keys are pairs ofstrings representing 
each pair of nodes, the values will be a pair with the cost of the shortest path, and a list of strings representing that path in total, this would be an n^2 size table, where n is the number of nodes. The output is a tuple: (cost, order) cost will be an int, order will be a list of strings, each string  representing a node. After making the djikstras table, I will run BFS on the graph to find the shortest path with all nodes._



---

## Entry 2 – [Date]: [Short description]

> Required. At least one entry must describe a bug, wrong assumption, or design change
> you encountered. Describe what went wrong and how you resolved it.

_Your entry here._

---

## Entry 3 – [Date]: [Short description]

_Your entry here._

---

## Entry 4 – [Date]: Post-Implementation Reflection

> Required. Written after your implementation is complete. Describe what you would
> change or improve given more time.

_Your entry here._

---

## Final Entry – [Date]: Time Estimate

> Required. Estimate minutes spent per part. Honesty is expected; accuracy is not graded.

| Part | Estimated Hours |
|---|---|
| Part 1: Problem Analysis | |
| Part 2: Precomputation Design | |
| Part 3: Algorithm Correctness | |
| Part 4: Search Design | |
| Part 5: State and Search Space | |
| Part 6: Pruning | |
| Part 7: Implementation | |
| README and DEVLOG writing | |
| **Total** | |
