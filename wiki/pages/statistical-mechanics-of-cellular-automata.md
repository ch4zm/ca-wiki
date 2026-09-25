---
title: Statistical Mechanics of Cellular Automata (Wolfram, 1983)
category: Sources
summary: Wolfram's founding study of one-dimensional two-state "elementary" cellular automata as models of self-organization - rule numbering, simple vs complex rules, fractal growth from a seed, universal statistics from random starts, irreversibility and entropy, and extensions to more states, larger neighbourhoods, two dimensions, and universality
tags: [wolfram, elementary-ca, statistical-mechanics, self-organization, fractals, irreversibility, entropy, universality]
sources: [statistical-mechanics-of-cellular-automata, theory-of-cellular-automata-a-survey]
created: 2026-09-24
updated: 2026-09-24
---

# Statistical Mechanics of Cellular Automata (Wolfram, 1983)

**Source:** raw/wolfram-1983-statistical-mechanics-cellular-automata.pdf (Wolfram, S., *Reviews of Modern Physics* 55(3), 601-644, July 1983; https://doi.org/10.1103/RevModPhys.55.601)
**Date ingested:** 2026-09-24
**Type:** paper

> Locators are the journal's printed page numbers (PDF page n = printed page 600 + n).
> Works Wolfram cites (Grassberger 1982, Martin, Odlyzko and Wolfram 1983, Farmer 1982,
> Smith 1971, Banks 1971, and others) are cited via this paper and have not been read.
> Moore 1962, which he also cites, is
> [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)].

## Summary

Wolfram treats cellular automata as the simplest mathematical models of
*self-organization*: systems that go from disorder to order, which the second law forbids
for closed reversible systems but allows for dissipative, irreversible ones. The stated
long-term aim is to find general laws of self-organizing behaviour "analogous to the laws
of thermodynamics." Cellular automata suit this because space, time and values are all
discrete. Differential equations and iterated maps encode their chaos in the far digits
of real numbers, which cellular automata do not have.[^1]

Almost the whole paper studies one family, the
[[elementary-cellular-automaton](pages/elementary-cellular-automaton.md)]: a line of
cells, each 0 or 1, each updated from itself and its two neighbours. Wolfram names each
rule by the 8-bit number of its rule table and keeps the 32 "legal" rules, meaning rules
that leave the all-0 state alone and are mirror-symmetric.[^2] The rules fall into
**simple** rules, which die out or become uniform, and **complex** rules, which build
structure.[^3] Two complex rules, 90 and 150, are
[[additive-cellular-automaton](pages/additive-cellular-automaton.md)] rules. Superposition
modulo 2 holds for them, so they can be solved exactly, and they act as the paper's
reference cases throughout.[^4]

The paper uses two approaches in turn. **Local** (Sec. III): statistics of the cells
within one configuration, such as density, correlations, and the lengths of runs of equal
values. **Global** (Sec. IV): statistics over the ensemble of all configurations, in the
spirit of phase-space statistical mechanics.[^5] Started from a single 1, the complex rules
grow self-similar patterns with [[fractal-dimension](pages/fractal-dimension.md)] log₂3 ≈
1.59 (1.69 for rule 150).[^6] Started from random noise, they reach an equilibrium whose
statistics do not depend on the starting state. These statistics split into two
universality classes, one for the additive rules and one for all the others
([[self-organization](pages/self-organization.md)]).[^7] What makes this possible is
[[irreversibility-and-entropy](pages/irreversibility-and-entropy.md)]. Many configurations
map to one, entropy falls, and most configurations become unreachable
([[garden-of-eden](pages/garden-of-eden.md)] configurations).[^8]

Sec. V widens the view. It covers more states per cell, larger neighbourhoods, two and more
dimensions, the [[game-of-life](pages/game-of-life.md)], totalistic rules, a simple
self-reproduction in [[rule-90](pages/rule-90.md)], and computational universality. The
paper ends with a conjecture: rules that can simulate each other under short encodings
should share statistical properties, and this may be why the universality classes
exist.[^9]

## Key Takeaways

- **Rule numbering and legality.** There are 2⁸ = 256 three-neighbour binary rules, each
  written as an 8-bit number and quoted in decimal. Quiescence plus reflection symmetry
  cuts this to 32.[^2]
- **Simple vs complex.** From a single 1, rules with 100→0 and 001→0 cannot spread the
  1. Some rules grow a uniform block. Complex rules such as 18, 22 and 90 give nontrivial
  patterns.[^3]
- **Fractals from seeds.** Rule 90 gives Pascal's triangle mod 2, a Sierpinski-type figure
  of dimension log₂3 ≈ 1.59. Every complex rule except 150 gives the same dimension from
  any finite seed, at scales larger than the seed. Wolfram conjectures that much
  self-similarity in nature comes from local, cellular-automaton-like growth.[^6][^10]
- **Density limits independent of the start.** For complex non-additive rules the
  limiting density of 1s does not depend on the starting density: 1/4 for rules 18, 122,
  126 and 146, 3/4 for rule 182, and about 0.35 for rule 22. A mean-field master equation
  gets within 10-20% of these values. The error shows that the evolution builds
  correlations.[^11]
- **Two universality classes.** From random starts, the density of "triangles" (runs of
  equal cells that shrink by one cell per side each step) with base n falls off as λ⁻ⁿ.
  λ ≈ 4/3 for every non-additive complex rule and λ ≈ 2 for the additive rules 90 and 150,
  whatever the initial density.[^7]
- **Sensitivity.** Under non-additive rules a one-cell change grows linearly in Hamming
  distance (the number of cells that differ). Under additive rules it follows the
  single-seed pattern, about τ^0.59 on average over time.[^12]
- **Irreversibility drives organization.** Trajectories merge but never split. From an
  equiprobable ensemble the entropy falls to an equilibrium. For rule 126 the fraction of
  unreachable configurations tends to 1 as the line length N grows.[^8]
- **Finite systems cycle.** Cycles of the complex non-additive rules are far shorter than
  2ᴺ. Cycle periods of rules 90 and 150 depend on number-theoretic properties of N. Cellular
  automata are "more irreversible" than random mappings.[^13]
- **Noise.** Flipping each cell with probability κ destroys structure smoothly, with no
  phase transition. Any κ > 0 changes the global behaviour abruptly, though: the system
  eventually visits every configuration.[^14]
- **Computation.** A cellular automaton is a parallel computer, with the initial
  configuration as its program. Life is universal through glider-stream circuits. Wolfram
  judges elementary rules too simple to be universal.[^15]

## Entities & Concepts

- [[elementary-cellular-automaton](pages/elementary-cellular-automaton.md)] — the family studied
- [[additive-cellular-automaton](pages/additive-cellular-automaton.md)] — rules 90 and 150, the exactly solvable cases
- [[rule-90](pages/rule-90.md)] — the modulo-two rule, the paper's running example
- [[fractal-dimension](pages/fractal-dimension.md)] — self-similar growth from simple seeds
- [[self-organization](pages/self-organization.md)] — order and universal statistics from random starts
- [[irreversibility-and-entropy](pages/irreversibility-and-entropy.md)] — the global, ensemble view
- [[garden-of-eden](pages/garden-of-eden.md)] — unreachable configurations
- [[erasable-configuration](pages/erasable-configuration.md)] - Moore's local form of irreversibility
- [[game-of-life](pages/game-of-life.md)] — the 2D example in Sec. V
- [[cellular-automaton](pages/cellular-automaton.md)] — the general notion, and neighbourhood types
- [[universal-turing-machine](pages/universal-turing-machine.md)] — universality in cellular automata
- [[self-reproduction](pages/self-reproduction.md)] — replication in rule 90

## Relation to Other Wiki Pages

Von Neumann
([[theory-of-self-reproducing-automata](pages/theory-of-self-reproducing-automata.md)])
designed one enormous 29-state rule to carry out a construction. Wolfram does the reverse.
He surveys every rule in the smallest possible family and asks what they do *statistically*.
Their shared ground is thermodynamics. Von Neumann expected a theory of automata to resemble
thermodynamics ([[maxwells-demon](pages/maxwells-demon.md)],
[[probabilistic-logic](pages/probabilistic-logic.md)]). Wolfram makes entropy and
irreversibility measurable in actual cellular automata. The two meet again on
[[garden-of-eden](pages/garden-of-eden.md)] configurations and on
[[self-reproduction](pages/self-reproduction.md)]. Wolfram's rule-90 copier replicates any
pattern, with no description or constructor, through superposition alone. Von Neumann
excluded that kind of trivial replication by requiring inheritable mutation.

Kari's survey
([[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)])
cites this paper for the rule numbering, which it says has become standard. It reports
Wolfram's later four-class scheme
([[classification-of-cellular-automata](pages/classification-of-cellular-automata.md)])
and the universality of [[rule-110](pages/rule-110.md)], an elementary rule outside the
32 legal ones studied here.[^16]

[^1]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] pp.601-602 [synthesis] — second law vs dissipative systems; the goal "to abstract from a study of cellular automata general features of 'self-organizing' behavior and perhaps to devise universal laws analogous to the laws of thermodynamics"; differential equations and iterated maps depend on "high-order digits"; cellular automata use discrete coordinates, variables and time
[^2]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.603 [synthesis] — "elementary" defined; the eight-digit binary rule number used interchangeably with its decimal equivalent; 2⁸ = 256 rules; the quiescence and reflection-symmetry restrictions leave 32 legal rules
[^3]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.604 [synthesis] — Fig. 3 classes: the 1 erased or frozen (local rules 100→0 and 001→0 prevent propagation); uniform expanding structure (50, 122); both termed "simple"; "complex" rules such as 18, 22 and 90 yield nontrivial patterns
[^4]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.604 — "Only rules 0, 90, 150, and 204 are of this form."
[^5]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] pp.607, 621 [synthesis] — Sec. III considers statistics of individual configurations; Sec. IV considers the ensemble of all configurations "in analogy with the Γ-space approach to classical statistical mechanics"
[^6]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] pp.605-606, 616 [synthesis] — rule 90 from one site gives Pascal's triangle mod 2 (Fig. 4) with the recursive construction of Fig. 5, dimension log₂3 ≈ 1.59; rule 150 gives log₂(2φ) ≈ 1.69 (Fig. 6)
[^7]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] pp.617, 619 [synthesis] — T(n) ~ λ⁻ⁿ (Eq. 3.7); λ ~ 4/3 for nonadditive rules, λ ~ 2 for additive rules, regardless of initial density; Fig. 16 groups 18, 22, 122, 126, 146, 182 vs 90, 150
[^8]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] pp.622-625 [synthesis] — local irreversibility: trajectories "may coalesce, but may never split"; unreachable configurations; rule 126 unreachable fraction tends to one (Fig. 23); entropy decreases to an equilibrium value (Fig. 24)
[^9]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] pp.629-630, 641 [synthesis] — "so long as the encoding defined by the interpreter is sufficiently simple, the statistical characteristics ... will be shared"; this capability "may well form a basis for the universality found in the statistical properties of various cellular automata"
[^10]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.617 [synthesis] — patterns from any simple initial state under complex rules (except 150) share self-similarity with dimension log₂3 at scales ≫ n₀; conjecture that many self-similar natural systems "attain this structure through local processes which follow cellular automaton rules"
[^11]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] pp.614-615 [synthesis] — Grassberger's results ρ∞ = 1/4 for 18, 146, 122, 126 and 3/4 for 182, independent of ρ₀; rule 22 ρ∞ = 0.35 ± 0.02 by simulation; master equation (3.4) gives equilibrium densities "within 10-20% of the exact values", the discrepancies reflecting correlations
[^12]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] pp.621-622 [synthesis] — Hamming distance under rule 90 given by the single-site pattern, time-averaged ~ τ^0.59; under rule 126 it increases linearly, H_τ ≈ τ; divergence into "an exponentially increasing volume"
[^13]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] pp.626-629 [synthesis] — Poincaré recurrence; rule 126 cycle and transient lengths far below 2ᴺ (Fig. 26); rules 90/150 cycle periods via Martin et al.; comparison with random mappings: cellular automaton evolution "is 'more irreversible' than iteration of a random mapping would imply"
[^14]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] pp.620, 629 [synthesis] — site reversal with probability κ; "the transition to disorder is a continuous one, and no phenomenon analogous to a 'phase transition' is found"; global properties "may, however, change discontinuously": with κ > 0 every configuration is eventually visited (Fig. 27)
[^15]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] pp.629-630, 639 [synthesis] — initial configuration as "program" and "initial data"; Life universal via glider streams as wires and NAND gates; the elementary rules "are not of sufficient complexity to be capable of universal computation"
[^16]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.8, 11 [synthesis] - Wolfram's naming scheme "has since become standard", the Wolfram number [73]; classes (W1)-(W4) from [74]; Theorem 2 (rule 110 computationally universal)
