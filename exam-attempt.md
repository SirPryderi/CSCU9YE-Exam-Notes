Question 1
---------------

> (a) In the context of Artificial Intelligence, briefly describe:

> What is an agent?

In the context of artificial intelligence, an **agent** is any entity capable of perceiving through **sensors** and acting upon the environment through **actuators**. §2.1 Humans, robots, programs are all agents.

> What is an uninformed search strategy? Mention two algorithms  use this strategy.

An **uninformed search strategy** is a set of search algorithms that are given no information about the problem other than its definition. They are also known as **blind**. They can only generates new states and distinguish goal-states from non-goal-states. Two know uninformed tree search algorithms are depth-first and breadth-first algorithms. They both work by exploring the entire tree, until they find a goal state. §3.4

> (b) Consider an autonomous robot designed for planetary exploration: the Mars rover:

> Describe its design in terms of the four main components of intelligent agents.

The four main components of the design of an intelligent agents (task environment) are **Performance**, **Actuators**, **Environment**, and **Sensors** §2.3. I should mention I played too much _Kerbal Space Program_.
- Performance
    - Danger level
    - Novelty
    - Maximise sites explored
    - Maximise samples analysed
    - Maximise photographs sent
- Actuators
    - Motors
    - Retractable solar panels
    - Arm
    - Drill
    - Retractable Antenna
- Environment
    - Lander
    - Rover
    - Mars!
    - Mission Control
- Sensors
    - Cameras
    - Environmental
    - On-board science kit
    - Odometers
    - Accelerometer/Gyroscopes
    - Antennas

>    Describe its environment in terms of two main distinctions or classifications of environments.

The environment is (two of these are enough) §2.3.2:
1. **Partially-Observable** — The rover can't see the whole planet
2. **Single-Agent** — Even if there are more rovers, their encounter is very unlikely, so it can be considered single-agent. Unless there are Martians.
3. **Stochastic** — It is impossible to predict the next state
4. **Sequential** — The rover will build knowledge for each step
5. **Dynamic** — The world might change (sandstorm, day/night)
6. **Continuous** – The rover is moving in the real world, not a grid
7. **Known** – The laws of physics are known (at least to the designer, hopefully)

> (c) In the 3-puzzle problem, the board is 2x2 and there are three tiles,
numbered A, B, and C, and one blank. The objective of the game is to
produce a configuration where the tiles are in consecutive order, with the
blank tile in the bottom right. The Start and End states are given below.

> Formulate the problem as a search problem indicating the required
components. Hint: consider that the actions are to move the white
space Right, Left, Up, Down. Of course not all actions are possible
from all states.

1. Initial State
    - In([BCA_])
2. Actions
    - Move blank Right, Left, Up, Down (According to constraints)
3. Transition Model
    - Moving a blank to a direction will swap the blank tile with the adjacent
4. Goal test
    - In([ABC_]) 
5. Path cost
    - The cost is one movement per state
6. States
    - The states are all the possible combinations of the tiles 

> Draw the search tree that would result from expanding 6 nodes
(including the start) of the state-space using a Depth-First-Search
approach that avoids revisiting states. The actions should be
considered in the order (R, L, U, D). As nodes of the tree, draw the
state as the 2x2 board with the specific configuration. Label the
edges with the action executed. Also enumerate each node with
consecutive numbers indicating the sequence of expansion.

![Diagram](exam-attempt-diagram.svg)

Note that if the if the algorithm wasn't excluding duplicates, it would branch twice at each node. I added other two steps, that were enough to find a solution.

Question 2
-----------------
> (a) In the context of local search and evolutionary algorithms, briefly describe:

> What is a search space? Give an example of a search space.

The search space is the set or domain where a search algorithm will search for solutions. They can be either finite or infinite.

The diagram used above is a subset of the search space.

Another examples could be:
- A string, when searching for a character
- All possible moves a chess piece can do

> What is a neighbourhood? Give an example of a neighbourhood.

A neighbourhood is the set of states that are _nearby_ the current state, according to a given distance function. 

Taking the diagram above as an example, the neighbourhood of the initial node, are the first two nodes to be expanded, so all the nodes that are _one action_ away.

Other examples could be:
- The Hamming distance for strings
- Swap or insert for permutations (remember the rucksack?)

> (b) As the logistics manager in a supermarket, you need to coordinate the
home delivery of shopping baskets to 10 clients. Consider that you have
a single van and the 10 shopping baskets fit in it. You have the
addresses of the 10 clients. Your job is to deliver all the orders and
return to your base. Formulate this as an optimisation problem
indicating:

> How will you encode a solution to the problem and how will this be interpreted?

(This problem is suspiciously similar to the Travelling Salesman's, masked like the Vehicle Routing's.)
I would encode the solution of the problem as an array of addresses or coordinates. This will be read by the driver, so that the first address in the list will be served first, thus indicating the order in which each location should be reached.

> What will be the fitness function and how will you implement it?

The fitness function will be the total distance that the van has to travel to reach all the locations and then travel back to the supermarket.

> (c) Consider the data below for training a cleaning robot. The robot needs
to decide to which rooms to go for collecting recycled paper. Assume
that an indication of the information gain of each attribute is given by:
Role = 0.66, Floor = 0.06, Subject = 0.0, Size = 0.06

> Construct the smallest possible decision tree (in terms of the
number of attributes required) to solve this classification task given
the information you have. Label the non-terminal nodes with the
attributes, and the edges with attribute values. For each terminal
node (leaf) of the tree indicate the examples classified.

![table](exam-attempt-table.png)

![Diagram 2](exam-attempt-diagram2.svg)

> Is this the only tree you can construct of this size? Justify your
answer.

No, other trees could be built, changing the second attribute (floor) with either subject or size. But this will require additional nodes before the goal state is reached.