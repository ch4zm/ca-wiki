---
title: "The Fantastic Combinations of John Conway's New Solitaire Game \"Life\" (Gardner, 1970)"
category: Sources
summary: Martin Gardner's October 1970 Scientific American column that introduced Conway's Game of Life - the birth/survival/death rules, how to run it by hand, the first named patterns (block, beehive, blinker, glider, R-pentomino, pulsar, pentadecathlon), the speed of light, and Conway's $50 unbounded-growth challenge
tags: [source, gardner, conway, life, patterns, still-life, oscillator, spaceship, glider]
sources: [fantastic-combinations-of-john-conways-life]
created: 2026-09-25
updated: 2026-09-25
---

# The Fantastic Combinations of John Conway's New Solitaire Game "Life" (Gardner, 1970)

**Source:** raw/gardner-1970-life.pdf. Gardner, M. (1970). Mathematical games: The fantastic combinations of John Conway's new solitaire game "life." *Scientific American, 223*(4), 120-123. The file is a 6-page printout of a web transcription (Uni Potsdam); the magazine's figures are not reproduced and page locators below are PDF pages.
**Date ingested:** 2026-09-25
**Type:** article (magazine column)

## Summary

Gardner presents Life as a solitaire "simulation game" played with counters on a large
board, an infinite plane in principle, where each cell has eight neighbours.[^1] Conway
tuned the rules through long experiment so that no pattern should be simply provable to
grow without limit, some patterns should appear to, and simple patterns should change for
a long time before dying out, freezing into a stable form, or entering a cycle. The goal
is a population whose behaviour is unpredictable.[^2] The rules: a counter with two or
three neighbours survives, one with four or more dies of overpopulation, one with zero or
one dies of isolation, and an empty cell with exactly three neighbours is a birth cell.
All births and deaths happen at once and make up one generation, or "move".[^3] Because
of that simultaneity, playing by hand needs two colours of counter so newborns can be told
apart from the previous generation while checking.[^4]

Most of the column is a catalogue of what small starting patterns become. Every single
counter and pair dies at once. Of the three-counter patterns, the ones that survive a move
end as nothing, a block, or a blinker.[^5] The tetrominoes end as the block, the beehive,
or the four-blinker "traffic lights".[^6] Among the pentominoes, only the
[[r-pentomino](pages/r-pentomino.md)] refuses to settle quickly; Conway had followed it
for 460 moves on a PDP-7 without learning its fate.[^7] Gardner names the stable forms
[[still-life](pages/still-life.md)] and the cycling ones flip-flops or oscillators, and
shows larger oscillators: Norton's period-8 "figure 8", the period-3
[[pulsar](pages/pulsar.md)], and the period-15
[[pentadecathlon](pages/pentadecathlon.md)].[^8]

The rest concerns motion and growth. The five-counter [[glider](pages/glider.md)] moves
one cell diagonally every four moves. Conway calls the king's move per generation "the
speed of light" and proved finite figures cannot exceed a quarter of it diagonally or half
of it orthogonally. He knew of four [[spaceship](pages/spaceship.md)]s, the glider being
the "featherweight", and kept the other three secret as a challenge.[^9] Conway
conjectured that no finite pattern grows without limit and offered $50 for a proof or
disproof before the end of the year; a "gun" emitting gliders or a "puffer train" leaving
smoke would disprove it.[^10]

## Key Takeaways

- Life's rule is stated in words as survival on 2 or 3 neighbours, birth on exactly 3,
  and death otherwise, applied to all cells simultaneously.[^3]
- Conway picked the rules for unpredictability: the boundary between dying out,
  stabilizing, oscillating, and possibly unbounded growth should be hard to call.[^2]
- The founding pattern vocabulary is here: still life, block, beehive, blinker, traffic
  lights, honey farm, glider, spaceship, R-pentomino, pulsar, pentadecathlon, gun, puffer
  train.[^5][^6][^8][^9][^10]
- "Speed of light" (one cell per generation) and the c/4 diagonal and c/2 orthogonal
  limits come from this column.[^9]
- From the start, Life was studied both by hand and by computer: Conway used a PDP-7
  program by M. J. T. Guy and S. R. Bourne for long-lived patterns.[^7]
- Systematic fate tables were already being built: all polyominoes up to size 5 (and
  hexominoes, most heptominoes), rows of n counters for n up to 20, and rows of five-cell
  blocks.[^11]

## Entities & Concepts

- [[game-of-life](pages/game-of-life.md)] - the rule itself
- [[still-life](pages/still-life.md)], [[oscillator](pages/oscillator.md)], [[spaceship](pages/spaceship.md)] - the three pattern classes
- [[block](pages/block.md)], [[beehive](pages/beehive.md)], [[blinker](pages/blinker.md)], [[glider](pages/glider.md)], [[r-pentomino](pages/r-pentomino.md)], [[pulsar](pages/pulsar.md)], [[pentadecathlon](pages/pentadecathlon.md)] - named patterns
- [[moore-neighbourhood](pages/moore-neighbourhood.md)] - the eight-neighbour cell

## Relation to Other Wiki Pages

This is the primary source for [[game-of-life](pages/game-of-life.md)] and its named
patterns. [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)],
[[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] and
[[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)]
cite Gardner for the rule and the standard structures; this column gives them first hand.

[^1]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] pp.1-2 [synthesis] - "a fantastic solitaire pastime he calls 'life'"; "a growing class of what are called 'simulation games'"; board "assumed to be an infinite plane"; "each cell of the checkerboard ... has eight neighboring cells, four adjacent orthogonally, four adjacent diagonally"
[^2]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] pp.1-2 [synthesis] - Conway's three desiderata: no initial pattern with a simple proof of unlimited growth; patterns that apparently grow without limit; simple patterns that change for a long time before fading, stabilizing, or oscillating; "In brief, the rules should be such as to make the behavior of the population unpredictable"
[^3]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.2 [synthesis] - Survivals with two or three neighbours; deaths with four or more (overpopulation) or one or none (isolation); "Each empty cell adjacent to exactly three neighbors--no more, no fewer--is a birth cell"; "all births and deaths occur simultaneously. Together they constitute a single generation or, as we shall call it, a 'move'"
[^4]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.2 [synthesis] - Conway's four-step procedure with black and white counters; "newborn counters play no role in causing other deaths and births. It is essential, therefore, to be able to distinguish them"
[^5]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] pp.3-4 [synthesis] - "A single organism or any pair of counters, wherever placed, will obviously vanish on the first move"; five triplets survive the first move: three vanish on the second, d becomes a block, e is the blinker
[^6]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.4 [synthesis] - the square tetromino is a still life; b and c become a beehive on the second move, d on the third; e "After nine moves ... becomes four isolated blinkers, a flip-flop called 'traffic lights'"
[^7]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] pp.4-5 [synthesis] - "The only pentomino that does not end quickly ... is the R pentomino"; "Its fate is not yet known. Conway has tracked it for 460 moves"; "Conway sometimes uses a PDP-7 computer ... The program was written by M. J. T. Guy and S. R. Bourne"
[^8]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] pp.2,4,6 [synthesis] - stable figures "Conway calls them 'still lifes'"; "flip-flops" (oscillating figures of period 2); "figure 8 ... found by Norton ... has a period of 8"; "pulsar CP 48-56-72 ... period 3"; "pentadecathlon, with a life cycle of period 15"
[^9]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] pp.4-5 [synthesis] - "The speed a chess king moves in any direction is called by Conway ... the 'speed of light'"; "Conway has proved that the maximum speed diagonally is a fourth the speed of light"; orthogonal movement "cannot exceed half the speed of light"; "Conway knows of only four, including the glider, which he calls 'spaceships' (the glider is a 'featherweight spaceship' ...)"; "He has asked me to keep the three heavier spaceships secret"
[^10]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.3 [synthesis] - "Conway conjectures that no pattern can grow without limit"; "$50 to the first person who can prove or disprove the conjecture before the end of the year"; a "gun" (repeatedly shoots out moving objects such as the glider) or a "puffer train" (moves but leaves behind a trail of "smoke")
[^11]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] pp.4-6 [synthesis] - pentomino exercise; "Conway also has tracked the life histories of all the hexominoes, and all but seven of the heptominoes"; "Conway has tracked the life histories of a row of n counters through n = 20"; rows of sets of five counters
