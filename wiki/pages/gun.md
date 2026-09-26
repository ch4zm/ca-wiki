---
title: Gun
category: Patterns
summary: A Life pattern class - an oscillating mechanism that emits spaceships forever; glider guns exist for every period from 14 (the minimum stream spacing), as pseudo-period guns built by glider insertion or true-period guns built from spark collisions, hasslers and Herschel tracks; variants fire on shifting lanes (slide guns, armless guns) or ever more slowly (sqrtguns, caber tossers)
tags: [pattern-class, life, gun, glider-stream, true-period, pseudo-period, slide-gun, armless-construction, sqrtgun]
sources: [cgol-ch8-guns-and-glider-streams, cgol-ch1-early-life]
created: 2026-09-25
updated: 2026-09-26
---

# Gun

## Description

A *glider gun* is a pattern that creates an endless stream of
[[glider](pages/glider.md)]s. The first, the period-30
[[gosper-glider-gun](pages/gosper-glider-gun.md)], was also the first pattern found that
grows without limit.[^1] Guns for other spaceships, such as the LWSS, MWSS and HWSS
(lightweight, middleweight and heavyweight spaceships,
[[light-middle-heavyweight-spaceships](pages/light-middle-heavyweight-spaceships.md)])
and the [[cordership](pages/cordership.md)], are built from the same parts.[^2]

**Period of a stream.** Consecutive gliders on one lane can be no closer than 14
generations, so period 14 is the tightest glider stream. The tightest LWSS, MWSS and HWSS
streams have periods 14, 16 and 18.[^3]

**Changing a gun's period.**[^4]
- **Deletion** raises the period: two streams collide to make a block that eats the next
  glider (doubling), or to make blocks and a blinker (tripling).
- **Filters** also raise it: an oscillator's spark deletes every second or third glider of
  a stream whose period shares a factor with its own.
- **Insertion** lowers it: spaceships collide to make a glider that fills a gap. The
  cleanest reaction turns an LWSS into a glider with two sparks and works at period 14.

Starting from a gun whose period is a multiple of the target and filling its gaps gives
a glider gun of every period 14 or more. Dietrich Leithner built the first period-14 gun
this way in November 1994.[^5]

**True-period and pseudo-period guns.** A *pseudo-period* gun oscillates at a multiple of
its output period; insertion generally produces one. A *true-period* gun oscillates at the
same period as its stream; deletion and filtering keep a gun true-period.[^6] True-period
guns need a new glider-making mechanism for each period:[^7]
- **Spark collisions.** Sparks from two oscillators meet and form a glider. Examples are
  the Gosper gun (period 30), the twin bees gun (46), and two copies of Jason's p22 (22).
- **Hasslers.** An oscillator ([[hassler](pages/hassler.md)]) hassles a T-tetromino,
  pi-heptomino, B-heptomino or pre-honey farm chaotically enough that a conduit can pull a
  glider out of the debris. A period-59 pi-heptomino reaction takes in 5 gliders and gives
  out 6, and feeding 5 of them back makes a gun.
- **Herschel tracks.** A [[herschel](pages/herschel.md)] track gives guns of any period 62
  or more. Tracks with custom oscillators that eat each Herschel's first natural glider
  early are called *quetzals*; they reach periods in the 50s.

True-period glider guns are known for every period 14 or more except 17, 19, 23, 26, 29, 31, 38 and 39.[^8]

**Firing on many lanes.**[^9]
- **Slide guns.** A few guns fire gliders that move a block (an *elbow*) and reflect a
  glider off it without destroying it. The block drifts, so each output glider appears on
  a new lane. Leithner built the first in July 1994.
- **Armless guns.** Two loop guns fire antiparallel gliders that collide into a
  perpendicular glider. The output lane is set by the spacing of gliders in the loops, so
  one pair of loops can encode a whole [[slow-salvo](pages/slow-salvo.md)] synthesis
  (*armless construction*). Changing only the loop contents changes what the gun builds.

**Slow and irregular guns.** Guns can fire more and more slowly, which gives patterns
whose population grows slower than linearly.[^10]
- A *sqrtgun* pushes a block further away each cycle, delaying each glider by 80 more
  generations, so its population grows like the square root of time. Dean Hickerson
  built the first around 1991.
- A [[caber-tosser](pages/caber-tosser.md)] bounces a glider off a receding Cordership and
  grows like log(t).
- Filters attached to a gun's output slow it further: quadratic and exponential filters
  (Gabriel Nivasch, 2006) and the recursive filter (Alexey Nigin, 2015), which gives
  growth like the iterated logarithm log*(t).

## Appearances in Sources

- [[cgol-ch8-guns-and-glider-streams](pages/cgol-ch8-guns-and-glider-streams.md)] - the whole chapter: deletion, filters, insertion, true-period guns, slide, armless and slow guns
- [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] - §1.3: the Gosper glider gun and the term "glider gun"

## Related Concepts

- [[gosper-glider-gun](pages/gosper-glider-gun.md)] - the first gun
- [[twin-bees](pages/twin-bees.md)] - the period-46 gun
- [[herschel](pages/herschel.md)] - Herschel tracks give guns of large period
- [[hassler](pages/hassler.md)] - basis of many true-period guns
- [[sparker](pages/sparker.md)] - sparks used as filters and in insertion
- [[inverter](pages/inverter.md)] - guns of period 120n and gun-against-stream logic
- [[caber-tosser](pages/caber-tosser.md)] - a gun with logarithmic growth
- [[puffer](pages/puffer.md)] - moving guns (rakes)
- [[game-of-life](pages/game-of-life.md)] - the rule where the Gosper gun gave the first unbounded growth
- [[oscillator](pages/oscillator.md)] - guns are oscillators that also emit moving objects
- [[conduit](pages/conduit.md)] - Herschel conduits that release gliders, each of which can be made into a gun
- [[period-multiplier](pages/period-multiplier.md)] - multiplies a gun's period, up to 2^100 in a 240 × 260 box
- [[primer](pages/primer.md)] - a gun built from inline-inverter guns whose stream marks the primes
- [[breeder](pages/breeder.md)] - builds guns
- [[catagolue](pages/catagolue.md)] - keeps a database of true-period and pseudo-period glider guns
- [[wireworld](pages/wireworld.md)] - clocks play the part of guns in wire circuits

[^1]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.11 - "Patterns that create glider streams are called glider guns, and this particular one is called the Gosper glider gun"; "This is the first pattern that we have seen that grows indefinitely (and indeed, it was the first such pattern ever to be discovered)"
[^2]: [[cgol-ch8-guns-and-glider-streams](pages/cgol-ch8-guns-and-glider-streams.md)] pp.228-230,251-253 [synthesis] - LWSS guns from a Herschel-to-LWSS conduit (Fig. 8.13); LWSS-to-MWSS and MWSS-to-HWSS upgrades (Fig. 8.16); 2-engine Cordership guns (Figs. 8.45, 8.46)
[^3]: [[cgol-ch8-guns-and-glider-streams](pages/cgol-ch8-guns-and-glider-streams.md)] pp.226,228 - "period 14, which is the smallest possible"; "the minimum possible periods of LWSS, MWSS, and HWSS streams are 14, 16, and 18, respectively"
[^4]: [[cgol-ch8-guns-and-glider-streams](pages/cgol-ch8-guns-and-glider-streams.md)] §8.1-8.2, pp.221-227 [synthesis] - block-forming doubling collision, block-and-blinker tripling collision; filters whose period "shares some factor (greater than one) with the period of the glider stream"; glider insertion to "thicken glider streams"; Fig. 8.10(a) LWSS-to-glider via two sparks fills "gaps in p14 glider streams"
[^5]: [[cgol-ch8-guns-and-glider-streams](pages/cgol-ch8-guns-and-glider-streams.md)] p.230 - "we just create a gun whose period is a suitably large multiple of the period that we actually want, and then repeatedly use multiple copies of this gun and the glider insertion reaction to fill in the gaps"; n.10 "The first period 14 glider gun was built by Dietrich Leithner in November 1994"
[^6]: [[cgol-ch8-guns-and-glider-streams](pages/cgol-ch8-guns-and-glider-streams.md)] pp.231,233 [synthesis] - pseudo-period guns "oscillate at a higher period than (and necessarily a multiple of) the stream that they produce"; true-period guns "actually oscillate at the same period as their stream"; insertion "results in a pseudo-period gun, but using filters or the glider deletion methods ... results in a true-period gun"
[^7]: [[cgol-ch8-guns-and-glider-streams](pages/cgol-ch8-guns-and-glider-streams.md)] §8.5, pp.233-244 [synthesis] - "Most of the simplest true-period glider guns work simply by having sparks from different oscillators collide"; Fig. 8.19(a) two copies of Jason's p22; hasslers where "a glider can be extracted from the debris"; Fig. 8.27 "a period 59 reaction that takes in 5 gliders ... and spits out 6"; n.14 Herschel tracks give "true-period guns of large period (period 62 and larger)"; a Herschel-track gun with custom components "is called a quetzalcoatlus (or simply quetzal for short)"
[^8]: https://conwaylife.com/wiki/Gun#True-period_guns - "True period n guns are known to exist for all possible periods except for 17, 19, 23, 26, 29, 31, 38, and 39" (read as a web-search excerpt)
[^9]: [[cgol-ch8-guns-and-glider-streams](pages/cgol-ch8-guns-and-glider-streams.md)] §8.6-8.7, pp.244-253 [synthesis] - elbow; block moved and glider reflected, "We call the resulting gun a slide gun"; n.33 first slide gun by Dietrich Leithner in July 1994; loop guns firing antiparallel gliders, "armless construction"; "All that we would have to change is the sequences of gliders running through the glider loops"
[^10]: [[cgol-ch8-guns-and-glider-streams](pages/cgol-ch8-guns-and-glider-streams.md)] §8.8, §8.9, pp.254-264 [synthesis] - sqrtgun "emits each glider 80 generations more slowly than its previous one", population Θ(√t), n.36 first by Dean Hickerson around 1991; caber tosser Θ(log(t)); recursive filter by Alexey Nigin in July 2015 giving Θ(log*(t)); quadratic and exponential filters by Gabriel Nivasch in June 2006
