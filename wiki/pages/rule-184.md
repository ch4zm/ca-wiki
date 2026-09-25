---
title: Rule 184
category: Rules
summary: The elementary "traffic rule" - a 1 moves one cell right whenever the cell ahead is empty (10 → 01), so particles flow without being created or destroyed; expressible as a push rule for particles or a pull rule for empty cells in the write-access model
tags: [rule, rule-184, elementary-ca, traffic, particles, number-conserving]
sources: [aucm-ch13-cellular-automata-with-write-access]
created: 2026-09-24
updated: 2026-09-24
---

# Rule 184

## Description

**The rule.** Rule 184, the *traffic rule*, is the
[[elementary-cellular-automaton](pages/elementary-cellular-automaton.md)] in which particles
(or cars) move in one direction. As a Boolean function, C′ = (C ∧ R) ∨ (L ∧ ¬C). A cell
holding a 1 takes its new value from the cell to its right, and an empty cell takes its new
value from the cell to its left.[^1] Equivalently, wherever the pattern 10 appears it
becomes 01. A car moves right exactly when the cell ahead is free.[^2]

(Own reasoning: evaluating the formula on the eight neighbourhoods 111, 110, …, 000 gives
1, 0, 1, 1, 1, 0, 0, 0, which is binary 184. Since 100 → 1 but 001 → 0, the rule is not
mirror-symmetric and is not one of Wolfram's legal rules.)

| 111 | 110 | 101 | 100 | 011 | 010 | 001 | 000 |
|---|---|---|---|---|---|---|---|
| 1 | 0 | 1 | 1 | 1 | 0 | 0 | 0 |

**Four descriptions.** Hoffmann writes the same rule four ways
([[cellular-automaton-with-write-access](pages/cellular-automaton-with-write-access.md)]):[^3]

1. **Cell rule.** Each cell sets its own state, as in any CA.
2. **Substitution.** A unit between each pair of cells rewrites 10 to 01.
3. **Push.** Occupied cells are active. A car writes 1 into the empty cell ahead and 0 into
   itself. The rule is inherently free of write conflicts.
4. **Pull.** Empty cells are active. A cell that sees a car to its left pulls it in. Hoffmann
   suggests this form when the particles are driven by an external field.

Moving the substitution onto the left cell gives the push rule, and onto the right cell the
pull rule.[^3]

**Conservation (own reasoning).** Every update moves a 1 without creating or destroying
one, so on a ring the number of 1s never changes. It is a
[[conserved-quantity](pages/conserved-quantity.md)] of the simplest additive kind.

## Appearances in Sources

- [[aucm-ch13-cellular-automata-with-write-access](pages/aucm-ch13-cellular-automata-with-write-access.md)] - the Boolean form, the substitution, and the push and pull programs

## Related Concepts

- [[elementary-cellular-automaton](pages/elementary-cellular-automaton.md)] - the family
- [[cellular-automaton-with-write-access](pages/cellular-automaton-with-write-access.md)] - the push and pull formulations
- [[conserved-quantity](pages/conserved-quantity.md)] - the particle number is conserved

[^1]: [[aucm-ch13-cellular-automata-with-write-access](pages/aucm-ch13-cellular-automata-with-write-access.md)] p.284 — "The elementary 1-D CA rule 184, also known as traffic rule, describes the moving of particles or cars in one direction ... In classical CA the new state is computed by the logical function C ← (C ∧ R) ∨ (L ∧ C̄). If the cell's state is 1, its new state is taken from the cell R to its right. Otherwise, its new state is taken from the cell L to its left."
[^2]: [[aucm-ch13-cellular-automata-with-write-access](pages/aucm-ch13-cellular-automata-with-write-access.md)] pp.284-285 [synthesis] — set-operation form: C ← 1 if LC = 10, C ← 0 if CR = 10, otherwise unchanged; substitution: "wherever the pattern 10 appears it is substituted by 01 without any conflict"; push rule: "the particle moves actively to the next free position"
[^3]: [[aucm-ch13-cellular-automata-with-write-access](pages/aucm-ch13-cellular-automata-with-write-access.md)] pp.285-286 [synthesis] — four cases: CA cell rule; substitution by a unit between each pair of cells; push rule (active particles, set(1) to the right neighbour and set(0) to itself, "inherently conflict-free"); pull rule (active empty cells, "useful for applications where the particle is driven by an external field or force"); the substitution shifted left gives push, shifted right gives pull
