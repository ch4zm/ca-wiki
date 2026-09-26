---
title: Spaceship
category: Patterns
summary: A finite Life pattern that moves through the plane on its own, reappearing shifted; speeds are measured against the "speed of light" c (one cell per generation), limited to c/4 diagonally and c/2 orthogonally; the glider, LWSS, MWSS and HWSS are the natural ones
tags: [pattern-class, life, spaceship, speed-of-light, moving]
sources: [cgol-ch1-early-life, fantastic-combinations-of-john-conways-life, theory-of-cellular-automata-a-survey]
created: 2026-09-25
updated: 2026-09-25
---

# Spaceship

## Description

A spaceship is an object that moves through the Life plane on its own.[^1] Formally, a
finite configuration c such that Gᵏ(c) is a translate of c.[^2]

**Speed of light.** The speed of a chess king, one cell per generation in any direction,
is called the "speed of light", written *c*. It is the highest speed at which any
movement can occur on the board.[^3]

**Speed limits.** No figure can move diagonally faster than c/4, and no finite figure can
move horizontally or vertically into empty space faster than c/2 (both proved by
Conway).[^4] Speed is the number of cells a figure shifts per move, counted over the moves
it takes to reappear in the same orientation.[^5]

**Natural spaceships.** Four spaceships arise from random soup, and they are the only
ones ever seen there ([[soup-search](pages/soup-search.md)]):[^6]
- the [[glider](pages/glider.md)], diagonal at c/4;
- the lightweight, middleweight and heavyweight spaceships (LWSS, MWSS, HWSS),
  orthogonal at c/2 ([[light-middle-heavyweight-spaceships](pages/light-middle-heavyweight-spaceships.md)]).

**Near-spaceships.** Some unstable objects move like spaceships but are destroyed by
their own debris unless it is cleaned up: the pi-heptomino moves 9 cells in 30
generations and the B-heptomino 5 cells in 10.[^7] The [[switch-engine](pages/switch-engine.md)]
keeps moving; stabilized by its debris it becomes a *puffer*, which moves while leaving
junk behind.[^8]

## Appearances in Sources

- [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] - definition, the four natural spaceships, near-spaceships
- [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] - speed of light, the c/4 and c/2 limits
- [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] - §2.6: the translate-of-itself definition (Kari calls every such object a "glider")

## Related Concepts

- [[glider](pages/glider.md)] - the smallest spaceship
- [[light-middle-heavyweight-spaceships](pages/light-middle-heavyweight-spaceships.md)] - the orthogonal natural spaceships
- [[oscillator](pages/oscillator.md)] - a spaceship is periodic up to translation
- [[switch-engine](pages/switch-engine.md)] - a moving unstable object and its puffers

[^1]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.6 - "An object that moves through the plane on its own is called a spaceship, and this particular one is called the glider"
[^2]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.10-11 [synthesis] - a glider in Kari's general sense is a finite c with Gᵏ(c) equal to a translate of c
[^3]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] pp.4-5 [synthesis] - "The speed a chess king moves in any direction is called by Conway ... the 'speed of light'"; "the highest speed at which any kind of movement can occur on the board"
[^4]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.5 - "Conway has proved that the maximum speed diagonally is a fourth the speed of light"; "Movement of a finite figure horizontally or vertically into empty space, Conway has also shown, cannot exceed half the speed of light"
[^5]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.5 [synthesis] - the glider "replicates itself in the same orientation after four moves, and has traveled one cell diagonally"; "If a figure replicates in four moves in the same orientation after traveling two unit squares horizontally or vertically, its speed will be half that of light"
[^6]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.7-8,28 [synthesis] - glider, LWSS, MWSS, HWSS; LWSS "moves orthogonally ... unlike the glider, which moves diagonally"; "the only spaceships that turned up were the four that we have already seen (the glider, LWSS, MWSS, and HWSS)"
[^7]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.10-12 [synthesis] - pi-heptomino "moves forward by 9 cells after 30 generations, while leaving behind some messy debris"; B-heptomino "after 10 generations it evolves into a copy of itself 5 cells forward"
[^8]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.13-14 [synthesis] - the switch engine "continually moves farther and farther away from where it started, just like a spaceship"; "An object like this one, which moves but leaves periodic junk behind it, is called a puffer"
