---
title: Spaceship
category: Patterns
summary: A finite Life pattern that reappears in its original form shifted across the board; speeds are measured against Conway's "speed of light" c (one cell per generation), with proved limits of c/4 diagonally and c/2 orthogonally; the glider is the "featherweight"
tags: [pattern-class, life, spaceship, speed-of-light, moving]
sources: [fantastic-combinations-of-john-conways-life, theory-of-cellular-automata-a-survey]
created: 2026-09-25
updated: 2026-09-25
---

# Spaceship

## Description

A spaceship is a figure that travels across the board by reproducing itself in a new
position. The name is Conway's, and the [[glider](pages/glider.md)] is the
"featherweight spaceship".[^1] Formally, a finite configuration c such that Gᵏ(c) is a
translate of c.[^2]

**Speed of light.** Conway calls the speed of a chess king, one cell per generation in
any direction, the "speed of light", written *c*. It is the highest speed at which any
movement can occur on the board.[^3]

**Speed limits.** Conway proved that no figure can move diagonally faster than c/4, and
no finite figure can move horizontally or vertically into empty space faster than
c/2.[^4] Speed is the number of cells a figure shifts per move, counted over the moves it
takes to reappear in the same orientation. The glider shifts one cell diagonally in four
moves, so it travels at c/4. A figure that shifts two cells orthogonally in four moves
travels at c/2.[^5]

**1970 state of knowledge.** Conway knew of four spaceships, including the glider. He had
Gardner keep the three heavier ones secret as a challenge. Gardner asked readers for
figures moving in any direction at any speed, "however slow", noting they are extremely
hard to find.[^6]

## Appearances in Sources

- [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] - the term, speed of light, the c/4 and c/2 limits, the four known spaceships
- [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] - §2.6: the translate-of-itself definition (Kari calls every such object a "glider")

## Related Concepts

- [[glider](pages/glider.md)] - the smallest spaceship
- [[oscillator](pages/oscillator.md)] - a spaceship is periodic up to translation
- [[game-of-life](pages/game-of-life.md)] - the rule

[^1]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.5 - "Figures that move in this way are extremely hard to find. Conway knows of only four, including the glider, which he calls 'spaceships' (the glider is a 'featherweight spaceship'; the others have more counters)"
[^2]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.10-11 [synthesis] - a glider in Kari's general sense is a finite c with Gᵏ(c) equal to a translate of c
[^3]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] pp.4-5 [synthesis] - "The speed a chess king moves in any direction is called by Conway ... the 'speed of light'"; "the highest speed at which any kind of movement can occur on the board"
[^4]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.5 - "Conway has proved that the maximum speed diagonally is a fourth the speed of light"; "Movement of a finite figure horizontally or vertically into empty space, Conway has also shown, cannot exceed half the speed of light"
[^5]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.5 [synthesis] - the glider "replicates itself in the same orientation after four moves, and has traveled one cell diagonally"; "If a figure replicates in four moves in the same orientation after traveling two unit squares horizontally or vertically, its speed will be half that of light"
[^6]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.5 - "He has asked me to keep the three heavier spaceships secret as a challenge to readers"; "any figures that crawl across the board in any direction at any speed, however slow"
