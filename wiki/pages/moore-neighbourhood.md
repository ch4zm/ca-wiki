---
title: Moore Neighbourhood
category: Concepts
summary: The nine-cell neighbourhood (a cell plus its eight orthogonal and diagonal neighbours) that Moore used for tessellation structures; contains the five-cell von Neumann neighbourhood as a special case
tags: [concept, neighbourhood, moore, lattice]
sources: [bays-1987-candidates-for-the-game-of-life-in-three-dimensions, lifewiki-von-neumann-neighbourhood, lifewiki-hexagonal-neighbourhood, lifewiki-higher-range-outer-totalistic-rule, cgol-ch1-early-life, fantastic-combinations-of-john-conways-life, machine-models-of-self-reproduction, theory-of-cellular-automata-a-survey]
created: 2026-09-24
updated: 2026-09-25
---

# Moore Neighbourhood

## Description

The Moore neighbourhood of a cell on the square lattice is the 3 × 3 block centred on it:
the cell itself and every cell whose coordinates each differ from it by at most 1. [[edward-f-moore](pages/edward-f-moore.md)]
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
chosen four neighbours over eight to keep the rule simple.[^4] Whether the centre cell
counts as part of a neighbourhood is a convention that depends on context. LifeWiki
describes the [[von-neumann-neighbourhood](pages/von-neumann-neighbourhood.md)] as the four
orthogonal cells, and Life-like rules count eight neighbours, while Moore and Kari include
the centre.[^5]

**Other shapes.** On the hexagonal grid the analogue is the six-cell
[[hexagonal-neighbourhood](pages/hexagonal-neighbourhood.md)]. Higher-range rules
([[higher-range-outer-totalistic-rule](pages/higher-range-outer-totalistic-rule.md)]) make
the neighbourhood a free choice among Moore, von Neumann, circular, cross, star and more;
Moore is the default there.[^6]

**In three dimensions.** The cubic analogue touches 26 cells: 6 across faces, 12 across
edges and 8 at corners. Carter Bays's 3D Games of Life, B6/S567 and B5/S45, count all 26
([[three-dimensional-life](pages/three-dimensional-life.md)]).[^7]

**Radius and speed.** Because each step reads only cells at distance 1, the non-quiescent
region can grow by at most one cell per step in each direction. This gives Moore's
quadratic bound on the number of offspring of a self-reproducing configuration
([[self-reproduction](pages/self-reproduction.md)]) and confines incoming information to a
thin boundary layer in the proof of the
[[garden-of-eden](pages/garden-of-eden.md)] theorem ([[garden-of-eden-theorem](pages/garden-of-eden-theorem.md)]).[^8]

**General definitions (Kari 2005).** In d dimensions, the *von Neumann neighbourhood*
is all offsets of Manhattan norm at most 1, giving 2d + 1 cells, and the *Moore
neighbourhood* is all offsets of max-norm at most 1, giving 3ᵈ cells. Replacing 1 by r
gives the *radius-r* neighbourhoods, so the Moore neighbourhood has radius 1. The
*radius-½* neighbourhood has offsets whose coordinates are all 0 or 1. In one dimension
that is (0, 1), the *one-way* CA (OCA), where information cannot flow in the positive
direction.[^9] One-way rules are used in the XOR counterexamples to the
[[garden-of-eden-theorem](pages/garden-of-eden-theorem.md)], in Kari's 1D nilpotency
proof ([[limit-set](pages/limit-set.md)]), and in
[[language-recognition-by-cellular-automata](pages/language-recognition-by-cellular-automata.md)].[^10]
The [[margolus-neighbourhood](pages/margolus-neighbourhood.md)] is not a neighbourhood in
this sense at all. It partitions the plane into blocks.[^11]

## Appearances in Sources

- [[lifewiki-von-neumann-neighbourhood](pages/lifewiki-von-neumann-neighbourhood.md)] - the centre cell may or may not count, by context
- [[lifewiki-higher-range-outer-totalistic-rule](pages/lifewiki-higher-range-outer-totalistic-rule.md)] - Moore as one of many HROT neighbourhoods
- [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] - von Neumann and Moore neighbourhoods in d dimensions; radius r; radius-½ and one-way CA
- [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] - defines the nine-cell neighbourhood for tessellation structures
- [[tsra-part2-ch2](pages/tsra-part2-ch2.md)] - von Neumann's choice of four neighbours over eight
- [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] - Life's eight neighbours, four orthogonal and four diagonal
- [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] - Moore vs von Neumann neighbourhoods; the Life-like rule family on the eight-cell neighbourhood

## Related Concepts

- [[three-dimensional-life](pages/three-dimensional-life.md)] - Bays's rules on the 26-cell 3D neighbourhood
- [[triangular-neighbourhood](pages/triangular-neighbourhood.md)] - the 12-cell neighbourhood of the triangular grid

- [[cellular-automaton](pages/cellular-automaton.md)] - the neighbourhood is part of every rule
- [[game-of-life](pages/game-of-life.md)] - the best-known rule on the eight-cell neighbourhood
- [[life-like-cellular-automaton](pages/life-like-cellular-automaton.md)] - all 262,144 count-based two-state rules on it
- [[von-neumann-29-state-ca](pages/von-neumann-29-state-ca.md)] - uses the five-cell von Neumann neighbourhood
- [[garden-of-eden](pages/garden-of-eden.md)] - the boundary-layer counting depends on the neighbourhood radius
- [[margolus-neighbourhood](pages/margolus-neighbourhood.md)] - a block-partition scheme, not a neighbourhood vector
- [[von-neumann-neighbourhood](pages/von-neumann-neighbourhood.md)] - the four orthogonal neighbours it contains
- [[hexagonal-neighbourhood](pages/hexagonal-neighbourhood.md)] - the hexagonal-grid counterpart
- [[language-recognition-by-cellular-automata](pages/language-recognition-by-cellular-automata.md)] - one-way CA as language recognizers

[^1]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] p.21 [synthesis] - neighbours are all cells, including the cell itself, whose coordinates differ by at most 1; all nine cells of Fig. 2 are neighbours of X; the neighbours of a rectangular array then form a rectangle; "The exact definition of neighbor used is not too important."
[^2]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] p.21 [synthesis] - in the formal quintuple, f maps the states of the 3^N neighbours of a cell at T − 1 to its state at T
[^3]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] p.21 [synthesis] - von Neumann's construction uses the five cells V and X of Fig. 2; his definition is included by making the next state independent of the D cells
[^4]: [[tsra-part2-ch2](pages/tsra-part2-ch2.md)] pp.132-134 [synthesis] - the four nearest neighbours chosen over eight for simplicity
[^5]: [[lifewiki-von-neumann-neighbourhood](pages/lifewiki-von-neumann-neighbourhood.md)] L7 - "the region of interest itself may or may not be considered part of the von Neumann neighbourhood, depending on context). For example, the von Neumann neighbourhood of a single cell consists of the four cells orthogonally touching it"
[^6]: [[lifewiki-hexagonal-neighbourhood](pages/lifewiki-hexagonal-neighbourhood.md)] L7 [synthesis] - "the set of all cells that are adjacent to the region of interest ... on the hexagonal tiling"; [[lifewiki-higher-range-outer-totalistic-rule](pages/lifewiki-higher-range-outer-totalistic-rule.md)] L17-36 [synthesis] - "Nn specifies the extended neighborhood type and can be omitted for the Moore neighbourhood"; the neighbourhood codes
[^7]: [[bays-1987-candidates-for-the-game-of-life-in-three-dimensions](pages/bays-1987-candidates-for-the-game-of-life-in-three-dimensions.md)] pp.375,393 [synthesis] - "In three dimensions, a cell can have from 0 to 26 living neighbors"; "six 'face' neighbors, twelve 'edge' neighbors and eight 'corner' neighbors"; only 4555 and 5766 satisfy definition 1
[^8]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] pp.23, 29 [synthesis] - each unit of time lets the non-quiescent region grow only one cell in each direction; local action confines information from outside an array to a thin boundary layer
[^9]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.5 [synthesis] - von Neumann neighbourhood ‖y‖₁ ≤ 1 with 2d + 1 neighbours; Moore neighbourhood ‖y‖∞ ≤ 1 with 3ᵈ neighbours; radius-r CA; "Moore neighborhood is of radius 1"; radius-½ offsets with each yᵢ 0 or 1; "A one-dimensional, radius-½ CA is also called one-way, or OCA for short"; information cannot flow to the positive direction
[^10]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.16, 24, 29 [synthesis] - XOR is "a one-dimensional radius-½ CA"; the 1D nilpotency construction uses neighbourhood (0, 1); one-way CA (OCA) in language recognition
[^11]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.18 - "Strictly speaking Margolus neighborhood is not a CA neighborhood in the sense of our definitions."
