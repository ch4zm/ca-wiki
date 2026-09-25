---
title: Conway's Game of Life
category: Rules
summary: Conway's two-state, eight-neighbour (Moore neighbourhood) rule - survival on two or three live neighbours, birth on exactly three, death otherwise; tuned for unpredictability, home of still lifes, oscillators, gliders and spaceships, and computationally universal via glider-stream circuits, with undecidable death of finite patterns
tags: [rule, life, conway, two-dimensional, totalistic, universality]
sources: [fantastic-combinations-of-john-conways-life, statistical-mechanics-of-cellular-automata, computation-at-the-edge-of-chaos, theory-of-cellular-automata-a-survey]
created: 2026-09-24
updated: 2026-09-25
---

# Conway's Game of Life

## Description

**Origin and design goals.** Martin Gardner's October 1970 *Scientific American* column
presented Life as Conway's new solitaire "simulation game". Conway chose
the rules after long experiment to meet three goals: no starting pattern should have a
simple proof that its population grows without limit; some patterns should apparently
grow without limit; and simple patterns should grow and change for a long time before
dying out, becoming stable, or oscillating. In short, the population's behaviour should be
unpredictable.[^1]

**The rule.** Life is a two-dimensional [[cellular-automaton](pages/cellular-automaton.md)]
with two states per cell on an infinite square board. Each cell has eight neighbours, four
orthogonal and four diagonal (the [[moore-neighbourhood](pages/moore-neighbourhood.md)]).[^2]
- **Survival:** a live cell with two or three live neighbours stays alive.
- **Death:** a live cell with four or more dies of overpopulation; one with zero or one
  dies of isolation.
- **Birth:** an empty cell with exactly three live neighbours comes alive.

All births and deaths happen at once and make up one generation, which Gardner calls a
"move".[^3] Wolfram classes Life as *totalistic*: a cell's new value depends only on the
sum of its neighbourhood's values.[^4]

**Running it by hand.** Conway's procedure uses black and white counters. Mark every
counter that will die by stacking a second black one on it, put a white counter on every
birth cell, check everything, then remove the stacks and turn the whites black. The two
colours are needed because newborns must not count toward the current generation's
births and deaths.[^5] For long runs Conway used a PDP-7 display program written by
M. J. T. Guy and S. R. Bourne.[^6]

**What patterns do.** Most starting patterns end as a [[still-life](pages/still-life.md)]
or an [[oscillator](pages/oscillator.md)]; a few die out, sometimes after many
generations. Patterns without symmetry tend to become symmetric, and once symmetry
appears it cannot be lost.[^7] The founding named patterns are the
[[block](pages/block.md)], [[beehive](pages/beehive.md)], [[blinker](pages/blinker.md)],
[[glider](pages/glider.md)], [[pulsar](pages/pulsar.md)] and
[[pentadecathlon](pages/pentadecathlon.md)]. The [[r-pentomino](pages/r-pentomino.md)]
is the one pentomino that does not settle quickly.[^8] Structures separated by four or
more empty cells can coexist without interfering.[^9]

**Speed of light and spaceships.** Conway calls one cell per generation, a chess king's
move, the "speed of light" c. He proved that finite figures move at most c/4 diagonally
and c/2 orthogonally. The glider moves at c/4 and is the smallest
[[spaceship](pages/spaceship.md)].[^10]

**Unbounded growth.** Conway conjectured in 1970 that no finite pattern grows without
limit, and offered $50 for a proof or disproof. A "gun" that keeps shooting out gliders,
or a "puffer train" that moves and leaves debris behind, would disprove it.[^11] Glider
guns were later found; by 1983 the simplest known evolved from 26 live cells.[^12]

**From random starts.** Monte Carlo runs suggest that a random N × N region usually
settles into a steady state within about N² steps, and often ten times sooner. It visits
very few of its 2^(N²) configurations. Complex structures such as guns almost never arise
by chance. Roughly, the density of structures with L live cells falls off like e^(−L₋)/L,
where L₋ is the size of the smallest configuration that turns into the structure in one
step.[^13]

**Irreversibility.** Like the one-dimensional rules
([[irreversibility-and-entropy](pages/irreversibility-and-entropy.md)]), Life is
irreversible and so has [[garden-of-eden](pages/garden-of-eden.md)] configurations,
which can occur only as initial states. The simplest known in 1983 had about 300
cells.[^14]

**Universality.** Glider streams can act as wires, with a glider or its absence as one bit.
Structures where streams meet decide whether the wires cross or combine through a NAND
gate. Memories are needed too. With these, Life can simulate a digital computer, so it is
computationally universal. Circuits such as binary adders have been built, and they appear
to run only a constant factor slower than the computers they imitate.[^15] Compare von
Neumann's [[von-neumann-29-state-ca](pages/von-neumann-29-state-ca.md)], which is also
universal but uses 29 states and the five-cell neighbourhood
([[universal-turing-machine](pages/universal-turing-machine.md)]).

**Place in rule space.** Life's [[lambda-parameter](pages/lambda-parameter.md)] is 0.273, which lies inside the
order-chaos transition region for 2-state, 9-neighbour rules. Langton reads its gliders
(used as signals) and blinkers (used as storage) in the universality proof as the kind of
moving and static structures that appear near the transition ([[edge-of-chaos](pages/edge-of-chaos.md)]).[^16]
He also notes that Bak had suggested Life is a self-organized critical system (cited via
Langton, not read).[^17]

**Formal definitions and undecidability (Kari 2005).** Kari defines Life's objects in
terms of finite configurations c and the global map G: a still life is a finite fixed
point, G(c) = c; an oscillator is a finite c with Gᵏ(c) = c for some k ≥ 2; a glider (in
general, any spaceship) is a finite c with Gᵏ(c) equal to a translate of c; a glider gun
is periodic like an oscillator and emits one or more gliders each period. His examples
are a period-two oscillator, a period-four glider and a period-30 glider gun. Random
starts quickly produce such objects, which interact by collisions "leading to
extraordinary complexity".[^18] For any Turing machine M one can build a finite Life
configuration that *dies*, meaning it eventually becomes all-dead, iff M halts on the
blank tape. So Life is computationally universal and **whether a finite configuration
dies is undecidable** (Berlekamp, Conway and Guy).[^19] Life's gliders correspond to the
signals of class-4 1D rules such as [[rule-110](pages/rule-110.md)], but signals cross
far more easily in two dimensions.[^20]

## Appearances in Sources

- [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] - Gardner 1970: design goals, the rule, hand procedure, first named patterns, speed of light, the growth conjecture
- [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] - §2.6: formal definitions of still lifes, oscillators, gliders and guns; Theorem 1 (universality, undecidable death)
- [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] - Sec. V: the rule, standard structures, statistics from random starts, Garden-of-Eden size, universality via glider streams
- [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] - λ = 0.273, gliders and blinkers as signals and storage

## Related Concepts

- [[still-life](pages/still-life.md)], [[oscillator](pages/oscillator.md)], [[spaceship](pages/spaceship.md)] - the three basic pattern classes
- [[glider](pages/glider.md)], [[block](pages/block.md)], [[beehive](pages/beehive.md)], [[blinker](pages/blinker.md)], [[r-pentomino](pages/r-pentomino.md)], [[pulsar](pages/pulsar.md)], [[pentadecathlon](pages/pentadecathlon.md)] - named patterns
- [[moore-neighbourhood](pages/moore-neighbourhood.md)] - the eight-neighbour cell
- [[edge-of-chaos](pages/edge-of-chaos.md)] - Life sits in the transition region
- [[cellular-automaton](pages/cellular-automaton.md)] - the general notion; type-I vs type-II neighbourhoods
- [[garden-of-eden](pages/garden-of-eden.md)] - Life has them, and the smallest known is large
- [[universal-turing-machine](pages/universal-turing-machine.md)] - computational universality in cellular automata
- [[von-neumann-29-state-ca](pages/von-neumann-29-state-ca.md)] - the earlier universal cellular automaton
- [[irreversibility-and-entropy](pages/irreversibility-and-entropy.md)] - the irreversibility Life shares with 1D rules
- [[rule-110](pages/rule-110.md)] - the 1D counterpart, with signals in place of gliders
- [[decidability-in-cellular-automata](pages/decidability-in-cellular-automata.md)] - whether a finite pattern dies is undecidable
- [[intrinsic-universality](pages/intrinsic-universality.md)] - Life's universality is the Turing-machine kind
- [[classification-of-cellular-automata](pages/classification-of-cellular-automata.md)] - Life's gliders as the 2D counterpart of class-4 signals

[^1]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] pp.1-2 [synthesis] - Life belongs to "a growing class of what are called 'simulation games'"; "Conway chose his rules carefully, after a long period of experimentation, to meet three desiderata"; "In brief, the rules should be such as to make the behavior of the population unpredictable"
[^2]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.2 [synthesis] - "each cell of the checkerboard (assumed to be an infinite plane) has eight neighboring cells, four adjacent orthogonally, four adjacent diagonally"; survivals with two or three neighbours; deaths with four or more or with one or none; births on exactly three
[^3]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.2 - "all births and deaths occur simultaneously. Together they constitute a single generation or, as we shall call it, a 'move'"
[^4]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.637 - "The game of 'Life' is an example of a special class of 'totalistic' cellular automata, in which the value of a site depends only on the sum of the values of its neighbors at the previous time step"
[^5]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.2 [synthesis] - Conway's four-step procedure with black and white counters; "newborn counters play no role in causing other deaths and births"
[^6]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.5 - "Conway sometimes uses a PDP-7 computer with a screen on which he can observe the changes. The program was written by M. J. T. Guy and S. R. Bourne"
[^7]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] pp.2-3 [synthesis] - "In a few cases the society eventually dies out ..., although this may not happen until after a great many generations. Most starting patterns either reach stable figures ... or patterns that oscillate forever. Patterns with no initial symmetry tend to become symmetrical. Once this happens the symmetry cannot be lost"
[^8]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] pp.3-6 [synthesis] - block, blinker, beehive, traffic lights, R pentomino, glider, figure 8, pulsar CP 48-56-72, pentadecathlon; "The only pentomino that does not end quickly ... is the R pentomino"
[^9]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.637 [synthesis] - structures separated by four or more unfilled sites coexist without interference
[^10]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] pp.4-5 [synthesis] - king's move called the "speed of light"; "the maximum speed diagonally is a fourth the speed of light"; orthogonal movement "cannot exceed half the speed of light"; "the glider is a 'featherweight spaceship'"
[^11]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.3 [synthesis] - "Conway conjectures that no pattern can grow without limit"; $50 prize; a "gun" or a "puffer train" would disprove it
[^12]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.637 [synthesis] - glider guns; the simplest known gun evolves from 26 live cells
[^13]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.637 [synthesis] - a disordered state of N² cells usually evolves to a steady state within about N² time steps, typically an order of magnitude quicker; very few configurations visited; glider guns very rarely produced; density of L-site structures decreases like e^(−L₋)/L
[^14]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.637 - "the simplest known 'unreachable' configuration contains around 300 sites"
[^15]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.639 [synthesis] - glider streams from glider guns used as wires, bits as presence or absence of gliders; meeting points determine crossing or a "NAND gate"; memories required; "The Life-game cellular automaton is thus computationally universal"; binary adders; circuits run slower "only by a constant multiplicative factor"
[^16]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] pp.25-26 [synthesis] - "The λ value for the Game of Life (λ_Life = 0.273) lies within the transition region for K = 2, N = 9 2D CAs"; the universality proof "employs propagating 'gliders' as signals and the period-2 'blinkers' as storage elements"
[^17]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] p.35 - "Bak has suggested that Conway's game of Life is a self-organized critical system, although he does not bring Life's computational capacity into the discussion."
[^18]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.10-11 [synthesis] - Game of Life by Conway; still life, oscillator, glider, glider gun defined via finite configurations; Fig. 5: still life, period two oscillator, period four glider, period 30 glider gun; objects emerge from random configurations and interact through collisions, "leading to extraordinary complexity"
[^19]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.11 [synthesis] - "for any given Turing machine M one can effectively construct a finite GOL configuration that dies if and only if machine M halts on the blank tape"; Theorem 1 (Berlekamp et al. [6])
[^20]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.11 [synthesis] - "gliders in GOL are analogous to the complicated localized structures, or signals, that emerge in class 4 elementary CA"; "in two dimensions it is much easier to make signals cross each other"
