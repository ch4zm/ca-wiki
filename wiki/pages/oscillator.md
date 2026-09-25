---
title: Oscillator
category: Patterns
summary: A Life pattern that returns to its original state after a fixed number of generations (its period); period-2 ones are Conway's "flip-flops" - blinker, traffic lights - with the pulsar (3), figure 8 (8) and pentadecathlon (15) as early larger examples
tags: [pattern-class, life, oscillator, period, flip-flop]
sources: [fantastic-combinations-of-john-conways-life, theory-of-cellular-automata-a-survey, statistical-mechanics-of-cellular-automata]
created: 2026-09-25
updated: 2026-09-25
---

# Oscillator

## Description

An oscillator is a pattern that repeats an endless cycle of two or more states. Along
with dying out and settling into a [[still-life](pages/still-life.md)], oscillating is
one of the three endings Conway designed [[game-of-life](pages/game-of-life.md)] to
allow.[^1] Formally, it is a finite configuration c with Gᵏ(c) = c for some k ≥ 2; the
least such k is its period.[^2]

**Period 2 ("flip-flops").** The [[blinker](pages/blinker.md)], a row of three, is the
simplest. Four isolated blinkers make *traffic lights*, a common end state.[^3]

**Longer periods (Gardner 1970).**[^4]
- *Figure 8*, found by Simon Norton, period 8.
- The [[pulsar](pages/pulsar.md)], period 3.
- The [[pentadecathlon](pages/pentadecathlon.md)], period 15.

Wolfram's 1983 survey lists oscillators of periods 3, 5 and 7, with more built by
composition.[^5] Gardner invited readers to find periodic figures beyond the ones he
showed.[^6]

## Appearances in Sources

- [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] - flip-flops, traffic lights, figure 8, pulsar, pentadecathlon
- [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] - §2.6: the periodic-orbit definition
- [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] - Sec. V: periods known in 1983

## Related Concepts

- [[still-life](pages/still-life.md)] - the period-1 case
- [[spaceship](pages/spaceship.md)] - periodic up to a translation
- [[blinker](pages/blinker.md)], [[pulsar](pages/pulsar.md)], [[pentadecathlon](pages/pentadecathlon.md)] - examples

[^1]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.2 - "fading away completely (from overcrowding or becoming too sparse), settling into a stable configuration that remains unchanged thereafter, or entering an oscillating phase in which they repeat an endless cycle of two or more periods"
[^2]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.10-11 [synthesis] - oscillator defined as a finite c with Gᵏ(c) = c for some k ≥ 2
[^3]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.4 [synthesis] - "Pattern e is the simplest of what are called 'flip-flops' (oscillating figures of period 2)"; tetromino e "becomes four isolated blinkers, a flip-flop called 'traffic lights.' It too is a common configuration"
[^4]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.6 [synthesis] - "figure 8 ... an oscillator found by Norton ... has a period of 8"; "pulsar CP 48-56-72, is an oscillator with a life cycle of period 3"; "the 'pentadecathlon,' with a life cycle of period 15"
[^5]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.637 [synthesis] - oscillators with periods 3, 5 and 7 known; others obtained by composition
[^6]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.5 - "Readers are also urged to search for periodic figures other than the ones given here"
