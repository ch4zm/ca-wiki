---
title: Caber tosser
category: Patterns
summary: A Life gun whose gliders come exponentially further apart because each is triggered by a glider bouncing off a receding Cordership, so its population grows like log(t); Dean Hickerson built the first in 1991, and fed into recursive or exponential filters it gives even slower growth
tags: [pattern, life, gun, caber-tosser, logarithmic-growth, cordership, slow-gun]
sources: [cgol-ch8-guns-and-glider-streams]
created: 2026-09-25
updated: 2026-09-25
---

# Caber tosser

## Description

A *caber tosser* is a [[gun](pages/gun.md)] that fires gliders more and more slowly. A
glider bounces back and forth between a receding spaceship and a stationary object that
reflects and duplicates it. The spaceship keeps moving away, so each round trip takes
longer than the last by a constant factor, and the gun's population grows
logarithmically.[^1]

**How it is built.** The simplest caber tossers bounce one glider off the back of a
[[cordership](pages/cordership.md)]. The duplicating part can be two glider guns:[^2]
- one gun is aimed so its gliders would be reflected back by the Cordership;
- a second gun's stream blocks the first;
- the returning glider knocks out one glider of the blocking stream, as in an
  [[inverter](pages/inverter.md)], so each gun releases a single glider and the cycle
  restarts.

In Johnston and Greene's example a period-60 gun and a period-30 gun work against a
2-engine Cordership. The round trip doubles each time, and the n-th glider leaves at
generation 480 × 2^n − 727, so the population in generation t is Θ(log t), meaning it
grows in proportion to log t.[^3] The doubling comes from the speeds: the Cordership
moves at c/12 and the bouncing glider at c/4.[^4]

**History.** Dean Hickerson built the first caber tosser in May 1991, with the same pair
of guns and a different glider reflection off a 13-engine Cordership.[^5]

**Slower still.** A caber tosser can drive devices that slow a gun's output further:[^6]
- An exponential filter (Gabriel Nivasch, 2006) on a caber tosser gives population
  Θ(log(log t)).
- A recursive filter (Alexey Nigin, 2015) on a caber tosser gives Θ(log*(t)), where
  log* counts how many times log must be applied to get a result no larger than 1. Its
  first output glider appears at about generation 1.947 × 10^34, and its second at a
  generation with roughly 10^33 digits.

**Fermat primes.** Aimed at the lightweight spaceships of the [[primer](pages/primer.md)],
a caber tosser picks out the positions 2^n + 1. Johnston and Greene use this to build a
pattern that self-destructs, and so has bounded population, exactly when a sixth Fermat
prime exists. It would not self-destruct before about generation 1.16 × 10^2585827975, so
running it cannot settle the question.[^7]

## Appearances in Sources

- [[cgol-ch8-guns-and-glider-streams](pages/cgol-ch8-guns-and-glider-streams.md)] - §8.8.2 caber tossers; §8.8.3 recursive filter; §8.8.4 Fermat prime calculator; §8.9 exponential filter

## Related Concepts

- [[reverse-caber-tosser](pages/reverse-caber-tosser.md)] - the same idea run backward as a universal constructor
- [[gun](pages/gun.md)] - the pattern class, including sqrtguns
- [[cordership](pages/cordership.md)] - the receding spaceship
- [[inverter](pages/inverter.md)] - the blocking trick in its duplicator
- [[primer](pages/primer.md)] - the prime gun it filters for Fermat primes

[^1]: [[cgol-ch8-guns-and-glider-streams](pages/cgol-ch8-guns-and-glider-streams.md)] p.254 - "bounce a glider back and forth between a receding spaceship and a stationary object that reflects and duplicates the glider. Because the spaceship gets farther and farther away, the time that it takes for the bouncing glider to make a round-trip and get duplicated increases by some multiplicative factor every loop ..., so the resulting growth rate is logarithmic"
[^2]: [[cgol-ch8-guns-and-glider-streams](pages/cgol-ch8-guns-and-glider-streams.md)] p.254 [synthesis] - "the simplest ones to construct make use of a single glider bouncing off of the back of a Cordership"; "we aim one glider gun in the correct positioning and timing as to be reflected by the receding Cordership, but we place another glider gun so as to block it"; "the returning glider blocks the blocking stream as in an inverter, thus letting a single glider from each stream escape and repeat the process"
[^3]: [[cgol-ch8-guns-and-glider-streams](pages/cgol-ch8-guns-and-glider-streams.md)] pp.254-256 [synthesis] - Fig. 8.48 "A period 60 glider gun ... fires gliders at a 2-engine Cordership ... but is blocked by a period 30 glider gun"; round trip "exactly twice as long each time"; "its n-th glider is released in generation 480 × 2^n − 727, so its growth rate is logarithmic (i.e., its population in generation t is Θ(log(t)))"
[^4]: [[cgol-ch8-guns-and-glider-streams](pages/cgol-ch8-guns-and-glider-streams.md)] p.267, Ex. 8.37 - "in the caber tosser of Figure 8.48(a) we had s1 = c/12, s2 = c/4, and a ratio of 2 (each glider took twice as long to be emitted as the previous one)"
[^5]: [[cgol-ch8-guns-and-glider-streams](pages/cgol-ch8-guns-and-glider-streams.md)] p.254, n.38 - "The first caber tosser was built by Dean Hickerson in May 1991 using this same arrangement of guns, but a slightly different glider reflection involving the 13-engine Cordership"
[^6]: [[cgol-ch8-guns-and-glider-streams](pages/cgol-ch8-guns-and-glider-streams.md)] pp.255-258,263-264 [synthesis] - recursive filter "Constructed by Alexey Nigin in July 2015"; first output glider "≈ 1.947 × 10^34"; second at "a number with roughly 10^33 digits"; "Its exact asymptotic growth rate is Θ(log*(t))", log* counts applications of log "to get a result no larger than 1"; Fig. 8.55 exponential filter "constructed by Gabriel Nivasch in June 2006" on a caber tosser gives "Θ(log(log(t)))"
[^7]: [[cgol-ch8-guns-and-glider-streams](pages/cgol-ch8-guns-and-glider-streams.md)] pp.258-259 [synthesis] - caber tosser blocks p240 guns so LWSSes "corresponding to numbers of the form 2^n + 1" pass; Fig. 8.51 calculator "self-destructs and has bounded population if a sixth Fermat prime exists, but grows without bound otherwise"; self-destruction "will not happen until at least generation 120 × 2^2^33 ≈ 1.16 × 10^2 585 827 975, so evolving this pattern via computer software is not actually an effective method of checking"
