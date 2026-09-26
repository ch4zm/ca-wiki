---
title: "Stable Circuitry (Johnston and Greene, Ch. 7)"
category: Sources
summary: Chapter 7 of Conway's Game of Life - Mathematics and Construction - circuitry built only from still lifes - named Herschel conduits and converters, the syringe that turns a glider into a Herschel, stable reflectors, rephasers and glider-to-object circuits, semi-Snark period multipliers giving guns of any period in a box of side about the square root of log p, factories, highway robbers and a stable MWSS Heisenburp
tags: [source, chapter, life, circuitry, conduit, herschel, syringe, period-multiplier, factory, heisenburp, reflector]
sources: [cgol-ch7-stable-circuitry]
created: 2026-09-25
updated: 2026-09-25
---

# Stable Circuitry (Johnston and Greene, Ch. 7)

**Source:** raw/johnston-greene-2022-conways-game-of-life.pdf, Chapter 7, printed pp. 183-220 (PDF pp. 197-234). Part of [[conways-game-of-life-mathematics-and-construction](pages/conways-game-of-life-mathematics-and-construction.md)].
**Date ingested:** 2026-09-25
**Type:** book chapter

## Summary

The previous chapter moved gliders with oscillators. This one does the same jobs with
still lifes only, which frees the circuitry from any fixed period. Still lifes give off
no sparks for a glider to use, so stable circuitry mostly works on easier objects such as
the [[herschel](pages/herschel.md)] and converts between object types.[^1]

The chapter builds a catalogue of [[conduit](pages/conduit.md)]s:
- Herschel-to-Herschel conduits named by turn and timing (R64, Fx77, L112, L156 and
  others), with variants for tight spaces.[^2]
- Herschel-to-glider converters, including edge shooters that place gliders close to
  other streams.[^3]
- The *syringe*, a small, fast glider-to-Herschel conduit (Tanner Jacobi, March 2015).[^4]
- Converters between gliders, spaceships, the Herschel, the B-heptomino, the R-pentomino
  and the pi-heptomino, named by a letter code.[^5]

Chaining these gives stable [[reflector](pages/reflector.md)]s, glider duplicators and a
table of *rephasers* that set a glider's colour and timing mod 8. With those, one input
glider can be turned into any object that has a glider synthesis. The chapter builds a
glider-to-LWSS circuit and a glider-to-2-engine-[[cordership](pages/cordership.md)]
circuit this way.[^6]

A [[period-multiplier](pages/period-multiplier.md)] emits one signal for every several
it receives. Chains of semi-Snarks, which pass every second glider, give guns of any
large period in a bounding box whose side grows like the square root of log p. The
chapter builds a gun of prime period 3,413,277,319 as an example.[^7]

*Factories* turn a moving signal into a still life or oscillator. They give logic
circuits, a *highway robber* that steals gliders from one lane without touching the
next, and a stable [[heisenburp](pages/heisenburp.md)] for the middleweight spaceship.[^8]
The historical notes cover the circuitry the syringe replaced: the Callahan G-to-H, the
Silver reflector and Herschel transceivers.[^9]

## Key Takeaways

- Stable circuitry works at any period; its cost is that still lifes offer no sparks.[^1]
- Converting a Herschel to a glider is easy, since the Herschel emits one after 21
  generations. The reverse is hard, and the syringe made it cheap.[^3][^4]
- One glider can be turned into many and rephased, so a single signal can trigger any
  glider synthesis.[^6]
- Period p guns need a box of side at least about the square root of log2(p), and period
  multipliers show that bound is tight up to a constant.[^7]
- A detector made only of still lifes can sense an MWSS without touching it.[^8]

## Entities & Concepts

- [[conduit](pages/conduit.md)], [[period-multiplier](pages/period-multiplier.md)], [[herschel](pages/herschel.md)], [[reflector](pages/reflector.md)], [[heisenburp](pages/heisenburp.md)]
- [[eater](pages/eater.md)], [[glider](pages/glider.md)], [[r-pentomino](pages/r-pentomino.md)], [[cordership](pages/cordership.md)], [[light-middle-heavyweight-spaceships](pages/light-middle-heavyweight-spaceships.md)], [[queen-bee](pages/queen-bee.md)], [[object-synthesis](pages/object-synthesis.md)], [[slow-salvo](pages/slow-salvo.md)]

## Relation to Other Wiki Pages

The chapter extends the Herschel tracks of
[[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] and reuses the glider syntheses
and one-time-turner timing method of
[[cgol-ch5-glider-synthesis](pages/cgol-ch5-glider-synthesis.md)]. Its bouncer comparison
and periodic Heisenburps come from
[[cgol-ch6-periodic-circuitry](pages/cgol-ch6-periodic-circuitry.md)].[^6][^8][^10]
Spartan conduits, those made of easy-to-synthesize pieces, are the main parts of the
book's later mega-constructions.[^4]

[^1]: [[cgol-ch7-stable-circuitry](pages/cgol-ch7-stable-circuitry.md)] p.183 - "which has the advantage of not restricting the period of the glider streams that can make use of the circuitry"; "stable objects can not provide any sparks for gliders to make use of. For this reason, stable circuitry typically focuses not just on manipulating gliders, but also on manipulating other (easier to manipulate) objects like Herschels"
[^2]: [[cgol-ch7-stable-circuitry](pages/cgol-ch7-stable-circuitry.md)] §7.1, pp.183-187 [synthesis] - p67 gun from two L112 and two L156; naming by orientation prefix and generation count; Table 7.1 of sixteen small fast conduits with repeat times; Fx77 variants a-e for tight squeezes
[^3]: [[cgol-ch7-stable-circuitry](pages/cgol-ch7-stable-circuitry.md)] §7.2, pp.188-190 [synthesis] - "Converting a Herschel into a glider is straightforward since it emits a natural glider after 21 generations anyway"; Figure 7.5 one-, two- and three-glider converters; <direction><lane>T<timing> names; Figure 7.7 edge shooters
[^4]: [[cgol-ch7-stable-circuitry](pages/cgol-ch7-stable-circuitry.md)] §7.3, p.190 [synthesis] - "the reverse conversion of a glider into a Herschel is much trickier"; the syringe, standard version with repeat time 78 taking 84 generations; n.10 "found in March 2015 by Tanner Jacobi, using the same 'Bellman' program that was used to find the Snark"; Spartan conduits "will be the main type of conduit used throughout most of the mega-constructions that we will see in Chapters 9-12"
[^5]: [[cgol-ch7-stable-circuitry](pages/cgol-ch7-stable-circuitry.md)] §7.7, pp.202-205 [synthesis] - letter codes G, L, M, H, B, R, P (Figure 7.24); <input code><orientation><timing><output code> names; Table 7.3 of converters
[^6]: [[cgol-ch7-stable-circuitry](pages/cgol-ch7-stable-circuitry.md)] §§7.4-7.5, pp.190-197 [synthesis] - syringe-based colour-changing reflector (repeat time 78) and Bandersnatch plus Snark (repeat time 70); duplicators and triplers; Table 7.2 rephasers "compare with Table 5.5, which did the same thing via one-time-turners"; glider-to-LWSS circuit (Figure 7.12); glider-to-2-engine-Cordership circuit (Figure 7.16)
[^7]: [[cgol-ch7-stable-circuitry](pages/cgol-ch7-stable-circuitry.md)] §7.6, pp.196-202 [synthesis] - counting bound "there cannot exist a period p gun inside a box of size less than √log2(p) × √log2(p)"; "this lower bound is 'essentially' tight"; semi-Snarks; binary counting circuits; period 3,413,277,319 gun (Figure 7.23)
[^8]: [[cgol-ch7-stable-circuitry](pages/cgol-ch7-stable-circuitry.md)] §7.8, pp.205-210 [synthesis] - factory definition; beehive-based logic test; Herschel-to-block factories and keepers; §7.8.1 highway robber (Chris Cain, March 2015); §7.8.2 stable MWSS Heisenburp (Figure 7.36, "Entity Valkyrie", June 2020, based on work by Martin Grant); "recall that we saw some periodic Heisenburps in Section 6.3.3"
[^9]: [[cgol-ch7-stable-circuitry](pages/cgol-ch7-stable-circuitry.md)] §7.9, pp.211-214 [synthesis] - Callahan G-to-H (repeat time 575); Silver reflector as the same beehive reaction plus Fx77, L112 and NW31 (repeat time 497); Herschel transceivers from 1996-1997 "made almost completely obsolete by the discovery of the syringe"
[^10]: [[cgol-ch7-stable-circuitry](pages/cgol-ch7-stable-circuitry.md)] pp.183,191 [synthesis] - "just as we did in Section 3.6"; the syringe reflector has repeat time 78, "the smaller and faster bouncer reflectors from Section 6.4 are still more useful in many situations"
