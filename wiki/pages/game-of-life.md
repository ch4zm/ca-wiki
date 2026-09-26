---
title: Conway's Game of Life
category: Rules
summary: Conway's B3/S23 rule on the eight-cell neighbourhood - survival on two or three live neighbours, birth on exactly three; the most-studied Life-like rule, home of still lifes, oscillators, spaceships, guns, puffers and methuselahs, and computationally universal via glider-stream circuits, with undecidable death of finite patterns
tags: [rule, life, conway, two-dimensional, totalistic, universality]
sources: [universality-and-complexity-in-cellular-automata, eppstein-2010-growth-and-decay-in-life-like-ca, cgol-ch9-universal-computation, cgol-ch12-0e0p-metacell, cgol-ch1-early-life, fantastic-combinations-of-john-conways-life, statistical-mechanics-of-cellular-automata, computation-at-the-edge-of-chaos, theory-of-cellular-automata-a-survey]
created: 2026-09-24
updated: 2026-09-26
---

# Conway's Game of Life

## Description

**Origin and design goals.** Life was first studied in 1969 and 1970 by John Conway and
collaborators at Cambridge and by a group led by Bill Gosper at MIT, and reached a wide
audience through Martin Gardner's October 1970 *Scientific American* column.[^1] Conway
chose the rules after long experiment to meet three goals: no starting pattern should have a
simple proof that its population grows without limit; some patterns should apparently
grow without limit; and simple patterns should grow and change for a long time before
dying out, becoming stable, or oscillating. In short, the population's behaviour should be
unpredictable.[^2]

**The rule.** Life is a two-dimensional [[cellular-automaton](pages/cellular-automaton.md)]
with two states per cell on an infinite square board. Each cell has eight neighbours, four
orthogonal and four diagonal (the [[moore-neighbourhood](pages/moore-neighbourhood.md)]).[^3]
- **Survival:** a live cell with two or three live neighbours stays alive.
- **Death:** a live cell with four or more dies of overpopulation; one with zero or one
  dies of isolation.
- **Birth:** an empty cell with exactly three live neighbours comes alive.

All births and deaths happen at once and make up one generation (also called a tick).[^4]
In rulestring notation Life is **B3/S23**, one of 262,144
[[life-like-cellular-automaton](pages/life-like-cellular-automaton.md)] rules. Among them
it stands out for simple rules, a balance between chaos and stability, and being by far
the most studied.[^5] Wolfram classes Life as *totalistic*: a cell's new value depends only on the
sum of its neighbourhood's values.[^6]

**Running it by hand.** Before simulation software, patterns were evolved by hand on
graph paper, checkerboards or Go boards.[^7] Conway's procedure uses black and white counters. Mark every
counter that will die by stacking a second black one on it, put a white counter on every
birth cell, check everything, then remove the stacks and turn the whites black. The two
colours are needed because newborns must not count toward the current generation's
births and deaths.[^8] For long runs Conway used a PDP-7 display program written by
M. J. T. Guy and S. R. Bourne.[^9]

**What patterns do.** Most starting patterns end as a [[still-life](pages/still-life.md)]
or an [[oscillator](pages/oscillator.md)]; a few die out, sometimes after many
generations. Patterns without symmetry tend to become symmetric, and because the rules
ignore orientation, symmetry once formed is never broken.[^10] Still lifes, oscillators and
[[spaceship](pages/spaceship.md)]s are the basic building blocks.[^11] Random soups leave
*ash* dominated by the [[block](pages/block.md)], [[beehive](pages/beehive.md)],
[[blinker](pages/blinker.md)] and [[glider](pages/glider.md)], with the
[[pulsar](pages/pulsar.md)], [[pentadecathlon](pages/pentadecathlon.md)] and
[[familiar-fours](pages/familiar-fours.md)] also common ([[soup-search](pages/soup-search.md)]).
Small patterns that take very long to settle are [[methuselah](pages/methuselah.md)]s,
the [[r-pentomino](pages/r-pentomino.md)] (1,103 generations) being the classic.[^12] Structures separated by four or
more empty cells can coexist without interfering.[^13]

**Speed of light and spaceships.** Conway calls one cell per generation, a chess king's
move, the "speed of light" c. He proved that finite figures move at most c/4 diagonally
and c/2 orthogonally. The glider moves at c/4 and is the smallest
[[spaceship](pages/spaceship.md)].[^14]

**Unbounded growth.** Finite patterns can grow without limit. A *[[gun](pages/gun.md)]* emits an endless
stream of moving objects; the [[gosper-glider-gun](pages/gosper-glider-gun.md)], two
[[queen-bee](pages/queen-bee.md)]s bouncing between blocks, was the first pattern found
to do so, and settled a $50 challenge Conway had set on the question.[^15] A *[[puffer](pages/puffer.md)]*
moves while leaving debris; the block-laying and glider-producing
[[switch-engine](pages/switch-engine.md)]s are the only infinitely growing patterns ever
seen to arise from random soup.[^16] Most modern Life patterns are engineered by
combining known reactions in this way.[^17]

**From random starts.** Monte Carlo runs suggest that a random N × N region usually
settles into a steady state within about N² steps, and often ten times sooner. It visits
very few of its 2^(N²) configurations. Guns almost never arise by chance. Roughly, the density of structures with L live cells falls off like e^(−L₋)/L,
where L₋ is the size of the smallest configuration that turns into the structure in one
step.[^18]

**Irreversibility.** Like the one-dimensional rules
([[irreversibility-and-entropy](pages/irreversibility-and-entropy.md)]), Life is
irreversible and so has [[garden-of-eden](pages/garden-of-eden.md)] configurations,
which can occur only as initial states. Almost all large patterns are Gardens of Eden; the
smallest known orphan has 45 live cells.[^19]

**Universality.** Glider streams can act as wires, with a glider or its absence as one bit.
Structures where streams meet decide whether the wires cross or combine through a NAND
gate. Memories are needed too. With these, Life can simulate a digital computer, so it is
computationally universal. Circuits such as binary adders have been built, and they appear
to run only a constant factor slower than the computers they imitate.[^20] Explicit programmable computers now exist as Life patterns small enough to run in
Golly: Adam P. Goucher's toolkit stores numbers in [[sliding-block-register](pages/sliding-block-register.md)]s and
binary registers, and programs written in [[apgsembly](pages/apgsembly.md)] compile into patterns such as
one that prints the digits of π forever.[^21] Compare von
Neumann's [[von-neumann-29-state-ca](pages/von-neumann-29-state-ca.md)], which is also
universal but uses 29 states and the five-cell neighbourhood
([[universal-turing-machine](pages/universal-turing-machine.md)]).

**Life hosts other rules.** Large Life patterns called [[metacell](pages/metacell.md)]s behave as single
cells of another rule. The 0E0P metacell emulates any two-state Moore-neighbourhood rule
in which empty stays empty, so patterns from [[highlife](pages/highlife.md)] or
[[isotropic-non-totalistic-rule](pages/isotropic-non-totalistic-rule.md)]s can be imported into Life, at a scale 2^18 larger
and 2^36 slower.[^22]

**Place in rule space.** Life's [[lambda-parameter](pages/lambda-parameter.md)] is 0.273, which lies inside the
order-chaos transition region for 2-state, 9-neighbour rules. Langton reads its gliders
(used as signals) and blinkers (used as storage) in the universality proof as the kind of
moving and static structures that appear near the transition ([[edge-of-chaos](pages/edge-of-chaos.md)]).[^23]
Wolfram (1984) used Life as the template for class 4 of his [[wolfram-classes](pages/wolfram-classes.md)], the class of complex
localized structures conjectured to be capable of universal computation; the
one-dimensional class 4 rule code 20 behaves in a way "strongly reminiscent" of Life.[^24]
He also notes that Bak had suggested Life is a self-organized critical system (cited via
Langton, not read).[^25]

**Fertile and mortal.** In Eppstein's rule-space terms Life is both *fertile* (the
glider escapes every bounding box) and *mortal* (some patterns die out), the combination
he finds shared by the rules with the richest engineering. He also stresses that Life's
famous constructions are designed, not found in random soup, and that almost nothing is
proved about random Life fields ([[fertile-and-mortal-rules](pages/fertile-and-mortal-rules.md)]).[^26]

**Formal definitions and undecidability (Kari 2005).** Kari defines Life's objects in
terms of finite configurations c and the global map G: a still life is a finite fixed
point, G(c) = c; an oscillator is a finite c with Gᵏ(c) = c for some k ≥ 2; a glider (in
general, any spaceship) is a finite c with Gᵏ(c) equal to a translate of c; a glider gun
is periodic like an oscillator and emits one or more gliders each period. His examples
are a period-two oscillator, a period-four glider and a period-30 glider gun. Random
starts quickly produce such objects, which interact by collisions "leading to
extraordinary complexity".[^27] For any Turing machine M one can build a finite Life
configuration that *dies*, meaning it eventually becomes all-dead, iff M halts on the
blank tape. So Life is computationally universal and **whether a finite configuration
dies is undecidable** (Berlekamp, Conway and Guy).[^28] Life's gliders correspond to the
signals of class-4 1D rules such as [[rule-110](pages/rule-110.md)], but signals cross
far more easily in two dimensions.[^29]

## Appearances in Sources

- [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] - Life as the model for class 4
- [[cgol-ch9-universal-computation](pages/cgol-ch9-universal-computation.md)] - explicit programmable computers: registers, APGsembly, π calculator
- [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] - B3/S23 and why, early history, soup and ash, guns and puffers, methuselahs, Gardens of Eden
- [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] - Gardner 1970: design goals, the rule, hand procedure, first named patterns, speed of light, the growth conjecture
- [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] - §2.6: formal definitions of still lifes, oscillators, gliders and guns; Theorem 1 (universality, undecidable death)
- [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] - Sec. V: the rule, standard structures, statistics from random starts, Garden-of-Eden size, universality via glider streams
- [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] - λ = 0.273, gliders and blinkers as signals and storage

## Related Concepts

- [[wolfram-classes](pages/wolfram-classes.md)] - Life is the template for class 4
- [[apgsembly](pages/apgsembly.md)] - programming computers built in Life
- [[metacell](pages/metacell.md)] - Life patterns that emulate other rules
- [[still-life](pages/still-life.md)], [[oscillator](pages/oscillator.md)], [[spaceship](pages/spaceship.md)] - the three basic pattern classes
- [[glider](pages/glider.md)], [[block](pages/block.md)], [[beehive](pages/beehive.md)], [[blinker](pages/blinker.md)], [[r-pentomino](pages/r-pentomino.md)], [[pulsar](pages/pulsar.md)], [[pentadecathlon](pages/pentadecathlon.md)] - named patterns
- [[moore-neighbourhood](pages/moore-neighbourhood.md)] - the eight-neighbour cell
- [[fertile-and-mortal-rules](pages/fertile-and-mortal-rules.md)] - Life is both
- [[life-like-cellular-automaton](pages/life-like-cellular-automaton.md)] - the B/S rule family
- [[gosper-glider-gun](pages/gosper-glider-gun.md)], [[queen-bee](pages/queen-bee.md)], [[twin-bees](pages/twin-bees.md)], [[switch-engine](pages/switch-engine.md)], [[light-middle-heavyweight-spaceships](pages/light-middle-heavyweight-spaceships.md)], [[familiar-fours](pages/familiar-fours.md)] - more patterns
- [[methuselah](pages/methuselah.md)], [[soup-search](pages/soup-search.md)] - long-lived patterns and how natural objects are found
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

[^1]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] §1.8, p.26 - "Conway's Game of Life was initially studied by John Conway and some of his collaborators at Cambridge University, as well as a research group led by Bill Gosper at MIT, in 1969 and 1970. It then received mainstream attention in 1970 due to an article that Martin Gardner wrote"
[^2]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] pp.1-2 [synthesis] - Life belongs to "a growing class of what are called 'simulation games'"; "Conway chose his rules carefully, after a long period of experimentation, to meet three desiderata"; "In brief, the rules should be such as to make the behavior of the population unpredictable"
[^3]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.2 [synthesis] - "each cell of the checkerboard (assumed to be an infinite plane) has eight neighboring cells, four adjacent orthogonally, four adjacent diagonally"; survivals with two or three neighbours; deaths with four or more or with one or none; births on exactly three
[^4]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.3 [synthesis] - cells "evolve in discrete timesteps (called generations or ticks)"; "these rules are applied to every square in the grid simultaneously"
[^5]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.4-5 [synthesis] - "the Game of Life is described by the rulestring B3/S23"; "2^18 = 262 144 distinct Life-like cellular automata"; Life is special for simple rules, a balance "between being chaotic and stable", and being "the most well-studied rule"
[^6]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.637 - "The game of 'Life' is an example of a special class of 'totalistic' cellular automata, in which the value of a site depends only on the sum of the values of its neighbors at the previous time step"
[^7]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.27 - "there was no pre-made Life simulation software for early enthusiasts to use, these patterns were often evolved by hand using graph paper, checkers, or the board and stones from the game Go"
[^8]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.2 [synthesis] - Conway's four-step procedure with black and white counters; "newborn counters play no role in causing other deaths and births"
[^9]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.5 - "Conway sometimes uses a PDP-7 computer with a screen on which he can observe the changes. The program was written by M. J. T. Guy and S. R. Bourne"
[^10]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] pp.2-3 [synthesis] - most starting patterns reach still lifes or oscillate forever; a few die out, sometimes "after a great many generations"; patterns with no initial symmetry tend to become symmetrical; [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.8 - "Since Life's rules do not care about the orientation of patterns, symmetry can never be broken once it has formed"
[^11]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.7 - "Still lifes, oscillators, and spaceships are the three most basic types of objects that we will study in Life, and they form the building blocks of all of the more complicated patterns"
[^12]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.6-9,16-17 [synthesis] - "soup" and "ash"; block, beehive, blinker, glider among objects that "frequently appear in the ash"; pulsar and pentadecathlon common; traffic light and honey farm formations; methuselah defined; the R-pentomino "takes 1 103 generations to stabilize"
[^13]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.637 [synthesis] - structures separated by four or more unfilled sites coexist without interference
[^14]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] pp.4-5 [synthesis] - king's move called the "speed of light"; "the maximum speed diagonally is a fourth the speed of light"; orthogonal movement "cannot exceed half the speed of light"; "the glider is a 'featherweight spaceship'"
[^15]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.11 [synthesis] - "Patterns that create glider streams are called glider guns"; the Gosper glider gun "was the first such pattern ever to be discovered"; n.10: it "earned Gosper a $50 reward from Conway himself"
[^16]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.14-15 [synthesis] - "An object like this one, which moves but leaves periodic junk behind it, is called a puffer"; "puffers based on switch engines are the only infinitely growing patterns that have ever formed as a result of randomly filling some portion of the Life plane"
[^17]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.11 - "This is how most recent discoveries in the Game of Life have been made ... we will combine simple patterns and reactions that we have already seen into more complicated patterns"
[^18]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.637 [synthesis] - a disordered state of N² cells usually evolves to a steady state within about N² time steps, typically an order of magnitude quicker; very few configurations visited; glider guns very rarely produced; density of L-site structures decreases like e^(−L₋)/L
[^19]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.22-23 [synthesis] - n.30 "almost all large patterns are Gardens of Eden"; Fig. 1.36(a) "An orphan with 45 live cells, found by Nicolay Beluchenko in 2009", the smallest known by live cells
[^20]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.639 [synthesis] - glider streams from glider guns used as wires, bits as presence or absence of gliders; meeting points determine crossing or a "NAND gate"; memories required; "The Life-game cellular automaton is thus computationally universal"; binary adders; circuits run slower "only by a constant multiplicative factor"
[^21]: [[cgol-ch9-universal-computation](pages/cgol-ch9-universal-computation.md)] pp.271,283,296-300 [synthesis] - original universality constructions "monstrously large and only mostly pieced together"; toolkit "Developed by Adam P. Goucher in 2009 and 2010"; sliding block registers already "Turing complete"; §9.6 π calculator, Fig. 9.15
[^22]: [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] pp.385-386,391 [synthesis] - the 0E0P metacell "can actually emulate a huge variety of 2D cellular automata besides Life ... any pattern from one of those other cellular automata can be straightforwardly 'imported' into Life"; 2^18 times as large, 2^36 times as slow; emulates "the 2^511 of them that send a dead cell with no live neighbors to a dead cell"
[^23]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] pp.25-26 [synthesis] - "The λ value for the Game of Life (λ_Life = 0.273) lies within the transition region for K = 2, N = 9 2D CAs"; the universality proof "employs propagating 'gliders' as signals and the period-2 'blinkers' as storage elements"
[^24]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] pp.30-31 [synthesis] - code 20 behaviour "strongly reminiscent of the two-dimensional (essentially totalistic) cellular automaton known as the 'Game of Life'"; "the speculation that class 4 cellular automata are characterized by the capability for universal computation"
[^25]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] p.35 - "Bak has suggested that Conway's game of Life is a self-organized critical system, although he does not bring Life's computational capacity into the discussion."
[^26]: [[eppstein-2010-growth-and-decay-in-life-like-ca](pages/eppstein-2010-growth-and-decay-in-life-like-ca.md)] pp.4-6,10,14 [synthesis] - fertility shown by growth patterns such as Life's glider; fading patterns in Life's undecidability proof; "the rules most likely to support interesting patterns are the ones that are both fertile and mortal"; "many of the most interesting patterns in Life were formed by human engineering"; "For the Game of Life, what we know rigorously is limited to random states in which the probability of a cell being live is a number ε that is very close to zero"
[^27]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.10-11 [synthesis] - Game of Life by Conway; still life, oscillator, glider, glider gun defined via finite configurations; Fig. 5: still life, period two oscillator, period four glider, period 30 glider gun; objects emerge from random configurations and interact through collisions, "leading to extraordinary complexity"
[^28]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.11 [synthesis] - "for any given Turing machine M one can effectively construct a finite GOL configuration that dies if and only if machine M halts on the blank tape"; Theorem 1 (Berlekamp et al. [6])
[^29]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.11 [synthesis] - "gliders in GOL are analogous to the complicated localized structures, or signals, that emerge in class 4 elementary CA"; "in two dimensions it is much easier to make signals cross each other"
