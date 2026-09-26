---
title: Glider
category: Patterns
summary: The five-cell Life spaceship that shifts one cell diagonally every four generations (speed c/4), named for its glide reflection; the commonest moving object in random soup, emitted by guns, and the signal of glider-stream circuits
tags: [pattern, life, glider, spaceship, signal]
sources: [cgol-ch1-early-life, fantastic-combinations-of-john-conways-life, statistical-mechanics-of-cellular-automata, computation-at-the-edge-of-chaos, theory-of-cellular-automata-a-survey]
created: 2026-09-25
updated: 2026-09-25
---

# Glider

## Description

The glider is a five-cell [[spaceship](pages/spaceship.md)]. After two generations it has
shifted slightly and been reflected in a diagonal line, a "glide reflection" in geometry,
which gives it its name. After two more it is back in its original orientation, one cell
diagonally from where it started.[^1] It therefore moves at c/4, the fastest possible
diagonal speed.[^2]

**In soup.** The glider is one of the objects that most often appear in the ash of random
soups, and one of only four spaceships ever seen arising naturally
([[soup-search](pages/soup-search.md)]).[^3] The first glider ever observed came out of
the [[r-pentomino](pages/r-pentomino.md)] in generation 69, noticed by Richard K. Guy in
1970.[^4]

**Guns.** A glider gun creates an endless stream of gliders. The first found was the
period-30 [[gosper-glider-gun](pages/gosper-glider-gun.md)]; the
[[twin-bees](pages/twin-bees.md)] gun has period 46.[^5] The glider-producing
[[switch-engine](pages/switch-engine.md)] leaves a glider every 384 generations.[^6]

**Collisions.** Gliders crashing in pairs can leave blocks: in one of Gardner's row
experiments, eight gliders collide in pairs to become eight [[block](pages/block.md)]s.[^7]

**As a signal.** Glider streams from guns serve as wires in Life circuits, with the
presence or absence of a glider as one bit. That is how
[[game-of-life](pages/game-of-life.md)] is shown to be computationally universal.[^8]
Langton reads gliders (signals) and [[blinker](pages/blinker.md)]s (storage) in that
construction as the moving and static structures typical of the
[[edge-of-chaos](pages/edge-of-chaos.md)].[^9]

## Appearances in Sources

- [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] - in soup, first observation, guns
- [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] - glide reflection, c/4
- [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] - Sec. V: glider-stream wires
- [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] - gliders as signals
- [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] - §2.6: period-four glider

## Related Concepts

- [[spaceship](pages/spaceship.md)] - the class
- [[light-middle-heavyweight-spaceships](pages/light-middle-heavyweight-spaceships.md)] - the orthogonal natural spaceships
- [[gosper-glider-gun](pages/gosper-glider-gun.md)] - the first glider gun
- [[r-pentomino](pages/r-pentomino.md)] - source of the first glider seen

[^1]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.5 - "After two moves it has shifted slightly and been reflected in a diagonal line. Geometers call this a 'glide reflection'; hence the figure's name. After two more moves the glider has righted itself and moved one cell diagonally down and to the right from its initial position"
[^2]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.5 [synthesis] - "the maximum speed diagonally is a fourth the speed of light"; the glider "glides across the field at a fourth the speed of light"
[^3]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.7,28 [synthesis] - Fig. 1.6: the glider among objects that "frequently appear in the ash"; "the only spaceships that turned up were the four that we have already seen (the glider, LWSS, MWSS, and HWSS)"
[^4]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.17 - the R-pentomino produces "the very first glider that was ever observed in Life in generation 69"; n.20 "First noticed by Richard K. Guy in 1970"
[^5]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.11,13 [synthesis] - "Patterns that create glider streams are called glider guns"; the Gosper glider gun oscillates at period 30; the twin bees gun is "a period 46 glider gun"
[^6]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.14 - the glider-producing switch engine leaves "a glider every 384 generations"
[^7]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.6 - "5-5-5-5-5 terminates with a 'spectacular display of eight gliders and eight blinkers. Then the gliders crash in pairs to become eight blocks.'"
[^8]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.639 [synthesis] - glider streams from glider guns used as wires, bits as presence or absence of gliders; "The Life-game cellular automaton is thus computationally universal"
[^9]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] pp.25-26 [synthesis] - the universality proof "employs propagating 'gliders' as signals and the period-2 'blinkers' as storage elements"
