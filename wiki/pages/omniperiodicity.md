---
title: Omniperiodicity
category: Concepts
summary: A cellular automaton is omniperiodic if it has oscillators of every period; Conway's Game of Life is, proved in 2023 when oscillators of the last two periods, 19 and 41, were found - the result of combining small-period searches, sparks, hasslers, glider loops and Herschel tracks
tags: [concept, life, omniperiodicity, oscillator, period]
sources: [cgol-ch3-oscillators]
created: 2026-09-25
updated: 2026-09-25
---

# Omniperiodicity

## Description

A cellular automaton is *omniperiodic* if it has [[oscillator](pages/oscillator.md)]s
of every period.[^1] Only non-trivial oscillators count, those with at least one cell
oscillating at the full period. A blinker beside a period-17 oscillator does not give a
genuine period 34.[^2]

**Life is omniperiodic.** This was proved in 2023, when oscillators with the last two
missing periods, 19 and 41, were found.[^3] (The proof paper was read at abstract level
only.)

**How the periods were filled.** Each construction method covers a different range, so
the hardest periods were in the middle.[^4]
- **Small periods** (about 8 or less) come from clever computer searches.
- **Composite periods** come from combining the sparks of lower-period
  [[sparker](pages/sparker.md)]s.
- **Periods of about 30 and up** come from mixing hassling and shuttling reactions
  ([[hassler](pages/hassler.md)]).
- **Every period 43 or more** comes from Snark glider loops
  ([[reflector](pages/reflector.md)]).
- **Every period 61 or more** comes from R64/Fx77 Herschel tracks
  ([[herschel](pages/herschel.md)]). Faster conduits reach 56-60.

Examples of low periods:[^5]

| Period | Examples |
|---|---|
| 2 | blinker, toad, clock, bipole, negentropy |
| 3 | pulsar, caterer, jam, two eaters |
| 4 | mold, confused eaters, T-nosed p4 |
| 5 | octagon 2, pentoad |
| 6 | unix |
| 7 | burloaferimeter, hebdarole |
| 8 | figure eight, blocker, cauldron, Hertz oscillator, roteightor |
| 9 | snacker, worker bee |
| 15 | pentadecathlon |
| 17 | honey thieves |
| 30 | queen bee shuttle, eureka |
| 46 | twin bees shuttle |

## Appearances in Sources

- [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] - §3.7: the problem, Table 3.1, why intermediate periods are hardest

## Related Concepts

- [[oscillator](pages/oscillator.md)] - what is being counted
- [[herschel](pages/herschel.md)], [[reflector](pages/reflector.md)] - the track methods for large periods
- [[sparker](pages/sparker.md)], [[hassler](pages/hassler.md)] - the methods for composite and mid-range periods

[^1]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] p.73 - "do there exist oscillators with all periods in Conway's Game of Life? If so, then Life is said to be omniperiodic, and this omniperiodicity problem is one of its oldest and most well-studied questions"
[^2]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] p.73, n.26 - "Even though we could just place a period 2 blinker next to a period 17 honey thieves to create a period 34 oscillator, ... this type of construction is considered 'trivial' and is thus ignored because no cell oscillates at the full period"
[^3]: https://arxiv.org/abs/2312.02799 (2023-12-05) - Brown, Cheng, Jacobi, Karpovich, Merzenich, Raucci and Riley, "Conway's Game of Life is Omniperiodic", abstract: the search ended "with the discovery of oscillators having the final two periods, 19 and 41, proving that Life is omniperiodic"
[^4]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] pp.73-75 [synthesis] - "Small periods (say with period 8 or less) can often be found via clever computer searches"; high periods "(say with period 30 or more) can often be found by combining various hassling and shuttling reactions"; "composite periods can often by constructed simply by placing sparks of lower-period oscillators next to each other"; Table 3.1: Snark-based glider loops for 43+, Herschel tracks for 61+; p.79 faster conduits for 56-60
[^5]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] p.74, Table 3.1 [synthesis] - examples listed per period; twin bees shuttle period 46 found in 1971
