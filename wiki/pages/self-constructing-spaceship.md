---
title: Self-constructing spaceship (Gemini, Geminoids, Demonoids)
category: Patterns
summary: A Life spaceship that moves by building a copy of itself further along and destroying the old copy, with its construction recipe carried as moving gliders; the Gemini and its Geminoid variants reach every rational slope, and Demonoids, which bounce one single-channel recipe between two small ends, reach every rational diagonal speed below c/4
tags: [pattern-class, life, spaceship, self-constructing, gemini, geminoid, demonoid, universal-constructor, single-channel]
sources: [cgol-ch11-universal-construction]
created: 2026-09-25
updated: 2026-09-26
---

# Self-constructing spaceship (Gemini, Geminoids, Demonoids)

## Description

A *self-constructing spaceship* is a [[spaceship](pages/spaceship.md)] that holds a long
recipe of gliders encoding its own construction. Machinery at its ends reads the recipe to
build a copy of the ship further along the plane, then destroys the old copy, so the whole
pattern travels without leaving anything behind.[^1] The recipe is not stored on a tape of
still lifes. It is a stream of moving gliders, spaced to encode the instructions and
bounced between the two ends so it can be used again every period.[^2]

**The Gemini** (Andrew J. Wade, May 2010) was the first self-constructing spaceship and
the first oblique one (moving at a slope other than 0 or ±1).[^3]
- Each of its two identical ends holds three construction arms of the Chapman-Greene design
  (see [[single-channel-construction](pages/single-channel-construction.md)] for the
  elbow idea). Two arms build the next copy; the third, a *destruction arm*, removes the
  previous one.[^4]
- The recipe runs on 24 parallel glider lanes, 12 in each direction. The name is Latin for
  "twins", after the identical ends.[^5]
- It moves (1024, 5120) cells every 33,699,586 generations, a slope of 5.[^6]

**Geminoids** are modified Geminis.[^7]
- **Slower.** Each extra full diagonal between the ends adds 8 generations to the period
  without changing the displacement, so Geminoids can be arbitrarily slow.
- **Any slope.** Pushing the two construction elbows out by m and n cells before building
  gives a displacement of (m - n, m + n) per period, so every rational slope is reachable.
  A slope-2 knightship Geminoid (Dave Greene, June 2010) moves (4096, 8192) cells every
  35,567,490 generations.
- **Faster, to a limit.** More PUSH operations make a Geminoid faster. Each costs at least
  579 generations: the 575-generation repeat time of the Callahan G-to-H conduit plus 4.
  Theorem 11.1: with the Gemini's own parts, Geminoids reach any speed (x, y)c with
  rational x, y < 1/579 and x ≠ y. A Silver reflector would raise the limit to c/501, and
  Snarks with syringe-based duplicators to c/94, at the price of a full rebuild.

**Demonoids** ("diagonal" plus "Geminoid") bounce a single-channel recipe between two
mirror-image ends. Each end is only a Scorbie splitter, which copies the recipe so one copy
can build while the other is kept, and a Snark reflector, which sends the kept copy back.[^8]
All Demonoids travel diagonally.[^9]
- **Slow Demonoid.** A 14,247-glider recipe builds the next ends 128 cells ahead and
  destroys the old ones with lightweight and middleweight spaceships. Its period is 2^21 =
  2,097,152 and its speed c/16384. It has about 7 × 10^4 live cells against the Gemini's
  8 × 10^5, and a bounding box about 3 × 10^5 cells on a side against 4 × 10^6.[^10]
- **Middling Demonoid.** To move the elbow faster, the recipe builds a 2-engine
  [[cordership](pages/cordership.md)] from a one-glider seed, lets it travel, and shoots it
  down with a single glider into ash that becomes a new elbow. It moves 2^14 cells every
  2^22 generations, c/256. Its design limit is c/14 rather than the Cordership's c/12,
  because a Snarkbreaker's backward glider must travel back part of the way.[^11]
- **Speed Demonoid** (Pavel Grankovskiy, September 2020).[^12]
  - Gliders cannot catch a c/4 ship from behind, so the elbow rides on a c/4 crab
    wickstretcher that stretches boat wicks. A glider lights a c/3 fuse along a wick; the
    fuse catches the crab and, helped by an escorting glider, turns it into an elbow.
  - Extra still lifes placed around each Snark and Scorbie splitter let a single glider
    destroy it, and that glider then moves on to the next, so no return glider is needed.
  - Two isolated TRIGGER gliders light the fuses of a double boatstretcher.
  - One built example moves 3,285,622 cells every 16,493,928 generations, about 0.1992c.
- **Every diagonal speed below c/4.** With trigger gap n generations and end separation m
  full diagonals, the speed is nc / (4(n + m)). Scaling n and m up past their minimum
  sizes (n ≥ 1,642,811 and n + m ≥ 2,061,741) gives any rational speed below c/4, the
  diagonal speed limit. A script builds a Speed Demonoid of any requested speed.[^13]

**Relatives.**[^14]
- The first Demonoid (Chris Cain and Dave Greene, November 2015) used pairs of gliders
  10 half-diagonals apart instead of single-channel recipes, so each end had twice as much
  circuitry.
- The Orthogonoid (Dave Greene, June 2017) works like a Demonoid but uses middleweight
  spaceships to travel orthogonally.
- Remini (Michael Simkin, April 2019) is an oblique self-constructing
  [[puffer](pages/puffer.md)] built like a single-channel Gemini on period-30 circuitry.
- The QuickSilver Demonoid (Pavel Grankovskiy, December 2021, from a blueprint by
  "googleplex") uses overclocked Silver reflectors.
- Dropping the destruction part of a Demonoid's recipe makes it a puffer that leaves Snarks
  and Scorbie splitters behind.

**Relation to self-reproduction.** A self-constructing spaceship is a working instance of
von Neumann's scheme in [[universal-constructor](pages/universal-constructor.md)]. The
construction arms play the constructor, the Scorbie splitter or glider duplicators play the
description copier, and the glider stream is the description. It differs from
[[self-reproduction](pages/self-reproduction.md)] in the full sense because each new copy
replaces the old one instead of adding to the population (own reasoning, from the sources
on this page).

## Appearances in Sources

- [[cgol-ch11-universal-construction](pages/cgol-ch11-universal-construction.md)] - §11.1 Gemini and Geminoids; §§11.5-11.7 slow, middling and Speed Demonoids; §11.8 history and relatives

## Related Concepts

- [[single-channel-construction](pages/single-channel-construction.md)] - how Demonoid recipes build
- [[universal-constructor](pages/universal-constructor.md)] - the scheme these ships carry out
- [[spaceship](pages/spaceship.md)] - speeds and slopes these ships fill in
- [[cordership](pages/cordership.md)] - the middling Demonoid's elbow carrier
- [[reverse-caber-tosser](pages/reverse-caber-tosser.md)] - another way to store a recipe, in one distance
- [[construction-arm](pages/construction-arm.md)] - the Chapman-Greene arms each end of the Gemini carries
- [[self-supporting-spaceship](pages/self-supporting-spaceship.md)] - the sibling engineered-ship family, driven by a reaction along a track

[^1]: [[cgol-ch11-universal-construction](pages/cgol-ch11-universal-construction.md)] pp.346-348 [synthesis] - Gemini "is primarily made up of long sequences of gliders that encode its own construction"; "use an extremely long chain of gliders to have two construction arms build copies of themselves somewhere else in the plane"; the construction must propagate "without leaving anything behind itself", so a destruction arm removes the old circuitry
[^2]: [[cgol-ch11-universal-construction](pages/cgol-ch11-universal-construction.md)] pp.348, 379 [synthesis] - "we instead have the glider recipes bounce back and forth between two copies of the entire three-arm circuit"; "you just store a bunch of moving gliders at the spacing you want - there is no need to encode anything at all"
[^3]: [[cgol-ch11-universal-construction](pages/cgol-ch11-universal-construction.md)] pp.349, 379 [synthesis] - n.6 "Constructed by Andrew J. Wade in May 2010"; Wade built "the first ever oblique and/or self-constructing spaceship"
[^4]: [[cgol-ch11-universal-construction](pages/cgol-ch11-universal-construction.md)] pp.348-349, 379 [synthesis] - a third "destruction arm" is built alongside the construction pair; Fig. 11.4 "three construction/destruction arms"; "the Gemini spaceship included not just one, but three complete copies of the prototype construction arm"
[^5]: [[cgol-ch11-universal-construction](pages/cgol-ch11-universal-construction.md)] pp.348-349 [synthesis] - Fig. 11.4 "24 parallel glider lanes (12 travelling in each direction), which carry a recipe for building the ship"; n.5 "the two ends of the spaceship that we construct will be exactly identical. This is the reason for its name “Gemini” - it is Latin for “twins”"
[^6]: [[cgol-ch11-universal-construction](pages/cgol-ch11-universal-construction.md)] p.349 - "It builds a copy of itself displaced by 5 120 cells in one direction and 1 024 cells in the other direction every 33 699 586 generations, giving its direction of travel a slope of 5120/1024 = 5"
[^7]: [[cgol-ch11-universal-construction](pages/cgol-ch11-universal-construction.md)] pp.350-352 [synthesis] - separating the ends adds "8 generations per period", so Geminoids "are arbitrarily slow"; displacement "(m − n, m + n) cells per period", "any rational slope"; n.9 knightship "constructed by Dave Greene in June 2010", Fig. 11.5 "(4096, 8192)c/35567490"; Callahan G-to-H "repeat time of 575 generations", "575 + 4 = 579 generations per PUSH"; Theorem 11.1 (Geminoid Speed Limit); Silver reflector "c/(497 + 4) = c/501"; Snarks and syringe-based conduits "c/(90 + 4) = c/94", which "would require a complete rebuild of the Gemini"
[^8]: [[cgol-ch11-universal-construction](pages/cgol-ch11-universal-construction.md)] p.367 [synthesis] - n.30 "The name “Demonoid” is a portmanteau of “diagonal” and “Geminoid”"; ends "consist just of a Scorbie splitter (to duplicate the single-channel recipe, so that one copy can be used for construction purposes while the other copy is preserved) and a Snark (to send the preserved copy ... back toward the other end)"
[^9]: [[cgol-ch11-universal-construction](pages/cgol-ch11-universal-construction.md)] p.345 - spaceships "with any rational speed (but fixed at a diagonal slope of 1)"
[^10]: [[cgol-ch11-universal-construction](pages/cgol-ch11-universal-construction.md)] pp.367-369 [synthesis] - "approximately 7 × 10^4 live cells instead of 8 × 10^5, and its bounding box has a side length of approximately 3 × 10^5 cells instead of 4 × 10^6"; recipe "consists of 14 247 gliders"; next ends "128 cells in front"; destruction "via lightweight and middleweight spaceships"; "period 2^21 = 2 097 152 and speed 128c/2097152 = c/16384"
[^11]: [[cgol-ch11-universal-construction](pages/cgol-ch11-universal-construction.md)] pp.369-371 [synthesis] - "use the elbow block to synthesize a spaceship that moves in the desired direction, and then shoot it down"; Fig. 11.18 one-glider seed for a 2-engine Cordership; Fig. 11.19 "shot down from behind by a single glider"; "displaces itself by 2^14 = 16 384 cells over the course of 2^22 = 4 194 304 generations, for a speed of ... c/256"; "This design's speed limit is actually c/14 (not c/12)" because of the Snarkbreaker's backward glider
[^12]: [[cgol-ch11-universal-construction](pages/cgol-ch11-universal-construction.md)] pp.371-376 [synthesis] - "those gliders cannot possibly catch up to the elbow-carrying spaceship since they travel at the same speed ... we instead synthesize a c/4 diagonal wickstretcher"; Fig. 11.22 c/3 fuse and escorting glider; Fig. 11.23 3 and 8 extra still lifes let one glider destroy a Snark or Scorbie splitter, then "the glider is reflected toward the next piece of circuitry"; n.37 "Constructed by Pavel Grankovskiy in September 2020"; double boatstretcher and TRIGGER1/TRIGGER2; Fig. 11.25 "moves 3 285 622 cells diagonally every 16 493 928 generations, for a speed of 1642811c/8246964 ≈ 0.1992c"
[^13]: [[cgol-ch11-universal-construction](pages/cgol-ch11-universal-construction.md)] pp.375-377 [synthesis] - parameters m (separation in full diagonals) and n (trigger gap in generations); speed 2nc/(8n + 8m) = (n/(n + m))(c/4); "we can choose n ≥ 1 642 811 and n + m ≥ 2 061 741 so that the resulting Speed Demonoid is actually constructible"; "Speed Demonoids can be adjusted to have any rational speed that is slower than c/4. In fact, there is a computer script that carries out this adjustment automatically"; p.371 n.33 "no diagonal spaceship can go faster than c/4"
[^14]: [[cgol-ch11-universal-construction](pages/cgol-ch11-universal-construction.md)] pp.379-383 [synthesis] - "In November 2015, Chris Cain and Dave Greene completed the first Demonoid ... used pairs of gliders separated by 10hd ... which doubled the amount of circuitry"; "In June 2017, Dave Greene constructed an Orthogonoid spaceship ... uses middleweight spaceships (instead of gliders) to achieve a slow orthogonal ... speed"; "In April 2019, Michael Simkin constructed Remini, an oblique self-constructing puffer that is designed like a single-channel version of the Gemini, but which uses period 30 circuitry"; QuickSilver Demonoid, December 2021, "googleplex", "overclocked Silver reflectors"; Ex. 11.26 "Demonoid spaceships can be turned into Demonoid puffers simply by removing the destruction portion of their glider recipe"
