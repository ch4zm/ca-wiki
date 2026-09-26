---
title: Phoenix
category: Patterns
summary: A Life pattern in which every live cell dies each generation yet the pattern lives on; every phoenix stays within one cell of its starting bounding box and so is an oscillator (no phoenix spaceships), every finite phoenix has period 2 (Goucher, 2024)
tags: [pattern-class, life, phoenix, oscillator, theorem]
sources: [cgol-ch12-0e0p-metacell, cgol-ch3-oscillators]
created: 2026-09-25
updated: 2026-09-26
---

# Phoenix

## Description

A *phoenix* is a pattern in which all live cells die every generation, yet the pattern
as a whole lives on. It is named for the mythical bird reborn after dying. A period-2
phoenix [[oscillator](pages/oscillator.md)] exists.[^1]

**Every phoenix is an oscillator (Theorem 3.3).** No phoenix ever extends more than one
cell beyond its original bounding box.[^2]
- *Proof idea.* Suppose X, two cells outside, is the first such cell born, at generation
  n. Its three parents J, K, L are alive at n − 1 and dead at n − 2. For K to be born at
  n − 1, its outer neighbours must be alive at n − 2 and so dead at n − 1.
- That leaves K with exactly two live neighbours at n − 1, so K survives, contradicting
  the phoenix property.
- A pattern confined to a w × h box must repeat within 2^(wh) generations, so it
  oscillates. There are no finite phoenix spaceships or puffers.

A phoenix can leave its original bounding box by one cell.[^3] The edge argument used
here is a standard tool; it also bounds spaceship speeds.[^4]

**Periods.**[^5]
- Period 2: examples exist.
- Period 3: impossible (Theorem 3.4). Take the leftmost rotor cell in the top row; a
  neighbour count on it and the cells feeding it rules this out.
- Period 5: impossible, by a computer-assisted proof (Alex Greason, 2019).
- Every finite phoenix has period 2: Adam P. Goucher proved it in January 2024, after
  Amling ruled out periods 7, 9 and 11. Infinite phoenix agars and wicks exist with
  periods 2, 4, 8 and 6n.[^8]

A whole rule can be phoenix-only: in the 8-state von Neumann rule that the 0E0P
[[metacell](pages/metacell.md)] runs, every cell dies every generation, so every pattern is a
phoenix.[^6]

Oscillators in which every cell oscillates (no *stator*) without being phoenices do
exist at higher periods, such as a period-3 example (Jason Summers, 2012).[^7]

## Appearances in Sources

- [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] - §3.8: Theorems 3.3-3.4

## Related Concepts

- [[oscillator](pages/oscillator.md)] - every phoenix is one
- [[spaceship](pages/spaceship.md)] - no phoenix can be one
- [[catagolue](pages/catagolue.md)] - awards the "Conchita" badge for a soup containing a phoenix
- [[seeds-rule](pages/seeds-rule.md)] - no survival, so every pattern is a phoenix
- [[brians-brain](pages/brians-brain.md)] - no survival either, so every pattern is a phoenix

[^1]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] p.75 - "the period 2 oscillator shown in Figure 3.37, which has the interesting property that all of its live cells die every generation, yet the pattern as a whole lives. A pattern with this property is called a phoenix, after the mythological bird that is cyclically reborn after dying"
[^2]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] p.75 [synthesis] - Theorem 3.3: "no phoenix can ever extend more than one cell outside of its original bounding box. In particular, every phoenix evolves into an oscillator"; proof via cells J, K, L, A, B, C and X; "2^(wh) different patterns"; "There's no such thing in Life as a phoenix spaceship"; n.28 proved by Stephen Silver, January 2000
[^3]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] p.82, Ex. 3.30 - asks for "a phoenix that does in fact leave its original bounding box", showing the bound cannot be tightened to zero
[^4]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] p.76 - "to prove that a pattern with a certain property does not exist, consider what happens to the pattern at one of its far edges ... we will use it again in Section 4.5 to find bounds on how fast spaceships can travel"
[^5]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] pp.76-77 [synthesis] - "to date no one has found any phoenices with period 3 or higher"; Theorem 3.4 (No Phoenices with Period 3) with proof via cells A, J, K, L, M, X, Y; "A computer-assisted proof has also been used to show that no phoenices of period 5 exist" (n.30 Alex Greason, September 2019); "essentially nothing else is known ... with period 4 or greater"
[^6]: [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] p.392, n.13 - the metacell emulates "an 8-state von-Neumann-neighborhood CA in which every cell dies in every generation"; "In other words, every pattern is a phoenix in these cellular automata"
[^7]: [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] p.77 - "every cell in the period 3 oscillator displayed in Figure 3.41 oscillates, even though it is not a phoenix" (Fig. 3.41: found by Jason Summers in August 2012)
[^8]: https://conwaylife.com/wiki/Phoenix (2026-09-26, search excerpt) - every finite phoenix has period 2 (Goucher, January 2024); earlier exclusions of periods 3 (Silver), 5 (Greason), 7, 9 and 11 (Amling); infinite phoenix agars and wicks of periods 2, 4, 8 and 6n
