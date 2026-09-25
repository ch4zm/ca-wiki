---
title: Block
category: Patterns
summary: The 2 × 2 square still life, the smallest stable Life pattern and one of the commonest end products of small patterns and glider collisions
tags: [pattern, life, still-life, block]
sources: [fantastic-combinations-of-john-conways-life, statistical-mechanics-of-cellular-automata]
created: 2026-09-25
updated: 2026-09-25
---

# Block

## Description

The block is a two-by-two square of live cells, a [[still-life](pages/still-life.md)].
It is one of the five three-counter patterns that survive the first move: the bent
triplet becomes a block on the second move. The square tetromino is already a block.[^1]
Wolfram's survey calls it the "square" of four live cells.[^2]

Blocks turn up throughout Gardner's fate tables:[^3]
- a row of 8 counters ends as four blinkers and four blocks;
- rows of 17 and 20 counters end as four blocks and two blocks;
- a row of three 5-cell segments ends as four blocks;
- in the five-segment row, eight [[glider](pages/glider.md)]s crash in pairs to become
  eight blocks.

## Appearances in Sources

- [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] - name, origin from triplets and tetrominoes, row fates
- [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] - Sec. V: the "square"

## Related Concepts

- [[still-life](pages/still-life.md)] - its class
- [[beehive](pages/beehive.md)] - the other common small still life
- [[game-of-life](pages/game-of-life.md)] - the rule

[^1]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] pp.3-4 [synthesis] - five triplets survive the first move; "Pattern d becomes a stable 'block' (two-by-two square) on the second move"; "The square [a] is, as we have seen, a still-life figure"
[^2]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.637 [synthesis] - the "square" of four live sites among the stable structures
[^3]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.6 [synthesis] - "eight end with four blinkers and four blocks"; "17 end with four blocks"; "20 generate two blocks"; "5-5-5 ends with four blocks"; "the gliders crash in pairs to become eight blocks"
