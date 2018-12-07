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

Question 2
-----------------

> Cyka Blyat