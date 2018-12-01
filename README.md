# Artificial Intelligence

## Table of Contents
* [Artificial Intelligence](#artificial-intelligence)
  * [What is Artificial Intelligence?](#what-is-artificial-intelligence)
    * [Rational Agent](#rational-agent)
  * [Search](#search)
    * [Optimisation problems](#optimisation-problems)
      * [Heuristic Optimisation](#heuristic-optimisation)
        * [NP-Hardness](#np-hardness)
        * [Constructive Heuristics](#constructive-heuristics)
        * [Local Search Heuristics](#local-search-heuristics)
    * [Tree Search](#tree-search)
      * [Comparing Strategies](#comparing-strategies)
      * [Uninformed Search Strategies](#uninformed-search-strategies)
        * [Breadth-first algorithms](#breadth-first-algorithms)
        * [Depth-first algorithms](#depth-first-algorithms)
      * [Informed Search](#informed-search)
        * [Best-first Search](#best-first-search)
          * [Greedy search](#greedy-search)
          * [A*](#a)
  * [Machine Learning](#machine-learning)
  * [Advanced Applications](#advanced-applications)
    * [Natural Language Processing](#natural-language-processing)
    * [Robotics](#robotics)
  * [Conclusions](#conclusions)

## What is Artificial Intelligence?

There are four historical definitions of artificial intelligence:

- **Thinking Humanly**
     - Studying how humans think
     - Emulating the functioning of human mind
- **Acting Humanly**
     - Having a machine that seem to think like a human mind
     - Turing test
  - **Thinking Rationally**
    - Notation and rules of logical thought
  - **Acting Rationally**
    - Having an **agent** that achieves the best outcome

The last definition is the one that is one that is currently recognised.

A **problem** has a **goal** and a set of allowed **actions** to achieve it
A **solution** is a sequence of allowed actions that achieves a problem's goal.

### Rational Agent
A **rational agent** is something that, for a specific problem, **acts rationally**, i.e. does the action that **maximise goal achievement**. This does not necessarily include rational thinking.

## Search

Search in computer science can be intended as follow:

1. Search for stored data
2. Search for web documents
3. Search for path or routes
4. Search for solutions

### Optimisation problems
In mathematics and computer science an **optimisation problem** is the problem of finding the **best solution** from all feasible solutions. The best solution is defined by the minimisation of time, cost and risk and/or the maximisation of profit, quality and efficiency.

Optimisation problems can be, depending on their variables, **continuous** and **discrete**.

#### Heuristic Optimisation
A heuristic is a technique designed for solving a problem quickly (**rule of thumb**), where the traditional approach would be too slow, or wouldn't find a complete solution.

Problems known as **NP-hard** are usually better tackled with heuristics.

##### NP-Hardness
The NP-hardness (non-deterministic polynomial time hardness) is a property of an optimisation problem. A problem is categorised as NP-hard where there is no algorithm that is capable of solving it in polynomial time (`O(n^k)`) on a _non-deterministic Turing machine_.

![NP-Hardness](https://upload.wikimedia.org/wikipedia/commons/thumb/a/a0/P_np_np-complete_np-hard.svg/800px-P_np_np-complete_np-hard.svg.png)

- `P` ─ set of problems that can be solved in polynomial time by a Turing machine
- `NP` ─ set of problems that can be solved in polynomial time by a nondeterministic Turing machine
- `NP-hard` ─ set of problems that are at least as hard as the hardest problem in NP 

```
____________________________________________________________
| Problem Type | Verifiable in P time | Solvable in P time | Increasing Difficulty
___________________________________________________________|           |
| P            |        Yes           |        Yes         |           |
| NP           |        Yes           |     Yes or No *    |           |
| NP-Complete  |        Yes           |      Unknown       |           |
| NP-Hard      |     Yes or No **     |      Unknown ***   |           |
____________________________________________________________           V
```
\* An NP problem that is also P is solvable in P time.
** An NP-Hard problem that is also NP-Complete is verifiable in P time.
*** NP-Complete problems (all of which form a subset of NP-hard) might be. The rest of NP hard is not.


##### Constructive Heuristics
A **constructive heuristic** is an algorithm that starts with an empty solution, and extends the current solution until a complete solution is found.

##### Local Search Heuristics
A **local search** algorithm starts from a complete solution, and tries to improve the current solution by via  local changes.

### Tree Search
A search problem can be mapped as as a tree of **state spaces** joined by actions. The tree root is the initial state. This allows the traversal of the tree using a search algorithm, that finds a solution to the problem. Hence, a **solution** is a sequence of actions (a plan) that reaches the **goal state**.

A **state space** contains:
- **The world state** ─ set of every detail of the problem
- **Search state** ─ set of details needed for planning

A search problem can be formulated as follows:
- (states)(???)
- Initial state
- Actions
- Transition Model
- Goal test
- Path cost

An example of this is the shortest path problem between two nodes in a weighted graph.

#### Comparing Strategies
Search algorithm can be compared based on the followings:
- completeness: does it always find a solution if one exists?
- time complexity: number of nodes generated
- space complexity: maximum number of nodes in memory
- optimality: does it always find a least-cost solution?

#### Uninformed Search Strategies
**Uniformed search strategies** also called **blind search strategies** use only the information available in the problem definition.

Uniformed search algorithms can be either breadth-first or depth-first.

##### Breadth-first algorithms
Aims to expand the shallowest unexpanded node.

![breadth-first](http://how2examples.com/artificial-intelligence/images/Breadth-First-Search.gif)

- Complete: Yes (if b is finite)
- Time:  O(b^(d+1))
- Space: O(b^(d+1)) (keeps every node in memory)
- Optimal: Yes (ONLY if cost = 1 per step)

##### Depth-first algorithms
Aims to expand the deepest unexpanded node.

![depth-first](http://how2examples.com/artificial-intelligence/images/Depth-First-Search.gif)

- Complete:
    - YES in finite spaces
    - NO in infinite-depth spaces, loops
        - Can be modified to avoid repeated states along path
- Time:  O(b^m)
- Space: O(b·m) (linear space!)
- Optimal: No

It is possible to impose a maximum depth (**depth-limited search**) to the algorithm. This would make the algorithm **complete**, but still **not optimal**.

Also, it is possible to gradually increase the maximum depth, combining the benefits of DFS and BFS.

#### Informed Search
Informed search algorithms use a problem-specific **evaluation function** that describes the desirability of a given search state.

##### Best-first Search
Best-first search algorithms expand the mode desirable node first.

###### Greedy search
Expands the node closest to the goal.

![GreedySearch](http://how2examples.com/artificial-intelligence/images/Greedy-Search.gif)

- Complete: No
- Time:  O(b ^ d )
- Space: O(b ^ d )
- Optimal: Yes (ONLY if cost = 1 per step)

###### A*
Expands the node on the least-cost solution path.

![a*](http://how2examples.com/artificial-intelligence/images/A-Star-Search.gif)

The evaluation function (`f(n)`) takes in account of:
- `g(n)`: path cost from the start node to node _n_.
- `h(n)`: the cost to get from the node to the goal.

`f(n)` = `g(n) + h(n)`

So it makes sense to expand the node with lowest `f(n)`.

- Complete: Yes
- Time:  O(b ^ d )
- Space: O(b ^ d )
- Optimal: Yes (ONLY if cost = 1 per step)

## Machine Learning

## Advanced Applications

### Natural Language Processing

### Robotics

## Conclusions
