---
title: Seeds (B2/S)
category: Rules
summary: The Life-like rule B2/S - birth on exactly two neighbours, no survival at all, so every pattern is a phoenix; still, most patterns explode, 4-cell photons fly at lightspeed, oscillators of many periods exist, and a Rule 110 unit stripe makes it Turing-complete; Brian's Brain is Seeds plus a refractory state
tags: [rule, life-like, seeds, b2-s, phoenix, explosive, turing-complete, photon]
sources: [lifewiki-seeds, lifewiki-brians-brain, lifewiki-life-like-cellular-automaton]
created: 2026-09-25
updated: 2026-09-25
---

# Seeds (B2/S)

## Description

**The rule.** Seeds is the [[life-like-cellular-automaton](pages/life-like-cellular-automaton.md)]
**B2/S** (S/B form **/2**, rule integer 4). A dead cell is born with exactly two live
neighbours, and the survival list is empty, so every live cell dies in the next
generation. Brian Silverman first investigated it and Mirek Wójtowicz named it.[^1] Its
black/white reversal is B012345678/S01234578.[^2]

**Every pattern is a phoenix.** With no survival, all live cells die every generation, so
every pattern is a [[phoenix](pages/phoenix.md)]. Yet most patterns still explode
quadratically, and no still life can exist.[^1][^3] Every Seeds oscillator is therefore a
phoenix oscillator (own reasoning, from the two facts above).

**What lives in it.**
- **Oscillators** of periods 2, 3, 4, 5, 6, 8, 12, 15, 20, 24 and 40 are known. The
  smallest is the 2-cell duoplet (period 2); the 3-cell shiplet and the 4-cell radar,
  lever and anchor follow.[^3]
- **Photons.** B2 lets spaceships reach the speed of light. The three smallest are
  4-cell, period-1 *photons*; larger lightspeed ships exist too. Slower ships run at 3c/5,
  c/2, c/4 and c/5 orthogonally and c/3 and c/4 diagonally.[^4]
- **Guns and growth.** Two period-4 photon guns (lasers) are known, but their streams are
  too dense for signal logic. Lightspeed puffers, photon rakes and a rake puffer breeder
  have been engineered ([[puffer](pages/puffer.md)], [[breeder](pages/breeder.md)]).[^5]

**Turing-complete.** Peter Naszvadi proved in 2020 that Seeds is Turing-complete on an
infinite, periodically tiled grid, by building a Rule 110 "unit stripe"
([[rule-110](pages/rule-110.md)]).[^6] So a rule in which nothing survives a single tick
can still compute, provided the tiling supplies the structure.

**Relatives.** [[brians-brain](pages/brians-brain.md)] is Seeds with one extra state: a
cell that fires spends a step refractory before it can fire again. That refractory tail
turns Seeds' explosions into directed motion.[^7] B2 rules in general are explosive or
expanding, because a domino at a pattern's edge breeds a new domino
([[life-like-cellular-automaton](pages/life-like-cellular-automaton.md)]).[^8]

## Appearances in Sources

- [[lifewiki-seeds](pages/lifewiki-seeds.md)] - the rule and its patterns
- [[lifewiki-brians-brain](pages/lifewiki-brians-brain.md)] - Brian's Brain as Seeds plus a third state

## Related Concepts

- [[brians-brain](pages/brians-brain.md)] - Seeds with a refractory state
- [[phoenix](pages/phoenix.md)] - every Seeds pattern is one
- [[rule-110](pages/rule-110.md)] - emulated to prove universality
- [[generations-rule](pages/generations-rule.md)] - Seeds is B2/S/C2; add states and it becomes Brian's Brain
- [[spaceship](pages/spaceship.md)], [[oscillator](pages/oscillator.md)] - its object types

[^1]: [[lifewiki-seeds](pages/lifewiki-seeds.md)] L12-15,L20 - rulestrings "/2", "B2/S", rule integer 4; "Seeds is a Life-like cellular automaton in which a new cell is born when it has exactly two live neighbours, and live cells never survive to the next generation. Even though all the living cells die in every generation (turning every pattern into a phoenix), most patterns are still exploding quadratically. The rule was initially investigated by Brian Silverman and named by Mirek Wójtowicz."
[^2]: [[lifewiki-seeds](pages/lifewiki-seeds.md)] L18-19 - "Black/white reversal B012345678/S01234578"
[^3]: [[lifewiki-seeds](pages/lifewiki-seeds.md)] L24 - "No still lifes can exist in this rule, due to the absence of survival conditions. Known oscillator periods include 2, 3, 4, 5, 6, 8, 12, 15, 20, 24, and 40. The five smallest oscillators are duoplet (2 cells, p2), shiplet (3 cells, p2), radar (4 cells, p4), lever (4 cells, p4) and anchor (4 cells, p4)."
[^4]: [[lifewiki-seeds](pages/lifewiki-seeds.md)] L31-32 - "With B2, the Seeds rule allows spaceships to travel at the speed of light. The three smallest ones, known as photons, have a period of 1 and consist of only 4 cells each. Larger lightspeed spaceships with higher periods are also known. There also exist 3c/5, c/2, c/4, and c/5 orthogonal spaceships and c/3 and c/4 diagonal spaceships."
[^5]: [[lifewiki-seeds](pages/lifewiki-seeds.md)] L37,L39 - "Two period-4 photon guns (lasers) have been found, yet their photon stream is too dense to implement any signal logic."; "Quite a lot of progress has been made in producing engineered patterns consisting of lightspeed puffers and photon rakes. A rake puffer breeder is known."
[^6]: [[lifewiki-seeds](pages/lifewiki-seeds.md)] L21 - "On October 30, 2020, Peter Naszvadi proved that Seeds is Turing-complete on an infinite, periodically-tiled grid by constructing a Rule 110 \"unit stripe\"."
[^7]: [[lifewiki-brians-brain](pages/lifewiki-brians-brain.md)] L16 - "It is similar to Seeds, but with an additional state; dead cells get born if they have exactly two live neighbors, and live cells never survive, but instead of dying immediately, they advance to a third state, not considered \"live\" for the purpose of cell birth, before dying."
[^8]: [[lifewiki-life-like-cellular-automaton](pages/lifewiki-life-like-cellular-automaton.md)] L27 - "All rules where the lowest birth condition is 2 neighboring ON cells are exploding or expanding in character; this is largely due to the fact that a domino at the edge of a pattern will give rise to a new domino, also located at the edge of the daughter pattern."
