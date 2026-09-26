---
title: Conduit
category: Patterns
summary: A stable Life pattern that takes in one active object, such as a Herschel or glider, and outputs another elsewhere; Herschel conduits are named by turn and timing (R64, Fx77, L112), converters by letter codes (BLx19R, RF28B), and the syringe turns a glider into a Herschel so conduits chain into reflectors, duplicators, rephasers and factories
tags: [pattern-class, life, conduit, herschel, syringe, catalyst, converter, factory, stable-circuitry]
sources: [cgol-ch7-stable-circuitry]
created: 2026-09-25
updated: 2026-09-26
---

# Conduit

## Description

A *conduit* is a stable pattern that an active object passes through: a
[[herschel](pages/herschel.md)] or [[glider](pages/glider.md)] goes in, and an object
comes out at a new place, orientation and time. Stable circuitry favours Herschels
because a still life offers no sparks for a glider, while a Herschel is easy to steer.[^1]

**Catalysts.** The still lifes in a conduit are *catalysts*: a passing reaction alters
them for a while but they recover with no permanent damage. The reaction is often an
unnamed chaotic mess that the catalyst makes evolve differently. Many catalysts are
[[eater](pages/eater.md)]s (eater 1 is very common), but not all. A *transparent
catalyst*, usually a block or beehive, is destroyed completely and then rebuilt in the
same spot. It lets a reaction pass "through" its location.[^2]

**Herschel conduits.** A Herschel-to-Herschel conduit is named by the output Herschel's
orientation relative to the input, then the number of generations it takes.[^3]
- The prefix is R (right turn), L (left turn), F (forward) or B (backward), with an x if
  the Herschel is mirrored, giving 8 prefixes. R64 turns right in 64 generations; Fx77
  goes forward, mirrored, in 77.
- More than 100 small Herschel conduits are known. The chapter's Table 7.1 lists sixteen
  small, fast ones with their repeat times, from B60 (repeat time 43) to B245 (278). All
  of them release at least one glider, so each can be made into a gun.
- Richer conduit sets make much smaller tracks. R64 and Fx77 alone need 32 conduits and
  36 Herschels for period 67; two L112s and two L156s make a period 67 gun on a
  536-generation track with 8 Herschels.
- *Variants* are conduits with the same input and output, whatever happens in between.
  The chapter shows five Fx77 variants whose welded eaters save a row or two when the next conduit
  needs its block-destroying eater in a particular position.

**Herschel to glider.** A Herschel emits a glider 21 generations in, so a
Herschel-to-glider converter only has to clean up the rest. Dozens are known. Some emit
two or three gliders, so they also duplicate a signal.[^4] They are named
<direction><lane>T<timing>, such as NE5T-4 or NW31T120. *Edge shooters* release their
glider close to the pattern's edge, so they can place gliders on lanes next to other
streams. NE5T-4 has a *transparent lane* that gliders cross safely, so it can insert
gliders into a passing stream.[^5]

**Glider to Herschel: the syringe.** The reverse conversion is much harder. The *syringe*
(Tanner Jacobi, March 2015, found with the Bellman search program that also found the
Snark) does it in 84 generations with repeat time 78. Its standard form uses a large
welded still life. A larger version made of blocks, eater 1s and an eater 2 takes 250
generations with repeat time 115, but is easier to build.[^6] The syringe still works on
gliders 74 or 75 generations apart, though not 76 or 77, which is called
*overclocking*.[^7]

**Spartan conduits.** A conduit made only of small, easy-to-synthesize still lifes and
period-2 oscillators is *Spartan*. The definition grows as synthesis improves: in 2004 it
meant still lifes of 7 or fewer cells, and it now usually means objects whose
[[slow-salvo](pages/slow-salvo.md)] synthesis the program slsparse can compile.[^8]

**What chains of conduits build.**[^9]
- **Reflectors.** A syringe plus NE5T-4 is a colour-changing stable
  [[reflector](pages/reflector.md)] with repeat time 78. The *Bandersnatch* (Martin Grant
  and "Entity Valkyrie", June 2020) changes a glider's colour without turning it, and with
  a Snark gives a colour-changing reflector with repeat time 70.
- **Duplicators.** A syringe followed by a Herschel-to-3-gliders converter duplicates a
  glider; each Fx77 inserted between them adds one more output glider.
- **Rephasers.** A syringe, optional Herschel conduits and a Herschel-to-glider converter
  set a glider's colour and its timing mod 8 (a table compiled by Simon Ekström, August
  2015). A *trombone slide*, a 180-degree reflection moved along the glider's path, adds
  8 generations per cell moved.
- **Glider-to-object circuits.** Duplicate one glider, reflect and rephase the copies,
  and they perform a glider synthesis ([[object-synthesis](pages/object-synthesis.md)]).
  The chapter builds a glider-to-LWSS circuit and a glider-to-2-engine-Cordership circuit,
  syncing the Cordership's 10 gliders 2 or 3 at a time in layers.

**Converters for other objects.** Conduits also convert between a glider (G), LWSS (L),
MWSS (M), Herschel (H), B-heptomino (B), [[r-pentomino](pages/r-pentomino.md)] (R) and
pi-heptomino (P). Names take the form <input><orientation><timing><output>. For
example, BLx19R turns a B-heptomino into a mirrored, left-turned R-pentomino in 19
generations, and RF28B turns an R-pentomino into a B-heptomino in 28. RF28B is a piece of
the Bx202, L156 and Rx164 Herschel conduits.[^10] The pi-heptomino turner PL8P is the
mechanism inside the period-32 "gourmet" oscillator and Tanner's p46, so those
[[hassler](pages/hassler.md)]s work like Herschel tracks.[^11]

**Factories.** A *factory* is a conduit, or any pattern, that repeatedly makes a still life
or oscillator. The [[queen-bee](pages/queen-bee.md)] is a beehive factory.[^12]
- **Logic tests.** A glider-to-beehive factory makes a beehive only if a signal arrived.
  A later test glider is blocked by the beehive or passes if there is none (Paul
  Callahan, 1996; Tanner Jacobi, 2015). The boat-making *demultiplexer* (Brice Due,
  August 2006) reflects the test glider if the boat is there.
- **Keepers.** Most factories self-destruct if a second input arrives before the product
  is used. A *keeper* rebuilds the same block unchanged, and a related block factory acts
  as a period tripler.
- **Highway robber.** A glider grazing a loaf yields a perpendicular glider. Routing it
  through a Snark, syringe, L112 and Herschel-to-loaf factory rebuilds the loaf, which
  gives a *highway robber* (Chris Cain, March 2015). It takes gliders from one lane and
  ignores the next lane over.
- **Stable Heisenburp.** An MWSS spark makes a ship explode into a glider, and a
  Herschel's own evolution leaves a ship. Circuitry linking the two makes a stable
  MWSS-detecting [[heisenburp](pages/heisenburp.md)].

**Before the syringe.** Paul Callahan's reaction (November 1998) turns a glider into a
Herschel plus a junk beehive. Conduits Fx77, L112, Fx77 route the Herschel's first glider
back to clear it, giving the Callahan G-to-H with repeat time 575. The Silver reflector
is the same circuit ending in NW31 instead of Fx77, with repeat time 497.[^13] A
*Herschel transceiver* (Callahan, 1996-1997) sends a Herschel as two gliders on nearby
lanes and rebuilds it far away. Its repeat time is 117, against the syringe's 78.[^14]

## Appearances in Sources

- [[cgol-ch7-stable-circuitry](pages/cgol-ch7-stable-circuitry.md)] - §7.1 Herschel conduits; §§7.2-7.5 converters, syringe, rephasers; §7.7 other converters; §7.8 factories; §7.9 history

## Related Concepts

- [[herschel](pages/herschel.md)] - the object most conduits carry
- [[reflector](pages/reflector.md)] - stable reflectors built from conduits
- [[period-multiplier](pages/period-multiplier.md)] - conduits that pass only some inputs
- [[gun](pages/gun.md)] - Herschel tracks built from conduits give guns of any period 62 or more
- [[inverter](pages/inverter.md)] - glider duplicators by double inversion, the periodic counterpart
- [[eater](pages/eater.md)] - the commonest catalyst
- [[object-synthesis](pages/object-synthesis.md)] - what glider-to-object circuits perform

[^1]: [[cgol-ch7-stable-circuitry](pages/cgol-ch7-stable-circuitry.md)] p.183 - "stable objects can not provide any sparks for gliders to make use of. For this reason, stable circuitry typically focuses not just on manipulating gliders, but also on manipulating other (easier to manipulate) objects like Herschels"
[^2]: [[cgol-ch7-stable-circuitry](pages/cgol-ch7-stable-circuitry.md)] p.185 [synthesis] - "A more general term for the still lifes that make up a conduit is catalyst"; the passing reaction "is simply some unnamed chaotic mess"; "a transparent catalyst. This is a small common object, usually a block or a beehive, that is temporarily destroyed completely by an active reaction, but reappears a few generations later in exactly the same location"
[^3]: [[cgol-ch7-stable-circuitry](pages/cgol-ch7-stable-circuitry.md)] pp.183-187 [synthesis] - "conduits are named according to the orientation of the output Herschel relative to that of the input Herschel, together with the number of generations"; prefixes R, F, L, B and "x" for mirroring, 8 in all; "there are well over 100 known Herschel conduits made up of small still lifes"; Table 7.1 repeat times; "All of these conduits release at least one glider and can thus be used to construct guns"; p67 via 4 R64 + 28 Fx77 with 36 Herschels versus Figure 7.1 with 8 Herschels on 536 generations; variants "take the same input and produce the same output in the same spacetime location"; Fx77 variants a-e (Figure 7.3)
[^4]: [[cgol-ch7-stable-circuitry](pages/cgol-ch7-stable-circuitry.md)] p.188 - "Converting a Herschel into a glider is straightforward since it emits a natural glider after 21 generations anyway ... dozens of Herschel-to-glider converters are known"; "many even produce multiple gliders travelling in different directions, and thus can be used to duplicate a signal"
[^5]: [[cgol-ch7-stable-circuitry](pages/cgol-ch7-stable-circuitry.md)] pp.188-190 [synthesis] - edge shooters "can be used to produce tight glider spacings"; transparent output lane lets NE5T-4 "insert gliders into a stream just like an edge shooter" (Figure 7.6); names "<direction><lane>T<timing>"; NE5T-4, NW31T120; Figure 7.7 edge shooters
[^6]: [[cgol-ch7-stable-circuitry](pages/cgol-ch7-stable-circuitry.md)] p.190 [synthesis] - "the reverse conversion of a glider into a Herschel is much trickier to implement"; Figure 7.8(a) "has repeat time 78 and takes 84 generations"; (b) "repeat time of 115 generations and takes 250 generations"; n.10 found "in March 2015 by Tanner Jacobi, using the same 'Bellman' program that was used to find the Snark"
[^7]: [[cgol-ch7-stable-circuitry](pages/cgol-ch7-stable-circuitry.md)] p.191, n.12 - "The syringe still works when its input gliders have a gap of 74 or 75 generations, but not 76 or 77 generations. We call this phenomenon overclocking"
[^8]: [[cgol-ch7-stable-circuitry](pages/cgol-ch7-stable-circuitry.md)] p.190, n.11 [synthesis] - "entirely made up of small, easy-to-synthesize still lifes and p2 oscillators) Spartan"; "The original definition, from 2004, included only still lifes with 7 or fewer live cells. Nowadays, the definition typically includes any object whose slow salvo synthesis can be automatically compiled by the computer program slsparse"
[^9]: [[cgol-ch7-stable-circuitry](pages/cgol-ch7-stable-circuitry.md)] pp.190-197 [synthesis] - Figure 7.9 syringe plus Figure 7.5(a) reflector, repeat time 78; Bandersnatch (n.13, Martin Grant and "Entity Valkyrie", June 2020) with Snark, repeat time 70; Figure 7.11 duplicator and tripler, "every copy of the Fx77 conduit that we insert increases the number of output gliders by 1"; Table 7.2 rephasers (n.14 Simon Ekström, August 2015); Figure 7.13 trombone slide "delaying the glider by 8 generations for each cell that it is moved away"; Figures 7.12 and 7.14-7.16 glider-to-LWSS and glider-to-Cordership circuits
[^10]: [[cgol-ch7-stable-circuitry](pages/cgol-ch7-stable-circuitry.md)] pp.202-205 [synthesis] - letter codes of Figure 7.24; names "<input code><orientation><timing><output code>"; BLx19R and RF28B (Figure 7.25); n.27 "The RF28B conduit appears in some of the Herschel conduits that we saw back in Table 7.1: Bx202, L156, and Rx164"; Table 7.3
[^11]: [[cgol-ch7-stable-circuitry](pages/cgol-ch7-stable-circuitry.md)] p.204 - "it was used in Figure 3.19(a) to create the p32 'gourmet' oscillator, and also as part of Tanner's p46 in Figure 3.19(c). In a sense, those oscillators (and a few other hasslers that we have seen) function in the same way as Herschel track oscillators"
[^12]: [[cgol-ch7-stable-circuitry](pages/cgol-ch7-stable-circuitry.md)] pp.205-210 [synthesis] - "A conduit that implements such a conversion is called a factory, as is any other pattern that repeatedly creates a still life or oscillator"; "the queen bee can be thought of as a beehive factory"; Figure 7.28 (Callahan 1996, Jacobi 2015); demultiplexer (n.33 Brice Due, August 2006); keepers and period tripler (p.207); highway robber (Figure 7.33, Chris Cain, March 2015) "reflects gliders from a particular lane without being affected whatsoever by gliders on any further away lanes (even directly adjacent ones)"; stable MWSS Heisenburp (Figures 7.34-7.36)
[^13]: [[cgol-ch7-stable-circuitry](pages/cgol-ch7-stable-circuitry.md)] p.211 [synthesis] - Figure 7.37 glider to Herschel plus junk beehive (n.40 Paul Callahan, November 1998); "The simplest sequence of stable conduits that does the job is Fx77 → L112 → Fx77, and the resulting glider-to-Herschel conduit is called the Callahan G-to-H"; repeat time 575; Silver reflector replaces the final Fx77 by NW31, "a slightly smaller repeat time of 497 generations"
[^14]: [[cgol-ch7-stable-circuitry](pages/cgol-ch7-stable-circuitry.md)] pp.212-213 [synthesis] - Figure 7.39 Herschel transceiver (Callahan, October 1996 and May 1997) converts a Herschel "into a pair of gliders travelling the same direction ... and then back into a Herschel"; "With the appearance of the syringe in 2015 (with a repeat time of 78 generations, instead of the Herschel transceiver's 117)"
