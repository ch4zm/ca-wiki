---
title: Life-like cellular automaton
category: Rules
summary: The family of 2^18 = 262,144 two-state rules on the square grid's eight-cell neighbourhood whose next state depends only on the number of live neighbours, written as B/S rulestrings (Life is B3/S23); hub for Life's sibling rules and the extensions beyond them
tags: [rule-family, life-like, rulestring, outer-totalistic, two-state]
sources: [lifewiki-generations, cgol-ch12-0e0p-metacell, cgol-ch1-early-life]
created: 2026-09-25
updated: 2026-09-25
---

# Life-like cellular automaton

## Description

A Life-like cellular automaton is a rule on the 2D square grid, with cells alive or dead,
in which whether a dead cell is born and whether a live cell survives depends only on how
many of its eight neighbours ([[moore-neighbourhood](pages/moore-neighbourhood.md)]) are
alive. There are 2^18 = 262,144 of them.[^1] The count follows because each of the nine
possible neighbour counts, 0 through 8, can independently cause birth or not, and
independently allow survival or not (own reasoning).

**Outer-totalistic.** In the precise terms, these rules are *outer-totalistic*: the new
state depends on the cell's own state and the number of live neighbours. A *totalistic*
rule would depend only on the count including the cell itself. "Life-like" adds the square
grid and the eight-cell neighbourhood.[^2]

**Rulestrings.** A rule is written **Bx/Sy**, where x lists the neighbour counts that
cause birth and y the counts that allow survival. [[game-of-life](pages/game-of-life.md)]
is **B3/S23**.[^3]

**Why Life among them.** Johnston and Greene single Life out, "special (but by no means
unique)", on three grounds:[^4]
- *Simple rules.* Dying of overcrowding with too many neighbours and of isolation with
  too few is the natural shape for a model of living things.
- *Balance.* Almost any rule with birth on 2 has too many births for anything to
  stabilize. Most rules without birth on 3 or fewer die off too fast. Life's patterns
  typically stay alive without taking over the grid.
- *History.* It is the most studied rule, and pushing one rule far is its own interest.

**Notable members.**[^5]
- [[highlife](pages/highlife.md)] (B36/S23), with its 12-cell [[replicator](pages/replicator.md)].
- The replicator rule B1357/S1357, where every pattern replicates in 8 directions.
- B12345678/S012345678, where a single cell fills the plane.
- B34568/S15678, with a spiral-growth pattern.

**The rule hierarchy.** There are 2^18 Life-like rules, inside the 2^102
[[isotropic-non-totalistic-rule](pages/isotropic-non-totalistic-rule.md)]s, inside the 2^512 [[non-isotropic-rule](pages/non-isotropic-rule.md)]s on the
same neighbourhood. Any Life-like rule can be emulated inside Life by the OTCA metapixel or
the 0E0P [[metacell](pages/metacell.md)].[^6]

**Multistate extension.** Every Life-like rule is the two-state case of a
[[generations-rule](pages/generations-rule.md)]. Bx/Sy/C2 is Bx/Sy, and adding dying states gives rules such as
[[star-wars-rule](pages/star-wars-rule.md)] (B2/S345/C4) and [[brians-brain](pages/brians-brain.md)] (B2/S/C3). The two-state
B2/S345 is a separate rule, called Star Trek.[^7]

**Beyond Life-like rules.** Other variations change what counts as a neighbour (the
four-cell von Neumann neighbourhood), the grid (hexagonal, triangular, 1D, 3D), or let the
relative *positions* of live neighbours matter, not just their number. The last are
*isotropic non-totalistic* (INT) rules.[^8]

**Soup search in other rules.** The soup-search programs TOLLCASS and apgsearch both run on
several Life-like rules, not only B3/S23 ([[soup-search](pages/soup-search.md)]).[^9]

## Appearances in Sources

- [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] - outer-totalistic definition, notable rules, emulation
- [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] - the count of Life-like rules, B/S rulestrings, why B3/S23, INT and other variants

## Related Concepts

- [[generations-rule](pages/generations-rule.md)] - the multistate extension with dying states
- [[highlife](pages/highlife.md)], [[replicator](pages/replicator.md)] - a notable member and its pattern
- [[isotropic-non-totalistic-rule](pages/isotropic-non-totalistic-rule.md)], [[non-isotropic-rule](pages/non-isotropic-rule.md)] - the larger rule families
- [[metacell](pages/metacell.md)] - emulates any Life-like rule inside Life
- [[game-of-life](pages/game-of-life.md)] - B3/S23, the best-known member
- [[moore-neighbourhood](pages/moore-neighbourhood.md)] - the neighbourhood the family is defined on
- [[cellular-automaton](pages/cellular-automaton.md)] - the general notion
- [[soup-search](pages/soup-search.md)] - census tools that also cover other Life-like rules

[^1]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.4 - "there are 2^18 = 262 144 distinct Life-like cellular automata: rules that can be applied to a 2D square grid of alive and dead cells that simply depend on the numbers of live and dead neighbors that lead to a cell staying alive or coming to life"
[^2]: [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] p.387 [synthesis] - "A 2-state cellular automaton is called outer-totalistic if the birth and death rules depend only on the state of the current cell, as well the number of live neighbors that it has"; n.4 "In contrast with totalistic cellular automata, in which the birth and death rules depend only on the number of live neighbors including the cell itself"; Life-like adds the 2D square grid and the Moore neighborhood
[^3]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.5 - "a rulestring of the form Bx/Sy, where we replace 'x' by all numbers of live neighbors that lead to the birth of a dead cell, and we replace 'y' by all numbers of live neighbors that lead to the survival of a live cell. For example, the Game of Life is described by the rulestring B3/S23"
[^4]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.4 [synthesis] - "the following three properties make Life special (but by no means unique)": simple rules (death from overcrowding and isolation); "almost any rule in which a cell is born when it has 2 live neighbors" is too chaotic, rules without birth on 3 or fewer are "too stable"; "historically it is the most well-studied rule"
[^5]: [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] pp.386-388 [synthesis] - HighLife (B36/S23) replicator; "the appropriately named replicator rule (B1357/S1357)"; B12345678/S012345678 single-cell replicator; spiral growth in B34568/S15678
[^6]: [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] pp.389,391,422 [synthesis] - 2^102 isotropic versus 2^18 outer-totalistic; 2^512 not necessarily isotropic; the OTCA metapixel "can be used to emulate any of the 2^18 different outer-totalistic (i.e., Life-like) cellular automata"
[^7]: [[lifewiki-generations](pages/lifewiki-generations.md)] L24 - "Any outer-totalistic cellular automaton with rulestring B.../S... is equivalent to the Generations rule with rulestring B.../S.../2"; [[lifewiki-star-wars](pages/lifewiki-star-wars.md)] L16 - "For the outer-totalistic rule, see OCA:Star Trek"
[^8]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.5 [synthesis] - "this 4-cell neighborhood is called the von Neumann neighborhood"; "a hexagonal or triangular grid instead of a square one, or a 1D or 3D grid"; "not only the number of live neighbors matters, but also their relative positions--such rules are known as isotropic rules, or INT rules (short for 'isotropic non-totalistic')"
[^9]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.28 [synthesis] - TOLLCASS "also worked not just with Conway's Game of Life, but also with a handful of other Life-like cellular automata"; apgsearch "can be used with several different Life-like CA"
