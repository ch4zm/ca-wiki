---
title: Herschel
category: Patterns
summary: A seven-cell chaotic Life object that emits a glider after 21 generations and appears in many evolutions (the B-heptomino becomes one in 20); moved through stable conduits such as R64 and Fx77, it runs around Herschel tracks that give oscillators and guns of every period 61 or more
tags: [pattern, life, herschel, conduit, herschel-track, r64, fx77]
sources: [cgol-ch7-stable-circuitry, cgol-ch3-oscillators, cgol-ch1-early-life]
created: 2026-09-25
updated: 2026-09-25
---

# Herschel

## Description

The Herschel is a 7-cell object that explodes chaotically and takes 128 generations to
stabilize. It turns up often in other evolutions: the B-heptomino becomes a block and a
Herschel in 20 generations ([[twin-bees](pages/twin-bees.md)]). A
[[glider](pages/glider.md)] escapes from its debris at generation 21.[^1] That glider
was the first ever observed in Life. Richard K. Guy, following the
[[r-pentomino](pages/r-pentomino.md)] by hand on a Go board, saw it become a B-heptomino
at 28 generations, a Herschel 20 later, and a glider 21 after that.[^2]

**Conduits.** Left alone a Herschel explodes, so it is moved with a *conduit*, a stable
pattern that takes in a Herschel and puts one out elsewhere.[^3]
- **R64**: four blocks that move a Herschel and turn it right by 90 degrees in 64
  generations (David Buckingham, 1995). The output Herschel's glider would hit the next
  Herschel, so a custom constrained [[eater](pages/eater.md)] removes it, giving a repeat
  time of 61.
- **Fx77**: moves a Herschel forward and flips it in 77 generations, also with repeat
  time 61. An eater 2 clears its stray glider.

**Herschel tracks.** Lining up conduits so each output Herschel is the next input makes a
closed track. With h Herschels equally spaced on a track of length L, the result is an
[[oscillator](pages/oscillator.md)] of period L/h, provided that is at least the repeat
time. Four R64s and eight Fx77s make a track of 4 × 64 + 8 × 77 = 872 generations. That
one track gives periods 872, 436, 218 and 109.[^4] A Herschel track is easily adapted
into a glider gun of the same period.[^5]
- **Theorem 3.1.** Square tracks with 4 R64s and 2k Fx77s per side have length 256 + 616k.
  By Bézout's identity some such length is a multiple of p exactly when p is not a
  multiple of 7 or 11.
- **Theorem 3.2.** "Folding in" corners changes the conduit mix and shortens a track by 52
  each time. Folding a large square 76 times gives length 77(8k − 48), which covers the
  multiples of 7 and 11. So R64 and Fx77 give oscillators of every period 61 or more.

These are far from the smallest tracks for most periods.[^6] Faster conduits reach
periods 58-60, and oscillating Herschel conduits (Dietrich Leithner, 1997) reach 56 and
57.[^7] David Buckingham developed Herschel tracks, and by October 1996 had a toolkit for
oscillators and guns of every period 61 or more. The Silver reflector is a Herschel track
that keeps its gliders ([[reflector](pages/reflector.md)]).[^7]

**Beyond R64 and Fx77.** Conduits are named by the output Herschel's turn (R, L, F or B,
plus x if mirrored) and the number of generations, and more than 100 small ones are
known. A richer set shrinks tracks a lot: two L112s and two L156s make a period-67 gun
with 8 Herschels, where R64 and Fx77 alone need 32 conduits and 36 Herschels.[^8] A
Herschel is easy to turn into a glider, since it emits one at generation 21. The reverse
is done by the syringe (Tanner Jacobi, March 2015), which turns a glider into a Herschel
in 84 generations with repeat time 78 ([[conduit](pages/conduit.md)]).[^9]

## Appearances in Sources

- [[cgol-ch7-stable-circuitry](pages/cgol-ch7-stable-circuitry.md)] - §7.1 conduit naming and catalogue; §§7.2-7.3 Herschel-to-glider converters and the syringe
- [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] - §3.6: the Herschel, R64 and Fx77, Theorems 3.1-3.2; §3.9 history
- [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] - appears in generation 48 of the R-pentomino

## Related Concepts

- [[conduit](pages/conduit.md)] - the full family of Herschel conduits and converters
- [[omniperiodicity](pages/omniperiodicity.md)] - Herschel tracks fill every period 61 or more
- [[reflector](pages/reflector.md)] - glider loops, the other track-based method
- [[twin-bees](pages/twin-bees.md)] - the B-heptomino becomes a Herschel
- [[r-pentomino](pages/r-pentomino.md)] - produces one on the way to the first glider

[^1]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] p.68 [synthesis] - "it consists of only 7 cells, it explodes chaotically and takes 128 generations to stabilize, and it occurs frequently in the evolution of other patterns"; "a Herschel is produced in generation 20 of the evolution of the B-heptomino"; "a glider escapes from its debris at generation 21"
[^2]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] p.68, n.18 - "The glider that the Herschel emits was the first glider ever observed in the Game of Life. Richard K. Guy was checking the evolution of the R-pentomino (by hand on a Go board), which produced a B-heptomino after 28 generations, which then made a Herschel 20 generations later, which finally made a glider 21 generations after that"
[^3]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] pp.68-70 [synthesis] - "a pattern that it can interact with (called a conduit)"; R64 "four blocks ... rotates it by 90 degrees over the course of 64 generations" (n.20 Buckingham, September 1995); custom eater gives repeat time 61; Fx77 "moves a Herschel forward and flips it"; eater 2 removes the interfering glider
[^4]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] pp.70-73 [synthesis] - track of 4 R64 and 8 Fx77 takes 872 generations; 1, 2, 4, 8 Herschels give 872, 436, 218, 109; Theorem 3.1 via Bézout's identity: "256 + 616k ≡ 4 (mod 7) and 256 + 616k ≡ 3 (mod 11)"; folding corners reduces by 52; Theorem 3.2: "The Herschel conduits R64 and Fx77 can thus be used to create oscillators of any period 61 or larger"
[^5]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] p.68 - "one of the advantages of creating oscillators via Herschels ... is that they can be straightforwardly tweaked to create glider guns of the same periods"
[^6]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] p.73 - "these Herschel tracks with k ≥ 13 are extremely large, and for many periods it is possible to find much smaller Herschel tracks that work"
[^7]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] pp.73,78-79 [synthesis] - the Silver reflector converts the glider into a Herschel "funneled along a Herschel track without suppressing the gliders"; Buckingham "by October 1996 ... had a complete toolkit capable of constructing oscillators and gliders guns with any period at least 61"; faster conduits give periods 58-60; Leithner's oscillating conduits (December 1997) give 56 and 57
[^8]: [[cgol-ch7-stable-circuitry](pages/cgol-ch7-stable-circuitry.md)] pp.183-185 [synthesis] - "conduits are named according to the orientation of the output Herschel relative to that of the input Herschel, together with the number of generations"; "there are well over 100 known Herschel conduits made up of small still lifes"; p67 via 4 R64 + 28 Fx77 with 36 Herschels versus Figure 7.1 with 8 Herschels, two L112 and two L156
[^9]: [[cgol-ch7-stable-circuitry](pages/cgol-ch7-stable-circuitry.md)] pp.188,190 [synthesis] - "Converting a Herschel into a glider is straightforward since it emits a natural glider after 21 generations anyway"; syringe "has repeat time 78 and takes 84 generations to convert a glider into a Herschel"; n.10 found "in March 2015 by Tanner Jacobi"
