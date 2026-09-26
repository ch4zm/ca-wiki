---
title: Row-by-row spaceship search
category: Concepts
summary: Finding spaceships by program - brute force over small patterns, depth-first cell-by-cell search (Hickerson's LS, Bell's lifesrc), and row-by-row search over a de Bruijn graph of partial patterns (Coe's knight, Eppstein's gfind), made possible by viewing a spaceship as an oscillator on a moving grid
tags: [concept, method, search, spaceship, gfind, lifesrc, de-bruijn, state-space-search]
sources: [eppstein-2002-searching-for-spaceships]
created: 2026-09-25
updated: 2026-09-25
---

# Row-by-row spaceship search

## Description

Random soups mostly yield small, common objects ([[soup-search](pages/soup-search.md)]).
Rarer [[spaceship](pages/spaceship.md)]s are found by programs that search directly for
a pattern with a given period and displacement.

**Three generations of method.**[^1]
- **Brute force.** Try every pattern in a small box, every pattern with few live cells,
  or combinations of known parts, exhaustively or at random. Symmetric boxes up to about
  7 × 8 are feasible, and such searches can turn up ships as large as 12 × 15. This is
  how small ships of high period are found in many rules.
- **Depth-first, cell by cell.** Dean Hickerson's LS (1989) fixes a box and stores, for
  every cell in every generation, *unknown*, *live* or *dead*. It deduces what it can from
  neighbours in the previous and next generations, and branches on one cell when stuck.
  It found Life's c/3, c/4 and 2c/5 orthogonal ships. David Bell's lifesrc adds a
  *don't care* state.
- **Row by row, over a de Bruijn graph.** Tim Coe's knight (1996), which found Life's c/5
  ship, and Eppstein's gfind build the pattern one row at a time.

**The moving frame.** A spaceship moving k cells every p generations is an
[[oscillator](pages/oscillator.md)] on a grid that shifts k/p cells per generation. With
gcd(k, p) = 1, each row of each phase sits at its own height, so all phases interleave
into one sequence of rows. The rule then becomes a condition on four rows at a time:
r[i − p + k] = evolve(r[i − 2p], r[i − p], r[i]). Any finite sequence that obeys it and
starts and ends with 2p blank rows is a spaceship.[^2] Glide-reflect and diagonal ships
need only small changes to the equation.[^2]

**The graph.** Two partial patterns with the same last 2p rows have the same possible
futures, so the search lives on a de Bruijn graph whose vertices are those 2p-row
windows: 2^(2pw) vertices at width w. Bounding the width is what makes the space finite
(own reasoning, connecting to [[de-bruijn-graph](pages/de-bruijn-graph.md)]: fixing the
width reduces a 2D question to a 1D one, where de Bruijn graphs are exactly the tool that
works).[^3] The graph's size is only a rough guide, since most of it is unreachable.[^3]

**gfind's search.**[^4]
- Breadth-first search until memory fills (by default 2^22 nodes).
- Then a depth-first probe from each frontier node, a few levels past the frontier. A
  probe that finishes without finding anything proves its root is a dead end, and the
  root is deleted. The survivors are compacted and breadth-first search resumes.
- This beats pure iterative deepening because the frontier here does not grow steadily:
  it bulges early and then fluctuates.
- Lookahead only accepts a new row if the row that will next depend on it can also be
  completed.
- Successor rows are paths through a graph of 2 × 2 cell blocks, 16 per column. The
  edges allowed by the rule are 64-bit masks read from precomputed tables, and a
  bit-parallel reachability pass means the backtracking never hits a dead end.

**What it finds, and what it cannot.** Row-by-row search suits ships that are long but
narrow with low period: the 2c/7 weekender in Life, a c/2 ship 42 cells wide in B27/S0,
and a c/7 ship in Diamoeba (B35678/S5678) whose back-to-back pairs fill space.[^5]
Engineered ships built from [[puffer](pages/puffer.md)]s, such as the
[[cordership](pages/cordership.md)], are designed by hand. Large, high-period ships with
no internal structure should exist, but no known method finds them.[^6]

**Open questions.** Why the frontier fluctuates, whether the different state spaces
really differ in power, and whether it is even decidable if a given rule has a spaceship
of a given speed.[^7]

## Appearances in Sources

- [[eppstein-2002-searching-for-spaceships](pages/eppstein-2002-searching-for-spaceships.md)] - the history, the state space and gfind's algorithms

## Related Concepts

- [[soup-search](pages/soup-search.md)] - the other way to find objects: let random patterns do the work
- [[de-bruijn-graph](pages/de-bruijn-graph.md)] - the graph the row-by-row search walks
- [[spaceship](pages/spaceship.md)] - what is being searched for
- [[oscillator](pages/oscillator.md)] - a spaceship in a moving frame
- [[decidability-in-cellular-automata](pages/decidability-in-cellular-automata.md)] - the open question of whether spaceship existence is decidable

[^1]: [[eppstein-2002-searching-for-spaceships](pages/eppstein-2002-searching-for-spaceships.md)] §2, pp.2-3 [synthesis] - brute force "tests patterns of bounded size, patterns with a bounded number of live cells, or patterns formed out of a small number of known building blocks"; "all patterns that fit within rectangles of up to 7×8 cells (assuming symmetric initial conditions)"; ships "as large as 12 × 15"; Hickerson's LS (1989) storing "unknown, live, or dead" and "a depth first branching step"; c/3, c/4 and 2c/5; Bell's lifesrc "added a fourth 'don't care' state"; Coe's knight (1996), c/5, breadth-first on de Bruijn graphs
[^2]: [[eppstein-2002-searching-for-spaceships](pages/eppstein-2002-searching-for-spaceships.md)] §4, pp.6-7 [synthesis] - "shifting the grid upward k/p units per generation ... so the ship acts like an oscillator"; with gcd(k, p) = 1 "each row of each phase of the pattern exists at a distinct vertical position"; equation (∗); "any finite sequence of rows can be extended ... if the first and last 2p rows ... contain only dead cells"; modifications for diagonal and glide-reflect ships
[^3]: [[eppstein-2002-searching-for-spaceships](pages/eppstein-2002-searching-for-spaceships.md)] §4, pp.7-8 [synthesis] - "two states are equivalent if their last 2p rows are identical"; the de Bruijn graph has 2^(2pw) vertices; the weekender search: width nine, 2^126 vertices, "most of the vertices in this graph were unreachable"
[^4]: [[eppstein-2002-searching-for-spaceships](pages/eppstein-2002-searching-for-spaceships.md)] §§5-7, pp.8-14 [synthesis] - storage for 2^22 nodes; depth-first rounds δ levels beyond the frontier; roots that "lead only to dead ends" removed; frontier "can fluctuate up and down, and typically has a particularly large bulge in the earlier levels"; lookahead (L) and approximate (LL); 16 vertices per column, 64-bit edge sets from table lookups, 16-bit reachability; "the third stage never reaches a dead end"
[^5]: [[eppstein-2002-searching-for-spaceships](pages/eppstein-2002-searching-for-spaceships.md)] pp.1-2,5-6,11 [synthesis] - the weekender; "c/2 spaceships with minimum dimension as high as 42" (Fig. 10, B27/S0); the Diamoeba c/7 ship and Bell's space-filling pair
[^6]: [[eppstein-2002-searching-for-spaceships](pages/eppstein-2002-searching-for-spaceships.md)] §3, p.6 [synthesis] - puffers, wickstretchers or replicators "combined by human engineering into a spaceship", e.g. Hickerson's c/12 Cordership; "large size, large period, and little internal structure. We believe such spaceships should exist, but none are known and we know of no effective method for finding them"
[^7]: [[eppstein-2002-searching-for-spaceships](pages/eppstein-2002-searching-for-spaceships.md)] §8, pp.15-16 [synthesis] - "Do these spaces really lead to different asymptotic search performance"; "Is it possible to explain the observed fluctuations"; "Is the problem of determining whether a given outer totalistic rule has a spaceship of a given speed or period even decidable?"
