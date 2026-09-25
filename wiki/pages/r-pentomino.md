---
title: R-pentomino
category: Patterns
summary: The one five-cell pattern among the 12 pentominoes that does not settle quickly in Life; Conway tracked it for 460 generations in 1970 without learning its fate, watching it throw off gliders - the first famous methuselah
tags: [pattern, life, r-pentomino, methuselah, polyomino]
sources: [fantastic-combinations-of-john-conways-life]
created: 2026-09-25
updated: 2026-09-25
---

# R-pentomino

## Description

Of the 12 pentominoes (five rookwise-connected cells), six vanish before the fifth move,
two quickly become a stable seven-cell pattern, and three become traffic lights. The
R-pentomino is the only one that does not end quickly by vanishing, stabilizing or
oscillating.[^1]

**Conway's 1970 track.** Conway followed it for 460 moves and its fate was still
unknown. By then it had thrown off several [[glider](pages/glider.md)]s and left "a lot
of miscellaneous junk stagnating around" with only a few small active regions. After 48
moves it has a seven-counter figure on the left and two symmetric regions on the right
that, left alone, would grow into a honey farm ([[beehive](pages/beehive.md)]s) and
traffic lights ([[blinker](pages/blinker.md)]s); instead the rest of the population eats
into both.[^2] Long runs like this were done on a PDP-7 display program by M. J. T. Guy
and S. R. Bourne.[^3]

The wiki's copy of the column omits the figure, so the shape is not described here.

## Appearances in Sources

- [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] - pentomino survey, the 460-move track

## Related Concepts

- [[glider](pages/glider.md)] - it emits them
- [[game-of-life](pages/game-of-life.md)] - the rule

[^1]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] pp.4-5 [synthesis] - "six vanish before the fifth move, two quickly reach a stable pattern of seven counters and three in a short time become traffic lights. The only pentomino that does not end quickly (by vanishing, becoming stable or oscillating) is the R pentomino"
[^2]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.5 [synthesis] - "Its fate is not yet known. Conway has tracked it for 460 moves. By then it has thrown off a number of gliders"; Conway's remark on "miscellaneous junk" and the 48-move state that "would grow into a honey farm (four beehives) and traffic lights. However, the honey farm gets eaten into pretty quickly and the four blinkers forming the traffic lights disappear one by one"
[^3]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.5 - "For long-lived populations such as this one Conway sometimes uses a PDP-7 computer with a screen on which he can observe the changes. The program was written by M. J. T. Guy and S. R. Bourne"
