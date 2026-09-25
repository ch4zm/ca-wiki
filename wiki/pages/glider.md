---
title: Glider
category: Patterns
summary: The five-cell Life spaceship that shifts one cell diagonally every four generations (speed c/4), named for its glide reflection; the moving signal of glider-stream circuits
tags: [pattern, life, glider, spaceship, signal]
sources: [fantastic-combinations-of-john-conways-life, statistical-mechanics-of-cellular-automata, computation-at-the-edge-of-chaos, theory-of-cellular-automata-a-survey]
created: 2026-09-25
updated: 2026-09-25
---

# Glider

## Description

The glider is a five-counter figure discovered by Conway. After two moves it has shifted
slightly and been reflected in a diagonal line, a "glide reflection" in geometry, which
gives it its name. After two more it is back in its original orientation, one cell
diagonally from where it started.[^1] It therefore moves at a quarter of the speed of
light, the fastest possible diagonal speed, and is the smallest
[[spaceship](pages/spaceship.md)], the "featherweight".[^2]

**Where gliders come from.** The [[r-pentomino](pages/r-pentomino.md)] throws off gliders
as it evolves.[^3] A row of five 5-cell segments ends in "a spectacular display of eight
gliders and eight blinkers"; the gliders then crash in pairs into eight
[[block](pages/block.md)]s.[^4] A *gun*, a pattern that repeatedly shoots out gliders,
was in 1970 a hypothetical that would refute Conway's bounded-growth conjecture.[^5] By
the 1980s guns were known; the simplest then known evolves from 26 live cells.[^6]

**As a signal.** Streams of gliders from glider guns serve as wires in Life circuits,
with the presence or absence of a glider as one bit. That is how
[[game-of-life](pages/game-of-life.md)] is shown to be computationally universal.[^7]
Langton reads the gliders (signals) and [[blinker](pages/blinker.md)]s (storage) in
that proof as the moving and static structures typical of the
[[edge-of-chaos](pages/edge-of-chaos.md)].[^8]

## Appearances in Sources

- [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] - discovery, glide reflection, c/4, featherweight spaceship
- [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] - Sec. V: glider guns, glider-stream wires
- [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] - gliders as signals
- [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] - §2.6: period-four glider, period-30 gun

## Related Concepts

- [[spaceship](pages/spaceship.md)] - the pattern class
- [[r-pentomino](pages/r-pentomino.md)] - an early natural source of gliders
- [[game-of-life](pages/game-of-life.md)] - the rule

[^1]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.5 - "After two moves it has shifted slightly and been reflected in a diagonal line. Geometers call this a 'glide reflection'; hence the figure's name. After two more moves the glider has righted itself and moved one cell diagonally down and to the right from its initial position"
[^2]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.5 [synthesis] - "Conway has proved that the maximum speed diagonally is a fourth the speed of light"; the glider "glides across the field at a fourth the speed of light"; "the glider is a 'featherweight spaceship'"
[^3]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.5 - "By then it has thrown off a number of gliders"
[^4]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.6 - "5-5-5-5-5 terminates with a 'spectacular display of eight gliders and eight blinkers. Then the gliders crash in pairs to become eight blocks.'"
[^5]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.3 - "a 'gun' (a configuration that repeatedly shoots out moving objects such as the 'glider,' ...)"
[^6]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.637 [synthesis] - glider guns emit a stream of gliders; the simplest known gun evolves from 26 live cells
[^7]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.639 [synthesis] - glider streams from glider guns used as wires, bits as presence or absence of gliders; "The Life-game cellular automaton is thus computationally universal"
[^8]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] pp.25-26 [synthesis] - the universality proof "employs propagating 'gliders' as signals and the period-2 'blinkers' as storage elements"
