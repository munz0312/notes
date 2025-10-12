# COMP34111: Game Theory

## Game Tree and Strategy

  

---

  

## What is a Game?

  

For this course, a game must satisfy three requirements:

  

1. **Multiple agents (players)** interact with each other

2. **Numerical outcomes (pay-offs)** at the end - can be negative, given as real numbers

3. **Clearly defined rules** for actions at each point in time, with uniquely determined outcomes

  

---

  

## The Game Tree

  

A game can be represented as a **tree structure** where:

  

- **Nodes** = decision points in the game

- **Root** = starting point (nothing has happened yet)

- **Edges** = moves/actions taken by players

- **Leaves (final nodes)** = outcomes of the game (no further decisions)

- **Path from root to leaf** = a complete play of the game

  

### Key Properties

- Every node uniquely determines the path from the root

- Every node encodes the **complete history** of the game so far

- Every node defines a **subtree** (subgame) of the original tree

- Trees cannot contain cycles

  

![Placeholder: Noughts and crosses partial game tree showing root, nodes, edges, and leaves with pay-offs]

  

### Pay-offs

- Written as tuples: (Player 1 pay-off, Player 2 pay-off, ...)

- Example convention for win/loss games: Winner = 1, Loser = -1, Draw = 0

  

---

  

## Handling Special Game Features

  

### 1. Chance Elements

  

Introduce **Nature** as a pseudo-player who controls random moves:

- Nature has no pay-off

- Edges from Nature nodes are labeled with **probabilities**

- Used for dice, cards, or uncertain outcomes

  

**Calculating Probabilities:**

1. Find all leaves corresponding to desired outcome

2. For each leaf, multiply all probabilities along the path from root

3. Sum all these probabilities

  

![Placeholder: Risk game tree showing Nature nodes with probability labels]

  

### 2. Imperfect Information

  

Players may not know their exact position in the game tree.

  

**Information Sets:**

- Nodes grouped in the same "bubble" (or connected by dotted lines)

- Player must choose action without knowing which node they're at

- All nodes in same information set must have **identical available actions**

  

![Placeholder: Hidden coin game showing information set bubble for Player 2]

  

### 3. Simultaneous Moves

  

Handle by:

1. Let one player move first

2. Make the second player unable to observe the first move (using information sets)

  

![Placeholder: Paper-stone-scissors game tree with information sets]

  

---

  

## Formal Definition of a Game

  

A game in **extensive form** consists of:

  

1. Finite set of **players**

2. A **tree** structure

3. For each node: the **player who owns it** (whose turn it is)

4. For each edge: an **action label** (Nature's actions include probabilities)

5. For each player: their **information sets** satisfying:

- Actions taken to reach nodes are identical

- Actions available from nodes are identical

6. For each leaf and each player: a **pay-off**

  

---

  

## Important Game Categories

  

### Types of Games

  

1. **2-player game**: Two players (not counting Nature)

  

2. **Perfect information**: All information sets have size 1 (everyone knows exactly where they are)

- **Imperfect information**: Some information sets contain multiple nodes

  

3. **Zero-sum**: At every leaf, sum of all pay-offs = 0

- One player's gain is another's loss

  

4. **Without chance**: No Nature nodes

- **With chance**: Contains Nature nodes

  

### Examples

- **Chess, Go, Draughts**: 2-player, zero-sum, perfect information, without chance

- **Poker**: Zero-sum, imperfect information, with chance

- **Backgammon**: 2-player, zero-sum, perfect information, with chance

- **Paper-stone-scissors**: 2-player, zero-sum, imperfect information, without chance

  

![Placeholder: Classification table of common games]

  

---

  

## Strategies

  

### Fully Specified Strategy

  

**Definition:** For Player i, choose an action for **each** of i's nodes such that:

- For all nodes in the same information set, the **same action** is chosen

  

**Counting fully specified strategies:**

- For each decision point, count the number of choices

- Multiply all these numbers together

  

**Problem:** Over-specifies behavior - includes decisions at unreachable nodes

  

![Placeholder: Two fully specified strategies in chomp that behave identically]

  

### Pure Strategy

  

**Definition (recursive):** A subtree of the game tree with:

  

1. The root belongs to the strategy

2. When it's Player i's turn at a node in the subtree:

- **Exactly one** available move belongs to the subtree

- Same action chosen for all nodes in same information set

3. When it's **not** Player i's turn:

- **All** available moves belong to the subtree

  

**Key difference:** Only specifies decisions at **reachable** positions given the strategy so far.

  

![Placeholder: All seven strategies for Player 1 in 2×2 chomp shown as subtrees]

  

---

  

## Generating Strategies (Perfect Information)

  

Recursive algorithm for counting strategies N_i(t) for Player i in game tree t:

  

**Base case:**

- Height 0 tree: N_i(t) = 1 (do nothing)

  

**Recursive cases (with immediate sub-games t₁, t₂, ..., tₙ):**

  

1. **If first move is Player i's:**

- N_i(t) = N_i(t₁) + N_i(t₂) + ... + N_i(tₙ)

- (Sum - choose one branch and strategy for that subgame)

  

2. **If first move is not Player i's:**

- N_i(t) = N_i(t₁) × N_i(t₂) × ... × N_i(tₙ)

- (Product - need strategy for each possible opponent move)

  

![Placeholder: Diagram showing immediate sub-games branching from root]

  

---

  

## Important Considerations

  

### Game Tree vs Game Graph

- Game tree distinguishes positions reached via different histories

- Allows more sophisticated strategies based on complete play history

- Assumes players can remember entire play

- Easier to implement (tree traversal)

  

### Assigning Pay-offs

- Not always obvious how to assign numerical values

- Must accurately reflect preferences and risks

- Critical for meaningful game analysis

- Example: Expected value of lottery is negative, but people play for the chance of winning

  

---

  

## Key Terminology

  

- **Play**: A complete path from root to leaf

- **Subgame**: Game defined by a subtree rooted at some node

- **Ante**: Initial stake in games like poker

	- **Extensive form**: Game represented as a tree

- **Normal form**: Alternative game representation

  

---

  

## Practice Examples

  

### Simple Games to Draw Trees For:

1. **Nim**: Remove matches from piles, player taking last match loses

2. **Chomp**: Eat chocolate squares, avoid poisoned top-left corner

3. **Simplified Poker**: 3-card deck, betting and revealing

  

### Classification Practice:

For each game you know, identify:

- Number of players

- Perfect vs imperfect information

- Zero-sum or not

- With or without chance