---
title: Universality and Complexity in Cellular Automata (Wolfram, 1984)
category: Sources
summary: Wolfram's proposal that every one-dimensional cellular automaton falls into one of four behaviour classes (homogeneous, periodic, chaotic, complex), with set and measure entropies, dimensions and propagation speeds to tell them apart, and the conjecture that class 4 rules are computationally universal and so unpredictable
tags: [wolfram, classification, universality, entropy, dimension, totalistic, computation, undecidability]
sources: [universality-and-complexity-in-cellular-automata]
created: 2026-09-24
updated: 2026-09-24
---

# Universality and Complexity in Cellular Automata (Wolfram, 1984)

**Source:** raw/wolfram-1984-universality-and-complexity-in-cellular-automata.pdf (Wolfram, S., *Physica D* 10(1-2), 1-35, 1984; https://doi.org/10.1016/0167-2789(84)90245-8)
**Date ingested:** 2026-09-24
**Type:** paper

> Locators are the journal's printed page numbers, which match the PDF page numbers. In
> the local scan, printed p.18 is replaced by the caption page for the colour plates, so
> eqs. (4.17)-(4.20) and Fig. 7 are missing and are not summarized here. Works Wolfram
> cites (Martin, Odlyzko and Wolfram 1983, Lind 1984, Grassberger 1982, Milnor's
> unpublished notes, Chaitin 1977, Bennett 1982, and others) are cited via this paper and
> have not been read.

## Summary

This paper follows up
[[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)].
That paper studied the 32 legal
[[elementary-cellular-automaton](pages/elementary-cellular-automaton.md)] rules. This one
lets each cell take k values and look r cells to each side (the *range*), and samples
many more rules.[^1] Most examples are
[[totalistic-cellular-automaton](pages/totalistic-cellular-automaton.md)] rules, where a
cell's new value depends only on the sum of its neighbourhood. Wolfram reports that these
behave like all rules with the same k and r.[^2] Started from random initial states, every
rule he looked at fell into one of four classes, the
[[wolfram-classes](pages/wolfram-classes.md)]:[^3]

1. evolution to a uniform state;
2. evolution to separate simple structures that are fixed or repeat periodically;
3. evolution to a chaotic pattern;
4. evolution to complex localized structures, some of them long-lived.

He conjectures that the four classes cover every one-dimensional cellular automaton. He
compares classes 1-3 to the limit points, limit cycles and chaotic ("strange")
attractors of continuous dynamical systems.[^4]

To make the classes quantitative, Sec. 4 defines
[[set-and-measure-entropy](pages/set-and-measure-entropy.md)] for blocks of cells in space,
in time and in space-time patches. It also defines the dimensions these entropies give in
the limit, and the speeds at which changes spread.[^5] Each class then gets its own
section. Class 2 rules act as "filters", and their persistent structures form a *regular
language* (a set of strings a finite automaton can recognize).[^6] Class 3 rules keep
spreading small changes, so their entropies and dimensions stay above zero.[^7] Sec. 7
also gives a finite test for whether a rule can produce every possible block, which is a
test for [[garden-of-eden](pages/garden-of-eden.md)] blocks.[^8]

Class 4 gets the strongest claim. Wolfram conjectures that class 4 rules can carry out
universal computation, as the [[game-of-life](pages/game-of-life.md)] can. If so, their
long-run behaviour is undecidable. Whether a given start dies out cannot be predicted in
general, and there is no shortcut much simpler than running the rule.[^9] The four classes
therefore also rank how far a rule's outcome can be predicted from its start.[^10]

## Key Takeaways

- **Four classes.** Among the 32 legal totalistic rules with k = 2 and r = 2, codes 0, 4,
  16, 32, 36, 48, 54, 60 and 62 are class 1. Codes 8, 24, 40, 56 and 58 are class 2. Sixteen
  codes, including 10, 12 and 42, are class 3. Codes 20 and 52 are class 4.[^3]
- **How common each class is.** As k and r grow, class 3 becomes most of the rule space.
  Classes 1 and 2 become rarer. Class 4 is rare, but it becomes more common for larger
  k and r. It is absent for k = 2, r = 1, the elementary rules.[^11]
- **No random space-time patterns.** Every cell in a space-time patch is fixed by the
  patch's edge (its "rind"). So the information per cell in a large patch tends to zero,
  and a cellular automaton can never generate a random space-time pattern.[^12]
- **Speed bounds entropy.** The ratio of temporal to spatial entropy is at most the
  largest speed at which features can travel, which is at most r cells per step.[^13]
- **Class 2 is regular.** After any finite number of steps, the configurations a rule can
  produce form a regular language. For class 2 the persistent structures stay regular in
  the long run.[^6]
- **A finite reachability test.** A predecessor-building procedure (from J. Milnor's
  unpublished notes, cited via this paper) finds the *critical block length* Xc, the
  shortest length at which some block can no longer be produced. It decides in finitely
  many steps whether every block of every length can be produced.[^8]
- **Injective at one end means everything is reachable.** If the rule is one-to-one in its
  leftmost or rightmost input, every block can be produced and the spatial set dimension
  is 1. Additive rules are the extreme case, since every block has exactly k^(2r)
  predecessors, so they are "maximally chaotic".[^14]
- **Rule 18 in time.** There is evidence that the time sequences at one cell under
  elementary rule 18 are exactly the sequences with no two adjacent 1s. That would give a
  temporal set dimension log₂φ ≈ 0.694, where φ is the golden ratio.[^15]
- **Class 4 in practice.** For code 20, about 93% of small starting patterns die out. The
  other 7% leave one of a handful of persistent structures, some of which move. Wolfram
  finds most of the parts needed for a universality proof, but not a glider gun.[^16]
- **No infinite-volume limit for class 4.** Rare patterns in an infinite random start,
  such as a glider gun or even a self-reproducing "organism", could take over the
  long-run statistics. So class 4 may have no smooth large-system limit.[^17]

## Entities & Concepts

- [[wolfram-classes](pages/wolfram-classes.md)] - the four-class scheme, the paper's main claim
- [[set-and-measure-entropy](pages/set-and-measure-entropy.md)] - the entropies, dimensions and speeds of Sec. 4
- [[totalistic-cellular-automaton](pages/totalistic-cellular-automaton.md)] - the rule family most examples use, and the code numbering
- [[stephen-wolfram](pages/stephen-wolfram.md)] - the author
- [[cellular-automaton](pages/cellular-automaton.md)] - the general k-value, range-r formalism
- [[elementary-cellular-automaton](pages/elementary-cellular-automaton.md)] - the k = 2, r = 1 case, which has classes 1-3 only
- [[additive-cellular-automaton](pages/additive-cellular-automaton.md)] - the maximally chaotic class 3 rules
- [[fractal-dimension](pages/fractal-dimension.md)] - self-similar class 3 patterns from single seeds
- [[irreversibility-and-entropy](pages/irreversibility-and-entropy.md)] - attractors, state-transition diagrams and reachable fractions
- [[self-organization](pages/self-organization.md)] - structure from random starts, now ranked by irreversibility
- [[garden-of-eden](pages/garden-of-eden.md)] - unreachable blocks and the critical block length
- [[game-of-life](pages/game-of-life.md)] - the universal 2D rule class 4 is compared to
- [[universal-turing-machine](pages/universal-turing-machine.md)] - universality, the halting problem and undecidability
- [[self-reproduction](pages/self-reproduction.md)] - a self-reproducing "organism" hidden in a long random start
- [[permutive-map](pages/permutive-map.md)] - Hedlund's name for rules one-to-one in an end variable
- [[shift-dynamical-system](pages/shift-dynamical-system.md)] - configurations as points of a Cantor set

## Relation to Other Wiki Pages

The paper replaces the simple/complex split of Wolfram (1983) with four classes. Own
reasoning: the 1983 "simple" rules correspond to classes 1 and 2, and the 1983 "complex"
rules correspond to class 3. The 1983 paper had already compared the two groups to limit
points and cycles on one side and strange attractors on the other
([[elementary-cellular-automaton](pages/elementary-cellular-automaton.md)]). Class 4 is
new, and it appears only beyond the elementary rules. That fits the 1983 judgment that
elementary rules are too simple for universal computation.

The paper also meets Hedlund's symbolic dynamics
([[endomorphisms-and-automorphisms-of-the-shift-dynamical-system](pages/endomorphisms-and-automorphisms-of-the-shift-dynamical-system.md)])
without citing it. Wolfram treats configurations as points of a Cantor set and rules as
continuous, shift-invariant maps of it, as on
[[shift-dynamical-system](pages/shift-dynamical-system.md)]. His two reachability results
match two of Hedlund's theorems (own reasoning). "One-to-one in an end argument means
every block is reachable" is Hedlund's theorem that a
[[permutive-map](pages/permutive-map.md)] is onto. "Every block has exactly k^(2r)
predecessors" is the balanced-preimage count on
[[surjective-shift-endomorphism](pages/surjective-shift-endomorphism.md)], with window
n = 2r + 1.

On computation, the class 4 conjecture links back to von Neumann. His
[[universal-turing-machine](pages/universal-turing-machine.md)] discussion stresses that
you "cannot build an organ which tells you whether it can be done". Wolfram draws the same
consequence for cellular automata: in a universal rule, detailed behaviour can be found
only by running it. Own reasoning: this parallels
[[description-vs-object-complexity](pages/description-vs-object-complexity.md)], where a
complex enough automaton is simpler than any description of what it does.

[^1]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] pp.1-2 [synthesis] - ref. 1 showed some cellular automata capable of complex behaviour; this paper discusses "the nature of this complex behaviour, its characterization, and classification"; site values 0 through k − 1; range r, neighbourhood of at most 2r + 1 sites; elementary cellular automata have k = 2, r = 1
[^2]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] pp.2-3, 5 [synthesis] - totalistic rules take αⱼ = 1 in eq. (2.2), so a site depends only on the total of the neighbourhood; "totalistic rules appear to exhibit no special simplifications, and give rise to behaviour typical of all cellular automaton rules with given k and r"
[^3]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.5 [synthesis] - Fig. 1, the 32 legal totalistic k = 2, r = 2 rules from a disordered state; classes: homogeneous state (codes 0, 4, 16, 32, 36, 48, 54, 60, 62); separated simple stable or periodic structures (8, 24, 40, 56, 58); chaotic pattern (2, 6, 10, 12, 14, 18, 22, 26, 28, 30, 34, 38, 42, 44, 46, 50); complex localized structures, sometimes long-lived (20, 52)
[^4]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] pp.1-2, 5 [synthesis] - "the general conjecture that the four classes introduced above cover all one-dimensional cellular automata"; attractors in classes 1, 2 and 3 "roughly analogous respectively to the limit points, limit cycles and chaotic ('strange') attractors found in continuous dynamical systems"
[^5]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] pp.8, 15-21 [synthesis] - Sec. 4: spatial set and measure entropies (4.1)-(4.2); set dimension (4.15); temporal entropies and dimensions (4.21)-(4.23); space-time patch entropies (4.25)-(4.26); mapping entropy h (4.33); propagation speeds λ₊ (4.37) and λ̄₊, λ̄₋; Hamming distance H(t)
[^6]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] pp.22-23 [synthesis] - class 2 cellular automata serve as "filters"; the set of persistent structures "corresponds to the set of words generated by a regular grammar"; configurations reached after one step recognized by a finite automaton with at most 2^(k^(2r)) states; for class 2 the number of relevant initial sites m "apparently remains finite", so persisting configurations are specified by a regular grammar
[^7]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.26 [synthesis] - class 3 "apparently always exhibit a nonzero minimum average propagation speed"; small changes lead to increasingly large changes; spatial and temporal dimensions "should be nonzero for all class 3 cellular automata"
[^8]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.27 [synthesis] - progressive construction of predecessors from Sec. 6 [21]; Xc determined from the finite-automaton state transition graph; the stop node ψ = 0 reached for finite Xc, closed cycles for infinite Xc; at most 2^(k^(2r)) tests; "a finite algorithm for determining whether all possible arbitrarily long sequences of site values may be generated by evolution with a particular cellular automaton rule"
[^9]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] pp.30-32 [synthesis] - class 4 structures "strongly reminiscent" of the Game of Life, which is computationally universal; "speculation that class 4 cellular automata are characterized by the capability for universal computation"; no general finite algorithm can predict whether a configuration evolves to the null configuration, analogous to the halting problem; the value "cannot in general be determined by any 'short-cut' procedure much simpler than explicit simulation"
[^10]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] pp.2, 34-35 [synthesis] - "The different classes of cellular automaton behaviour allow different levels of prediction of the outcome"; class 1 trivial; class 2 needs a small initial region; class 3 needs complete knowledge of the initial state; class 4 "can be found by no procedure significantly simpler than direct simulation"
[^11]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.5 [synthesis] - Table I fractions of legal totalistic rules (classes 1-4): k = 2, r = 1: 0.50, 0.25, 0.25, 0; k = 2, r = 2: 0.25, 0.16, 0.53, 0.06; k = 2, r = 3: 0.09, 0.11, 0.73, 0.06; k = 3, r = 1: 0.12, 0.19, 0.60, 0.07; "class 3 becomes overwhelmingly the most common ... Class 4 is comparatively rare, but becomes more common for larger k and r"
[^12]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] pp.19-20 [synthesis] - all sites in a T × X patch are determined by the "rind", X + 2r(T − 1) sites (4.29); the information per site in a T × X patch tends to zero; "The evolution of cellular automata can therefore never generate random space-time patterns."
[^13]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] pp.20-21 [synthesis] - maximum propagation speed λ₊ defined from the minimum R on which a site's value after many steps depends (4.37), with λ₊ ≤ r (4.38); "The ratio of temporal to spatial entropy is thus bounded by the maximum propagation speed in the cellular automaton"
[^14]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] pp.27-28 [synthesis] - for additive rules "all possible blocks of any length X may be reached, and have exactly k^(2r) predecessors of length X + 2r", so d⁽ˣ⁾ = d_μ⁽ˣ⁾ = 1 (7.1) and they are "maximally chaotic"; s⁽ˣ⁾(X) = 1 for all X if F is injective in its first or last argument, proved by induction; "A necessary condition is not known"
[^15]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.29 [synthesis] - for k = 2, r = 1 rule 18, "some evidence [21] that all possible temporal sequences which contain no 11 subsequences may appear", N⁽ᵗ⁾(T) = F_T (Fibonacci), suggesting d⁽ᵗ⁾ = log₂φ ≈ 0.694
[^16]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] pp.30-33 [synthesis] - Fig. 13 and Table III persistent structures of code 20 from initial regions of 20 or fewer sites, periods 1, 2, 4, 9, 22, 38, some propagating (R/L); Fig. 14 asymptotic "halting probability" around 0.93, 7% generate persistent structures; the structures "represent a significant fraction of those necessary"; "A major missing element is ... the 'glider gun'"
[^17]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.33 [synthesis] - for class 4 "no simple smooth infinite volume limit exists"; a sufficiently long initial sequence should contain a glider-gun seed; "a sufficiently long (but finite) initial sequence should evolve to behave as a self-reproducing 'organism', capable of eventually taking over its environment"
