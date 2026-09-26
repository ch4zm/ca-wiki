---
title: Margolus Neighbourhood
category: Concepts
summary: Margolus's space-partitioning scheme - apply a permutation to every 2 × 2 block, then shift the partition and apply another - which makes any rule reversible by construction; basis of the billiard-ball computer and, generalized and composed with a translation, of every 1D and 2D reversible cellular automaton
tags: [concept, neighbourhood, margolus, reversibility, block-permutation, billiard-ball, lattice-gas]
sources: [theory-of-cellular-automata-a-survey]
created: 2026-09-24
updated: 2026-09-25
---

# Margolus Neighbourhood

## Description

**The scheme.** Margolus (1984) introduced *space partitioning* as a way to guarantee
reversibility. Each update has two steps. First the plane is cut into 2 × 2 blocks along
odd coordinates, and a permutation π₁ of S⁴ is applied inside each block. Then the cut is
moved to even coordinates and a second permutation π₂ is applied. This became known as
the Margolus neighbourhood. The source's Fig. 8 shows the two partitions, solid for odd
steps and dashed for even ones.[^1]

**Why it is reversible.** Each step permutes the contents of disjoint blocks, so the
inverse automaton applies the inverse permutations (in reverse order, own reasoning). Other constraints are as
easy to build in. If the permutations never change the number of black cells in a block,
the number of black cells in a finite configuration is conserved
([[conserved-quantity](pages/conserved-quantity.md)]).[^2]

**Is it a CA?** Strictly, no. Even and odd cells use different rules, and even and odd
steps differ. Grouping each 2 × 2 block into one "supercell" and each pair of steps into
one step gives an ordinary CA. In that strict sense the billiard-ball computer below has
2⁴ = 16 states.[^3]

**The billiard-ball computer.** Margolus's rule uses two states, white and black, with
π₁ = π₂. The permutation changes only a few block patterns, which the source shows in a
figure. Because the partition alternates, a single black cell moves diagonally in a
direction set by the parity of its position. With this rule one can simulate billiard
balls of positive size moving and colliding, build walls for them to bounce off, and
combine these into arbitrary computation.[^4]

**Generalized.** Blocks can be bigger than 2 × 2, the clock cycle longer than two, and the
dimension anything. Each phase may use its own partition, but every step applies a
permutation to the blocks. Kari calls these *GMN-CA* (generalized Margolus neighbourhood)
and notes that the literature also calls them lattice gases.[^5] Every 1D and 2D
[[reversible-cellular-automaton](pages/reversible-cellular-automaton.md)] is a GMN-CA
composed with a translation, and a d-dimensional GMN-CA needs a clock cycle of at most
d + 1.[^6]

## Appearances in Sources

- [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] - §4: the scheme, the billiard-ball computer, GMN-CA, Theorem 11

## Related Concepts

- [[reversible-cellular-automaton](pages/reversible-cellular-automaton.md)] - what the scheme guarantees, and the representation theorem
- [[conserved-quantity](pages/conserved-quantity.md)] - conservation laws built in by choosing the permutations
- [[moore-neighbourhood](pages/moore-neighbourhood.md)], [[von-neumann-neighbourhood](pages/von-neumann-neighbourhood.md)], [[hexagonal-neighbourhood](pages/hexagonal-neighbourhood.md)] - the ordinary neighbourhoods it departs from
- [[universal-turing-machine](pages/universal-turing-machine.md)] - the billiard-ball computer is computationally universal

[^1]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.18 [synthesis] - "He also introduced the technique of space partitioning as a way to ensure reversibility"; 2 × 2 blocks along odd coordinates with permutation π₁ of S⁴, then even coordinates with π₂; "This technique became known as the Margolus neighborhood."; p.19 Fig. 8: "Odd updates use the solid partitioning, even updates the dashed partitioning"; [51] N. Margolus, Physics-like models of computation, Physica D 10 (1984)
[^2]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.18 [synthesis] - "A CA that uses the Margolus neighborhood is trivially reversible-the inverse automaton applies the inverse permutations"; the number of black cells in finite configurations is preserved if the permutations conserve black states
[^3]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.18 [synthesis] - "Strictly speaking Margolus neighborhood is not a CA neighborhood"; supercells of 2 × 2 blocks and combined clock cycles; "In this strict sense the billiard ball computer by Margolus has 2⁴ = 16 states."
[^4]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.18 [synthesis] - π₁ = π₂, binary states white and black; the exchanged blocks are shown pictorially; a single black state propagates diagonally depending on the parity of its location; motion and collisions of billiard balls of positive diameter, walls, "arbitrary computation [51]"
[^5]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.20 [synthesis] - larger blocks, longer clock cycles, any dimension d, different partitions per phase; "call them GMN-CA. In the literature, GMN-CA are also known as lattice gases."
[^6]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.20 [synthesis] - Theorem 11 (Kari [43,45]): all 1D and 2D reversible CA are a composition of a GMN-CA and a "translation-type" CA; every d-dimensional GMN-CA can be modified to one with clock cycle at most d + 1
