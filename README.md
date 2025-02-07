# Shortest Path Problem - Optimization & Code Implementation

## Overview

This project focuses on an optimization problem where code has been developed to solve a generalized shortest path problem. Unlike the standard shortest path problem, this version allows cycles and negative costs, making it a more complex variation inspired by the Traveling Salesman Problem (TSP). The project implements a branch-and-cut algorithm  with separation procedures for both integer and fractional solutions, to efficiently handle these complexities.

## Problem Description

The shortest path is determined in a Directed Graph G = (V, A).

Unlike classical shortest path problems, this formulation allows cycles and negative costs, requiring specialized constraints to avoid infeasible solutions.

The problem is framed using integer and fractional programming, with binary decision variables xij to indicate arc selection.

## Key Formulation

The optimization problem is formulated as follows:

### Objective Function:

Minimize the total path cost:


### Constraints:

- The source node s has exactly one outgoing edge.

- The sink node t has exactly one incoming edge.

- Flow conservation at intermediate nodes ensures proper path formation.

- Each node has at most one outgoing arc in the solution.

- xij values are binary (0 or 1).

## Challenges & Extensions

- Negative Cost Cycles: The standard formulation does not work when negative cycles exist.

- Subtour Elimination Constraints (SECs):

  - The classical TSP-inspired SECs fail to prevent subtours.

  - A corrected SEC is proposed to address this issue.

## Implementation Details

A branch-and-cut algorithm is implemented to solve the problem efficiently.

A separation procedure is devised to enforce the correct subtour elimination constraints.

The algorithm is tested on complete graphs, which inherently contain cycles, and graphs with negative-cost cycles to validate its robustness.
