---
title: Irreversibility and Entropy (cellular automata)
category: Concepts
summary: The global, ensemble view of cellular automaton evolution - trajectories merge but never split, entropy of an equiprobable ensemble decreases, most configurations become unreachable, finite systems fall into short cycles, and reversible second-order rules restore Liouville's theorem
tags: [concept, irreversibility, entropy, ensemble, cycles, reversible-ca, wolfram]
sources: [statistical-mechanics-of-cellular-automata, theory-of-cellular-automata-a-survey]
created: 2026-09-24
updated: 2026-09-24
---

# Irreversibility and Entropy (cellular automata)

## Description

**The ensemble view.** Instead of the statistics of cells within one configuration, look
at a probability distribution over *all* configurations. This is the analogue of phase-space
(Γ-space) statistical mechanics, and it connects cellular automata to dynamical systems
and the theory of computation. It treats a cellular automaton as a kind of "symbolic
dynamics" in which the variables really are discrete.[^1] A ring of N cells has 2ᴺ
configurations, and each rule is a map of that set to itself.[^2]

**Local irreversibility.** A rule can send several configurations to the same one. Each
configuration has exactly one successor but may have several predecessors, or none, so
trajectories "may coalesce, but may never split". In a reversible system trajectories never
meet and the number of possible configurations stays constant (Liouville's theorem). In an
irreversible system that number can shrink. Trajectories bunch together in limited regions
of the configuration space and do not fill it.[^3] This bunching is what makes
[[self-organization](pages/self-organization.md)] possible.[^3] Among the elementary rules,
only the identity (rule 204) is invertible.[^4]

**Unreachable configurations.** Some configurations can only be initial states. These are
the [[garden-of-eden](pages/garden-of-eden.md)] configurations:[^5]

- Rule 0 reaches only all-0. Rule 4 reaches a fraction of configurations that goes to 0 as
  N grows. (Own reasoning: rule 4 keeps only isolated 1s, so what it reaches is the
  configurations with no two adjacent 1s.) Rule 204 reaches everything.
- The additive [[rule-90](pages/rule-90.md)] reaches half the configurations (N odd) or a
  quarter (N even), a fixed fraction.
- Rule 126 reaches only configurations whose 1s come in pairs. The unreachable fraction
  tends to 1 and behaves as 1 − λᴺ with λ ≈ 0.88, a root of a cubic (Martin et al. 1983,
  cited via this paper and not read). Other non-additive rules behave similarly.

Wolfram points to Moore (1962, [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)]) and Aggarwal
(1973, cited via this paper and not read) for criteria for Garden-of-Eden configurations to
exist, which he describes as "equivalent to irreversibility".[^5]

**Entropy.** The entropy S is the base-2 logarithm of the average number of possible
states, computed from the probabilities pᵢ of the states. It measures how many bits it
takes on average to specify one state. It is additive over independent subsystems and is
maximal, one bit per cell, for the equiprobable ensemble.[^6] Reversible evolution almost
always increases entropy. Cellular automaton evolution can *decrease* it. Starting from an
equiprobable ensemble with N = 10 under rule 126, S falls and levels off at an equilibrium
value, "a direct signal of irreversibility".[^7] For infinite lattices the *block entropy*
S_b, taken over blocks of b cells, converges quickly to the entropy per cell as b grows,
because correlations decay exponentially.[^8] (Wolfram's comparison is printed English:
from single letters, pairs and triples he gets S₁ ≈ 4.70, S₂ ≈ 4.15, S₃ ≈ 3.57 bits, with
S∞ ~ 2.3.)[^8]

**Organized probabilities.** After a few steps from an equiprobable start, the ensemble
reaches an equilibrium in which configurations have unequal probabilities, and many have
probability zero. For N = 10 under rule 126 the all-0 configuration is the most likely, at
about 0.13. If configurations are read as binary fractions in [0, 1], the equilibrium
ensemble is a Cantor set whose dimension is set by the entropy. For rule 126 it is 0.5
(Farmer 1982, cited via this paper and not read).[^9]

**Sensitive dependence.** For non-additive complex rules, two configurations that differ in
one cell separate linearly in Hamming distance, so a bundle of nearby trajectories spreads
into an exponentially growing volume. After a few steps the map from initial to final
configurations looks roughly random.[^10]

**Cycles in finite systems.** A ring of N cells must become periodic within 2ᴺ steps (the
Poincaré recurrence time).[^11]

- Simple rules reach cycles whose length does not grow with N. Rules 0 and 72 go to all-0.
  Rules 36, 76 and 104 reach fixed configurations. Rules 94 and 108 split into small
  independent regions with short cycles.
- Complex rules can have cycles that grow without bound as N grows, but they visit only a
  tiny part of the space. Under rule 126 with N = 8, no start visits more than 8 of the 256
  configurations. The maximum is 38 for N = 10 and at least 1547 for N = 32.[^11][^12]

Configurations therefore fall into three classes: those that can only be initial states,
transients that lead into cycles, and cycle states, which act as attractors.[^13]

**Compared with a random mapping.** A random map on K elements leaves a fraction 1/e ≈ 0.37
of the elements with no preimage. Its average cycle length is about √(πK/8). Take K = 256
(N = 8) as an example. A random map gives an average cycle length of about 10, about 94
unreachable configurations and about 7 cycles. Rule 126 gives 3.2, 190 and 7. Complex
cellular automata are "more irreversible" than random mappings, and any agreement is
"largely fortuitous".[^14]

**Noise changes the global picture.** Locally, noise erodes structure continuously. Globally
the change is abrupt. With no noise, a ring of N = 7 under rule 126 enters a cycle after 6
configurations. With any noise rate κ > 0 it eventually visits all 128.[^15]

**Reversible rules.** The irreversibility comes from each configuration depending only on
the one before it, S_n = F[S_{n−1}], like a PDE (partial differential equation) that is
first order in time, such as the diffusion equation. Second-order rules,
S_n = F[S_{n−1}] ⊕ S_{n−2}, are like the wave equation. Because XOR can be undone, S_{n−2}
can be recovered from S_{n−1} and S_n, so every pair of successive configurations has a
unique past and future. This construction is due to Fredkin and Margolus (1982), cited via
this paper and not read.[^16] Infinite reversible rules almost always increase entropy.
Finite ones become effectively irreversible only when the boundary injects random values.
From simple seeds they grow self-similar patterns that are symmetric in time, not the
one-directional triangles of irreversible rules.[^17]

**The physical and topological sides (Kari 2005).** Kari gives the physical case for
reversible rules directly. Microscopic physics is reversible, and a computer that makes
optimal use of physics must be reversible too, because irreversibility always dissipates
energy as heat ([[reversible-cellular-automaton](pages/reversible-cellular-automaton.md)]).[^18]
The shrinking set of reachable configurations described above has an exact topological
counterpart on the infinite lattice. The sets Gⁿ(C) form a decreasing chain whose
intersection is the [[limit-set](pages/limit-set.md)]: compact, non-empty, and a single
configuration exactly when the rule is nilpotent.[^19] Conservation laws other than
information, such as particle number, are handled as additive invariants
([[conserved-quantity](pages/conserved-quantity.md)]).[^20]

## Appearances in Sources

- [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] - the physical argument for reversibility; limit sets as the topological version of shrinking reachable sets
- [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] — Sec. IV: configuration-space mappings, irreversibility, unreachable configurations, entropy, cycles, random mappings, noise, reversible rules

## Related Concepts

- [[garden-of-eden](pages/garden-of-eden.md)] — the unreachable configurations
- [[self-organization](pages/self-organization.md)] — what irreversibility makes possible
- [[additive-cellular-automaton](pages/additive-cellular-automaton.md)] — exact cycle and reachability results
- [[rule-90](pages/rule-90.md)] — reaches a fixed fraction of configurations
- [[maxwells-demon](pages/maxwells-demon.md)] — the entropy-information link behind von Neumann's thermodynamic view of automata
- [[elementary-cellular-automaton](pages/elementary-cellular-automaton.md)] — the family analysed
- [[automorphism-group-of-the-shift](pages/automorphism-group-of-the-shift.md)] - the invertible 1D rules
- [[erasable-configuration](pages/erasable-configuration.md)] - local information loss
- [[probabilistic-logic](pages/probabilistic-logic.md)] - von Neumann's treatment of noisy components, cf. noisy rule 126
- [[reversible-cellular-automaton](pages/reversible-cellular-automaton.md)] - the rules with no information loss
- [[limit-set](pages/limit-set.md)] - the configurations left after infinitely many steps
- [[conserved-quantity](pages/conserved-quantity.md)] - other conservation laws
- [[margolus-neighbourhood](pages/margolus-neighbourhood.md)] - a different way to build reversible rules, by block permutations

[^1]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.621 [synthesis] — the ensemble of all configurations "in analogy with the Γ-space approach to classical statistical mechanics"; connections with dynamical systems theory and the formal theory of computation; "symbolic dynamics" with genuinely discrete degrees of freedom
[^2]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.621 [synthesis] — finite N, 2ᴺ configurations, each a length-N binary integer; rules define a mapping of the set of binary numbers of length N onto itself (Fig. 19)
[^3]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] pp.622-623 [synthesis] — "local irreversibility": unique descendants but not unique ancestors, trajectories "may coalesce, but may never split"; in a reversible system the number of configurations stays constant (Liouville's theorem); trajectories "become concentrated in limited regions"; "This behavior makes self-organization possible"
[^4]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.625 — "Except in the trivial case of the identity transformation (rule 204), F is not invertible."
[^5]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.623 and n.10 [synthesis] — rule 0 reaches only the null state; rule 4 generates only configurations "in which no two adjacent sites have the same value", a fraction tending to zero as N → ∞; rule 204 reaches all; rule 90 half (N odd) or ¼ (N even); rule 126 only paired nonzero sites, unreachable fraction → 1 as 1 − λᴺ, λ ≈ 0.88 (Martin et al. 1983); n.10: Moore (1962) and Aggarwal (1973) give criteria "(equivalent to irreversibility)"
[^6]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] pp.623-625 [synthesis] — entropy as the base-2 logarithm of the average number of possible states, Eq. 4.1 in terms of pᵢ; "the average number of binary bits necessary to specify one state"; additive over independent subsystems; maximal value of one bit per site for an equiprobable ensemble
[^7]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.625 [synthesis] — "For reversible systems, time evolution almost always leads to an increase in entropy. However, for irreversible systems, such as cellular automata, the entropy may decrease with time"; Fig. 24, N = 10, rule 126; "The decrease is a direct signal of irreversibility."
[^8]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.625 [synthesis] — block (Rényi) entropy S_b = (1/b) Σ pᵢ⁽ᵇ⁾ log pᵢ⁽ᵇ⁾; S_{b→∞} gives the entropy per site, approached rapidly because of exponentially decreasing correlations; printed English S₁ ≈ 4.70, S₂ ≈ 4.15, S₃ ≈ 3.57, S∞ ~ 2.3
[^9]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] pp.622-623 [synthesis] — equilibrium ensemble with different probabilities and gaps (Figs. 21-22); null configuration most probable ≈ 0.13 (Fig. 21); configurations as real numbers form a Cantor set (Farmer 1982a, b) whose dimension is given by the entropy; for rule 126 it is 0.5
[^10]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] pp.621-622, 641 [synthesis] — a single-site change under rule 126 gives linearly increasing Hamming distance; "A bundle of initial trajectories therefore diverges with time into an exponentially increasing volume"; the mapping from initial to final configurations "becomes apparently random"
[^11]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.626 [synthesis] — periodic after at most 2ᴺ steps (the "Poincaré recurrence time"); rules 0, 72 to the null configuration; 36, 76, 104 to stationary configurations; 94, 108 to small independent regions with short cycles; simple rules' cycle lengths constant in N, complex rules' may increase without bound; for N = 8 a maximum of eight distinct configurations from any initial state
[^12]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.627 [synthesis] — "For N = 10, the maximum is 38 states, while for N = 32, it is at least 1547"
[^13]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.628 [synthesis] — three classes: configurations only as initial states; configurations with "parents" but no "grandparents" (transients); configurations on cycles, which "may be considered as attractors"
[^14]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] pp.628-629 [synthesis] — random mappings (cf. Kauffman 1969): fraction 1/e ≈ 0.37 unreached; average cycle length ≈ √(πK/8); K = 256: cycle ≈ 10, transient ≈ 10, ≈ 94 unreachable, ≈ 7 cycles; rule 126: 3.2, 2.5, 190, 7; "more irreversible"; "Any agreement with results for random mappings appears to be largely fortuitous"
[^15]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.629 [synthesis] — "Global properties may, however, change discontinuously when a nonzero κ is introduced"; Fig. 27, N = 7, rule 126: six configurations at κ = 0; with κ > 0 every configuration is eventually visited
[^16]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] pp.625-626 [synthesis] — irreversibility from S_n = F[S_{n−1}]; analogy with first-order PDEs such as diffusion; reversible cellular automata (Fredkin 1982; Margolus 1982) S_n = F[S_{n−1}] ⊕ S_{n−2}, analogous to the wave equation; invertibility of modulo-two addition gives unique descendants and ancestors
[^17]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.626 [synthesis] — infinite reversible cellular automata: entropy almost always increases; finite ones globally irreversible with dissipative (random) boundaries; self-similar patterns from simple seeds, "symmetrical in time, rather than the asymmetrical triangle structures found with irreversible rules"
[^18]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.17 - "a massively parallel computer that optimally uses physics to compute must itself be reversible. Non-reversibility always implies energy dissipation, in practice in the form of heat."
[^19]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.23-24 [synthesis] - Λ⁽ⁿ⁾ = Gⁿ(C) decreasing chain, Λ = ⋂ Λ⁽ⁿ⁾; Theorem 14: compact, non-empty, finite iff nilpotent
[^20]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.21 [synthesis] - "Reversible CA preserve information. There are also other conservation laws in physics that CA may obey"; additive conserved quantities; number conservation
