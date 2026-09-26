---
title: Reflector
category: Patterns
summary: A stationary pattern that turns an incoming glider into an outgoing one in another direction while surviving; oscillator-based reflectors (buckaroo, pentadecathlon) and stable ones (Silver reflector, repeat time 497; Snark, repeat time 43) turn glider loops into oscillators of every sufficiently large period
tags: [pattern-class, life, reflector, snark, glider-loop, repeat-time]
sources: [cgol-ch3-oscillators]
created: 2026-09-25
updated: 2026-09-25
---

# Reflector

## Description

A *reflector* is a still life or oscillator that a [[glider](pages/glider.md)] can hit
without harming it, and that sends a glider out in a different direction.[^1] With
reflectors, gliders can be made to circulate on a closed track, a *glider loop*, which is
an [[oscillator](pages/oscillator.md)] whose period depends on track length and the
number of gliders on it. Gliders can be no closer than 14 generations apart without
colliding.[^2]

**Oscillator reflectors.** Any [[sparker](pages/sparker.md)] with an accessible duoplet
or banana spark turns a glider by 90 degrees, provided the stream's period is a multiple
of the oscillator's. Four buckaroos make a track that takes a glider 180 generations;
two gliders on it give period 90, and in general every multiple of 30 is reachable.[^3]
The [[pentadecathlon](pages/pentadecathlon.md)] reflects a glider by 180 degrees; two
of them give periods 60 + 120n. 180-degree reflectors are less useful than 90-degree
ones. Two 90-degree reflectors make a 180-degree one but not the reverse, and a
180-degree track holds only one glider, since its input and output paths overlap.[^4]

**Stable reflectors.** A reflector made only of still lifes needs no phase matching, and
it gives oscillators of every sufficiently large period.[^5] Its key figure is the
*repeat time*, the minimum spacing of gliders it can handle; this is at least 14 and
usually much more.[^6]
- The **Silver reflector** (Stephen Silver, November 1998) turns the glider into a
  [[herschel](pages/herschel.md)] via a beehive and runs it through 17 still lifes. It
  emits three gliders and has repeat time 497.
- The **Snark** (completed by Mike Playle in April 2013 with a custom search program,
  from a near-miss by Dietrich Leithner around 1998) is the smallest and fastest, with
  repeat time 43. Four Snarks make oscillators of every period 43 or more, and this
  method gives the only known oscillators of periods 43 and 53.

The first explicit stable reflector, built by Paul Callahan from Herschel tracks in 1996,
had repeat time 4,840, cut in steps to 497. Two 180-degree stable reflectors followed:
the boojum reflector (Dave Greene, 2001, repeat time 202) and the rectifier (Adam P.
Goucher, 2009, repeat time 106).[^7]

## Appearances in Sources

- [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] - §3.5: reflectors and glider loops; §3.9 history of stable reflectors

## Related Concepts

- [[glider](pages/glider.md)] - what it reflects
- [[herschel](pages/herschel.md)] - the Silver reflector works through a Herschel track
- [[omniperiodicity](pages/omniperiodicity.md)] - Snark loops fill every period 43 or more
- [[sparker](pages/sparker.md)] - oscillator reflectors use duoplet and banana sparks

[^1]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] p.65 - "a stationary pattern (i.e., a still life or an oscillator) with the property that if a glider hits it then the stationary pattern is unaffected and another glider is output in a different direction. Such a pattern is called a reflector"
[^2]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] p.65 - "The closest together that we can place gliders without them crashing into each other is 14 generations apart"
[^3]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] p.65 [synthesis] - reflect a glider stream "using any oscillator that emits one of these sparks with enough clearance, as long as the period of the glider stream is a multiple of the period of the oscillator"; four buckaroos, 180 generations, two gliders, period 90; "any period that is a multiple of 30"
[^4]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] p.65 [synthesis] - pentadecathlon reflects by 180 degrees; smallest period 60; "period 60 + 120n"; "we can use two 90-degree reflectors to create a single 180-degree reflector, but we cannot use 180-degree reflectors to make a 90-degree reflector"; only a single glider fits
[^5]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] pp.65-66 [synthesis] - a still-life reflector avoids phase matching; "Glider reflectors consisting entirely of still lifes are called stable reflectors"; with non-interfering paths, "oscillators with every sufficiently large period"
[^6]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] pp.66-68 [synthesis] - "how many generations are needed between subsequent gliders colliding with the reflector, which is called its repeat time"; at least 14; Silver reflector colliding a glider with a beehive and 17 still lifes, repeat time 497, three output gliders; the Snark "with a repeat time of 43 generations", "the smallest and fastest"; nn.15-16 discovery history; "gives the only known oscillators with period 43 or 53"
[^7]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] p.78 [synthesis] - Callahan's first explicit stable glider reflector with repeat time 4 840, reduced through 894, 747, 672, 623, 575 to 497; boojum reflector (Dave Greene, April 2001, 202); rectifier (Adam P. Goucher, March 2009, 106)
