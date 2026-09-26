---
title: Still life
category: Patterns
summary: A Life pattern that never changes from one generation to the next (a finite fixed point of the rule); the block, tub, boat, ship, beehive, loaf and pond are the commonest in random ash
tags: [pattern-class, life, still-life, stable]
sources: [cgol-ch1-early-life, fantastic-combinations-of-john-conways-life, theory-of-cellular-automata-a-survey]
created: 2026-09-25
updated: 2026-09-25
---

# Still life

## Description

A still life is a pattern that remains unchanged from one generation to the next: every
live cell survives and no dead cell is born.[^1] Formally, a finite configuration c with
G(c) = c, a fixed point of the global map.[^2] Still lifes, [[oscillator](pages/oscillator.md)]s
and [[spaceship](pages/spaceship.md)]s are the three basic object types in
[[game-of-life](pages/game-of-life.md)], the building blocks of everything larger.[^3]
Most starting patterns end as still lifes or oscillators.[^4]

**Common still lifes.** Seven turn up constantly in the ash of random soups: the
[[block](pages/block.md)], tub, boat, ship, [[beehive](pages/beehive.md)], loaf and
pond.[^5] Groups of still lifes can also be stable together, such as the honey farm
(four beehives) and the blockade (four blocks) ([[familiar-fours](pages/familiar-fours.md)]).

**Eating.** A still life can destroy another object and survive; a block placed next to
a beehive destroys it in 7 generations and is left unharmed. Such stabilizers turn
unstable objects into oscillators ([[queen-bee](pages/queen-bee.md)]).[^6]

**Counts in soup.** Automated soup searches have catalogued over 8,000 distinct still
lifes arising naturally ([[soup-search](pages/soup-search.md)]).[^7]

## Appearances in Sources

- [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] - definition, common ash still lifes, eating
- [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] - the term
- [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] - §2.6: the fixed-point definition

## Related Concepts

- [[oscillator](pages/oscillator.md)] - the periodic generalization; a still life is period 1
- [[spaceship](pages/spaceship.md)] - periodic up to a translation
- [[block](pages/block.md)], [[beehive](pages/beehive.md)] - examples
- [[familiar-fours](pages/familiar-fours.md)] - stable groups of four
- [[game-of-life](pages/game-of-life.md)] - the rule

[^1]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.4 - "A pattern like this that remains unchanged from one generation to the next is called a still life"
[^2]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.10-11 [synthesis] - still life defined as a finite configuration c with G(c) = c
[^3]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.7 - "Still lifes, oscillators, and spaceships are the three most basic types of objects that we will study in Life, and they form the building blocks of all of the more complicated patterns"
[^4]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.2 - "Most starting patterns either reach stable figures--Conway calls them 'still lifes'--that cannot change or patterns that oscillate forever"
[^5]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.7, Fig. 1.6 - "seven still lifes, called the block, tub, boat, ship, beehive, loaf and pond ... All of these objects frequently appear in the ash left behind by chaotic patterns"
[^6]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.10-11 [synthesis] - "a block being placed next to a beehive results in the beehive being destroyed and the block surviving unharmed (we thus say that the block eats the beehive)"; Fig. 1.16: 7 generations
[^7]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.28 - Okrasinski's screensaver "cataloged over 4.7 × 10^11 ash objects, including over 8 000 distinct still lifes"
