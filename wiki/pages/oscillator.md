---
title: Oscillator
category: Patterns
summary: A Life pattern that cycles through a fixed number of configurations (phases) and returns to its start; its period is the cycle length - blinker, toad, beacon and clock (2), pulsar (3), figure 8 (8), pentadecathlon (15), and engineered shuttles such as the queen bee (30) and twin bees (46)
tags: [pattern-class, life, oscillator, period, phase, shuttle]
sources: [cgol-ch3-oscillators, cgol-ch2-still-lifes, cgol-ch1-early-life, fantastic-combinations-of-john-conways-life, theory-of-cellular-automata-a-survey]
created: 2026-09-25
updated: 2026-09-25
---

# Oscillator

## Description

An oscillator is a pattern that cycles between finitely many configurations; the
configuration it takes in each generation is a *phase*.[^1] Formally, a finite
configuration c with Gᵏ(c) = c for some k ≥ 2; the least such k is its period.[^2]

**Terms.** The oscillating cells are the *rotor*; cells alive in every generation are
the *stator*. "pn" abbreviates "period n". An oscillator is *non-trivial* only if some
cell oscillates at its full period, which rules out side-by-side oscillators of
different periods.[^3] Life has oscillators of every period
([[omniperiodicity](pages/omniperiodicity.md)]).

**Natural oscillators.** These appear in the ash of random soups:[^4]
- period 2: the [[blinker](pages/blinker.md)], toad, beacon and clock;
- period 3: the [[pulsar](pages/pulsar.md)];
- period 15: the [[pentadecathlon](pages/pentadecathlon.md)].

Soup searches have found about 180 distinct oscillators arising naturally
([[soup-search](pages/soup-search.md)]).[^5] Simon Norton's *figure 8* has period 8.[^6] Rarer
natural ones turn up in computer soup searches, such as the bipole (p2), jam (p3), mold
(p4) and octagon 2 (p5).[^7]
Groups of oscillators, such as the four blinkers of a traffic light, oscillate together
([[familiar-fours](pages/familiar-fours.md)]).

**Engineered oscillators.** The main construction methods:[^8]
- **Billiard tables**: the rotor is enclosed in the stator. A box is walled with
  induction coils and seeded with debris that bounces inside without escaping. A 4 × 3
  box works; a 5 × 3 box cannot be filled.
- **Stabilized corners**: [[eater](pages/eater.md)]s absorb debris bouncing between them. Two eaters
  (p3) is two eater 1s eating and rebuilding each other's corners; the snacker (p9) is a
  pentadecathlon among four eater 1s.
- **Sparks** combine oscillators into composite periods ([[sparker](pages/sparker.md)]).
- **Hasslers and shuttles** push standard unstable objects back and forth
  ([[hassler](pages/hassler.md)]).
- **Tracks**: glider loops with reflectors ([[reflector](pages/reflector.md)]) and Herschel
  tracks ([[herschel](pages/herschel.md)]) give every large period.

Oscillators whose every live cell dies each generation are [[phoenix](pages/phoenix.md)]es.

A *shuttle* is an oscillator in which an unstable object
moves back and forth between stabilizing objects.[^9] Two examples:[^10]
- the [[queen-bee](pages/queen-bee.md)] shuttle, period 30;
- the [[twin-bees](pages/twin-bees.md)] shuttle, period 46.

The maximum density of an oscillator is open; averaged over phases it seems never to
exceed 1/2, and 8/13 is a proved upper bound ([[still-life-density](pages/still-life-density.md)]).[^11]

Guns are oscillators that also emit a stream of moving objects
([[gosper-glider-gun](pages/gosper-glider-gun.md)]).

## Appearances in Sources

- [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] - the whole chapter: construction methods, omniperiodicity, phoenices
- [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] - phases, natural oscillators, shuttles
- [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] - figure 8
- [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] - §2.6: the periodic-orbit definition

## Related Concepts

- [[omniperiodicity](pages/omniperiodicity.md)] - oscillators exist of every period
- [[sparker](pages/sparker.md)], [[hassler](pages/hassler.md)], [[reflector](pages/reflector.md)], [[herschel](pages/herschel.md)], [[phoenix](pages/phoenix.md)] - construction methods and special kinds
- [[still-life-density](pages/still-life-density.md)] - the open density question for oscillators
- [[still-life](pages/still-life.md)] - the period-1 case
- [[spaceship](pages/spaceship.md)] - periodic up to a translation
- [[blinker](pages/blinker.md)], [[pulsar](pages/pulsar.md)], [[pentadecathlon](pages/pentadecathlon.md)] - natural examples
- [[queen-bee](pages/queen-bee.md)], [[twin-bees](pages/twin-bees.md)] - engineered shuttles
- [[apgsearch](pages/apgsearch.md)], [[catagolue](pages/catagolue.md)] - soup search, where many oscillators (Rob's p16, 32P21, 30P25) were first found

[^1]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.6 - "Patterns like this one, which cycle between finitely many different configurations, are called oscillators, and the configurations that they take on in individual generations are called phases"
[^2]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.10-11 [synthesis] - oscillator defined as a finite c with Gᵏ(c) = c for some k ≥ 2
[^3]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] pp.54,57 [synthesis] - n.3 "the cells that oscillate are called its rotor and the cells that stay alive for all generations are called its stator"; "pn" stands for "period n"; "an oscillator must have at least one cell that oscillates at its full period in order to be considered non-trivial"
[^4]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.6-7 [synthesis] - the blinker "oscillates back and forth between 2 phases"; "the pulsar and has period 3, appears rather frequently in random ash"; Fig. 1.8: "three oscillators with period 2, called toad, beacon and clock, and a period 15 oscillator called pentadecathlon"
[^5]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.28 - Okrasinski's screensaver catalogued "over 8 000 distinct still lifes and about 180 oscillators"
[^6]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.6 - "The 'figure 8' ..., an oscillator found by Norton, both resembles an 8 and has a period of 8"
[^7]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] pp.53-54, Fig. 3.1 - "Some more small naturally occurring (but rare) oscillators that can be found via computer-assisted soup searches": bipole (p2), jam (p3), mold (p4), octagon 2 (p5)
[^8]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] §§3.1-3.6, pp.54-73 [synthesis] - billiard tables ("all of the oscillating cells are enclosed entirely within some stable pattern"); 4 × 3 box works, 5 × 3 box cannot be filled; two eaters (p3) and snacker (p9); sparks; hasslers and shuttles; glider loops; Herschel tracks
[^9]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.11, n.8 - "The term 'shuttle' typically refers to oscillators in which an unstable object moves back and forth between stabilizing objects"
[^10]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.11,13 [synthesis] - "This period 30 oscillator is called the queen bee shuttle"; "the period 46 oscillator known as the twin bees shuttle"
[^11]: [[cgol-ch2-still-lifes](pages/cgol-ch2-still-lifes.md)] p.48 [synthesis] - "The related problem of finding the maximum density of an oscillator remains open"; average density "never greater than 1/2" appears to hold; "an infinite pattern cannot have average density ... that exceeds 8/13"
