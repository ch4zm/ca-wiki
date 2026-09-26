---
title: Oscillator
category: Patterns
summary: A Life pattern that cycles through a fixed number of configurations (phases) and returns to its start; its period is the cycle length - blinker, toad, beacon and clock (2), pulsar (3), figure 8 (8), pentadecathlon (15), and engineered shuttles such as the queen bee (30) and twin bees (46)
tags: [pattern-class, life, oscillator, period, phase, shuttle]
sources: [cgol-ch1-early-life, fantastic-combinations-of-john-conways-life, theory-of-cellular-automata-a-survey]
created: 2026-09-25
updated: 2026-09-25
---

# Oscillator

## Description

An oscillator is a pattern that cycles between finitely many configurations; the
configuration it takes in each generation is a *phase*.[^1] Formally, a finite
configuration c with Gᵏ(c) = c for some k ≥ 2; the least such k is its period.[^2]

**Natural oscillators.** These appear in the ash of random soups:[^3]
- period 2: the [[blinker](pages/blinker.md)], toad, beacon and clock;
- period 3: the [[pulsar](pages/pulsar.md)];
- period 15: the [[pentadecathlon](pages/pentadecathlon.md)].

Soup searches have found about 180 distinct oscillators arising naturally
([[soup-search](pages/soup-search.md)]).[^4] Simon Norton's *figure 8* has period 8.[^5]
Groups of oscillators, such as the four blinkers of a traffic light, oscillate together
([[familiar-fours](pages/familiar-fours.md)]).

**Engineered oscillators.** A *shuttle* is an oscillator in which an unstable object
moves back and forth between stabilizing objects.[^6] Two come from chapter 1 of Johnston
and Greene:[^7]
- the [[queen-bee](pages/queen-bee.md)] shuttle, period 30;
- the [[twin-bees](pages/twin-bees.md)] shuttle, period 46.

Guns are oscillators that also emit a stream of moving objects
([[gosper-glider-gun](pages/gosper-glider-gun.md)]).

## Appearances in Sources

- [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] - phases, natural oscillators, shuttles
- [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] - figure 8
- [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] - §2.6: the periodic-orbit definition

## Related Concepts

- [[still-life](pages/still-life.md)] - the period-1 case
- [[spaceship](pages/spaceship.md)] - periodic up to a translation
- [[blinker](pages/blinker.md)], [[pulsar](pages/pulsar.md)], [[pentadecathlon](pages/pentadecathlon.md)] - natural examples
- [[queen-bee](pages/queen-bee.md)], [[twin-bees](pages/twin-bees.md)] - engineered shuttles

[^1]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.6 - "Patterns like this one, which cycle between finitely many different configurations, are called oscillators, and the configurations that they take on in individual generations are called phases"
[^2]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.10-11 [synthesis] - oscillator defined as a finite c with Gᵏ(c) = c for some k ≥ 2
[^3]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.6-7 [synthesis] - the blinker "oscillates back and forth between 2 phases"; "the pulsar and has period 3, appears rather frequently in random ash"; Fig. 1.8: "three oscillators with period 2, called toad, beacon and clock, and a period 15 oscillator called pentadecathlon"
[^4]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.28 - Okrasinski's screensaver catalogued "over 8 000 distinct still lifes and about 180 oscillators"
[^5]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.6 - "The 'figure 8' ..., an oscillator found by Norton, both resembles an 8 and has a period of 8"
[^6]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.11, n.8 - "The term 'shuttle' typically refers to oscillators in which an unstable object moves back and forth between stabilizing objects"
[^7]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.11,13 [synthesis] - "This period 30 oscillator is called the queen bee shuttle"; "the period 46 oscillator known as the twin bees shuttle"
