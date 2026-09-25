---
title: Edge of Chaos
category: Concepts
summary: Langton's phase transition between ordered and chaotic cellular-automaton dynamics, found by sweeping the λ parameter - critical slowing down, size-sensitive transients, glider-like particles, and peak mutual information cluster there; Wolfram's class IV sits on it, and Langton conjectures it is where computation (and perhaps life) emerges
tags: [concept, langton, edge-of-chaos, phase-transition, criticality, entropy, mutual-information, emergent-computation, wolfram-classes]
sources: [computation-at-the-edge-of-chaos]
created: 2026-09-24
updated: 2026-09-24
---

# Edge of Chaos

## Description

**The claim.** If rule space is ordered by the [[lambda-parameter](pages/lambda-parameter.md)],
there is a phase transition between highly ordered and highly disordered dynamics, which
Langton likens to the change between solid and fluid. The most complex behaviour is found
near it, and so is the greatest capacity to store, transmit, and modify information.
Langton's hypothesis is that computation can emerge spontaneously in physical systems
near such a transition, especially a second-order ("critical") one.[^1]

**Why computation needs it.** Every known proof of universal computation in a
[[cellular-automaton](pages/cellular-automaton.md)] embeds a computer in the rule. Each
relies on three features of the dynamics: storing information for arbitrarily long times,
sending it over arbitrarily long distances, and letting stored and sent information
interact. Together they need correlation lengths that can grow without bound. Langton
quotes Codd: propagation must be "unbounded in principle but boundable in practice".[^2]

**The 1D picture** (K = 4, N = 5, 128-cell rings):[^3]

| λ | behaviour |
|---|---|
| ≤ 0.15 | dies to the uniform quiescent state within a few steps |
| 0.20-0.35 | periodic structures appear, fixed points with scattered stuck cells, longer transients |
| 0.40 | transients of about 60 steps, a structure with a period of about 40 |
| 0.45 | transients of almost 1000 steps, moving structures, one with a true period of 14,848 |
| 0.50 | activity balanced between collapse and expansion, transients of about 12,000 steps |
| 0.55-0.60 | effectively chaotic, transients now shrinking as λ rises |
| 0.65-0.75 | chaos within about 10 steps, then 2, then 1; activity spreads at up to the maximum rate |

Langton reads four things from this.[^4]

- **Critical slowing down.** Transient length peaks at the transition.
- **Size sensitivity.** Array size affects transients only near the transition. At
  λ = 0.50 transients grow exponentially with array size. Far from it on either side they
  do not depend on size at all.
- **Randomness grows toward λ = 0.75**, the point of maximum disorder.
- **Particles.** The transition supports both static and moving structures. The moving
  ones are solitary waves, like gliders in the [[game-of-life](pages/game-of-life.md)].
  They collide with each other and with static periodic structures, and could serve as
  signals and storage.

The transition is not always this clean. Different walks through λ cross it at different
values, and often the dynamics jumps from fairly ordered to fairly disordered, which looks
like a first-order transition. Langton concludes that first- and second-order transitions
both occur.[^5]

**The 2D measurements** (K = 8, N = 5, 64 × 64 arrays):

- **Entropy.** About 10,000 random tables give a bimodal spread of average cell entropy,
  with a sparse gap below H ≈ 0.84. The ceiling of the gap is the entropy of a common
  chaotic rule that uses only two states and draws the Sierpiński gasket in 1D. Along one
  table walk-through the entropy stays near zero until a critical λ, then jumps, which is
  "a classic signature of a first-order phase transition".[^6] Lining walks up by distance
  from the jump, Δλ, instead of by λ shows the structure more clearly.[^7]
- **Mutual information.** I(A;B) = H(A) + H(B) - H(A,B) between a cell and itself one step
  later is near zero in the ordered phase, jumps at the transition, and decays slowly as λ
  rises. At high λ the cells act independently, like "a hot gas of randomly flipping
  cells". Correlations decay slowest in space and time in the middle region.[^8]
- **Mutual information against entropy.** Plotting one against the other removes λ. The
  maximum is sharp, at a normalized entropy of about 0.32, which suggests an "optimal
  working entropy". Langton's explanation is that storing information lowers entropy and
  sending it raises entropy, so a computing system must balance the two. Crutchfield and
  Young report the same shape for the logistic map (cited via Langton, not read).[^9]

Cells that compute together need "some - but not too much" correlation. Too much and one
simply copies the other. Too little and neither can read the other's signals, since
correlation is what gives them a common code.[^10] Complexity therefore rises with
randomness only up to the transition and falls after it, unlike Chaitin-Kolmogorov
complexity, which rises steadily with randomness.[^11]

**Wolfram's classes on the λ axis.** Wolfram's four classes (Wolfram 1984, cited via
Langton, not yet read) are: I, evolves to a homogeneous state; II, to simple separated
periodic structures; III, to chaotic aperiodic patterns; IV, to complex localized
structures, with very long transients.[^12] Langton puts I and II in the ordered phase,
III in the disordered phase, and IV at the transition. Packard and Wolfram had suggested
class IV is a set of measure 0. Langton agrees: in the limit of large rule spaces, the
transition lies on a (K - 2)-dimensional hyperplane. Class IV rules are still easy to find
when you know where that hyperplane is. If Wolfram is right that class IV supports
universal computation, universal computation also sits at the transition.[^13]

**Computation analogies.**

- **Complexity classes.** Far from the transition, transients do not depend on array
  size. Near it, the dependence becomes exponential or worse, from either side. Langton
  reads this as a complexity-class hierarchy for computations that do not halt.[^14]
- **The freezing problem.** Below the transition, rules quickly freeze into short-period
  behaviour. Above it, they quickly become chaotic. Near it, both outcomes occur and
  transients are so long that the outcome is effectively undecidable. Langton calls this
  the *freezing problem* and pairs it with Turing's halting problem
  ([[universal-turing-machine](pages/universal-turing-machine.md)]). He calls it "quite
  likely" undecidable.[^15]

**The conjecture.** Langton labels this part a conjecture. Solid and fluid are not only
states of matter but the two universality classes of dynamical behaviour. Systems in the
transition region can avoid both outcomes by staying on long transients, and computations
are special cases of what physical systems do near a solid-liquid or liquid-vapour
transition. The halting problem would then be one instance of the freezing problem.[^16]
His open questions include:[^17]

- whether "fluid" dynamics divides further into gases and liquids;
- whether statistical mechanics can supply analogues of temperature, pressure, volume and
  energy;
- whether simulated annealing works because the annealed system computes its own solution
  near the freezing point;
- how the transition relates to Bak's self-organized criticality. Bak had suggested that
  Life is self-organized critical.

The furthest speculation is about life. Life may have begun on extended transients near a
phase transition, and evolution may be how living systems learned to hold themselves
there, steering "between too much order and too much chaos, the Scylla and Charybdis of
dynamical systems".[^18]

**Complexity bounds.** Langton ends on von Neumann's
[[complexity-threshold](pages/complexity-threshold.md)], using a slightly different sense
of complexity. Below the threshold, synthesis is degenerative. Langton adds that it is
degenerative above an upper level as well. The two limits are close together, near the
phase transition, and computation sits there, "at the 'edge of chaos'".[^19]

**Related work** (all cited via Langton, not read). Kauffman found a similar
order-disorder transition in random Boolean networks. Vichniac, Tamayo and Hartman
recovered Wolfram's classes by mixing two rules in an inhomogeneous CA, and linked critical
slowing down to the halting problem. Li and Packard mapped the elementary rule space with a
similar parameter. Packard found that rules selected for a task drift toward the
transition. Wootters and Langton used mean field theory to reproduce much of the entropy
data.[^20]

## Appearances in Sources

- [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] - the primary source: the λ surveys, the measures, and the interpretation

## Related Concepts

- [[lambda-parameter](pages/lambda-parameter.md)] - the axis along which the transition appears
- [[complexity-threshold](pages/complexity-threshold.md)] - von Neumann's lower bound, to which Langton adds an upper one
- [[universal-turing-machine](pages/universal-turing-machine.md)] - the halting problem, analogue of the freezing problem
- [[game-of-life](pages/game-of-life.md)] - a transition-region rule whose gliders and blinkers make a computer
- [[self-organization](pages/self-organization.md)] - Wolfram's noise experiments found no phase transition, on a different axis
- [[irreversibility-and-entropy](pages/irreversibility-and-entropy.md)] - Wolfram's entropy view of CA evolution
- [[chris-langton](pages/chris-langton.md)] - proposed it

[^1]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] p.13 [synthesis] - Sec. 1.2: "a phase transition between highly ordered and highly disordered dynamics, analogous to the phase transition between the solid and fluid states of matter"; most complex behaviour and greatest potential for information storage, transmission and modification in the transition region; hypothesis that computation "may emerge spontaneously" near the transition, "especially in the vicinity of a second-order or 'critical' transition"
[^2]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] p.16 [synthesis] - Sec. 2.5: universality proofs embed a computer in the CA; three fundamental features; "arbitrarily large correlation lengths in space and time"; Codd: "unbounded in principle but boundable in practice"
[^3]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] pp.17-24 [synthesis] - Sec. 3 itemized tour from λ = 0.00 to 0.75 with Figs. 1-2; transients about 60 (0.40), almost 1000 (0.45), about 12 000 (0.50); true period 14 848 at 0.45; chaos in about 10 steps (0.65), 2 steps (0.70), 1 step (0.75)
[^4]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] pp.25-26 [synthesis] - Sec. 4: critical slowing down (Fig. 3); array size effect only at intermediate λ, exponential at λ = 0.50 (Fig. 4); more random as λ → 0.75; static and propagating structures, solitary waves like Life's gliders; propagating and static structures "can form the basis for signals and storage"
[^5]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] p.26 [synthesis] - Sec. 4.1: transitions at different λ on different traversals; "the dynamics jumps directly from fairly ordered to fairly disordered behavior, suggesting that both first- and second-order transitions are possible"
[^6]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] pp.27-28 [synthesis] - Fig. 6, about 10 000 runs, bimodal, gap between 0.0 < H ≤ 0.84; ceiling H = 0.84 from a common chaotic rule collapsed onto s_q and one other state, the Sierpiński gasket in 1D; Fig. 7: entropy stays near zero until a critical λ, "Such a discontinuity is a classic signature of a first-order phase transition"
[^7]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] p.28 [synthesis] - Figs. 8-10: 50 superimposed runs; plots lined up by the transition event, abscissa Δλ the distance from the event
[^8]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] p.29 [synthesis] - Eq. 3; Fig. 11 mutual information between a cell and itself at the next step; Fig. 12 "essentially zero below the transition point, it jumps to a moderate value at the transition, and then decays slowly"; "a hot gas of randomly flipping cells"; Fig. 13: decay in time and space "slowest in the middle region"
[^9]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] p.31 [synthesis] - Fig. 14; envelope lines intersect at H_c ≈ 0.32 normalized; "an optimal working entropy"; "information storage involves lowering entropy while information transmission involves raising entropy"; Crutchfield's similar relation for the logistic map (Fig. 15)
[^10]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] pp.29, 31 [synthesis] - cells "must exhibit some - but not too much - correlation"; too strong and one mimics the other; too small and each is unpredictable to the other; "Correlations in behavior imply a kind of common code, or protocol"
[^11]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] pp.31-32 [synthesis] - "rather than increasing monotonically with randomness - as is the case for the usual measures of complexity, such as that of Chaitin and Kolmogorov - complexity increases with randomness only up to a point"; "total disorder is just as 'simple', in a sense, as total order"
[^12]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] p.16 [synthesis] - Sec. 2.6 lists Wolfram's four classes and their dynamical-systems analogues (limit points, limit cycles, strange attractors, "very long transients"); Wolfram suggests class IV can support universal computation
[^13]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] pp.17, 32-33 [synthesis] - Packard and Wolfram hypothesized class IV is a set of measure 0; Sec. 7.1: classes I and II ordered, III disordered, IV at the transition (Fig. 16); a (K - 2)-dimensional hyperplane in the thermodynamic limit; "when we locate class IV CAs at a phase transition, we are also locating universal computation at a phase transition"
[^14]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] p.33 [synthesis] - Sec. 7.2: far from the transition, transients independent of array size; near a critical transition "this size dependence appears to be exponential or worse", from either side; "a similar complexity-class hierarchy for non-halting computations"
[^15]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] p.33 [synthesis] - Sec. 7.3: three outcomes for computations and for CAs; below the transition CAs "freeze up", above they settle to chaos; near it "effectively" undecidable; "the Freezing problem"; "It is quite likely that the freezing problem is undecidable"
[^16]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] pp.33-34 [synthesis] - Sec. 8: "only a conjecture at this point"; solid and fluid "constitute two fundamental universality classes of dynamical behavior"; a third possibility of "indefinitely extended transients"; "the halting problem can be seen as a specific instance of the more general freezing problem"
[^17]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] p.35 [synthesis] - Sec. 8.3: gases and liquids; analogues for temperature, pressure, volume and energy; simulated annealing and "an emergent computation"; Bak's self-organized criticality, "Bak has suggested that Conway's game of Life is a self-organized critical system"
[^18]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] p.35 [synthesis] - "life had its origin in just these kinds of extended transient dynamics"; precursors of life "had to gain control over their own dynamical state"; "to steer a delicate course between too much order and too much chaos, the Scylla and Charybdis of dynamical systems"
[^19]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] pp.35-36 [synthesis] - Sec. 9 quotes von Neumann's critical-size passage; "a slightly different sense of 'complexity'"; "above a certain level of 'complexity', the process of synthesis is also degenerative"; upper and lower bounds "fairly close together and are located in the vicinity of a phase transition"; "at a phase transition here at the 'edge of chaos'"
[^20]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] pp.34-35 [synthesis] - Sec. 8.2: Kauffman's Boolean nets; Vichniac, Tamayo and Hartman's inhomogeneous CA and critical slowing down vs the halting problem; Packard and Li's elementary rule space; Packard's rules drifting toward the transition; Wootters' mean-field reproduction of Fig. 6
