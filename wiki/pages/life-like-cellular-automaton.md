---
title: Life-like cellular automaton
category: Rules
summary: The family of 2^18 = 262,144 two-state rules on the square grid's eight-cell neighbourhood whose next state depends only on the number of live neighbours, written as B/S rulestrings (Life is B3/S23); hub for Life's sibling rules and the extensions beyond them
tags: [rule-family, life-like, rulestring, outer-totalistic, two-state]
sources: [cgol-ch1-early-life]
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

**Rulestrings.** A rule is written **Bx/Sy**, where x lists the neighbour counts that
cause birth and y the counts that allow survival. [[game-of-life](pages/game-of-life.md)]
is **B3/S23**.[^2]

**Why Life among them.** Johnston and Greene single Life out, "special (but by no means
unique)", on three grounds:[^3]
- *Simple rules.* Dying of overcrowding with too many neighbours and of isolation with
  too few is the natural shape for a model of living things.
- *Balance.* Almost any rule with birth on 2 has too many births for anything to
  stabilize. Most rules without birth on 3 or fewer die off too fast. Life's patterns
  typically stay alive without taking over the grid.
- *History.* It is the most studied rule, and pushing one rule far is its own interest.

**Beyond Life-like rules.** Other variations change what counts as a neighbour (the
four-cell von Neumann neighbourhood), the grid (hexagonal, triangular, 1D, 3D), or let the
relative *positions* of live neighbours matter, not just their number. The last are
*isotropic non-totalistic* (INT) rules.[^4]

**Soup search in other rules.** The soup-search programs TOLLCASS and apgsearch both run on
several Life-like rules, not only B3/S23 ([[soup-search](pages/soup-search.md)]).[^5]

## Appearances in Sources

- [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] - the count of Life-like rules, B/S rulestrings, why B3/S23, INT and other variants

## Related Concepts

- [[game-of-life](pages/game-of-life.md)] - B3/S23, the best-known member
- [[moore-neighbourhood](pages/moore-neighbourhood.md)] - the neighbourhood the family is defined on
- [[cellular-automaton](pages/cellular-automaton.md)] - the general notion
- [[soup-search](pages/soup-search.md)] - census tools that also cover other Life-like rules

[^1]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.4 - "there are 2^18 = 262 144 distinct Life-like cellular automata: rules that can be applied to a 2D square grid of alive and dead cells that simply depend on the numbers of live and dead neighbors that lead to a cell staying alive or coming to life"
[^2]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.5 - "a rulestring of the form Bx/Sy, where we replace 'x' by all numbers of live neighbors that lead to the birth of a dead cell, and we replace 'y' by all numbers of live neighbors that lead to the survival of a live cell. For example, the Game of Life is described by the rulestring B3/S23"
[^3]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.4 [synthesis] - "the following three properties make Life special (but by no means unique)": simple rules (death from overcrowding and isolation); "almost any rule in which a cell is born when it has 2 live neighbors" is too chaotic, rules without birth on 3 or fewer are "too stable"; "historically it is the most well-studied rule"
[^4]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.5 [synthesis] - "this 4-cell neighborhood is called the von Neumann neighborhood"; "a hexagonal or triangular grid instead of a square one, or a 1D or 3D grid"; "not only the number of live neighbors matters, but also their relative positions--such rules are known as isotropic rules, or INT rules (short for 'isotropic non-totalistic')"
[^5]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.28 [synthesis] - TOLLCASS "also worked not just with Conway's Game of Life, but also with a handful of other Life-like cellular automata"; apgsearch "can be used with several different Life-like CA"
