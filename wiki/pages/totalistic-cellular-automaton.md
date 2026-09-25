---
title: Totalistic Cellular Automaton
category: Concepts
summary: A cellular automaton whose new cell value depends only on the sum of the values in its neighbourhood; Wolfram's code numbers (C = Σ kⁿ f[n]) name them, and they behave like all rules with the same number of values k and range r, which made them his main sample for the four classes
tags: [concept, totalistic, rule-numbering, wolfram, one-dimensional]
sources: [universality-and-complexity-in-cellular-automata, statistical-mechanics-of-cellular-automata]
created: 2026-09-24
updated: 2026-09-24
---

# Totalistic Cellular Automaton

## Description

A **totalistic** cellular automaton is one in which a cell's new value depends only on
the *sum* of the values in its neighbourhood at the previous step, not on which cells
hold which values.[^1] In one dimension, with k values per cell and range r (the
neighbourhood is the cell and r cells on each side, 2r + 1 in all), the rule is a
function f of a single integer, the neighbourhood total n, which runs from 0 to
(2r + 1)(k − 1).[^2]

**Code numbers.** Wolfram names a totalistic rule by its *code*,
C = Σ kⁿ f[n], summed over all possible totals n. Written in base k, the code lists
f[n] from the largest total down to f[0].[^3] A rule is *legal* if it leaves the all-0
state alone (f[0] = 0) and is mirror-symmetric. Totalistic rules are symmetric
automatically, and f[0] = 0 makes the code a multiple of k.[^4] For k = 2, r = 2 the total
runs from 0 to 5, so there are 2⁵ = 32 legal codes, the even numbers 0 to 62.[^5] Examples
(own reasoning, from the definition):

- **Code 20** = 010100 in binary. A cell becomes 1 exactly when its five-cell
  neighbourhood holds two or four 1s. This is Wolfram's main class 4 example
  ([[wolfram-classes](pages/wolfram-classes.md)]).
- **Code 42** = 101010. A cell becomes 1 when the total is odd, so it is the XOR of all
  five cells. This matches Wolfram's listing of code 42 as an
  [[additive-cellular-automaton](pages/additive-cellular-automaton.md)].[^6]

Wolfram numbers general rules differently, by a *rule number* built from the full rule
table. For k = 2, r = 1 that is the familiar
[[elementary-cellular-automaton](pages/elementary-cellular-automaton.md)] numbering.[^7] A
code number and a rule number for the same k and r are therefore not interchangeable.

**Why they are used.** Totalistic rules give equal weight to every cell in the
neighbourhood. Wolfram reports that they show "no special simplifications" and behave like
all rules with the same k and r, which made them his main sample.[^8] The four
behaviour classes were first shown for the 32 legal k = 2, r = 2 codes, then for k = 2,
r = 3, k = 3, r = 1 and k = 5, r = 1 codes, with the class fractions in his Table I.[^9]

**Growth inhibition.** For totalistic rules, Wolfram gives simple conditions on f alone.
If f is zero for all small totals, a block of nonzero cells surrounded by zeros can never
grow. If f rises with the total, there is no "growth inhibition". Either way the rule is
class 1 or 2.[^10]

**Two dimensions.** The [[game-of-life](pages/game-of-life.md)] is the standard 2D example.
Wolfram (1983) calls it totalistic, and Wolfram (1984) calls it "essentially totalistic",
since a cell with exactly two live neighbours keeps its own value.[^11]

## Appearances in Sources

- [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] - defines totalistic rules for general k and r, the code numbers, and uses them as the main sample for the four classes
- [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] - introduces totalistic rules, with Life as an example

## Related Concepts

- [[wolfram-classes](pages/wolfram-classes.md)] - the classification the totalistic sample supports
- [[cellular-automaton](pages/cellular-automaton.md)] - the general notion and neighbourhood types
- [[elementary-cellular-automaton](pages/elementary-cellular-automaton.md)] - the rule-number scheme for k = 2, r = 1
- [[additive-cellular-automaton](pages/additive-cellular-automaton.md)] - code 42 is additive
- [[game-of-life](pages/game-of-life.md)] - the best-known 2D totalistic rule

[^1]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.637 [synthesis] - "totalistic" cellular automata, in which the value of a site depends only on the sum of the values of its neighbours at the previous time step
[^2]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] pp.2-3 [synthesis] - site values 0 to k − 1, range r, neighbourhood of at most 2r + 1 sites; form (2.2) with f taking a single integer argument; totalistic rules take αⱼ = 1 (2.3), so a site depends "only on the total of all preceding neighbourhood site values"
[^3]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.3 [synthesis] - the function f "may similarly be specified by a numerical 'code'" C_f = Σ kⁿ f[n], n = 0 to (2r + 1)(k − 1) (2.7); Fig. 1 labels give each code with its base-k digits, e.g. code 20 (010100)
[^4]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] pp.2-3 [synthesis] - null configuration invariant, F[0, …, 0] = 0 and f[0] = 0 (2.4); symmetric rules (2.5); rules satisfying (2.4) and (2.5) "termed 'legal'"; "The condition (2.4) implies that both R_F and C_f are multiples of k"
[^5]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] pp.5-8 [synthesis] - Fig. 1 shows "all possible legal one-dimensional totalistic cellular automata with k = 2 and r = 2", 32 rules with codes 0 through 62
[^6]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.27 - "For additive cellular automata (such as code 42 in fig. 1 and table II)"
[^7]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.3 [synthesis] - the form of F "may be specified by a 'rule number' [1]" R_F (2.6), summing F over all neighbourhoods, alongside the separate code C_f for totalistic f
[^8]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] pp.3, 5 [synthesis] - totalistic rules "give equal weight to all sites in a neighbourhood"; "The results of section 3 suggest that totalistic rules exhibit behaviour characteristic of all cellular automata"; "totalistic rules appear to exhibit no special simplifications, and give rise to behaviour typical of all cellular automaton rules with given k and r"
[^9]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.5 [synthesis] - Fig. 1 (k = 2, r = 2), Figs. 4-6 (k = 3 r = 1, k = 2 r = 3, k = 5 r = 1) "lie in the same four classes"; Table I fractions of legal totalistic rules in each class
[^10]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.4 [synthesis] - for totalistic rules the growth condition becomes (2.9), f[n] ≠ 0 for some small n; totalistic rules satisfying (2.10) "exhibit no 'growth inhibition' and must therefore similarly be of class 1 or 2"
[^11]: [[universality-and-complexity-in-cellular-automata](pages/universality-and-complexity-in-cellular-automata.md)] p.30 and footnote [synthesis] - "the two-dimensional (essentially totalistic) cellular automaton known as the 'Game of Life'"; footnote rule: with 2 neighbouring sites nonzero "the site takes the same value as on the previous time steps"
