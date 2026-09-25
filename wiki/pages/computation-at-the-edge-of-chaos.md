---
title: Computation at the Edge of Chaos (Langton, 1990)
category: Sources
summary: Langton's survey of cellular-automaton rule space ordered by the λ parameter - a phase transition between ordered and chaotic dynamics, with long transients, glider-like particles, peak mutual information, and Wolfram's class IV at the transition; computation analogies (complexity classes, the "freezing problem") lead to the conjecture that computation lives at the "edge of chaos"
tags: [langton, lambda-parameter, edge-of-chaos, phase-transition, rule-space, entropy, mutual-information, emergent-computation, wolfram-classes]
sources: [computation-at-the-edge-of-chaos]
created: 2026-09-24
updated: 2026-09-25
---

# Computation at the Edge of Chaos (Langton, 1990)

**Source:** raw/langton-1990-computation-at-the-edge-of-chaos.pdf (Langton, C. G., "Computation at the edge of chaos: Phase transitions and emergent computation", *Physica D* 42, 12-37, 1990; https://doi.org/10.1016/0167-2789(90)90064-V)
**Date ingested:** 2026-09-24
**Type:** paper

> Locators are the journal's printed page numbers (PDF page n = printed page 11 + n).
> Wolfram (1984), Packard and Wolfram (1985), Gutowitz, Kauffman, Packard, Crutchfield and
> Young, Bak, Li and Packard, McIntosh, Wootters, and Langton's own thesis (1990) are cited
> via this paper and have not been read. Wolfram's four classes come from Wolfram (1984),
> which is on the reading list.

## Summary

Langton asks when a physical system can support computation at all. His answer is that it
must be able to store, transmit, and modify information. He studies the question in
[[cellular-automaton](pages/cellular-automaton.md)] rule space.[^1] A rule space with K
states and N neighbours is huge and has no built-in order. Langton orders it with one
number, the [[lambda-parameter](pages/lambda-parameter.md)]: the fraction of rule-table
entries that do not lead to a chosen quiescent state.[^2] He sweeps λ, builds random rule
tables at each value, and measures what the rules do.[^3]

The result is a phase transition ([[edge-of-chaos](pages/edge-of-chaos.md)]). In 1D rules
with K = 4 and N = 5, low λ gives fixed points, then periodic structures. Transients grow
until, around λ ≈ 0.45-0.5, they last thousands of steps, grow exponentially with the
array size, and carry particle-like moving structures. Past that point the dynamics are
effectively chaotic, and the time to reach typical chaos shrinks as λ rises.[^4] In about 10,000 runs of 2D rules with K = 8 and N = 5, the average
cell entropy jumps at a transition value of λ that differs from table to table. Mutual
information between cells peaks near the transition. Plotted against entropy, it has a
sharp maximum at a normalized entropy of about 0.32.[^5]

The rest of the paper interprets this. Wolfram's classes I and II are the ordered phase,
class III is the chaotic phase, and class IV sits at the transition. That explains why
class IV is rare in the limit of large rule spaces and still easy to find when you know
where to look.[^6] Langton pairs critical slowing down with computational complexity
classes, and the "freezing problem" with Turing's halting problem.[^7] He ends with a
conjecture that he labels as such. Solid and fluid are the two universality classes of all
dynamics. Computation happens on the extended transients between them, and life may have
begun there.[^8]

## Key Takeaways

- **λ orders rule space.** λ = (K^N - n)/K^N, where n is the number of transitions to the
  quiescent state. λ = 0 is the most ordered table and λ = 1 - 1/K the most mixed. It
  works well for large K and N and poorly for 2-state, 3-neighbour rules.[^2][^9]
- **Three things computation needs.** Storage, which means keeping local state for
  arbitrarily long times. Transmission, which means signals over arbitrarily long
  distances. Interaction between the two. Together they need correlation lengths that can
  be arbitrarily long.[^10]
- **Critical slowing down.** Transients are short and independent of array size at both
  ends of the λ range, and longest at the transition. At λ = 0.50 in the 1D survey they
  grow exponentially with array size. One λ = 0.45 structure has a true period of 14,848
  steps.[^4][^11]
- **Particles and storage at the transition.** The λ = 0.45 rule supports several kinds
  of moving particles that collide with each other and with static periodic structures,
  like [[glider](pages/glider.md)]s and [[blinker](pages/blinker.md)]s in the [[game-of-life](pages/game-of-life.md)]. Life's own λ
  is 0.273, inside the transition region for 2-state, 9-neighbour rules.[^12]
- **Entropy gap and percolation.** In the 2D survey the entropy data are bimodal, with a
  sparse gap below H ≈ 0.84. The low-entropy cutoff at λ ≈ 0.6 matches the site-percolation
  threshold 0.59 for the five-cell neighbourhood, and the nine-cell neighbourhood cuts off
  near 0.4, against a threshold of 0.402.[^13]
- **Complexity peaks in the middle.** Mutual information is near zero in the ordered
  phase, jumps at the transition, then decays toward the "hot gas" of high λ. Information
  storage lowers entropy and transmission raises it, so computation needs a compromise.
  Crutchfield and Young found a similar complexity-vs-entropy curve for the logistic
  map.[^5][^14]
- **Upper and lower bounds on complexity.** Langton extends von Neumann's
  [[complexity-threshold](pages/complexity-threshold.md)]. There is a lower limit, and also
  an upper one, above which synthesis is again degenerative. The two sit close together,
  near the phase transition.[^15]

## Structure of the paper

- **Sec. 1** (pp.12-14) - the question, results, and a formal definition of CAs. With K
  states and a neighbourhood of N cells there are K^N neighbourhood states and K^(K^N)
  rules, about 10^30,000 for K = 8, N = 5.[^16]
- **Sec. 2** (pp.14-17) - the λ parameter and two ways to sample with it (random-table and
  table-walk-through). Rules must obey strong quiescence and isotropy. The two views of
  computation in CAs, the three computational primitives, and Wolfram's four classes.[^17]
- **Sec. 3** (pp.17-24) - qualitative tour of 1D K = 4, N = 5 rules from λ = 0.00 to 0.75,
  on 128-cell rings, from full-random and patch-random starts.[^18]
- **Sec. 4** (pp.24-26) - critical slowing down, array-size effects, particles, and two
  complications. The transition happens at different λ on different walks, and it is
  sometimes an abrupt jump (first-order) rather than a smooth second-order transition.[^19]
- **Sec. 5-6** (pp.26-32) - quantitative survey of 2D K = 8, N = 5 rules on 64 × 64
  arrays: Shannon entropy, mutual information, and the two plotted against each other.[^20]
- **Sec. 7** (pp.32-33) - Wolfram's classes on the λ axis, complexity classes, and the
  freezing problem.[^6][^7]
- **Sec. 8-9** (pp.33-36) - solids and fluids as universality classes, related work,
  open questions, and the conclusion.[^8][^15]

## Entities & Concepts

- [[lambda-parameter](pages/lambda-parameter.md)] - the one-number ordering of rule space
- [[edge-of-chaos](pages/edge-of-chaos.md)] - the phase transition, its measures, and the computation analogies
- [[chris-langton](pages/chris-langton.md)] - the author
- [[cellular-automaton](pages/cellular-automaton.md)] - Langton's formal definition and rule counts
- [[game-of-life](pages/game-of-life.md)] - λ = 0.273, in the transition region
- [[glider](pages/glider.md)], [[blinker](pages/blinker.md)] - signal and storage in the Life universality proof
- [[complexity-threshold](pages/complexity-threshold.md)] - von Neumann's lower bound, plus Langton's upper one
- [[universal-turing-machine](pages/universal-turing-machine.md)] - the halting problem and its "freezing" analogue
- [[self-organization](pages/self-organization.md)] - Wolfram found no phase transition in noise, while Langton finds one in rule space
- [[elementary-cellular-automaton](pages/elementary-cellular-automaton.md)] - where λ discriminates poorly
- [[von-neumann-29-state-ca](pages/von-neumann-29-state-ca.md)] - the first CA shown to support universal computation

## Relation to Other Wiki Pages

Langton's opening question is von Neumann's, turned around. Von Neumann designed one rule,
[[von-neumann-29-state-ca](pages/von-neumann-29-state-ca.md)], in which a computer could be
built. Langton asks which rules in a whole space can support one.[^21] His method follows
[[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)]:
survey many rules and measure them statistically. His answer is a phase transition. Wolfram
(1983) varied a different quantity, site noise κ, and found the change to disorder
continuous, with nothing like a phase transition
([[self-organization](pages/self-organization.md)]). Both results can hold, because κ and λ
are different axes (own reasoning).

The closing section returns to von Neumann's
[[complexity-threshold](pages/complexity-threshold.md)] and adds an upper bound to it. The
freezing-problem analogy connects the phase transition to the halting problem on
[[universal-turing-machine](pages/universal-turing-machine.md)]. The glider-and-blinker
reading of computation matches the universality construction summarized on
[[game-of-life](pages/game-of-life.md)].

[^1]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] pp.12-13 [synthesis] - abstract and Sec. 1: the substrate must support "the transmission, storage, and modification of information"; the question is reformulated for cellular automata
[^2]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] p.14 [synthesis] - "there is no intrinsic order within" the rule space; Sec. 2.1: pick a quiescent state s_q, n transitions to it, the rest filled uniformly from the other K - 1 states, λ = (K^N - n)/K^N (Eq. 1); λ = 0.0 when all transitions go to s_q; λ = 1.0 - 1/K when all states are represented equally; "the most homogeneous and the most heterogeneous rule tables"
[^3]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] pp.14-15 [synthesis] - Sec. 2.2: step through 0.0 < λ < 1.0 - 1/K, construct random Δ functions at each λ, run them, and examine measures of dynamical behaviour as a function of λ
[^4]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] pp.17-25 [synthesis] - Sec. 3 λ tour: homogeneous fixed point for λ ≤ 0.15, periodic structures from 0.20, transients of about 60 steps at 0.40 and almost 1000 at 0.45, about 12 000 at 0.50 where activity is "at a balance point between collapse and expansion"; effectively chaotic from 0.55 with transients shrinking; fully random after one step at 0.75; Sec. 4: transient length depends exponentially on array size at λ = 0.50
[^5]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] pp.27-31 [synthesis] - Fig. 6 entropy for approximately 10 000 runs; Figs. 7-10 table-walk transitions at different λ; Fig. 12 mutual information "essentially zero below the transition point, it jumps to a moderate value at the transition, and then decays slowly"; Fig. 14 envelope lines intersect at H_c ≈ 0.32 normalized; "a clear, sharply defined maximum value of mutual information at a specific value of the entropy"
[^6]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] p.32 [synthesis] - Sec. 7.1: "classes I and II constitute the ordered phase, while class III constitutes the disordered phase"; "the only logical choice for the location of class IV CAs is at the transition"; in the thermodynamic limit the transition lies on a (K - 2)-dimensional hyperplane, a set of measure 0, but "if we know where to look for a set of measure 0, we can find many instances"
[^7]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] p.33 [synthesis] - Sec. 7.2: divergence of transient times as the analogue of complexity classes, suggesting a hierarchy "for non-halting computations"; Sec. 7.3: the "Freezing problem", "It is quite likely that the freezing problem is undecidable"
[^8]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] pp.33-35 [synthesis] - Sec. 8: "this interpretation, although strongly supported by evidence, is only a conjecture at this point"; solid and fluid phases "constitute two fundamental universality classes of dynamical behavior"; systems can avoid both "by maintaining themselves on indefinitely extended transients"; Sec. 8.3: "life had its origin in just these kinds of extended transient dynamics"
[^9]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] p.15 [synthesis] - Sec. 2.4: "λ discriminates well between dynamical regimes for 'large' values of K and N, whereas λ discriminates poorly for small values of K and N"; for K = 2, N = 3 "λ is only roughly correlated with dynamical behavior"; the survey uses K ≥ 4 and N ≥ 5
[^10]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] p.16 [synthesis] - Sec. 2.5: storage "must preserve local state information for arbitrarily long times", transmission "over arbitrarily long distances", stored and transmitted information must interact; "any dynamical system supporting computation must exhibit arbitrarily large correlation lengths in space and time"
[^11]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] pp.18-19, 25 [synthesis] - λ = 0.45: quasi-period of 116 steps shifting 3 sites, must orbit the 128-cell array 3 times, "the true period of this structure is 14 848 time steps"; Sec. 4: "a phenomenon known in the study of phase transitions as critical slowing down"; array size has an effect "only for intermediate values of λ"
[^12]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] pp.25-26 [synthesis] - particle-like solitary waves "like the 'gliders' in Conway's Game of Life"; "λ_Life = 0.273 lies within the transition region for K = 2, N = 9 2D CAs"; Fig. 5 (512 cells, λ = 0.45) shows several kinds of particles; a particle hitting a static periodic structure produces a particle travelling the opposite way; the Life universality proof uses gliders as signals and blinkers as storage
[^13]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] p.27 [synthesis] - sparsely populated gap between 0.0 < H ≤ 0.84, "bimodal"; cutoff of low H at λ = 0.6 "corresponds to the site-percolation threshold p_c ≈ 0.59"; 9-neighbour template cutoff at λ = 0.4 vs p_c = 0.402; the H = 0.84 ceiling is the entropy of a common two-state chaotic rule that makes the Sierpiński gasket in 1D
[^14]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] pp.29-32 [synthesis] - high λ is "a hot gas of randomly flipping cells"; "information storage involves lowering entropy while information transmission involves raising entropy"; Crutchfield's machine complexity vs normalized entropy for the logistic map (Fig. 15); complexity "increases with randomness only up to a point"
[^15]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] pp.35-36 [synthesis] - quotes von Neumann's 1949 critical-size passage; "above a certain level of 'complexity', the process of synthesis is also degenerative"; "there exist an upper limit as well as a lower limit"; the bounds "seem to be fairly close together and are located in the vicinity of a phase transition"
[^16]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] pp.13-14 [synthesis] - Sec. 1.4: D-dimensional lattice, neighbourhood template, K^N neighbourhood states, K^(K^N) transition functions; Sec. 1.5: K = 8, N = 5 gives 32 768 neighbourhood states and about 10^30 000 rules
[^17]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] pp.14-17 [synthesis] - Secs. 2.1-2.6: λ; random-table and table-walk-through methods; strong quiescence and isotropy conditions; CAs as computers vs as universes with embedded computers; three primitives; Wolfram's four classes
[^18]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] p.17 [synthesis] - K = 4, N = 5 (two cells either side), 128 sites in a circle, table-walk-through; Fig. 1 from fully random starts, Fig. 2 from a random patch of 20 sites in a field of 0s
[^19]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] pp.25-26 [synthesis] - Sec. 4 observations; Sec. 4.1: different traversals make the transition at different λ with "a well defined distribution around a mean value"; "Often, the dynamics jumps directly from fairly ordered to fairly disordered behavior, suggesting that both first- and second-order transitions are possible"
[^20]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] pp.26-31 [synthesis] - Sec. 5: 2D, K = 8, N = 5, arrays typically 64 × 64 with periodic boundaries; Shannon entropy H (Eq. 2), mutual information I(A;B) = H(A) + H(B) - H(A,B) (Eq. 3); Sec. 6 plots them against each other
[^21]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] p.16 [synthesis] - von Neumann's proof of machine self-reproduction shows a universal computer/constructor in a 29-state CA; Codd, Smith, Conway and co-workers, Fredkin and Toffoli found simpler universal rules; "when is it possible - even necessary - to adopt the second point of view"
