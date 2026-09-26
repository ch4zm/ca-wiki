---
title: Fertile and mortal rules
category: Concepts
summary: Eppstein's two yes/no tests for a Life-like rule - fertile if some finite pattern escapes every bounding box, mortal if some finite pattern dies out - which split rule space into four regions decidable by short proofs for 96% and 99.8% of rules without B0; the fertile-and-mortal region is where gliders, guns and engineered complexity live, whatever the rule's Wolfram class
tags: [concept, classification, fertile, mortal, rule-space, life-like, growth, decay]
sources: [eppstein-2010-growth-and-decay-in-life-like-ca, eppstein-gliders-in-life-like-cellular-automata]
created: 2026-09-25
updated: 2026-09-26
---

# Fertile and mortal rules

## Description

**Two questions.** For a [[life-like-cellular-automaton](pages/life-like-cellular-automaton.md)]
rule without B0, so that finite patterns stay finite, Eppstein asks:[^1]
- **Fertile?** Is there a finite pattern that eventually escapes every bounding box? Such a
  *growth pattern* can be a [[glider](pages/glider.md)] or other
  [[spaceship](pages/spaceship.md)], a [[puffer](pages/puffer.md)], a
  [[gun](pages/gun.md)], a rake or a [[breeder](pages/breeder.md)]. A rule is fertile
  exactly when not every finite pattern ends up periodic, since a pattern trapped in a
  box has only finitely many states to cycle through.
- **Mortal?** Is there a finite pattern whose next generation is empty? This is the same
  as some pattern eventually fading away.

Growth and decay are both needed for Life-style complexity: some patterns must spread
and others must be able to vanish, as in the undecidability of whether a Life pattern
dies ([[game-of-life](pages/game-of-life.md)]), whose proof uses patterns that fade.[^2]

**Deciding fertility.** Most cases fall to short arguments.[^3]
- **B1** is fertile: a single cell grows forever, its bounding box's corners always live.
- **B2** is fertile: a 2 × 2 block spreads outward, keeping two live cells in the middle
  of each edge of its bounding box.
- **No B1, B2 or B3** is infertile: a dead cell outside the bounding box sees at most three
  live neighbours.
- In **B3**, spaceship searches show 10,736 of the 16,384 rules fertile. A diamond-shaped
  bounding argument proves 64 infertile (B3 rules with none of B1245 and none of
  S012345). That leaves 5,584 open, so 96% of all 131,072 rules without B0 are settled. Fertility without
  spaceships also occurs, as in the ladders of Life without Death.

**Deciding mortality.** Dean Hickerson's duality makes mortality a still-life question: a
pattern fades in a rule exactly when it is a still life of the rule with the same births
and complementary survivals.[^4] A still life's cells all survive and no cell is born;
under complementary survival the same counts now kill every cell, so the pattern empties
in one step (own reasoning, checking the duality). A 2001 still-life census by Hickerson,
Cook, Summers and Eppstein therefore settles mortality too. Case arguments show B1 rules,
rules with survival on 0-4, and several other families immortal. Of the 131,072 rules
without B0, 77,563 are immortal, 53,214 mortal and 295 unsettled, and every B3 rule is
decided.[^5]

**Immortal but moving.** Immortality alone does not forbid spaceships; B3456/S013 has
c/4 and c/3 ones. But many immortality proofs show a pattern's minimum bounding box or
diamond can never shrink, and then no spaceship can exist.[^6]

**The four regions.** Eppstein's map of rule space by area:[^7]

| | Mortal | Immortal |
|---|---|---|
| **Fertile** | where engineered complexity lives: Life, HighLife, B36/S245, Morley, B37/S23, Day & Night, Diamoeba, B35/S236, many B2 rules | B1 rules; the Fredkin parity rule B1357/S1357, all replicators; Life without Death with its ladders |
| **Infertile** | Anneal (B4678/S35678), which coarsens into live and dead blobs | B4/S01234, which freezes into striped regions |

The hypothesis is that the fertile-and-mortal region holds the rules most likely to carry
interesting patterns. Its members sit in different Wolfram classes: B35/S236 is chaotic
from random starts (class III) yet builds quadratic-growth patterns, while HighLife and
Morley settle like Life (class II or IV).[^8]

**Against random-start classes.** Wolfram's classes are read off random starts, so they
describe a rule only after watching it, blur at the borders, and cannot see built
structures. Life's famous guns, metapixels and caterpillars would never arise from a
random field, and rigorous results about random Life fields barely exist. Fertility and
mortality, by contrast, have rigorous yes/no answers that can be settled for whole blocks
of rules at once ([[classification-of-cellular-automata](pages/classification-of-cellular-automata.md)]).[^9]
Eppstein's earlier three-way screen of rules where contraction is impossible, rules where
expansion is impossible, and the rest where gliders can exist is the seed of the same
idea.[^10]

**Beyond empty backgrounds.** Both notions extend to rules on a periodic background: a
rule and background are fertile if some finite perturbation escapes every bounding box,
and mortal if some perturbation heals back to pure background. B0 rules with death on 8
flip between live and dead backgrounds every step, and B01245/S0125 is a strobing Day &
Night. Which rule-background pairs are fertile and mortal is largely unknown.[^11]

**Open edges.** The unsettled 5,584 fertility cases and 295 mortality cases are concrete
targets. Eppstein's "most wanted" list asks for proofs that rules with B23, rules with B3
and no survival on 0-5, and rules with all of B3/S34567 cannot have gliders. The 64-rule
diamond argument settles part of the second family, those that also lack B4 and B5 (own
reasoning, comparing the two sources).[^12]

## Appearances in Sources

- [[eppstein-2010-growth-and-decay-in-life-like-ca](pages/eppstein-2010-growth-and-decay-in-life-like-ca.md)] - the definitions, proofs, counts, map and rule tour
- [[eppstein-gliders-in-life-like-cellular-automata](pages/eppstein-gliders-in-life-like-cellular-automata.md)] - the spaceship database behind the fertility counts; the earlier three-way screen; the most-wanted list

## Related Concepts

- [[classification-of-cellular-automata](pages/classification-of-cellular-automata.md)] - the random-start and topological classes this replaces for Life-like rules
- [[life-like-cellular-automaton](pages/life-like-cellular-automaton.md)] - the rule space mapped; its lowest-birth-count table is the coarse version
- [[rule-range](pages/rule-range.md)] - one spaceship certifies fertility for its whole interval of rules
- [[still-life](pages/still-life.md)] - the duality that turns mortality into a still-life question
- [[replicator](pages/replicator.md)], [[highlife](pages/highlife.md)], [[seeds-rule](pages/seeds-rule.md)] - rules in the fertile regions
- [[phoenix](pages/phoenix.md)] - patterns whose cells all die each step, yet which never fade
- [[gl-rule](pages/gl-rule.md)] - Bays's test for a "Game of Life" rule, which judges from random soup where Eppstein judges by proof

[^1]: [[eppstein-2010-growth-and-decay-in-life-like-ca](pages/eppstein-2010-growth-and-decay-in-life-like-ca.md)] pp.7,10-11 [synthesis] - "We define a cellular automaton rule to be fertile if it has a finite pattern that eventually escapes any of its bounding boxes"; growth patterns in Life "including gliders and spaceships, puffer trains, guns, rakes, breeders, and other spacefillers"; "it would be equivalent to define an infertile rule as one in which every finite pattern eventually becomes periodic"; "If a rule supports a pattern P with a finite number of live cells, such that the state following P has no live cells, we say that the rule is mortal"; equivalent to having a finite pattern that fades
[^2]: [[eppstein-2010-growth-and-decay-in-life-like-ca](pages/eppstein-2010-growth-and-decay-in-life-like-ca.md)] p.10 - "it is important in Life that some patterns shrink as well as that others grow"; "the proof that determining the eventual fate of a Life pattern is undecidable depends on patterns that fade"
[^3]: [[eppstein-2010-growth-and-decay-in-life-like-ca](pages/eppstein-2010-growth-and-decay-in-life-like-ca.md)] pp.7-9 [synthesis] - B1: single cell, "a single live cell at each of its four corners"; B2: 2 × 2 block "will have two adjacent live cells at the center of each of its edges"; without B1, B2, B3 "The dead cells outside of a bounding box B of any pattern can have at most three live neighbors"; "10736 out of the 16384 possible B3 rules have spaceships"; "There are 64 B3 rules without any of B1245/S012345, all of which can be proven to be infertile"; "There remain only 5584 rules ... in 96% of the cases"; ladders in Life Without Death and Maze
[^4]: [[eppstein-2010-growth-and-decay-in-life-like-ca](pages/eppstein-2010-growth-and-decay-in-life-like-ca.md)] p.11 - "As Dean Hickerson observed, a pattern fades in rule r if and only if the same pattern forms a still life in the rule r̄ with the same birth conditions and complementary survival conditions"
[^5]: [[eppstein-2010-growth-and-decay-in-life-like-ca](pages/eppstein-2010-growth-and-decay-in-life-like-ca.md)] pp.11-14 [synthesis] - "A 2001 analysis by Hickerson, aided by Matthew Cook, Jason Summers, and the author"; "If a rule allows births with exactly one live neighbor, then it is immortal"; "If a rule causes all live cells with fewer than five live neighbors to survive, then it is immortal"; further immortal families B23/S0, B2 or B3 with S0123, B2/S01245, B345/S013; "77563 of them are immortal and 53214 of them are mortal. There remain 295 rules ... In particular this classification covers all rules that include B3"
[^6]: [[eppstein-2010-growth-and-decay-in-life-like-ca](pages/eppstein-2010-growth-and-decay-in-life-like-ca.md)] p.14 - "the immortal rule B3456/S013 has spaceships"; Fig. 7 c/4 and c/3 orthogonal spaceships; "the minimal bounding box or minimal bounding diamond of a pattern can never shrink. When this is true, it is impossible for a spaceship to exist"
[^7]: [[eppstein-2010-growth-and-decay-in-life-like-ca](pages/eppstein-2010-growth-and-decay-in-life-like-ca.md)] pp.14-25 [synthesis] - Fig. 8 "A map of the possible life-like rules, depicting regions of fertile, infertile, mortal, and immortal rules"; fertile-and-mortal tour (HighLife, B368/S12578, B36/S245, Morley, B37/S23, Day & Night, Diamoeba, B35/S236, B27/S0, B25/S4, B24/S, B2/S7); "Anneal (B4678/S35678) is mortal but infertile"; "B1357/S1357 is a fertile but immortal rule ... nothing but replicators"; B1/S012345678 fertile and immortal; "B4/S01234 is both infertile and immortal ... horizontal stripes"; Life Without Death immortal and fertile
[^8]: [[eppstein-2010-growth-and-decay-in-life-like-ca](pages/eppstein-2010-growth-and-decay-in-life-like-ca.md)] pp.14,16,18,20 [synthesis] - "It is our hypothesis that the rules most likely to support interesting patterns are the ones that are both fertile and mortal"; HighLife "should probably be assigned the same Wolfram class as Life, either Class II or Class IV"; Morley "either as Class II or Class IV"; B35/S236 quadratic growth pattern, "When started from a random initial condition, this rule remains chaotic, falling into Wolfram's Class III"
[^9]: [[eppstein-2010-growth-and-decay-in-life-like-ca](pages/eppstein-2010-growth-and-decay-in-life-like-ca.md)] pp.1-2,4-6 [synthesis] - Wolfram's classification "defines the interesting rules negatively rather than positively"; "many of the most interesting patterns in Life could not have been found in this way"; Greene's gun, the meta-pixel, the Caterpillar; "what we know rigorously is limited to random states in which the probability of a cell being live is a number ε that is very close to zero"; the new classification is "more objective ... more predictive (as we can classify large groups of rules without observing them individually)"
[^10]: [[eppstein-gliders-in-life-like-cellular-automata](pages/eppstein-gliders-in-life-like-cellular-automata.md)] raw/eppstein-ca-wolfram.md L82-84 [synthesis] - "Contraction impossible. If a rule includes B1 ... or includes B23/S0, the bounding box of a pattern can never shrink"; "Expansion impossible. If a rule does not include B2 or B3, any pattern remains within its initial bounding box"; "Both expansion and contraction possible. Only in the remaining cases can gliders exist"
[^11]: [[eppstein-2010-growth-and-decay-in-life-like-ca](pages/eppstein-2010-growth-and-decay-in-life-like-ca.md)] pp.25-27 [synthesis] - periodic backgrounds; rules with birth on zero and death on eight reverse the background on odd steps; "B01245/S0125 is a strobing version of Day & Night"; "a mortal combination of rule and background is one in which some finite perturbation to the background eventually stabilizes so that only the background remains. We know little about which combinations of rules and backgrounds are likely to be both fertile and mortal"
[^12]: [[eppstein-gliders-in-life-like-cellular-automata](pages/eppstein-gliders-in-life-like-cellular-automata.md)] raw/eppstein-ca-wanted.md L55 - "I would like a mathematical proof that certain rules (e.g. rules with B23, with B3 and none of S0-S5, or with all of B3/S34567) are unable to support gliders"; [[eppstein-2010-growth-and-decay-in-life-like-ca](pages/eppstein-2010-growth-and-decay-in-life-like-ca.md)] p.9 - "There are 64 B3 rules without any of B1245/S012345, all of which can be proven to be infertile"
