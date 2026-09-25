---
title: Pulsar
category: Patterns
summary: "Pulsar CP 48-56-72", a period-3 Life oscillator whose three phases have 48, 56 and 72 live cells; it grows from a small heptomino in 32 generations
tags: [pattern, life, oscillator, pulsar, period-3]
sources: [fantastic-combinations-of-john-conways-life]
created: 2026-09-25
updated: 2026-09-25
---

# Pulsar

## Description

Gardner names it "pulsar CP 48-56-72". It is a period-3
[[oscillator](pages/oscillator.md)]: its three states have 48, 56 and 72 live cells, and
then it returns to 48.[^1]

**Where it comes from.**[^2]
- A heptomino, a row of five cells with one cell directly below each end, generates it in
  32 moves.
- Two 5-cell rows separated by one empty cell generate it in 21 moves.

## Appearances in Sources

- [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] - name, phase populations, precursors

## Related Concepts

- [[oscillator](pages/oscillator.md)] - its class
- [[pentadecathlon](pages/pentadecathlon.md)] - the other large oscillator in Gardner's column

[^1]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.6 - "The form c, called 'pulsar CP 48-56-72,' is an oscillator with a life cycle of period 3. The state shown here has 48 counters, state two has 56 and state 3 has 72, after which the pulsar returns to 48 again"
[^2]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.6 [synthesis] - "It is generated in 32 moves by a heptomino consisting of a horizontal row of five counters with one counter directly below each end counter of the row"; "The 5-5 row generates the pulsar CP 48-56-72 in 21 moves"
