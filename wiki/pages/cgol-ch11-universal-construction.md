---
title: "Universal Construction (Johnston and Greene, Ch. 11)"
category: Sources
summary: Chapter 11 of Conway's Game of Life - Mathematics and Construction - glider-driven universal constructors that build copies of themselves - the Gemini and Geminoids (any rational slope), single-channel glider synthesis with 90-degree and zero-degree elbows, the Snarkmaker, Snarkbreaker and Scorbie splitter, and Demonoids up to the Speed Demonoid, which reaches every rational diagonal speed below c/4
tags: [source, chapter, life, universal-constructor, construction-arm, single-channel, gemini, demonoid, self-constructing-spaceship]
sources: [cgol-ch11-universal-construction]
created: 2026-09-25
updated: 2026-09-25
---

# Universal Construction (Johnston and Greene, Ch. 11)

**Source:** raw/johnston-greene-2022-conways-game-of-life.pdf, Chapter 11, printed pp. 345-384 (PDF pp. 359-398). Part of [[conways-game-of-life-mathematics-and-construction](pages/conways-game-of-life-mathematics-and-construction.md)].
**Date ingested:** 2026-09-25
**Type:** book chapter

## Summary

In Life, *universal construction* means using gliders to build or move components while
also moving or rebuilding those gliders so they can be used again. A *universal
constructor* is a pattern that does this for any pattern that has a glider synthesis.[^1]
Most constructors only fire [[slow-salvo](pages/slow-salvo.md)]s, which is enough by the
slow-salvo universality theorem of Chapter 5. Most are also built from simple stable parts
such as blocks, beehives and eater 1s, so they are easy to synthesize and can build copies
of themselves.[^2] The chapter uses this to build spaceships: first ones with any rational
slope, then ones with any rational diagonal speed below c/4.[^3]

**Gemini and Geminoids (§11.1).** A block that gliders push, pull, or use to fire a
perpendicular glider acts as a *construction elbow*. Four such operations are enough to
emit any one-direction slow salvo, and Herschel circuitry turns them into a construction
arm driven by four input lanes.[^4] The Gemini (Andrew J. Wade, 2010) uses three of these
arms at each of two identical ends and bounces its recipe between the ends as glider
streams. Geminoids, its modified forms, reach any rational slope and any speed below a
fixed limit ([[self-constructing-spaceship](pages/self-constructing-spaceship.md)]).[^5]

**Single-channel synthesis (§§11.2-11.4).** A slow salvo encodes a construction in the
*positions* of its gliders. Single-channel synthesis encodes it in their *timing* instead,
with every glider on one lane from one direction. A block hit by such a stream acts as a
90-degree or zero-degree elbow ([[single-channel-construction](pages/single-channel-construction.md)]).[^6]
Single-channel recipes also build the tools for bending and copying a recipe on its own
lane:[^7]
- the *Snarkmaker*, which builds a Snark reflector in the recipe's path;
- the *Snarkbreaker*, which removes it again;
- the *Scorbie splitter*, a stable glider duplicator the recipe can build in its path.

**Demonoids (§§11.5-11.7).** A Demonoid bounces one single-channel recipe between two
mirror-image ends, each a Scorbie splitter plus a Snark. It is about ten times smaller
than the Gemini.[^8] The slow Demonoid moves at c/16384. Carrying the elbow on a
[[cordership](pages/cordership.md)] gives a c/256 version. Carrying it on a c/4 crab
wickstretcher and destroying old circuitry with pre-placed still lifes gives the Speed
Demonoid, which can be tuned to any rational speed below c/4.[^9]

**Notes (§11.8).** Paul Chapman and Dave Greene built the first universal constructor in
2004. It read its instructions from a tape of still lifes. The Gemini showed that a
recipe can simply be stored as moving gliders at the right spacing, and self-constructing
patterns followed quickly.[^10] Single-channel synthesis with widely spaced gliders mostly
came in 2017 from Simon Ekström.[^11]

## Key Takeaways

- Life has universal constructors built from easily synthesized parts, so they can build
  copies of themselves.[^2]
- One lane of gliders, varying only in timing, can build anything that gliders can build
  (Theorem 11.2).[^6]
- Self-constructing spaceships exist with every rational slope (Geminoids) and every
  rational diagonal speed below c/4 (Speed Demonoids).[^5][^9]
- Storing a recipe as a moving glider stream, rather than as a still-life tape, made these
  constructions practical.[^10]

## Entities & Concepts

- [[single-channel-construction](pages/single-channel-construction.md)], [[self-constructing-spaceship](pages/self-constructing-spaceship.md)]
- [[universal-constructor](pages/universal-constructor.md)], [[construction-arm](pages/construction-arm.md)], [[slow-salvo](pages/slow-salvo.md)], [[object-synthesis](pages/object-synthesis.md)]
- [[cordership](pages/cordership.md)], [[reflector](pages/reflector.md)], [[herschel](pages/herschel.md)], [[block](pages/block.md)], [[breeder](pages/breeder.md)]

## Relation to Other Wiki Pages

The chapter is Life's working answer to von Neumann's
[[universal-constructor](pages/universal-constructor.md)]: a machine that builds any
constructible pattern from a coded recipe and builds itself from its own (own reasoning).
It rests on the slow-salvo theorems of
[[cgol-ch5-glider-synthesis](pages/cgol-ch5-glider-synthesis.md)], and the same
single-channel toolkit drives the [[metacell](pages/metacell.md)] of
[[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)].[^2][^12]

[^1]: [[cgol-ch11-universal-construction](pages/cgol-ch11-universal-construction.md)] p.345 - "we can use gliders to create or move some component in the Life plane, while simultaneously moving or recreating those gliders so that they can be reused. We refer to these techniques as universal construction ... with “universal” referring to the fact that they can build any Life pattern that is synthesizable via gliders"
[^2]: [[cgol-ch11-universal-construction](pages/cgol-ch11-universal-construction.md)] p.345 - "Although most universal constructors only fire slow glider salvos, we know from Theorem 5.1 that this is enough to implement arbitrary glider syntheses. Most useful universal constructors are built out of simple stable components like blocks, beehives, and eater 1s ... and thus they can even be used to build copies of themselves"
[^3]: [[cgol-ch11-universal-construction](pages/cgol-ch11-universal-construction.md)] p.345 [synthesis] - spaceships "with any rational slope (but not necessarily any rational speed)", then "any rational speed (but fixed at a diagonal slope of 1)"; n.2 "any rational speed below c/4"
[^4]: [[cgol-ch11-universal-construction](pages/cgol-ch11-universal-construction.md)] pp.346-347 [synthesis] - PULL, PUSH, FIRE WHITE and FIRE BLACK "are enough for us to be able to implement any unidirectional slow salvo"; "By using a sliding block ... as a construction elbow, we can fire gliders at any location in the Life plane"; Fig. 11.2 construction arm built with Herschel circuitry, "Constructed by Paul Chapman and Dave Greene in 2004"
[^5]: [[cgol-ch11-universal-construction](pages/cgol-ch11-universal-construction.md)] pp.347-352 [synthesis] - two construction arms plus a destruction arm at each end; recipes "bounce back and forth between two copies of the entire three-arm circuit"; n.6 "Constructed by Andrew J. Wade in May 2010"; Geminoids of any rational slope and Theorem 11.1 (Geminoid Speed Limit)
[^6]: [[cgol-ch11-universal-construction](pages/cgol-ch11-universal-construction.md)] pp.353-359 [synthesis] - "We now flip this idea around and instead show how to encode the construction of a pattern in the timing of a sequence of gliders, with their position playing no role"; Theorem 11.2 "Every pattern that can be constructed via glider synthesis can be constructed by a single-channel glider synthesis with a 90-degree elbow"; zero-degree elbow on p.359
[^7]: [[cgol-ch11-universal-construction](pages/cgol-ch11-universal-construction.md)] pp.363-367 [synthesis] - "The recipes that create and destroy this in-lane Snark are appropriately called the Snarkmaker and Snarkbreaker"; 2 427-glider Snarkmaker; 20-glider Snarkbreaker; Scorbie splitter built by a 4 006-glider recipe
[^8]: [[cgol-ch11-universal-construction](pages/cgol-ch11-universal-construction.md)] p.367 - "this Demonoid works by bouncing a single-channel recipe back and forth between two mirror-image ends ... the ends consist just of a Scorbie splitter ... and a Snark"; "smaller than the Gemini by roughly one order of magnitude"
[^9]: [[cgol-ch11-universal-construction](pages/cgol-ch11-universal-construction.md)] pp.368-377 [synthesis] - c/16384 slow Demonoid (Fig. 11.16); Cordership-carried elbow gives c/256 (p.371); c/4 crab wickstretcher and still-life-seeded destruction; "Speed Demonoids can be adjusted to have any rational speed that is slower than c/4" (p.377)
[^10]: [[cgol-ch11-universal-construction](pages/cgol-ch11-universal-construction.md)] pp.378-379 [synthesis] - "Paul Chapman and Dave Greene built the first universal constructor in 2004"; commands "stored in unary as boats"; "if you want to build some kind of memory storage system for a bunch of spacings between gliders, you just store a bunch of moving gliders at the spacing you want"; "a flood of other self-constructing spaceships and bizarre patterns"
[^11]: [[cgol-ch11-universal-construction](pages/cgol-ch11-universal-construction.md)] p.381 - "The development of single-channel glider synthesis mostly took place in 2017 ... Simon Ekström"; "Ekström was the first to show that it is possible even when the gliders are far enough apart from each other that they can be fed through standard components like Snarks and syringes"
[^12]: [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] §§12.3-12.8, pp.393-421 [synthesis] - the metacell builds its neighbours by single-channel construction
