# CS471: Introduction to Artificial Intelligence

Projects completed for CS471 Intro to AI at the University of Oregon under Professor Thanh Nguyen. The course is modeled after UC Berkeley's CS188, and the three projects build search, adversarial search, and reinforcement learning agents for the Pacman and Gridworld environments.

All three projects are complete and pass their autograders at full marks:

| Project | Autograder score |
| --- | --- |
| [`search/`](./search) | 25/25 |
| [`multiagent/`](./multiagent) | 25/25 |
| [`reinforcement/`](./reinforcement) | 25/25 |

Last verified on Python 3.14.3.

## Project Overview

### 1. Search Algorithms
Located in [`search/`](./search)

Implements various search algorithms to help Pacman navigate through maze environments:
- **Depth First Search (DFS)**: Explores paths to their deepest level before backtracking
- **Breadth First Search (BFS)**: Explores all paths of the same length before moving deeper
- **Uniform Cost Search**: Finds the shortest path by considering path costs
- **Greedy Search**: Makes decisions based on estimated cost to goal
- **A\* Search**: Combines path cost and heuristic estimates for optimal pathfinding
  - Implementation with pre-defined heuristics
  - Development of custom optimized heuristics
- **Corners and food problems**: Custom state-space formulations with admissible heuristics

Main implementation files: `search.py`, `searchAgents.py`

### 2. Multi-Agent Search
Located in [`multiagent/`](./multiagent)

Focuses on game theory and adversarial search in zero-sum games:
- **Reflex Agent**: Uses basic state evaluation heuristics
- **Minimax Agent**: Implements adversarial search
  - Alpha-Beta Pruning optimization for efficient tree traversal
- **Expectimax Agent**: Handles probabilistic behavior in adversaries
- **Advanced Evaluation Functions**: Enables recursive state evaluation

Main implementation file: `multiAgents.py`

### 3. Reinforcement Learning
Located in [`reinforcement/`](./reinforcement)

Explores fundamental concepts in reinforcement learning across Gridworld, a simulated robot controller (Crawler), and Pacman:
- **Value Iteration**: Implementation of the Bellman equation for optimal value function computation
- **Policy Management**: Development of explicit state-action policies under varying discount, noise, and reward parameters
- **Q-Learning**: Model-free learning from experience
  - Epsilon-Greedy exploration strategy
- **Approximate Q-Learning**: Function approximation over extracted state features

Main implementation files: `valueIterationAgents.py`, `qlearningAgents.py`, `analysis.py`

## Getting Started

Each project is self-contained — there is no shared package or build step. `cd` into a project directory and run its autograder or an individual agent directly.

```bash
cd search
python3 autograder.py                # run all questions
python3 autograder.py -q q3          # run a single question
python3 autograder.py --no-graphics  # run headless (no tkinter needed)
```

Each project directory has its own README with the full list of per-question commands for running individual agents.

## Requirements

- **Python 3.x** — verified on 3.14.3
- **numpy** — required by `reinforcement/` only (`qlearningAgents.py` imports it)
- **tkinter** — required only for the graphical Pacman, Gridworld, and Crawler displays. The autograders run fine without it via `--no-graphics`, but `crawler.py` and the interactive `gridworld.py`/`pacman.py` views need it.

```bash
pip install numpy
```

On Debian/Ubuntu, tkinter comes from the system package manager rather than pip:

```bash
sudo apt install python3-tk
```

## Repository Layout

```
search/           Project 1 — search algorithms
multiagent/       Project 2 — adversarial and probabilistic search
reinforcement/    Project 3 — value iteration and Q-learning
```

Each project directory follows the same structure:

```
autograder.py     Test runner for the project's questions
test_cases/       Per-question test and solution fixtures
layouts/          Pacman maze and Gridworld layout definitions
*TestClasses.py   Project-specific autograder logic
README.md         Per-question commands and file guide
```

## Attribution

The Pacman projects, environments, and autograder infrastructure were developed at UC Berkeley for CS188 by John DeNero, Dan Klein, Pieter Abbeel, and others, and were adapted for CS471. The agent implementations in the files listed above are my own coursework; the surrounding framework code is course-provided and retains its original license headers.

## Course Information

- **Course**: CS471 — Introduction to Artificial Intelligence
- **Institution**: University of Oregon
- **Professor**: Thanh Nguyen
- **Term**: Fall 2024
