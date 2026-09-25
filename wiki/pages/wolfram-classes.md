---
title: Wolfram Classes
category: Concepts
summary: Wolfram's four behaviour classes for one-dimensional cellular automata started from random states - (1) uniform, (2) separate fixed or periodic structures, (3) chaotic, (4) complex localized structures - analogous to limit points, limit cycles and strange attractors, with class 4 conjectured universal and so unpredictable
tags: [concept, classification, wolfram, attractors, predictability, universality]
sources: [universality-and-complexity-in-cellular-automata, statistical-mechanics-of-cellular-automata]
created: 2026-09-24
updated: 2026-09-24
---

# Wolfram Classes

## Description

The **Wolfram classes** are four kinds of behaviour that Wolfram found when he started
one-dimensional cellular automata from random initial states. A random ("disordered")
state is one where each cell takes each of its k values independently and with equal
probability. The individual patterns differ from rule to rule, but each one falls into one
of four qualitative classes:[^1]

| Class | What evolution leads to | Dynamical-systems analogue | Example codes (k = 2, r = 2 totalistic) |
|---|---|---|---|
| 1 | a uniform state, every cell the same | limit point | 0, 4, 16, 32, 36, 48, 54, 60, 62 |
| 2 | separate simple structures, fixed or periodic | limit cycle | 8, 24, 40, 56, 58 |
| 3 | a chaotic, aperiodic pattern | chaotic ("strange") attractor | 2, 6, 10, 12, 14, 18, 22, 26, 28, 30, 34, 38, 42, 44, 46, 50 |
| 4 | complex localized structures, some long-lived | none; conjectured universal computation | 20, 52 |

The codes are [[totalistic-cellular-automaton](pages/totalistic-cellular-automaton.md)]
code numbers.[^1][^2] The same classes appear for k = 3 and k = 5 rules and for larger
ranges. Changing the random start changes the details but not the class. Wolfram
conjectures that the four classes cover every one-dimensional cellular automaton.[^3]
Early looks at two-dimensional rules (demonstrations by Toffoli, Margolus and Vishniac,
cited via Wolfram) suggest the same four classes there.[^4]

**How common each class is.** Fractions of legal totalistic rules, from Wolfram's
Table I:[^5]

| Class | k = 2, r = 1 | k = 2, r = 2 | k = 2, r = 3 | k = 3, r = 1 |
|---|---|---|---|---|
| 1 | 0.50 | 0.25 | 0.09 | 0.12 |
| 2 | 0.25 | 0.16 | 0.11 | 0.19 |
| 3 | 0.25 | 0.53 | 0.73 | 0.60 |
| 4 | 0 | 0.06 | 0.06 | 0.07 |

Class 3 takes over as k and r grow. Class 4 is rare and does not occur among the
[[elementary-cellular-automaton](pages/elementary-cellular-automaton.md)] rules
(k = 2, r = 1), which fall into classes 1-3.[^5][^6] Own reasoning: Wolfram's 1983
"simple" elementary rules are classes 1 and 2, and his "complex" ones are class 3. The
1983 paper already compared them to limit points and cycles on one side and strange
attractors on the other.[^7]

**What the rule alone tells you.** Very little can be read directly off a rule. Two things
can. If a block of nonzero cells surrounded by zeros can never grow, the rule is class 1
or 2. A totalistic rule whose output rises with the neighbourhood total has no "growth
inhibition" and is also class 1 or 2.[^8] Composing two rules in either order (F₁F₂ or
F₂F₁) gives the same class.[^9] *Reducible* rules, where some values or some sublattice of
cells evolve independently of the rest, are left out. They can mix classes, with
"membranes" of one value separating class 3 or 4 regions.[^10]

### The classes one by one

**Class 1.** Almost every start reaches the same uniform state in finitely many steps, so
all information about the start is lost. The spatial and temporal dimensions of the
attractor are zero. Exceptional starts that cycle instead seem to form a set of measure
zero. For code 60 the usual final state is not all-0, so the all-0 state itself is
exceptional.[^11]

**Class 2.** These rules act as "filters". They pick out particular short sequences in the
start and turn each into a separate simple structure. So the final statistics depend on
how often those sequences occur in the start, and there is no unique long-run
distribution. Wolfram notes this makes them directly useful for digital image
processing.[^12] A change to the start affects only a finite region, usually about r
cells wide, so the average spreading speed is zero, and the temporal and mapping
dimensions vanish ([[set-and-measure-entropy](pages/set-and-measure-entropy.md)]).[^12]
The structures are fixed or have short periods. Under codes 8 and 40 the only persistent
structure is 111, under code 24 it is 111 and 1111, and under code 56 it is any run of two
or more 1s.[^13] In general the set of persistent structures of a class 2 rule is a
*regular language*, a set of strings that a finite automaton can recognize.[^14]

**Class 3.** Almost every start leads to aperiodic patterns whose statistics soon stop
depending on the start. The density of nonzero cells settles to a fixed value, often
near 1/k.[^15] Patterns range from very irregular (code 10) to fairly regular (code 12).
The regular ones have many triangular "clearings" of cells with the same value. Clearing
density falls with size n roughly as σ⁻ⁿ, and σ varies continuously between rules, so
there is no sharp line between regular and irregular class 3 rules.[^16] Changes always
spread at a nonzero speed, so spatial and temporal dimensions are nonzero.[^17] From a
single nonzero cell, some class 3 rules grow self-similar fractals
([[fractal-dimension](pages/fractal-dimension.md)]).[^18] The
[[additive-cellular-automaton](pages/additive-cellular-automaton.md)] rules are the most
chaotic case, producing every block of every length.[^19] More regular class 3 rules show
a larger drop in entropy, which Wolfram reads as more
[[self-organization](pages/self-organization.md)] through more irreversibility.[^20]

**Class 4.** The example is code 20 (k = 2, r = 2). From most small random starts all
cells die. From a few, stable or periodic structures persist, and some structures move.
Moving structures that can be reflected give final states with any cycle length.[^21]
These behaviours are "strongly reminiscent" of the [[game-of-life](pages/game-of-life.md)],
which is computationally universal. Wolfram conjectures that class 4 rules can carry out
universal computation ([[universal-turing-machine](pages/universal-turing-machine.md)]).
He argues that k = 2, r = 1 rules are too simple for this, but the class 4 rules at
k = 2, r = 2 and k = 3, r = 1 suggest that such simple systems may be universal.[^22]
Their persistent structures show no simple pattern and do not seem to form a regular
language.[^23] Groups of class 4 rules behave alike, which suggests further
subdivision.[^24]

### Predictability

The classes also rank how well a rule's outcome can be predicted from its start:[^25]

- **Class 1.** Every start gives the same end, so prediction is trivial.
- **Class 2.** Each region of the end state depends on a finite region of the start.
- **Class 3.** Changes spread forever at a finite speed, so a region depends on an
  ever-growing part of the start and prediction needs the whole start. Wolfram still
  conjectures that, given the start, a simple algorithm may give a cell's value.[^26]
- **Class 4.** If the rule is universal, the dependence can be arbitrarily complex.
  No general finite algorithm can say whether a start will die out, just as no algorithm
  solves the halting problem. The behaviour can be found by no procedure much simpler
  than running the rule.[^27]

Own reasoning: this is von Neumann's "you cannot build an organ which tells you whether
it can be done", applied to a whole class of rules
([[description-vs-object-complexity](pages/description-vs-object-complexity.md)]).

**Deciding the class.** Whether a given rule is universal cannot be decided in general,
because the structures needed may be arbitrarily large. The smallest moving structure
could involve an arbitrarily long sequence of cells.[^28]

## Appearances in Sources

- [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] - introduces the four classes, their frequencies, their entropies and dimensions, and the class 4 universality conjecture
- [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] - the earlier simple/complex split of the elementary rules

## Related Concepts

- [[totalistic-cellular-automaton](pages/totalistic-cellular-automaton.md)] - the rule family used for most examples
- [[set-and-measure-entropy](pages/set-and-measure-entropy.md)] - the quantities that separate the classes
- [[elementary-cellular-automaton](pages/elementary-cellular-automaton.md)] - k = 2, r = 1, classes 1-3 only
- [[additive-cellular-automaton](pages/additive-cellular-automaton.md)] - the maximally chaotic class 3 rules
- [[fractal-dimension](pages/fractal-dimension.md)] - class 3 growth from a single seed
- [[self-organization](pages/self-organization.md)] - structure from random starts
- [[irreversibility-and-entropy](pages/irreversibility-and-entropy.md)] - attractors and the loss of information
- [[game-of-life](pages/game-of-life.md)] - the 2D universal rule class 4 resembles
- [[universal-turing-machine](pages/universal-turing-machine.md)] - universality and the halting problem
- [[complexity-threshold](pages/complexity-threshold.md)] - class 4 is absent below a certain rule size
- [[stephen-wolfram](pages/stephen-wolfram.md)] - proposed the scheme

[^1]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.5 [synthesis] - Fig. 1, all 32 legal totalistic k = 2, r = 2 rules from a disordered initial configuration (each site 0 or 1 with probability ½); "they appear to fall into four qualitative classes": homogeneous state (codes 0, 4, 16, 32, 36, 48, 54, 60, 62); separated simple stable or periodic structures (8, 24, 40, 56, 58); chaotic pattern (2, 6, 10, 12, 14, 18, 22, 26, 28, 30, 34, 38, 42, 44, 46, 50); complex localized structures, sometimes long-lived (20, 52)
[^2]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] pp.1-2 [synthesis] - attractors of classes 1, 2 and 3 "roughly analogous respectively to the limit points, limit cycles and chaotic ('strange') attractors found in continuous dynamical systems"; class 4 conjectured capable of universal computation
[^3]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.5 [synthesis] - Fig. 2: patterns from different initial states differ in detail but share the qualitative features; Figs. 4-6 (k = 2 r = 3, k = 3 r = 1, k = 5 r = 1) lie in the same four classes; "the general conjecture that the four classes introduced above cover all one-dimensional cellular automata"
[^4]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] pp.5, 8 [synthesis] - two-dimensional cellular automata "also appear to exhibit a few distinct classes of behaviour. Superficial investigations [5] suggest that these classes may in fact be identical to the four found in one-dimensional cellular automata"; [5] Toffoli, Margolus and Vishniac, private demonstrations
[^5]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.5 [synthesis] - Table I, approximate fractions of legal totalistic rules in each class for (k, r) = (2, 1), (2, 2), (2, 3), (3, 1); "With increasing k and r, class 3 becomes overwhelmingly the most common. Classes 1 and 2 are decreasingly common. Class 4 is comparatively rare, but becomes more common for larger k and r."
[^6]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.5 - "Patterns generated by all possible k = 2, r = 1 cellular automata were given in ref. 1, and are found to lie in classes 1, 2 and 3."
[^7]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.607 - "simple rules exhibit simple limit points or limit cycles, while complex rules exhibit phenomena analogous to strange attractors."
[^8]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] pp.3-4 [synthesis] - "Very little information on the behaviour of a cellular automaton can be deduced directly from simple properties of its rule"; without the growth conditions (2.8) "regions containing nonzero sites surrounded by zero sites can never grow, and the cellular automaton must exhibit behaviour of class 1 or 2"; totalistic rules satisfying (2.10) "exhibit no 'growth inhibition' and must therefore similarly be of class 1 or 2"
[^9]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.3 [synthesis] - if F₁F₂ generates a sequence with period π then F₂F₁ must also; "this implies that the rules F₁F₂ and F₂F₁ must yield behaviour of the same class"
[^10]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] pp.3, 5 [synthesis] - "reducible" rules, where sites with particular values or on a particular grid evolve independently, are usually excluded; they may generate patterns with features of several classes, with fixed or propagating "membranes" separating class 3 or 4 regions
[^11]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] pp.21-22 [synthesis] - class 1 evolves after a finite number of steps from almost all initial states to a unique homogeneous state; "limit points"; "completely destroys any information on the initial state"; spatial and temporal dimensions zero; exceptional configurations entering nontrivial cycles appear to be of measure zero; for code 60 the null configuration is exceptional
[^12]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.22 [synthesis] - class 2 serve as "filters" generating separated simple structures from particular (typically short) initial sequences; no unique large-time invariant measure; changes affect final values only within a finite range, typically of order r; λ̄₊ vanishes; temporal and mapping (but not spatial) dimensions vanish; footnote: "They are thus of direct significance for digital image processing"
[^13]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.22 [synthesis] - codes 8, 24, 40, 56 show only stable persistent structures; rule 108 (k = 2, r = 1) and code 198 (k = 3, r = 1) give periodic ones; for codes 8 and 40 only 111 persists, for code 24 111 and 1111, for code 56 any sequence of two or more consecutive 1s
[^14]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] pp.22-23 [synthesis] - "the set of persistent structures generated by any class 2 cellular automaton corresponds to the set of words generated by a regular grammar"; a regular grammar specifies a language whose words "may be recognized by a finite automaton"
[^15]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.23 [synthesis] - class 3 evolution from almost all initial states leads to aperiodic ("chaotic") patterns whose statistical properties are typically the same for almost all initial states; density of nonzero sites tends to a fixed nonzero value, "often close to 1/k"; equilibrium approached roughly exponentially
[^16]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.25 [synthesis] - patterns from highly irregular (code 10) to rather regular (code 12); triangular "clearings"; clearing boundary slopes from 1/k to r sites per step; density of clearings decreases with size n roughly as σ⁻ⁿ; "a continuous range of σ values"; "No sharp distinction appears to exist between class 3 cellular automata yielding regular and irregular patterns"
[^17]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.26 [synthesis] - class 3 "apparently always exhibit a nonzero minimum average propagation speed"; spatial and temporal dimensions should be nonzero
[^18]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.25 [synthesis] - Fig. 9: unbounded growth from a single nonzero site in all cases; rules such as code 2 give asymptotically self-similar fractal curves
[^19]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] pp.27-28 [synthesis] - additive rules reach all blocks of every length, each with exactly k^(2r) predecessors; d⁽ˣ⁾ = d_μ⁽ˣ⁾ = 1; "The configurations generated by additive cellular automata are thus maximally chaotic."
[^20]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.27 [synthesis] - the entropy decrease "is found to be much greater for class 3 cellular automata which generate regular patterns"; "The more regular patterns require a higher degree of self-organization, with correspondingly greater irreversibility, and larger entropy decrease"
[^21]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.30 [synthesis] - Fig. 12, code 20 (k = 2, r = 2): in most cases all sites "die"; in a few, stable or periodic structures persist; in some, propagating structures form; "By arranging for suitable reflections of these propagating structures, final states with any cycle lengths may be obtained"
[^22]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] pp.30-31 [synthesis] - behaviour "strongly reminiscent" of the Game of Life, which is computationally universal; "speculation that class 4 cellular automata are characterized by the capability for universal computation. k = 2, r = 1 cellular automata are too simple to support universal computation; the existence of class 4 cellular automata with k = 2, r = 2 ... and k = 3, r = 1 suggests that with suitable time evolution rules even such apparently simple systems may be capable of universal computation"
[^23]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.33 [synthesis] - the persistent structures of class 4 "typically exhibit no simple patterns, and do not appear to be specified, for example, by regular grammars"; a finite specification is impossible if class 4 is universal
[^24]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.34 - "groups of class 4 cellular automata with different rules often yield qualitatively similar behaviour, and similar sets of persistent structures, suggesting further classification."
[^25]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] pp.2, 34-35 [synthesis] - "The different classes of cellular automaton behaviour allow different levels of prediction"; class 1 "complete prediction is trivial"; class 2 each region of the final state depends only on a finite region of the initial state; class 3 changes "almost always propagate forever at a finite speed", so prediction "requires complete knowledge of the initial state"; class 4 "can be found by no procedure significantly simpler than direct simulation"
[^26]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.2 - "given the necessary set of initial values, it is conjectured that the value of a site in a class 3 cellular automaton may be determined by a simple algorithm."
[^27]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.32 [synthesis] - "no general finite algorithm can predict whether a particular initial configuration in a computationally universal cellular automaton will evolve to the null configuration after a finite time", analogous to "the insolubility of the halting problem for universal Turing machines"; the value "cannot in general be determined by any 'short-cut' procedure much simpler than explicit simulation"
[^28]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.33 [synthesis] - "it is impossible to determine in general whether a particular cellular automaton is capable of universal computation", since the necessary structures "may be arbitrarily complicated"; "the smallest propagating structure might involve an arbitrarily long sequence of site values"
