---
title: Isotropic non-totalistic rule
category: Rules
summary: A two-state Moore-neighbourhood rule whose transitions depend on the arrangement of live neighbours up to rotation and reflection, not just their count; 2^102 such rules, written in Hensel notation (e.g. B3-j6i/S23-c4i), home of looping reflectorless rotating oscillators and spaceships made of spaceships
tags: [rule-family, isotropic, int, hensel-notation, rulestring, two-state, moore-neighbourhood]
sources: [cgol-ch12-0e0p-metacell, cgol-ch1-early-life]
created: 2026-09-25
updated: 2026-09-25
---

# Isotropic non-totalistic rule

## Description

A cellular automaton is *isotropic* if its transition rule is unchanged by rotating or
reflecting the neighbourhood. It may depend on the relative positions of a cell's live
neighbours, but not on their absolute directions.[^1] Every
[[life-like-cellular-automaton](pages/life-like-cellular-automaton.md)] (outer-totalistic
rule) is isotropic, but not conversely: two cells with two live neighbours each must
behave alike in a Life-like rule, while an isotropic rule can tell some such
arrangements apart. Isotropic rules that are not Life-like are called *isotropic
non-totalistic* (INT).[^2] There are 2^102 isotropic two-state rules on the square grid,
against 2^18 Life-like ones.[^3]

**Hensel notation.** Start from a B/S rulestring and add a letter after a neighbour count
to select particular arrangements of that many neighbours. The notation is named after
Alan Hensel, who created it.[^4]
- The letters c (corner), e (edge), a (adjacent), k (knight), i, n, j, q, r, y, t, w and z
  each name one arrangement up to symmetry. Not every letter exists for every count.
- A letter adds that arrangement ("B3acj": born with 3 neighbours only in arrangements a,
  c, j). A minus removes it ("B3-kr": born with 3 in any arrangement except k and r).
- Rulestrings are not unique (B3/S2ac3 is the same rule as B3/S2-eikn3); the shorter is
  preferred.

For example, **B3-j6i/S23-c4i** is Life with four changes. There is no birth on the j
arrangement of 3 and there is birth on the i arrangement of 6; there is no survival on
the c arrangement of 3 and there is survival on the i arrangement of 4.[^5]

**Patterns unlike Life's.**[^6]
- **Reflectorless rotating oscillator (RRO).** An oscillator one of whose phases is a
  rotation of another, which travels a loop "like a spaceship that periodically turns a
  corner". Two non-interacting copies combine into one of half the period. B3-j6i/S23-c4i
  has a period-200 RRO (Justin Tang, 2020); two or four copies on the same path give
  periods 100 and 50.
- **Spaceship made of spaceships (SMOS).** A spaceship that works by colliding other
  spaceships. In B3acijn4jktwyz5ijr6-en7c/S2aen3-aceq4acijqty5cikr6ak7c, the glider
  behaves as in Life. Two gliders colliding just right make a 4c/17 orthogonal spaceship,
  and two of those make a c/44 diagonal one, a spaceship made of spaceships made of
  spaceships.

Via the [[metacell](pages/metacell.md)] these patterns can be imported into Life.[^7]

## Appearances in Sources

- [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] - §12.1.2 isotropic rules and their patterns; Appendix B.6 Hensel notation
- [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] - INT rules named as a variant of Life

## Related Concepts

- [[life-like-cellular-automaton](pages/life-like-cellular-automaton.md)] - the outer-totalistic subfamily
- [[non-isotropic-rule](pages/non-isotropic-rule.md)] - the fully general superfamily
- [[metacell](pages/metacell.md)] - emulates these rules inside Life
- [[spaceship](pages/spaceship.md)] - SMOS and looping oscillators extend the notion

[^1]: [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] p.388 - "A cellular automaton is called isotropic if the cell transition rules are invariant under rotations and reflections ... an isotropic cellular automaton may take into account the relative positions of neighboring cells, but not their absolute positions"
[^2]: [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] p.388, Fig. 12.7 [synthesis] - "Every outer-totalistic cellular automaton is isotropic, but the converse is not true"; configurations with 2 neighbours must evolve alike in an outer-totalistic rule, only rotations and reflections of each other in an isotropic one; [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.5 - "such rules are known as isotropic rules, or INT rules (short for 'isotropic non-totalistic')"
[^3]: [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] p.389 - "there are a whopping 2^102 isotropic 2-state CA on a 2D square grid, versus 'just' 2^18 outer-totalistic ones"
[^4]: [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] Appendix B.6, pp.444-446 [synthesis] - "add modifiers after each integer in the rulestring to either add or remove some of those birth and survival conditions"; Table B.3 modifiers c, e, a, k, i, n, j, q, r, y, t, w, z; positive and negative modifiers; "the rule B3/S2ac3 is exactly the same as the rule B3/S2-eikn3"; "we typically prefer shorter rulestrings"; n.5 "sometimes called Hensel notation, after its creator Alan Hensel"; n.6 some modifiers cannot follow some integers
[^5]: [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] p.389 and Appendix B.6, p.445 [synthesis] - B3-j6i/S23-c4i: born with 3 unless j, born with 6 only if i, survives with 2, survives with 3 unless c, survives with 4 only if i
[^6]: [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] pp.389-390 [synthesis] - "a reflectorless rotating oscillator (or RRO for short): an oscillator with the property that one of its phases is a rotation of another one, and two non-interacting copies of the oscillator can combine so as to produce an oscillator with period half as large"; "they are even sometimes called looping spaceships"; Fig. 12.9 periods 200, 100, 50 (Justin Tang, January 2020); "a spaceship made of spaceships (or SMOS for short)"; Fig. 12.10 glider, 4c/17 orthogonal SMOS ("Saka", August 2017), c/44 diagonal SMOSMOS ("FWKnightship", August 2019)
[^7]: [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] p.391 - "this method gave the first explicit construction of a spaceship made of spaceships in Life (and thus the first SMOSMOS in Life as well). This method also gave the first reflectorless rotating oscillator in Life"
