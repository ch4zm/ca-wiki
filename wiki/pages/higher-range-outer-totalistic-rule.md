---
title: Higher-range outer-totalistic rule
category: Rules
summary: HROT - rules where a cell's fate depends on its own state and the count of live cells in a neighbourhood of any range, with arbitrary lists of birth and survival counts; generalizes both Life-like rules and Larger than Life, allows Generations-style decay, and is written Rr,Cc,Slist,Blist,Nn over sixteen neighbourhood shapes in Golly
tags: [rule-family, hrot, higher-range, outer-totalistic, rulestring, golly, neighbourhood]
sources: [lifewiki-higher-range-outer-totalistic-rule, lifewiki-higher-range-isotropic-non-totalistic-rule, lifewiki-larger-than-life, lifewiki-apgsearch, lifewiki-catagolue, lifewiki-hexagonal-neighbourhood]
created: 2026-09-25
updated: 2026-09-25
---

# Higher-range outer-totalistic rule

## Description

A *higher-range outer-totalistic* (HROT) rule works like a
[[life-like-cellular-automaton](pages/life-like-cellular-automaton.md)] over a bigger
neighbourhood. A cell's next state depends on its own state and on how many live cells
lie within range r. A live cell follows the survival list and a dead cell the birth list,
and either list can be any set of counts.[^1] It generalizes in two directions at once:[^1]
- **From Life-like rules**, by letting the range exceed 1.
- **From [[larger-than-life](pages/larger-than-life.md)]**, by dropping LtL's requirement
  that birth and survival each be a single interval of counts.

Like LtL, it also allows extra decaying states, as in a
[[generations-rule](pages/generations-rule.md)].[^1]

**How big the space is.** A range-r Moore neighbourhood has (2r + 1)^2 - 1 cells around
the centre, so a live count can take (2r + 1)^2 values, and each value is independently in
or out of the birth list and the survival list. That gives 2^18 rules at range 1, the
Life-like family, and 2^50 at range 2 (own reasoning). LtL keeps only the rules whose two
lists are intervals, a thin slice of this space (own reasoning).

**Notation.** HROT rules are written **Rr,Cc,Slist,Blist,Nn**:[^2]
- **R**: the range, 1 to 500 in Golly (1 to 250 on the triangular grid).
- **C**: the number of states, 0 to 256.
- **S** and **B**: survival and birth counts, comma-separated, with dashes for runs, as
  S6-8,13-14,18.[^3]
- **N**: the neighbourhood shape. It is omitted for Moore.

**Neighbourhood shapes.** HROT is where the neighbourhood itself becomes a free
parameter. Golly offers Moore (M), von Neumann (N), circular (C), Euclidean (2),
checkerboard and aligned checkerboard (B, D), hash (#), cross (+), saltire (X), star (*),
hexagonal (H), asterisk (A), tripod (3), triangular (L), custom (@) and weighted (W);
LifeViewer adds far corners/edges (F).[^2] Rules in the Larger than Life example table
show what these allow:[^4]
- Marine, R2,C2,S4,6-9,B6-8,N@03ddef, uses a custom neighbourhood (@) given as a code string,
  and its survival list is not an interval, so it is HROT but not LtL (own reasoning).
- Coexistence uses a weighted neighbourhood, in which cells at different offsets count
  with different weights (own reading of the NW code).
- Factorio (R3,C2,S2,B3,N+) uses a cross and Hash (R2,C2,S4-6,B5-6,N#) a hash-shaped
  neighbourhood.

**Where it runs.** Golly from version 4.0 and LifeViewer simulate HROT rules, including
hexagonal ones.[^5] [[apgsearch](pages/apgsearch.md)] can soup-search them up to range 5,
and [[catagolue](pages/catagolue.md)] accepts outer-totalistic rules of range 1 to 5.[^6]

**Isotropic extension.** Letting the arrangement of the live cells matter, not only their
number, gives higher-range isotropic non-totalistic rules
([[isotropic-non-totalistic-rule](pages/isotropic-non-totalistic-rule.md)]). There the
number of cases to specify explodes, and most such rulespaces have no notation at all.[^7]

## Appearances in Sources

- [[lifewiki-higher-range-outer-totalistic-rule](pages/lifewiki-higher-range-outer-totalistic-rule.md)] - the whole article
- [[lifewiki-larger-than-life](pages/lifewiki-larger-than-life.md)] - HROT notation and example rules
- [[lifewiki-apgsearch](pages/lifewiki-apgsearch.md)], [[lifewiki-catagolue](pages/lifewiki-catagolue.md)] - soup search up to range 5
- [[lifewiki-hexagonal-neighbourhood](pages/lifewiki-hexagonal-neighbourhood.md)] - hexagonal HROT support

## Related Concepts

- [[larger-than-life](pages/larger-than-life.md)] - the one-interval special case
- [[life-like-cellular-automaton](pages/life-like-cellular-automaton.md)] - the range-1 two-state case
- [[generations-rule](pages/generations-rule.md)] - decay through extra states
- [[moore-neighbourhood](pages/moore-neighbourhood.md)], [[von-neumann-neighbourhood](pages/von-neumann-neighbourhood.md)], [[hexagonal-neighbourhood](pages/hexagonal-neighbourhood.md)] - some of the neighbourhood shapes
- [[rulestring](pages/rulestring.md)] - how HROT rules are written

[^1]: [[lifewiki-higher-range-outer-totalistic-rule](pages/lifewiki-higher-range-outer-totalistic-rule.md)] L7-8 [synthesis] - "a natural generalization of Larger than Life (LtL) rules, and separately a generalization of outer-totalistic rules"; "Unlike LtL, HROT rules allow to define any list of birth and survival conditions. The new state of a cell in the next generation is a function of the number of cells in its neighbourhood and the cell's own state"; "It also supports higher range Generations rules"
[^2]: [[lifewiki-higher-range-outer-totalistic-rule](pages/lifewiki-higher-range-outer-totalistic-rule.md)] L12-36 [synthesis] - notation Rr,Cc,Slist,Blist,Nn; "Golly supports r from 1 to 500, except for the Triangular neighbourhood where r is from 1 to 250"; "Golly supports c from 0 to 256"; Nn may be omitted for Moore; the sixteen Golly neighbourhood codes; "LifeViewer also supports: NF for Far Corners/Edges"
[^3]: [[lifewiki-larger-than-life](pages/lifewiki-larger-than-life.md)] L37 - "Ranges of consecutive numbers can be contracted via dashes; e.g. S6,7,8,13,14,18 can be expressed as S6-8,13-14,18"
[^4]: [[lifewiki-larger-than-life](pages/lifewiki-larger-than-life.md)] L84-100 [synthesis] - "R2,C2,S4,6-9,B6-8,N@03ddef - Marine a chaotic rule by MathAndCode"; "R3,C2,S2,B3,N+ - Factorio a semistable rule"; "R4,C2,S9,14,16-17,...,NW1000100010000... - Coexistence a chaotic rule"; "R2,C2,S4-6,B5-6,N# - Hash a chaotic rule"
[^5]: [[lifewiki-higher-range-outer-totalistic-rule](pages/lifewiki-higher-range-outer-totalistic-rule.md)] L9 - "HROT rules are supported by Golly 4.0 and onwards and by LifeViewer"; [[lifewiki-hexagonal-neighbourhood](pages/lifewiki-hexagonal-neighbourhood.md)] L74 - "hexagonal Higher-range outer-totalistic (including Larger than Life) rules are supported from v4.0 onwards"
[^6]: [[lifewiki-apgsearch](pages/lifewiki-apgsearch.md)] L98 - "Higher-range outer totalistic (HROT) rules. (up to range 5)"; [[lifewiki-catagolue](pages/lifewiki-catagolue.md)] L423 - "Arbitrary outer-totalistic rules (range 1 to 5)"
[^7]: [[lifewiki-higher-range-isotropic-non-totalistic-rule](pages/lifewiki-higher-range-isotropic-non-totalistic-rule.md)] L99 - "The number of unique transitions for higher ranges tends to be extremely large, and the development of notations for such rules is generally infeasible"
