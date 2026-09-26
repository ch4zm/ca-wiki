---
title: Soup search
category: Concepts
summary: Finding Life objects by evolving random starting patterns ("soup") and cataloguing what is left ("ash"); automated since 1994 (Flammenkamp), now done at scale by Goucher's apgsearch and its Catagolue census, which also runs other Life-like rules
tags: [concept, method, soup, ash, apgsearch, census, simulation]
sources: [cgol-ch4-spaceships-and-moving-objects, cgol-ch1-early-life, lifewiki-catagolue, lifewiki-apgsearch]
created: 2026-09-25
updated: 2026-09-25
---

# Soup search

## Description

**Soup and ash.** A random starting configuration is called *soup*, and the objects it
leaves after its chaos dies down are *ash*, what remains once a pattern stops
"burning".[^1] Evolving soups is one of three ways to find Life objects, alongside
programs that search for patterns with given properties and combining known objects into
new ones.[^2] Tiny changes matter: flipping one cell of a soup can make it last 25 times
longer and leave 20 times as much ash.[^3]

**What ash shows.** The commonest ash objects are the block, tub, boat, ship, beehive,
loaf and pond, the [[blinker](pages/blinker.md)], and the [[glider](pages/glider.md)].
The [[pulsar](pages/pulsar.md)], toad, beacon, clock, [[pentadecathlon](pages/pentadecathlon.md)]
and [[light-middle-heavyweight-spaceships](pages/light-middle-heavyweight-spaceships.md)]
also appear reasonably often.[^4] How often an object appears depends on how many parents
it has. The block has many; the six-cell clock has few and is rarer in soup than the much
larger pulsar or pentadecathlon.[^5] Okrasinski's search of 4.7 × 10^11 objects turned up only
the glider, LWSS, MWSS and HWSS as spaceships. The far larger asymmetric-soup census of
[[catagolue](pages/catagolue.md)] has also produced the sidecar, the loafer, the Schick
engine and the Coe ship, and symmetric soups have produced rarer ones such as the c/10
copperhead.[^6][^7] The only infinitely growing patterns seen to arise from random fills are switch-engine
puffers ([[switch-engine](pages/switch-engine.md)]).[^8]

**Early method.** Early Life players, with little computing power and no ready-made
software, evolved patterns by hand on graph paper, checkerboards or Go boards. They were
also more systematic: instead of random soups, they studied every small starting
configuration, which is where the T-tetromino, [[r-pentomino](pages/r-pentomino.md)],
B-heptomino and stairstep hexomino come from.[^9]

**Automated searches.**[^10]

| Search | Years | Ash objects | Notes |
|---|---|---|---|
| Flammenkamp | 1994 | 5.0 × 10^9 | first automated soup search; 48 distinct oscillators |
| Flammenkamp | 2004 | 5.0 × 10^10 | over 3,500 still lifes, over 80 oscillators |
| Okrasinski (screensaver) | 2003-2008 | 4.7 × 10^11 | over 8,000 still lifes, about 180 oscillators; also found methuselahs |
| TOLLCASS (Johnston) | 2009-2011 | 1.7 × 10^11 | distributed online search; several Life-like rules |
| [[apgsearch](pages/apgsearch.md)] (Goucher) | 2014-present | over 7 × 10^15 | distributed, very fast; feeds the [[catagolue](pages/catagolue.md)] census; 20,000+ rules[^11] |

apgsearch ("ash pattern generator") is the current state of the art. It has catalogued
about 10,000 times as many objects as all earlier searches combined, and it is available
at catagolue.hatsya.com/apgsearch.[^12] Its totals grow daily; the asymmetric Life census
alone counts about 5.9 × 10^14 soups.[^11] Beyond counting, the census works as Life's
natural history: which objects arise on their own, how rare they are, and which only
symmetric soups can reach.

## Appearances in Sources

- [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] - §1.1 random fumbling; §1.8 history of soup searches, Table 1.2
- [[lifewiki-catagolue](pages/lifewiki-catagolue.md)] - the census's scale and its natural spaceships
- [[lifewiki-apgsearch](pages/lifewiki-apgsearch.md)] - the search program

## Related Concepts

- [[apgsearch](pages/apgsearch.md)], [[catagolue](pages/catagolue.md)] - the program and census that do soup search at scale today
- [[life-like-cellular-automaton](pages/life-like-cellular-automaton.md)] - TOLLCASS and apgsearch cover other rules too
- [[methuselah](pages/methuselah.md)] - found by the same kind of random search
- [[familiar-fours](pages/familiar-fours.md)] - common ash formations
- [[still-life](pages/still-life.md)], [[oscillator](pages/oscillator.md)], [[spaceship](pages/spaceship.md)] - the object classes catalogued

[^1]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.5 - "Random starting configurations like this one are sometimes called soup, and the objects that they leave behind are called ash"; n.3 "The term 'ash' refers to the fact that it is what is left after a pattern stops 'burning'"
[^2]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.5 [synthesis] - three techniques: "a computer program that searches for patterns with particular properties"; "combine different already-known objects"; "put some random garbage on the Life board and evolve it"
[^3]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.6 [synthesis] - "by just changing one cell from alive to dead, we have made a new pattern that takes almost 3 000 generations to stabilize and results in ash that has over 20 times as many live cells"; Fig. 1.5 "over 25 times as long to stabilize"
[^4]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.6-7 [synthesis] - Fig. 1.6 objects that "frequently appear in the ash"; the pulsar "appears rather frequently in random ash for its size"; toad, beacon, clock, pentadecathlon "appear reasonably often"; LWSS common, MWSS and HWSS "slightly more rare"
[^5]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.19 [synthesis] - the block has "numerous parents ..., which is part of the reason why they appear so frequently in the ash of random soups"; the clock "appears in random soups much less frequently than some much larger objects like the period 3 pulsar or the period 15 pentadecathlon"
[^6]: [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] p.111, n.41 - the copperhead "was then found in random ash generated by apgsearch less than a month after its initial discovery"; "The copperhead was found from evolving a random symmetric soup"
[^7]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.28 - Okrasinski's screensaver catalogued over 4.7 × 10^11 ash objects, "but still the only spaceships that turned up were the four that we have already seen (the glider, LWSS, MWSS, and HWSS)"; [[lifewiki-catagolue](pages/lifewiki-catagolue.md)] L124-128 [synthesis] - B3/S23/C1 spaceships include the sidecar, "1 period 7 spaceship (the loafer)", "1 period 12 spaceship (the Schick engine)", "1 period 16 spaceship (the Coe ship)"
[^8]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.15 - "puffers based on switch engines are the only infinitely growing patterns that have ever formed as a result of randomly filling some portion of the Life plane and then evolving it"
[^9]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.26-27 [synthesis] - "there was no pre-made Life simulation software"; patterns "evolved by hand using graph paper, checkers, or the board and stones from the game Go"; "early Lifers investigated the evolution of all possible small starting configurations"
[^10]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.27-28, Table 1.2 [synthesis] - Flammenkamp 1994 (48 distinct oscillators) and 2004 (over 3 500 still lifes, over 80 oscillators); Okrasinski's screensaver (over 8 000 still lifes, about 180 oscillators, methuselahs); TOLLCASS by Nathaniel Johnston 2009; apgsearch by Adam P. Goucher 2014; ash-object counts per Table 1.2
[^11]: [[lifewiki-catagolue](pages/lifewiki-catagolue.md)] L32,L434 - "20,644 rules have been investigated"; "at least 587,443,221,069,880 soups have been investigated by the census's participants, yielding a total of at least 7,315,050,809,532,447 objects of 553,848 distinct types"
[^12]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.28 [synthesis] - apgsearch "is the current state-of-the-art when it comes to soup searching"; "it has cataloged about 10 000 times as many ash objects as all of the previous searches combined"; n.43 "ash pattern generator"; n.44 catagolue.hatsya.com/apgsearch
