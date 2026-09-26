---
title: Brian's Brain (B2/S/C3)
category: Rules
summary: Brian Silverman's mid-1990s three-state Generations rule B2/S/C3 (Golly /2/3), Seeds plus a refractory state - a ready cell fires if exactly two neighbours are firing, fires for one step, then spends one step refractory; almost every pattern is a spaceship, rake or lightspeed wave, yet oscillators, photon logic gates and a Rule 110 unit cell make it Turing-complete
tags: [rule, generations, brians-brain, multistate, refractory, neural-analogy, b2-s-c3, turing-complete, phoenix]
sources: [lifewiki-brians-brain, lifewiki-list-of-generations-rules, lifewiki-generations, golly-help-generations]
created: 2026-09-25
updated: 2026-09-25
---

# Brian's Brain (B2/S/C3)

## Description

**The rule.** Brian's Brain is the [[generations-rule](pages/generations-rule.md)]
**B2/S/C3** (Golly **/2/3**), devised by Brian Silverman, who first considered it in the mid-1990s.[^1] It has three states, named
from a neural analogy: 0 *ready*, 1 *firing*, 2 *refractory* (also off, on, dying).[^2]
- A ready cell fires if exactly two of its eight neighbours are firing.
- A firing cell always becomes refractory next step. The empty "S" means no survival.
- A refractory cell returns to ready. Refractory cells do not count as firing, and they
  block births.

It is [[seeds-rule](pages/seeds-rule.md)] (B2/S) with one extra state: the same birth
condition, but a cell that fails to survive passes through the refractory state before
dying.[^3] It is described as "unquestionably one of the best known
and most beautiful CA rules".[^2]

**What it does.**[^4]
- **Nearly everything moves.** A cell fires for one step, then leaves a refractory tail
  behind, so patterns move in the direction of their firing edge. Almost every pattern is
  a [[spaceship](pages/spaceship.md)], and many spaceships are rakes. A common c/4 diagonal
  spaceship is the *butterfly*. Rocknlol found a c/5 orthogonal spaceship in 2020, the
  first orthogonal one slower than light.[^5]
- **Explosions.** Random starts typically explode at the speed of light, throwing off
  spaceships, rakes, breeders, puffers and wavestretchers. A 2 × 2 block of firing cells
  grows into an ever-expanding diamond of four diagonal waves at lightspeed.
- **Oscillators exist.** Every pattern is a [[phoenix](pages/phoenix.md)], so stable
  patterns are hard to build, but Michael Sweney found the first oscillators in December
  1999. One has just four firing and four dying cells and period 3. Period 4 is also known.
  Period 2 is impossible, as in every Generations rule with more than two states.
  Gun reactions give larger oscillators with periods divisible by 3, and periodic agars
  and wicks have been built.[^6]

**Computation.** Giles Edkins found lasers shooting the smallest photon by 2001. From them
signal reflectors, a duplicator, and AND, OR and XOR gates have been built. In 2020 Yoel
Matveyev built a Rule 110 unit cell for Brian's Brain, whose infinitely extendable tiling
proves the rule Turing-complete ([[rule-110](pages/rule-110.md)]). It avoids XOR gates,
using AND-NOT gates and toggle flip-flops, plus gun period doublers, memory units and
spaceship-flotilla generators to display Rule 110's output.[^7] A rule where nothing
survives and almost everything flies away can still hold a computer.

**Relatives.** Star Wars ([[star-wars-rule](pages/star-wars-rule.md)]) keeps Brian's
Brain's birth rule and adds survival on 3-5 plus a second dying state, which lets fixed
structures form. Brain 6 (B246/S6/C3) is a variation with many constructed patterns, and
Faders (B2/S2/C25) is described as a "genetic" cross of Life and Brian's Brain.[^8]

## Appearances in Sources

- [[lifewiki-brians-brain](pages/lifewiki-brians-brain.md)] - patterns, computation, Turing-completeness
- [[golly-help-generations](pages/golly-help-generations.md)] - listed as "/2/3 [Brian's Brain] - a chaotic rule by Brian Silverman"
- https://en.wikipedia.org/wiki/Brian%27s_Brain - rules and behaviour
- [[lifewiki-list-of-generations-rules](pages/lifewiki-list-of-generations-rules.md)] - neural analogy, first oscillators, relatives

## Related Concepts

- [[generations-rule](pages/generations-rule.md)] - its family
- [[star-wars-rule](pages/star-wars-rule.md)] - Brian's Brain with survival added
- [[spaceship](pages/spaceship.md)] - nearly every pattern is one
- [[seeds-rule](pages/seeds-rule.md)] - Brian's Brain minus the refractory state
- [[rule-110](pages/rule-110.md)] - emulated to prove universality
- [[wireworld](pages/wireworld.md)] - another Silverman rule whose signals move by refractory tails

[^1]: [[golly-help-generations](pages/golly-help-generations.md)] L11 - "/2/3 [Brian's Brain] - a chaotic rule by Brian Silverman"; [[lifewiki-brians-brain](pages/lifewiki-brians-brain.md)] L16 - "The rule was first considered by Brian Silverman in the mid-1990s."
[^2]: [[lifewiki-list-of-generations-rules](pages/lifewiki-list-of-generations-rules.md)] L56-61 - "B2/S/C3 /2/3 Brian's Brain Chaotic Brian Silverman Also called BB, or simply Brain, this is unquestionably one of the best known and most beautiful CA rules. If we name the possible cell values based on a simplistic neural analogy, viz. 0 = 'ready', 1 = 'firing', 2 = 'refractory', then this simple rule can be stated thusly: Only a cell in the ready state may fire and it will only do so if exactly 2 of its neighbors are firing. After firing for one step, a cell spends a step in the refractory state before regaining readiness"
[^3]: [[lifewiki-brians-brain](pages/lifewiki-brians-brain.md)] L16 - "It is similar to Seeds, but with an additional state; dead cells get born if they have exactly two live neighbors, and live cells never survive, but instead of dying immediately, they advance to a third state, not considered \"live\" for the purpose of cell birth, before dying."
[^4]: https://en.wikipedia.org/wiki/Brian%27s_Brain (2026-08-13) - "almost every pattern in Brian's Brain is a spaceship. Many spaceships are rakes"; "a 2×2 block of on cells will result in an ever-expanding diamond consisting of four diagonal waves that move across the plane at the pattern's speed of light"; [[lifewiki-brians-brain](pages/lifewiki-brians-brain.md)] L27 - "Usually, a random starting configuration in Brian's Brain will explode at the speed of light, emitting many spaceships, rakes, breeders, puffers and wavestretchers. Additionally, there is a common c/4 diagonal spaceship called the butterfly."
[^5]: [[lifewiki-brians-brain](pages/lifewiki-brians-brain.md)] L30 - "On December 31, 2020, Rocknlol found a c/5 orthogonal spaceship in Brian's Brain - the first orthogonal non-light-speed spaceship in this rule."
[^6]: [[lifewiki-list-of-generations-rules](pages/lifewiki-list-of-generations-rules.md)] L62 - "In December 1999, Michael Sweney discovered the first BB oscillators"; https://en.wikipedia.org/wiki/Brian%27s_Brain (2026-08-13) - "An example has just four on cells and four dying cells, and oscillates with period 3"; [[lifewiki-brians-brain](pages/lifewiki-brians-brain.md)] L28 - "Due to all patterns being phoenixes, it is not very easy to construct stable patterns in it. ... No period-2 oscillators exist (as in any Generations rule with more than two states); an example of a period-3 oscillator is shown to the left. Period-4 oscillators are also known to exist. Larger period oscillators with periods divisible by 3 can be constructed by gun reactions. Some periodic agars and wicks have also been constructed in Brian's Brain."
[^7]: [[lifewiki-brians-brain](pages/lifewiki-brians-brain.md)] L18,L29 [synthesis] - "On November 12, 2020, Yoel Matveyev published a Rule 110 unit cell for Brian's Brain, proving the rule Turing-complete ... does not contain XOR gates. Instead, it uses AND-NOT gates and toggle flip-flops"; "A group of lasers shooting the smallest photon were discovered by Giles Edkins no later than May 2001, based on which signal reflectors, duplicator, AND gate, OR gate and XOR gate have been explicitly constructed"; the tiling "demonstrates a usage of gun period doublers, flip-flops, arbitrary length memory units and custom spaceship flotilla generators used for Rule 110's output display"
[^8]: [[lifewiki-list-of-generations-rules](pages/lifewiki-list-of-generations-rules.md)] L243,L50-55,L110-115 [synthesis] - Star Wars "a successful combination of famous Brian's Brain with a stabilizing factor"; "B246/S6/C3 ... Brain 6 ... An interesting variation of the immortal Brian's Brain, with many patterns constructed"; "B2/S2/C25 ... Faders ... A 'genetic' cross of Life and Brian's Brain"
