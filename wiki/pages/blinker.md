---
title: Blinker
category: Patterns
summary: A row of three live cells that alternates between horizontal and vertical - the simplest Life oscillator (period 2); four of them make "traffic lights", and blinkers serve as storage in glider-logic circuits
tags: [pattern, life, oscillator, blinker, traffic-lights, period-2]
sources: [fantastic-combinations-of-john-conways-life, statistical-mechanics-of-cellular-automata, computation-at-the-edge-of-chaos]
created: 2026-09-25
updated: 2026-09-25
---

# Blinker

## Description

The blinker is a row of three live cells. It alternates between horizontal and vertical
every move, making it the simplest period-2 [[oscillator](pages/oscillator.md)], which
Conway calls a "flip-flop".[^1] Wolfram's 1983 survey also lists it as the basic period-2
structure.[^2]

**Traffic lights.** Four isolated blinkers form *traffic lights*, a common end state. One of
the five tetrominoes reaches it after nine moves, three of the pentominoes reach it quickly,
and a row of five counters ends in it. A row of 16 counters gives *big traffic lights*,
eight blinkers.[^3]

**In circuits.** Langton notes that the Life universality proof uses period-2 blinkers
as storage elements alongside [[glider](pages/glider.md)] signals.[^4]

## Appearances in Sources

- [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] - name, flip-flops, traffic lights
- [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] - Sec. V: the period-2 blinker
- [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] - blinkers as storage

## Related Concepts

- [[oscillator](pages/oscillator.md)] - its class
- [[glider](pages/glider.md)] - the signal to its storage in Life circuits
- [[game-of-life](pages/game-of-life.md)] - the rule

[^1]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.4 - "Pattern e is the simplest of what are called 'flip-flops' (oscillating figures of period 2). It alternates between horizontal and vertical rows of three. Conway calls it a 'blinker'"
[^2]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.637 [synthesis] - the "blinker" with period two
[^3]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] pp.4,6 [synthesis] - tetromino e "After nine moves it becomes four isolated blinkers, a flip-flop called 'traffic lights.' It too is a common configuration"; of the pentominoes "three in a short time become traffic lights"; "Five counters result in traffic lights"; "16 give 'big traffic lights' (eight blinkers)"
[^4]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] pp.25-26 [synthesis] - the universality proof "employs propagating 'gliders' as signals and the period-2 'blinkers' as storage elements"
