---
title: Single-channel construction
category: Concepts
summary: Glider synthesis driven by gliders that all travel on one lane in one direction, with the recipe stored only in the gaps between them; a block elbow turns the stream into slow gliders on any lane (90-degree or zero-degree elbow), so one lane can build anything gliders can build, including the Snarks and splitters that bend and copy the recipe itself
tags: [concept, life, single-channel, universal-constructor, construction-elbow, glider-synthesis, snarkmaker, scorbie-splitter]
sources: [cgol-ch11-universal-construction, cgol-ch12-0e0p-metacell]
created: 2026-09-25
updated: 2026-09-25
---

# Single-channel construction

## Description

In *single-channel glider synthesis* every [[glider](pages/glider.md)] comes from the same
direction on the same lane. The construction is encoded in the *timing* of the gliders,
and their positions play no role. This reverses a [[slow-salvo](pages/slow-salvo.md)],
which encodes a construction in glider positions and ignores timing.[^1] A recipe is
therefore just a list of gaps in generations between consecutive gliders. For example, 13
gliders with the gaps 109, 91, 94, 91, 91, 124, 91, 105, 90, 106, 112, 108 hit a
[[block](pages/block.md)], release one perpendicular glider, and rebuild the block 20
half-diagonals further along the lane.[^2] The first glider of every such recipe turns the
block into a pi-heptomino explosion, and the later gliders clean up the debris into the
wanted output.[^3]

**The elbow.** The block the stream hits is the *elbow*, and the object that the output
gliders hit is the *hand*.[^4] There are two kinds of elbow.
- **90-degree elbow.** The output glider travels perpendicular to the stream. Lanes are
  marked *i* (internal, on the elbow's side of the stream) or *x* (external).[^5]
  - Each firing recipe moves the elbow by an amount it dictates. If that amount is an odd
    number of half-diagonals, the elbow crosses to the other side of the stream and every
    later i and x label swaps.[^5]
  - Separate push and pull recipes move the elbow by 1 to 10 half-diagonals without firing,
    so the elbow can be walked to any lane before a firing recipe is sent.[^6]
- **Zero-degree elbow.** The output glider keeps the stream's direction but moves to
  another lane, so an object can be built directly in front of the stream.[^7] Searches
  found recipes for every output lane from -100 to +100, and the elbow's exact position
  matters much less than for a 90-degree elbow.[^8]

**Universality.** With a 90-degree elbow and a recipe that builds a hand block, a single
lane can fire slow gliders on any lanes at a target. By the slow-salvo theorem that makes
it universal. Theorem 11.2: every pattern constructible by glider synthesis can be built
by single-channel synthesis with a 90-degree elbow.[^9] A zero-degree elbow is universal
too, but in general only by an "excruciatingly slow" detour. In practice it builds
anything whose slow salvo is no wider than about 200 lanes.[^10]

**Cost and timing.**
- A single-channel recipe needs roughly 25 to 40 times as many gliders as the slow salvo
  it emulates. In return, the surrounding circuitry only has to handle one lane.[^11]
- Recipes are built with gaps of at least 90 generations so they can pass through Snark
  reflectors and syringe conduits. A gap of 91 marks a glider whose timing matters mod 2,
  because a period-2 object appears in the reaction.[^12]

**Tools that act on the recipe's own lane.** A recipe can build and remove the machinery
that bends or copies it.[^13]
- **Snarkmaker.** Builds a Snark (a stable [[reflector](pages/reflector.md)]) in the
  recipe's own path. It emulates a 95-glider slow salvo of a Snark (Adam P. Goucher, March
  2017) with zero-degree recipes and totals 2,427 gliders.
- **Snarkbreaker.** 20 gliders that destroy such a Snark and turn it back into an elbow
  block. One glider fired backward from the elbow meets a later recipe glider at the Snark.
- **Scorbie splitter.** A stable glider duplicator: the left half of a syringe followed by
  a [[herschel](pages/herschel.md)]-to-two-gliders conduit found by "praosylen" in January
  2016. It has repeat time 90 and is named after Dongook Lee ("Scorbie"). The script
  slsparse generated a 4,006-glider recipe that builds it.

## Uses

- Demonoids, self-constructing spaceships that bounce one recipe between two ends
  ([[self-constructing-spaceship](pages/self-constructing-spaceship.md)]).[^11]
- The 0E0P [[metacell](pages/metacell.md)], which builds its neighbours by single-channel
  construction.[^14]
- A spiral growth pattern whose recipe, mostly a Snarkmaker, circles a diamond-shaped
  track and extends it with new Snarks; and Remini (Michael Simkin, April 2019), a
  single-channel form of the Gemini built on period-30 circuitry, where every gap must be a
  multiple of 30.[^15]

**History.** How to emulate any glider synthesis with gliders on one lane was known in
2015. Simon Ekström showed in 2017 that it also works with gliders spaced far enough apart
for standard components. Most of the recipe searches are his, with optimizations by Dave
Greene.[^16]

**Relation to von Neumann's arm.** In von Neumann's rule a
[[construction-arm](pages/construction-arm.md)] is a path of cells that is extended to a
site and retracted. In Life nothing needs extending: the "arm" is a movable block elbow,
and the glider stream reaches it from any distance. The recipe plays the role of the
description tape of a [[universal-constructor](pages/universal-constructor.md)] (own
reasoning, from the sources on this page).

## Appearances in Sources

- [[cgol-ch11-universal-construction](pages/cgol-ch11-universal-construction.md)] - §§11.2-11.4: 90-degree and zero-degree elbows, Theorem 11.2, Snarkmaker, Snarkbreaker, Scorbie splitter
- [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] - the metacell's construction by single-channel recipes

## Related Concepts

- [[slow-salvo](pages/slow-salvo.md)] - what a single-channel recipe emulates
- [[object-synthesis](pages/object-synthesis.md)] - the class of buildable patterns
- [[construction-arm](pages/construction-arm.md)] - von Neumann's construct-and-retract arm
- [[universal-constructor](pages/universal-constructor.md)] - the concept this realizes in Life
- [[reverse-caber-tosser](pages/reverse-caber-tosser.md)] - another recipe-driven constructor, with the recipe held in one distance

[^1]: [[cgol-ch11-universal-construction](pages/cgol-ch11-universal-construction.md)] p.353 - "We now flip this idea around and instead show how to encode the construction of a pattern in the timing of a sequence of gliders, with their position playing no role. In particular, we show how to encode glider synthesis via gliders that are all coming from the same direction on the same lane"
[^2]: [[cgol-ch11-universal-construction](pages/cgol-ch11-universal-construction.md)] p.353 [synthesis] - Fig. 11.6: 13 gliders "(a) produce a single perpendicular glider, and (b) recreate the target block along the same lane (but shifted northwest by 20 half-diagonals)"; encoded by "12 timing gaps: 109, 91, 94, 91, 91, 124, 91, 105, 90, 106, 112, 108"
[^3]: [[cgol-ch11-universal-construction](pages/cgol-ch11-universal-construction.md)] pp.353-354 [synthesis] - "first create a chaotic explosion (by turning the block into a pi-heptomino), and then clean up the resulting debris while creating a perpendicular glider"; boats, beehives and ponds "explode into a pi-heptomino when they are hit by a glider in the exact same way that a block does"
[^4]: [[cgol-ch11-universal-construction](pages/cgol-ch11-universal-construction.md)] pp.353-355 [synthesis] - "we make use of a block that acts as an elbow"; "a target block (which we refer to as a hand)"
[^5]: [[cgol-ch11-universal-construction](pages/cgol-ch11-universal-construction.md)] pp.354-355 [synthesis] - "internal and external, which refer to the output glider travelling on the same side as the elbow block ... or the opposite side"; "If this value is odd then the elbow is moved to the other side of the input glider stream ... the output lanes of all subsequent glider sequences are flipped from i to x, and vice-versa"
[^6]: [[cgol-ch11-universal-construction](pages/cgol-ch11-universal-construction.md)] p.355 [synthesis] - elbow-moving sequences; Table 11.2 moves "the 90-degree elbow in either direction by any number of half-diagonals up to 10"; "by repeating the sequences from Table 11.2 we can move the elbow to any lane that we like"
[^7]: [[cgol-ch11-universal-construction](pages/cgol-ch11-universal-construction.md)] p.359 - "we use a zero-degree elbow: a small stable object (like a block) that several gliders are fired at on a particular lane so as to produce a single glider going in the same direction but on a different lane"
[^8]: [[cgol-ch11-universal-construction](pages/cgol-ch11-universal-construction.md)] p.360 [synthesis] - "extensive computer searches have been used to generate single-channel glider sequences of this type that produce a single output glider on any lane from −100 to +100"; "we typically do not care about the exact position of the zero-degree elbow"
[^9]: [[cgol-ch11-universal-construction](pages/cgol-ch11-universal-construction.md)] p.356 - "we immediately see from Theorem 5.2 that these types of glider syntheses are universal"; Theorem 11.2 "Every pattern that can be constructed via glider synthesis can be constructed by a single-channel glider synthesis with a 90-degree elbow"
[^10]: [[cgol-ch11-universal-construction](pages/cgol-ch11-universal-construction.md)] p.362 [synthesis] - "straightforward to use a zero-degree elbow to synthesize any object that has a slow salvo synthesis no wider than 200 or so lanes"; n.24 zero-degree elbows are universal via a second, 90-degree elbow, but "actually synthesizing anything in this manner is excruciatingly slow"
[^11]: [[cgol-ch11-universal-construction](pages/cgol-ch11-universal-construction.md)] p.367 [synthesis] - "the former requires somewhere around 25 to 40 times as many gliders to synthesize the same object ... However, the upside of it is that the surrounding circuitry that makes use of the synthesis can be considerably simpler, since it just needs to be able to manipulate gliders along a single lane"; the Demonoid "works by bouncing a single-channel recipe back and forth between two mirror-image ends"
[^12]: [[cgol-ch11-universal-construction](pages/cgol-ch11-universal-construction.md)] p.355 [synthesis] - gaps of 90 and 91 so recipes can be fed "through standard components like Snarks and the easy-to-synthesize Lx200-assisted syringe ... (which has a repeat time of 90 generations)"; "their timing matters mod 2, due to p2 components like blinkers in an intermediate reaction"
[^13]: [[cgol-ch11-universal-construction](pages/cgol-ch11-universal-construction.md)] pp.363-367 [synthesis] - Snarkmaker from "the 95-glider monstrosity" (n.25 "found by Adam P. Goucher in March 2017"), "a grand total of 2 427 gliders"; "the Snarkbreaker consists of 20 gliders", the "varies" glider "must collide with the Snark at the same time as the glider that is fired backward from the elbow"; Scorbie splitter "uses the left half of the ... syringe ... and then another conduit to convert that Herschel into two output gliders", repeat time 90, n.29 Dongook Lee, Fig. 11.15 "praosylen" January 2016; slsparse recipe of "4 006 gliders"
[^14]: [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] §§12.3-12.8, pp.393-421 [synthesis] - the metacell builds its neighbours by single-channel construction
[^15]: [[cgol-ch11-universal-construction](pages/cgol-ch11-universal-construction.md)] pp.380-381 [synthesis] - Fig. 11.27 "A single-channel recipe that is primarily made up of a Snarkmaker bounces around the diamond-shaped track ... creating Snarks that extend the track"; "In April 2019, Michael Simkin constructed Remini ... designed like a single-channel version of the Gemini, but which uses period 30 circuitry ... the only timing gaps that are allowed are multiples of 30"
[^16]: [[cgol-ch11-universal-construction](pages/cgol-ch11-universal-construction.md)] p.381 [synthesis] - "It was already known in 2015 how to emulate arbitrary glider synthesis via gliders on a single lane, but Ekström was the first to show that it is possible even when the gliders are far enough apart ... Snarks and syringes"; p.354 n.13 searches "Mostly by Simon Ekström, with some optimizations by Dave Greene, in 2017"
