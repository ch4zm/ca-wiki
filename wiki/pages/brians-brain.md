---
title: Brian's Brain (B2/S/C3)
category: Rules
summary: Brian Silverman's three-state Generations rule B2/S/C3 (Golly /2/3) - a ready cell fires if exactly two neighbours are firing, fires for one step, then spends one step refractory; live cells never survive, so almost every pattern is a spaceship, rake or lightspeed wave, though small oscillators exist
tags: [rule, generations, brians-brain, multistate, refractory, neural-analogy, b2-s-c3]
sources: [lifewiki-list-of-generations-rules, lifewiki-generations, golly-help-generations]
created: 2026-09-25
updated: 2026-09-25
---

# Brian's Brain (B2/S/C3)

## Description

**The rule.** Brian's Brain is the [[generations-rule](pages/generations-rule.md)]
**B2/S/C3** (Golly **/2/3**), devised by Brian Silverman.[^1] It has three states, named
from a neural analogy: 0 *ready*, 1 *firing*, 2 *refractory* (also off, on, dying).[^2]
- A ready cell fires if exactly two of its eight neighbours are firing.
- A firing cell always becomes refractory next step. The empty "S" means no survival.
- A refractory cell returns to ready. Refractory cells do not count as firing, and they
  block births.

It is closely related to Silverman's two-state rule Seeds, which has the same birth
condition and no dying state.[^3] It is described as "unquestionably one of the best known
and most beautiful CA rules".[^2]

**What it does.**[^4]
- **Nearly everything moves.** A cell fires for one step, then leaves a refractory tail
  behind, so patterns move in the direction of their firing edge. Almost every pattern is
  a [[spaceship](pages/spaceship.md)], and many spaceships are rakes. A common c/4 diagonal
  spaceship is the *butterfly*.
- **Explosions.** Random starts typically explode at the speed of light, throwing off
  spaceships, rakes, breeders, puffers and wavestretchers. A 2 × 2 block of firing cells
  grows into an ever-expanding diamond of four diagonal waves at lightspeed.
- **Oscillators exist.** The rule is so lively that stable patterns are hard to build,
  but Michael Sweney found the first oscillators in December 1999. One has just four
  firing and four dying cells and period 3.[^5]

**Relatives.** Star Wars ([[star-wars-rule](pages/star-wars-rule.md)]) keeps Brian's
Brain's birth rule and adds survival on 3-5 plus a second dying state, which lets fixed
structures form. Brain 6 (B246/S6/C3) is a variation with many constructed patterns, and
Faders (B2/S2/C25) is described as a "genetic" cross of Life and Brian's Brain.[^6]

## Appearances in Sources

- [[golly-help-generations](pages/golly-help-generations.md)] - listed as "/2/3 [Brian's Brain] - a chaotic rule by Brian Silverman"
- https://en.wikipedia.org/wiki/Brian%27s_Brain - rules and behaviour
- [[lifewiki-list-of-generations-rules](pages/lifewiki-list-of-generations-rules.md)] - neural analogy, first oscillators, relatives

## Related Concepts

- [[generations-rule](pages/generations-rule.md)] - its family
- [[star-wars-rule](pages/star-wars-rule.md)] - Brian's Brain with survival added
- [[spaceship](pages/spaceship.md)] - nearly every pattern is one

[^1]: [[golly-help-generations](pages/golly-help-generations.md)] L11 - "/2/3 [Brian's Brain] - a chaotic rule by Brian Silverman"
[^2]: [[lifewiki-list-of-generations-rules](pages/lifewiki-list-of-generations-rules.md)] L56-61 - "B2/S/C3 /2/3 Brian's Brain Chaotic Brian Silverman Also called BB, or simply Brain, this is unquestionably one of the best known and most beautiful CA rules. If we name the possible cell values based on a simplistic neural analogy, viz. 0 = 'ready', 1 = 'firing', 2 = 'refractory', then this simple rule can be stated thusly: Only a cell in the ready state may fire and it will only do so if exactly 2 of its neighbors are firing. After firing for one step, a cell spends a step in the refractory state before regaining readiness"
[^3]: https://en.wikipedia.org/wiki/Brian%27s_Brain (2026-08-13) - "devised by Brian Silverman, which is very similar to his Seeds rule"; "a cell turns on if it was off but had exactly two neighbors that were on, just like the birth rule for Seeds. All cells that were 'on' go into the 'dying' state, which is not counted as an 'on' cell in the neighbor count, and prevents any cell from being born there. Cells that were in the dying state go into the off state"
[^4]: https://en.wikipedia.org/wiki/Brian%27s_Brain (2026-08-13) - "almost every pattern in Brian's Brain is a spaceship. Many spaceships are rakes"; "a 2×2 block of on cells will result in an ever-expanding diamond consisting of four diagonal waves that move across the plane at the pattern's speed of light"; "An example has just four on cells and four dying cells, and oscillates with period 3"; https://conwaylife.com/wiki/Brian's_Brain/Snippet (search excerpt) - "a random starting configuration in Brian's Brain will explode at the speed of light ..., emitting many spaceships, rakes, breeders, puffers and wavestretchers. Additionally, there is a common c/4 diagonal spaceship called the butterfly"
[^5]: [[lifewiki-list-of-generations-rules](pages/lifewiki-list-of-generations-rules.md)] L62 - "The rule is so lively that it's not easy to construct stable patterns in it. In December 1999, Michael Sweney discovered the first BB oscillators"; https://en.wikipedia.org/wiki/Brian%27s_Brain (2026-08-13) - "An example has just four on cells and four dying cells, and oscillates with period 3"
[^6]: [[lifewiki-list-of-generations-rules](pages/lifewiki-list-of-generations-rules.md)] L243,L50-55,L110-115 [synthesis] - Star Wars "a successful combination of famous Brian's Brain with a stabilizing factor"; "B246/S6/C3 ... Brain 6 ... An interesting variation of the immortal Brian's Brain, with many patterns constructed"; "B2/S2/C25 ... Faders ... A 'genetic' cross of Life and Brian's Brain"
