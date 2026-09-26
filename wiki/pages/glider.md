---
title: Glider
category: Patterns
summary: The five-cell Life spaceship that shifts one cell diagonally every four generations (speed c/4), named for its glide reflection; the commonest moving object in random soup, emitted by guns, and the signal of glider-stream circuits
tags: [pattern, life, glider, spaceship, signal]
sources: [eppstein-gliders-in-life-like-cellular-automata, lifewiki-catagolue, cgol-ch4-spaceships-and-moving-objects, cgol-ch3-oscillators, cgol-ch2-still-lifes, cgol-ch1-early-life, fantastic-combinations-of-john-conways-life, statistical-mechanics-of-cellular-automata, computation-at-the-edge-of-chaos, theory-of-cellular-automata-a-survey]
created: 2026-09-25
updated: 2026-09-25
---

# Glider

## Description

The glider is a five-cell [[spaceship](pages/spaceship.md)]. After two generations it has
shifted slightly and been reflected in a diagonal line, a "glide reflection" in geometry,
which gives it its name. After two more it is back in its original orientation, one cell
diagonally from where it started.[^1] It therefore moves at c/4, the fastest possible
diagonal speed.[^2]

**In soup.** The glider is one of the objects that most often appear in the ash of random
soups; it and the LWSS, MWSS and HWSS are by far the commonest spaceships random soups
produce ([[soup-search](pages/soup-search.md)]).[^3] The first glider ever observed came out of
the [[r-pentomino](pages/r-pentomino.md)] in generation 69, noticed by Richard K. Guy.[^4]

**Colour, lanes and timing.** Circuit design needs bookkeeping for gliders.[^5]
- **Colour.** Colour the grid like a checkerboard; a glider's colour is the colour of its
  leading cell in a fixed reference phase. It never changes as the glider moves, but a
  reflector may change it. The Snark is *colour-preserving* and the twin bees shuttle
  *colour-changing*, so every glider loop uses an even number of colour-changing
  reflectors ([[reflector](pages/reflector.md)]).
- **Lanes.** Lanes are diagonal lines of cells perpendicular to travel. One lane apart is
  a half diagonal (hd), two a full diagonal (fd), and colour is lane number mod 2.
- **Timing.** Timing compares how far ahead one glider is of another. Only differences in
  lane and timing matter.

**Tagalongs.** Though the glider has no real sparks, its rearmost cell can hold
*tagalongs*, objects that trail it without touching and collapse without it. Chains of
dozens of known c/4 tagalongs give a grammar of c/4 diagonal spaceships.[^6]

**Guns.** A glider gun creates an endless stream of gliders. The first found was the
period-30 [[gosper-glider-gun](pages/gosper-glider-gun.md)]; the
[[twin-bees](pages/twin-bees.md)] gun has period 46.[^7] The glider-producing
[[switch-engine](pages/switch-engine.md)] leaves a glider every 384 generations.[^8]

**Eating.** Gliders are deleted by [[eater](pages/eater.md)]s; eater 1 does it with a recovery time
of 4 generations, the fastest possible. A glider stream is erased most compactly by the
6-cell boat-bit.[^9]

**Reflection.** [[reflector](pages/reflector.md)]s turn gliders by 90 or 180 degrees; the Snark
does it with a repeat time of 43. Gliders can be no closer than 14 generations apart on
the same path without colliding.[^10]

**Collisions.** Gliders crashing in pairs can leave blocks: in one of Gardner's row
experiments, eight gliders collide in pairs to become eight [[block](pages/block.md)]s.[^11]

**Rule range.** The glider is not Life's alone. It runs unchanged in every rule from
B3/S23 up to B3678/S0235678, 256 Life-like rules in all, because in its cycle no dead cell
ever sees 6, 7 or 8 live neighbours and no live cell sees 0 or 5-8
([[rule-range](pages/rule-range.md)]; count and reading are own reasoning from the two
rulestrings).[^12] So a single glider proves all of those rules fertile
([[fertile-and-mortal-rules](pages/fertile-and-mortal-rules.md)]).

**As a signal.** Glider streams from guns serve as wires in Life circuits, with the
presence or absence of a glider as one bit. That is how
[[game-of-life](pages/game-of-life.md)] is shown to be computationally universal.[^13]
Langton reads gliders (signals) and [[blinker](pages/blinker.md)]s (storage) in that
construction as the moving and static structures typical of the
[[edge-of-chaos](pages/edge-of-chaos.md)].[^14]

## Appearances in Sources

- [[eppstein-gliders-in-life-like-cellular-automata](pages/eppstein-gliders-in-life-like-cellular-automata.md)] - its minimum and maximum rule in glider.db
- [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] - §4.1: colour, lanes, timing, tagalongs
- [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] - in soup, first observation, guns
- [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] - glide reflection, c/4
- [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] - Sec. V: glider-stream wires
- [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] - gliders as signals
- [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] - §2.6: period-four glider

## Related Concepts

- [[rule-range](pages/rule-range.md)] - the 256 rules it works in
- [[gun](pages/gun.md)] - guns of every period from 14; slide, armless and slow guns
- [[spaceship](pages/spaceship.md)] - tagalongs and diagonal speeds
- [[reflector](pages/reflector.md)] - turns gliders
- [[herschel](pages/herschel.md)] - emits a glider 21 generations in
- [[eater](pages/eater.md)] - deletes gliders
- [[spaceship](pages/spaceship.md)] - the class
- [[light-middle-heavyweight-spaceships](pages/light-middle-heavyweight-spaceships.md)] - the orthogonal natural spaceships
- [[gosper-glider-gun](pages/gosper-glider-gun.md)] - the first glider gun
- [[r-pentomino](pages/r-pentomino.md)] - source of the first glider seen

[^1]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.5 - "After two moves it has shifted slightly and been reflected in a diagonal line. Geometers call this a 'glide reflection'; hence the figure's name. After two more moves the glider has righted itself and moved one cell diagonally down and to the right from its initial position"
[^2]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.5 [synthesis] - "the maximum speed diagonally is a fourth the speed of light"; the glider "glides across the field at a fourth the speed of light"
[^3]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.7,28 [synthesis] - Fig. 1.6: the glider among objects that "frequently appear in the ash"; "the only spaceships that turned up were the four that we have already seen (the glider, LWSS, MWSS, and HWSS)" in Okrasinski's search; [[lifewiki-catagolue](pages/lifewiki-catagolue.md)] L124-128 [synthesis] - the asymmetric census also lists the sidecar, the loafer, the Schick engine and the Coe ship, none of which turned up among Okrasinski's 4.7 × 10^11 objects
[^4]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.17 - the R-pentomino produces "the very first glider that was ever observed in Life in generation 69"; n.20 first noticed by Richard K. Guy
[^5]: [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] pp.84-86 [synthesis] - color "stays constant as it moves, but can change when it hits a reflector"; checkerboard definition; the Snark is "a color-preserving reflector", the twin bees shuttle color-changing; "every glider loop must make use of an even number of color-changing reflectors"; lanes, "half diagonal (or hd)", "full diagonal (or fd)"; n.5 "a glider's color can just be thought of as its lane modulo 2"; timing; relative not absolute
[^6]: [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] pp.86-87 [synthesis] - "its rearmost cell is nonetheless far enough away from the body of the glider that it can carry some tagalongs"; tagalongs do not touch the glider but "if the glider is not present, the tagalong will collapse"; "dozens of different c/4 diagonal tagalongs known"; "a sort of grammar for c/4 diagonal spaceships"
[^7]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.11,13 [synthesis] - "Patterns that create glider streams are called glider guns"; the Gosper glider gun oscillates at period 30; the twin bees gun is "a period 46 glider gun"
[^8]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.14 - the glider-producing switch engine leaves "a glider every 384 generations"
[^9]: [[cgol-ch2-still-lifes](pages/cgol-ch2-still-lifes.md)] pp.39-41 [synthesis] - eater 1 has "a recovery time of 4 generations, which is the fastest possible for any glider eater"; the boat-bit "gives the smallest known way of erasing such a glider stream (in particular, it contains only 6 cells)"
[^10]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] pp.65-67 [synthesis] - reflectors output "another glider ... in a different direction"; the Snark "with a repeat time of 43 generations"; "The closest together that we can place gliders without them crashing into each other is 14 generations apart"
[^11]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.6 - "5-5-5-5-5 terminates with a 'spectacular display of eight gliders and eight blinkers. Then the gliders crash in pairs to become eight blocks.'"
[^12]: https://www.ics.uci.edu/~eppstein/ca/glider.db entry "Glider" - "Glider:John Conway, 1970:B3/S23:B3678/S0235678:4/2:-1:-1:3:3:bo$o$3o!"
[^13]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.639 [synthesis] - glider streams from glider guns used as wires, bits as presence or absence of gliders; "The Life-game cellular automaton is thus computationally universal"
[^14]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] pp.25-26 [synthesis] - the universality proof "employs propagating 'gliders' as signals and the period-2 'blinkers' as storage elements"
