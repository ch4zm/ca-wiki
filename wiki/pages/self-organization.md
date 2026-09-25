---
title: Self-Organization (cellular automata)
category: Concepts
summary: Order arising from disorder under deterministic local rules - complex cellular automata turn random initial states into equilibria with start-independent densities, correlations, and triangle/sequence spectra that fall into two universality classes (λ ≈ 4/3 non-additive, λ ≈ 2 additive)
tags: [concept, self-organization, universality, statistical-mechanics, wolfram, noise]
sources: [statistical-mechanics-of-cellular-automata, computation-at-the-edge-of-chaos]
created: 2026-09-24
updated: 2026-09-24
---

# Self-Organization (cellular automata)

## Description

**The problem.** By the second law, an isolated, microscopically reversible system tends
toward maximum entropy and maximum disorder. Dissipative systems, or systems open to their
environment, can instead move from disorder to order: snowflakes, turbulent flow, living
things. Wolfram proposes cellular automata as the simplest models of this. They are simple
enough to analyse in detail but still complex enough to show the phenomena.[^1]

**Disordered states.** A configuration is *disordered* if the values at different cells
are statistically independent: discrete white noise, specified by a single probability p
that a cell is 1. Any departure of a statistic from its disordered value signals order,
that is, correlations between cells.[^2]

**The core observation.** Start a complex
[[elementary-cellular-automaton](pages/elementary-cellular-automaton.md)] from random
noise and the evolution destroys the independence of the cells. It builds correlations
and visible structure, above all *triangles*: runs of equal cells that appear together and
then shrink by one cell per side each step. Wolfram calls this "the essence of
self-organization in cellular automata".[^3]

**Measures, from coarse to fine:**

- **Density.** For complex non-additive rules the density of 1s tends to a limit that does
  not depend on the starting density ρ₀: 1/4 for rules 18, 122, 126 and 146, 3/4 for rule
  182, and 0.35 ± 0.02 for rule 22 (found by simulation). Wolfram calls a universal ρ∞
  characteristic of complex rules.[^4] Block densities stay Gaussian with width about
  1/√b ("law of large numbers"). For non-additive rules, averaging over space and averaging
  over time give the same limit.[^5]
- **Mean field fails a little.** A master equation that ignores correlations and tracks
  only the density predicts ½ for rule 90, 1 − 1/√2 ≈ 0.293 for rule 18, and 2/3 for rule
  182, against the exact 0.5, 0.25 and 0.75. In general it lands within 10-20%. The error
  is itself evidence that the evolution builds correlations.[^6] In Wolfram's summary, the
  Markov approximation fails because of "feedback".[^7]
- **Two-point correlations.** Additive rules build none from random starts. Rule 18 builds
  correlations that decay exponentially with a correlation length of about 2, the paper's
  "first indication of the generation of order".[^8]
- **Triangles.** The density T(n) of triangles with base n reaches equilibrium within a few
  steps and then follows T(n) ~ λ⁻ⁿ. Structure appears on all scales, but it is damped
  exponentially rather than self-similar.[^9]
- **Sequences.** The density Q(n) of runs of exactly n equal cells follows the same λ⁻ⁿ
  law. Compared with noise of the same density, the equilibrium has too many long runs of
  0s and too few short ones, whatever the starting density.[^10]

**Universality classes.** For large n, every non-additive complex rule (18, 22, 122,
126, 146, 182) gives the *same* triangle spectrum, with λ ≈ 4/3, whatever the initial
state. The additive rules 90 and 150 form a second class with λ ≈ 2. The spectrum is
"universal, independent both of the details of the initial state, and of the precise
cellular automaton rule used". The non-additive value of λ is fixed and does not depend on
each rule's final density. Wolfram notes it corresponds to an "effective density" of
about 0.25.[^11]

**A proposed explanation.** One rule can often simulate another under a short
encoding. Under rule 22, encoding each 0 as 00 and each 1 as 01 reproduces rule 146 at half
speed. A similar encoding reproduces rule 182. Wolfram suggests that the simplicity of
such "interpreters" is why these rules share statistics. Rule-to-rule simulation may
"form a basis for the universality found in the statistical properties of various cellular
automata."[^12] (Fig. 28 of the paper maps which complex rules simulate which under
length-two encodings. Not every pair is related.)

**Initial-state sensitivity of the class.** Random starts affect the pattern at every
scale and for all time. Correlated ("Brownian") starts give more long-range structure, with
T(n) falling more slowly. Homogeneous starts such as …1111… or …1010… produce no finite
structures.[^13]

**Noise.** Flipping each cell's new value with probability κ at every step (a finite
temperature, in Boltzmann terms) destroys the structure gradually. Densities and
correlations change continuously with κ, and there is nothing like a phase transition.[^14]
Global behaviour does change abruptly, though
([[irreversibility-and-entropy](pages/irreversibility-and-entropy.md)]).
Langton (1990) does find a phase transition, along a different axis: the rule itself, as
measured by his [[lambda-parameter](pages/lambda-parameter.md)] (a different λ from the triangle constant
above). See [[edge-of-chaos](pages/edge-of-chaos.md)].[^18]

**Why it can happen at all.** Self-organization depends on irreversibility. Trajectories
merge, probability concentrates on a shrinking set of configurations, and some
configurations become much more likely than others even at equilibrium. The global side
of this is on [[irreversibility-and-entropy](pages/irreversibility-and-entropy.md)].[^15]
Wolfram also notes that nontrivial behaviour in applications usually needs some form of
"growth inhibition".[^16]

**Beyond elementary rules.** With three or more states per cell, some rules form
protective "membranes". These shield regions from outside noise, so very regular patterns
can grow from rare seeds. Any long enough random configuration contains a seed, which then
dominates the long-time behaviour.[^17]

## Appearances in Sources

- [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] - a phase transition across rule space, measured by entropy and mutual information
- [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] — Sec. III (local statistics), the simulation-encoding conjecture (Sec. IV), membranes (Sec. V)

## Related Concepts

- [[edge-of-chaos](pages/edge-of-chaos.md)] - a phase transition in rule space rather than in noise
- [[irreversibility-and-entropy](pages/irreversibility-and-entropy.md)] — the ensemble-level mechanism
- [[fractal-dimension](pages/fractal-dimension.md)] — the seeded counterpart: self-similar rather than exponentially damped structure
- [[additive-cellular-automaton](pages/additive-cellular-automaton.md)] — the second universality class
- [[elementary-cellular-automaton](pages/elementary-cellular-automaton.md)] — the family studied
- [[maxwells-demon](pages/maxwells-demon.md)] — the entropy-information link von Neumann drew from thermodynamics
- [[probabilistic-logic](pages/probabilistic-logic.md)] — von Neumann's treatment of noisy components
- [[universal-turing-machine](pages/universal-turing-machine.md)] - universality in the computational sense
- [[classification-of-cellular-automata](pages/classification-of-cellular-automata.md)] - Wolfram's classes and their formal successors
- [[chaos-in-cellular-automata](pages/chaos-in-cellular-automata.md)] - sensitivity to initial conditions in the topological sense

[^1]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.601 [synthesis] — the second law for isolated reversible systems; dissipative or open systems may evolve from disordered to ordered states; snowflakes, turbulent flow, biological systems; cellular automata "sufficiently simple to allow detailed mathematical analysis, yet sufficiently complex to exhibit a wide variety of complicated phenomena"
[^2]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.608 [synthesis] — disordered configurations have statistically uncorrelated sites, "a discrete form of 'white noise'"; deviations of statistical measures indicate order and correlations; a disordered configuration is specified by a single parameter p
[^3]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.607 — "time evolution according to these rules destroys the independence of the initial sites, and generates correlations between values at separated sites. This phenomenon is the essence of self-organization in cellular automata."
[^4]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] pp.614-615 [synthesis] — ρ∞ = 1/4 for 18, 146, 122, 126 and 3/4 for 182, independent of ρ₀ (Grassberger 1982); rule 22 ρ∞ = 0.35 ± 0.02; "The existence of a universal ρ∞, independent of initial density ρ₀, is characteristic of complex cellular automaton rules."
[^5]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.615 [synthesis] — block density estimates Gaussian with standard deviation ≈ 1/√b maintained by complex rules; "law of large numbers"; for nonadditive rules block-over-time and many-blocks procedures give the same limits
[^6]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.615 [synthesis] — master equation (3.4); rule 90 p = ½; rule 18 p = 1 − 1/√2 ≈ 0.293; rule 182 p = 2/3 vs exact 0.75; "within 10-20% of the exact values"; discrepancies reflect "the presence of correlations induced by cellular automaton evolution"
[^7]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.641 [synthesis] — "Markovian master equation approximations to the density development were found inadequate because of the importance of 'feedback' in the cellular automaton evolution"
[^8]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.615 [synthesis] — additive rules keep C⁽²⁾(r) zero; rule 18 falls roughly exponentially "with a correlation length ~2"; "our first indication of the generation of order by cellular automaton evolution"
[^9]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] pp.616-617, 619 [synthesis] — triangles form when a long sequence of sites suddenly attains the same value and is reduced by "ambient noise"; T(n) ~ λ⁻ⁿ (Eq. 3.7); Fig. 16: T(n) falls off exponentially, "in contrast to the power law form found for the self-similar patterns"
[^10]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] pp.617-620 [synthesis] — sequence density Q₍ᵢ₎(n); sum rule Q(n) ≈ Σ 2T(i)/i links it to T(n); Fig. 17: equilibrium "containing an excess of long sequences of sites with value 0, and a deficit of short ones", independent of initial density
[^11]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] pp.617, 619-620 [synthesis] — "all nonadditive rules yield the same T(n), distinct from that for the additive rules"; λ ~ 4/3 nonadditive, λ ~ 2 additive; "the spectrum of triangles generated by complex cellular automaton evolution is universal, independent both of the details of the initial state, and of the precise cellular automaton rule used"; fixed λ irrespective of final densities; "effective density" ≈ 0.25
[^12]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] pp.629-630, 641 [synthesis] — rule 22 simulates 146 with 0 → 00, 1 → 01, after 2τ steps; rule 182 by a similar encoding; "The simplicity of the interpreter ... is presumably responsible for the similarities in their statistical behavior"; Fig. 28 network; "Not all complex cellular automaton rules are thus related by linear encodings of any length"; "This capability may well form a basis for the universality found in the statistical properties of various cellular automata."
[^13]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.617 [synthesis] — a disordered infinite initial state affects the pattern at all scales and times; Brownian initial states yield T(n) decreasing less rapidly; homogeneous initial states (...11111... or ...10101...) preserve homogeneity with no finite structures
[^14]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.620 [synthesis] — value reversed with probability κ, which "gives the Boltzmann factor corresponding to a finite temperature heat bath"; "the transition to disorder is a continuous one, and no phenomenon analogous to a 'phase transition' is found" (Fig. 18)
[^15]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.623 [synthesis] — trajectories become concentrated in limited regions; "This behavior makes self-organization possible, by allowing some configurations to occur with larger probabilities than others even in the large-time equilibrium limit."
[^16]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.641 — "Their nontrivial features are typically evident only when some form of growth inhibition is present."
[^17]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.631 [synthesis] — membranes that "protect" sites from external noise; regular patterns grow from seeds; "any sufficiently long disordered configuration will contain at least one, and the large time behavior of the cellular automaton will be radically affected by its presence"
[^18]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] pp.24, 27-28 [synthesis] - sweeping λ over K = 4, N = 5 1D rules gives "a phase transition between periodic and chaotic dynamics"; in 2D K = 8, N = 5 rules the average cell entropy jumps at a critical λ, "a classic signature of a first-order phase transition"
