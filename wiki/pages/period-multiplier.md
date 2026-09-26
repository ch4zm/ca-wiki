---
title: Period Multiplier
category: Patterns
summary: A Life conduit that emits one output signal for every two or more identical inputs, multiplying a glider stream's period; semi-Snarks double it, chains of them count in binary, and with an on-off period adder they give glider guns of any large period in a bounding box whose side grows like the square root of log p, which is optimal up to a constant
tags: [pattern-class, life, period-multiplier, semi-snark, glider-gun, stable-circuitry, conduit]
sources: [cgol-ch7-stable-circuitry]
created: 2026-09-25
updated: 2026-09-26
---

# Period Multiplier

## Description

A *period multiplier* is a [[conduit](pages/conduit.md)] that produces an output signal
only for every two or more identical input signals, so it multiplies the period of a
[[glider](pages/glider.md)] stream.[^1]

**How small can a gun be?** An m × m box holds 2^(m²) patterns, so a gun or
[[oscillator](pages/oscillator.md)] in it has period at most 2^(m²). Turned around, a
period p gun needs a box of side at least the square root of log2(p). This bound is tight
up to a constant factor: for some constant C there are period p guns in a box of side
C times the square root of log2(p), for all large p. Period multipliers are the key
parts of those guns.[^2]

**Semi-Snarks.** The two simplest period multipliers reflect every second glider, so they
double a stream's period.[^3]
- The colour-preserving semi-Snark (Tanner Jacobi, October 2017) is a Snark with one
  eater 1 replaced by a custom catalyst. The first glider makes a tub that destroys the
  next glider. Repeat time 48.
- The colour-changing semi-Snark (Sergey Petrov, July 2013) reflects the first glider
  and moves a central block; the second glider pulls the block back. Repeat time 51.

Other stable period multipliers from the chapter's exercises are the tremi-Snark (x3,
Jacobi, September 2017) and quadri-Snark (x4, Jacobi, October 2017). The quinti-Snark
(x5, Jacobi, October 2018) contains a period-5 heavyweight volcano, so it is not
stable.[^4] One of the chapter's Herschel-to-block factories also works as a period
tripler.[^5]

**Doubling guns.** One semi-Snark on the output of the 536-generation Herschel track gun
gives period 1,072, and a second gives 2,144. The chapter's largest example feeds a
period-256 *machine gun* (four R64 conduits) through 92 semi-Snarks in a spiral. Its
period is 2^100, about 1.27 × 10^30, and it fits in a 240 × 260 box. Longer spirals give
period 2^n guns in a box of side about 30 times the square root of n.[^6]

**Any multiplier, by binary counting.** A row of semi-Snarks counts down in binary if a
blocking semi-Snark is read as 1 and a passing one as 0. Set to the bits of n, the row
blocks n gliders and passes the next one. That glider leaves every semi-Snark at 1, so
extra circuitry uses it to toggle the right ones back to 0. The chapter's example blocks
18 of every 19 gliders.[^7]

**Adding to the period.** Multiplication alone never gives a prime period. The fix is to
add generations with a gun that can be switched off and on.[^8]
- The *adjustable glider gun* (Matthias Merzenich, September 2015) is two halves, each a
  syringe, an F117 conduit and a Herschel-to-glider converter, passing one glider back
  and forth. As shown it has period 80; moving the top half n cells adds n. It works for
  every period 78 or more (and, by overclocking, 74 and 75), but its bounding box is
  (p + 18) × (p - 14), so it grows fast.
- Firing a glider at its side turns it off, and feeding one in turns it back on. With one
  glider on the period-77 version's track, it has period 616. A glider tripler on its
  output then sends one glider out, one to stop the gun and one to restart it later. That
  adds any chosen number of generations of at least 1,087.

**A prime-period gun.** For period 3,413,277,319, the chapter multiplies a p616 gun by
5,541,032 with a spiral of semi-Snarks set to its binary digits, then adds 1,607
generations: 616 × 5,541,032 + 1,607 = 3,413,277,319. Chris Cain assembled most of the
parts in December 2017, together with a script that builds a gun of this type for any
period of at least 1,703.[^9]

## Appearances in Sources

- [[cgol-ch7-stable-circuitry](pages/cgol-ch7-stable-circuitry.md)] - §7.6: period multipliers and small high-period guns; Exercises 7.20-7.25, 7.38

## Related Concepts

- [[conduit](pages/conduit.md)] - the syringe and Herschel conduits these guns use
- [[reflector](pages/reflector.md)] - the Snark that semi-Snarks modify
- [[herschel](pages/herschel.md)] - Herschel tracks give the base guns
- [[inverter](pages/inverter.md)] - the periodic route to big-period guns
- [[primer](pages/primer.md)] - another gun built around number theory
- [[gun](pages/gun.md)] - other ways to change a gun's period: deletion, filters, insertion

[^1]: [[cgol-ch7-stable-circuitry](pages/cgol-ch7-stable-circuitry.md)] p.198 - "period multipliers--conduits that only produce an output signal for every two or more (identical) input signals that are received, and thus multiply the period of the input stream"
[^2]: [[cgol-ch7-stable-circuitry](pages/cgol-ch7-stable-circuitry.md)] p.198 [synthesis] - an m × m box has 2^(m²) patterns, so "there cannot exist a period p gun inside a box of size less than √log2(p) × √log2(p)"; "this lower bound is 'essentially' tight--there exists a constant C such that it is possible to construct period p guns inside a box of size C√log2(p) × C√log2(p) for all large p"; "The key objects used in the construction of such guns are period multipliers"
[^3]: [[cgol-ch7-stable-circuitry](pages/cgol-ch7-stable-circuitry.md)] p.198 [synthesis] - Figure 7.18(a) CP semi-Snark, repeat time 48, "one of its eater 1s replaced by a custom catalyst that, when hit by a glider, creates a tub that destroys the next glider. Found by Tanner Jacobi in October 2017"; (b) CC semi-Snark, repeat time 51, block moved and pulled back, "Found by Sergey Petrov in July 2013"
[^4]: [[cgol-ch7-stable-circuitry](pages/cgol-ch7-stable-circuitry.md)] pp.199,216-217 [synthesis] - n.22 "tremi-, quadri-, and quinti-Snarks that multiply the period of a glider stream by 3, 4, and 5"; n.45 tremi-Snark found by Tanner Jacobi in September 2017; n.46 quadri-Snark October 2017; n.47 quinti-Snark October 2018; Exercise 7.24(c) "The quinti-Snark is not stable--it contains a p5 heavyweight volcano"
[^5]: [[cgol-ch7-stable-circuitry](pages/cgol-ch7-stable-circuitry.md)] p.207 - "This conduit can thus act as a period tripler for a glider or Herschel stream"
[^6]: [[cgol-ch7-stable-circuitry](pages/cgol-ch7-stable-circuitry.md)] pp.198-199 [synthesis] - periods 2 × 536 = 1,072 and 4 × 536 = 2,144 (Figure 7.19(a)); "a p256 gun with 92 semi-Snarks arranged in a spiral"; "256 × 2^92 = 2^100 = 1 267 650 600 228 229 401 496 703 205 376, despite fitting inside a bounding box of size just 240 × 260"; central gun "consists of four copies of the R64 conduit and is called the machine gun"; period 2^n in "roughly (30√n) × (30√n)"
[^7]: [[cgol-ch7-stable-circuitry](pages/cgol-ch7-stable-circuitry.md)] pp.199-200 [synthesis] - "firing a glider at those semi-Snarks counts down in binary"; the first glider through "resets all of the semi-Snarks to '1'"; toggling back to "0"; Figure 7.21 "blocks 18 out of every 19 input gliders"
[^8]: [[cgol-ch7-stable-circuitry](pages/cgol-ch7-stable-circuitry.md)] pp.196-201 [synthesis] - Figure 7.17 period 80 adjustable gun (Matthias Merzenich, September 2015); syringe, F117, Herschel-to-glider converter; "move the top half ... northeast by n cells"; "any period at least 78"; n.18 overclocking for 74 and 75; bounding box "(p + 18) × (p − 14)"; "no small prime-period gun can be created in this way"; turned off by a glider at the side; p616 from the period 77 version with one glider; Figure 7.22 tripler mechanism; "any number of generations at least 1 087 can be added"
[^9]: [[cgol-ch7-stable-circuitry](pages/cgol-ch7-stable-circuitry.md)] pp.201-202 [synthesis] - multiply by 5 541 032 = 10101001000110010101000 in binary via a semi-Snark spiral, add 1 607; "(616 × 5 541 032) + 1 607 = 3 413 277 319" (Figure 7.23); n.24 "assembled by Chris Cain in December 2017, as was a script that automatically compiles a gun of this type for any period at least 1 703"
