---
title: Star Wars (B2/S345/C4)
category: Rules
summary: Mirek Wójtowicz's 1999 Generations rule B2/S345/C4 (Golly 345/2/4) - Brian's Brain's birth-on-two plus survival on 3-5 and two dying states; mostly lightspeed "photon" spaceships, cross-shaped still lifes, railroad oscillators of every period from 4 (none of period 2 or 3), abundant natural guns, and a photon logic technology with gates, an adder and a Rule 110 emulator
tags: [rule, generations, star-wars, mirekgro, multistate, refractory, b2-s345-c4, photon]
sources: [lifewiki-star-wars, lifewiki-list-of-generations-rules, lifewiki-generations, golly-help-generations]
created: 2026-09-25
updated: 2026-09-25
---

# Star Wars (B2/S345/C4)

## Description

**The rule.** Star Wars (also MirekGro) is the [[generations-rule](pages/generations-rule.md)]
**B2/S345/C4**, written **345/2/4** in Golly and MCell. Mirek Wójtowicz devised it in
March 1999.[^1]
- A dead cell (state 0) becomes live (state 1) if it has exactly two live neighbours.
- A live cell stays live with 3, 4 or 5 live neighbours. Otherwise it enters state 2 next
  tick, then state 3, then dies.

The two dying states count as neither live nor available for birth. Its name comes from
behaviour resembling "deep space battle scenes". It is described as "a successful
combination of famous Brian's Brain with a stabilizing factor": it shares
[[brians-brain](pages/brians-brain.md)]'s birth rule and adds survival on 3-5.[^2] The
two-state rule B2/S345, with no dying states, is a different rule, called Star
Trek.[^3]

**Character.** John Elliott wrote that it is "notable for the abundance, intricacy, and
variety of its naturally-occurring glider guns". He also noted that it is "active to a
degree almost reminiscent of Brain, with the distinction that it likes to build fixed
lego-like skeletal structures". In some runs these grow into universe-spanning
"shells".[^4] Large soups routinely produce guns, puffers, rakes, wickstretchers and
wavestretchers.[^5]

**Still lifes.** They exist with populations 5, 8, 10, 12 and above. The only 5-cell one
is the X-pentomino (a plus-shaped cross), a common extendable piece of larger still
lifes. Rectangular box-shaped still lifes cannot be broken from inside, so they act like
a finite universe: an m × n interior needs an (m + 4) × (n + 4) box.[^6]

**Oscillators.**[^7]
- Because of the two dying states, oscillators of period 2 and 3 are impossible.
- Many oscillators are *railroads*: lightspeed signals, each led by a live cell, running
  around the surface of a still life like trains on a track. They give at least one
  oscillator of every period p ≥ 4.
- Concretely, q X-pentominoes joined orthogonally make a still life with circumference
  6q + 6. When 6q + 6 = kp, k evenly spaced signals give a period-p oscillator.
- Chaotic puffers are abundant, so billiard-table oscillators are relatively common.

**Spaceships.** Most move at c orthogonally and are called *photons*; many are
extensible. An elementary c/6 diagonal spaceship was found on 21 March 2021 and later
shown to be extensible.[^8]

**Guns.** Stephen Silver built guns of periods 4-7 in May 1999. "Lasers" firing the
smallest photon exist at every period above 4: two still lifes attached to the
adjustable railroad oscillator.[^9]

**Photon circuitry.** The smallest photon is the basis of a developed technology.
Firing it at the edge of a still life splits it into two lightspeed signals, which travel
along the edge and can merge back into a photon elsewhere. Known photon conduits include
an eater, 90- and 180-degree reflectors, delays, and XOR, AND and OR gates. An adder
(Jeremy Tan, 2015) and a Rule 110 emulator (FWKnightship, 2020) have been built, so the
rule can compute ([[rule-110](pages/rule-110.md)]).[^10]

**Small seeds.** A domino expands in a diamond shape. A block grows quadratically,
producing wickstretchers. Diagonal lines of 6 or more cells become a family of period-5
oscillators.[^11]

**Relatives and software.** *Bombers* (B24/S345/C25) is a close variant with many more
dying states, known for ships, puffers and oscillators.[^12] Golly, LifeViewer and MCell
all run Star Wars, and Mirek's Cellebration holds a pattern collection.[^13]

## Appearances in Sources

- [[lifewiki-star-wars](pages/lifewiki-star-wars.md)] - the rule's patterns and technology
- [[lifewiki-list-of-generations-rules](pages/lifewiki-list-of-generations-rules.md)] - author, date, description, Elliott quote
- [[golly-help-generations](pages/golly-help-generations.md)] - listed as an example rule

## Related Concepts

- [[generations-rule](pages/generations-rule.md)] - its family
- [[brians-brain](pages/brians-brain.md)] - shares its birth rule, lacks its survival
- [[oscillator](pages/oscillator.md)], [[spaceship](pages/spaceship.md)], [[still-life](pages/still-life.md)] - its object types
- [[omniperiodicity](pages/omniperiodicity.md)] - railroads give every period from 4 up
- [[rule-110](pages/rule-110.md)] - emulated in Star Wars

[^1]: [[lifewiki-star-wars](pages/lifewiki-star-wars.md)] L10-18 - rulestrings "345/2/4", "B2/S345/C4", "B2/S345/G4"; "Star Wars, also known as MirekGro, is a Generations rule devised by Mirek Wójtowicz in March 1999. In this rule, a state-0 cell will become state 1 iff it has two state-1 neighbours. A state-1 cell does not change if it has 3, 4 or 5 state-1 neighbours, otherwise it will enter state 2 next tick and then state 3 before dying"
[^2]: [[lifewiki-star-wars](pages/lifewiki-star-wars.md)] L19 - "Named after its behaviour that resembles deep space battle scenes"; [[lifewiki-list-of-generations-rules](pages/lifewiki-list-of-generations-rules.md)] L243 - "a very interesting and beautiful rule producing deep space battle scenes; a paradise for patterns' creators in the tradition of Conway Life. It's a successful combination of famous Brian's Brain with a stabilizing factor"
[^3]: [[lifewiki-star-wars](pages/lifewiki-star-wars.md)] L16 - "This article is about the Generations rule. For the outer-totalistic rule, see OCA:Star Trek"
[^4]: [[lifewiki-star-wars](pages/lifewiki-star-wars.md)] L21-23 - "it is notable for the abundance, intricacy, and variety of its naturally-occurring glider guns. In general when running 'au naturel' StarWars is active to a degree almost reminiscent of Brain, with the distinction that it likes to build fixed lego-like skeletal structures. In some orbits this latter penchant reaches its zenith, and we get large universe-spanning 'shells'" — John Elliott
[^5]: [[lifewiki-star-wars](pages/lifewiki-star-wars.md)] L57 - "Usually, abundant linear growth patterns including guns, puffers, rakes, wickstretchers and wavestretchers emerge from sufficiently large soups"
[^6]: [[lifewiki-star-wars](pages/lifewiki-star-wars.md)] L43-44 - "Still lifes of population 5, 8, 10, 12 and above exists. The only 5-cell still life is the X-pentomino, or cross, which is a common extendable segment in larger still lifes. A group of still lifes in the shape of rectangular boxes are invincible from inside ... for a m × n plane the exterior has a bounding box of (m + 4) × (n + 4)"
[^7]: [[lifewiki-star-wars](pages/lifewiki-star-wars.md)] L46-48 - "Due to the two dying states, oscillators of period 2 and 3 are impossible"; railroads provide "at least one specimen for every period p ≥ 4"; "jointing q copies of the X-pentomino orthogonally will give a still life with circumference 6q + 6 cells ... If 6q + 6 = kp for some integer k, then k copies of the signal can be put in the circumference evenly to yield a period-p oscillator"; "billiard table oscillators are relatively common"
[^8]: [[lifewiki-star-wars](pages/lifewiki-star-wars.md)] L50 - "Most of the spaceships in Star Wars are at c orthogonal, thus are also referred to as photons. The structure is extensible to various degrees. On March 21, 2021, Rocknlol discovered a c/6 diagonal elementary spaceship which Dets65 found to be extensible"
[^9]: [[lifewiki-star-wars](pages/lifewiki-star-wars.md)] L51,L56 - "Guns of period 4, 5 ..., 6 and 7 ... in Star Wars (Stephen Silver, May 1999)"; "Guns (or rather, lasers) firing the smallest photon exist at all periods above 4, which can be constructed by connecting two still lifes to the aforementioned adjustable oscillator"
[^10]: [[lifewiki-star-wars](pages/lifewiki-star-wars.md)] L53,L59-60,L66-67 [synthesis] - photon conduits: "eater, 90-degree reflector, 180-degree reflector, 3-tick delay, 2-tick delay ... XOR gate with two outputs, AND gate, OR gate"; "shooting the photon at the edge of a still life can split it into two lightspeed signals, which travel on the edge and merge into a photon elsewhere"; "an adder and a Rule 110 emulator" (Jeremy Tan, March 2015; FWKnightship, November 2020)
[^11]: [[lifewiki-star-wars](pages/lifewiki-star-wars.md)] L62 - "The domino in this rule expands in a diamond shape, while the block grows quadratically generating wickstretchers. Diagonal lines of at least 6 cells in length evolve into a family of p5 oscillators"
[^12]: [[lifewiki-list-of-generations-rules](pages/lifewiki-list-of-generations-rules.md)] L44-49 - "B24/S345/C25 ... Bombers ... A close variant of the Star Wars rule with many more history steps, resulting in beautiful ships, puffers and oscillators"
[^13]: [[lifewiki-star-wars](pages/lifewiki-star-wars.md)] L24 - "A collection of patterns in Star Wars rule is in Mirek's Cellebration. The rule can also run in modern simulators (e.g. Golly and LifeViewer) that support Generations rules"; [[golly-help-generations](pages/golly-help-generations.md)] L18 - "345/2/4 [Star Wars] - an exploding rule by Mirek Wojtowicz"
