# RRT vs RRT\*

A Python implementation and visual comparison of the **RRT (Rapidly-exploring Random Tree)** and **RRT\*** path planning algorithms in a 2D environment with polygonal obstacles.

The project generates an animated visualization showing how both algorithms explore the configuration space and compute a path from a start configuration to a goal configuration.

---

## Overview

This notebook implements and compares:

- **RRT**
  - Fast exploration-based planner
  - Builds a feasible path quickly
  - Does not optimize the final path

- **RRT\***
  - Extension of RRT
  - Includes parent optimization and rewiring
  - Produces shorter and smoother paths over time

The simulation is performed inside a 2D workspace populated with polygonal obstacles using the `Shapely` geometry library.

---

## Features

- Implementation of:
  - Node-based tree structure
  - Collision detection
  - Random configuration sampling
  - Tree expansion
  - Path reconstruction
  - RRT\* rewiring and cost optimization

- Visualization utilities:
  - Obstacle rendering
  - Tree evolution plotting
  - Final path visualization

- Animated comparison:
  - Side-by-side execution of RRT and RRT\*
  - GIF generation of the exploration process

---

## Algorithms

### RRT

The RRT algorithm incrementally builds a tree by:

1. Randomly sampling a point in the configuration space
2. Finding the nearest node already in the tree
3. Extending the tree toward the sampled point
4. Verifying collision-free motion

The algorithm prioritizes fast exploration of unexplored regions.

---

### RRT\*

RRT\* extends RRT with optimization mechanisms:

- **choose_parent**
  - Selects the parent node minimizing path cost

- **rewire**
  - Reconnects nearby nodes if a shorter path is found

Over time, the generated path converges toward an optimal solution.

---

## Project Structure

```text
RRTvsRRTStar.ipynb
```

Main notebook sections:

| Section | Description |
|---|---|
| Node definition | Tree node structure |
| Basic RRT utilities | Distance, nearest node, collision checking |
| RRT implementation | Standard exploration algorithm |
| RRT\* utilities | Cost computation, rewiring |
| RRT\* implementation | Optimized planning algorithm |
| Environment setup | Obstacles and visualization parameters |
| Visualization tools | Plotting and animation |
| Simulation execution | GIF generation and comparison |

---

## Dependencies

Install the required Python libraries:

```bash
pip install matplotlib shapely imageio
```

---

## Usage

Run the notebook:

```bash
jupyter notebook RRTvsRRTStar.ipynb
```

Execute all cells to:

1. Generate a random start and goal configuration
2. Run both RRT and RRT\*
3. Visualize the generated trees
4. Create the animated GIF comparison

---

## Environment

The configuration space:

- Size: `100 x 100`
- Obstacles:
  - Polygonal regions generated with Shapely
  - Collision detection based on segment intersection

Start and goal configurations are sampled randomly in free space.

---
