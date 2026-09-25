---
title: Elementary Cellular Automaton
category: Concepts
summary: Wolfram's name for the simplest nontrivial cellular automata - a line of two-state cells, each updated from itself and its two nearest neighbours; 256 rules named by their 8-bit rule tables, 32 of them "legal"
tags: [concept, elementary-ca, wolfram, rule-numbering, one-dimensional]
sources: [statistical-mechanics-of-cellular-automata, computation-at-the-edge-of-chaos]
created: 2026-09-24
updated: 2026-09-24
---

# Elementary Cellular Automaton

## Description

An **elementary cellular automaton** is a one-dimensional
[[cellular-automaton](pages/cellular-automaton.md)] with two possible values per cell,
0 and 1, where a cell's neighbourhood is the cell itself and the cells immediately to its
left and right. Wolfram introduced the name.[^1]

**Rule numbers.** A three-cell neighbourhood has 2³ = 8 possible states, listed in the
order 111, 110, 101, 100, 011, 010, 001, 000. A rule gives the new value of the centre
cell for each one, so a rule is an 8-digit binary number. Wolfram uses that number and its
decimal equivalent interchangeably. There are therefore 2⁸ = 256 rules.[^1] For example,
[[rule-90](pages/rule-90.md)] is 01011010: each cell becomes the sum modulo 2 of its two
neighbours.[^2]

**Legal rules.** Wolfram normally imposes two restrictions:[^1][^3]

- **Quiescence.** The all-0 configuration must stay all-0. Among other things, this rules
  out "instantaneous propagation" of 1s. The rule number must be even, because 000 must
  map to 0.
- **Reflection symmetry.** 100 and 001 must give the same value, and so must 110 and 011.
  This makes the rule isotropic (the same in both directions) as well as homogeneous.

32 legal rules remain. The rules that break these conditions add nothing qualitatively
new. Breaking quiescence makes the background flash between all-0 and all-1. Breaking
symmetry makes patterns shift or shear uniformly.[^4] (Own reasoning: rule 110 maps 100 to
0 and 001 to 1, so it is not symmetric and is not among the 32.)

**Boolean form.** Each rule can be written as a Boolean function of s₋, s, s₊ (the left
neighbour, the cell, the right neighbour). Rule 90 is s₋ ⊕ s₊ and rule 150 is
s₋ ⊕ s ⊕ s₊. This form makes simulation fast. Pack 32 cells into one machine word, make
copies shifted one bit left and one bit right, and apply the rule with bitwise
instructions.[^5]

**Special families.** Only rules 0, 90, 150 and 204 satisfy additive (XOR) superposition
([[additive-cellular-automaton](pages/additive-cellular-automaton.md)]). Rules 0, 4, 50 and
254 satisfy conjunctive superposition, and 0, 204, 250 and 254 disjunctive superposition.
No other legal rule has a superposition principle. *Peripheral* rules ignore the centre
cell: 0, 90, 160 and 250.[^6]

**Simple vs complex.** From a single 1, the legal rules fall into three behaviours:[^7]

- The 1 is erased at once, as in rules 0 and 160, or frozen forever, as in rules 4 and 36.
  These rules have 100→0 and 001→0, so the 1 cannot spread.
- The 1 grows into a uniform block that widens by one cell per side per step, as in rules
  50 and 122.
- The 1 grows into a nontrivial, self-similar pattern, as in rules 18, 22 and 90.

Wolfram calls the first two groups **simple** and the third **complex**. From random
starts, simple rules settle to fixed points or short cycles, like the limit points and
limit cycles of dynamical systems. Complex rules behave more like strange attractors.[^8]
The complex rules are 18, 22, 122, 126, 146 and 182, which are non-additive, and the
additive rules 90 and 150.[^9] Their statistics are covered on
[[self-organization](pages/self-organization.md)] and
[[irreversibility-and-entropy](pages/irreversibility-and-entropy.md)].

**Finite versions.** A finite line needs boundary conditions. The two used are
*periodic*, where the ends are joined into a circle, and *null*, where the cells beyond the
ends are held at 0. Neither changes the qualitative behaviour.[^10] A finite elementary
automaton of length N is close to a feedback shift register of length N with taps at
N-2, N-1 and N. Only the two end cells behave differently. Rules 90 and 150 correspond to
*linear* feedback shift registers.[^10]

**Generalizations.** With k values per cell and three neighbours there are k^(k³) rules.
The legality conditions leave k^((k³+k²)/2 - 1) of them: 32 for k = 2 and 3¹⁷ ≈ 1.3 × 10⁸
for k = 3.[^11] Wolfram judged the elementary rules too simple for universal
computation.[^12]

**Too small for λ.** Langton's [[lambda-parameter](pages/lambda-parameter.md)] orders larger rule spaces well,
but for 2-state, 3-neighbour rules it is "only roughly correlated" with behaviour.
Langton suggests this is why earlier classification work on the smallest rule spaces did
not see the order-chaos transition ([[edge-of-chaos](pages/edge-of-chaos.md)]).[^13]

## Appearances in Sources

- [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] - why λ works poorly for elementary rules
- [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] — defines the family, the numbering, the legal subset, and the simple/complex split

## Related Concepts

- [[lambda-parameter](pages/lambda-parameter.md)] - discriminates poorly in this small rule space
- [[cellular-automaton](pages/cellular-automaton.md)] — the general notion
- [[additive-cellular-automaton](pages/additive-cellular-automaton.md)] — the exactly solvable subfamily
- [[rule-90](pages/rule-90.md)] — the standard example
- [[fractal-dimension](pages/fractal-dimension.md)] — what complex rules grow from a seed
- [[self-organization](pages/self-organization.md)] — what complex rules do from random starts
- [[irreversibility-and-entropy](pages/irreversibility-and-entropy.md)] — the global, ensemble view of the family

[^1]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.603 [synthesis] — one-dimensional, base 2, neighbourhood of the site and its two neighbours, "We shall call such cellular automata elementary"; the eight-digit binary rule number used interchangeably with its decimal equivalent; 256 rules; quiescence forbids rules whose binary specification ends in 1; reflection symmetry requires 100 ≡ 001 and 110 ≡ 011; 32 legal rules
[^2]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] pp.603-604 [synthesis] — rule 90: s_{n+1}(m) = s_n(m-1) ⊕ s_n(m+1) (Eq. 2.1); Fig. 1 gives its rule table 01011010
[^3]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.603 n.2 — "The quiescence condition is required in many applications to forbid 'instantaneous propagation' of value-one sites. The reflection symmetry condition guarantees isotropy as well as homogeneity in cellular automaton evolution."
[^4]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] pp.606-608 [synthesis] — violating quiescence gives alternation of 0 and 1 at infinity; violating reflection symmetry gives uniform shifting (self-similar patterns sheared, as in rule 225); "consideration of illegal as well as 'legal' cellular automaton rules introduces no qualitatively new features"; Fig. 7 caption: rule 1 "flashes", rule 2 shifts
[^5]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] pp.603-604 n.3 [synthesis] — Boolean forms of rules 18, 22, 54, 90, 150; bit-parallel simulation using a word of 32 sites and copies shifted one bit left and right
[^6]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.604 [synthesis] — additive rules 0, 90, 150, 204; conjunctive superposition for 0, 4, 50, 254; disjunctive for 0, 204, 250, 254; "no other legal cellular automaton rules satisfy superposition principles with any combining function"; peripheral rules 0, 90, 160, 250
[^7]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.604 [synthesis] — Fig. 3 classes: 1 erased (0, 160) or maintained (4, 36) with local rules 100→0 and 001→0; uniform expanding structure (50, 122); "These two classes of rules will be termed 'simple'"; "complex" rules exemplified by 18, 22 and 90
[^8]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.607 — "simple rules exhibit simple limit points or limit cycles, while complex rules exhibit phenomena analogous to strange attractors."
[^9]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.619 Fig. 16 caption [synthesis] — the nonadditive complex rules 18, 22, 122, 126, 146 and 182; the additive rules 90 and 150
[^10]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.607 [synthesis] — periodic and null boundary conditions, "no important qualitative differences"; correspondence with feedback shift registers with taps at N-2, N-1, N; additive rules 90 and 150 correspond to linear feedback shift registers; end sites differ
[^11]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.630 [synthesis] — k^(k³) rule sets; legality imposes ½k²(k-1)+1 constraints; 2⁵ = 32 for k = 2; 3¹⁷ = 129140163 ≈ 1.3 × 10⁸ for k = 3
[^12]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.630 — "the elementary cellular automata considered here and in Secs. II and III are not of sufficient complexity to be capable of universal computation."
[^13]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] p.15 [synthesis] - Sec. 2.4: "for a 1D CA with K = 2, and N = 3, λ is only roughly correlated with dynamical behavior. This may explain why the relationships reported here were not observed in earlier work on classifying CA dynamics"
