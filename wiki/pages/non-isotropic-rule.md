---
title: Non-isotropic rule
category: Rules
summary: The fully general two-state Moore-neighbourhood rule, where each of the 512 possible 3 × 3 neighbourhoods independently decides the next state; 2^512 rules, written as 86-character base-64 "MAP" rulestrings; a single cell can be a lightspeed spaceship, a knightship, or a Sierpiński-triangle generator, and elementary CA embed as a special case
tags: [rule-family, non-isotropic, map-rulestring, two-state, moore-neighbourhood, elementary-ca]
sources: [cgol-ch12-0e0p-metacell]
created: 2026-09-25
updated: 2026-09-25
---

# Non-isotropic rule

## Description

A *non-isotropic* rule may treat each absolute arrangement of a cell and its eight
neighbours differently, with no symmetry required. There are 2^512 such two-state rules
on the square grid.[^1] They contain the
[[isotropic-non-totalistic-rule](pages/isotropic-non-totalistic-rule.md)]s, which contain
the [[life-like-cellular-automaton](pages/life-like-cellular-automaton.md)] rules.

**MAP rulestrings** (format by Chris Rowett).[^2]
- Number the 512 neighbourhoods 0-511 by giving the 3 × 3 cells the weights 256, 128,
  64 / 32, 16, 8 / 4, 2, 1 and adding the weights of the live cells. Configuration 0 is
  all dead; 1 is only the bottom-right cell alive.
- Write a 512-bit string whose bit i says whether neighbourhood i makes the centre cell
  alive next.
- Encode it in base 64, six bits per character, giving 86 characters. Prefix "MAP".
- Hexagonal (7-cell) and von Neumann (5-cell) neighbourhoods take 22 and 6 base-64
  characters.

**Single cells that do anything.**[^3]
- Cells never survive and are born only with one live cell directly to their left: a
  single cell is an orthogonal spaceship moving at the speed of light.
- A rule where cells are born with no neighbours or one neighbour to the southeast, and
  survive only with neighbours everywhere except north and northwest, makes a single cell
  a (1, 2)c/2 knightship. Because empty neighbourhoods give birth, the background flashes
  between all-dead and all-alive.
- Cells always survive, and are born only with exactly one live cell directly northeast
  or northwest: a single cell draws ever-better approximations of the Sierpiński
  triangle.

**Elementary CA inside.** Restrict a non-isotropic rule to one dimension, with every cell
surviving and births only below live cells, and each row evolves from the one above as an
[[elementary-cellular-automaton](pages/elementary-cellular-automaton.md)]. All 2^8 = 256
arise this way. The Sierpiński rule above emulates elementary rule 18.[^4]

**In Life.** The 0E0P [[metacell](pages/metacell.md)] emulates the 2^511 of these rules
in which a dead cell with no live neighbours stays dead. That covers every example above
except the knightship, whose rule gives birth on empty neighbourhoods.[^5]

## Appearances in Sources

- [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] - §12.1.3 non-isotropic rules; Appendix B.7 MAP rulestrings

## Related Concepts

- [[isotropic-non-totalistic-rule](pages/isotropic-non-totalistic-rule.md)] - the symmetric subfamily
- [[elementary-cellular-automaton](pages/elementary-cellular-automaton.md)] - the one-dimensional special case
- [[metacell](pages/metacell.md)] - emulates these rules inside Life
- [[moore-neighbourhood](pages/moore-neighbourhood.md)] - the neighbourhood the family is defined on
- [[von-neumann-neighbourhood](pages/von-neumann-neighbourhood.md)], [[hexagonal-neighbourhood](pages/hexagonal-neighbourhood.md)] - smaller neighbourhoods with shorter MAP strings
- [[rulestring](pages/rulestring.md)] - MAP strings among the other rule notations
- [[ruleloader](pages/ruleloader.md)] - Golly's rule-table route for rules without a compact notation

[^1]: [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] p.391 - "There are 2^512 different 2D not necessarily isotropic cellular automata"
[^2]: [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] Appendix B.7, pp.446-448 [synthesis] - "list what happens to the central cell in each of the 2^9 = 512 different possible configurations"; Fig. B.4 weights 256, 128, 64, 32, 16, 8, 4, 2, 1; 512-bit string; Table B.4 base-64 encoding; "a ⌈512/6⌉ = 86-character string"; "prepend this base-64 string with the characters 'MAP'"; n.7 "created by Chris Rowett"; hexagonal 22 characters, von Neumann 6 characters
[^3]: [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] pp.390-391 [synthesis] - "cells never survive, and they are only born if they have a single live cell directly to their left ... a single cell is a spaceship that travels orthogonally at lightspeed"; (1, 2)c/2 knightship rule and Fig. 12.11(b) "the background array of cells alternates between dead and alive"; Fig. 12.12 "a single cell produces the Sierpiński triangle"
[^4]: [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] p.391 - "if we restrict non-isotropic cellular automata to a single dimension ... then we get exactly what are called elementary cellular automata. There are 2^8 = 256 cellular automata of this type, and the Sierpiński-triangle-generating rule works by emulating the one called Rule 18"
[^5]: [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] p.391 - "the 0E0P metacell can emulate the 2^511 of them that send a dead cell with no live neighbors to a dead cell. It can thus be used to embed all of the patterns from this section into Life, except for the knightship from Figure 12.11(b)"
