---
title: Self-Supporting Spaceship
category: Patterns
summary: A Life spaceship that runs a moving reaction along a track and uses the reaction's output gliders to build the track ahead and clear it behind - the 31c/240 silverfish (Herschels on block tracks), the 17c/45 caterpillar (pi-heptominoes on blinkers), the oblique (23, 5)c/79 waterbear, caterloopillars, and the half-baked knightships; helices carry signals forward when the reaction outruns a glider
tags: [pattern-class, life, spaceship, self-supporting-spaceship, silverfish, caterpillar, waterbear, helix, crawler, rake, half-baked-knightship]
sources: [cgol-ch10-self-supporting-spaceships]
created: 2026-09-25
updated: 2026-09-25
---

# Self-Supporting Spaceship

## Description

A *self-supporting spaceship* is a [[spaceship](pages/spaceship.md)] built around a
reaction that moves along a track. The ship uses the reaction's by-products to construct
the track in front of itself, so the finite pattern keeps going.[^1] It is a small case
of universal construction: the ship reaches into the empty space ahead and builds
there.[^2] Most rely on a core reaction in which one object moves forward with the help
of another object in its path.[^3] Such reactions are called *crawlers* or
*climbers*.[^4]

**The general recipe.**[^5]
- **Wick.** Lay the supporting objects in a line at the spacing the reaction needs. The
  moving object burns through them. Two or more tracks side by side can clean up each
  other's leftovers, giving a *reburnable wick*: one the fuse repositions or rephases
  but does not use up.
- **Rakes.** Several crawlers on parallel tracks, arranged so that their gliders or sparks
  interact, fire gliders forward or backward. A *rephaser* shifts the tracks so later
  rakes fire on other lanes.
- **Front and back.** Gliders from the rakes synthesize new tracks ahead and destroy old
  tracks behind. Getting a glider in front of the leading crawler is the hard part.

### Silverfish (31c/240)

In the 31c/240 reaction a [[herschel](pages/herschel.md)] hits a [[block](pages/block.md)]
and moves forward 31 cells in 240 generations. The block moves back 22 cells, and a second
block and two [[glider](pages/glider.md)]s appear.[^6] On two block tracks, a glider from
each Herschel erases the other Herschel's extra block.[^7]

- **Rakes and lanes.** Six block tracks carry six-Herschel forward rakes, backward rakes
  and rephasers. Forward rakes use the two-glider kickback reaction
  ([[object-synthesis](pages/object-synthesis.md)]). A rephaser shifts the tracks back 22
  cells, and since gcd(22, 31) = 1 enough rephasers reach any lane.[^8] Rakes are named
  R*m*L*n* for *m* Herschels per track firing on lane *n* mod 31, and a table lists the
  shortest rake for each lane.[^9]
- **Front end.** A glider hitting two heavyweight spaceships (HWSSes) makes a
  middleweight spaceship, and a Herschel's spark turns that into the missing front
  block.[^10] The HWSSes are rebuilt by the ship itself. Two gliders turn a passing HWSS's
  sparks into a toad and a beehive without harming it (a
  [[heisenburp](pages/heisenburp.md)]). A 13-glider [[slow-salvo](pages/slow-salvo.md)]
  from forward rakes turns that debris into a new HWSS on the same lane.[^11]
- **Result.** The silverfish has 215 338 live cells in an 11 970 by 48 047 bounding box.
  Chris Cain, Dave Greene and Adam P. Goucher built it in May 2020.[^12] Two earlier
  31c/240 ships, the shield bug (Greene) and the centipede (Cain), were both completed on
  4 September 2014. They used six HWSSes on each side instead of two.[^13]

### Caterpillar (17c/45)

A [[blinker](pages/blinker.md)] moves a pi-heptomino forward 17 cells in 45 generations
and is only repositioned, so a row of blinkers 17 cells apart is a reburnable wick.[^14]
The pi crawler emits no gliders, but two crawlers side by side can collide their large
sparks to make a rake.[^15]

**Helices.** The 17c/45 reaction is faster than a glider's c/4, so gliders cannot be fired
forward to reach flotillae ahead.[^16] The fix is a *helix*: a line of xWSS flotillae
([[light-middle-heavyweight-spaceships](pages/light-middle-heavyweight-spaceships.md)])
with a burning front end that travels below c/2 and fires gliders to at least one side. A
glider does the burning, and each flotilla shifts, reflects or duplicates it.[^17]
- With *m* glider-shifting flotillae in each direction and a delay of *n* generations in
  the duplicator, the helix moves at (20m + 20)c/(40m + n + 101).[^18]
- **Theorem 10.1.** Helices of any rational orthogonal speed below c/2 exist.[^19]
- The caterpillar's helix moves 102 cells in 270 generations with 21 xWSSes.[^20]

The caterpillar is over 7 times as long as the silverfish and has over 50 times as many
live cells, mainly because it has to build the helix along its side. Its components were
found by Gabriel Nivasch, David Bell and Jason Summers, and a program by Nivasch completed
it in December 2004.[^21]

### Waterbear ((23, 5)c/79)

A Herschel hits a glider, moves (23, 5) in 79 generations, and duplicates the glider. This
is faster than c/4, so the ship again needs a helix.[^22] Using fewer glider-shifting
flotillae on one side than the other tilts the helix.
- **Theorem 10.2.** For any x ≥ y > 0, helices exist at any rational speed no faster than
  (x, y)c/(2x + 2y), so they can match the speed and direction of any oblique
  spaceship.[^23]
- Burning through xWSSes, a glider-driven helix can travel diagonally at speeds close to
  c/2, above the c/4 limit for objects in empty space.[^24]

Brett Berger built the waterbear in December 2014, on reactions (including the helix)
found by Ivan Fomichev. Its helix uses 6 xWSSes and fires backward. The reaction runs at an
angle to the helix, so the ship is triangular: 197 896 live cells in a 13 295 by 28 010
box.[^25]

### Caterloopillars and half-baked knightships

A [[caterloopillar](pages/caterloopillar.md)] reverses the roles: trains of spaceships
move a trail of still lifes, and the trains build each other. It reaches every rational
orthogonal speed below c/4.[^26]

A half-bakery moved (3, 6) by passing gliders is stable, so glider timing hardly matters.
Seven gliders on half-bakery tracks generate gliders that return to the start of the
tracks and rebuild the seven gliders by slow salvo. Chris Cain built the parallel
half-baked knightship in July 2014; Adam P. Goucher built the first half-baked knightship
five days earlier.[^27] The parallel version moves at (6, 3)c/245912.[^28]

Other known crawlers include a (13, 1)c/31 B-heptomino crawler, a (27, 1)c/72
Herschel-pair crawler and a (34, 7)c/156 Herschel crawler. Each is harder to use: a helix
at (13, 1)c/31 built from the standard three components needs at least 35 xWSSes, the
Herschel-pair crawler gives no spare glider, and the (34, 7)c/156 crawler leaves junk that
needs extra tracks to clear.[^29]

## Appearances in Sources

- [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] - the whole chapter: silverfish, caterpillar, helices, waterbear, caterloopillars, crawlers
- [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] - lists these ships among the engineered speeds

## Related Concepts

- [[spaceship](pages/spaceship.md)] - the class; these are engineered ships
- [[caterloopillar](pages/caterloopillar.md)] - the self-supporting family that covers every speed below c/4
- [[cordership](pages/cordership.md)] - an engineered ship built from switch engines instead of a track
- [[puffer](pages/puffer.md)] - rakes and the wick-and-fuse idea
- [[signal-wire](pages/signal-wire.md)] - fuses burning through wicks
- [[slow-salvo](pages/slow-salvo.md)], [[object-synthesis](pages/object-synthesis.md)] - how the ships build their tracks and supports

[^1]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] p.311 - "self-supporting spaceships (the topic of this chapter) work by manipulating a reaction that moves along a track so as to construct the track in front of itself"
[^2]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] p.311 - universal construction "could be loosely summarized as the ability to 'construct anything that can be constructed'"; "we will build spaceships that work by reaching out into a region of empty space in front of themselves and constructing something there"
[^3]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] p.311 - "Most self-supporting spaceships rely on a core reaction that moves an object forward with the help of another object that is in its path"
[^4]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] p.338 - "numerous other known reactions that involve an object moving through a stable or glider-based wick--such reactions are called crawlers or climbers"
[^5]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] pp.312-315,322 [synthesis] - "a reburnable wick: a wick that is not used up (but is potentially repositioned and/or rephased) after its fuse ... burns through it"; forward and backward rakes; rephasers; kickback reactions to synthesize and destroy tracks; "there is no way to arrange kickback reactions so as to put gliders in front of the frontmost rakes"; the same ideas reused for the caterpillar
[^6]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] pp.311-312 - "a Herschel collides with a block in such a way that it moves forward by 31 cells over the course of 240 generations. At the same time, the block is moved back by 22 cells, a second block is created, and two gliders are released"
[^7]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] p.312 - "we can use one of the output gliders from one of the Herschels to cleanly erase the extra block that is produced by the other Herschel"
[^8]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] p.313 [synthesis] - the forward rake uses "the two-glider kickback reaction from Table 5.1" and "six Herschels and six block tracks"; the rephaser "moves the block tracks backward by 22 cells"; "since gcd(22, 31) = 1, we can use multiple copies of this rephaser so as to make subsequent rakes output gliders on any lanes of our choosing"
[^9]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] pp.317-319 [synthesis] - names "of the form R<number of Herschels>L<lane number>"; Table 10.1 "A summary of the shortest forward rakes that can be used to put a glider on a given lane (mod 31)"
[^10]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] p.315 - "a middleweight spaceship can stabilize the front of the Herschel track in the exact same way as a block (in fact, one of the Herschel's sparks simply converts the MWSS into a block in the correct position)"; Fig. 10.5(a) "colliding a glider with two heavyweight spaceships so as to make a perpendicular middleweight spaceship"
[^11]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] pp.315-317 [synthesis] - a glider pair creates "a toad and a beehive a safe distance from the HWSS ... (without disturbing the HWSS)"; n.4 "this reaction is a Heisenburp"; n.3 "we are using a heavyweight spaceship to synthesize itself"; Fig. 10.7 "A 13-glider slow salvo that turns the configuration of a beehive and toad ... back into an HWSS on the same lane"
[^12]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] p.321 - "Despite its massive size of 215 338 live cells and 11 970 × 48 047 bounding box"; n.13 "Created by Chris Cain, Dave Greene, and Adam P. Goucher in May 2020"
[^13]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] p.337 - "These spaceships, called the shield bug and the centipede ... were completed on the same day--September 4, 2014--by Dave Greene and Chris Cain, respectively"; the silverfish's front end "is supported by just two heavyweight spaceships on each side instead of six"
[^14]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] p.321 - "a blinker can be used to move a pi-heptomino forward by 17 cells over the course of 45 generations (while just repositioning, not destroying, the blinker). By placing a row of blinkers with a spacing of 17 cells ... we thus get a reburnable blinker wick"
[^15]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] p.322 - "the pi crawler does not emit any gliders on its own. Fortunately, it does create a large spark, and we can collide two of those sparks without much effort so as to create a backward rake"
[^16]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] p.323 - "because the 17c/45 reaction that we are using travels faster than c/4, we cannot fire gliders forward at those xWSSes to change their direction"
[^17]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] pp.323-324 - "a helix: a configuration of xWSSes that has a burning front end that causes it to (a) travel at a speed slower than c/2 ... and (b) periodically fire gliders off to at least one side. One way to make a helix is to have a glider do the burning"; Fig. 10.13 moves, reflects and duplicates the glider
[^18]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] p.324 [synthesis] - delay the final xWSS pair by n generations and use m glider-shifting flotillae in each direction; the helix "moves the glider forward orthogonally by 20m + 20 cells over the course of 40m + n + 101 generations"
[^19]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] p.325 - Theorem 10.1: "The three reactions from Figure 10.13 can be used to create an orthogonal helix, which fires gliders forward on one side, with any rational speed slower than c/2"
[^20]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] pp.324-325 - "the helix displayed in Figure 10.14 takes 270 generations to push a glider forward orthogonally by 102 cells"; "the 17c/45 helix from Figure 10.14 that consists of 21 xWSSes"
[^21]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] p.325 - "it is over 7 times as long and has over 50 times as many live cells. The primary reason ... is that it has to synthesize the 21-xWSS helix"; n.23 "The components used in the caterpillar were found by Gabriel Nivasch, David Bell, and Jason Summers, and construction was completed in December 2004 by a computer program written by Nivasch"
[^22]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] p.327 - "a Herschel colliding with a glider so as to displace itself by (23, 5) over the course of 79 generations while duplicating the glider"; "since this reaction moves faster than a glider (i.e., c/4), we again need to use the backward gliders to synthesize a helix"
[^23]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] p.328 - "the only modification ... is to use fewer glider-shifting flotillae on one half of the helix than on the other"; Theorem 10.2: "For any integers x ≥ y > 0, the three reactions from Figure 10.13 can be used to create an oblique helix ... with any rational speed that is no faster than (x, y)c/(2x + 2y). In particular, such helices exist that travel at the same speed and direction as any oblique spaceship"
[^24]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] p.329, n.27 - "These helices can travel diagonally at speeds arbitrarily close to c/2, for example, despite the c/4 diagonal spaceship speed limit ... the glider is not travelling through empty space--it is burning through xWSSes"
[^25]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] pp.329-330 [synthesis] - Fig. 10.18 "Constructed by Brett Berger in December 2014, based on numerous reactions (such as the helix) that were found by Ivan Fomichev"; helix of "just 6 xWSSes" that "fires gliders backwards"; "the simplest waterbear to construct is triangular"; "197 896 live cells and fits in a 13 295 × 28 010 bounding box"
[^26]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] pp.330,335 [synthesis] - "what if instead of using an infinite trail of stable objects ... to support a naturally moving object ..., we use an infinite trail of spaceships to move a stable object?"; Theorem 10.3 "any rational speed slower than c/4"
[^27]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] pp.337-339 [synthesis] - Fig. 10.25(d) "A (3, 6) half-bakery crawler"; "a half-bakery is stable and thus the timing of the gliders is almost completely irrelevant"; seven parallel copies; gliders sent "back to the start of the half-bakery trails" recreate the gliders by slow salvo; "constructed by Chris Cain in July 2014, is called the parallel half-baked knightship"; n.38 "The first half-baked knightship was built by Adam P. Goucher just 5 days earlier"
[^28]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] p.343, Ex. 10.36 - "The parallel HBK from Figure 10.27 has speed (6, 3)c/245912"
[^29]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] pp.337-340 [synthesis] - Fig. 10.25 crawlers; forward-firing helix at (13, 1)c/31 "built out of the components from Figure 10.13 must contain at least 35 xWSSes"; the (27, 1)c/72 crawler "does not produce an extra output glider"; the (34, 7)c/156 crawler "produces some junk behind itself every period" and "seems to require 4 tracks instead of just 2"
