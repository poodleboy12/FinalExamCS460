# The Torchbearer

**Student Name:** ___________________________
**Student ID:** ___________________________
**Course:** CS 460 – Algorithms | Spring 2026

> This README is your project documentation. Write it the way a developer would document
> their design decisions , bullet points, brief justifications, and concrete examples where
> required. You are not writing an essay. You are explaining what you built and why you built
> it that way. Delete all blockquotes like this one before submitting.

---

## Part 1: Problem Analysis

> Document why this problem is not just a shortest-path problem. Three bullet points, one
> per question. Each bullet should be 1-2 sentences max.

- **Why a single shortest-path run from S is not enough:**
  _ The djisktra algorithm skips nodes so it wouldn't work in this situation because this problem needs to go through all nodes.
  

- **What decision remains after all inter-location costs are known:**
  _The order to traverse nodes in.

- **Why this requires a search over orders (one sentence):**
  _Once all the shortest paths are suited then we order the shortest order must be computed._

---

## Part 2: Precomputation Design

### Part 2a: Source Selection

> List the source node types as a bullet list. For each, one-line reason.

| Source Node Type | Why it is a source |
|---------------|-------------------|
| Actual source | _Because it is the source_ |
| _Internal nodes_ | _They must eventually be reached and used as a source to continue_ |

### Part 2b: Distance Storage

> Fill in the table. No prose required.

| Property | Your answer |
|---|---|
| Data structure name | Python Dictionary (Hashmap) |
| What the keys represent | Nodes |
| What the values represent | distances to other nodes |
| Lookup time complexity | O(1) |
| Why O(1) lookup is possible | Because lookup requires computing a hashcode and array access, which are also O(1)|

### Part 2c: Precomputation Complexity

> State the total complexity and show the arithmetic. Two to three lines max.

- **Number of Dijkstra runs:** _n, where n is the number of nodes_
- **Cost per run:** _O(n^{2} logn)_
- **Total complexity:** _O(n^{3} logn)_
- **Justification (one line):** _Djikstras runtime on an adjacency list is O((E+V)logV), E is O(V^2), running Dijkstra's
for each V gives the above complexity_

---

## Part 3: Algorithm Correctness

> Document your understanding of why Dijkstra produces correct distances.
> Bullet points and short sentences throughout. No paragraphs.

### Part 3a: What the Invariant Means

> Two bullets: one for finalized nodes, one for non-finalized nodes.
> Do not copy the invariant text from the spec.

- **For nodes already finalized (in S):**
  _We know the nodes have finished finding their tiniest distance from the source. This algorithm has shown us earlier that there is no cheaper path for them to show up in the future._

- **For nodes not yet finalized (not in S):**
  _The nodes have found their smallest distance from the source so far by using finalized nodes we have so far. We could possibly make the distances better in the future._

### Part 3b: Why Each Phase Holds

> One to two bullets per phase. Maintenance must mention nonnegative edge weights.

- **Initialization : why the invariant holds before iteration 1:**
  _Shortest path from source to source 0 and shortest undiscovered path are infinite._

- **Maintenance : why finalizing the min-dist node is always correct:**
  _When a shorter non-negative path is found, the distance map gets updated._

- **Termination : what the invariant guarantees when the algorithm ends:**
  _All nodes have been explored and compared against the shortest path._

### Part 3c: Why This Matters for the Route Planner

> One sentence connecting correct distances to correct routing decisions.

_At each node, the shortest path can be taken so knowing the correct distance will get you the correct decision._

---

## Part 4: Search Design

### Why Greedy Fails

> State the failure mode. Then give a concrete counter-example using specific node names
> or costs (you may use the illustration example from the spec). Three to five bullets.

- **The failure mode:** _Does not give shortest path._
- **Counter-example setup:** 
_**Entrance:** S | **Relic chambers:** B, C, D | **Exit:** T

| From \ To | B   | C   | D   | T   |
|-----------|-----|-----|-----|-----|
| S         | 1   | 2   | 2   | --  |
| B         | --  | 100 | 10  | 1   |
| C         | 1   | --  | 1 | 1   |
| D         | 1   | 1   | --  | 100 |
_
- **What greedy picks:** _S->B->D->C->T Cost: 1+10+1+1=13._
- **What optimal picks:** _S->C->D->B->T Cost: 2+1+1+1=5._
- **Why greedy loses:** _It picks the local shortest path,
- and assumes that there is not a shorter path using that node._

### What the Algorithm Must Explore

> One bullet. Must use the word "order."

- _The algorithm needs to find the order to explore all the nodes in the shortest way._

---

## Part 5: State and Search Space

### Part 5a: State Representation

> Document the three components of your search state as a table.
> Variable names here must match exactly what you use in torchbearer.py.

| Component | Variable name in code | Data type | Description |
|---|---|---|---|
| Current location |  current_loc    | String | The node to be the source of the current search state |
| Relics already collected | relics_collected | set | Visited nodes of the current search state  |
| Fuel cost so far | fuel_cost | int  |  the cost of the current search state |

### Part 5b: Data Structure for Visited Relics

> Fill in the table.

| Property | Your answer |
|---|---|
| Data structure chosen | set |
| Operation: check if relic already collected | Time complexity: O(1) |
| Operation: mark a relic as collected | Time complexity: O(1) |
| Operation: unmark a relic (backtrack) | Time complexity: O(1) |
| Why this structure fits | For speed, a set is advantageous over a list. The final answer, requiring order, would be a list. |

### Part 5c: Worst-Case Search Space

> Two bullets.

- **Worst-case number of orders considered:** _O(k!)._
- **Why:** _All possible orders must be searched. I haven't seen any optimizations yet._

---

## Part 6: Pruning

### Part 6a: Best-So-Far Tracking

> Three bullets.

- **What is tracked:** _Your answer here._
- **When it is used:** _Your answer here._
- **What it allows the algorithm to skip:** _Your answer here._

### Part 6b: Lower Bound Estimation

> Three bullets.

- **What information is available at the current state:** _Your answer here._
- **What the lower bound accounts for:** _Your answer here._
- **Why it never overestimates:** _Your answer here._

### Part 6c: Pruning Correctness
> One to two bullets. Explain why pruning is safe.

- _Your answer here._

---

## References

> Bullet list. If none beyond lecture notes, write that.
#shortest path from source to terminal visiting all nodes google search 
#shortest path visiting all nodes leetcode and stackoverflow. wikipedia travels salesman problem
- _general problem research (the whole problem):
https://en.wikipedia.org/wiki/Branch_and_bound 
Google search AI: "shortest path directed weighted graph visiting all nodes with source and target
https://en.wikipedia.org/wiki/Travelling_salesman_problem
used in parts 2 and 3: https://en.wikipedia.org/wiki/Dijkstra%27s_algorithm 
https://stackoverflow.com/questions/46636656/python-heapq-replace-priority
"_
