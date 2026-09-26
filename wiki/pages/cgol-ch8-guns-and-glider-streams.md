---
title: "Guns and Glider Streams (Johnston and Greene, Ch. 8)"
category: Sources
summary: Chapter 8 of Conway's Game of Life - Mathematics and Construction - thinning glider streams by deletion and filters, thickening them by insertion down to the minimum period 14, xWSS streams, true-period versus pseudo-period guns (spark collisions, hasslers, quetzals), slide guns and armless guns that fire on any lane, and slow guns (sqrtguns, caber tossers, recursive filters) with growth as slow as log*(t)
tags: [source, chapter, life, gun, glider-stream, true-period, pseudo-period, slide-gun, armless-construction, caber-tosser]
sources: [cgol-ch8-guns-and-glider-streams]
created: 2026-09-25
updated: 2026-09-25
---

# Guns and Glider Streams (Johnston and Greene, Ch. 8)

**Source:** raw/johnston-greene-2022-conways-game-of-life.pdf, Chapter 8, printed pp. 221-270 (PDF pp. 235-284). Part of [[conways-game-of-life-mathematics-and-construction](pages/conways-game-of-life-mathematics-and-construction.md)].
**Date ingested:** 2026-09-25
**Type:** book chapter

## Summary

Earlier chapters give glider streams of only a few spacings: period 30 from the
[[gosper-glider-gun](pages/gosper-glider-gun.md)], period 46 from the
[[twin-bees](pages/twin-bees.md)] gun, and period 62 and up from
[[herschel](pages/herschel.md)] tracks. This chapter builds a [[gun](pages/gun.md)]
for any spacing and almost any position.[^1]

**Changing a stream's period.**
- **Deletion.** Two streams of period 29 or more fired at each other in the right phase
  make a block, which kills the next glider of one stream. One stream vanishes and the
  other loses every second glider, so two Gosper guns give a period-60 gun.[^2] A similar
  collision triples even-period streams of period 34 or more, and others multiply by 5 or
  7.[^3]
- **Filters.** A *filter* is an oscillator whose spark deletes some gliders of a passing
  stream: a blocker's dot spark doubles a stream of period 8n + 4, Rich's p16 one of
  period 16n + 8. The filter's period generally has to share a factor with the stream's,
  or some spark-glider phase eventually causes an explosion.[^4]
- **Insertion.** Colliding spaceships to make one glider that fits a gap lowers a
  stream's period. A 3-glider *tee* or an LWSS (lightweight spaceship) hitting a glider
  turns a glider through 90 degrees, but their debris limits them to periods of about 22
  or more.[^5] Dietrich Leithner's reaction (by 1994) turns an LWSS into a glider with two
  sparks so cleanly that it fills gaps in period-14 streams, the tightest possible.[^6]

**Guns of every period from 14.** Build a gun whose period is a multiple of the target,
then fill its gaps by insertion. Seven Gosper guns give a period-15 gun; a period-84 base
with four insertion mechanisms gives period 14. Leithner built the first period-14 gun
this way in November 1994.[^7] Spaceship streams work the same way: sparks filter LWSS
streams, a 10-glider collision (Chris Cain, 2018) inserts an LWSS into a stream of period
36 to give period 18, and spaceships fired at an LWSS or MWSS (middleweight spaceship)
"upgrade" it to the next size. The minimum LWSS, MWSS and HWSS (heavyweight spaceship)
stream periods are 14, 16 and 18.[^8]

**True-period guns.** Guns made by insertion oscillate at a multiple of their output
period; these are *pseudo-period* guns. A *true-period* gun oscillates at its stream's
period. Deletion and filtering keep a gun true-period; insertion does not.[^9] True-period
guns need new glider-making mechanisms, of three main kinds:[^10]
- **Spark collisions**: two sparky oscillators whose sparks meet to form a glider
  (periods 22, 30, 33, 36, 45, 46).
- **Hasslers**: an oscillator that hassles a T-tetromino, pi-heptomino, B-heptomino or
  pre-honey farm chaotically enough that a glider can be pulled from the debris
  ([[hassler](pages/hassler.md)]).
- **Quetzals**: short Herschel tracks, with oscillators that eat each Herschel's first
  natural glider fast enough to let Herschels follow each other every 52 to 57
  generations.

**Any lane.** An *elbow* is a small still life, usually a block, that gliders can move
anywhere and that also turns gliders. Gliders that move a block and reflect a glider off
it without destroying it make a *slide gun*, whose output lane shifts every cycle.[^11]
*Armless guns* instead collide antiparallel gliders from two loop guns to make a
perpendicular glider on any chosen lane, which lets one pair of loops encode a whole
[[slow-salvo](pages/slow-salvo.md)] synthesis. Two such guns fire 2-engine
[[cordership](pages/cordership.md)]s.[^12]

**Slow guns.** Guns can also fire more and more slowly. A *sqrtgun* pushes a block
further each cycle, so its population grows like the square root of time. A
[[caber-tosser](pages/caber-tosser.md)] bounces a glider off a receding Cordership and
grows like log(t). Filters attached to a gun's output slow it further, down to
log*(t) and beyond.[^13] A caber tosser attached to the [[primer](pages/primer.md)]
gives a pattern whose unbounded growth depends on whether a sixth Fermat prime
exists.[^14]

## Key Takeaways

- Glider streams can be thinned and thickened freely, which gives guns of every period
  from 14, the minimum.[^6][^7]
- Pseudo-period guns come from insertion; true-period guns need glider-making
  mechanisms built for that period.[^9][^10]
- Moving a block, or colliding gliders from two loops, puts output gliders on any lane
  without a fixed gun there.[^11][^12]
- There is no slowest-growing pattern: a filter can always be added to slow a gun
  further.[^15]

## Entities & Concepts

- [[gun](pages/gun.md)], [[caber-tosser](pages/caber-tosser.md)]
- [[gosper-glider-gun](pages/gosper-glider-gun.md)], [[twin-bees](pages/twin-bees.md)], [[herschel](pages/herschel.md)], [[hassler](pages/hassler.md)], [[sparker](pages/sparker.md)], [[reflector](pages/reflector.md)]
- [[light-middle-heavyweight-spaceships](pages/light-middle-heavyweight-spaceships.md)], [[cordership](pages/cordership.md)], [[slow-salvo](pages/slow-salvo.md)], [[primer](pages/primer.md)], [[inverter](pages/inverter.md)], [[regulator](pages/regulator.md)]

## Relation to Other Wiki Pages

The chapter extends the period-30 and period-46 circuitry of
[[cgol-ch6-periodic-circuitry](pages/cgol-ch6-periodic-circuitry.md)]: its caber tosser's
blocking trick is an [[inverter](pages/inverter.md)], and the primer becomes a Fermat
prime detector.[^13][^14] Armless construction implements the slow salvos of
[[cgol-ch5-glider-synthesis](pages/cgol-ch5-glider-synthesis.md)], and the authors say
the idea of storing a recipe in glider sequences carries into universal
construction.[^16] The [[reverse-caber-tosser](pages/reverse-caber-tosser.md)] runs the
caber tosser's idea backward.

[^1]: [[cgol-ch8-guns-and-glider-streams](pages/cgol-ch8-guns-and-glider-streams.md)] p.221 - "so far we have only seen how to create glider streams with a few different spacings: the period 30 stream produced by the Gosper glider gun ..., the period 46 stream produced by the twin bees gun ..., and the streams of period 62 and higher than we can construct via the Herschel tracks ... In this chapter, we look at how to construct glider guns that create gliders of any spacing and almost any positioning that we like"
[^2]: [[cgol-ch8-guns-and-glider-streams](pages/cgol-ch8-guns-and-glider-streams.md)] pp.221-222 [synthesis] - two streams "synthesize a block, and that block then destroys the next glider in one of the streams"; works for period 29 or more; Fig. 8.2(a) "two period 30 Gosper glider guns creating a period 60 gun"
[^3]: [[cgol-ch8-guns-and-glider-streams](pages/cgol-ch8-guns-and-glider-streams.md)] pp.222-224 [synthesis] - Fig. 8.3 tripling for "two even-period glider streams of period at least 34"; Fig. 8.4 period 138 gun from two twin bees guns; Fig. 8.5 thinning by a factor of 5 (period at least 108) or 7 (period at least 46)
[^4]: [[cgol-ch8-guns-and-glider-streams](pages/cgol-ch8-guns-and-glider-streams.md)] pp.224-225 [synthesis] - "a filter, which is an oscillator that pulsates or gives off a spark in such a way as to destroy some of the gliders in the stream, but not all of them"; blocker for period 8n + 4, Rich's p16 for 16n + 8, Jason's p22 for 22n + 11; the filter period generally "shares some factor (greater than one) with the period of the glider stream", otherwise some combinations "cause a chaotic explosion"
[^5]: [[cgol-ch8-guns-and-glider-streams](pages/cgol-ch8-guns-and-glider-streams.md)] pp.225-226 [synthesis] - tees give "an output glider that is perpendicular to all 3 input gliders"; LWSS-glider collision rotates a glider by 90 degrees; Fig. 8.9 period 23 gun from period 46 guns; tee limited to period 25 or more, LWSS-glider collision to "periods of at least 22"
[^6]: [[cgol-ch8-guns-and-glider-streams](pages/cgol-ch8-guns-and-glider-streams.md)] pp.226-227 [synthesis] - "all the way down to period 14, which is the smallest possible"; Fig. 8.10(a) dot spark then domino spark transform an LWSS into a glider "so cleanly that it can be used to fill in gaps in p14 glider streams"; n.7 "found by Dietrich Leithner no later than 1994"
[^7]: [[cgol-ch8-guns-and-glider-streams](pages/cgol-ch8-guns-and-glider-streams.md)] pp.226,230-232 [synthesis] - p15 gun from 7 Gosper guns (Fig. 8.11); "construct glider guns of all periods 14 and greater"; Fig. 8.18 p14 gun from p84 components with four insertion mechanisms; n.10 "The first period 14 glider gun was built by Dietrich Leithner in November 1994"
[^8]: [[cgol-ch8-guns-and-glider-streams](pages/cgol-ch8-guns-and-glider-streams.md)] pp.228-230 [synthesis] - sparks "filter (i.e., thin out) LWSS streams" (Fig. 8.14); "the minimum possible periods of LWSS, MWSS, and HWSS streams are 14, 16, and 18"; Fig. 8.15 10-glider LWSS insertion "Found by Chris Cain in October 2018"; Fig. 8.16 upgrading LWSS to MWSS and MWSS to HWSS
[^9]: [[cgol-ch8-guns-and-glider-streams](pages/cgol-ch8-guns-and-glider-streams.md)] pp.231,233 [synthesis] - guns that "oscillate at a higher period than (and necessarily a multiple of) the stream that they produce ... are called pseudo-period guns"; guns "that actually oscillate at the same period as their stream ... We call such guns true-period guns"; "using glider insertion ... results in a pseudo-period gun, but using filters or the glider deletion methods ... results in a true-period gun"
[^10]: [[cgol-ch8-guns-and-glider-streams](pages/cgol-ch8-guns-and-glider-streams.md)] §8.5.1-8.5.3, pp.233-244 [synthesis] - spark-collision guns of periods 22, 30, 33, 36, 45, 46; hasslers of a T-tetromino, pi-heptomino, B-heptomino, or pre-honey farm where "the hassling reaction has to be chaotic enough that a glider can be extracted"; quetzals built on Fx77 tracks with fast eaters giving repeat times of 52, 54, 55, 56, 57
[^11]: [[cgol-ch8-guns-and-glider-streams](pages/cgol-ch8-guns-and-glider-streams.md)] §8.6, pp.244-245 [synthesis] - "an elbow, which is a small and simple still life (typically a block) or constellation ... that can be moved to any point in the Life plane by gliders, and which can also turn gliders"; reflections where "the block is not destroyed"; "We call the resulting gun a slide gun"; n.33 first slide gun by Dietrich Leithner in July 1994
[^12]: [[cgol-ch8-guns-and-glider-streams](pages/cgol-ch8-guns-and-glider-streams.md)] §8.7, pp.247-253 [synthesis] - "collide antiparallel gliders with each other so as to create a perpendicular glider"; monochrome tee-based and multicolor armless guns; "This method of implementing a slow salvo synthesis is called armless construction"; Figs. 8.45 and 8.46 two 2-engine Cordership guns
[^13]: [[cgol-ch8-guns-and-glider-streams](pages/cgol-ch8-guns-and-glider-streams.md)] §8.8.1-8.8.3, pp.254-258 [synthesis] - sqrtgun "population in generation t is Θ(√t)"; caber tosser "growth rate is logarithmic", its returning glider "blocks the blocking stream as in an inverter"; recursive filter gives "Θ(log*(t))", and filters in series give Θ(log**(t))
[^14]: [[cgol-ch8-guns-and-glider-streams](pages/cgol-ch8-guns-and-glider-streams.md)] §8.8.4, pp.258-259 [synthesis] - caber tosser aimed at the primer's LWSSes at positions 2^n + 1; Fig. 8.51 "A Fermat prime calculator that self-destructs and has bounded population if a sixth Fermat prime exists, but grows without bound otherwise"
[^15]: [[cgol-ch8-guns-and-glider-streams](pages/cgol-ch8-guns-and-glider-streams.md)] p.255 - "are there patterns that grow even slower than logarithmically, and is there an asymptotically slowest-growing pattern? The answers to these questions are 'yes' and 'no', respectively, and they both follow from the existence of devices that can be attached to the output of a glider gun so as to create an asymptotically slower glider gun"
[^16]: [[cgol-ch8-guns-and-glider-streams](pages/cgol-ch8-guns-and-glider-streams.md)] pp.250,253 [synthesis] - armless guns "shine" for slow salvos since they "can reach across any number of lanes"; "This trick of encoding patterns in sequences of gliders, rather than in the positions of various complicated guns, will be extremely useful once we investigate universal construction in Chapter 11"
