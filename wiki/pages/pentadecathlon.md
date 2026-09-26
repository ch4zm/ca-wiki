---
title: Pentadecathlon
category: Patterns
summary: The period-15 Life oscillator that a straight row of ten live cells evolves into; it changes size through its cycle and appears reasonably often in random ash
tags: [pattern, life, oscillator, pentadecathlon, period-15]
sources: [cgol-ch3-oscillators, cgol-ch1-early-life, fantastic-combinations-of-john-conways-life]
created: 2026-09-25
updated: 2026-09-25
---

# Pentadecathlon

## Description

The pentadecathlon is an [[oscillator](pages/oscillator.md)] with period 15, which is
what a straight row of 10 live cells becomes.[^1] It appears reasonably often in random
ash, more often than the much smaller clock. Unlike the smaller oscillators, it pulsates
and changes size as it goes through its period, a property that makes it useful in later
constructions.[^2]

**Sparks and reflection.** In one phase it gives off two domino sparks that die at once
and can be used without disturbing it. Paired with other sparkers it makes composite
periods; next to a snacker (itself a pentadecathlon between four eater 1s) it gives a
non-trivial period 45 ([[sparker](pages/sparker.md)]).[^3] It also reflects a glider by 180 degrees;
two pentadecathlons make glider loops of periods 60 + 120n
([[reflector](pages/reflector.md)]).[^4]

## Appearances in Sources

- [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] - domino sparks, snacker, 180-degree glider reflection
- [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] - frequency in soup, changing size
- [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] - origin from a row of ten

## Related Concepts

- [[sparker](pages/sparker.md)] - its domino sparks
- [[reflector](pages/reflector.md)] - it reflects gliders by 180 degrees
- [[oscillator](pages/oscillator.md)] - its class
- [[pulsar](pages/pulsar.md)] - another large natural oscillator
- [[soup-search](pages/soup-search.md)] - frequency in ash

[^1]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.6 - "10 lead to the 'pentadecathlon,' with a life cycle of period 15"
[^2]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.7,19 [synthesis] - "the pentadecathlon, which has a surprisingly large period of 15 ... it pulsates and changes in size as it moves through its period--a property that will be very useful for us later on"; the clock appears "much less frequently than ... the period 15 pentadecathlon"
[^3]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] pp.56-57 [synthesis] - "the pentadecathlon, which gives off two sparks in one of its phases"; the sparks "can be erased or manipulated without affecting the subsequent evolution"; snacker is "a pentadecathlon in the middle of four eater 1s"; pentadecathlon plus snacker is a non-trivial period 45 oscillator
[^4]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] p.65 [synthesis] - "the pentadecathlon" directly reflects a glider by 180 degrees; smallest such oscillator has period 60; "period 60 + 120n for any integer n ≥ 0"
