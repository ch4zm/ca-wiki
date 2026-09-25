---
title: Moore Neighbourhood
category: Concepts
summary: The nine-cell neighbourhood (a cell plus its eight orthogonal and diagonal neighbours) that Moore used for tessellation structures; contains the five-cell von Neumann neighbourhood as a special case
tags: [concept, neighbourhood, moore, lattice]
sources: [machine-models-of-self-reproduction]
created: 2026-09-24
updated: 2026-09-24
---

# Moore Neighbourhood

## Description

The Moore neighbourhood of a cell on the square lattice is the 3 × 3 block centred on it:
the cell itself and every cell whose coordinates each differ from it by at most 1. Moore
uses this definition in his 1962 paper, where all nine cells of his Fig. 2 count as
neighbours of the centre cell. The name "Moore neighbourhood" is later usage.[^1]

**Why Moore chose it.** With this definition the neighbours of a rectangular array form a
rectangle, which makes it easier to count the cells in the arrays his proofs use. He adds
that the exact definition of neighbour "is not too important".[^1] In N dimensions the
same rule gives 3^N neighbours.[^2]

**Relation to von Neumann's neighbourhood.** Von Neumann's rule depends only on the cell
and its four orthogonal neighbours, five cells in all
([[von-neumann-29-state-ca](pages/von-neumann-29-state-ca.md)]). Moore includes this as a
special case: a rule on nine cells that ignores the four diagonal ones.[^3] Von Neumann had
chosen four neighbours over eight to keep the rule simple.[^4]

**Radius and speed.** Because each step reads only cells at distance 1, the non-quiescent
region can grow by at most one cell per step in each direction. This gives Moore's
quadratic bound on the number of offspring of a self-reproducing configuration
([[self-reproduction](pages/self-reproduction.md)]) and confines incoming information to a
thin boundary layer in the proof of the
[[garden-of-eden](pages/garden-of-eden.md)] theorem.[^5]

## Appearances in Sources

- [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] - defines the nine-cell neighbourhood for tessellation structures
- [[tsra-part2-ch2](pages/tsra-part2-ch2.md)] - von Neumann's choice of four neighbours over eight

## Related Concepts

- [[cellular-automaton](pages/cellular-automaton.md)] - the neighbourhood is part of every rule
- [[von-neumann-29-state-ca](pages/von-neumann-29-state-ca.md)] - uses the five-cell von Neumann neighbourhood
- [[garden-of-eden](pages/garden-of-eden.md)] - the boundary-layer counting depends on the neighbourhood radius

[^1]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] p.21 [synthesis] - neighbours are all cells, including the cell itself, whose coordinates differ by at most 1; all nine cells of Fig. 2 are neighbours of X; the neighbours of a rectangular array then form a rectangle; "The exact definition of neighbor used is not too important."
[^2]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] p.21 [synthesis] - in the formal quintuple, f maps the states of the 3^N neighbours of a cell at T − 1 to its state at T
[^3]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] p.21 [synthesis] - von Neumann's construction uses the five cells V and X of Fig. 2; his definition is included by making the next state independent of the D cells
[^4]: [[tsra-part2-ch2](pages/tsra-part2-ch2.md)] pp.132-134 [synthesis] - the four nearest neighbours chosen over eight for simplicity
[^5]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] pp.23, 29 [synthesis] - each unit of time lets the non-quiescent region grow only one cell in each direction; local action confines information from outside an array to a thin boundary layer
