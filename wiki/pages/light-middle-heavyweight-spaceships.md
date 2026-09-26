---
title: Lightweight, middleweight and heavyweight spaceships
category: Patterns
summary: The LWSS, MWSS and HWSS - three period-4 Life spaceships that move orthogonally 2 cells every 4 generations (c/2); with the glider they are the only spaceships that arise naturally from random soup
tags: [pattern, life, spaceship, lwss, mwss, hwss, orthogonal, c-over-2]
sources: [cgol-ch1-early-life, fantastic-combinations-of-john-conways-life]
created: 2026-09-25
updated: 2026-09-25
---

# Lightweight, middleweight and heavyweight spaceships

## Description

The **lightweight spaceship** (LWSS), **middleweight spaceship** (MWSS) and
**heavyweight spaceship** (HWSS) are [[spaceship](pages/spaceship.md)]s that move
orthogonally, directly north, south, east or west, unlike the diagonal
[[glider](pages/glider.md)]. All three have period 4 and move 2 cells every 4
generations.[^1] That is c/2, the fastest possible orthogonal speed for a finite
pattern moving into empty space.[^2]

The LWSS is common in random soup; the MWSS and HWSS are rarer.[^3] These three and the
glider are the only spaceships that have turned up in large-scale random soup
searches.[^4] Following the naming, the glider was once called the "featherweight
spaceship".[^5]

## Appearances in Sources

- [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] - period, speed and frequency in soup
- [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] - the c/2 orthogonal limit

## Related Concepts

- [[spaceship](pages/spaceship.md)] - the class
- [[glider](pages/glider.md)] - the diagonal counterpart
- [[soup-search](pages/soup-search.md)] - where their natural frequency is measured

[^1]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.7-8 [synthesis] - "the lightweight spaceship (or LWSS for short) ... moves orthogonally (i.e., directly north, south, east, or west), unlike the glider, which moves diagonally"; Fig. 1.10: "a lightweight, middleweight, and heavyweight spaceship. They all have period 4 and travel to the right 2 cells every 4 generations"
[^2]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.5 - "Movement of a finite figure horizontally or vertically into empty space, Conway has also shown, cannot exceed half the speed of light"
[^3]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.7 - "commonly occurring objects, such as the lightweight spaceship"; "Slightly more rare than the lightweight spaceship are the middleweight spaceship (or MWSS) and the heavyweight spaceship (or HWSS)"
[^4]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.28 - Okrasinski's screensaver catalogued over 4.7 × 10^11 ash objects, "but still the only spaceships that turned up were the four that we have already seen (the glider, LWSS, MWSS, and HWSS)"
[^5]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.7, n.4 - "the glider was sometimes called the featherweight spaceship in the early days of Life, though this name is very rarely used now"
