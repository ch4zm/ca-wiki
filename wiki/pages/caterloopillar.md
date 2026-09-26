---
title: Caterloopillar
category: Patterns
summary: A family of self-supporting Life spaceships in which xWSS flotillae push and pull two antiparallel tracks of loaves and build each other by unidirectional slow salvo encoded in the loaf spacing - the first (Michael Simkin, April 2016, Pattern of the Year) moves at c/8, the book's worked example at c/24; caterloopillars exist in theory for every rational orthogonal speed below c/4, though the construction script misses some speed forms
tags: [pattern, life, spaceship, self-supporting-spaceship, caterloopillar, loaf, flotilla, slow-salvo, adjustable-speed]
sources: [cgol-ch10-self-supporting-spaceships]
created: 2026-09-25
updated: 2026-09-26
---

# Caterloopillar

## Description

A *caterloopillar* is a [[self-supporting-spaceship](pages/self-supporting-spaceship.md)]
that reverses the usual design. The silverfish and caterpillar use a trail of stable
objects to support a moving object. A caterloopillar uses a trail of spaceships to move a
stable object, a loaf.[^1] David Bell proposed the idea in October 2006; slow-salvo
technology was ready to build it in April 2016.[^2] Each half of the ship acts as a
[[universal-constructor](pages/universal-constructor.md)], building the other half's parts
while reading and moving the shared construction tape.[^18]

**The first ones.** Michael Simkin completed the first caterloopillar on April 9, 2016. It
moves at c/8 (250 cells per 2000 generations), the first spaceship of that speed. It has
232,815 to 239,370 live cells and a bounding box of about 734 × 500,000.[^17][^19] Simkin's
script then gave c/9 (252c/2268) within a week, followed by 2c/9 (the fastest at the time),
c/11 and c/12. The smallest early ones, c/13 and c/12, have about 117,000 and 125,000
cells.[^20] A 31c/240 caterloopillar beat the Centipede, the earlier record holder at that
speed. The caterloopillar was voted the ConwayLife.com Pattern of the Year for 2016.[^17]
Trivial changes turn it into puffers and rakes.[^19]

**Loaf tracks.** The spine is a track of loaves.[^3]
- A **loaf-pusher** of three xWSS flotillae ([[light-middle-heavyweight-spaceships](pages/light-middle-heavyweight-spaceships.md)])
  turns a loaf into a [[glider](pages/glider.md)], reflects the glider, and rebuilds the
  loaf 46 cells farther forward without destroying the glider. Spreading the flotillae
  raises the push to 46 + 2n cells.[^4]
- A **loaf-puller** of three flotillae pulls a loaf back 54 + 2n cells the same way. With
  the pusher set to 46 + 2m, choosing m = n + 4 makes both move the loaves equally.[^5]
- Unlike helix flotillae, these flotillae survive the glider.[^6]

**The loop.** Pushers travel forward along one loaf track, and pullers travel backward
along a parallel one. The spacing of the loaves on each track encodes a unidirectional
[[slow-salvo](pages/slow-salvo.md)] of gliders that builds the flotillae of the other
track.[^7] The xWSSes form a long loop that seems to build itself. The name echoes the
caterpillar and Douglas Hofstadter's "strange loop".[^8]

**Front and back ends.** Spent flotillae are destroyed by still lifes that must move with
the ship. A single still life plus extra flotillae does it. The still life becomes a
glider, then two gliders, which rebuild the still life farther down the track and build a
constellation that destroys the loaf-movers.[^9] A honey farm serves the pusher (moved 62
+ 2n cells) and a [[beehive](pages/beehive.md)] the puller (94 + 2n cells).[^10]

**The glider synthesis.** The slow salvo must be monochrome, all gliders of one colour,
because the loaf spacing is orthogonal. It runs to hundreds of steps and is found by
computer. Michael Simkin wrote the script that built the first caterloopillars in April
2016.[^11]

**Speeds.** The ship's speed is the loaf displacement per period over the flotilla
spacing, corrected for a Doppler effect: the flotillae must also cover the distance the
loaves were moved.[^12]
- The example in the book pushes and pulls the loaves 98 cells per period with forward
  flotillae 1 078 cells apart, for 98c/(2(1078 + 98)) = c/24.[^12]
- Spreading its flotillae gives slower ships. Squeezing them is limited to a 352-cell
  spacing, so its design tops out at 49c/450.[^13]
- **Theorem 10.3.** Caterloopillars exist at every rational speed below c/4. Set the
  flotillae to move the loaves 100 + 2n cells and space the pushers 400 + 2n + 2m cells
  apart. The speed is (50 + n)c/(500 + 4n + 2m), and n = 300p - 50, m = 150(q - 4p) - 150
  gives any p/q < 1/4.[^14] In practice Simkin's script does not work for speeds of the
  form m/(8k+2) and m/(8k+6).[^17]
- The c/4 ceiling comes from the glider: at larger displacements more of each period is
  spent as a c/4 glider bouncing between flotilla parts. Reaching c/2 would need a major
  redesign.[^15]
- Faster caterloopillars are usually larger: their flotillae spread out and their
  syntheses need more steps.[^16]

## Appearances in Sources

- [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] - §10.4: loaf tracks, pushers and pullers, front and back ends, the c/24 example, Theorem 10.3
- [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] - listed as the engineered ship covering every orthogonal speed below c/4

## Related Concepts

- [[self-supporting-spaceship](pages/self-supporting-spaceship.md)] - its class
- [[spaceship](pages/spaceship.md)] - the speed catalogue and the c/4 and c/2 limits
- [[slow-salvo](pages/slow-salvo.md)] - how each track builds the other
- [[universal-constructor](pages/universal-constructor.md)] - what each half of the ship is
- [[light-middle-heavyweight-spaceships](pages/light-middle-heavyweight-spaceships.md)] - the flotillae

[^1]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] p.330 - "what if instead of using an infinite trail of stable objects like blocks or blinkers to support a naturally moving object like a Herschel or pi-heptomino, we use an infinite trail of spaceships to move a stable object?"
[^2]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] p.330, n.29 - "This basic idea for the construction of a caterloopillar spaceship was originally proposed by David Bell in October 2006. It wasn't until April 2016 that slow-salvo technology had advanced to the point that it was actually constructed"
[^3]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] p.330 - "We will thus use a track of loaves as the central spine of a self-supporting spaceship"
[^4]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] p.331 - Fig. 10.19 "three xWSS flotillae that push a loaf forward by 46 cells and simultaneously create a glider"; the first flotilla "turns the loaf into a glider", the next "reflects that glider", the last "creates a loaf from that glider (without destroying it)"; spreading them gives "46 + 2n cells"
[^5]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] p.332 - Fig. 10.21 "three xWSS flotillae that pull a loaf backward by 54 cells"; "we can adjust the loaf-pushing and loaf-pulling flotillae to move the loaf by 46 + 2m and 54 + 2n cells, respectively. Choosing m = n + 4 results in both flotillae moving the loaf track by 54 + 2n cells"
[^6]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] p.330, n.30 - "In contrast with the glider-manipulating flotillae that are used in helices ..., these flotillae are not destroyed by the glider"
[^7]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] pp.330-331 [synthesis] - loaf-pushing and loaf-pulling flotillae "run on parallel tracks in opposite directions" and "synthesize each other"; Fig. 10.20 each loaf track "encodes a unidirectional slow-salvo synthesis" of the other flotilla; task 3 "encode them in the spacing between loaves"
[^8]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] p.330, n.31 - "the xWSSes form a long loop that seems to be synthesizing itself. The name is also a reference to the term 'strange loop', a concept explored in Douglas Hofstadter's famous book Gödel, Escher, Bach"
[^9]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] p.332 [synthesis] - "we can place a constellation of still lifes at the ends of the tracks. The tricky part is moving that constellation down the track"; "we instead use a single still life along with additional xWSS flotillae"; still life to glider to two gliders to a moved copy of the still life and a destroying constellation
[^10]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] p.333, Fig. 10.22 [synthesis] - "A honey farm and 9-xWSS flotilla" destroys the loaf-pusher, pushed "62 + 2n cells"; "A beehive and 10-xWSS flotilla" destroys the loaf-puller, pulled "94 + 2n cells"
[^11]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] p.334 - "we even need this glider synthesis to be monochrome--consisting entirely of gliders of just one color ... that spacing is orthogonal"; "Such a glider synthesis will consist of hundreds of steps, so actually coming up with it is best left to a computer script"; n.33 "made by Michael Simkin and used to construct the first caterloopillars in April 2016"
[^12]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] p.335 - "pushes and pulls the loaf track by 98 cells per period, and the forward-travelling xWSS flotillae are separated by 1 078 cells, for a speed of 98c/(2(1078 + 98)) = 98c/2352 = c/24"; n.34 "a 'doppler effect': the flotillae do not have to travel just 1 078 cells per period, but also the extra 98 cells that the still lifes were pushed"
[^13]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] p.335 - "move the flotillae farther apart, resulting in larger caterloopillars that travel much more slowly"; "the forward flotillae used by this caterloopillar must be separated by at least 352 cells, so these simple adjustments cannot possibly produce caterloopillars that are any faster than 98c/(2(352 + 98)) = 49c/450"
[^14]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] p.335 [synthesis] - Theorem 10.3 "Caterloopillar spaceships can be constructed that travel at any rational speed slower than c/4"; proof with push 100 + 2n, separation 400 + 2n + 2m, speed (50 + n)c/(500 + 4n + 2m), n = 300p - 50 and m = 150(q - 4p) - 150
[^15]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] p.335, n.35 - "more and more of its travel time is spent as a (c/4) glider bouncing between the components of the flotillae ... Reaching the theoretical speed limit of c/2 would require a major redesign"
[^16]: [[cgol-ch10-self-supporting-spaceships](pages/cgol-ch10-self-supporting-spaceships.md)] pp.335-337 - "faster caterloopillars are typically larger than slower ones, not just because their component flotillae become more spaced out, but also because the glider syntheses used to construct those flotillae require more steps"
[^17]: https://conwaylife.com/wiki/Caterloopillar (2026-09-26, search excerpt) - "The first Caterloopillar was constructed by Michael Simkin and completed on April 9, 2016; this Caterloopillar has a speed of c/8"; period 2000, 250c/2000; "voted Pattern of the Year for 2016"; "The script does not work for speeds of the form m/(8k+2) and m/(8k+6)"; "the first three being c/9, c/11 and c/12"; "a 31c/240 one smaller than the Centipede"
[^18]: https://playgameoflife.com/list.html (Life Lexicon, 2026-09-26, search excerpt) - "The front and back halves of Caterloopillars each function as universal constructors, with each half constructing the building blocks of the other half, while also reading and moving a construction tape"
[^19]: https://mathematrec.wordpress.com/2016/04/10/how-slow-do-you-want-it/ (2016-04-10) - Simkin "has found an orthogonal c/8 spaceship, the first of that speed"; can be modified "to produce spaceships - or, with trivial modifications, puffers or rakes - of any speed slower than c/4"; Simkin: "cell count: minimal - 232,815 maximal - 239,370 bounding box ~ 734 X 500K"
[^20]: https://conwaylife.com/forums/viewtopic.php?t=2151 (2016-04-15 to 2016-04-18, search excerpt) - simsim314: "I've managed to complete the c/9 caterloopillar ... It's c252/2268 (=c/9)"; "Here is 2c/9 (1016/4572) ... the fastest caterloopillar yet"; "The smallest caterloopillar (c/13 with 117K and c/12 with 125K)"
