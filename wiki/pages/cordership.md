---
title: Cordership
category: Patterns
summary: A c/12 diagonal Life spaceship built from switch engines that clean up each other's debris - the 10-engine Cordership (period 96) is the classic form, versions with as few as 2 engines exist, and the pulsating sparks at the rear reflect gliders and turn them into LWSSes
tags: [pattern, life, spaceship, cordership, switch-engine, c-over-12, diagonal]
sources: [cgol-ch4-spaceships-and-moving-objects, cgol-ch1-early-life]
created: 2026-09-25
updated: 2026-09-25
---

# Cordership

## Description

A *Cordership* is a [[spaceship](pages/spaceship.md)] built from
[[switch-engine](pages/switch-engine.md)]s that stabilize one another and erase their
debris completely, so nothing is left behind. Like the switch engine it travels
diagonally at c/12. It is named for Charles Corderman, who found the switch engine and
most of its simple puffers.[^1] Making switch engines stabilize each other into a
puffer (an ark) is easy; erasing all the debris is much harder.[^2]

**How it works.** Two switch engines side by side overcrowd and destroy each other's
debris, but only for the 48 generations in which they move apart. In the next 48, as they
close in, the debris is too far apart to interact and survives. An infinitely long line
of switch engines would work, each using a different neighbour to clean up in turn, but
it would not be finite.[^3] The fix uses the fact that the edge engines' debris briefly
makes a block, and a single-file trail of blocks spaced that way can destroy that same
debris.[^4]
- **Front:** a row of switch engines leaves two trails of blocks.
- **Middle:** switch engines destroy the front engines' leftover debris.
- **Back:** a row of switch engines destroys, and is stabilized by, the trails of blocks.

The **10-engine Cordership** (4 front, 2 middle, 4 back) is a c/12 diagonal spaceship
with period 96. The first Cordership, built by Dean Hickerson in April 1991, used 13
engines. Versions with 3 engines and with just 2 have been found.[^5]

**Uses.** The rear engines give off pulsating sparks. A 10-engine Cordership can reflect
a [[glider](pages/glider.md)] by 90 or 180 degrees, or turn it into a lightweight
spaceship. Changing the back end gives a different set of sparks.[^6] A *Corderrake* is a
switch-engine rake that fires gliders sideways ([[puffer](pages/puffer.md)]).[^7]

## Appearances in Sources

- [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] - §4.3: construction, the 10-engine Cordership, its sparks; Exs. 4.15-4.21
- [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] - the switch engine and arks it is built from

## Related Concepts

- [[switch-engine](pages/switch-engine.md)] - its components
- [[spaceship](pages/spaceship.md)] - its class; c/12 diagonal
- [[puffer](pages/puffer.md)] - arks and Corderrakes are its non-spaceship relatives

[^1]: [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] p.90 [synthesis] - the switch engine "travels at a speed of c/12 diagonally"; using switch engines "to stabilize each other and erase their debris entirely (thus creating a spaceship) ... Spaceships constructed in this way are called Corderships"; n.13 "Named after Charles Corderman, who discovered the switch engine and most of the simple puffers based on it in 1971"
[^2]: [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] p.90 - "using switch engines to stabilize each other and erase their debris entirely ... is much more difficult"; n.12 "The first ark was found in 1971, whereas the first spaceship based on switch engines was not found until 1991"
[^3]: [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] p.91 [synthesis] - Fig. 4.19: the debris of two switch engines is destroyed only in the first 48 generations; Fig. 4.20: "An infinitely long wave of switch engines"; "the object it creates must be infinitely long"
[^4]: [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] pp.91-92 [synthesis] - the edge debris "temporarily creates a block"; "this exact same spacing of blocks can be used to destroy the debris left behind by these edge switch engines"; front, middle and back scheme
[^5]: [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] pp.92-93 [synthesis] - Fig. 4.23: "A 10-engine Cordership, which is a c/12 diagonal spaceship with period 96" with 4, 2 and 4 engines; n.15 "The first ever Cordership, which used 13 switch engines, was constructed by Dean Hickerson in April 1991"; Corderships "that use as few as 2 switch engines" (n.16 "praosylen", December 2017); 3 engines (Ex. 4.18, Paul Tooke 2004)
[^6]: [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] p.93 - "the collection of pulsating sparks that are produced by the rear row of switch engines"; Fig. 4.24 reflects a glider by 90 and 180 degrees and turns a glider into an LWSS; changing the back end gives a new set of sparks
[^7]: [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] p.115, Ex. 4.21 - "A Corderrake ..., which is a c/12 rake based on switch engines that shoots gliders sideways as it moves"
