---
title: Pulsar
category: Patterns
summary: A period-3 Life oscillator whose three phases have 48, 56 and 72 live cells; common in random ash for its size, and grows from small precursors such as a heptomino in 32 generations
tags: [pattern, life, oscillator, pulsar, period-3]
sources: [cgol-ch1-early-life, fantastic-combinations-of-john-conways-life]
created: 2026-09-25
updated: 2026-09-25
---

# Pulsar

## Description

The pulsar is a period-3 [[oscillator](pages/oscillator.md)]. Its three phases have 48,
56 and 72 live cells, after which it returns to 48; Gardner calls it "pulsar CP
48-56-72".[^1] It appears rather frequently in random ash for its size, more often than
the six-cell clock.[^2]

**Precursors.**[^3]
- A heptomino, a row of five cells with one cell directly below each end, becomes a
  pulsar in 32 generations.
- Two 5-cell rows separated by one empty cell become one in 21 generations.

## Appearances in Sources

- [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] - frequency in soup
- [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] - phase populations, precursors

## Related Concepts

- [[oscillator](pages/oscillator.md)] - its class
- [[pentadecathlon](pages/pentadecathlon.md)] - another large natural oscillator
- [[soup-search](pages/soup-search.md)] - frequency in ash

[^1]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.6 - "The form c, called 'pulsar CP 48-56-72,' is an oscillator with a life cycle of period 3. The state shown here has 48 counters, state two has 56 and state 3 has 72, after which the pulsar returns to 48 again"
[^2]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.7,19 [synthesis] - "the pulsar and has period 3, appears rather frequently in random ash for its size"; the clock "appears in random soups much less frequently than some much larger objects like the period 3 pulsar"
[^3]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.6 [synthesis] - "It is generated in 32 moves by a heptomino consisting of a horizontal row of five counters with one counter directly below each end counter of the row"; "The 5-5 row generates the pulsar CP 48-56-72 in 21 moves"
