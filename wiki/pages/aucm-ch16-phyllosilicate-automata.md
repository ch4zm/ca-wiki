---
title: "Automata, Universality, Computation — Ch. 16: Phyllosilicate Automata"
category: Sources
summary: Adamatzky's binary automata on the silicate-sheet lattice (3-neighbour silicon, 6-neighbour oxygen nodes, one totalistic rule per node type) - a 100K-rule survey classified by pattern shape and interior, a sub-linearly growing rule, and three Life-like rules R65, R68, R72 with gliders, oscillators, an oscillator-eater, a still life and a glider gun
tags: [phyllosilicate, non-orthogonal-lattice, game-of-life, gliders, oscillators, glider-gun, morphology, collision-based-computing, adamatzky]
sources: [aucm-ch16-phyllosilicate-automata]
created: 2026-09-24
updated: 2026-09-24
---

# Automata, Universality, Computation — Ch. 16: Phyllosilicate Automata

**Source:** assets/adamatzky-2015-automata-universality-computation.pdf, printed pp. 353–381 (PDF pp. 357–385)
**Date ingested:** 2026-09-24
**Type:** book chapter (overview of the author's 2013 papers)
**Author:** Andrew Adamatzky
**Part of:** [[automata-universality-computation](pages/automata-universality-computation.md)]

## Summary

Phyllosilicates are sheets of silicate tetrahedra, common in clay minerals and used in
nanomaterials and catalysis.[^1] A
[[phyllosilicate-automaton](pages/phyllosilicate-automaton.md)] is a regular network of
two-state finite machines laid out like such a sheet. Silicon nodes sit at the centres of
tetrahedra and have three neighbours. Oxygen nodes sit at the shared corners and have six.
Each node type updates by its own totalistic rule, which depends on its current state and
the number of live neighbours.[^2] The chapter continues work on automata on
non-orthogonal and aperiodic lattices, such as triangular tessellations, Penrose tilings
and the hyperbolic plane.[^3]

A survey of 100,000 random rules sorts the patterns that grow from a random seed. They are
classified once by overall shape and once by internal morphology.[^4] Searching the
high-activity, low-density part of rule space turned up three minimal rules with
[[game-of-life](pages/game-of-life.md)]-like behaviour: gliders, oscillators, a still life
and a glider gun.[^5] Adamatzky proposes the automata as fast prototypes for
collision-based computing with travelling defects in real silicate sheets. He adds that
most collisions explode, and that experimental confirmation would be very difficult.[^6]

## Key Takeaways

- **Rule notation.** A rule R(s₀, s₁, o₀, o₁) is four bit strings: 4 bits for silicon and 7
  for oxygen, one string for each current state. Bit i gives the next state when i
  neighbours are live, and each string is written as its decimal value. For example,
  s₀ = 0111 (decimal 7) means a resting silicon node wakes with 1, 2 or 3 live neighbours.
  State 0 is quiescent.[^7]
- **Shape classes** (frequency among random rules):[^8]

  | Class | Patterns | Frequency |
  |---|---|---|
  | C1 | octagonal growth, bounded by eight half-planes along the lattice axes | 0.14 |
  | C2 | near-circular growth, boundary close to a circle of radius t | 0.21 |
  | C3 | stationary convex or concave hulls | 0.051 |
  | C4 | dendritic growth, with growth cones that outrun the rest of the front | 0.04 |
  | C5 | shrink to a few still localizations and oscillators | 0.23 |

- **Interior classes.** M1 solid, M2 labyrinthine (mostly chains of oxygen nodes), M3
  wave-like (like target and spiral waves in excitable media), M4 disordered (0.34 of
  random rules), and M5 still, travelling and propagating localizations. M5 overlaps C5.
  The classification is coarse, and transient rules can fit several classes.[^9]
- **Sub-linear growth.** Wave-like patterns and gliders grow linearly. Under
  R(7, 5, 31, 33), a random seed becomes a convex hull that mostly stops growing. A single
  *growth point* crawls along its boundary, and the pattern gains two nodes only each time
  the point completes a circuit.[^10] (Own reasoning: with a perimeter proportional to the
  size L, that gives dL/dt ∝ 1/L, so L grows like √t.)
- **Three Life-like rules.** R65 = R(5, 2, 16, 65), R68 = R(5, 2, 16, 68) and
  R72 = R(5, 2, 16, 72) share their silicon rule (born with 1 or 3 live neighbours,
  surviving with 2) and their oxygen birth rule (born with 2). They differ only in oxygen
  survival, which is 0 or 6, 0 or 4, and 0 or 3 live neighbours.[^11]

## The Life-like zoo

| Object | Rule | Period | Live nodes (min-max) |
|---|---|---|---|
| glider G¹⁶₆₅ | R65 | 16 | 6-13 |
| glider G¹²₆₈ | R68 | 12 | 7-13 |
| glider G⁴₇₂ | R72 | 4 | 4-11 |
| oscillator O⁵₆₅ | R65 | 5 | 6-10 |
| oscillator O⁶₆₅ | R65 | 6 | 4-9 |
| oscillator O⁶ᴬ₆₅ | R65 | 6 | 3-5 |
| oscillator O⁶₆₈ | R68 | 6 | 3-6 |
| oscillator O¹²₆₈ | R68 | 12 | 8-26 |
| oscillator O²₇₂ | R72 | 2 | 3-4 |
| oscillator O⁴₇₂ | R72 | 4 | 6-10 |
| oscillator O¹²₇₂ | R72 | 12 | 2-5 |

(Periods and weights from the chapter's Table 16.1.)[^12]

- **Gliders.** G¹⁶₆₅ is the heaviest and has the longest period. It alternates between
  thickening across its direction of motion and lengthening along it. G¹²₆₈ "breathes"
  about its centre, and its state at t + 6 mirrors its state at t. G⁴₇₂ is the smallest,
  with four phases.[^13]
- **Collisions.** Most glider collisions explode into unbounded growth. In R65, a head-on
  collision with no offset fuses the pair into a period-6 oscillator. In R68, at some
  offsets one glider survives while the other explodes.[^14]
- **Eaters.** O¹²₇₂ absorbs a colliding G⁴₇₂ in some phases and positions. Since it is not
  a still life, Adamatzky calls it an *oscillator-eater*. The one still life found is a ring
  of six silicon and six oxygen nodes in R68. It also acts as an eater, and under R65 it
  becomes an oscillator.[^15]
- **Glider gun.** R72 has a glider gun. Adamatzky expects guns in R65 and R68 and still
  lifes in R65 and R72 to exist, since the search was extensive but not exhaustive.[^16]
- **Comparing with Conway.** Adamatzky normalizes each threshold by neighbourhood size.
  Life's B3/S23 on 8 neighbours becomes birth 3/8 and survival 2/8, 3/8. In his occupancy
  map, Life sits below average, the silicon rules above average, and the oxygen rules below
  average for survival. He concludes that survival conditions matter more than birth
  conditions, since glider-supporting rules mostly keep survival occupancy between 0.3 and
  0.4 while birth ranges from 0 to 1.[^17]

## Entities & Concepts

- [[phyllosilicate-automaton](pages/phyllosilicate-automaton.md)]
- [[game-of-life](pages/game-of-life.md)]
- [[classification-of-cellular-automata](pages/classification-of-cellular-automata.md)]
- [[cellular-automaton](pages/cellular-automaton.md)]

## Relation to Other Wiki Pages

The shape and morphology classes are a phenomenological scheme like Wolfram's classes
([[classification-of-cellular-automata](pages/classification-of-cellular-automata.md)]):
they sort what grows from random seeds, with no formal definition. C5 and M5 play roughly
the role of Wolfram's localized structures (own comparison). The gliders, eaters and gun
are the same toolkit that makes Life universal
([[game-of-life](pages/game-of-life.md)]). Here, though, most collisions explode, which
Adamatzky says "may somehow limit, however not totally take away" collision-based designs,
like those of the [[billiard-ball-model](pages/billiard-ball-model.md)].[^18] The model
also breaks homogeneity, one of the defining assumptions of a
[[cellular-automaton](pages/cellular-automaton.md)], because there are two kinds of node.[^19]

[^1]: [[aucm-ch16-phyllosilicate-automata](pages/aucm-ch16-phyllosilicate-automata.md)] p.353 [synthesis] — phyllosilicates are "parallel sheets of silicate tetrahedra", found in clay-related minerals, used in nano-materials, nano-wires, patterned surfaces and as catalysts
[^2]: [[aucm-ch16-phyllosilicate-automata](pages/aucm-ch16-phyllosilicate-automata.md)] pp.354-355 [synthesis] — silicon automata at the centre vertex of each tetrahedron (three neighbours), oxygen automata at corner vertices (six neighbours); states 0 (resting) and 1; update a^{t+1} = a_{a^t}[σ(a)^t], with σ the number of 1-state neighbours; apical oxygens ignored
[^3]: [[aucm-ch16-phyllosilicate-automata](pages/aucm-ch16-phyllosilicate-automata.md)] p.353 — "We continue lines of enquiry into space-time dynamics of cellular automata on non-orthogonal and aperiodic lattices, including triangular tessellations and Penrose tilings and hyperbolic planes"
[^4]: [[aucm-ch16-phyllosilicate-automata](pages/aucm-ch16-phyllosilicate-automata.md)] pp.355-357 [synthesis] — "100K rules are generated at random"; random perturbation, 100 steps, evaluation "visually and using few integral parameters" (density μ, activity α); five shape classes C1-C5 and five morphology classes M1-M5
[^5]: [[aucm-ch16-phyllosilicate-automata](pages/aucm-ch16-phyllosilicate-automata.md)] p.367 — "Exploring the 'activity-density' space in the loci with high activity and low density we discovered three minimal ... rules that support gliders, R65 = R(5, 2, 16, 65), R68 = R(5, 2, 16, 68), and R72 = R(5, 2, 16, 72)"; "We have also discovered one still life, observed in rule R68 and a glider gun, found in rule R72"
[^6]: [[aucm-ch16-phyllosilicate-automata](pages/aucm-ch16-phyllosilicate-automata.md)] pp.378-379 [synthesis] — "Most interactions between localizations lead to explosions ... This may somehow limit, however not totally take away, an applicability of phyllosilicate automata in design of collision-based circuits"; travelling localizations as defects in silicate sheets, generated by irradiation; "Obviously, to obtain an experimental confirmation would be a very difficult task"
[^7]: [[aucm-ch16-phyllosilicate-automata](pages/aucm-ch16-phyllosilicate-automata.md)] p.355 [synthesis] — o and s binary strings of seven and four symbols; rule R(dec(s₀), dec(s₁), dec(o₀), dec(o₁)); example s₀ = (0111), dec 7: a resting silicon node takes state 1 with one, two or three live neighbours; "We assume state 0 is a quiescent state"
[^8]: [[aucm-ch16-phyllosilicate-automata](pages/aucm-ch16-phyllosilicate-automata.md)] pp.357-363 [synthesis] — C1 octagonal (bounded by eight half-planes, probability 0.14); C2 boundaries "close, in shape and position, to a circle of radius t" (0.21); C3 stationary convex and concave hulls (0.051); C4 dendritic growth with growth-cones (0.04); C5 still localizations and oscillators (0.23)
[^9]: [[aucm-ch16-phyllosilicate-automata](pages/aucm-ch16-phyllosilicate-automata.md)] pp.363-365, 376 [synthesis] — M1 solid; M2 labyrinthine, "most labyrinthine patterns are made of oxygen nodes"; M3 wave-like, "analogues of target and spiral wave-fronts in excitable nonlinear media"; M4 disordered, "frequency 0.34"; M5 localizations, overlapping C5; "The classes proposed give rather a coarse classification of a rule space"
[^10]: [[aucm-ch16-phyllosilicate-automata](pages/aucm-ch16-phyllosilicate-automata.md)] pp.366-367 [synthesis] — "Wave-like patterns and gliders are fastest growing configurations"; rule R(7, 5, 31, 33) forms a convex hull that "in general, do not grow anymore"; a growth point "always propagate along the boundary"; the linear size increases "by two nodes only when the growth point made a full turn along boundary of the pattern"
[^11]: [[aucm-ch16-phyllosilicate-automata](pages/aucm-ch16-phyllosilicate-automata.md)] p.367 [synthesis] — shared strings s₀ = (0101), s₁ = (0010), o₀ = (0010000); o₁ = (1000001) in R65, (1000100) in R68, (1001000) in R72; "Silicon node in state 0 takes state 1 only if it has one or three neighbours in state 1. Silicon node in state 1 remains in state 1 if it has two neighbours in state 1. Oxygen node in state 0 takes state 1 only if it has two neighbours in state 1. An oxygen node in state 1 remains in state 1 if it has no neighbours in state 1 or six in rule R65, four in rule R68 and three in rule R72"
[^12]: [[aucm-ch16-phyllosilicate-automata](pages/aucm-ch16-phyllosilicate-automata.md)] p.367 (Table 16.1) [synthesis] — period p and minimum and maximum numbers of non-resting nodes for G¹⁶₆₅, G¹²₆₈, G⁴₇₂, O⁵₆₅, O⁶₆₅, O⁶ᴬ₆₅, O⁶₆₈, O¹²₆₈, O²₇₂, O⁴₇₂, O¹²₇₂
[^13]: [[aucm-ch16-phyllosilicate-automata](pages/aucm-ch16-phyllosilicate-automata.md)] pp.368-372 [synthesis] — G¹⁶₆₅ "the heaviest amongst gliders discovered", thickening and lengthening phases; G¹²₆₈ state at t "vertically symmetric to the glider state at time step t + 6", "breathing around its centre of mass"; G⁴₇₂ "smallest amongst gliders discovered and has smallest period. It has just four different states"
[^14]: [[aucm-ch16-phyllosilicate-automata](pages/aucm-ch16-phyllosilicate-automata.md)] pp.370-372 [synthesis] — "Most collisions between gliders in rule R65 lead to explosions"; head-on collision with nil shift fuses into "an oscillator of period six"; in R68 "For certain offsets one glider can survive collision"
[^15]: [[aucm-ch16-phyllosilicate-automata](pages/aucm-ch16-phyllosilicate-automata.md)] pp.374-376 [synthesis] — collisions of G⁴₇₂ with O¹²₇₂: both vanish, both explode, or "glider disappear but oscillator remains intact"; "Oscillator O¹²₇₂ is not a still life so it can be classified as oscillator-eater"; still life in R68 "a ring of six oxygen and six silicon non-resting nodes"; Fig. 16.24: "in this rule the localisation acts as eater. The localisation (a) becomes an oscillation (b–e) in rule R65"
[^16]: [[aucm-ch16-phyllosilicate-automata](pages/aucm-ch16-phyllosilicate-automata.md)] pp.373, 378 [synthesis] — glider gun in R72 (Fig. 16.15); "We did not find glider guns in rules R65 and R68, we believe they exist"; "Our search ... was extensive yet not exhaustive. Thus substantial chances remain that glider guns could be found in rules R65 and R68, and still lifes in rules R65 and R72"
[^17]: [[aucm-ch16-phyllosilicate-automata](pages/aucm-ch16-phyllosilicate-automata.md)] pp.376-377 (Fig. 16.25) [synthesis] — Life B3/S23 normalized as B 3/8 / S 2/8 3/8; rules normalized by neighbourhood size; Game of Life in the below-average quadrant, silicon above average, oxygen below average for survival; "conditions for survival are more critical than conditions for birth. Most rules supporting gliders obey a neigbourhood occupancy between 0.3 and 0.4 while neighbourhood occupancy for birth varies from 0 to 1"
[^18]: [[aucm-ch16-phyllosilicate-automata](pages/aucm-ch16-phyllosilicate-automata.md)] p.378 — "This may somehow limit, however not totally take away, an applicability of phyllosilicate automata in design of collision-based circuits [2]."
[^19]: [[aucm-ch16-phyllosilicate-automata](pages/aucm-ch16-phyllosilicate-automata.md)] p.378 — "The phyllosilicate automata are not strictly cellular automata, because they have two types of nodes which updates their states by two different functions."
