---
title: von Neumann neighbourhood
category: Concepts
summary: The four cells orthogonally adjacent to a cell (Manhattan distance 1), named for von Neumann's 29-state automaton; 2n cells in n dimensions and 2n(n+1) at range n; with two states and no B1 nothing can leave its bounding box, so spaceships need a third state; written with a V suffix (B1/S0V)
tags: [concept, neighbourhood, von-neumann, manhattan-distance, lattice]
sources: [lifewiki-von-neumann-neighbourhood, lifewiki-rulestring, lifewiki-larger-than-life, lifewiki-higher-range-outer-totalistic-rule, lifewiki-higher-range-isotropic-non-totalistic-rule, lifewiki-apgsearch, lifewiki-unit-cell]
created: 2026-09-25
updated: 2026-09-25
---

# von Neumann neighbourhood

## Description

The *von Neumann neighbourhood* of a region is the set of cells orthogonally adjacent to
it. For a single cell it is the four cells sharing an edge with it, the cells at
Manhattan distance 1. Whether the cell itself counts depends on context.[^1] So the same
neighbourhood is described as four cells here and as five cells (cell plus four) in
[[moore-neighbourhood](pages/moore-neighbourhood.md)]'s general definitions. It is named
after John von Neumann, creator of the first self-replicating cellular automaton,
whose 29-state rule ([[von-neumann-29-state-ca](pages/von-neumann-29-state-ca.md)]) uses
it.[^1]

**Size.**[^2]
- In n dimensions a cell has 2n von Neumann neighbours: 4 in the plane, 6 in 3D, where
  they form an octahedron.
- Range n is defined by iterating: the von Neumann neighbourhood of the range-(n - 1)
  neighbourhood. A single cell's range-n neighbourhood has 2n(n + 1) cells, a diamond.
- The Moore neighbourhood grows as a square instead, so at range 1 it has twice as many
  neighbours (8 against 4) (own reasoning).

**Why two states are not enough for spaceships.** In a two-state rule on this
neighbourhood, a pattern cannot leave its bounding box without B1, birth on a single
neighbour, and B1 makes every pattern grow at the speed of light. So spaceships are
impossible.[^3] The reason is geometric (own reasoning): a dead cell just outside a
pattern's bounding box touches at most one cell inside it orthogonally, so only a
one-neighbour birth can put a live cell there. Adding a third state breaks the barrier:
one three-state rule has many spaceships, rakes and breeders.[^3] B1 rules are
not dull, though. The Larger than Life rule Gnarl, R1,C2,S0,B1,NN or **B1/S0V**, is an
exploding rule by Kellie Evans ([[larger-than-life](pages/larger-than-life.md)]).[^4]

**Isotropic rules.** Up to rotation and reflection, the four neighbours have only six
arrangements, so there are few isotropic rules.[^5] With six arrangements each for birth
and survival, that gives 2^12 two-state isotropic von Neumann rules (own reasoning). They
all fit inside the [[isotropic-non-totalistic-rule](pages/isotropic-non-totalistic-rule.md)]
Moore rules, and that is how [[apgsearch](pages/apgsearch.md)] searches them: as isotropic
Moore rules that ignore the corners.[^6] At range 2 the count jumps to 618 arrangements.[^5]

**In rulestrings and software.** A trailing **V** marks a von Neumann rule
([[rulestring](pages/rulestring.md)]); in range-based notation the code is **NN**
([[higher-range-outer-totalistic-rule](pages/higher-range-outer-totalistic-rule.md)]).[^7]

**Universality.** Banks-I, an early two-state rule on this neighbourhood, is logically
universal, as shown with a Rule 110 unit cell; Roger Banks's own proofs date to
1971.[^8]

## Appearances in Sources

- [[lifewiki-von-neumann-neighbourhood](pages/lifewiki-von-neumann-neighbourhood.md)] - the whole article
- [[lifewiki-rulestring](pages/lifewiki-rulestring.md)] - the V suffix
- [[lifewiki-larger-than-life](pages/lifewiki-larger-than-life.md)] - Gnarl, B1/S0V
- [[lifewiki-higher-range-isotropic-non-totalistic-rule](pages/lifewiki-higher-range-isotropic-non-totalistic-rule.md)] - transition counts at ranges 1 and 2
- [[lifewiki-apgsearch](pages/lifewiki-apgsearch.md)] - searching von Neumann rules as isotropic Moore rules
- [[lifewiki-unit-cell](pages/lifewiki-unit-cell.md)] - Banks-I

## Related Concepts

- [[moore-neighbourhood](pages/moore-neighbourhood.md)] - the eight-cell square neighbourhood that contains it
- [[hexagonal-neighbourhood](pages/hexagonal-neighbourhood.md)] - the six-cell neighbourhood of the hexagonal grid
- [[margolus-neighbourhood](pages/margolus-neighbourhood.md)] - a block partition, not a neighbourhood of this kind
- [[von-neumann-29-state-ca](pages/von-neumann-29-state-ca.md)] - the rule it is named after
- [[metacell](pages/metacell.md)] - the 0E0P metacell works by emulating an 8-state von Neumann rule

[^1]: [[lifewiki-von-neumann-neighbourhood](pages/lifewiki-von-neumann-neighbourhood.md)] L7 - "the set of all cells that are orthogonally adjacent to the region of interest (the region of interest itself may or may not be considered part of the von Neumann neighbourhood, depending on context) ... named after John von Neumann, the creator of the first self-replicating cellular automaton"; L9 "the points at a Manhattan distance of 1 from that cell"
[^2]: [[lifewiki-von-neumann-neighbourhood](pages/lifewiki-von-neumann-neighbourhood.md)] L8,L13 [synthesis] - "a 6-cell octahedral neighborhood for a cellular automaton in three dimensions"; 2n cells in n dimensions; range n defined recursively; "The number of cells in the von Neumann neighbourhood of range n of a single cell is given by 2 n (n + 1)"
[^3]: [[lifewiki-von-neumann-neighbourhood](pages/lifewiki-von-neumann-neighbourhood.md)] L11 - "With two states, patterns cannot escape their bounding box without B1, which causes patterns to grow at the speed of light, so spaceships are impossible. However, a three-state rule has been found in which many spaceships (and rakes and breeders) exist"
[^4]: [[lifewiki-larger-than-life](pages/lifewiki-larger-than-life.md)] L52-55 - "R1,C2,S0,B1,NN B1/S0V Gnarl an exploding rule by Kellie Evans"
[^5]: [[lifewiki-higher-range-isotropic-non-totalistic-rule](pages/lifewiki-higher-range-isotropic-non-totalistic-rule.md)] L120-127,L208-217 [synthesis] - range-1 von Neumann, 2 states: 6 transitions; R2 von Neumann INT: 618 transitions
[^6]: [[lifewiki-apgsearch](pages/lifewiki-apgsearch.md)] L97,L107 [synthesis] - "Isotropic von Neumann neighbourhood rules. (implicitly by isotropic non-totalistic Moore neighbourhood rules)"; "the von Neumann neighbourhood can be indirectly simulated by isotropic Moore rules"
[^7]: [[lifewiki-rulestring](pages/lifewiki-rulestring.md)] L13 - "a suffixed V indicates that the CA in question uses the von Neumann neighbourhood"; [[lifewiki-higher-range-outer-totalistic-rule](pages/lifewiki-higher-range-outer-totalistic-rule.md)] L20 - "NN for von Neumann neighbourhood"
[^8]: [[lifewiki-von-neumann-neighbourhood](pages/lifewiki-von-neumann-neighbourhood.md)] L19 - "Banks-I, an early two-state Von Neumann rule"; [[lifewiki-unit-cell](pages/lifewiki-unit-cell.md)] L44 - "Banks-I: proves logic universality using Matthew Cook's results, simplifying Roger Banks' proofs from 1971"
