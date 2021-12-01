# TDT4138 - IntroAI

1. [_Introduction_](#c1)
2. [_Intelligent Agents_](#c2)
3. [_Problem Solving as Search_](#c3)
4. [_Informed search and Local search_](#c4)
5. [_Adversarial Search_](#c5)
6. [_Constraint Satisfaction Problems_](#c6)
7. [_Logical Agents_](#c7)
8. [_First Order Logic_](#c8)
9. [_Inference in First Order Logic_](#c9)
10. [_Planning_](#c10)
11. [_Multiagent-Systems and Game Theory_](#c11)
12. [_Knowledge Representation_](#c12)
13. [_Artificial Intelligence and Ethics_](#c13)

# Lecture 1 - Introduction <a name="c1"></a>

## What is AI?

There are no crisp definitions. Here is one from **John McCarthy**, (Father of the phrase _Artificial Intelligence_)
see http://www.formal.stanford.edu/jmc/whatisai/

**Question:** What is artificial intelligence?
**Answer:** It is the science and engineering of making intelligent machines, especially intelligent computer programs. It is related to the similar task of using computers to understand human intelligence, but AI does not have to confine itself to methods that are biologically observable.

**Question:** Yes, but what is intelligence?
**Answer:** Intelligence is the computational part of the ability to achieve goals in the world. Varying kinds and degrees of intelligence occur in people, many animals and some machines.

"It is the science and engineering of making intelligent machines, especially inteliigent computer programs" - **John McCarthy**

"AI is the science of making machines to do things that would require intelligence if done by men." - **Marvin Minsky**

"The study of mental faculties through the use of computational models" - **Eugen Charniak**

In short: There is no formal definition covering all aspects of intelligence.

## Two aspects of AI

**Science**
The science of understanding intelligent entities, developing theories which attempt to explain and predict the nature of such entities
Discover ideas about knowledge that help explain various sorts of intelligence
Model functions of the human brain

**Engineering**
Solving real-world problems by employing ideas of how to represent and use knowledge
Engineering of intelligent entities
Produce intelligent behaviour by any means

## Can machines be Intelligent?

- _Symbolic system hypothesis_ (Newell and Simon)
  - Intelligence is substrate neutral
  - A _physical symbol system_ has necessary and sufficient means for general intelligent action.
- Biological substrate only (John Searle, philosopher)
  - Intelligence is substrate dependent
  - The material humans are made of is fundamental for our intelligence.
  - Thinking is possible only in special machines - living ones made of proteins.
- Some researchers belive that _sub-symbolic_ processing (signal processing) may be needed to replicate intelligence.

## AI prehistory - grounding disciplines

Computer Science is the main discipline underlying AI.
Can we thing which other disciplines AI is grounded on?
![](img/l1/figure1.png)

## AI prehistory

- **Philosophy:** logic, methods of reasoning, mind as physical system, foundations of learning, language, rationality
- **Mathematics:** logic, formal representation, algorithms, computation, probability theory
- **Statistics:** modeling uncertainty, learning from data
- **Psychology:** phenomena of perception and motor control, cognitive psychology
- **Economics:** formal theory of rational decisions, utility
- **Linguistics:** knowledge representation, grammar, syntax, semantics
- **Neuroscience:** neurons as information processing units, synapse as learning mechanism
- **Control theory:** homeostatic systems, stability, simple optimal agent designs, maximize objective function
- **Computer science:** engineering, hardware, computational complexity theory

## Birth of AI field

A Summer Research Project in the Dartmouth College, in 1956 was the birth of the AI research field.
![](img/l1/figure2.png)
McCarthy: "...to proceed on the basis of the conjecture that every aspect of learning or any other feature of intelligence can in principle be so precisely described that a machine can be made to simulate it."

## Brief history of AI

- **1943**: McCulloch & Pitts: Boolean circuit model of brain
- **1950**: Turing's "Computing Machinery and Intelligence"
- **1952-69**: Early AI programs, including Samuel's checkers program, Newell & Simon's Logic Theorist, Gelernter's Geometry Engine
- **1956**: Dartmouth meeting: "Artificial Intelligence" adopted
- **1962**: Rosenblatt's Perceptron for training simple neural networks
- **1965**: Robinson's complete algorithm for logical reasoning
- **1972**: The logic programming language PROLOG is created
- **1966-74**: Disappointment: AI discovers computational complexity. Neural network research almost disappears.
- **1969-79**: Early development of knowledge-based systems
- **1980-88**: Expert systems industry booms
- **1988-93**: Expert systems industry busts: "AI Winter"
- **1985-95**: Backpropagation learning returns neural networks to popularity.
- **1988-**: Resurgence of probability; general increase in technical depth. "Nouvelle AI": ALife, GA
- **1995-**: Agents, agents, everywhere...
- **2003-**: Human-level AI back on the agenda
- **2005-2010**: AI disappoints again, AI is not much appreciated

## Example from Early History of AI

1943 McCulloch & Pitts: Boolean circuit model of brain
![](img/l1/figure3.png)

## McCulloch and Pitts 1943

**Goal:** to understand how the brain produces complex thoughts ("propositions") by using (simple) neurons

- model of a neuron, axon, dendrone - "MCP neuron"
- network of neurons
- transfer of information through on/off mechanism of neurons
- every network of MCP neurons encodes some logical proposition

## McCulloch and Pitts 1943 - "Bird example"

Example from:
http://www.mind.ilstu.edu/curriculum/mcp_neurons/mcp_neuron_1.php?modGUI=212&compGUI=1749&itemGUI=3018

Assume a bird will "decide" to eat/not an object (e.g., blue berry, orange, basketball, daisy). It receives/perceives two inputs about the object:

- shape: round or not
- colour: purple or not
- decision: eat only if round purple object (e.g., blue berry)
  ![](img/l1/figure4.png)
- two inputs (each takes value $0$ or $1$)
- threshold $T$
- output is a function of inputs and $T$

```
IF(sum(inputs)) >= T
THEN Output=1
```

![](img/l1/figure5.png)
![](img/l1/figure6.png)
![](img/l1/figure7.png)

## Some killer apps in AI

- **1991:** During the Gulf War, US forces deployed an AI logistics planning and scheduling program that involved up to $50,000$ vehicles, cargo, and people. Saved the US more money than spent on all AI research since 1950.
- **1997:** Deep Blue (IBM) beat world chess champion Gerry Kasparov"
- **2011:** Watson (IBM) beat human champions on "Jeopardy"
- **2012:** Google car obtains driver's license in Nevada, US. By 2014, the cvars have driven for 1.1 million km without accidents.
- **2017:** DeepMind's AlphaGo and Elon Musk's A.I. Destroys Champion Gamer! https://www.youtube.com/watch?v=XbDmxEOj9OY

## What is AI?

Russel and Norvig's definition of AI
Two dimensions:
![](img/l1/figure8.png)
Types/approaches to AI - as defined by Russel and Norvig:
![](img/l1/figure9.png)

## Thinking humanly: Cognitive Science

1960s "**cognitive revolution**": information-processing psychology replaced prevailing orthodoxy of **behaviorism.**
Tries to form computational theories of internal activities of the brain. How to validate? Requires

1. Predicting and testing behaviour of human subjects (top-down), or
2. Direct identification of neurological data (bottom-up)

Both approaches (roughly, **Cognitive Science** and **Cognitive Neuroscience**) are now distinct from AI.

Both share with AI the following characteristics: the available theories do not explain (or engender) anything resembling human-level general intelligence.

## John McCarthy talks about AI

https://www.youtube.com/watch?v=Ozipf13jRr4

## Acting humanly: The Turing test

Turing (1950) "Computing machinery and intelligence":
"Can machines think?" $\rightarrow$ "**Can machines behave intelligently**"
Operational test for intelligent behavior: the **Imitation Game**
![](img/l1/figure10.png)

## Acting Humanly - Eliza

- One of the most famous early AI programs: Eliza, the computer psychotherapist, created by Joseph Weizenbaum in 1966 at MIT.
- Eliza functions by "twisting the statements of her 'patients' back at them in the classic manner of a non-directive psychotherapist."
- The fact that it understands the subject's statements is an illusion.
- Surprisingly, many users were taking its performance quite seriously.
  ![](img/l1/figure11.png)

## How humanly is Sophia (Hong Kong firm Hanson Robotics)?

https://www.youtube.com/watch?v=suRuQbDXcrc

## Thinking rationally: Laws of Thought - 1

- Aristotle: what are correct arguments/thought processes? Formalize "correct" reasoning using a mathematical model.
- Several Greek schools developed various forms of **logic:** _notation_ and _rules of derivation_ for thoughts.
- Direct line through mathematics and philosophy to modern AI.

## Thinking rationally: Laws of Thought - 2

![](img/l1/figure12.png)

## Thinking rationally: Laws of Thought - 3

![](img/l1/figure13.png)

## Thinking rationally: Laws of Thought - 4

Problems:

1. Not all intelligent behavior is mediated by logical deliberation
2. What is the purpose of thinking? What thoughts _should_ I have out of all the thoughts (logical or otherwise) that I _could_ have?
3. Formalizing (informal) common sense knowledge is difficult.
4. General deductive inference is computationally intractable.

## Acting rationally: Rational Agents approach

- **Rational** behavior: doing the right thing.
- The right thing: that which is expected to maximize goal achievement, given the available information and computational abilities.
- Doesn't necessarily involve thinking - e.g., blinking reflex - but thinking should be in the service of rational action.

## Two main AI paradigms

- **Good old fashioned AI** (GOFAI)
- **Situated embodied AI** (SEAI)

## Good old fashioned AI

- Most of the successes if AI in the 1970s and 1980s were due to research based on Newell's and Simon's _Physical Symb'ol System Hypothesis_
- A physical symbol system has the necessary and sufficient means for general intelligent action.
- Newell and Simon viewed intelligence as _symbol manipulation,_ and hypothesized that it didn't make difference what physical medium - brain, paper, or computer - was used to do the symbol manipulation.
- Hence a special emphasis on _symbolic representations,_ which can be interpreted as reprsenting situations in the real world, e.g. "a block world"

## Critiques of GOFAI

- **Searle:** a program (or any physical symbol system) could not be said to understand the symbols that is utses; the symbols have no meaning for the machine.
- **Brooks:** our most basic skills of motion, survival, perception, balance etc. do not seem to require high level symbols at all; the use of high level symbols was more complicated and less successfull.
- **Harnad:** the **symbol grounding** problem: an agent does not perceive symbols, instead the brain converts sensory inputs into higher level abstractions, e.g. symbols.

## Emergence of SEAI

- The GOFAI approaches turned out to be brittle and very little robust when deployed on real-world problems.
- Trying to define a model of the world turned out to be quite hard - this led to Brook's statement that "the world is its own best model"
- Situated and embodied AI focuses on having a body (i.e. motor skills) in a physical environment.
- Swarm intelligence, subsymbolic AI, genetic algorithms, neural networks - however, this is not a big part of this course, this is covered in more detail in other AI courses.

# Lecture 2 - Intelligent Agents <a name="c2"></a>

## Agents and environments

![](img/l2/figure1.png)

## Agent types

An agent is anything that can be viewed as perceiving its environment through sensors and acting upon that environment through actuators.
![](img/l2/figure2.png)

## Agent

- Human agent: eyes, ears, and other organs for sensors; hands, legs, mouth, and other body parts for actuators.
  ![](img/l2/figure3.png)
- Robotic agent: cameras and infrared range finders for sensors; various motors for actuators.
- Software agent: screen, keyboard, smart phones etc.

## Example: Vacuum-cleaner world

![](img/l2/figure4.png)

## Agent function - and program

An **agent function** maps from percepts to actions:
$$f:\mathcal{P}\rightarrow\mathcal{A}$$
The **agent program** runs on the physical _architecture_ to produce $f$
![](img/l2/figure1.png)

## Systems that act rationally

- Rational behavior: "doing the right thing". What is the **right thing**?
- May include thinking for action - action without thinking: ?
- Rationality can be defined and optimized
- On the other hand
  - perfect rationality is only feasible in ideal environments.
  - rationality is often not a very good model of reality.
    - Humans are, e.g., very bad in estimating probabilities.

## Rational agent

A rational agent should select an action that is expected to maximize its performance measure, given

- the evidence provided by the percept sequence and
- whatever built-in knowledge the agent has

Rational $\implies$ exploration, learning, autonomy

An agent is **autonomous:** takes its decisions (e.g., decide actions) according to the current situation, and changes their "plans" accordingly.
![](img/l2/figure5.png)
Sphex wasp relies on its innate "plan", hence lacks autonomy.

## Rationality depends on PEAS

**P:** The _performance_ measure
**E:** The agent's prior knowledge about the _environment_
**A:** The _actions_ that the agent can perform
**S** The percept _sequence_

## Design objects and rationality

- A rational agent performs actions in line with the design objectives.
- These objectives shape the performance measure
- Selected performance measure evaluates the **environment sequence**

- For example, in case of the vacuum cleaner, the designer should focus only on collecting as much dirt as possible in time $T$
  ![](img/l2/figure4.png)
- Or, take also other factors into account, e.g.:
  - amount of time taken to clean
  - amount of electricity consumed
  - amount of noise generated, etc
- e.g., one point per square cleaned up in time $T,$ or
  - one point per clean square per time step, minus one per move
  - etc

## PEAS

To design a rational agent, we must specify the **PEAS**
Consider, e.g., designing an automated taxi:
**Performance measure??**
**Environment??**
**Actuators??**
**Sensors??**

## Automated taxi

- **Performance measure:** safety, destination, profits, legality, comfort
- **Environment:** streets/highway, traffic, pedestrians, weather
- **Actuators:** steering, accelerator, brake, horn, speaker/display
- **Sensors:** video, accelerometers, gauges, engine sensors, GPS

## Internet shopping agent

- **Performance measure:** price, quality, appropiateness, efficiency
- **Environment:** current and future WWW sites, vendors, shippers
- **Actuators:** display to user, follow URL, fill in form
- **Sensors:** HTML pages (text, graphics, scripts)

## Medical diagnosis system agent

- **Performance measure:** healthy patient, minimize costs, lawsuits
- **Environment:** patient, hospital, staff
- **Actuators:** screen display (questions, tests, diagnoses, treatment, referrals)
- **Sensors:** keyboard (entry of symptoms, findings, patient's answers)

## Properties of environments

**Fully observable environments**

- relevant parts of the state of the environment can be sensed
- no need to maintain any internal state to keep track of the world

**Partially observable environments**

- parts of the environment cannot be sensed
- agent must make informed guesses about the world

## Fully vs Partially Observable Environments - example

![](img/l2/figure6.png)

- squares adjacent to Wumpus are smelly
- squares adjacent Pit are breezy
- glitter iff gold is in the same square
- shooting kills wumpus if you are facing it
- only one arrow to shoot

## Fully vs Partially Observable Environments

![](img/l2/figure7.png)

## Properties of environments

**Deterministic environment**

- Any action has a single guaranteed effect, and no uncertainty/failure.

**Stochastic environment**

- There is some uncertainty about the outcome of an action
- Multiple outcome alternatives, quantified in terms of probabilities

![](img/l2/figure8.png)

**Episodic environments**

- The agent's experience is divided into atomic episodes.
- Each episode consists of the agent perceiving and then performing a single action
- The choice of action in each episodes depends only on the episode itself.

**Sequential environments**

- The current decision could affect all future decisions

![](img/l2/figure9.png)

**Discrete**
Finite number of distinct states, percepts and actions.

**Continuous**
Continuous time/state/actions

![](img/l2/figure10.png)

**Dynamic environments**
May change while an agent is deliberating

**Static environments**
The environment does not change

**Semidynamic**
The world does not change but the agent's performance score may

![](img/l2/figure11.png)

**Single agent**
No otger agents - there may be but as a part of the environment

**Multi-agent**

- Which entities will be viewed as "other agents"?
- The environment contains other agens whose performance measure depends on my actions and vice versa
- Competitive and cooperative interactions

![](img/l2/figure12.png)

**Known environments**

- The agent's knowledge about how the environment works/evolves.
- Note that a known environment (i.e., the agent knows all the rules that apply) may be only partially observable

![](img/l2/figure13.png)

**Unknown environment**

- The agent will have to learn how it works
- An unknown environment can be fully observable

## Environment type and agent design

**The environment type largely determines the agent design**

The real world is (of course) partially observable, stochastic, sequential, dynamic, continuous, multi-agent

## Agent Function

- The agent function will internally be represented by the agent program.
- The agent program runs on the physical architecture to produce $f.$

![](img/l2/figure14.png)

## A simple vacuum-cleaner agent

Table that maps percept sequences to actions
![](img/l2/figure15.png)

## A simple general agent

```
function Table-driven-Agent([percepts]) returns an action
  static: table, maps percepts to actions

  append percept to the end of percepts
  action <-- Lookup(percepts, table)
```

- looks up the right respone in the table
- Infeasible: if there are $|P|$ percepts and a life-time of $T,$ then need for a look-up table of size $\sum_{t=1}^T{|P|^t}$

## Agent programs

Writing down such agent functions is not feasible.

The goal of AI is to write agent programs with small code which produces the desired rational behaviour.

## Agent types

Four basic types in order of increasing generality:

- simple reflex agent
- model-based reflex agent
- goal-based agents
- utility-based agents

## Simple reflex agents

![](img/l2/figure16.png)

- Uses only the current percept - ignores the percept sequence
- Implemented through condition-action rules
- Large reduction in possible percept/action situations from $\sum_{t=1}^T{|P|^t}$ to $|P|$

Example:

```
function Reflex-Vacuum-Agent([location,status]) returns an action

  if status == Dirty then return Suck
  else if location == A then return Right
  else if location == B then return Left
```

## Generic Simple Reflex Agent program

A more general simple reflex agent program:

```
function Generic-SimpleReflexAgent( percept) returns an action
  static: rules

  state <-- Interpret(percept)
  rule <-- Rule-match(state)
  action <-- Rule-action(rule)
  return action
```

- Will only work if the environment is fully observable
- everything relevant needs to be determinable from the current input
- otherwise infinite loops may occur, e.g. in the vacuum world without a sensor for the room, the agent does not know whether to move right or left
  - any possible solution: randomize actions

## Simple Reflex agent in "Wumpus world" ??

![](img/l2/figure17.png)

How good a Simple Relex (i.e., without a memory of past) can do in the Wumpus world? Not good :(

## Model-based Reflex agents

![](img/l2/figure18.png)

```
function REFLEX-AGENT-WITH-STATE(percept) returns an action
  static: state, a description of the current world state
          rules, a set of condition-action rules
          action, the most recent action, initially none

  state <-- UPDATE-STATE(state, action, percept)
  rule <-- RULE-MATCH(state, rule)
  action <-- RULE-ACTION(rule)
  return action
```

- difficult to exactly determine the current state in partially observable environments - independent from the kind of models used
- hence, may require under certainty - to "guess" the current situation
- action decision in the same way as the simple reflex agent.

## Goal-based agents

![](img/l2/figure19.png)

## Example

- Belief Desire Intention agents (BDI) agents have a **mental state** as the basis for their reasoning.
- Three main mental attitudes: beliefs, desires and, intentions.
- Their reasoning is also **practical reasoning** - e.g., contrary to deductive reasoning.

![](img/l2/figure20.png)

## Goal-based agents

- explicit representation og goals: agent knows which states are desirable
- reasoning about goals
- more flexible since knowledge is represented explicitly and can be manipulated
- different reasoning methods than reflex - not condition-action rules and selection of rule/action
- main different from reflex agents: deliberates about future when making decision
- long sequence of actions may be needed to achieve the goal
  - e.g., agents in chapters 3-5 (search) and chapters 10-11 (planning)
- less efficient than reflex agents - but more flexible

## Utility-based agents

Goals provide just a binary happy/unhappy distinction, while utility functions provide a continious scale.

Some goals may be achieved in more than one way, with different utility values

![](img/l2/figure21.png)

- utilities are internalization of the performance measure
- Utility function maps a state (or a sequence of states) onto a real number
- utilities reflect agent's preferences
- not always known the utility of an action/outcome, hence "expected utility"
- agent chooses actions that maximize the expected utility of the outcomes

## Learning agents

![](img/l2/figure22.png)

# Lecture 3 - Problem Solving as Search | Uninformed Search <a name="c3"></a>

## Problem solving and search

- Some problems have straightforward soltions
  - Solve by applying a formula, or a well-known procedure.
  - Example: differential equations
- Other problems require search:
  - no single standardized method
  - alternatives need to be exlored to solve the problem
  - the number of alternatives to search among can be very large, even infinite.

## Example: Cabbage, goat, wolf and farmer

![](img/l3/figure1.png)

How many river crossings does the farmer need? 4, 5, 6, 7, or no solution?
How did you think to solve the problem?

## Cabbage, goat, wolf, and the farmer

![](img/l3/figure2.png)

## Cabbage, goad, wolf and farmer - an answer

![](img/l3/figure3.png)

- The important thing is not how you solved this manually
- Important is how we can make the machine to solve such problems automatically
- What kind of systemical approach in order to considers possibilities?
- Search is a suitable method to do this

## Example: solving 8-puzzle

![](img/l3/figure4.png)

What is a **state**?

## Example: 8-puzzle

![](img/l3/figure5.png)

Search is about exploring alternatives.

## Problem-solving agents

A type of goal-based agent.

```
function SIMPLE-PROBLEM-SOLVING-AGENT(percept) returns an action
    static: seq, an action sequence, initially empty
            state, some description of the current world state
            goal, a goal, initially null
            problem, a problem formulation

    state <-- UPDATE-STATE(state, percept)
    if seq is empty then
        goal <-- FORMULATE-GOAL(state)
        problem <-- FORMULATE-PROBLEM(state, goal)
        seq <-- SEARCH(problem)
    action <-- FIRST(seq, state)
    seq <-- REST(seq, state)
    return action
```

## Problem formulation

![](img/l3/figure6.png)

A _problem_ is defined by:

- initial state: e.g., "at Arad"
- actions: e.g., Go(Sibiu)
- transition model: defines what each action does. e.g., {In(Arad), Go(Sibiu), In(Sibiu)}
- goal test
- path cost: e.g., sum of distances, number of actions executed, etc. $c(x,a,y)$ is the _step cost_, assumed to be nonnegative.

A _solution_ is a sequence of actions leading from the initial state to a goal state.

## Goal formulation

Goal may be

- explicit, e.g., 8-puzzle
- implicit, e.g., "no dirt"; through a condition as in sudoku: underdefined $8$-puzzle (figure below) where "any" means any except 8, 3, 1

![](img/l3/figure7.png)

## Solution

- A solution is a sequence of actions that connect the initial state to a goal state.
- Sometimes no solutions exists

![](img/l3/figure8.png)

## State Space

![](img/l3/figure9.png)

**A state:** the agent location and the dirt locations
**State Space:** All the possible states and the links/relationship (in terms of actions) between them

- How many states in this state space?
- The agent can be in one of the $2$ locations, and each location may/not have dirt, so $2\times2^2$ possible states.
- For an $n$-location environment, the state space has $n\times2^n$ states

## State space - Romania example

![](img/l3/figure6.png)

On holday in Romania; currently in Arad.
Flight leaces tomorrow from Bucharest

- **Formulate goal:** be in Bucharest
- **Formulate problem:**
  - **states:** various cities
  - **actions:** drive between cities
- **Find solution:** sequences of cities, e.g., Arad, Sibiu, Fagaras, Bucharest

## Example: Vauum world state space graph

![](img/l3/figure9.png)

- **States:** integer dirt and robot locations (ignore dirt _amounts_ etc.)
- **Actions:** Left, Right, Suck, NoOp
- **Goal test:** no dirt
- **Path cost:** 1 per action (0 for NoOP)

## Example 8-puzzle

![](img/l3/figure5.png)

- **States:** integer locations of tiles (ignore intermediate positions)
- **Actions:** move blank left, right, up, down (ignore unjamming etc.)
- **Goal test:** goal state (given)
- **Path cost:** 1 per move

[Note: optimal solution of $n$-Puzzle is NP-hard]

## Example: robotic assembly

![](img/l3/figure10.png)

- **States:**
  - real-valued coordinates of robot joint angles
  - parts of the object to be assembled
- **Actions:** continious motions of robot joints
- **Goal test:** complete assembly
- **Path cost:** time to execute

## State Space Graph and Search Tree

![](img/l3/figure11.png)
![](img/l3/figure12.png)

- A _state_ is a (representation of) a physical configuration
- A _node_ is a data structure consistuting part of a search tree
  - includes parent, children, depth, path cost $g(x)$
- Sates do not have parents, children, depth, or path cost!

## State graph is incrementally explored

- Most of the time it is not feasible or too expensive to build and represent the entire state graph. The problem solver agent (i.e., AI) generates a solution by **incrementally exploring** a small portion of the graph.

## Implementation: general tree search

Basic idea: simulated exploration of state space by generating successors of already-explored states

```
function TREE-SEARCH(problem, frontier) returns a solution, or failure

  Initialize the frontier using the initial state of the problem
  loop do
    if frontier is empty then return failure
    choose a leaf node and remove it from the frontier
    if the node contains a goal state then return the correspond solution
    expand the chosen node, adding the resulting nodes to the frontier
  end
```

## Graph search

Checks the repetition of nodes.

```
function GRAPH-SEARCH(problem, frontier) returns a solution, or failure

  Initialize the frontier using the initial state of the problem
  Initialize the explored set to be empty
  loop do
    if frontier is empty then return failure
    choose a leaf node and remove it from the frontier
    if the node contains a goal state then return the correspond solution
    add the node to the explored set
    expand the chosen node, adding the resulting nodes to the frontier
      only if not in the frontier or explored
  end
```

## Search strategies

A strategy is defined by picking the _order of node expansion_

Strategies are evaluated along the following dimensions:

- _completeness_ - does it always find a solution if one exists?
- _time complexity_ - number of nodes generated/expanded
- _space complexity_ - maximum number of nodes in memory
- _optimality_ - does it always find a least-cost solution?

Time and space complexity are measured in terms of

- $b$ - maximum branching factor of the search tree
- $d$ - depth of the least-cost solution
- $m$ - maximum depth of the state space (may be $\infty$)

## Examples on Uninformed Search Strategies

Different "search strategies" explore the possibilites in different order

![](img/l3/figure13.png)

## Uninformed search strategies

_Uninformed_ strategies use only the information in the problem definition

- Breadth-first search
- Uniform-cost search
- Depth-first search
- Depth-limited search
- Iterative deepening search

## Breadth-first search

Idea: explore the search space "horizontally", i.e. expanding all nodes at level $k$ before taking into account nodes at level $k+1$

Implementation: The intended behavior can be ensured by using a FIFO policy for storing to be expanded nodes.

## Breadth-first search on a graph

```
function BREADTH-FIRST-SEARCH(problem) returns a solution, or failure

  node <-- a node with STATE = problem.INITIAL-STATE, PATH-COST = 0
  if problem.GOAL-TEST(node.STATE) then return SOLUTION(node)
  frontier <-- a FIFO queue with node as the only element
  explored <-- an empty set
  loop do
    if EMPTY?(frontier) then return failure
    node <-- POP(frontier) /* chooses the shallowest node in frontier */
    add node.STATE to explored
    for each action in problem ACTIONS(node.STATE) do
      child <-- CHILD-NODE(problem,node,action)
      if child.STATE is not in explored or frontier then
        if problem.GOAL-TEST(child.STATE) then return SOLUTION(child)
        frontier <-- INSERT(child,frontier)
```

### Breadth-first search

Expand shallowest unexpanded node
**Implementation:**

- _fringe_ is a FIFO queue, i.e., new successors go at end

![](img/l3/figure14.png)
![](img/l3/figure15.png)
![](img/l3/figure16.png)

## Properties of breadth-first search

- **Complete:** Yes (if $b$ is finite)
- **Time:** $1+b+b^2+b^3+\dots+b^d=O(b^d),$ i.e., exp. in $d$
- **Space:** $O(b^d)$ (keeps every node in memory)
- **Optimal:** Yes (if path cost is nondecreasing with depth, e.g., all actions have the same cost); not optimal in general.

**Space** is the big problem; can generate nodes at 1000MB/sec so 24hrs = 86400GB.

## Uniform-cost search

An algorithm optimal with varying positive step costs.

```
function UNIFORM-COST-SEARCH(problem) returns a solution, or failure

  node <-- a node with STATE=problem.INITIAL-STATE, PATH-COST=0
  frontier <-- a priority queue ordered by PATH-COST, with node as the only element
  explored <-- an empty set
  loop do
    if EMTPY?(frontier) then return failure
    node <-- POP(frontier) /* chooses the lowest-cost node in frontier */
    if problem-GOAL-TEST(node.STATE) then return SOLUTION(node)
    add node.STATE to explored
    for each action in problem.ACTIONS(node.STATE) do
      child <-- CHILD-NODE(problem,node,action)
      if child.STATE is not in exlored or frontier then
        frontier <-- INSERT(child,frontier)
      else if child.STATE is in frontier with higher PATH-COST then
        replace that frontier node with child
```

Expand least-cost unexpanded node
**Implementation:**

- _fringe_ = queue ordered by path cost, lowest first

Equivalent to breadth-first if step costs all equal

- **Complete:** Yes, if step cost $\geq\epsilon$
- **Time:** # of nodes with $g\leq$ cost of optimal solution, $O\left(b^{1+[C*/\epsilon]}\right)$ where $C*$ is the cost of the optimal solution
- **Space:** # of nodes with $g\leq$ cost of optimal solution, $O\left(b^{1+[C*/\epsilon]}\right)$
- **Optimal:** Yes - nodes expanded in increasing order of $g(n)$

## Depth-first search

Expand deepest unexpanded node
**Implementation:**

- _fringe_ = LIFO queue, i.e., put successors at front

![](img/l3/figure17.png)
![](img/l3/figure18.png)
![](img/l3/figure19.png)
![](img/l3/figure20.png)
![](img/l3/figure21.png)
![](img/l3/figure22.png)
![](img/l3/figure23.png)
![](img/l3/figure24.png)
![](img/l3/figure25.png)
![](img/l3/figure26.png)
![](img/l3/figure27.png)
![](img/l3/figure28.png)

## Properties of depth-first search

- **Complete:** No: tree search fails in infinite-depth spaces, e.g., spaces with loops
  - Modify to avoid repeated states along path. Check if current nodes occured before on path to root. No extra memory cost but it avoids infinite loops, not redundant paths.
  - Can use graph search (remember all nodes ever seen). It is complete in finite spaces. Problem with graph search: space is exponential, not linear. Still fails in infinite-depth spaces (may miss goal).
  - $\implies$ complete in finite spaces
- **Time:** $O(b^m):$ terrible if $m$ is much larger than $d$ but if solutions are dense, may be much faster than breadth-first
- **Space:** $O(bm),$ i.e., linear space!
- **Optimal:** No

## DFS

![](img/l3/figure29.png)

## Depth-limited search

= depth-first search with depth limt $l$, i.e., nodes at depth $l$ have no successors

**Recursive implementaiton:**

```
function DEPTH-LIMITED-SEARCH(problem, limit) returns soln/fail/cutoff
  RECURSIVE-DLS(MAKE-NODE(INITIAL-STATE[problem]), problem, limit)

function RECURSIVE-DLS(node,problem,limit) returns soln/fail/cutoff
  cutoff-occurred? <-- false
  if GOAL-TEST(problem,STATE[node]) then return node
  else if DEPTH[node] == limit then return cutoff
  else for each successor in EXPAND(node,problem) do
    result <-- RECURSIVE-DLS(successor,problem,limit)
    if result == cutoff then cutoff-occurred? <-- true
    else if result != failure then return result
  if cutoff-occurred? then return cutoff else return failure
```

## Iterative deepening search

```
function ITERATIVE-DEEPENING-SEARCH(problem) returns a solution
  inputs: problem, a problem

  for depth <-- 0 to infinity do
    result <-- DEPTH-LIMITED-SEARCH(problem, depth)
    if result != cutoff then return result
  end
```

## Iterative deepening search with $l=0$

![](img/l3/figure30.png)

## Iterative deepening search with $l=1$

![](img/l3/figure31.png)

## Iterative deepening search with $l=2$

![](img/l3/figure32.png)

## Iterative deepening search with $l=3$

![](img/l3/figure33.png)

## Properties of iterative deepening search

- **Complete:** Yes
- **Time:** $(d+1)b^0+db^1+(d-1)b^2+\dots+b^d=O(b^d)$
- **Space:** $O(bd)$
- **Optimal:** Yes, if step cost are equal

## Uninformed vs informed search

![](img/l3/figure34.png)

- For an uninformed search strategy, states S1 and S2 are two indifferent nodes (e.g., at the same level in the search tree)
- Uninformed search strategies uses only the position of the nodes in the tree, not the state descriptions
- S1 is more promising than S2 for an informed (heuristic) search strategy that counts the number of misplaced tiles
- Heuristic strategies use the information in the state description

## Summary of tree-search algorithms

![](img/l3/figure35.png)

- \*a) breadth-first complete if $b$ is finite
- \*b) uniform-cost complete if step cost is $\geq\epsilon>0$
- \*c) optimal if step costs are equal. Also if path cost non-decreasing fn. of depth.

# Lecture 4 - Informed search and Local search <a name="c4"></a>

## Recap

- Problem solving through searching in a solution space
- The basis:

```
funciton TREE-SEARCH(problem,frontier) returns a solution, or failure

    Initialize the frontier using the initial state of the problem
    loop do
        if frontier is empty then return failure
        choose a leaf node and remove it from the frontier
        if the node contains a goal state then return node the corresponding solution
        expand the chosen node, adding the nodes to the frontier
    end
```

- A strategy is defined by picking the **order of node exploration**

## Uninformed Search disadvantageous

- Last week: Uninformed search
- Uninformed search, systematically searching the search space blindly - not questioning where the goal may be in the space
- Search space is often very large. Time/space problems with such exhaustive search - think of chess
- In such situations, better to use algorithms which does a more informed search

## Heuristic

Informed Search algorithms used "heuristics".
What is a heuristic?

![](img/l4/figure1.png)

## Heuristic - example

![](img/l4/figure2.png)
![](img/l4/figure3.png)

## Heuristic Search Algorithms

Today we look at two well-known informed search algorithms:

- Greedy Best First search
- A\*

## Best-first search

- **Idea:** use an **evaluation function** for each node
  - estimate of "desirability"
- $\implies$ Expand most desirable unexpanded node
- **Implementation:**
  - _frontier_ is a queue sorted in decreasing order of desirability
- Special cases:
  - Greedy search
  - A\* search

## Greedy search

- Evaluation funcion = $h(n)$ (<b>h</b>euristic)
  - estimate the cost from $n$ to the closest goal
- E.g., $h_{SLD}(n)=$ straight-line distance from $n$ to Bucharest
- Gready search expands the nodes that **appears** to be closest to goal

## Greedy Search, Romania Example

![](img/l4/figure4.png)

## Greedy search for Romania example

![](img/l4/figure5.png)

## Greedy search example

![](img/l4/figure6.png)
![](img/l4/figure7.png)
![](img/l4/figure8.png)

## Properties of greedy search

![](img/l4/figure3.png)

- **Complete:**
  - No for tree search - can get stuck in loops, e.g., assume getting from Iasi to Fagaras.
  - Straight line distance-wise, Neamt is closest to Fagaras. Hence, Iasi $\rightarrow$ Neamt $\rightarrow$ Iasi $\rightarrow$ Neamt $\rightarrow\dots$
  - Complete in graph version (i.e., with repeated-state checking) for finite spaces
- **Time:** $O(b^m)$, but a good heuristic can give dramatic improvement
- **Space:** $O(b^m)$ - keeps all nodes in memory
- **Optimal:** No. E.g., the path it found (Sibiu-Fagaras-Bucharest) is longer than the path Sibiu-Rimnicu-Vilcea-Pitesti-Bucharest

## A\* search

**Idea:** avoid expanding paths that are already expensive

Evaluation function
$$f(n)=g(n)+h(n)$$
$g(n)=$ cost so far to reach $n$
$h(n)=$ estimated cost of the cheapest path from $n$ to goal node
$f(n)=$ estimated cost of the cheapest solution through $n$ to goal

## A\* search example

![](img/l4/figure9.png)
![](img/l4/figure10.png)
![](img/l4/figure11.png)
![](img/l4/figure12.png)
![](img/l4/figure13.png)
![](img/l4/figure14.png)

## Properties of A\*

- **Complete:**
  - Yes, unless there are infinitely many nodes with $f\leq f(G).$
  - I.e., if all step costs are $>\epsilon$ and $b$ is finite.
- **Time:** Exponential in [relative error in $h\times$ length of solution.]
- **Space:** Main drawback. Keeps all nodes in memory
- **Optimal:** Yes - cannot expand $f_{i+1}$ until $f_i$ is finished

A* expands all nodes with $f(n)<C*$ (where $C*$ is the cost of optimal solution path)
A* expands some nodes with $f(n)=C*$
A* expands no nodes with $f(n)>C*$

## Optimality of A\*

A\* optimal if

- the branching factor is finite
- arc costs are strictly positive
- for tree search: $h$ is admissible and is non-negative
- for graph search: $h$ is consistent (monotonic) and non-negative

**Admissible:** Does not overestimate the cost from node $n$ to the goal node (Also require $h(n)\geq0,$ so $h(G)=0$ for any goal $G.$)

**Lemma:** A\* expands nodes in order of increasing $f$ value

Gradually adds "$f$-contours" of nodes (cf. breadth-first adds layers). Contour $i$ has all nodes with $f=f_i,$ where $f_i<f_{i+1}$

![](img/l4/figure15.png)

Suppose some suboptimal goal $G_2$ has been generated and is in the queue. Let $n$ be an unexpanded node on a shortest (least cost) path to an optimal goal $G.$
We want to prove: $f(n)<f(G_2)$ - (then A\* will prefer $n$ over $G_2$)

![](img/l4/figure16.png)

## Example - Admissibility-Optimality

![](img/l4/figure17.png)

## A\* is optimally efficient

Optimal Efficiency: No other algorithm using the same heuristic information is guaranteed to expand fewer nodes than A* - expcept it may be unlucky about how it breaks ties between nodes with $f(n)<C*.$

This is because any algorithm that does not expand all nodes with $f(n)<C*$ has the risk of missing the optimal solution.

## Consistency

A heuristic is **consistent** / **monotonous** if

![](img/l4/figure18.png)
If $h$ is consistent, we have

$$
\begin{aligned}
f(n')&=g(n')+h(n')\\
&=g(n)+c(n,a,n')+h(n')\\
&\geq g(n)+h(n)\\
&\geq f(n)
\end{aligned}
$$

I.e., $f(n)$ is nondecreasing along any path.

## A\* graph search algorithm - pseudocode

Assumption: heuristic is consistent (hence admissible)
**Theorem:** If $h(n)$ is consistent, A\* Graph Search is optimal

```
Start.g = 0;
Start.h = heuristc(Start);
FRONTIER = {Start}
CLOSED = {empty set}
WHILE FRONTIER is not empty
  N = FRONTIER.popLowestF()
  IF state of N = GOAL RETURN N
  add N to CLOSED
  FOR all children M of N not in CLOSED:
    M.parent = N
    M.g = N.g + cost(N,M)
    M.h = heuristic(M)
    add M to FRONTIER
  ENDFOR
ENDWHILE
```

Does not re-expand nodes in CLOSED.
Would it find the optimal solution?

## Example - More on A\* graph search

![](img/l4/figure19.png)

- When a new node $N$ is generated:
  - If $N$ is in _Closed_ then discard $N$
  - If $N$ is already in frontier, then keep $N$ with least $f$ value.

## Example cont. Graph with consistent heuristic

![](img/l4/figure20.png)

- When a new node $N$ is generated:
  - If $N$ is in _Closed_ then discard $N$
  - If $N$ is already in frontier, then keep $N$ with least $f$ value.

## Admissible heuristics

E.g., for the $8$-puzzle:

Goal state is: Upper left tile is empty, in the rest of the frid: numbers 1-8 are in natural order (example from the book).

$h_1(n)=$ number of misplaced tiles
$h_2(n)=$ total Manhattan distance (i.e., no. of squares from desired location of each tile)

![](img/l4/figure21.png)

## Dominance

If $h_2(n)\geq h_1(n)$ for all $n$ (both admissible) then $h_2$ dominates $h_1$ and is better for search

Typical search costs:

![](img/l4/figure22.png)

Given any admissible heuristics $h_a,h_b,$
$$h(n)=max(h_a(n),h_b(n))$$
is also admissible and dominates $h_a,h_b$

## Relaxed problems

Admissible heuristics can be derived from the **exact** solution cost of a **relaxed** version of the problem

If the rules of the 8-puzzle are relaxed to that a tile can move **anywhere**, then $h_1(n)$ gives the shortest solution.

If the rules are relaxed to that a tile can move to any **any adjacent square,** then $h_2(n)$ gives the shortest solution

Key point: the optimal solution cost of a relaxed problem is no greater than the optimal solution cost of the real problem

## Local Search

In many optimization problems, **path** is irrelevant; the goal state itself is the solution

Then state space = set of "complete" configurations;
find **optimal** configuration, e.g., TSP
or, find configuration satisfying constraints, e.g., timetable

In such cases, can use iterative improvement algorithms;
keep a single "current" state, try to improve it

Constant space, suitable for online as well as offline search

## Incremental versus Local Search

![](img/l4/figure23.png)

## Properties of Local Search

- Low space complexity - only need to save one (or a set) of current solutions, NOT paths back to the start state.
- Time complexity varies, though recent work indicates major improvements over incremental search for problems with densely-packed optimal solutions.
- Satisficing - can often find _reasonably good_ solutions quickly.
- Requires representations that are easy to _tweak_ to generate search-space neighbors.
- Uses an **objective function** to evaluate solutions. Similar to a heuristic but for complete solutions $\rightarrow$ less guesswork.
- Often portrayed as movement in a **landscape.**

## Example: Travelling Salesperson Problem

Find the shortest (least cost) tour that visits each city and returns to the start-city, i.e., Eval(Solution) is minimum.

![](img/l4/figure24.png)

Start with any complete tour, perform (action) pairwise exchanges

![](img/l4/figure25.png)

Variants of this approach get within 1% op optimnal very quicklu with thousands of cities

## Example: $n$-queens

Put $n$ queens on an $n\times n$ board with no two queens on the same row, column, or diagonal

Move a queen (on the same column) to reduce the number of conflicts

![](img/l4/figure26.png)

Almost always colves $n$-queens problems almost instantaneously for very large $n,$ e.g., $n=1$ million

## Egg Carton Problem

Put as many eggs as possible into the $M\times N$ carton, but never have more than $K$ eggs along any horizontal, vertical or diagonal line. Typically, $K=2.$

![](img/l4/figure27.png)

## Representations, Translation and Evaluation

![](img/l4/figure28.png)

## State-space Landscape

Useful to consider **state space landscape**

![](img/l4/figure29.png)

## Search Landscape

![](img/l4/figure30.png)
**Critical-Design Decisions**

- Objective function defines the landscape.
- Representation-modifying operators define legal moves in landscape.

## Hill-climbing (or gradient ascent/descent)

```
function HILL-CLIMBING(problem) returns a state that is a local maximum
  inputs: problem, a problem
  local variables: current, a node
                   neighbour, a node

  current <-- MAKE-NODE(INITIAL-STATE[problem])
  loop do
    neighbour <-- a highest valued successor of current
    if VALUE[neighbour] <= VALUE[current] then return STATE[current]
    current <-- neighbour
  end
```

VALUE may be the value of objective function (ascending, here) or heuristic cost (descending).

## Hill-Climbing - 8-puzzle

![](img/l4/figure31.png)

Heuristic cost $h=17$ for the state on the left, and $h=1$ for the state on the right.
$h=$ number of paris of queens attacking each other.

## Hill-climbing -cont.

"Like climbing Everest in thick fog with amnesia."

![](img/l4/figure32.png)

## Hill-Climbing

![](img/l4/figure33.png)
**Properties**

- Greedy: always moves to states with immediate benefits, (i.e., $\uparrow$ evals).
- Quick on smooth landscapes.
- Easily gets stuck on rough landscapes (e.g., the 8-puzzle state with $h=1$ in the previous slides.)

## Simulated Annealing (SA)

![](img/l4/figure34.png)
**Properties**

- Hill-climbing with _jiggle._
- SA's **temperature** parameter regulates amount of jiggle: high early in search, then gradually decreasing.
- Jiggle allows traversal of chasms and plateaus.

## Simulated Annealing

Idea: escape local maxima by allowing some "bad" moves
**but gradually decrease their size and frequency**

```
function SIMULATED-ANNEALING(problem,schedule) returns a solution state
  inputs: problem, a problem
          schedule, a mapping from time to "temperature"
  local variables: current, a node
                   next, a node
                   T, a "temperature" controlling prob. of downward steps

  current <-- MAKE-NODE(INITIAL-STATE[problem])
  for t <-- 1 to infinity do
    T <-- schedule[t]
    if T == 0 then return current
    next <-- a randomly selected successor of current
    Delta E <-- VALUE[next] - VALUE[current]
    if Delta E > 0 then current <-- next
    else current <-- next only with probability e^{Delta E / T}
```

## Local beam search

**Idea:** keep $k$ states instead of $1;$ choose top $k$ of all their successors

Not the same as $k$ searches run in parallel!
Searches that find good states recruit other searches to join them

**Problem:** quite often, all $k$ states end up on same local hill

**Idea:** choose $k$ successors randomly, biased towards good ones

Observe the close analogy to natural selection!

## Genetic algorithms

- A successor state is generated by combining two parent states
- Start with $k$ randomly generated states (population)
- A state is reprsented as a string over a finite alphabet (often a string of 0s and 1s)
- Evaluation function (fitness function). Higher values for better states.
- Produce the next generation of states by selection, crossover, and mutation

Example: 8-queens

![](img/l4/figure35.png)

Fitness function (i.e., objective fn): number of non-attacking pairs
Selection: Probability of being regenerated in the next generation

## Genetic algorithms contd.

GAs require states encoded as strings (GPs use programs)

Crossover helps **iff substrings are meaningful components**

![](img/l4/figure36.png)

## Summary

# Lecture 5 - Adversarial Search <a name="c5"></a>

## Adversarial Search

- Adversiarial search problems are searches in multiagent environments.
- The agent needs to consider:
  - The possible actions of other agents
  - How these actions can affect its own welfare.

## Single agent vs. multiagent environments

- Agents may interact
  - compete
  - collaborate
- AI game theory is often concerned with a specific subset of games:
  - **Deterministic** - Outcome of any action is certain and consistent.
  - **Turn-taking** - Each player takes one turn each per round
  - **Two-player** - Only two players involved...
  - **Zero-sum** - The total losses and gains of both agents sums to zero.
  - **Perfect information** - All participants have full knowledge about their cost and utility functions and game history.

![](img/l5/figure1.png)
![](img/l5/figure2.png)

## Example: Nim

- Game rule: there are $x$ number of objects - e.g., fruits - and each player picks up and eats either one or $2$ fruits on their turn. The player that eats the last one wins.
- Perfect information, 2-player, Deterministic, Zero-sum, Turn-taking.
- We can represent the game as a tree and do search

![](img/l5/figure3.png)

## Example: Tic-tac-toe

![](img/l5/figure4.png)
Problem/question: What is the best strategy to win?
In tic-tac-toe when both players play optimally, neither player will win.

## Games vs. search problems

- We call the two players: MAX and MIN
- MAX wants to reach a state with maxmimum value
- MIN wants to reach a state with minimum value
- The player we want to win starts the game (MAX)

## The Game Tree

- In games the search tree is a tree where at each alternating level one of the players has the control/decisions.
- One move involves a decision from each player. Each player decision is called a ply.
- Each leaf in the search tree is assigned a utility value - often:
  - +1 = win
  - -1 = lose
  - 0 = draw
- We assume that the opponent is "unpredictable" $\implies$ **solution** is a **strategy** specifying a move for every possbile opponent reply.

## Let's define the optimal game strategy!

The optimal strategy is one that leads to outcomes **at least as good** as any other strategy when playing an **infallible** opponent.

## The minimax value

The MiniMax value of a node (MINIMAX$(n)$) is the **utility** for MAX of being in the corresponding state, assuming that both players optimally from there on to the end of the game.

- In **terminal states** the minimax value is just the utility of that state.
- If given a choice, MAX will always move to a state with maximum value.
- MIN will always move to a state with minimum value.
  $$
  \text{MINIMAX}(n)=\begin{cases}
  \text{UTILITY}&\quad\text{if TERMINAL-TEST}(s)\\
  max_{a\in\text{Actions}(s)}{\text{MINIMAX}(s,a)}&\quad\text{if PLAYER}(s)=\text{MAX}\\
  min_{a\in\text{Actions}(s)}{\text{MINIMAX}(s,a)}&\quad\text{if PLAYER}(s)=\text{MIN}
  \end{cases}\tag{1}
  $$

## Minimax adversarial search algorithm

![](img/l5/figure5.png)

## Basis Process of Adversarial Search

- From the start state, generate a search tree in a depth-first manner, alternating between own (computer) and opponent's possible moves.
- Only use heuristics/eval functions to evaluate the promise of the bottom-level nodes; then propagate values upwards, combining them using MAX and MIN operators.
- Return to the root and choose the action $A_\text{best},$ leading to the highest-rated child state, $S_\text{best}.$
- Apply $A_\text{best}$ to the current game state, producing $S_\text{best}$. Wait for the opponent to choose an action, which then produces the new game state, $S_\text{new}.$
- Now from $S_\text{new}$ node choose and apply the action that leads to the highest-rated child state.

## Minimax algorithm

Adversarial analogue of DFS

```
function MINIMAX-DECISION(state) returns an action
    inputs: state, current state in game

    return the a in ACTIONS(state) maximizing MIN-VALUE(RESULT(a, state))
```

```
function MAX-VALUE(state) returns a utility value
    if TERMINAL-TEST(state) then return UTILITY(state)
    v <-- negative infinity
    for a, s in SUCCESSORS(state) do v <-- MAX(v, MIN-VALUE(s))
    return v
```

```
function MIN-VALUE(state) returns a utility value
    if TERMINAL-TEST(state) then return UTILITY(state)
    v <-- positive infinity
    for a, s in SUCCESSORS(state) do v <-- MIN(v, MAX-VALUE(s))
    return v
```

## Minimax example

![](img/l5/figure6.png)

## Properties of minimax

- **Complete:** Only if tree is finite
- **Optimal:** Yes, against an optimal opponent,
- **Time complexity:** $O(b^m)$
- **Space complexity:** $O(bm)$ (depth-first exploration)

For chess, $b\approx35,m\approx100$ for "reasonable" games
$\implies$ exact solution completely infeasible

But do we need to explore every path?

## Alpha-Beta Pruning

![](img/l5/figure7.png)

## Alpha and Beta

**Alpha**

- A modifiable property of a MAX node.
- Indicates the lower bound on the evaluation of that MAX node.
- Updated whenever a LARGER evaluation is returned from a child MIN node.
- Used for pruning at MIN nodes.

**Beta**

- A modifiable property of a MIN node.
- Indicates the upper bound on the evaluation of that MIN node.
- Updated whenever a SMALLER evaluation is returned from a child MAX node.
- Used for pruning at MAX nodes.

Both alpha and beta are passed between MIN and MAX nodes.

## The $\alpha$-$\beta$ algorithm

```
function ALPHA-BETA-SEARCH(state) returns an action
    v <-- MAX-VALUE(state, negative infinity, positive infinity)
    return the action a in ACTIONS(state) with value v
```

```
function MAX-VALUE(state, alpha, beta) returns a utility value
    inputs: state, current state in game
            alpha, the value of the best alternative for MAX along the path to state
            beta, the value of the best alternative for MIN along the path to state

    if TERMINAL-TEST(state) then return UTILITY(state)
    v <-- negative infinity
    for each a in ACTIONS(state) do
        v <-- MAX(v, MIN-VALUE(s, alpha, beta))
        if v >= beta then return v
        alpha <-- max(alpha, v)
    return v
```

```
function MIN-VALUE(state, alpha, beta) returns a utility value
    inputs: state, current state in game
            alpha, the value of the best alternative for MAX along the path to state
            beta, the value of the best alternative for MIN along the path to state

    if TERMINAL-TEST(state) then return UTILITY(state)
    v <-- positive infinity
    for each a in ACTIONS(state) do
        v <-- MIN(v, MIN-VALUE(s, alpha, beta))
        if v <= alpha then return v
        beta <-- min(beta, v)
    return v
```

## A moment in MAX node's life

![](img/l5/figure8.png)

## A moment in MIN node's life

![](img/l5/figure9.png)

## $\alpha$-$\beta$ pruning example

![](img/l5/figure10.png)

## Properties of $\alpha$-$\beta$

- Pruning **does not** affect final result
- Good move ordering improves effectiveness of pruning
- Which nodes can be pruned in the following example:

![](img/l5/figure11.png)

With "perfect ordering," time complexity = $O(b^{m/2})$
$\implies$ **doubles** solvable depth

A simple example of the value of reasoning about which computations are relevant (a form of **metareasoning**)

Unfortunately, $35^{50}$ (e.g., chess) is still impossible!

## Resource limits

Standatd approach:

- Use CUTOFF-TEST instead of TERMINAL-TEST
  - e.g, depth limit
- Use EVAL instead of UTILITY
  - i.e., a heuristic evaluation function that estimates desirability of position

## Evaluation Functions

A evaluation function returns an estimate of the expected utility of the game in a given position. An inaccurate evaluation function can guide agent into horrible states.

Properties of a good evaluation function:

- It should order terminal states the same way as the true utility function.
- Computation must not take too long (that's the whole point remember).
- For non-terminal states, the evaluation function should be strongly correlated with the true chance of winning.

![](img/l5/figure12.png)

For chess, typically linear weighed sum of features

$$\text{Eval}(s)=w_1f_1(s)+w_2f_2(s)+\dots+w_nf_n(s)$$

e.g., $w_1=9$ with
$$f_1(s)=\text{(number of white queens)}-\text{(number of black queens)},\quad\text{etc.}$$

## Digression: Exact values don't matter

![](img/l5/figure13.png)

Behaviour is preserved under any **monotonic** transformation of EVAL

## Deterministic games in practise

- **Checkers:** Chinook ended 40-year-reign of human world champion Marion Tinsley in 1994. Used an endgame database defining perfect play for all positions involving 8 or fewer pieces on board, a total of $443,748,401,247$ positions.
- **Chess:** Deep Blue defeated human world champion Gary Kasparov in a six-game match in 1997. Deep Blue searches 200 million positions per second, uses very sophisticated evaluation, and undisclosed methods for extending some lines of search up to 40 ply.
- **Othello:** human champions refuse to compete ageaint computers, who are too good.
- **Go ($b>300$):** human champions refused to compete against computers, who were too bad - until 2015. In 2017 Future of Go Summit, AlphaGo beat Ke Jie, the world No. 1 ranked player at the time.

## Stochastic (nondeterministic) games

In stochastic games, chance introduced by dice, card-shuffling etc.
We use chance nodes to represent chance in stochastic games:

- Each branch represents a possible outcome (6 branches for a dice).
- Branches are labelled with the associated probability (1/6 for dice).

## Stochastic games in general

Simplified example with coin-flipping:

![](img/l5/figure14.png)

## Algorithms for nondeterministic games

EXPECTIMINIMAX gives perfect play.
Just like MINIMAX, except we must also handle chance nodes:

```
...
if state is a MAX node then
    return the highest EXPECTIMINIMAX-VALUE of SUCCESSORS(state)
if state is a MIN node then
    return the lowest EXPECTIMINIMAX-VALUE of SUCCESSORS(state)
if state is a chance node then
    return sum of ... EXPECTIMINIMAX-VALUE of SUCCESSORS(state)
alternative: ...
```

## Digression: Exact values DO matter

![](img/l5/figure15.png)

EVAL should be proportional to the expected payoff.

## Summary

Games are fun to work on! (and dangerous)

They illustrate several important points about AI

- perfection is unattainable $\implies$ must approximate
- good idea to think about what to think about
- uncertaintiy constraints the assignment of values to states

Games are to AI as grand prix racing is to automobile design.

# Lecture 6 - Constraint Satisfaction Problems <a name="c6"></a>

## What is a constraint satisfaction problem

**Example:** $N$-queen problem

![](img/l6/figure1.png)

Place $N$ queens on an $N\times N$ chess board with the constraint that they don't attack each other.

## 8-queen problem

Solution to the 8-queen problem?

![](img/l6/figure2.png)

There are $92$ different solutions.

## How would you solve the $N$-queen problem?

Humans solve this problem

- by experimenting with different configurations.
- using various insights about the problem to explore only a small number of configurations before they find an answer.
- However, it would be hard for humans to solve a $1000$ Queen problem!

We need computer-specific methods for solving such a problem.

## Method: Try every configuration systematically?

![](img/l6/figure3.png)

Although computers are good at trying many small things quickly

- for the 4-quuen problem there are 256 configurations
- 16,777,216 configurations for $8$-queen problem, and
- ...
- there are $N^N$ configurations for $N$-Queens.
- still too much time for the modern machines.

## Good news

- We notice that in, e.g., the $4$-Queens problem, as soon as we place some of the queens we know that an entire addtional set of configurations are invalid.
- This is the rationale behind the methods for solving CS problems.
- $N$-queen problem is an instance of a generic problem class and we want to design algorithms that solve this type of problems.

![](img/l6/figure4.png)

## Example: Map-Coloring

![](img/l6/figure5.png)

**Task/problem:** colour this map using $3$ colours with the **constraint:** adjacent regions must have different colours.

## CSP in real-world

- Assignment problems
  - e.g., who teaches what class
- Timetabling problems
  - e.g., which class is offered when and where?
- Hardware configuration
- Transportation scheduling
- Factory scheduling
- etc.

## CSP definition, components

- A Constraint Satisfaction Problem (CSP) is defined through $3$ components:
  - A set of **variables**
  - A set of **values**
  - A set of **constraint** between variables
- A CSP solving algorithm should assign a value to each variable that satisfies all the constraints.

## Example: Map-Coloring

![](img/l6/figure5.png)

- Variables: $\{WA,NT,Q,NSW,V,SA,T\}$
- Domain: {red, green, blue}
- Constraints: adjacent regions must have different colors, e.g., $WA\ne NT$ (if the language allows this), or
  $$(WA,NT)\in\{(red,green),(red,blue),(green,red),(green,blue),\dots\}$$

## Varieties of constraints

- Unary constraints involve a single variable,
  - e.g., $SA\ne green$
- Binary constraints involve pairs of variables,
  - e.g., $SA\ne WA$
- Higher-order constraints involve $3$ or more variables,
  - e.g., Sudoku
- Preferences (soft constraints), e.g., red is better than green often representable by a cost for each variable assignment
  - $\rightarrow$ constrained optimization problems

## What is a Solution?

![](img/l6/figure6.png)

**Solutions** are assignments satisfying all constraints, e.g.,

$$\{WA=red,NT=green,Q=red,\\NSW=green,V=red,SA=blue,T=green\}$$

## Visualization of CSP - Constraint graph

**Constraint graph:** nodes are variables, arcs shows constraints, e.g., in the following figure: WA and NT cannot take the same value.

![](img/l6/figure7.png)

**Basic problem:** Find a $d_i\in D$ for each variable $V_i$ such that all constraints are satisfied, i.e., find consistent values for variables.

## Approaches to Solving CSPs

- Incremental Search - Backtracking
- Inference, e.g., Forward Checking, Arc consistency
- Backtracking with inference, e.g., with Forward Checking
- Local Search

## CSP as a Standard Search problem

States are defined by the values assignes so far

- **Initial state:** the empty assignment, $\{\}$
- **Successor function:** assign a value to an unassigned variable that does not conflict with current assignment.
  - $\implies$ fail if no legal assignments (not fixable!)
- **intermediate states:** partial assignment of variables
- **Goal test:** the current assignment is complete and consistent

## Backtracking search

- Variable assignments are **commutative**, i.e.,
  - [$WA=red$ then $NT=green$] same as [$NT=green$ then $WA=red$]
- Backtracking employs **Depth-first search** for CSPs with single-variable assignments
- Backtracking search is the basic uninformed algorithm for CSPs
- Only need to consider assignments to a single variable at each node
  - $\implies b=d$ and there are $d^n$ leaves

Can solve $n$-queens for $n\approx25$

```
function BACKTRACKING-SEARCH(csp) returns solution/failure
    return RECURSIVE-BACKTRACKING({}, csp)

function RECURSIVE-BACKTRACKING(assignment, csp) returns soln/failure
    if assignment is complete then return assignment
    var <-- SELECT-UNASSIGNED-VARIABLE(VARIABLES[csp], assignment, csp)
    for each value in ORDER-DOMAIN-VALUE(var, assignment, csp) do
        if value is consistent with assignment given CONSTRAINTS[csp] then
            add {var = value} to assignment
            result <-- RECURSIVE-BACKTRACKING(assignment, csp)
            if result != failure then return result
            remove {var = value} from assignment
    return failure
```

## Example - Backtracking

![](img/l6/figure8.png)
![](img/l6/figure9.png)
![](img/l6/figure10.png)

## Improving backtracking efficiency by Heuristics

- Previously we talked about heuristics for improvement of uninformed search
- This time heuristics are NOT domain-specific though
- For CSP, general-purpose methods can give huge gains in speed:
  - Which variable should be assigned next?
  - In what order should its values be tried?
  - Can we detect inevitable failure early?
  - Can we take advantage of problem structure?

## Order of variables

The choice of variable to be assigned next makes a difference.

![](img/l6/figure11.png)

- Assume now this static order, WA, NT, Q, NSW, V, SA, T, and then these 2 assignments: WA = RED, NT = GREEN.
- Q would be default next selection. But is it a good choice... After WA and NT are assigned? Problem for SA?

## Minimum remaining values (MRV) heuristic

Which variable should be assigned next?

![](img/l6/figure7.png)

- **Minimum remaining values (MRV) heuristic:** choose the variable with the fewest legal values
- Also called "most constrained variable" or "fail first" heuristic
- Objective: detect immediately if variable has no legal values (left) or most likely to cause a failure soon

![](img/l6/figure12.png)

## Degree heuristic

Which variable should be assigned next?

- Does MRV help in the very beginning?
- **Degree heuristic:** choose the variable with the most constraints on remaining variables.
- Objective: reduce the future branching on future choices
- Tie-breaker among MRV variables

![](img/l6/figure11.png)

## What order should its values be tried?

- Heuristic for decision on value ordering.
- Given a variable, choose the **least constraining value:** the one that rules out the fewest values in the remaining variables
- Objective: make more likely to find a solution early

![](img/l6/figure13.png)

Combining these heuristics makes $1000$ queens feasible

## Inference in CSP

- A specific type of inference called **constraint propagation** - node consistency, arc consistency, path consistency, $K$-consistency, forward cheking (restricted arc consistency)
- Objective: reduce legal values for a variable using constraints
- Reduction in legal values of a variable in turn reduces legal values of another variable...

## Improving Backtracking search through Inference

- It is possible to discover the unpromising nodes by inference for consistency
- Arc-consistency can be used during search, however time consuming
- Another possible type of inference is **Forward Checking** of consistency
- Backtracking search can be pruned by applying Forward checking
- Forward checking:
  - is simpler than Arc consistency, checks only the direct neighbours
  - keep track of remaining legal values for unassigned variables
  - checks "future" rather than "past" which is what backtracking does.

## Backtracking with Forward Checking

- During search, assume assignment of a value to the next variable and check if it reduces the domain of its neighbours.

**Idea:** Keep track of remaining legal values for unassigned variables
**Idea:** Terminate search when any variable has no legal values

## Example: Backtracking with Forward Checking

![](img/l6/figure14.png)
![](img/l6/figure15.png)
![](img/l6/figure16.png)

## Forward checking example in the book

**Idea:** Keep track of remaining legal values for unassigned variables
**Idea:** Terminate search when any variable has no legal values
![](img/l6/figure17.png)
![](img/l6/figure18.png)
![](img/l6/figure19.png)
![](img/l6/figure20.png)

## Inference - Arc consistency

**Arck consistency** eliminates the values from the domains of variables that can not be part of a solution

An arc $V_i\rightarrow V_j$ is consistent if

$\forall x\in D_i\exists y\,D_j$ such that $(x,y)$ is allowed by the constraint on the arc.

We can obtain arc consistency by removing values from the domains of the variables that fail the constraint.

## Arc consistency algorithm

```
function AC-3(csp) returns false if an inconsistency is found and true otherwise
    inputs: csp, a binary CSP with variables {X_1, X_2, ..., X_n}
    local variables: queue, a queue of arcs, initially all the arcs in csp

    while queue is not empty do
        (X_i, X_j) <-- REMOVE-FIRST(queue)
        if REMOVE-INCONSISTENT-VALUES(X_i, X_j) then
            for each X_k in NEIGHBOURS[X_i] do
                add (X_k, X_i) to queue
    return true
```

```
function REMOVE-INCONSISTENT-VALUES(X_i, X_j) returns true iff succeeds
    removed <-- false
    for each x in DOMAIN[X_i] do
        if no value y in DOMAIN[X_j] allows (x, y) to satisfy the constraint X_i <-> X_j
            then delete x from DOMAIN{X_i}; removed <-- true
    return removed
```

## Arc Consistency - Example

Three variables, V1, V2, V3, and their initial domains. Values within each node show the initial domains of the variables.

![](img/l6/figure21.png)

- A binary constraint (e.g., DIFF(V1, V2)) can be satisfied through checking 2 arcs, e.g. V1V2 and V2V1.
- ALl arcs are checked for consistency, e.g., according to algorithm AC-3

![](img/l6/figure22.png)
![](img/l6/figure23.png)

- For the arc V1-V2: check if there is a value in the domain of V2 for each value of V1 (i.e., R, G, B)
- For the arc V2-V1: check if there is a value in the domain of V1 for each value of V2 (i.e., R, G)

![](img/l6/figure24.png)
![](img/l6/figure25.png)

We stopped when there is no more changes.

## Arc Consistency

If one of the Domains become empty: there is no solution to the problem

ELSE: Arc consistency is required for existence of a solution - i.e., no empty domains

BUT: Is Arc consistency sufficient to find a solution?

## Arc Consistency - Example

Is this graph Arc-consistent?
Solution?

![](img/l6/figure26.png)

MESSAGE: SEARCH may be necessary to find a solution

PS! However, sometimes Arc-consistency alone may find the solution.

## Arc Consistency for Map Coloring

Forward checking propagates information from assigned to unassigned variables, but doesn't provide early detection for all failures:

![](img/l6/figure27.png)

$NT$ and $SA$ cannot both be blue!

Arc consistency repeatedly enforces constraints locally

![](img/l6/figure27.png)

Simplest form of propagation makes each arc consistent

$X\rightarrow Y$ is consistent iff
for each value $x$ of $X$ there is some allowed $y$

![](img/l6/figure28.png)
![](img/l6/figure29.png)
![](img/l6/figure30.png)
![](img/l6/figure31.png)

If $X$ loses a value, neighbors of $X$ need to be rechecked
Arc consistency detects failure earlier than forward checking
Can be run as a preprocessor or after each assignment

## Local search applied to CSP

- Iterative
- Generate complete assignments: assume/guess a value for each variable.
- Evaluate the assignments w.r.t. violated contraints.
- Modify the assignments to reduce the numbers of violations.

## Local search with heuristic

To apply CSPs:

- allow states with unsatisfied constraints
- operators **reassign** variable values

Variable selection: randomly select any conflicted variable

Value selection: by **min-conflicts** heuristic:
choose value that violates the fewest constraints
i.e., hillclimb with $h(n)=$ total number of violated constraints

The local search strategies (e.g., hill-climbinb, simulated annealing) in # Lecture 4 are candidates for use in CSP. <a name="c4"></a>

## Solving K-Queens with _Dumb_ Local Search

![](img/l6/figure32.png)

## Min Conflicts: Local Search with Intelligence

![](img/l6/figure33.png)

- Moving queen to column of least violations $\rightarrow$ intelligent successor generation.
- Integers denote number of violations if queen moved there.

## Problem structure

![](img/l6/figure7.png)

Tasmania and mainland are **independent subproblems**

Identifiable as **connected components** of constraint graph

## Graph structure and problem complexity

![](img/l6/figure7.png)

- Solving disconnected subproblems
  - Suppose each subproblem has $c$ variables out of a total of $n.$
  - Worst case solution cost is $O(n/c\,d^c),$ i.e. linear in $n$
    - Instead of $O(d^n),$ exponential in $n$
- E.g. $n=80, c=20, d=2$
  - $2^{80}=4$ billion years at $1$ million nodes/sec.
  - $4*2^{20}=.4$ second at $1$ million nodes/sec.

![](img/l6/figure34.png)

- Theorem:
  - if a constraint graph has no loops then the CSP can be solved in $O(nd^2)$ time
  - linear in the number of variables
- Compare difference with general CSP, where worst case is $O(d^n)$

# Lecture 7 - Logical Agents <a name="c7"></a>

## Knowkedge-based agents

- **Knowledge base (KB):** A set of sentences that describe facts about the world in some formal (representational) language
- **Inference engine:** A set of procedures that use the representational language to infer new facts from known ones as well as to answer a variety of KB queries.

![](img/l7/figure1.png)

## Operation on the Knowledge base

Two important operations on the KB:

- add new knowledge to KB
- ask questions about the knowledge in KB. Questions are "asked"/triggerred in two ways:
  - a direct question from the user that doesn't require reasoning but just **retrieval** from the KB
  - a question representing a lack of knowledge required to solve a problem. This knowledge is implicit in the KB and need to be **inferred.**

## Inference and Retrieval

- What does it happen in your mind when you are asked this question?
  - Question: Is Stockholm in Sweden?
- What does it happen in your mind when you are asked this question?
  - Question: Does a vegan person eat snail?
- Different?

## A simple knowledge based agent

- Knowledge base = set of **sentences** in a **formal** language
- Declarative approach to building an agent (or other system):
  - **Tell** it what it needs to know
  - Then it can **Ask** itself what to do - answers should follow from KB

```
function KB-AGENT(percept) returns an action
    static: KB, a knowledge base
             t, a counter, initially 0, indicating time

    TELL(KB, MAKE-PERCEPT-SENTENCE(percept,t))
    action <-- ASK(KB, MAKE-ACTION-QUERY(t))
    TELL(KB, MAKE-ACTION-SENTENCE(action, t))
    t <-- t + 1
    return action
```

## Remember the Wumpus' Cave

![](img/l7/figure2.png)

## Wumpus World PEAS description

![](img/l7/figure3.png)
![](img/l7/figure4.png)

## First movement

![](img/l7/figure5.png)

- Knowledge Base: Rules of game/environment
- Location (always starts at): $[1,1]$
- Percept: $[\neg Stench, \neg Breeze, \neg Glitter, \neg Bump, \neg Scream]$
- Action: Move forward to cell $[2,1].$ Outcome: Location $[2,1]$
- New Percept: $[\neg Stench, Breeze, \neg Glitter, \neg Bump, \neg Scream]$
- Infer: There must be a pit in $[2,2]$ or $[3,1]$
- Action: Return to $[1,1]$ to try next safe cell.

## Next move

![](img/l7/figure6.png)

- Location: after move action - from $[1,1]$
- Percept: $[Stench, \neg Breeze, \neg Glitter, \neg Bump, \neg Scream]$
- Infer: Can there be a Wumpus in $[2,2]$ Why/not?
  - Remember - what is already in the KB?
- Action: Move to $[2,2]$
- Percept:
- In the knowledge base: Pit in $[2,2]$ or $[3,1]$
- Pit in $[3,1]!$

## How to tell a machine to play the Wumpus game?

- How to reprsent the knowledge into the agent?
- How does the agent do the inference based on built knowledge?
- **We need a knowledge reprsentation language.**
- The objective of knowledge representation is to express the knowledge about the world in a computer-tractable form
- Various Knowledge Representation Languages

## Physical World and Internal Representations

![](img/l7/figure7.png)

## Computers and logic

- Computers can use logic in order to, e.g.m prove mathematical theorems and to diagnose failures
- But, first what is logic and how it works.

![](img/l7/figure8.png)

## Propositional Logic

In this # Lecture we deal with **Propositional (Boolean) Logic.** <a name="cwe"></a>

## What is Logic

- One of the oldest disciplines in history
- Dates back to Aristoteles

![](img/l7/figure9.png)
![](img/l7/figure10.png)

## Please use logic all the time

- People use logic in order to talk about observations, to define concepts, and to formalize theories.
- People use logic to prove something.

![](img/l7/figure11.png)

- Using logical reasoning we can derive new information from what we already knew.

![](img/l7/figure12.png)
![](img/l7/figure13.png)

- We use logical proos to convince others of our conclusions..

![](img/l7/figure14.png)
![](img/l7/figure15.png)

## Syntax of Propositional Logic

Syntax - symbols, sentences

- Symbols (alphabet) consists of:
  - Constants: True, False
  - Propositon symbols: P, Q, ...
  - Connectives: $\wedge,\vee,\neg,\rightarrow,\Leftrightarrow$
- Sentences can be atomic (constants and propositions) or compound sentences

## Syntax

![](img/l7/figure16.png)

## Atomic Sentences

- **Proposition:** a declarative statement about the world that is either true or false
- Which of the followings are propositions:
  - Norway is in Europe.
  - Stockholm is capital city of Norway.
  - What is your name?
  - Do your homework.
  - This sentence if false.

## Which of the following are propositions?

- Norway is in Europe (true).
- Stockholm is capital city of Norway (false).
- What is your name? (not declarative)
- Do your homework (not declarative).
- This sentence if false (neither true nor false).

## Compound Sentences

- Compound sentences: constructed from atomic and/or other compound sentences via connnectives:
  - If $S$ is a sentence, $\neg S$ is a sentence (negation)
  - If $S_1$ and $S_2$ are sentences, $S_1\wedge S_2$ is a sentence (conjunction)
  - If $S_1$ and $S_2$ are sentences, $S_1\vee S_2$ is a sentence (disjunction)
  - If $S_1$ and $S_2$ are sentences, $S_1\implies S_2$ is a sentence (implication)
  - If $S_1$ and $S_2$ are sentences, $S_1\Leftrightarrow S_2$ is a sentence (biconditional)

## Example - Compound Sentences

Assume the following propositions:

- $P:$ It is sunny this afternoon.
- $Q:$ It is colder than yesterday.
- $Lg:$ The traffic light is green.
- $Cg:$ The cars will go.

How are the following compound sentences be represented in terms of the proposition symbols above?

1. It is not sunny this afternoon and it is colder than yesterday.
2. If the traffic light is green then the cars will go.
3. The cars will go only if traffic light is green.

Representations of these sentences in propositional logic:

1. $\neg P\wedge Q$
2. $Lg\implies Cg$
3. $Cg\implies Lg$

## Semantics in Propositional Logic

Semantics of **atomic** sentences are determined according to their truth values wrt interpretations.

An **interpretation** maps symbols to one of the two values: True $(T)$, or False $(F)$, depending on whether the symbol is **satisfied** in the "world":

- $P:$ Light in the room is on _(True in Interpretation $I$)_ then Value$(P,I)=$ True.
- $Q:$ It rains outside (False) then Value$(Q,I)=$ False.
- If $P:$ Light in the room is on (False in $I'$) then Value$(P,I')=$ False.

## Semantics of Connectives

Semantics of **compositional** sentences are determined using the standard rules of logic for connectives:

![](img/l7/figure17.png)

## Inference in propositional logic

How to desgin the procedure that answers $KB\models\alpha?$

**Inference methods in propositional logic:**

- Model checking/enumeration
- Inference algorithms
  - Resolution and Proof by Contradiction
  - Forward and Backward chaining

## Semantics of Inferring new information

- The logical agent can use the sentences in the Knowledge Base to draw conclusions that are **logically entailed** by those sentences. Entailment is obtained in different ways in different inference methods.

## Entailment: A key semnatic relationship

- Entailment means that the truth of one sentence $(\alpha)$ follows from the truth of another (e.g., set of all sentences in $KB$)
- $KB\models\alpha$ ($KB$ entails $\alpha$) if and only if $M(KB)\subseteq M(\alpha)$
- Example:
  - $KB=$ "RBK won" and "Brann won"
  - $\alpha=$ "RBK won"

**Entailment is a relationship between sentences based on semantics**

## Model and Model checking

**Model:** We say $m$ is a model of a sentence $\alpha$ if $\alpha$ is true in $m$

$KB=$ "RBK won" and "Brann won"
$\alpha=$ "RBK won"

![](img/l7/figure18.png)

$M(\alpha)$ is the set of all models of $\alpha$

## Example: Wumpus gridworld

Propositional representation of Wumpus gridworld.

- Rules of Wumpus game and representation of a game.
- Let $P_{i,j}$ be true if there is a pit in $[i,j].$
- Let $B_{i,j}$ be true if there is a breeze in $[i,j].$
- "Pits cause breezes in adjacent squares" = "A square is breezy **if and only if** there is an adjacent pit"
- KB = wumpus-world rules + observations

## Wumpus world after the first 2 moves

- Situations after detecting nothing in $[1,1]$ and moving right, breeze in $[2,1]:$
  - $R_1:\neg P_{1,1}$
  - $R_2:B_{1,1}\leftrightarrow(P_{1,2}\vee P_{2,1})$
  - $R_3:B_{2,1}\leftrightarrow(P_{1,1}\vee P_{2,2}\vee P_{3,1})$
  - $R_4:\neg B_{1,1}$
  - $R_5:\neg B_{2,1}$
- $KB=R_1\wedge R_2\wedge R_3\wedge R_4\wedge R_5$

## Models in reduced Wumpus gridworld

Consider possbiel models for $KB$ assuming only pits and a **reduced** Wumpus world with only 5 squares and pits:

![](img/l7/figure19.png)

## Wumpus Models

The reduced Wumpus World. All 8 possible worlds/models are:

![](img/l7/figure20.png)

## Decision in Wumpus world by Model Checking

Still reduced Wumpus gridworld example.

![](img/l7/figure21.png)

## Model Checking through Truth Tables

Truth Table is a simple method for model enumeration and checking.

![](img/l7/figure22.png)

- $M[(A\wedge B\rightarrow C)\wedge(A\wedge B)]=\{7\}\subseteq\{1,3,5,7\}=M(C).$
- Yes

## Example: Model enumeration in Wumpus world

- After visiting $(1,1)$ and $(2,1)$
  - $R_1:\neg P_{1,1}$
  - $R_2:B_{1,1}\leftrightarrow(P_{1,2}\vee P_{2,1})$
  - $R_3:B_{2,1}\leftrightarrow(P_{1,1}\vee P_{2,2}\vee P_{3,1})$
  - $R_4:\neg B_{1,1}$
  - $R_5:B_{2,1}$
- $KB=R_1\wedge R_2\wedge R_3\wedge R_4\wedge R_5$
- In this Wumpus world: 7 symbols (in $KB$). We can get $2^7=128$ models.

![](img/l7/figure23.png)

- Answer: $KB\models\neg P_{1,2}$. No pit in $P_{1,2}.$

## Inference by Model Enumeration

- Enumeration is sound and complete
- The truth table is exponential in the number of propositional symbols (we checked all rows/assignments)
- Model checking complexity:
  - If $KB$ and $\alpha$ contain $n$ symbols:
    - Time complexity: $O(2^n)$
    - Space complexity: $O(n)$
- **We need effective/smarter ways of doing inference**

## Inference Rules approach

- How to make the process more efficient?
- $KB$ is true on only a smaller subset
- **Solution:** check only entries for which $KB$ is True.
- That is, infer new logical sentences from the knowledge base and see if they match a query
- This is the idea behind the inference rules approach
- _Inference rules_ represent sound inference patterns repeated in inferences.

## Properties of an Inference Procedure and connection to Entailment

- Assume an **inference procedure** $i$ that
  - derives a sentence $\alpha$ from the $KB$, i.e. $KB\vdash_i\alpha$
- **Soundness:** An inference procedure is sound
  - If whenever $KB\vdash_i\alpha,$ then it is also true that $KB\models\alpha$

![](img/l7/figure24.png)

- **Completeness:** An inference procedure is complete
  - If whener $KB\models\alpha$ then it is also true that $KB\vdash_i\alpha$
- Sound and complete inference procedures are desirable

## Inference rules

![](img/l7/figure25.png)

## Some other inference rules

![](img/l7/figure26.png)

## Inference rules approach

- Inference rule approach: Apply an inference rule that matches with the knowledge in $KB.$ Do this until satisfying the query, e.g., $P_1.$
- Starting with a $KB$
  - ASK$(P_1):$ is $P_1$ true given what is in $KB?$
- Derive $P_1$ from the $KB$

1. Use inference rules to add new statements
2. Use **logical equivalence** (next slide) to rewrite existing statements

## Logical equivalence

Two sentences are **logically equivalent** iff true in same models:
$\alpha\equiv\beta$ if and only if $\alpha\models\beta$ and $\beta\models\alpha$

![](img/l7/figure27.png)

## Inference rules approach - Example

**KB:** $P\implies Q,Q\implies R$
**Question:** Does $KB\models(P\implies R)?$

Using Inference rules:

1. $P\implies Q$ (Premise)
2. $Q\implies R$ (Premise)
3. $P\implies (Q\implies R)$ (Implication Creation: 2)
4. $(P\implies Q)\implies(P\implies R)$ (Implication Distribution: 3)
5. $P\implies R$ (Modus Ponens: 4, 1)

## Problems with Inference rules approach

- There may be more than one rule that can apply at a certain stage.

![](img/l7/figure28.png)

- One solution: **Resolution** is a single inference rule that yields a complete inference algorithm

## Some definitions

- A sentence is **satisfiable** if it is true in **some** models
- A sentence is **unsatisfiable** if it is true in **no** models
  - e.g., $A\wedge\neg A$
- A sentence is **valid** if it is true in **all** models,
  - e.g., $True,A\vee\neg A,A\implies A,(A\wedge(A\implies B))\implies B$

## Connection to Inference

- **Validity** is connected to inference via the deduction theorem:
  - $KB\models\alpha$ if and only if $(KB\implies\alpha)$ is valid.
- Hence, $KB\models\alpha$ is true iff every interpretation that makes all $S\subseteq KB$ true, makes $\alpha$ true.
- **Satisfiability** is connected to inference via the following:
  - $KB\models\alpha$ if and only if $(KB\wedge\neg\alpha)$ is unsatisfiable
  - i.e., **prove** $\alpha$ by contradiction

## Proof by contradiction

- The inference rule called _Resolution Rule_ can be used for **proof by contradiction**
- Instead of showing $KB\models\alpha,$ we show that $KB\wedge\neg\alpha$ is not satisfiable.
- Disproving $KB,\neg\alpha$ proves the entailment $KB\models\alpha$

## Resolution Rule

![](img/l7/figure29.png)

## Resolution algorithm

Proof by contradiction, show $KB\wedge\neg\alpha$ unsatisfiable

```
function PL-RESOLUTION(KB, alpha) returns true or false
    inputs: KB, the knowledge base, a sentence in propositional logic
            alpha, the query, a sentence in propositional logic

    clauses <-- the set of clauses in the CNF representation of KB AND NOT alpha
    new <-- {}
    loop do
        for each C_i, C_j in clauses do
            resolvents <-- PL-RESOLVE(C_i, C_j)
            if resolvents contains the empty clause then return true
            new <-- new UNION resolvents
        if new subseteq clauses then return false
        clauses <-- claues UNION new
```

## Conjunctive Normal Form

However to apply resolution technique its required to represent $KB$ as well as any sentence $\alpha$ that we wish to derive in a special format known as **Conjunctive Normal Form** (CNF): conjunction of disjunctive clauses of literals

- Example: $(A\vee B)\wedge(\neg A\vee\neg C\vee D)$
- a **disjunctive clause** is a disjunction of literals.
- A clause is an expression of the form $I_1\vee I_2\dots I_k$ where each $I_i$ is a literal.
- a **literal** is either a propositional symbol or the negation of a symbol.
- A sentence can be converted to CNF for by using Logical Equivalences.

## Resolution (Refutation) for Wumpus problem

![](img/l7/figure30.png)

Our knowledge base:
$$(B_{1,1}\leftrightarrow(P_{1,2}\vee P_{2,1}))\wedge\neg B_{1,1}$$

Now, we want to verify that there is no pit in $[1,2].\,\alpha=\neg P_{1,2}$

$$KB\models\alpha?$$
For this, we need to show that $KB\wedge\neg\alpha$ is unsatisfiable.

## Remember the Logical Equivalences

![](img/l7/figure27.png)

## Resolution Refutation on Wumpus Example

$$
\begin{aligned}
KB&=(B_{1,1}\Leftrightarrow(P_{1,1}\vee P_{2,1}))\wedge\neg B_{1,1}\\
\alpha&=\neg P_{1,2}
\end{aligned}
$$

Applying the Logical Equivalences to $KB\wedge\neg\alpha$, we convert the $KB$ into CNF:
$$(\neg P_{2,1}\vee B_{1,1})\wedge(\neg B_{1,1}\vee P_{1,2}\vee P_{2,1})\wedge(\neg P_{1,2}\vee\neg B_{1,1})\wedge(\neg B_{1,1})\wedge(P_{1,2})$$

## Conversion to CNF

$$B_{1,1}\Leftrightarrow(P_{1,2}\vee P_{2,1})$$

1. Eliminate $\Leftrightarrow,$ replacing $\omega\Leftrightarrow\beta$ with $(\omega\implies\beta)\wedge(\beta\implies\omega).$
   $$(B_{1,1}\implies(P_{1,2}\vee P_{2,1}))\wedge((P_{1,2}\vee P_{2,1})\implies B_{1,1})$$
2. Eliminate $\implies,$ replacing $\omega\implies\beta$ with $\neg\omega\vee\beta.$
   $$(\neg B_{1,1}\vee P_{1,2}\vee P_{2,1})\wedge(\neg(P_{1,2}\vee P_{2,1})\vee B_{1,1})$$
3. Move $\neg$ inwards using de Morgan's rules and double-negation:
   $$(\neg B_{1,1}\vee P_{1,2}\vee P_{2,1})\wedge((\neg P_{1,2}\wedge\neg P_{2,1})\vee B_{1,1})$$
4. Apply distributivity law ($\vee$ over $\wedge$) and flatten:
   $$(\neg B_{1,1}\vee P_{1,2}\vee P_{2,1})\wedge(\neg P_{1,2}\vee B_{1,1})\wedge(\neg P_{2,1}\vee B_{1,1})$$

## RR process on Wumpus example

$$
\begin{aligned}
KB&=(B_{1,1}\Leftrightarrow(P_{1,1}\vee P_{2,1}))\wedge\neg B_{1,1}\\
\alpha&=\neg P_{1,2}
\end{aligned}
$$

![](img/l7/figure31.png)

## Problem with Resolution Refutation

- Resolution is complete but can be exponential in space and time.
- If we can reduce all clauses to a special form called **Horn Clauses**, deciding entailment becomes linear in the size of the knowledge base (KB)
- Inference with Horn clauses can be done through the **forward chaining** and **backward chaining** algorithms

## Horn Clauses

- Definite clause: Disjunction of literals of which exactly one is positive; the rest are negative
- Horn Clause: Disjunction of literals of which at most one is positive

![](img/l7/figure32.png)

## Forward and backward chaining

- **Modus ponens** is perfect for **Definite Clause** KBs
- Two inference procedures:
  - **Forward chaining** (data driven)
    - Idea: Whenever the premises of a rule are satisfied, infer the conclusion. Continue with rules that became satisfied.
  - **Backward chaining** (goal driven)
    - Idea: To prove the fact that appears in the conclusion of a rule prove the premises of the rule. Continue recursively.
  - Both procedures are complete for KBs in the Definite clause form.

Forward and Backward algorithms rely on the inference rule **Modus Ponens** (for definite clause Form):

![](img/l7/figure33.png)

## Forward chaining

Idea: fire any rule whose premises are satisfied in the $KB,$ add its conclusion to the $KB,$ until query is found

![](img/l7/figure34.png)

## Forward chaining example

![](img/l7/figure35.png)
![](img/l7/figure36.png)
![](img/l7/figure37.png)
![](img/l7/figure38.png)
![](img/l7/figure39.png)
![](img/l7/figure40.png)
![](img/l7/figure41.png)

## Backward chaning

Idea: work backwards from the query $q:$
to prove $q$ by BC,
check if $q$ is known already, or
prove by BC all premises of some rule concluding $q$

Avoid loops: check if new subgoal on the goal stack

Avoid repeated work: check if new suboal

1. has already been proved true, or
2. has already failed

## Backward chaining example

![](img/l7/figure42.png)
![](img/l7/figure43.png)
![](img/l7/figure44.png)
![](img/l7/figure45.png)
![](img/l7/figure46.png)
![](img/l7/figure47.png)
![](img/l7/figure48.png)
![](img/l7/figure49.png)
![](img/l7/figure50.png)
![](img/l7/figure51.png)

## Forward vs. backward chaining

FC is **data-driven**, cf. automatic, unconscious processing, e.g., object recognition, routine decisions

May do lots of work that is irrelevant to the goal

BC is **goal-driven**, appropiate for problem solving, e.g., Where are my keys? How do I get into a PhD program?

Complexity of BC can be **much less** than linear in size of KB.

# Lecture 8 - First Order Logic <a name="c8"></a>

## Pros and Cons of propositional logic

**PROS:**

- Propositional logic is declarative: pieces of syntax correspond to facts
- Propositional logic allows partial information (unlike most data structures and databases)
- Propositional logic is compositional: meaning of $B_{1,1}\wedge P_{1,2}$ is derived from meaning of $B_{1,1}$ and of $P_{1,2}.$
- Meaning in propositional logic is context-independent (unlike natural language, where meaning depends on context)

**CONS:**

- Propositional logic has very limited expressive power (unlike natural language)

## Limitations of propositional logic

- Some knowledge is hard or impossible to encode in the propositional logic.
- Two cases that are specially hard to represent:
  - Statements about similar objects, relations
  - Statements referring to groups of objects.

## Limitations of propositional logic - Example 1

- **Statements referring to groups of objects required to be enumerated**
- Example: Assume we want to express _Every student likes vacation:_
  - John likes vacation $\wedge$
  - Mary likes vacation $\wedge$
  - Ann likes vacation $\wedge$
  - ...
- **Problem:** KB grows large
- **Possible solution: ??**
- _All students like vacation._

## Limitations of propositional logic - Example 2

- Statements about similar objects and relations need to be enumerated
- Assume we have
  - Stig is older than Sissel
  - Sissel is older than Paul
  - Stig is older than Sissel $\wedge$ Sissel is older than Paul $\implies$ Stig is older than Paul
  - We can derive _Stig is older than Paul_
- Assume we add _Hanne is older than Sissel_ into the KB
- The current KB Now:
  - Stig is older than Sissel
  - Sissel is older than Paul
  - Stig is older than Sissel $\wedge$ Sissel is older than Paul $\implies$ Stig is older than Paul
  - Hanne is older than Sissel
- What else do we need to have in the KB in order to derive _Hanne is older than Paul?_
- We need:
  - Hanne is older than Sissel $\wedge$ Sissel is older than Paul $\implies$ Hanne is older than Paul
- **What is the problem?**
- **KB grows large**
- **Possible solution: ??**
- PersA is older than PersB $\wedge$ PersB is older than PersC $\implies$ PersA is older than PersC

## Limitations of Propsitional Logic - example 3: Wumpus

- Consider the statement "If there is breeze in a square, there must be pit in an adjacent square"
- In propositional logic we need 16 sentences (one for each square) to represent this statement (for $4\times4$ grid):
  - $B_{1,1}\implies P_{1,2}\vee P_{2,1}$
  - $B_{1,2}\implies P_{1,2}\vee P_{1,3}\vee P_{2,2}$
  - ...
  - ...
- **We want to be able to say this in one single sentence.**

## How to say it in one sentence

- Our statement above refers to $2$ types objects (pit and square). The square has the property to be breezy. The relationship between a square and pit is adjacency, i.e., neighbourhood.
- In FOL, this statement is represented by means of the following formula - instead of 16 sentences in propositional logic:

$$\forall square, adjacent(square,pit)\implies breezy(square)$$

## Saying and Inferring more

- People eat and drink in Solsiden
  - conclude: People drink in Solsiden
- Ingrid watched Game of Thrones
  - conclude: Somebody watched Game of Thrones
- Every bird can fly. Canary is a bird.
  - conclude: Canary can fly

## First Order Logic (FOL)

- More expressive than propositional logic. While PL assumes that the world contains facts, FOL assumes the world containts
  - Objects: trees, people, numbers, movies, Trump :orange:, maps, colours, hypotheses, Wumpus...
  - Relations: square, smelly, brother of, older than, ownsm, has colour, adjacent to...
  - Functions: brother-of, colour-of, adjacent-to, ...
- Representing objects, their properties, relations and statements about them.

## First-order Logic

Like, PL, FOL has:

- Syntax: symbols and rules for combining them - the grammar - What you can express
- Semtantics: How the sentences relate to the world - What it means
- Inference procedure: Rules for deriving new sentences from the ones in KB
  - Reasoning

## Syntax of FOL - elements

- Constants: NTNU, KingHarald, 5, ...
- Predicates: Brother, >, -, ...
- Functions: Sqrt, LeftLegOf
- Variables: x, y, a, b, ...
- Connectives: $\neg, \wedge, \vee, \rightarrow, \leftrightarrow$
- Quantifiers: $\forall, \exists$
- First order logic or "predicate calculus" introduces **variables** and **quantifiers** to refer to objects in the world, their relations, group of objects, and to express general rules.

## Atomic Sentences

- Atomic sentence: predicate(term$_1$,...,term$_n$)
- Term: constant, or variable or function(term$_1$,...,term$_m$)

## Complex sentences

- Composed of atomic sentences using connectives
  $$\neg S_1, S_1\vee S_2, S_1\wedge S_2, S_1\implies S_2, S_1\Leftrightarrow S_2$$
- Examples:
  - Brother(JonSnow, AryaStark) $\implies$ Sister(AryaStark, JonSnow)
  - Childish(Trump) $\vee$ BestStudents(Students(NTNU), Norway)

## Functions versus Relations

- Functions are a way of referring to individuals indirectly, e.g., - brother-of(Janne) and Edvard would refer to the same object(individual) if Janne's brother is the person name Edvard.
- Relations hold among objects:
  - brother(Janne,Edvard) is true of Edvard is Janne's brother

## Predicates

- A relation is the set of tuples of objects
  - Brotherhood relationship (Richard, John), (John, Richard)
  - Unary, binary, $n$-ary relations
- set of blocks a, b, c, d, e. The "On" relation included:
  - On = $(a,b),(b,c),(d,e)$
  - the predicate On$(a,b)$ can be interpreted as $(a,b)\in$ On.

![](img/l8/figure1.png)

## Example of comparison of Propositional Logic and FOL

Primitives in Propositional Logic. Ski-race example.
**Objects**

- Anne (A), Berit (B), Camilla (C), Dina (D)
- There are not actually represented in propositional logic.
- Only True-or-False facts **about** them are represented.
- Objects alone do not have a truth value, whereas all primitives in propositional logic do.

**Propositional Symbols**

- $F_{AB}$ (Anne is faster than Berit), $F_{BA}$ (Berit is faster than Anne), ..., $F_{AC}$
- These have truth values and are the primitive terms
- Their logical combinations into sentences (representing specific facts or general rules) also have truth values.

## Models in Propositional Logic

![](img/l8/figure2.png)

## FOL Semantics - Interpretation

- An interpretation $I$ is defined by mapping symbols (e.g. constants, predicates) to the domain of discourse $D$ or relations on $D$
- domain of discourse: the set of objects in the world we represent and refer to
- An interpretation $I$ maps:
  - Constant symbols to object in $D$
  - Predicate symbols to relations and properties(1-ary rels.) on $D$
  - Function symbols to functional relations on $D$

![](img/l8/figure3.png)

## Ski Race: Conceptualization

**Objects**

- Anne, Berit, Camilla, Dina
- These are now represented in the logic, even though they still have no truth value.

**Functions**

- best10(person) $\rightarrow$ time. Mapping from athelte to their best 10K time.
- rank(person) $\rightarrow$ integer. Mapping from athlete to their seeding in the competition.
- start(person) $\rightarrow$ integer. Mapping from athlete to start order in the race, where slowest start first.
- These have no truth value and map one primitive object (person) to another (number).
- greater(X,Y) $\rightarrow$ {True, False}. Is the number X greater than number Y?
- faster(X,Y) $\rightarrow$ {True, False}. Is athlete X faster than athlete Y?
- These always have a truth value.
- These are often viewed as explicit lists of tuples, one list for each TRUE relation. So in one possible world, faster is represented by:
  $$\{(anne, berit), (anne, camilla), (dina, anne), (dina, camilla),(camilla, berit), (dina, berit)\}$$

## Interpretations in First-Order Logic

Interpretation - Mapping from constant, function and predicate symbols of the representation to the conceptualization

![](img/l8/figure4.png)

## Another Legal Interpretation

![](img/l8/figure5.png)

## Universal Quantifiers

- Quantification express properties of collections of objects.
- $\forall:$ "For all"
- $\forall\,(variable)\,(sentence)$ Let $P(x):x+1\geq x$
- We can state the following: $\forall x P(x)$
- English translation: "for all values of $x, P(x)$ is true"
- English translation: "for all values of $x, x+1\geq x$ is true"
- Everyone at NTNU is smart:
  $$\forall x\, At(x, NTNU)\implies Smart(x)$$
- $\forall x\, P$ is true in a model $m$ iff $P$ is true with $x$ being **each** possible object in the model
- **Equivalent to the _conjunction_ of _instantiations_ of $P$**
  ![](img/l8/figure6.png)

## Existential quantification

- $\exists:$ "There exist a/some"
- $\exists\,(variables)\,(sentence)$
- Someone at NTNU is smart
  $$\exists x\, At(x, NTNU)\wedge Smart(x)$$
- $\exists x\, P$ is true if in a model $m$ iff $P$ is true with $x$ being **some** possible object in the model.
- **Equivalent to the _disjunction_ of _instantiations_ of $P$**
  ![](img/l8/figure7.png)

## Evaluating Sentences with Quantified Variables

![](img/l8/figure8.png)

## Ski Models - Interpretation 1

![](img/l8/figure9.png)

## Ski Models - Interpretation 2

![](img/l8/figure10.png)

## Common mistakes with Quantifiers

- Typically, $\implies$ is the main connective with $\forall$
- Common mistake: using $\wedge$ as the main connective with $\forall:$
  $$\forall x\, At(x,NTNU)\wedge Smart(x)$$
  means "Everyone is at NTNU and everyone is smart"

## Another common mistake to avoid

- Typically, $\wedge$ is the main connective with $\exists$
- Common mistake: using $\implies$ as the main connective with $\exists:$
  $$\exists x\, At(x,NTNU)\implies Smart(x)$$
  is true if there is anyone who is not at NTNU!

## Connections between $\forall$ and $\exists$

- ALl statements made with one quantifier can be converted ibto equivalent statements with the other quantifier by using negation.
- Remember De Morgan's Rules
  - $P\wedge Q\equiv(\neg(\neg P\vee\neg Q))$
  - $P\vee Q\equiv(\neg(\neg P\wedge\neg Q))$
  - $\neg(P\wedge Q)\equiv\neg P\vee\neg Q$
  - $\neg(P\vee Q)\equiv\neg P\wedge\neg Q$
- Generalized De Morgan's Rule
  - $\forall x\, P(x)\equiv \neg\exists x(\neg P(x))$
  - $\exists x\, P(x)\equiv \neg\forall x(\neg P(x))$
  - $\neg\forall x\, P(x)\equiv \exists x(\neg P(x))$
  - $\neg\exists x\, P(x)\equiv \forall x(\neg P(x))$

## Connections between $\forall$ and $\exists$

- Conversion/negation of a quantifier means to represent the quantified statement in terms of the "other" quantifier.
- Negation rules/laws:
  - $\neg\exists\equiv\forall\neg$
  - $\neg\forall\equiv\exists\neg$
  - $\neg\forall\neg\equiv\exists$
  - $\neg\exists\neg\equiv\forall$

## Multiple Quantifiers

- more complex sentences can be formulated by multiple varialbes and by nesting quantifiers
- Variables must be introduced by quantifiers, and belong to the innermost quantifier that mentions them
- Example
  - $\forall x, y\, Parent(x,y)\implies Child(y,x)$
  - $\forall x\, Human(x)\forall y Loves(x,y)$
  - $\exists x\, Human(x)\forall y Loves(x,y)$
- "For all $x$, there exists a $y$ such that $P(x,y)$"
  - $\forall x\exists y\, P(x,y)$
  - Example: $\forall x\exists y(x+y=0)$
- "There exists an $x$ such ahat for all $y$ $P(x,y)$ is true"
  - $\exists x\forall y\, P(x,y)$
  - Example: $\exists x\forall y(x\cdot y=0)$

## Order of Quantifiers

- Reversing the order of the same type of quantifiers does not change the truth value of a sentence
  $\forall x\forall y\,P(x,y)$ is the same as $\forall y\forall x\,P(x,y)$
- $\exists x\forall y$ and $\forall x\exists y$ are not equivalent!
  - $\forall x\exists y\, Loves(x,y)$
  - $\exists x\forall y\, Loves(x,y)$

## Example - Order of Quantifiers

- $\forall x\exists y\, Loves(x,y)$
  - Everyone in the world loves someone.
  - Everybody does not necessarily love the same person. $y$ may be different.
  - With parantheses: $\forall x(\exists y\, Loves(x,y))$
  - $y$ is inside the **scope** of $x$
- $\exists x\forall y\, Loves(x,y)$
  - There is a person who loves everyone in the world
  - The same person $x$ loves everybody.
  - $y$ is inside the scope of $x$
- $\exists y\forall x\, Loves(x,y)$
  - There is someone whom everybody likes
  - Everybody likes the same $y$
  - $x$ is inside the scope of $y$

## Negating multiple Quantifiers

- Recall negation rules for single quantifiers:
  - $\neg\forall x\, P(x)\equiv\exists x\neg P(x)$
  - $\neg\exists x\, P(x)\equiv\forall x\neg P(x)$
- You change the quantifier(s), and negate what it's quantifying:
  $$\neg(\forall x\exists y\, P(x,y))\equiv\exists x\neg\exists y\, P(x,y\equiv\exists x\forall y\neg P(x,y)$$

# Lecture 9 - Inference in First Order Logic <a name="c9"></a>

## Inference by Reduction to Propositionalized Sentences

- In First order logic we formlate the inference in the same way as PL.
- We want to find out whether a KB entails a sentence $\alpha$
- One inference approach is to propositionalize the sentences in KB and then apply inference methods (e.g., resolution refutation) used in propositiona logic
  - Every FOL KB can be propositionalized so as to preserve entailment
  - A sentence is entailed by new KB iff it is entailed by the original KB

## Propositionalization process

Every KB in FOL can be "propositionalized"

- instantiate universal quantification
- instantiate existential quantification

## Propositionalization

- Suppose the KB contains just the following:
  $$
  \forall x\,King(x)\wedge Greedy(x)\implies Evil(x)\\
  King(John)\\
  Greedy(John)\\
  Brother(Richard, John)
  $$
- To "propositionalize", we need to get rid of **quantifiers** and **variables.**

## Propositionalization of Universal Quantification

- We instantiate the universal sentence in _all_ possible ways.
  - The "Substitution" rule for instantiation of variables (for propositionalization):
    ![](img/l9/figure1.png)
    variable $x$ in the sentence $\alpha$ is substituted with a ground term $g$
- Variable $x$ is _substituted_ with the _ground terms_ referring to the objects _John_ and _Richard_ in the model one by one.

## Propositionalization of Existential Quantification

Removal of existential quantifiers.

- Each existentially quantified variable is replaced by a _Skolem_ constant or a _Skolem function._
- **Skolem Constant:** if the existential variable is not within the scope of any universaly quantified variable. Every instance of the existentially quantified variable is replaced with the same unique constant, a brand new one does not appear anywhere else.
- For any sentence $\alpha$ with variable $x,$ $x$ is substituted by _new constant symbol_ $k$ **that does not appear elsewhere in the knowledge base:**
  ![](img/l9/figure2.png)
  E.g., $\exists y(P(y)\wedge Q(y))$ is converted to: $P(CC)\wedge Q(CC)$

## Skolemization

- **Skolem Function:** If the existential quantifier is in the **scope** (i.e., "inside") of a (or more, e.g., $n$) universally quantified variables, then replace it with a unique $n$-ary function over these universally quantified variables. Remove then the existential quantifier.

E.g.,
$$\forall x\exists y(P(x)\vee Q(y))$$
converted to
$$\forall x\,P(x)\vee Q(f(x))$$

## Problems with propositionalization

- Problems: with function symbols, there are infinitely many ground terms,
  - e.g., Father(Father(Father(John))), etc.

## Solution: Herbrand Theorem

- Herbrand Theorem (1930). If a ground sentence $\alpha$ is entailed by an FOL KB, it is entailed by a finite subset of the propositionalized KB
  - Idea: For $n=0$ to $\infty$ do
    create a propositional KB by instantiating with depth-$n$ terms
    see if $\alpha$ is entailed by this $KB$
- Problem: works if $\alpha$ is entailed, loops if $\alpha$ is not entailed. Hence, it is semi-decidable.
- Theorem: Turing (1936), Church(1936) Entailment for FOL is semidecidable (algorithm exist that say yes to every entailed sentence, but no algorithm exists that also says no to every nonentailed sentence.)

## Problems with propositionalization

- Propositionalization seems to generate lots of irrelevant sentences.
  Eg. from
  $$
  \forall x\,King(x)\wedge Greedy(x)\implies Evil(x)\\
  King(John)\\
  Greedy(John)\\
  Brother(Richard, John)
  $$
- It seems obvious that $Evil(John)$ will be inferred at the end, but propositionalization produces lots of facts such as $Greedy(Richard)$ that are irrelevant
- With $p$ $k$-ary predicates and $n$ constants, there are $p\cdot n^k$ instantiations

## Inference without propositionalization

- Problem: Universal elimination gives us (too) many oppurtunities for substituting variables with ground terms
- Solution: avoid making blind substitution of ground terms
  - Make substitutions that help to advance inferences
  - i.e., use substitutions matching "similar" sentences in KB
- Make, inferences on the variable level
  - How?

UNIFICATION: takes two sumilar sentences and computes the **substitution** that makes them look the same, if it exists
UNIFY(P,Q)$=\theta;$ SUBST($\theta$,P)$=$SUBST($\theta$,Q)

## Motivating example for Unification

- Ground clases are clauses with no variables in them. For ground clauses we can use syntactic identity to detect when we have a $P$ and $\not P$ pair.
- What about variables? For example, can the following two clauses be resolved?
  - $P(john)\vee Q(fred)\vee R(x)$
  - $\neg P(y)\vee R(susan)\vee R(y)$

**KB:**
$(\forall x)(Bird(x)\implies Flies(x))\\Bird(Tweety)$
**Query:** $Flies(Tweety)?$

- Convert to a clausal form:
  $\neg Bird(x)\vee Flies(x)\\Bird(Tweety)$
- Can we apply _unit resolution rule_ here and infer $Flies(Tweety)?$

## Unification

- If two clauses have matching but complementary literals, we can resolve them.
- If we have a literal $P(x),$ where $x$ is a variable, in one clause and a complementary literal $\neg P(y)$ where $y$ is a term that does not contain $x,$ we can substitute $y$ for $x$ throughout the first clause.
- ... and then do propositional resolution on the complementary literals to produce the resolvent of the two clauses.
- Consider the two clauses:
  - $P(f(y),A)\vee Q(B,C)$
  - $\neg P(x, A)\vee R(x,C)\vee S(A,B)$
- Substituting $f(y)$ for the $x$ in the second clause yields
  $Q(B,C)\vee R(f(y),C)\vee S(A,B)$
  The appropiate substitution process i called _unification_

## Unification process

- Unify procedure: Unify(P, Q) takes two atomic (i.e. single predicates) sentences $P$ and $Q$ and returns a subsitution that makes $P$ and $Q$ identitcal.
- The aim is be able to mach literals even when they have variables.
- Rules for substitutions: Can replace a variable
  - by a constant.
  - by a varuable.
  - by a function expression, as long as the function expression does not contain the variable.

**Unifier:** a substitution that makes two clauses resolvable, e.g.,
$$\theta:\{x_1/M; x_2/x_3; x_4/f(..)\}$$

- A substitution $\theta$ is a set of pairings of variables with terms (i.e., constant symbol, variable or function(term, ...))
  $\theta=$ {v1/term1, v2/term2, ...}
- A unifier of two formulas $\alpha$ and $\beta$ is a substitution $s$ that makes $\alpha$ and $\beta$ syntactically identical.
- Two sentences $\alpha$ and $\beta$ are unified by $\theta$
  $Unify(\alpha,\beta)=\theta$ if $\alpha\theta=\beta\theta$
- Not all formulas can be unified - substitutions only affect variables.
  - Example: Consider the pair $p(f(x),a)$ and $p(y(f(w)))$
  - This pair cannot be unified as there is no way of making $a=f(w)$ with a substitution.
  - in $\theta,$ each variable is paired at most once
  - A variable's pairing term may not contain the variable directly or indirectly
    - e.g., can't have substitution $\{x/f(y), y/f(x)\}$
  - When unifying expressions $P$ and $Q,$ the variable names in $P$ and the variable names in $Q$ should be disjoint.
    - Yes: $UNIFY(Loves(John, x), Loves(y, Jane))=\theta=\{x/Jane, y/John\}$
    - No: $UNIFY(Loves(John, x), Loves(y, Jane))=\theta=\{x/Jane, y/John\}$

## Unification

- Unification: Makes two sentences equivalent by substituting values for variables.
- Given the KB:
  $
S_1: \forall x\,King(x)\wedge Greedy(x)\implies Evil(x)\\
S_2: King(John)\\
S_3: \forall y\, Greedy(y)\\$
  We want to infer Evil(John)
- **Unify** $S_1$ and $S_2$ by **substituting** $x$ with John (shown as {x/John}), and $S_1$ and $S_3$ with {y/John}
- Two sentences $\alpha$ and $\beta$ are unified by $\theta$
  $Unify(\alpha,\beta)=\theta$ if $\alpha\theta=\beta\theta$

## Unification - exercise

![](img/l9/figure3.png)
![](img/l9/figure4.png)

## Unify and Infer

A subtitution $\theta$ unifies atomic sentences $P$ and $Q$ if $subst(\theta, P)=subst(\theta, Q)$ (also denoted $P\theta=Q\theta$)

Idea: Unify rule premises with known facts, apply unifier to conclusion
E.g., if we know both $Q$ and $Knows(John, x)\rightarrow Likes(John, x)$ then we conclude

Likes(John, Jane)
Likes(John, OJ)
Likes(John, Mother(John))

## Most General Unifier

- Our aim is to be able to match conflicting literals (for the use of resolution), even when they have variables. Unification process determines whether there is a "specialization" that matches.
- However, we don't want to over specialize

## Most General Unifier - example

- Consider the two sentences:
  - $\neg P(x)\vee S(x)\vee Q(April)$
  - $P(y)\vee R(y)$
- Possible resolvants:
  - $(S(Arvid)\vee Q(April)\vee R(Arvid))$ $\{y=x, x=Arvid\}$
  - $(S(Sophie)\vee Q(April)\vee R(Sophie))$ $\{y=x, x=Sophie\}$
  - $(S(x)\vee Q(April)\vee R(x))$ $\{y=x\}$
- The last resolvant is "most-general", the other two are specializations of it.
- We want to keep the most general clause so that we can use it future resolution steps.

## Most general unifier

- Unification is not uniquq
- $Unify(Loves(John, y), Loves(x, y))=\theta=x/John, y/Jane$ or $\theta=x/John, y/z$
- Informally, the most general unifier (MGU) imposes the fewest constraints on the terms (contains the most variables).
- Formally, a substitution $\theta$ is more general than $\beta$ iff there is a substitution $\sigma$ such that $\theta\sigma=\beta.$
  e.g. $\theta=z/F(w)$ is more general than $\beta=z/F(C)$ since $\sigma=w/C$
- A most general unifier $\theta$ of $P$ and $Q$ is such that, for any unifier $\rho$ of $P$ and $Q,$
  there exists a substitution $P\theta=Q\theta=(P\theta)\rho.$

## Motivation for Standardizing apart

![](img/l9/figure5.png)
![](img/l9/figure6.png)

## Standardizing apart

$Knows(John, x)$ and $Knows(x, OJ)$ cannot be unified, i.e., unifications _fails._ Needs **"Standardizing apart".**

- Intuitively we know that if we knpw: John hates everyone he knows and that everyone knows OJ. So we should be able to infer that John hates OJ.
- This is why we require that every variable has a separate name.
- UNIFY $Knows(John, z_{27})$ and $Knows(z_{17}, OJ)$. This works!!!
- **Standardizing apart** eliminates overlap of variables.

## Inference without propositionalization: Forward and backward chaining

Our previous example:
$S_1: \forall x\,King(x)\wedge Greedy(x)\implies Evil(x)\\
S_2: King(John)\\
S_3: \forall y\, Greedy(y)\\
S_4: Brother(Richard, John)$

Now we would like to infer $Evil(John)$ without propositionalization. **We can use Modus ponents, but its "generalized" form.**

## Adapting Modus Ponens to FOL

![](img/l9/figure7.png)

- $P_1'$ is $King(John)$ and $P_1$ is $King(x)$
- $\theta$ is $\{x/John\}$
- $Q\theta$ is $Evil(John)$

## Inference through Forward and Backward Chaning in FOL

Example KB:

The law says that it is a crime for an American to sell weapons to hostile nations. The country Nono, an enemy of America, has some missiles, and all of its missiles were sold to it by Colonel West, who is American.

We want to Prove that **"Colonel West is criminal".**

- We need
  - to translate these natural language sentences to FOL
  - convert these sentences in the KB to Definite Clauses if they are not in DC form by eliminating quantifiers:
    - remove $\forall$
    - eliminate $\exists$ by skolemization

**Knowledge Base**
$S_1:$ It is a crime for an American to sell weapons to hostile nations:
$$\forall x,y,z\,American(x)\wedge Weapon(y)\wedge Sells(x,y,z)\wedge Hostile(z)\implies Criminal(x)$$
$S_1: American(x)\wedge Weapon(y)\wedge Sells(x,y,z)\wedge Hostile(z)\implies Criminal(x)$

$S_2:$ Nono ... has some missiles
$$\exists x\, Owns(Nono, x)\wedge Missile(x)$$

$S_2: Owns(Nono, M_1)\wedge Missile(M_1)$

$S_3:$ ... all of its missiles were sold to it by Colonel West
$$\forall x\, Missile(x)\wedge Owns(Nono, x)\implies Sells(West, x, Nono)$$

$S_3: Missile(x)\wedge Owns(Nono, x)\implies Sells(West, x, Nono)$

$S_4:$ Missiles are weapons.
$$\forall x\,Missile(x)\implies Weapon(x)$$

$S_4: Missile(x)\implies Weapon(x)$

$S_5:$ An enemy of America counts as "hostile"
$$\forall x\, Enemy(x, America)\implies Hostile(x)$$

$S_5: Enemy(x, America)\implies Hostile(x)$

$S_6:$ West, who is American...

$S_6: American(West)$

$S_7:$ The country Nono, an enemy of America...

$S_7: Enemy(Nono, America)$

## Forward chaining algorithm - abstract

- Similar to Propositional Logic, restriction on sentences - definite clause.
- Find and use rules that have as premises the known facts in the KB.
  - In Propositional Logic: $A\wedge B\implies C$
  - In FOL: $King(x)\wedge Greedy(x)\implies Evil(x)$
  - FOL Needs Unification to match sentences
- Continue matching and deriving consequences of sentences until deriving the goal.

## Forward chaining proof of Colonel West

Our data base:

1. $American(x)\wedge Weapon(y)\wedge Sells(x,y,z)\wedge Hostile(z)\implies Criminal(x)$
2. $Owns(Nono, M_1)$
3. $Missile(M_1)$
4. $Missile(x)\wedge Owns(Nono, x)\implies Sells(West, x, Nono)$
5. $Missile(x)\implies Weapon(x)$
6. $Enemy(x, America)\implies Hostile(x)$
7. $American(West)$
8. $Enemy(Nono, America)$

## Forward chaining proof of Colonel West

![](img/l9/figure8.png)
![](img/l9/figure9.png)
![](img/l9/figure10.png)

## Backward chaining example

![](img/l9/figure11.png)
![](img/l9/figure12.png)
![](img/l9/figure13.png)
![](img/l9/figure14.png)
![](img/l9/figure15.png)
![](img/l9/figure16.png)
![](img/l9/figure17.png)

## Example Resolution Refutation - same example

Now we solve the same Colonel West example using resolution, more correctly resolution refutation.

First, we look at Resolution rule in FOL.

## Resolution Rule

Full first-order version:
![](img/l9/figure18.png)
where $UNIFY(l_j, \neg m_j)=\theta.$

Two standardized clauses can be resoved if they contain **complementary literals** (one is the negation of the other). FOL literals are complementary if one _unifies_ with the negation of the other.

Apply resolution steps to $CNF(KB\wedge\neg\alpha);$ complete for FOL.

## Conversion to CNF - example

We'll soon start solving Colonel West example using Resolution Refutation.

- The idea is the same as in Propositional Logic:
  Our goal is to determine if $KB\models\alpha:$

1. Add $\neg\alpha$ to the $KB$
2. Convert $KB$ and $\alpha$ to Conjunctive Normal Form
3. Use the resolution rule and search to determine whether the ststem is satisfiable (SAT)

- Let us look at the procedure for conversion of FOL sentences to CNF through an example.

Translate this sentence to FOL and convert to CNF:

"Everyone who loves all animals is loved by someone"
$$\forall x[\forall y\, Animal(y)\implies Loves(x,y)]\implies [\exists y\, Loves(y,x)]$$

1. Eliminate biconditionals and implications
   $$\forall x[\neg\forall y\, \neg Animal(y)\vee Loves(x,y)]\vee [\exists y\, Loves(y,x)]$$

2. Move $\neg$ invards: $\neg\forall x,p\equiv\exists x\,\neg p,\quad\neg\exists x,p\equiv\forall x\,\neg p:$

   $$
   \forall x[\exists y\, \neg(\neg Animal(y)\vee Loves(x,y))]\vee [\exists y\, Loves(y,x)]\\
   \forall x[\exists y\, \neg\neg Animal(y)\wedge\neg Loves(x,y)]\vee [\exists y\, Loves(y,x)]\\
   \forall x[\exists y\, Animal(y)\wedge\neg Loves(x,y)]\vee [\exists y\, Loves(y,x)]
   $$

3. Standardize variables: each quantifier should use a different variable name
   $$\forall x[\exists y\, Animal(y)\wedge\neg Loves(x,y)]\vee [\exists z\, Loves(z,x)]$$

4. Skolemize: Each existential variable is replaced by a Skolem function of the enclosing universally quantified variables:
   $$\forall x[Animal(f(x))\wedge\neg Loves(x,f(x))]\vee Loves(g(x),x)$$

5. Drop universal quantifiers:
   $$[Animal(f(x))\wedge\neg Loves(x,f(x))]\vee Loves(g(x),x)$$

6. Distribute $\wedge$ over $\vee:$
   $$[Animal(f(x))\vee Loves(g(x),x)]\wedge[\neg Loves(x, f(x))\vee Loves(g(x),x)]$$

## Colonel West using Resolution Refutation

- KB:
  $American(x)\wedge Weapon(y)\wedge Sells(x,y,z)\wedge Hostile(z)\implies Criminal(x)$
  $Owns(Nono, M_1)\wedge Missile(M_1)$
  $Missile(x)\wedge Owns(Nono, x)\implies Sells(West, x, Nono)$
  $Missile(x)\implies Weapon(x)$
  $Enemy(x, America)\implies Hostile(x)$
  $American(West)$
  $Enemy(Nono, America)$
- Question: Is colonel West criminal?

## Colonel West example in CNF form

1. $\neg American(x)\vee\neg Weapon(y)\vee\neg Sells(x,y,z)\vee\neg Hostile(z)\vee Criminal(x)$
2. $\neg Missile(x)\vee\neg Owns(Nono, x)\vee Sells(West, x, Nono)$
3. $\neg Enemy(x, America)\vee Hostile(x)$
4. $\neg Missile(x)\vee Weapon(x)$

- Facts:
  $American(West), Owns(Nono, M_1), Missile(M_1), Enemy(Nono, America)$
- Add $\neg Criminal(West)$

![](img/l9/figure19.png)

# Lecture 10 - Planning <a name="c10"></a>

## What is planning?

Human Planning and Acting

- Acting without (explicit) planning
  - when purpose is immediate
  - when performing well-trained behaviour
  - when course of action can be freely adopted
- Acting after planning
  - when addressing a new situation
  - when tasks are complex
  - when the environment imposes high risk/cost
  - when collaborating with others

People plan only when strictly necessary.

## Intelligent Agents: Planning, Execution, and Learning

![](img/l10/figure1.png)

## An early example

![](img/l10/figure2.png)

- Example: NASA's Deep Space 1
  - Launched in 1998 to test technologies and perform flybys of astreroid Braille and Comet Borrelly
  - First spacecraft to be controlled by an AI system without human intervention
  - Remote Agent (remote intelligent self-repair software) system used to **plan** on-board activities and correctly diagnose and respond to simulated faults
  - Planning system was later used on the ground-based **Mars Exploration Rovers**

## Aspects of Planning

- There are various ways of defining a planning problem and several ways of doing planning
- Two main aspects of planning are
  - representation
  - reasoning mechanism

## Representation types

Chapter 2 defines 3 types of representation:

- Atomic
- Factored
- Structured

![](img/l10/figure3.png)

## Representational related issues

Let us revisit Chapter 7, Wumpus example.

- Using propositional logic, the agent could answer questions like "Which square I am in after making a _forward_ action", or "is the neighbour square $(2,1)$ safe to move to?".
- Remember that the KB has:
  - axioms, general domain knowledge of which truth doesn't need to be proven. They are given true.
  - Perceived current situation/observations.
- It is important to note that a percept is about only one time step.
  - For example, proposition **Stench** now may be contradictory if $\neg$**Stench** is already in the KB - if we don't represent time.
  - There is Stent in time step 3, i.e., **Stench**$^3$ will not contradict with $\neg$**Stench**$^2$

## The issue of time

- The time is an important aspect in Planning.
- Definition: We refer to aspects of world that changes from one time step to another as **fluents.**
- Example fluent: Location$_{xy}^t=$ Location, i.e., coordinates of the square the agent is in at time $t$ is a fluent.
- An action changes some aspect of the world (hence fluents), but not all aspects.
- The agent needs to keep track of fluents. But it also should know what remains unchanged.

## Fluents

- We say, in planning, that the **effect** of an action makes change in the fluents.
- Example **effect axiom:** The agent is at location/square/$[1,1]$ and facing east at time $=0$ and goes forward. The result is that the agent is in square $[2,1]$ and not any longer in $[1,1]$ at time $=1$
  $$Location_{11}^0\wedge FacingEast^0\wedge Forward^0\implies Location_{21}^1\wedge\neg Location_{11}^1$$
- If we use effect axioms, we'll need explicit assertion of such sentences about all time steps, all squares, actions, etc.
- In addition, effect axioms don't represent/express what remains unchanged by an action

## The Frame Problem

- So, the agent needs to know what remains unchanged in the environment when a particular action is executed
- This we call representational **frame problem,** i.e. how to represent fluents that don't change from one time step to another.
- A solution: The unchanged aspects of world can be represented in form of "Frame axioms" expressing all propositions that remain unchanged. E.g.,
  - $Forward^t\implies(HaveArrow^t\Leftrightarrow HaveArrow^{t+1})$
  - $Forward^t\implies(WumpusAlive^t\Leftrightarrow WumpusAlive^{t+1})$
  - ...
- Too many such axioms, hence inefficient
- One solution: Focusing on fluents $(F)$ rather than actions, and use **successor state axioms** instead
- "Successor state axioms"
  $$F^{t+1}\Leftrightarrow ActionCauses\,F^t\vee(F^t\wedge\neg ActionCausesNotF^t.)$$
- Examples on Successor state axioms:
  - $HaveArrow^{t+1}\Leftrightarrow(HaveArrow^t\wedge\neg Shoot^t)$
  - $L_{1,1}^{t+1}\Leftrightarrow(L_{1,1}^t\wedge(\neg Forward^t\vee Bump^{t+1})\vee(L_{1,2}^t\wedge(South^t\wedge Forward^t)\vee(L_{1,3}^t\wedge(West^t\wedge Forward^t))$

## Preconditions for Actions

- Representation of actions also need explicit statement of when an action is executable
- I.e., the conditions where the action can be applied, as **precondition axiom**
- Example in Propositional logic: In order to shoot an arrow, the agent must have an arrow: $Shoot^t\Leftrightarrow HaveArrow^t$
- Another issue: the interference between actions
  - For ex. Let us assume that Shoot and Forward may not be done at the same time - How to represen this in the system?
  - Explicitly state every action pair not allowed to "execute" at the same time in form of **action exclusion axioms**
  - Example action exclusion axiom: $\neg Shoot^t\vee\neg Forward^t$
- We will see different types of action (and action-related knowledge) representations in the research field of Planning - soon.

## Propositional Logic for planning

Logic can be used in 2 ways for planning:

1. Using SAT solver, i.e., using **satisfiability**
2. Combined with a search algorithm

## Use of Satisfiability for Planning

Basic idea:

1. Define and represent the problem:
   a) A collection of assertions about the initial state

   b) Successor-state axioms for all possible actions at each time step, precondition-axioms, action-exclusion axioms

   c) Assertion for the goal state. E.g., Havegold

2. Present the problem sentenses to **SAT solver.** If it finds a satisfying model then the goal is achievable, otherwise plan is impossible.
3. Assuming a model is found, extract from the model those variables that represent actions and are assigned true.

## Logic and Search

- The agent uses logical inference to infer whether it has an arrow (or another aspect of world) after an action.
- The agent uses search to decide which action to take.
  - The agent can use a search algorithm we saw in chapter $3,$ for example, $A^*$ to decide which action to take
- Hence, we can consider planning as a search in a search space (more about spaces later today)

## Representation in Planning Research

- As we have seen, it is possible to represent as ground sentence
  1. initial state
  2. axioms in the domain - other names are "domain knowledge", "state transition knowledge"
  3. goal state
- But representation of each ground sentence is not efficient and takes too much memory to scale up
- As a result researchers in the field defined new language tailored for planning

## Representation of Actions

- PDDL, a modified version of STRIPS language the text book uses.
- Basic idea:
  - Describe actions at an abstract level as **action schema**
  - Uses a restricted form of predicate logic
    ![](img/l10/figure4.png)
    **Action:** $PutOn(r,x,y)$
    **Precondition:** $On(r,x)\wedge Clear(r)\wedge Clear(y)$
    **Effect:** $On(r,y)\wedge Clear(x)\wedge\neg On(r,x)\wedge\neg Clear(y)$
- times and states are implicit in the action schemas: preconditions refer to time $t$ and effect to time $t+1$
- the set of action schemas define the domain of the considered planning problem

## The Frame Problem

- Should we represent the effect of **PutOn** on the other variables? Need to enumerate explicitly all of the variables in the world.
- One solution: It is implicitly assmed that **any symbol not mentioned in effect remains unchanged.**
- Compute the result of an action $a$ taken in state $s:$
  - Think of the **effect** of an action consisting of the positive and negative effects, i.e.,
    - **Effect:** $On(r,y)\wedge Clear(x)\wedge\neg On(r,x)\wedge\neg Clear(y)$
  - The positives (call "ADD") are the one that will be true in the resulting state while the negative (call "DEL") ones will be removes from state $s:$
    State of $s+1$ caused by execution of action $a:$ $(s-DEL(a))\cup ADD(a).$

## Representation of States

- Each state is represented as a conjunction of fluents that are ground, functionles, and non-negative atoms.
- The following are not allowed in a state:
  - $University(x)$; $x$ is a university. Not state because of variable.
  - $\neg BestUniversity(NTNU, Norway)$; not, because of negation.
  - $InTrondheim(BestUniversity(Norway)):$ not, because of function.

## Representation of States in PDDL and Closed World Assumption

- State representation relies on **Closed World Assumption:** any fluent not mentioned in a state is false.
- An initial state is a conjunction of ground atoms - i.e. no variable
- A goal state is a conjunction of literals (positive/negative) that may contain variables - similar to preconditions.
  E.g., $At(p, Trondheim)\wedge Politican(p)$ a/any politician is in Trondheim.
- Other languahes make different assumptions, e.g., negative literals part of state, unmentioned literals unknown.
- E.g., STRIPS does not allow negative literals in preconditions and goals.

## Design of Actions

Example: Blocks are represented by constants $A,B,C$ and an additional constant, $Table,$ is representing the table.
![](img/l10/figure5.png)
**Start:** $On(A, Table)\wedge On(B, Table)\wedge On(C, A)\wedge Clear(B)\wedge Clear(C)$
**Goal:** $On(A, B)\wedge On(B,C)$
**Action Schema:**
$Action(Move(b,x,y))$
$PRECOND: On(b,x)\wedge Clear(b)\wedge Clear(y)$
$EFFECT: On(b,y)\wedge Clear(x)\wedge\neg On(b,x)\wedge\neg Clear(y)$

However, there are some problems here. Which?

**Prolem:** When $x$ is the table, then the effect $Clear(x)$ becomes a problem because the table is never empty.

**Solution:** Introduce new action schema:
$Action(Move(b,x))$
$PRECOND: On(b,x)\wedge Clear(b)\wedge Clear(y)$
$EFFECT: On(b,Table)\wedge Clear(x)\wedge\neg On(b,x)$

Problem stays after distinguishing, $Move$ and $Move-to-table.$

1. The system does not know when to use $Move-to-table(b,x)$ instead of i.e. $Move(b,x,Table),$ which results in a larger-than-necessary search space; and
2. Some of the operator applications, such as $Move(B,C,C),$ which should do nothing, have inconsistent effects.

Some solution:

1. We could introduce $Block$ and make $Block(x)$ and $Block(y)$ preconditions of $Move(x,y,z)$
2. We could add $\neg(y=z)$ as a precondition for $Move(x,y,z)$

Relationships/inference between actions is a rather challenging issue which we'll come back later.

## Planning Algorithms

Different planning algorithms have different searcg spaces

- State-space planning
  - Each node represents a state of the world
  - A plan is a path through the space
- Plan-space planning
  - Starts with partial partial incorrect plan, then apply changes to correct it
  - Each node is a set of partially-instantiated operators, plus some constraints
  - Impose more and more constraints, until we get a plan.

## State-space planners

Now we are back to thinking planning as Problem Solving.

Two types of State-space planners:

**Progression planners** reason from the start state, trying to find the actions that can be applied (match preconditions)

**Regression planners** reason from the goal state, trying to find the actions that will lead to the start state (match effects)

## Progression (forward) planning

![](img/l10/figure6.png)

Algorithm:

1. Determine all actions that are applicable in the start state
2. Ground the actions by replacing any variable with constants
3. Choose an action to apply
4. Determine the new content of the knowledge base, based on the action description
5. Repeat until goal state is reached

## Example: supermarket domain

![](img/l10/figure7.png)
Consider the task **get milk, bananas, and a cordless drill**
![](img/l10/figure8.png)

- Actions of which preconditions are true at a state are "applicable" at that state.
- Note that in this case there are **a lot** of possible actions to perform!

## Branching Factor of Forward Search

- Forward search can have a very large branching factor
  - E.g., many applicable actions that don't progress toward goal
- Why this is bad: The search algorithms we saw, e.g., in chapter 3 can waste time trying lots of irrelevant actions
- Need good (domain-specific) heuristic and/or pruning procedure

## Regression (backward) planning

![](img/l10/figure9.png)

Algorithm:

1. Pick an action that satisfies (some of) the goal propositions.
2. Make a new goal by:

- Removing the goal conditions satisfied by the action
- Adding the preconditions of this action
- Keeping any unsolved goal propositions

3. Repeat until the goal set is satisfied by the start state.

## Backward search

- For forward search, we started at the initial state and computed state transitions
  - new state $=\gamma(s,a)$
- For backward search, we start at the goal and compute inverse state transitions
  - new set of subgoals $=\gamma^{-1}(g,a)$
- To define $\gamma^{-1}(g,a),$ must first define **relevance:**
  - An action $a$ is relevant for a goal $g$ if
    - $a$ makes at least one of $g$'s literals true
      - $g\cap\,effects(a)\ne\empty$
    - $a$ does not make any og g's literals false
      - $g^+\cap\,effects^-(a)=\empty$ and $g^-\cap\,effects^+(a)=\empty$
        where $g^-=$ negative fluents in $g$

## Example: supermarket domain

![](img/l10/figure7.png)

In the goal state we have $Have(Milk)\wedge Have(Drill)\wedge Have(Banana)$

The action $Buy(ClahsOhlson, Drill)$ enables ut to achiece $Have(Drill),$ so we create a new goal by removing this effect and adding the preconditions.

## Efficiency of Backward Search

- Not guided regarding which subgoal to pursue at a moment, hence inefficient.
- Note that the **order** in which we try to achieve these propositions matters!

Next: We'll talk about the subgoal dependencies and planning algorithms that handle this.

## Total vs Partial Order Planning

**Total order:** Plan is always a strict sequence of actions
![](img/l10/figure10.png)
**Partial order:** Plan steps may be unordered
![](img/l10/figure11.png)

- The planning methods so far generated total-order plans - strict order of execution of actions
- However, in some cases, the subgoals/subproblems are independent
- And some actions may be executed in parallel (e.g., get bruch and get ladder)
- Partial order planning on **plan space** creates more optimal plans

## Partial Order Planning

Search in **plan space** and use **least commitment** to ordering whenever possible.

In state-space search:

- Search space is a set of states of the world
- Actions cause transitions between states
- Plan is a path through state space

In plan-space search:

- Search space is a set of **partially ordered plans**
- **Plan operators** cause transitions
- Goal is a legal plan

## Partial Order Planning Process

- Start with an empty plan consistinf of
  - _Start_ step with the initial state description as its effect
  - _Finish_ step with the goal description as its precondition
- Proceed by the operations:
  Plan operatores: add _actions_, add _causal links_, specify **orderings**, **bind** variables
  - adding actions to achieve preconditions
  - adding causal linkgs from an existing action to achieve preconditions
  - order on action w.r.t. another to remove possible conflicts/threats
- Gradually move from incomplete/vague plans to complete, correct plans
- Backtrack if an open condition is unachievable or if a conflict is unresolvable
- A plan is **complete** iff every precondition is achieved
- A precondition is **achieved** iff it is the effect of an earlier step and no **possibly intervening** step undoes it

## POP Example 1

In this example on Partial order Planning (POP) the subproblems/subgoals are independent

![](img/l10/figure12.png)

## Example 1 - 2

![](img/l10/figure13.png)

## Example 1 - 3

![](img/l10/figure14.png)

## Example 1 - 4

![](img/l10/figure15.png)

## Example 1 - 5

![](img/l10/figure16.png)

## Example 1 - 6

![](img/l10/figure17.png)

- Two subgoals, found a plan for each $P_1$ and $P_2$
  - $P_1:$ MoveToTable(B,A) + Move(A, Table, B)
  - $P_2:$ MoveToTable(D,C) + Move(C,Table,D)
- Since the subgoals are independent, i.e., like two separate problem instances:
  - Any total order plan consistent with this partial order will work.
  - E.g.: MoveToTable(B,A), MoveToTable(D,C), Move(C, Table, D), Move(A, Table, B)

## Sussman Anomaly and Subgoal Dependency

![](img/l10/figure18.png)
Total order planners typically separate the goal (stack A atop B atop C) into subgoals, such as:

1. get A atop B
2. get B atop C

Accomplish subgoal 1 first by removing C from A and moving A atop B ... but then we cannot accomplish subgoal 2 without undoing subgoal.

Accomplish subgoal 2 first ... then subgoal 1 cannot be achieved without undoing suboal 2.

Either way of ordering, subgoals cause clobbering.
When using linear planning, we may for example repeatedly put A on top of B and remove it.

## POP Example 2 - 1

This example shows the threats/conflicts between actions, and ordering constraints in planning for Sussman anomaly type of cases.

![](img/l10/figure19.png)

## Example 2 - 2

![](img/l10/figure20.png)

## Example 2 - 3

![](img/l10/figure21.png)

## Example 2 - 4

![](img/l10/figure22.png)

## Example 2 - 5

![](img/l10/figure23.png)

- Move(B, Table, C) must be after MoveToTable(C, A) - otherwise it will do $\neg$Clear(C) true
- Move(A, Table, B) must be after Move(B, Table, C) for a similar reason
- Optimal plan: MoveToTable(C, A), Move(B, Table, C), Move(A, Table, B)

## Discussion of Partial Order Planning

**Advantages:**

- Plan steps may be executed unordered
- Handles concurrent plans
- Least commitment can lead to shorter search times
- Sound and complete
- Typically produces the optimal plan

**Disadvantage:**
Complex plan operatores lead to high cost for generating actions

Next: Planning Graphs

## Planning graphs

Back to State-space Search

- Forward and Backward search in state-space planning not efficient, needs heuristic
- Some alternatives are "ignore preconditions" and "ignore delete list"
- Heuristic using **Planning Graph**

## A planning graph

![](img/l10/figure24.png)

- A layered graph
- Two kinds of layers alternate
  - literal
  - action
- Every two layer (i.e., state+action) corresponds to a discrete time. No variables as in action schema.

## Planning graphs idea

**Planning graph:**

- A polynomial size approximation of a tree with all possible actions from an initial state $S_0$ to successor states
- Can be used as an admissible heuristic to determine if $G$ is reachable from $S_0$

**GraphPlan** extracs a plan directly from such a planning graph

Main idea:

- Construct a graph that encodes constraints on possible plans
- If a valid plan exists it will be part of this planning graph, so search only within this graph

## Planning Graph Definition

- Planning graphs work only for propositional planning problems, with no variables.
- A planning graph is a directed graph which is built forward and is organized into levels:
  - a level $S_0$ for the initial state, representing each fluent that holds in $S_0$
  - a level $A_0$ consisting of nodes for each ground action applicable in $S_0$
  - alternating levels $S_I$ followed by $A_i$ are built until we reach a termination condition
    - $S_i$ contains all the literals that could hold at time $i$ (even $P$ and $\neg P$)
    - $A_i$ contains all the actions that could have their preconditions satisfied at time $i$
- Mutual exclusion links (mutex) between actions mean that two actions cannot occur at the same time. Mutex between literals mean that two literals cannot appear in the same belief state.

## A Planning Graph

- Straight lines between two literals at consecutive literal levels denote NoOp ("persistence" or "maintenance" actions)
- The red lines show mutex relationships
- Those are the literals and actions that are mutually exclusive, i.e., cannot appear at the same time

![](img/l10/figure25.png)

## Mutex Relationships for Actions

- Inconsistent effects: one action negates the effect of the other
  ![](img/l10/figure26.png)
- Interference: one of the effects of one action is the negation of a precondition of the other
  ![](img/l10/figure27.png)
- Competing needs: one of the preconditions of one action is mutually exclusive with a precondition of another
  ![](img/l10/figure28.png)

## Mutex Relationships for Literals/propositions

- One is the negation of the other
- Inconsistent support: all ways of achieving two literals is mutually exclusive

![](img/l10/figure29.png)

## Example

In this example a husband is preparing dinner for the birthday of his wife without her being aware of.
In the beginning there is garbage in the kitchen, hands are clean, and it is quiet. The goal of the husband is to wrap a gift, prepare a dinner, and remove the garbage before the dinner.
![](img/l10/figure30.png)

## Example - graph expanded to level $S_1$

![](img/l10/figure31.png)

## Solution extraction (first attempt)

- At level $S_1,$ all the goal conditions are present, can look for a solution
- There are two ways to satisfy dinner, present, $\neg$garbage:
  carry; cook; wrap
  dolly; cook; wrap
- carry is mutex with cook; dolly is mutex with wrap
- Solution extraction fails, need to expand the graph

## Example - graph expanded to level $S_2$

![](img/l10/figure32.png)

## Solution extraction (second attempt)

- Support $\neg$garbage with carry, dinner with noop, and present with wrap. This is a _consistent_ set because none are mutually exclusive.
- The subgoals from level $A_1$ are dinner (precondition for noop), quiet (precondition of wrap)
  There are only two subgoals because dolly and carry do not have preconditions
- Choose cook to support dinner, and noop for quiet. These two actions are not mutex.
- If there are multiple actions at a level, they can be executed in parallel

## Valid plan

A **valid plan** is a subgraph of the planning graph such that:

- All goal propositions are satisfied in the last level
- No goal propositions are mutex
- Actions at the same level are not mutex
- Each action's preconditions are made true by the plan

Basic algorithm:

1. Grow the planning graph until all goal propositions are reachable and not mutex.
2. If the graph levels off first, return failure (no valid plan exists)
3. Search the graph for a solution (CSP or backward search)
4. If no valid plan is found, add a level and try again

## GraphPlan Algorithm

```
function GraphPlan(problem)
returns a solution, or failure

    graph <-- INITIAL-PLANNING-GRAPH(problem)
    goals <-- CONJUNCTS[problem.GOAL]
    nogoods <-- an empty hash table
    for tl=0 to infinity do
        if goals all non-mutex in last level of graph then
            solution <-- EXTRACT-SOLUTION(graph, goals, NUMLEVELS(graph), nogoods)
            if solution != failure then return solution
            if graph and nogoods have both leveled off then return failure
        graph <-- EXPAND-GRAPH(graph, problem)
```

## The GRAPHPLAN algorithm

- The GRAPHPLAN algorithm is a strategy for extracting a plan from the planning graph.
- The planning graph is computed incrementally by the function EXPAND-GRAPH
- Once a level is reached where all the goals show up as non-mutex, a plan is extracted with EXTRACT-SOLUTION
- If this EXTRACT-SOLUTION fails, the failure is recorded as a no-good, another level is expanded and the process repats until a terminal condition is met.

## Extract Solution

Can be solved as a backward search problem:

- Start with $S_n,$ the last level of the planning graphs, and the goals.
- Foe each level $S_i$ select a number of non-conflicting actions in $A_{i-1}$ whose effects cover the goals in $S_i.$ The resulting state is $S_{i-1}$ with goals the precondition of the selected actions.
- The process is repated until level $S_0$ hoping all the goals are satisfied.

If EXTRACT-SOLUTION fails to find a solution for a set of goals at a given level, we record the (level, goal) pair as no-good, so that we can avoid to repeat the computation.

## Properties of Plan Graphs

- A literal that does not appear in the final level of the graph cannot be achieved by any plan.
- The level cost of a goal literal is the first level it appears, e.g., $0$ for cleanhands and $1$ for dinner
- Level cost is an admissible heuristic but might undercount: it counts the number of levels, wheras there might be several actions at each level $\leftrightarrow$ use a serial planning graph

## Use of planning graphs for heuristic estimation

Information that can be extracted from the planning graph:

1. If any goal literal fails to appear in the final level of the graph, hen the problem is unsolvable.
2. We can estimate the cost of achieving a goal literal $g_i$ as the level at which $g_i$ first appears in the planning graph, the level cost. This estimate is admissible.
3. A better estimate can be obtained by serial plannning graphs, only one action at each level.
4. Estimating the heuristic of a conjunction of goals:
   1. max-level heuristic: the maximum level cost of any of the sub-goals. Admissible.
   2. level sum heuristic: the sum of the level costs of the goals. This can be inadmissible when goals are not independent, but can be accurate.
   3. set-level heuristic: finds the level at which all the literals appear toghther in the planning graph, without any mutex between pair of them. Admissible, dominates max-level, works well when the subplans interact a lot.

# Lecture 11 - Multiagent-Systems and Game Theory <a name="c11"></a>

## Agent Design (micro) vs. Society Design (macro)

**Micro-questions:**

- How do we build agents that are capable of independent, autonomous actions in order to successfully carry out the tasks that we delegate them?

**Macro-questions:**

- Types and characteristics of interactions between agents, interaction protocols
- Behaviour in societies of self-interested agents?
  - Cooperative
  - Competitive

## Game theory

- Studies the decisions of agents in a multiagent environment where
  - Actions of each agent have an effect in the environment
  - So, outcome of an action of one agent may depend on other agents' actions
  - Hence, "strategical decision" making

## Strategical Reasoning

- An agent's decision depends in what it reasons/thinks the other agent(s) will do.
  - The agent is **uncertain** about the decisions (i.e., acitons) of the other participating agent.
  - Tries to predict other's next decisions
  - Computes how these affect him/her
  - Makes own decisions accordingly

## Let us play

- Pretend we are playing a game. Here's how it works. You must choose a number, $x$, between $[0, 100].$
- Assume we would then calculate the average of all the numbers. Then the person whose number is closest to $2/3$ of the average will win.
- _In case of a tie, the prize will go to a person chosen randomly among the winners._
- Assume that everybody is rational
- You choose $x=??$

## Different types of games

- Sequential games - chapter $5$ in R&N
- Strategic/simultaneous normal form games - today
- Repeated games - very interesting

## Sequential (extensive form) games

- Turn taking
- At each point the agents may decide/change their strategy
- Representation: tree
- Example: tik tak toe, chess, go

## Example on sequential games: tic-tac-toe

Sequential games, represented as a tree
![](img/l11/figure1.png)

## Strategic normal form games

- One shot
- The agent chooses its strategy only once at the beginning of the game, and all agents take their actions simultaneously.
- Main issue: predict what the other agent(s) will play.
- Represented: payoff matrix (will see soon)
- Example: Prisoner's dilemma, battle of sexes, stag hunt

## Example 1: Prisoner's Dilemma

- Two men are collectively charged with a crime and held in separate cells.
  - If one confesses and the other does not, the confessor will be freed, and the other will be jailed for three years.
  - If both confesses, then each will be jailed for two years.
  - If neither confesses, then they will each be jailed for one year.
- They are both rational and both know the other is rational.
- No communication - no way of agreement.
- What kind of behavior would you expect them to display?

![](img/l11/figure2.png)

## Example 2: Stag Hunt

- Describes a conflict betwween safety and social ccoperation, "trust dilemma"
- Story is due to Jean-Jacques Rousseau: two individuals go out on a hunt. Each can individually choose to hunt a stag or hunt a hare.
- Each player must choose an action without knowing the choice of the other
- If an individual hunts a stag, he must have a cooperation of his partner in order to suceed. An individual can get a hare by himself, but a hare is worth much less than a stag.
- Each agent wants to do what the other does.

## Example 3: Battle of Sexes

- Jonathan and Sofie are married and they are in their offices on a Friday evening trying to figure out what they should do after work. They cannot get in touch with each other but would like to meet and spend the veening to a **movie or an opera.**
- Jonathan likes movies better while Sofie would rather go to an opera.
- However, being in love, the most important thing for them is to do something together; both view the night "wasted" unless they spend it together.

## Assumptions of Classical Game theory

- Agents are _rational_
  - They have well-defined objectives/preferences over a set of outcomes and
  - They choose the actions thay lead them to their preferred outcomes
- Agents have a common knowledge
  - The rules of the game
  - Know what other agents are rational and the others know that they know they are rational...

## Defining Strategical environments

Three main components

1. Players
2. Strategies/actions
3. Payoffs (utilities)

## A Simple Interaction Environment

- Assume we have just two agents, $Agent=\{i,j\}$
- All actions an agent $i$ can perform are $A_i={a_1,a_2,\dots}$
- All possible outcomes (i.e. outcome space) of the system are $\Omega=\{\omega_1,\omega_2,\dots\}$ where $\omega$ represents an outcome corresponding to a collection of actions, one for each agent
- Hence, actual outcome $\omega$ depends on the combination of actions taken by $i$ and $j$
- So, environmental behaviour is given by the state transformer function:
  $$\tau:A_i\times A_j\rightarrow\Omega$$

## State Transformer Function

- Assume each agent has just two possible actions that it can perform, $C$ and $D.$
- Here is an environment controlled by agent $j$ _only:_
  $$\tau(D,D)=\omega_1\quad\tau(D,C)=\omega_2\quad\tau(C,D)=\omega_1\quad\tau(C,C)=\omega_2$$
- Now, a state transformer function of an environemt which is sensitive
  $$\tau(D,D)=\omega_1\quad\tau(D,C)=\omega_2\quad\tau(C,D)=\omega_3\quad\tau(C,C)=\omega_4$$
- And here is another environment where none of the agent has any influence:
  $$\tau(D,D)=\omega_1\quad\tau(D,C)=\omega_1\quad\tau(C,D)=\omega_1\quad\tau(C,C)=\omega_1$$

## Strategic Normal Games

A game in strategic normal form is defined by:

1. Agents $(N>1)$
2. Actions:
   - Each agent $i$ chooses an action $a_i$ from its own action set $A_i$
   - The vector $a=(a_1,\dots,a_n)$ of individual actions is alled a **joint action** (or **action profile** or strategy profile). The set $A$ is the set of all joint ations.
     ![](img/l11/figure3.png)
3. Utility function:
   - Each agent $i$ has its own utility function $u_i(a)$ that measures the goodness of the joint actions.
   - Each agent may give different preferences to different joint actions.
   - A **payoff matrix** representation shows the utilities of **joint actions** for each agent (_coming soon_)

## Utility Function

- Suppose we have the case where both agents can influence the outcome and Action={a,b}, i.e., each agent has just two possible ations that it can perform. Four possible different outcomes can be produced by the system:
  $$
  \tau(a,a)=\omega_1\quad\tau(a,b)=\omega_2\\
  \tau(b,a)=\omega_3\quad\tau(b,b)=\omega_4
  $$
- Suppose the agents have utility function as follows:
  $$
  u_i(\omega_1)=1\quad u_i(\omega_2)=1\quad u_i(\omega_3)=4\quad u_i(\omega_4)=4\\
  u_j(\omega_1)=1\quad u_j(\omega_2)=4\quad u_j(\omega_3)=1\quad u_j(\omega_4)=4
  $$

## Utility/Payoff Matrix

- Assume agent $i$ has $A_i=\{a,b\}$ and agent $j$ has $A_j=\{c,d\}$
- Agent's utilities are shown as a payoff matrix
  ![](img/l11/figure4.png)
- The payoff $u_1$ is the utility for agent $i$ when agent $i$ chooses action $a$ and agent $j$ chooses action $c.$
- The payoff $u_2$ is the utility for agent $j$ when agent $i$ chooses action $a$ and agent $j$ chooses action $c.$

## Utilities and Preferences

- Agent's preferences over outcomes are captured by utility funtions:
  $$u:\Omega\rightarrow\R$$
- Utility functions lead to preference orderings over outcomes:
  $\omega>_i\omega'$ iff $u_i(\omega)>u_i(\omega')$ where $u_i$ is the utility fn of agent $i$
- Hence, $\omega>_j\omega'$ iff $u_j(\omega)>u_j(\omega')$
- Suppose the agents have utility functions as follows
  $$
  u_i(\omega_1)=1\quad u_i(\omega_2)=1\quad u_i(\omega_3)=4\quad u_i(\omega_4)=4\\
  u_j(\omega_1)=1\quad u_j(\omega_2)=4\quad u_j(\omega_3)=1\quad u_j(\omega_4)=4
  $$
  where $\omega_1=\{D,D\}, \omega_2=\{D,C\}, \omega_3=\{C,D\}, \omega_4=\{C,C\},$
- We say agent $i$ and $j$'s preferences (over outcomes) are as follows:
  ![](img/l11/figure5.png)
- If you ware agent $i,$ what would you prefer to do, $C$ or $D?$ Why?

## Rational action

- We can characterize this scenario (preceding slide) in this payoff matrix:
  ![](img/l11/figure6.png)
- $C$ is the rational choise for $i$, because $i$ prefers all outcomes that arise through $C$ over all outcomes that arise through $D,$ no matter what $j$ does. Indeed both agents prefer $C$ independently from each together!
- In this situation agents do not need to worry about what the other agent will do - **no "strategic thinking".**

## Prisoner's Dilemma

![](img/l11/figure7.png)

- Confess = defect
- Stay silent = cooperate
- Note that the numbers of the payoff matrix do not refer to years in prison but how good an outcoe is for the agent, the shorter time in jail the better.
- Top left: Reward for mutual ccooperation ($1$ year each).
- Top right: If $i$ cooperates and $j$ defects, $i$ gets sucker's payoff of $1,$ while $j$ gets $4$ (zero vs. 3 years)
- Bottom left: If $j$ cooperates and $i$ defects, $j$ gets sucker's payoff of $1,$ while $i$ gets $4$ (zero vs. 3 years)
- If both defect, then both get punishment for mutual defection (e.g., 2 years each)

## Canonical PD payoff matrix

![](img/l11/figure8.png)
Applies when this condition holds:
$$T>R>P>S$$

## Solution Concepts

- A solution to a game is a prediction of the outcome of the game using the assumption that all agents are rational and strategic.
- How does the game theory predict?
  - Strictly (Strongly) / weakly dominant equilibriums.
  - Iterated elimination of dominated actions
  - Nash equilibrium

## Strictly Dominant Strategy (SDS)

**Example:**
![](img/l11/figure9.png)

- Preferences:
  ![](img/l11/figure10.png)
- "Defect" is the **strictly dominant strategy** for both agents.
- $(D,D)$ is the strictly (also called **strongly**) dominant strategy equilibrium.

## Strictly Dominant Strategy Equilibrium

- An action is strictly dominant if it strictly dominates every action in $A_i.$
- **A dominant action must be unique, and when it exists, a rationa agent will choose it.**
- The strictly dominant strategy equilibrium is the joint strategy where all the agents choose the strictly dominant action.

## Strictly Dominant Strategy (SDS) - formal

- $A$ is the set of all joint actions.
- $a_{-i}$ is a joint action taken by all players other than $i.$
- $A_{-i}$ is the set of joint actions except the action of agent $i,$ i.e., $a_{-i}\in A_{-i}.$
- Given a game in strategic normal form, an action $a_i\in A_i$ for all player/agent $i$ <u>strictly dominates</u> action $b_i\in A_i$ if
  $$U_i(a_i, a_{-i})>U_i(b_i, a_{-i})\quad\forall a_{-i}\in A_{-i}$$

## SDS equilibrium Example 2

- Does this game have a dominant strategy for agent $i?$
- For agent $j?$

![](img/l11/figure11.png)

- Preferences
  ![](img/l11/figure12.png)
- Action $b$ is a strictly dominant action for agent $i.$
- Action $b$ is a strictly dominant action for agent $j.$
- Thus $(b,b)$ is a strictly dominant strategy equilibrium.

## Definition: Weakly Dominant Strategy (WDS)

- $a_i$ weakly **dominates** $b_i$ if
  - $u_i(a_i, a_{-i})\geq u_i(b_i, a_{-i})\quad\forall a_{-i}\in A_{-i}$ and
  - $u_i(a_i, a_{-i})>u_i(b_i, a_{-i})\quad\text{ for some } a_{-i}\in A_{-i}$
- It is called weakly dominant if it weakly dominates every action in $A_i.$

## Solution Concept: WDS equilibrium

Example:
![](img/l11/figure13.png)

- There is no strongly dominant strategy for each agent here.
- Action $b$ is a weakly dominant strategy for both agent $i$ and agent $j$
- Therefore $(b,b)$ is a weakly dominant strategy equilibrium.
- Rational agents will usually play this strategy.

## Example: No Dominant Strategy at all

![](img/l11/figure14.png)

- The game has no dominant strategy equilibrium.

## Solution Concept: Iterated elimination of Dominant strategies (IEDS)

- This solution may be used in games where there is no dominant strategy equilibrium.
- Required Common knowledge:
  - Each agent knows that the other is also rational.
  - All players know everybody's payoff functions.
- **A rational agent will never choose a suboptimal action, i.e., a dominated action.**
- IESD is a solution technique that iteratively eliminates strictly dominated actions from all agents until no more actions are strictly dominated.

## Definition: Strictly/weakly dominated

![](img/l11/figure15.png)

- Take a game in strategic form and consider any two actions $a_i, b_i\in A_i$ for any player $i\in N.$ We say that $a_i$ is **strictly dominated** by $b_i$ if
  $$u_i(a_i, a_{-i})<u_i(b_i, a_{-i})\quad\forall a_{-i}\in A_{-i}$$
- We say that $a_i$ is **weakly dominated** by $b_i$ if
  - $u_i(a_i, a_{-i})\leq u_i(b_i, a_{-i})\quad\forall a_{-i}\in A_{-i}$ and
  - $u_i(a_i, a_{-i})<u_i(b_i, a_{-i})\quad\text{ for some } a_{-i}\in A_{-i}$

## IEDS Example

![](img/l11/figure16.png)

- $R$ is strictly dominated for agent $j$ (by action $M$)
- We eliminate $R$ because agent $i,$ being rational, knows that agent $j$ will not play $R.$
- Now agent $j$ notices that $D$ is strictly dominated for agent $i.$ Agent $j$ eliminated in his head the ation for agent $i.$
- Eliminate $L$ for agent $j$.
- The order of elimination does not matter in IESD.

## Example: Iterated elimination of weakly dominated actions (IEWDS)

- If no strongly dominated actions, then use weakly dominated ones to eliminate
  ![](img/l11/figure17.png)
- Does the order matter?
- Start with eliminating $U$
- Start with $M$

## IESDS/IEWDS - problems

- Different outcomes may arise as outcomes that survive, depending on the order of elimination in IEWDS.
- There may be left more than one solution after elimination.
- Hence, need a stronger solution concept.
  - Nash equilibrium.

## Definitions: Pareto Optimality and Social Welfare

Two important notions for comparison and selection of solutions; How good is a solution?

1. Pareto optimality
2. Social welfare maximization

## Pareto optimality (efficiency) - defn.

- A solution (i.e., a strategy profile, e.g., $(a_1, a_2,\dots, a_n)$) $S^P$ is Pareto optimal, if there is **no** solution $S'$ with:
  - $\exists$ agent $i:U_i(S')>U_i(S^P)$ and
  - $\forall$ ageng $j:U_j(S')\geq U_j(S^P)$ i.e., none of the others are worse off
- In plain english: there is no other outcome where some agentcs can increase their payoffs without decreasing the payoffs of other agents.

## Example on pareto optimality

![](img/l11/figure18.png)

- Which joint action(s) is/are pareto optimal?
  - $(A,A):$ optimal because no other outcome makes an agent better without making the other worse.
  - $(A,B):$ optimal, because payoff "7" of agent1 can be improved but then agent2 is worse off.
  - $(B,A):$ optimal
  - $(B,B):$ Not optimal. Both agents are better off when they shift to $(A,A)$

## Social Welfare - defn.

- Social welfare value (of a solution)
  - Sum of utilities of all agents for this strategy profile.
  - If a solution maximizes social welfare (i.e., social optimum), then the available utilities are not wasted.
- if a solution is a social optimum, then it is Pareto efficient.
  - The converse does not hold.

## Solution concept: Nash Equilibrium - Definition

- **Nash equilibrium** is a strategy profile (i.e., a collection of strategies, one for each player) such that each strategy is a **best response** (maximizes payoff) to all the other agents' strategies.
- The best response of agent $i$ is given by $BR_i(a_{-i})=\{a_i\in A_i: u_i(a_i, a_{-i})\geq u_i(b_i, a_{-i}\text{ for all }b_i\in A_i)\}.$
- Best response for each agent gives the set of payoff maximizing strategies for each strategy profile of the other player.

## How to find the Nash equilibrium(s)

- One way of finding Nash eq. in two-person strategic form games is to utilize the best response correspondence in the payoff matrix.
- Mark the best response(s) of each agent given the action choice of the other agent. A strategy profile where best response of all agents intersect is a Nash equilibrium (not necessarily a singleton set)
- The Nash equilibriums are $(x,x)$ and $(y,y).$

![](img/l11/figure19.png)

## Finding NE - example

![](img/l11/figure20.png)

## Finding NE - another example

![](img/l11/figure21.png)

## Example: Prisoner's Dilemma

![](img/l11/figure22.png)

- The strategy profile (defect, defect) is a Nash Equilibrium.
  - If agent $i$ changes its strategy (defect) to cooperate - the new situation is (cooperate, defect) - agent $i$ will be worse off (payoff from 2 to 1).
  - If $j$ changes its strategy (defect $\rightarrow$ cooperate) it will be worse off (payoff, again, from 2 to 1).
- So defection is the best response to all possible strategies
- Pareto optimal: $(C,D), (D,C)$ and $(C,C)$
- Socially welfare maximizing: $(C,C)$
- The solution is $(D,D)$
  - Unique Nash (also strongly dominant strategy profile) is not Pareto optimal
  - Not socially (welfare) maximizing
- Intution says this is not the best outcome - not social optimum. Surely they should both cooperate and each get payoff of 3!
- This apparent paradox is the fundamental problem of multi-agent interactions.

## Multiple Nash equilibria

![](img/l11/figure23.png)

- Not every interaction scenario has a single Nash equilibrium.
- Consider two agents of whom chooses either l (left) or r (right). If their choice do not match, they receive a payoff of zero.
- There are two Nash equilibriums, $(l,l)$ and $(r,r).$
- The two Nash Equilibriums are not equal. Would the agents possibly "agree" (coordinate) upon one of the solutions?
  - $(r,r)$ is _social optimum_
- This type of game is known as "pure coordination game"

## Example: Multiple Nash equilibria - Battle of sexes

![](img/l11/figure24.png)

- The story: Two individuals (a woman and a man) are arguing abot what to do for entertainment in the evening.
- The couple is in love, to the most important thing is to do something together; both view the night "wasted" unless they spend it together.
- Given agent $i$ plays $m$, the best response for agent $j$ is to play $m,$ which is expressed by underscoring player $j$'s payoff at $(m,m)$ and its best response to $o$ is $o$.
- Similar for agent $j,$ and the Nash equilibria are
  - $(m,m)$ and $(o,o)$. No strict equilibrium.
- Hence, they agree that cooperation is better but "disagree" about the best outcome.

## Example: Multiple Nash equilibria - Stag Hunt

Two individuals go out on a hunt. Each can individually choose to hunt a stag or hunt a hare. If an individual hunts a stag, he must have a cooperation of his partner in order to suceed. An individual can get a hare by himself, but a hare is worth much less than a stag.

- Each agent wants to do what the other does - which may be different than what they _say_ they'll do.
- Coordination game

![](img/l11/figure25.png)

- Two pure Nash equilibria: $(H,H)$ and $(S,S).$
- $(S,S)$ is pareto optimal/payoff dominant (more payoff) while $(H,H)$ is risk dominant (less risky).
- Higher payoff vs safer?
- If one agent trusts the other (that she will cooperate to hunt stag). But if... So, hunting stags is most beneficial for society but requires a lot of trust among its members.

## Stag Hung - solution selection

- Conflicting opinions
- Haranyi and Selten (1988) propose that the payoff dominant equilibrium is the **rational choice** in the stag hunt game
- Haranyi (1995) changes this conclusion to take risk dominance as the relevant selection criterion.

## Changing the environment/norms in Stag hunt game?

- If both agents hunt a hare the hares will be given to others.
- If only one catches a hare (whilst the other tries Stag) then the two agents will share the hare
- How would you hunt?

## No Nash Equilibrium

- There is no Nash in Zero-sum interactions
- Zero-sum games: preferences of agents are diametrically opposed, we have **strictly competitive** scenarios.
- Zero_sum encounters are those where utilities sum to zero.
  $$u_i(\omega)+u_j(\omega)=0\quad\forall\omega\in\Omega,\text{ where }\omega\text{ is an outcome}$$

## Zero-sum - Example

![](img/l11/figure26.png)

- Mathing pennies game
- Two agents. Each chooses either Head or Tail simultaneously. If the choice differ, agent $i$ pays agent $j$ (let's say 100 NOK). If they choose the same, agent $j$ pays agent $i$.
- No possibility for cooperation or coordination or anything.
- What may happen?

## Mixed Strategies

![](img/l11/figure27.png)

- No Nash: Because in Nash, the players don't change their strategies even when they know what the other agent will play.
- Here for every strategy pair, there is an agent that may want to change his strategy to get more payoff.
- Hence, no **pure** strategy equilibrium?
- What now? Randomized behaviour: Mixed strategies

## Repeated games

- Focus: remembering past behaviour of others, strategies based on past behaviour of other agents.
- Main issue: evolution of cooperation, learning, opponent modelling
- Example: prisoner's dilemma repeatedly played

## Iterated Prisoner's Dilemma

- How to evolve cooperation?
  - One answer: play the game more than once.
- If you know you will be meeting your opponent again, then the incentive to defect appears to evaporate

## Axelrod's Tournament

- Suppose you play iterated prisoner's dilemma against a range of opponents. What strategy should you choose, so as to maximize your overall payoff?
- Axelrod (1984) investigated this problem with a computer tournament for programs playing the prisoner's dilemma.
- In the tournament, programs played games against each other and themselves repeatedly.

## Strategies in Axelrod's Tournament

- ALLD
  - Always defect - the hawk strategy
- RANDOM
  - Selects either cooperate or defect on random.
- TIT-FOR-TAL
  - On round $t=0,$ cooperate
  - On round $t>0,$ do what your opponent did on round $t-1.$
- TESTER
  - On 1st round defect. If the opponent ever retaliated with defection, then play TIT-FOR-TAT. Otherwise play a repeated sequence of cooperating for two rounds, then defecting.
- JOSS
  - As TIT-FOR-TAT, except periodically defect.

## Recipes for Success in Axelrod's Tournament

Axelrod suggested the following rules for succeeding in his tournament:

- **Don't be envious:**
  - Don't Play as if it were zero sum!
- **Be nice:**
  - Start by cooperating, and reciprocate cooperation
- **Retaliate appropiately:**
  - Always punish defection immediately, but use "measured" force - don't overdo it.
- **Don't hold grudges:**
  - Always reciprocate cooperation immediately.

# Lecture 12 - Part 1 - Knowledge Representation <a name="c12"></a>

## Knowledge-based systems

![](img/l12/figure1.png)

"Knowledge is knowing that a tomato is a fruit, wisdom is not putting it in a fruit salad." - _Miles Kington_

## Knowledge Acquisition

Knowledge acquisition is the part of the job of Knowledge engineer.

**Knowledge engineer:**

- decides the content and organization of the knowledge required for the domain specific KB
- acquires this knowledge into the KB

**Knowledge acquisition techniques:**

- Traditional: working together with human experts - manual work
- Recent: from databases, text and data - information extraction and knowledge discovery.

## Ontological engineering

- How to create more general and flexible representations
  - Concepts like actions, time, physical objects, beliefs
  - Operates on a bigger scale than knowledge engineering
- Define general framework of concepts
  - Upper ontology

## The upper ontology of the world

![](img/l12/figure2.png)

## Difference with special-purpose ontologies

- A general-purpose ontology should be applicable in more or less any special-purpose domain
  - Add domain-specific axioms
- In any sufficiently demanding domain different areas of knowledge need to be unified
  - Reasoning and problems solving involve several areas simultaneously
- What do we need to express?
  - Categories, measures, composite objects, time, space, change, events, processes, physical objects, substances, mental objects, beliefs

## IBM Watson: Example of the power of knowledge

https://www.youtube.com/watch?v=_Xcmh1LQB9I

## KR languages

- **Main requirements for KR languages:**
  - Expressive power
  - Inferential adaquacy
  - Modifiability
  - Readability
- **Typical KR languages:**
  - Logic
  - Semantic networks
  - Frames
  - Description Logic
  - Production Rules

## Categories and objects

- Knowledge representation requires the organisation of objects into categories
  - Interaction at the level of the objects
  - Reasoning at the level of categories
- For example, Category-subcategory relationship
  - defines a taxonomy
  - enables Reasoning through **Inheritance**
- Example: All instances of Food are edible, Fruits is a subclass of Food, and Apples is a subclass of Fuit, then an apple is edible.

## Role of Categories in Reasoning

- Categories play a role in the **predictions** about objects
  - Based on **perceived properties:** An object that is orange colour, spherical with $10$ cm diameter and smells. Can this be edible?
  - IN KB: Orange is a fruit. All fruits are edible. Orange category has the same properties that the perceived object has.
  - Predict: It can be eaten

## Expressive power of logic

- Limitations of logic representations
  - Exceptions. Elephants are grey. But Eli, which is an elephant, is blue. Possible to represent in logic?
  - Uncertainty, e.g., tomatoes can be red, green or yellow
- We will use however FOL to discuss content and organization of knowledge. FOL can easily state facts about categories

## First-order logic and categories

- An object is a member of a category
  - $BB_{12}\in Basketballs$
  - Member(BB12, Basketballs)
- A category is a subclass of another category
  - $Basketballs\subset Balls$
  - Subcategory(Basketballs, Balls)
- All members of a category have some properties
  - $(x\in Basketballs)\implies Spherical(x)$
- All members of a category can be recognized by some properties
  - $Orange(x)\wedge Round(x)\wedge Diameter(x)=9.5"\wedge x\in Balls\implies x\in Basketballs$

## Relations between categories

- **Disjoint:** Two or more categories are disjoint if they have no members in common
  - $Disjoint(\{Animals, Vegetables\})$
- **Exhaustive Decomposition:** A set of categories $s$ constitutes an exhaustive decomposition of a category $c$ if all members of the set $c$ are covered by categories in $s$
  - $ExhaustiveDecomposition(\{Americans, Canadians, Mexicans\}, NorthAmerican)$
- **Partition:** A disjoint exhaustive decomposition is a partition
  - $Partition(\{Archaea, Bacteria, Eukarya\}, LivingThings)$

## Natural kinds

- Many categories have no clear-cut definitions (chair, bush, book)
- Tomatoes: sometimes green, red, yellow, black. Mostly round and mostly red.
- One solution: category $Typical(Tomatoes)$
  - $x\in Typical(Tomatoes)\implies Red(x)\wedge Spherical(x)$
- We can write down useful facts about categories without providing exact definitions

## Physical composition

- One object may be part of another
  $PartOf(Bucharest, Romania)\\
PartOf(Romania, EasternEurope)\\
PartOf(EasternEurope, Europe)\\
PartOf(Europe, Earth)$
- The $PartOf$ predicate is transitive reflexive and transitive
  $PartOf(x,x)\\
PartOf(x,y)\wedge PartOf(y,z)\implies PartOf(x,z)$
- So we can infer that $PartOf(Bucharest, Earth)$
- **Composite objects** are often characterized by structural relations among parts

## Event calculus

- Addresses what happens **during** the action.
- Example: $At(Knut, NTNU)$ refers to the fact of Knut being at NTNU, but does not say whether it is true.
- For this we need the predicate $T:$
  - $T(At(Knut, NTNU), t)$

## Time intervals

- Represented as an interval $i=(start,end)$
- $T(f,t)\quad f$ is true at time $t$
- $Happens(e,i)\quad e$ happens over the tame interval $i$
- $Initiates(e,f,t)\quad e$ causes $f$ to start to hold at time $t$
- $Terminates(e,f,t)\quad e$ causes $f$ to cease to hold at time $t$
- $Clipped(f,i)\quad f$ ceases to be true at some point during interval $i$
- $Restored(f,i)\quad f$ becomes true sometime during interval $i$

## Mental events and objects

- So far, knowledge based agents can have beliefs and deduce new beliefs
- What about **knowledge about** beliefs? What about knowledge about the inference process?
- Requires a model of the **mental objects** in someones head and the processes that manipulate these objects
- **Relationships** between agents and mental objects:
  - believes,
  - knows,
  - wants,
  - ...
- Example: $Believes(Lois, Flies(Superman))$ with $Flies(Superman)$ being a candidate for a **mental object**
- An agent can now reason about the beliefs of agents

## Intrinsic and Extrincic properties

- Stuff versus things, e.g. butter versus elephant
- count nouns versus mass nouns in linguistics
- an instance of stuff continues to be stuff when divided but not things
- instances of stuff have intrinsic properties that belong to the substance, e.g., butter has property _smelting point_
- instances of thing have extrinsic properties, e.g. weight.

## Semantic Networks, Quillian

- Developed by Ross Quillian, as "a psychological model of associative memory" (1968).
- Associationist theories define the meaning og an object in terms of a network of associations with other objects in a domain or a knowledge base.
- Quillian experimented with human objects:
- The structure of the network was devised from laboratory testing of human response times to question such as "Is a canary a bird?", "Can a canary sing?", "Is a canary yellow?", or "Can a canary fly?"

## Quillian experiments

- Experiment: E.g., "Can a canary fly?" needed longer response time than "Can a canary sing?"
- Quillian: humans organize knowledge herarchically and store information at its most abstract level.
- Reduces the size of the knowledge base; prevents update inconsistencies

## Semantic networks

- Logic vs semantic networks
- **Main idea:** Knowledge is not a large collection of small pieces of knowledge but larger pieces that are highly interconnected. The meaning of a concept emerges from how it is connected to other concepts.
- **Efficient algorithms:** for a category membership inference using inheritance reasoning
  - Female persons inherit all properties from person
  - Similar to object-oriented programming
- Inference of **inverse links**, e.g., $SisterOf$ vs. $HasSister$

## Semantic network example

![](img/l12/figure4.png)

## Multiple inheritance

![](img/l12/figure5.png)
White - Royal Elephant is more specific than Elephant.
![](img/l12/figure6.png)
Use model preference. E.g., religious belief may be given preference over political beliefs.

## Frame-based representations - example

- A Frame consists of a number of slots.
- A slot consists of a variable (a property) which has a value

![](img/l12/figure7.png)
![](img/l12/figure8.png)

## Frame-based representations

- Semantic networks where nodes have structure
- Frame with a number of slots (age, height, ...)
- Each slot stores specific items of information - attribute-value or slot-filler pairs
- When agent faces a new situation - Slots can be filled in (value may be another frame)
- Filling in may trigger actions
- May trigger retrieval of other frames
- Inhertiance of properties between frames
- Very similar to objects in OOP

## Frame-based representations - example

- Logic and semantic networks are declarative knowledge representatiojn languages.
- Frame-based languages are also mainly declarative but can also represent procedural knowledge through **demons**

![](img/l12/figure9.png)

## Reasoning with default information

- FOL is monotonic which is limiting - the set of entailed sentences can only increase.
- If $KB\models\alpha$ then $KB\wedge\beta\models\alpha$
- **Nonmonotonic logic,** e.g.,:
  - Circumscription
  - Default logic

## Circumscription

- Introduced by McCarthy: "A bird will fly if it is not abnormal."
- McCarthy introduces an $ab$ predicate into the default reasoning rule:
  - $(\forall x)[(bird(x)\wedge\neg ab(x))\rightarrow flies(x)]$
  - If there is no proof given by the logic that $ab(x),$ we can "circumscript" the $ab$ predicate and assume that it is not true.
- Given the premises
  - $(\forall x)[penguin(x)\rightarrow\neg flies(x)]$
  - $(\forall x)[penguin(x)\rightarrow\ bird(x)]$
  - $bird(Tweety)$
- If we add $penguin(Tweety)$ to the premises, then we can infer $ab(Tweety)$ by rewriting the default sentence like this:
  - $(\forall x)bird(x)\wedge\neg flies(x)\rightarrow ab(x)$

![](img/l12/figure10.png)

## Default logic

- Default rules that produce contingent conclusions.
- Example: $Bird(x):Flies(x)\char`\\ Flies(x)$ means "If $Bird(x)$ is true and $Fliex(x)$ is consistent with KB then $Flies(x)$ can be concluded by default.
- A default rule has $3$ components:
  - Prerequisite $(P),$
  - Justification $(J),$
  - Conclusion $(C)$
- $P:J_1\dots,J_n\char`\\C$
- If $P$ and $J_1\dots,J_n$ cannot be proven false, then the conclusion can be drawn.

## Truth maintenance systems - nonmonotonicity

- Many of the inferences have default status rather than being absolutely certain
  - Inferred facts can be wrong and need to be retracted $=$ **belief revision**
  - Assume knowledge base contains sentence $P$ and we want to execute $Tell(KB,\neg P)$
  - To avoid contradiction: $Retract(KB,P)$
  - But what about sentences inferred from $P?$
- Truth maintenance systems are designed to handle these complications

# Lecture 12 - Part 2 - Artificial Intelligence and Ethics <a name="c12"></a>

## The Emergence of AI-Ethical Principles

In the last few years, a number of institutions have published AI principles:

- The Asilomar AI principles (Future of Life Institute, 2017
- Principles for Algorithmic Transparency and Accountability (ACM2017).
- IEEEs General Principles of Ethical Autonomous and Intelligent Systems (IEEE 2017)
- Five principles for a cross-sector AI code (UK House of Lords, 2018)
- AI ethics principles (Google, 2018)
- Ethics guidelines for trustworthy AI (European Commission, 2019)
- ...

## An older one: Asimov's Three Laws of Robotics

- A robot may not injure a human being or, through inaction, allow an human being come to harm;
- A robot must obey the orders given it by human beings except where such orders would conflict with the First Law;
- A robot must protect its own existence as long as such protection does not conflict with the First or Second Laws.

'Runaround' (1942), Isaac Asimov

## Example: The 7 EU principles

- Human agency and oversight: AI systems should empower human beings, allowing them to make informed decisions.
- Technical Robustness and safety: AI systems need to be resilient and secure. They need to be safe, ensuring a fall back plan in case something goes wrong.
- Privacy and data governance: besides ensuring full respect for privacy and data protection, adequate data governance mechanisms must also be ensured
- Transparency: the data, system and AI business models should be transparent
- Diversity, non-discrimination and fairness: Unfair bias must be avoided
- Societal and environmental well-being: AI systems should benefit all human beings
- Accountability: Mechanisms should be put in place to ensure responsibility and accountability for AI systems

## Common Grounds

There are many different lists of principles, but it seems that they all can be synthesized into five key principles

- autonomy (people should be able to make their own decisions, e.g., human-in-the-loop, privacy protection)
- beneficence (society at large should benefits)
- non-maleficence (harmful consequences should be avoided, e.g., systems should be robust)
- justice (diversity, non-discrimination and fariness)
- explicability (transperancy and explainability)

## Problems with Principles

It is good to state principles! Howeber they also create problems since they are very high-level.

- They can be interpreted in different ways.
  - For example, autonomous killer drones can be considered as being beneficient for the soliders, or being morally impermissible, because machines decide about life and death
- They can conflict with each other in concrete cases.
  - For example, privacy and data collection for health science can conflict
- They can come into conflict in practise
  - For example, an excellent diagnosis might still be preferable even if its reasoning cannot be explained

It is nevertheless good to have such principles as orientation points along one can evaluate solutions.

## Artificial Intelligence$\ne $ Machine Learning

- In this course we looked at mainstream AI, and not Machine learning
- Unbelievable many times ML is considered as if it is AI, but it is only a subfield of it
- Main (and very important difference) between mainstream AI (Good old fashioned AI, knowledge-based systems) and the vast majority of machine learning (e.g., Neural networks) is:
  - Mainstream AI is knowledge-driven while majority of ML is data-driven
  - ML uses "labelles" data points (many of them) as examples and the system generates a model of this data, and then use this model to tell something about a new data (representing for example a person applying for a job)
  - This type of ML systems are called "black box"

## ML-pipeline

The "reasoning" processes underlying machine learning systems.
![](img/l12/figure11.png)

## Why/when AI-fairness is important?

Many things become automated by machine learning:

- employers select candidates by using ML systems.
- LinkedIn and XING use ML systems to rank candidates
- Courts in the US use ML systems to predict recidivism
- Banks use credit rating systems, which use ML
- Amazon and Netflix use recommender systems
- If these systems act unfair, groups and individuals may suffer

## Why AI-fairness is important

- Discrimination in a social sense of the word is prejudiced **treatment** of people based on perceived membership in certain classes, groups or categories, often called _protected classes._ The attribute that defines a protected class is called a _sensitive attribute_, e.g., gender, race, religion, disability, or age.
- Unfairness is to limit people's life chances based not on merits but based on sensitive attributes like gender or race.
- In some cases it is unintended discrimination, where different groups receive different outcomes or treatment even though their protected class membership was not explicitly considered in the decision process. This is called **disparate impact.**

## Unfairness in ML

- Where is the problem?
- Where to look at?
- How to measure it?
- How to solve it?

![](img/l12/figure12.png)

## Source of Bias in Data

![](img/l12/figure13.png)

## COMPAS example to Fairness

- This example is a very famous one creating hot debates in Fairness research and practise.
- It is about a system called COMPAS designed for predicting which criminals will reoffend.
- It is used by judges for risk estimation, across USA.

![](img/l12/figure14.png)

## Performance of an AI system

![](img/l12/figure15.png)

- In this course we talked about PEAS (i.e. performance, environment, actuators, sensors), and defined rational behaviour as
  - _an agent's taking actions that maximize the expected value of the **performance measure** given the percept sequrnce so far._
- Performance of an agent is measured through its "objective function"

![](img/l12/figure16.png)

## Objective function

- can be defined either as cost/loss function (to be minimized) or utility/profit/fitness function (to be maximized)
- and can be evaluated to a value, e.g., 90% of the dirt sucked, fruit classes are predicted with 70% accuracy.

Traditionally, objective function does not include ethical considerations such as fairness, privacy etc.

- ... And adding "ethical objective aspects" to the objective function may interfere with the measures of traditional objective function
- Often there is a tradeoff between for example accuracy and fairness measures.

## Perspective on Ethics in Philosophy

- Different perspectives in Ethics in Philosophy:
  - Deontological
  - Consequentialist
  - Utilitarian
  - Virtue

## Deontological vs Consequentialism

From "Stanford Encyclopedia of Philosophy":

- In comtemporary moral philosophy, deontology is one of those kinds of normative theories regarding which choices are morally required, forbidden, or permitted. In other words,
- deontology falls within the domain of moral theories that guide and assess _our choices_ of what we ought to do (deontic theories), in contrast to those that guide and assess _what kind of person we are_ and should be ("virtue" theories).

## Deontological approach

- Deontologist's claim: some actions have inherent moral value - as required, forbidden, etc.
- Whether an act is morally right or wrong depends on whether it is in conformity or conflict with moral duties and rights.
- Moral principles and rules.

## Consequentialist approach (from Stanford Encyclopedia)

Consequentialists hold that choices - acts and/or intentions - are to be morally assessed solely by the states of affairs they bring about. Consequentialists thus must specify initially the states of affairs that are intrinsically valuable - often called, collectively, "the Good." They then are in a position to assert that whetver choices increate the Good, that is, bring about more of it, are the choices that it is morally right to make and to execute. (The Good in that sense is said to be prior to "the Right.")

Consequentialists can and do differ widely in terms of specifying the Good. Some consequentialists are monists about the Good. Utilitarians, for example, identify the Good with pleasure, happiness, desire satisfaction, or "welfare" in some other sense. Other consequentialists are pluralists regarding the Good. Some of such pluralists belive that how the Good is distributed among persons (or all sentient beings) is itself partly constitutive of the Good, whereas conventional utilitarians merely add or average each person's share of the Good to achieve the Good's maximization.

## Moral Machines?

- Philosophers usually consider machines as not capable of making moral decisions.
- Howeveer, one can try to find properties such that machines could act morally.
- Machines need to have at least
  - beliefs about the world
  - intentions
  - moral knowledge
  - the possibility to compute the consequences ones own actions can have, in which case they can be considered as moral agents.

## Famous "Trolley Problem" and Autonomous driving

![](img/l12/figure17.png)

- The story goes like this: There is a runaway trolley barrelling down the railway tracks. Ahead, on the tracks, there are five people tied up and unable to move. The trolley is headed straight for them. You are standing some distance off in the train yard, next to a lever. If you pull this lever, the trolley will switch to a different set of tracks. However, you notice that there is one person on the side track. You have two options:
  - Do nothing and allow the trolley to kill the five people on the main track.
  - Pull the lever, diverting the trolley onto the side track where it will kill one person.
- What is the more ethicla option? Or, more simply: What is the right thing to do?
- Trolley problems highlight the difference between deontological and consequentialist ethical systems. The central question that these dilemmas bring to light is on whether or not it is right to actively inhibit the utility of an individual of doing so produces a greater utility for other individuals.

## Summary

- If a new AI winter arises, it will be due to ethical problems
- What are the main ethical concerns
- Several AI-ethics Regulations
- Philosophical approaches to ethics and morality
- AI is not equal to Machine Learning
- Why and how unfairness (and discrimination) occur in ML?
- Fairness definitions and metrics - some
- About migitations of fairness
- Trolley problem and the link to Consequentialism (in Philosophy of ethics)
