---
title: Slow salvo
category: Concepts
summary: A stream of gliders all from one direction that hit a seed object one at a time; with block moves, one-time turners, blockic splitters, timing adjusters and the clock inserter, a p1 slow salvo can build anything that any glider synthesis can
tags: [concept, life, slow-salvo, glider-synthesis, seed, one-time-turner, clock-inserter, universality]
sources: [cgol-ch5-glider-synthesis]
created: 2026-09-25
updated: 2026-09-25
---

# Slow salvo

## Description

A *slow salvo* is a group of [[glider](pages/glider.md)]s that is *slow*, with only one
glider interacting at a time, and a *salvo*, with every glider coming from the same
direction. The gliders hit a starting object, the *seed*, usually a
[[block](pages/block.md)]. In a *p1* slow salvo every intermediate object is a still life;
in a *p2* slow salvo, still lifes and period-2 oscillators.[^1] Despite the restrictions,
slow salvos can build exactly what unrestricted [[object-synthesis](pages/object-synthesis.md)]
can, though they may need many more gliders.[^2]

**Building blocks of the proof.**
- **Block moves.** Two gliders turn one block into two. The (2,1) block pull (one glider)
  and a 6-glider move together shift a block one cell in any direction. Many faster p2
  moves exist, such as the (2,1) block push and (11, 0) pulls and pushes.[^3]
- **One-time turners.** Two blocks can turn a glider 90 degrees and are destroyed doing
  it. Twelve slow gliders build such a turner and leave a spare block. So one-direction
  salvos can emulate syntheses whose gliders come from several directions.[^4]
- **Splitters and timing.** A *blockic splitter*, made only of blocks, turns one glider
  into several; one of three blocks gives four gliders.[^5]
  - 180-degree one-time turners built from two 90-degree ones can keep or change a
    glider's colour and delay it by 0 to 7 generations.
  - Moving a turner one cell adds 8 generations, so any timing is reachable.
- **Seeds.** A configuration of still lifes that builds an object when hit by a glider is
  a *seed*. A 31-block seed for the clock exists, but turning seeds into actual salvos
  takes hundreds of gliders and is done by scripts such as slsparse.[^6]
- **Clock inserter** (Martin Grant, 2014). Two opposing gliders turn a clock into a
  perpendicular glider, cleanly and in the space the gliders just left. That places a new
  glider right next to existing ones, so tightly packed glider groups can be built back to
  front.[^7]

**Theorems.**[^8]
- **5.1:** every pattern constructible by glider synthesis can be built by a p2 slow
  salvo. Rewind the synthesis into four one-direction salvos, then build them one glider
  at a time, with turners for spread-out gliders and clock insertion for tight ones.
- **5.2:** p1 suffices. Replace each clock with the blockic clock seed, triggered by a
  splitter that also supplies the two inserting gliders.

## Appearances in Sources

- [[cgol-ch5-glider-synthesis](pages/cgol-ch5-glider-synthesis.md)] - §5.7: block moves, one-time turners, splitters, timing, the clock inserter, Theorems 5.1-5.2

## Related Concepts

- [[single-channel-construction](pages/single-channel-construction.md)] - encodes the same constructions in glider timing on one lane
- [[object-synthesis](pages/object-synthesis.md)] - what slow salvos emulate
- [[block](pages/block.md)] - the usual seed
- [[reflector](pages/reflector.md)] - a permanent turner, unlike a one-time turner
- [[catagolue](pages/catagolue.md)] - a pseudo-symmetry there records what slow salvos build

[^1]: [[cgol-ch5-glider-synthesis](pages/cgol-ch5-glider-synthesis.md)] p.136 [synthesis] - slow salvos "are slow: only one glider interacts in the synthesis at a time, and ... form a salvo: all of the gliders come from the same direction"; "another object (called a seed) for it to crash into ... it is typical to use a block"; p1 and p2 slow salvos
[^2]: [[cgol-ch5-glider-synthesis](pages/cgol-ch5-glider-synthesis.md)] p.136 - "if we can synthesize an object with gliders at all then we can synthesize it with a p2 slow salvo"; n.10 "the slow salvo might contain considerably more gliders"
[^3]: [[cgol-ch5-glider-synthesis](pages/cgol-ch5-glider-synthesis.md)] pp.136-138 [synthesis] - Fig. 5.20 "A 2-glider slow salvo can turn one block into two blocks"; Fig. 5.21 (2,1) block pull and a 6-glider move; moving a block one cell in any direction; Fig. 5.22 p2 salvos: (2,1) block push, (1,−1) move, (11,0) pull and push; "hundreds of salvos of this type known"
[^4]: [[cgol-ch5-glider-synthesis](pages/cgol-ch5-glider-synthesis.md)] pp.138-139 [synthesis] - Fig. 5.23 two-block one-time turner "rotates a glider by 90 degrees and destroys the blocks"; Fig. 5.24 12-glider p1 slow salvo building it with a spare block; "we are now able to emulate multi-directional glider syntheses via unidirectional syntheses"
[^5]: [[cgol-ch5-glider-synthesis](pages/cgol-ch5-glider-synthesis.md)] pp.140-142 [synthesis] - "blockic splitters"; Fig. 5.26 three blocks turn one glider into four; Table 5.5 180-degree turners, color-preserving or color-changing, delays 0-7; moving a turner one cell delays the glider 8 generations
[^6]: [[cgol-ch5-glider-synthesis](pages/cgol-ch5-glider-synthesis.md)] p.143 [synthesis] - "A configuration of simple still lifes ... that synthesizes a particular object when hit by a glider ... is called a seed"; the 31-block clock seed "requires hundreds of slow gliders to construct"; slsparse "being the most widely used"
[^7]: [[cgol-ch5-glider-synthesis](pages/cgol-ch5-glider-synthesis.md)] pp.143-144 [synthesis] - Fig. 5.28 "the clock inserter ... uses two opposing gliders to transform a clock into a perpendicular glider"; n.15 Martin Grant, December 2014; output glider "moves through the space just vacated"; "we can use this reaction to build any arrangement of gliders, no matter how tight"
[^8]: [[cgol-ch5-glider-synthesis](pages/cgol-ch5-glider-synthesis.md)] pp.144-145 [synthesis] - Theorem 5.1 (Universality of p2 Slow Salvo Synthesis) with proof via four rewound salvos, turners and clock insertion; Theorem 5.2 (Universality of p1 Slow Salvo Synthesis) via the blockic clock seed and splitters
