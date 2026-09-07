## 2.1: Problem Search and Solving

Classical AI is based on the premise that thinking is computation. Under this approach, solving a problem does not depend on intuition, but on logical algorithms that systematically explore a map of possibilities. Therefore, for a machine to solve a problem, we must translate it into a mathematical language based on the following concepts:

| Concept | Definition |
|---|---|
| **State Space** | The complete “map”: the set of all possible situations the system can be in. |
| **Transitions** | The legal moves or actions that allow the system to move from one state to another. |
| **Costs** | The value of each transition, such as time, distance, or energy. The goal is to minimize the total cost. |

### Problem-Solving Methodology

- **Initial State:** The starting point, such as the current position in a GPS system.
- **Goal State:** The final objective, such as the destination.
- **Filtering:** Identifying and eliminating forbidden states or actions that violate the rules—for example, preventing the fox from eating the chicken.
- **Mechanical Search:** Once the diagram has been defined, the computer performs an automatic search to find the optimal path.

### Why Were Games the First Testing Ground?

During the 1950s and 1960s, AI focused on games such as chess for three reasons:

- **Closed Environments:** Rigid rules with no unexpected events or changes, providing perfect information.
- **Objective Evaluation:** It is easy to program when success has been achieved—the goal state.
- **Prestige and Benchmarking:** Surpassing humans in “intellectual” tasks demonstrated the power of machines.

### Historical Milestones

- **Alan Turing (1936):** Introduced the idea that a universal machine could perform any task, provided it had the appropriate algorithm.
- **John McCarthy (1956):** Coined the term “artificial intelligence” and proposed the McCarthy Conjecture: any aspect of intelligence can be described with enough precision that a machine can simulate it.

# III: Search and Games

## 1. The Concept: Game Trees

A game can be visualized as a **tree**:

- **Root node:** The current board position.
- **Children:** All possible positions resulting from a legal move.
- **Leaves (terminal nodes):** States in which the game ends—win, lose, or draw.

## 2. The Minimax Algorithm

Minimax is a logical strategy for two-player games, such as chess or tic-tac-toe, based on direct competition:

- **MAX (You):** You want to **maximize** the value of the outcome, represented by a score of +1.
- **MIN (Opponent):** The opponent wants to **minimize** the value of the outcome, represented by a score of -1.
- **Logic:** To decide which move to make, the AI looks ahead while assuming that the opponent will always choose the option that is most harmful to you. The value of the current node is determined by propagating values upward from the leaves of the tree.

## 3. Limitations: Combinatorial Explosion

Pure Minimax is impractical for complex games:

- **Chess:** It has more than $10^{120}$ possible variations. Analyzing only 10 moves ahead would require examining trillions of nodes.
- **Heuristics:** Since it is impossible to reach the end of the tree, the search stops at a fixed depth, such as five moves ahead, and uses a **heuristic evaluation function** to estimate which player is in a better position by considering factors such as material, piece placement, and board position.

## 4. Classification of Games for AI

Not all games can be solved in the same way. Minimax works best for games with:

- **Perfect information:** Both players can see the entire board, as in chess and Go.
- **Deterministic outcomes:** There is no element of chance, such as dice rolls or shuffled cards, as in tic-tac-toe.

> **Key Point:** If a game involves chance, such as poker or Monopoly, or contains hidden information, pure Minimax is not sufficient. In those cases, we need to use **probability**, which will be covered in the next chapter.
