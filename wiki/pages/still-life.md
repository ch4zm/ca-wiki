---
title: Still life
category: Patterns
summary: A Life pattern that never changes from one generation to the next (a finite fixed point of the rule); Conway's term, with the block, beehive and honey farm as the first named examples
tags: [pattern-class, life, still-life, stable]
sources: [fantastic-combinations-of-john-conways-life, theory-of-cellular-automata-a-survey, statistical-mechanics-of-cellular-automata]
created: 2026-09-25
updated: 2026-09-25
---

# Still life

## Description

A still life is a stable figure that cannot change: every live cell survives and no dead
cell is born. The name is Conway's. Most starting patterns in
[[game-of-life](pages/game-of-life.md)] end either as still lifes or as
[[oscillator](pages/oscillator.md)]s.[^1] Formally, a still life is a finite
configuration c with G(c) = c, a fixed point of the global map.[^2]

**Examples.**
- The [[block](pages/block.md)], a 2 × 2 square, the smallest.[^3]
- The [[beehive](pages/beehive.md)], six cells, which Gardner calls frequently
  produced.[^4]
- The *honey farm*, four beehives, stable as a group. A horizontal row of seven counters
  becomes one after 14 moves.[^5]

Gardner's column illustrated the 12 commonest still lifes; the figure is not reproduced
in the wiki's copy.[^6] In Wolfram's 1983 survey the block and beehive appear as the
"square" and "hexagon".[^7]

## Appearances in Sources

- [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] - the term, the block, beehive and honey farm
- [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] - §2.6: the fixed-point definition
- [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] - Sec. V: the square and hexagon as standard structures

## Related Concepts

- [[oscillator](pages/oscillator.md)] - the periodic generalization; a still life is period 1
- [[spaceship](pages/spaceship.md)] - periodic up to a translation
- [[block](pages/block.md)], [[beehive](pages/beehive.md)] - examples
- [[game-of-life](pages/game-of-life.md)] - the rule

[^1]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.2 - "Most starting patterns either reach stable figures--Conway calls them 'still lifes'--that cannot change or patterns that oscillate forever"
[^2]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.10-11 [synthesis] - still life defined as a finite configuration c with G(c) = c
[^3]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.4 - "Pattern d becomes a stable 'block' (two-by-two square) on the second move"
[^4]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.4 - "Tetrominoes b and c reach a stable figure, called a 'beehive,' on the second move. Beehives are frequently produced patterns"
[^5]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] pp.5-6 [synthesis] - "a honey farm (four beehives)"; "The stable honey farm ... results after 14 moves from a horizontal row of seven counters"
[^6]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.4 - "The illustration above shows the 12 commonest forms of still life"
[^7]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.637 [synthesis] - "square" of four and "hexagon" of six live sites among the stable structures
