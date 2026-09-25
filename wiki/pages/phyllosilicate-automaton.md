---
title: Phyllosilicate Automaton
category: Concepts
summary: A binary automaton network on the silicate-sheet lattice - 3-neighbour silicon nodes and 6-neighbour oxygen nodes, each type with its own totalistic rule R(s₀, s₁, o₀, o₁) - whose rule space shows octagonal, circular, hull, dendritic and localized patterns and contains Life-like rules with gliders, oscillators and a glider gun
tags: [concept, phyllosilicate, non-orthogonal-lattice, two-rule, totalistic, life-like, adamatzky]
sources: [aucm-ch16-phyllosilicate-automata]
created: 2026-09-24
updated: 2026-09-24
---

# Phyllosilicate Automaton

## Description

**Lattice.** A phyllosilicate sheet is made of (SiO₄)⁴⁻ tetrahedra, each sharing its three
basal oxygens with neighbouring tetrahedra. The automaton keeps two kinds of node. Silicon
nodes, at the tetrahedron centres, have 3 neighbours. Oxygen nodes, at the shared corners,
have 6. The apical oxygens are ignored.[^1]

**Rules.** Every node has state 0 (resting) or 1, and all nodes update together. The next
state depends on the node's type, its current state, and σ, the number of live neighbours.
So a rule is four bit strings R(s₀, s₁, o₀, o₁), 4 bits for silicon and 7 for oxygen,
where bit σ of string a_i gives the next state of a type-a node in state i. Each string is
written as its decimal value. State 0 is quiescent, and rules whose resting-state string is all zeros
are excluded because they produce no patterns.[^2] Because the two node types follow
different functions, Adamatzky notes these are not strictly cellular automata.[^3] (Own
reasoning: grouping a silicon node with its oxygen corners into one supercell would give
an ordinary CA on a larger state set, much as the
[[margolus-neighbourhood](pages/margolus-neighbourhood.md)] becomes a CA by grouping its
blocks.)

**Rule space.** In a sample of 100,000 random rules, patterns grown from a random seed
fall into five shape classes. These are octagonal growth, near-circular growth,
stationary convex and concave hulls, dendritic growth, and decay into still localizations
and oscillators. There are also five interior classes: solid, labyrinthine, wave-like,
disordered, and localizations.[^4] One rule, R(7, 5, 31, 33), grows sub-linearly, through
a single growth point circling a convex hull.[^5]

**Life-like rules.** R(5, 2, 16, 65), R(5, 2, 16, 68) and R(5, 2, 16, 72) support gliders
of periods 16, 12 and 4, many oscillators, an oscillator that eats gliders, a still life
that eats gliders (in R68), and a glider gun (in R72). Silicon is born with 1 or 3 live
neighbours and survives with 2. Oxygen is born with 2 and survives with 0 plus,
respectively, 6, 4 or 3 live neighbours
([[game-of-life](pages/game-of-life.md)]).[^6]

**Purpose.** The author treats the automata as cheap models of excitation and defect
propagation in silicate sheets, and as prototypes for collision-based computing devices.[^7]

## Appearances in Sources

- [[aucm-ch16-phyllosilicate-automata](pages/aucm-ch16-phyllosilicate-automata.md)] - definition, the rule survey, the Life-like rules

## Related Concepts

- [[game-of-life](pages/game-of-life.md)] - the model its glider-supporting rules imitate
- [[cellular-automaton](pages/cellular-automaton.md)] - it relaxes homogeneity (two node types)
- [[classification-of-cellular-automata](pages/classification-of-cellular-automata.md)] - a morphological classification of its rule space
- [[margolus-neighbourhood](pages/margolus-neighbourhood.md)] - another non-standard scheme that becomes a CA after grouping cells

[^1]: [[aucm-ch16-phyllosilicate-automata](pages/aucm-ch16-phyllosilicate-automata.md)] p.354 [synthesis] — "Phyllosilicates are sheets of coordinated (SiO₄)⁴⁻ tetrahedra units. Each tetrahedron shares its three corner basal oxygens of neighbouring tetrahedra"; apical oxygens "are not taken into account"; silicon automata at centre vertices with three neighbours, oxygen automata at corner vertices with six neighbours
[^2]: [[aucm-ch16-phyllosilicate-automata](pages/aucm-ch16-phyllosilicate-automata.md)] pp.354-355 [synthesis] — states 0 and 1, synchronous discrete-time update a^{t+1} = a_{a^t}[σ(a)^t]; strings of four (silicon) and seven (oxygen) symbols; rule R(dec(s₀), dec(s₁), dec(o₀), dec(o₁)); state 0 quiescent; rules with a₀[i] = 0 for all 0 ≤ i ≤ 6 not studied
[^3]: [[aucm-ch16-phyllosilicate-automata](pages/aucm-ch16-phyllosilicate-automata.md)] p.378 — "The phyllosilicate automata are not strictly cellular automata, because they have two types of nodes which updates their states by two different functions."
[^4]: [[aucm-ch16-phyllosilicate-automata](pages/aucm-ch16-phyllosilicate-automata.md)] pp.355-365 [synthesis] — 100K random rules; shape classes C1 (octagonal), C2 (almost circular), C3 (convex and concave hulls), C4 (dendritic), C5 (still localizations and oscillators); morphology classes M1 (solid), M2 (labyrinthine), M3 (wave-like), M4 (disordered), M5 (localizations)
[^5]: [[aucm-ch16-phyllosilicate-automata](pages/aucm-ch16-phyllosilicate-automata.md)] pp.366-367 [synthesis] — rule R(7, 5, 31, 33): convex-hull pattern whose boundary is traversed by a growth point; size increases by two nodes per full turn
[^6]: [[aucm-ch16-phyllosilicate-automata](pages/aucm-ch16-phyllosilicate-automata.md)] pp.367-376 [synthesis] — R65, R68, R72 with s₀ = (0101), s₁ = (0010), o₀ = (0010000), o₁ = (1000001), (1000100), (1001000); gliders of period 16, 12, 4 (Table 16.1); oscillator-eater O¹²₇₂; still life in R68 acting as eater; glider gun in R72
[^7]: [[aucm-ch16-phyllosilicate-automata](pages/aucm-ch16-phyllosilicate-automata.md)] pp.354, 378 [synthesis] — automata as "a fast prototyping tool for an express evaluation of a space-time dynamics" of silicate sheets; state transition functions "could be used as fast-prototyping tools for designing and future manufacturing of collision-based computing devices in silicon sheets"
