---
title: Blinker
category: Patterns
summary: A row of three live cells that alternates between horizontal and vertical - the simplest Life oscillator (period 2) and the commonest in soup; four of them make a traffic light, and blinkers serve as storage in glider-logic circuits
tags: [pattern, life, oscillator, blinker, traffic-light, period-2]
sources: [cgol-ch1-early-life, fantastic-combinations-of-john-conways-life, computation-at-the-edge-of-chaos]
created: 2026-09-25
updated: 2026-09-25
---

# Blinker

## Description

The blinker is a row of three live cells that rotates by 90 degrees every generation,
alternating between two phases. It is the simplest period-2
[[oscillator](pages/oscillator.md)] and appears frequently in the ash of random
soups.[^1]

**Traffic light.** Four blinkers form a *traffic light*
([[familiar-fours](pages/familiar-fours.md)]). The T-tetromino explodes into one in 9
generations, and that common explosion is why blinkers so often appear in this
formation.[^2] A row of five cells also ends as a traffic light, and a row of 16 as eight
blinkers.[^3]

**In circuits.** The Life universality construction uses period-2 blinkers as storage
elements alongside [[glider](pages/glider.md)] signals.[^4]

## Appearances in Sources

- [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] - in soup; the T-tetromino and traffic light
- [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] - name; row fates
- [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] - blinkers as storage

## Related Concepts

- [[oscillator](pages/oscillator.md)] - its class
- [[familiar-fours](pages/familiar-fours.md)] - the traffic light
- [[glider](pages/glider.md)] - the signal to its storage in Life circuits

[^1]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.5-7 [synthesis] - "the blinker that rotates itself by 90 degrees every generation"; "oscillates back and forth between 2 phases every 2 generations"; Fig. 1.6: among objects that "frequently appear in the ash"
[^2]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.8 - the T-tetromino "explodes into an arrangement of 4 blinkers that is called a traffic light"; "the common T-tetromino explosion is exactly why blinkers appear in this formation so frequently"; Fig. 1.11: 9 generations
[^3]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.6 - "Five counters result in traffic lights"; "16 give 'big traffic lights' (eight blinkers)"
[^4]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] pp.25-26 [synthesis] - the universality proof "employs propagating 'gliders' as signals and the period-2 'blinkers' as storage elements"
