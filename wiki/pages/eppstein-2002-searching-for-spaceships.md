---
title: "Eppstein (2002), Searching for Spaceships"
category: Sources
summary: David Eppstein's paper on gfind, a spaceship search program for Life and other outer-totalistic rules - spaceships recast as oscillators on a shifted grid, a state space of partial row sequences tied to a de Bruijn graph, a hybrid breadth-first / iterative-deepening search, lookahead, and a bit-parallel graph trick for finding each state's successors; found the weekender (2c/7) in Life and a space-filling c/7 ship in Diamoeba
tags: [source, paper, eppstein, gfind, spaceship, search, de-bruijn, state-space-search, life-like]
sources: [eppstein-2002-searching-for-spaceships]
created: 2026-09-25
updated: 2026-09-26
---

# Eppstein (2002), Searching for Spaceships

**Source:** raw/eppstein-2002-searching-for-spaceships.pdf (arXiv cs/0004003v2 preprint, 17 pp.; published as Eppstein, D., "Searching for spaceships", in R. J. Nowakowski (ed.), *More Games of No Chance*, MSRI Publications 42, 2002, pp. 433-453). Page locators below are the arXiv preprint's.
**Date ingested:** 2026-09-25
**Type:** paper

## Summary

Spaceships are "extremely hard to find" by hand, and Eppstein's program **gfind**
automates the search for large, low-period ones in Life and in any two-state
outer-totalistic Moore-neighbourhood rule.[^1] The paper places gfind in a lineage:
brute force over small patterns, then Hickerson's depth-first cell-by-cell program LS
(1989) and Bell's lifesrc, then Coe's breadth-first program knight (1996), which first
used a de Bruijn graph state space.[^2]

The key move is geometric. Shift the grid along with the spaceship and it becomes an
oscillator. Interleave the rows of all its phases into a single sequence, and the rule
becomes a local condition linking four rows at a time. A spaceship is then a finite row
sequence that starts and ends in 2p blank rows, and the search is a walk through a graph
whose vertices are the last 2p rows, a de Bruijn graph of 2^(2pw) vertices for width
w.[^3] Standard search strategies each fail in some way on this space, so gfind runs
breadth-first until memory fills, then prunes the frontier with bounded depth-first
probes, which delete branches that lead only to dead ends.[^4] Lookahead rejects rows
that cannot be continued, and each state's successors are read off as paths in a small
16-vertex-per-column graph using 64-bit edge masks and a bit-parallel reachability
pass.[^5]

Results include the 2c/7 weekender and Paul Tooke's c/6 dragon in Life, a c/7 Diamoeba
spaceship whose back-to-back pairs fill space (answering a Hickerson prize problem), and
new ships in HighLife, Day & Night and thousands of unnamed rules.[^6] The paper closes
with open questions, including whether it is even decidable if a given rule has a
spaceship of a given speed.[^7]

## Key Takeaways

- A moving pattern is an oscillator in a moving frame; that single change of viewpoint
  turns spaceship search into a one-dimensional row-by-row search.[^3]
- Bounding the width makes a two-dimensional question finite: a de Bruijn graph over
  rows, the same object that decides 1D properties.[^3]
- Search difficulty is not the de Bruijn graph's size; most of it is unreachable, and the
  frontier bulges early instead of growing steadily.[^4][^7]
- Spaceships fall into four classes by how they can be found: small (brute force),
  long and narrow with low period (gfind), engineered from puffers and other parts (by
  hand), and large, high-period, unstructured ones, which should exist but which no
  method can find.[^8]

## Entities & Concepts

- [[row-by-row-search](pages/row-by-row-search.md)] - the methods this paper describes and places in history
- [[spaceship](pages/spaceship.md)], [[de-bruijn-graph](pages/de-bruijn-graph.md)], [[life-like-cellular-automaton](pages/life-like-cellular-automaton.md)]
- [[cordership](pages/cordership.md)], [[puffer](pages/puffer.md)] - the engineered class of spaceships
- [[highlife](pages/highlife.md)] - one of the rules where gfind found new ships
- [[eppstein-gliders-in-life-like-cellular-automata](pages/eppstein-gliders-in-life-like-cellular-automata.md)] - Eppstein's database of spaceships across Life-like rules

## Relation to Other Wiki Pages

The book chapters ([[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)]) describe what spaceships exist; this paper is about how the long,
narrow elementary ones are found. It is the other half of object-finding alongside
[[soup-search](pages/soup-search.md)], which lets random soups do the work. It also
revisits the [[de-bruijn-graph](pages/de-bruijn-graph.md)], known in this wiki from 1D
decidability, as a search engine for 2D patterns of bounded width.

[^1]: [[eppstein-2002-searching-for-spaceships](pages/eppstein-2002-searching-for-spaceships.md)] p.1 [synthesis] - Gardner wrote that spaceships "are extremely hard to find"; "a program, gfind, that can quickly find large low-period spaceships in Life and many related cellular automata"; p.4 "We consider here only outer totalistic rules"
[^2]: [[eppstein-2002-searching-for-spaceships](pages/eppstein-2002-searching-for-spaceships.md)] §2, pp.2-3 [synthesis] - brute force over bounded patterns; Hickerson's LS (1989) with unknown/live/dead states and depth-first branching; Bell's lifesrc adding "don't care"; Coe's knight (1996) using "breadth first search ... on a representation of the problem based on de Bruijn graphs"
[^3]: [[eppstein-2002-searching-for-spaceships](pages/eppstein-2002-searching-for-spaceships.md)] §4, pp.6-8 [synthesis] - "shifting the grid upward k/p units per generation ... so the ship acts like an oscillator"; merged row sequence and equation r[i − p + k] = evolve(r[i − 2p], r[i − p], r[i]); start state of 2p dead rows; states equivalent "if their last 2p rows are identical"; "the number of vertices in this de Bruijn graph is 2^(2pw)"; the weekender search had 2^126 vertices, "most of the vertices ... were unreachable"
[^4]: [[eppstein-2002-searching-for-spaceships](pages/eppstein-2002-searching-for-spaceships.md)] §5, pp.8-10 [synthesis] - drawbacks of depth-first, breadth-first and iterative deepening; "the number of states in the search frontier can fluctuate up and down, and typically has a particularly large bulge in the earlier levels"; depth-first rounds from each breadth-first queue node, removing roots that "lead only to dead ends"
[^5]: [[eppstein-2002-searching-for-spaceships](pages/eppstein-2002-searching-for-spaceships.md)] §§6-7, pp.10-14 [synthesis] - lookahead equation (L) and approximate double lookahead (LL); graph of 16 vertices per column (2 × 2 blocks); 64 possible edges per column pair stored as a 64-bit quantity; 16-bit reachability sets; backtracking that "never reaches a dead end"
[^6]: [[eppstein-2002-searching-for-spaceships](pages/eppstein-2002-searching-for-spaceships.md)] p.1 [synthesis] - the weekender 2c/7, Tooke's c/6 dragon, a c/7 Diamoeba spaceship; "two back-to-back copies of these spaceships form a pattern that fills space"; Hickerson's 1993 open problem "with a $50 bounty"; "new spaceships in well known rules such as HighLife and Day&Night as well as in thousands of unnamed rules"
[^7]: [[eppstein-2002-searching-for-spaceships](pages/eppstein-2002-searching-for-spaceships.md)] §8, pp.15-16 [synthesis] - open questions: whether the three state spaces differ asymptotically; the frontier fluctuations; "our searches typically examine far fewer nodes than are present in the de Bruijn graph"; "Is the problem of determining whether a given outer totalistic rule has a spaceship of a given speed or period even decidable?"; automating Bell's human-guided arm searches; predecessor search; Bays's 3D and triangular rules
[^8]: [[eppstein-2002-searching-for-spaceships](pages/eppstein-2002-searching-for-spaceships.md)] §3, pp.5-6 [synthesis] - small ships "found by brute force search"; low period with one small dimension found by "search algorithms similar to the ones described in this paper"; puffers or replicators "combined by human engineering into a spaceship", e.g. the Cordership; "large size, large period, and little internal structure. We believe such spaceships should exist, but none are known and we know of no effective method for finding them"
