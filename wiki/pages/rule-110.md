---
title: Rule 110
category: Rules
summary: Elementary cellular automaton 110 (01101110) - Wolfram class 4, full of colliding localized signals, and proved computationally universal by Cook and Wolfram; whether it is intrinsically universal is open, as is the universality of its class-4 cousin rule 54
tags: [rule, rule-110, elementary-ca, class-4, universality, cook, wolfram]
sources: [theory-of-cellular-automata-a-survey, statistical-mechanics-of-cellular-automata, aucm-ch12-linear-cellular-automata-and-decidability, lifewiki-brians-brain, lifewiki-seeds, lifewiki-star-wars]
created: 2026-09-24
updated: 2026-09-26
---

# Rule 110

> The universality proof is cited via
> [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)]
> (as Wolfram's *A New Kind of Science*, 2002) and has not been read.

## Description

**The rule.** Rule 110 is the
[[elementary-cellular-automaton](pages/elementary-cellular-automaton.md)] whose rule table
is the binary expansion 110 = 01101110:[^1]

| 111 | 110 | 101 | 100 | 011 | 010 | 001 | 000 |
|---|---|---|---|---|---|---|---|
| 0 | 1 | 1 | 0 | 1 | 1 | 1 | 0 |

(Own reasoning: 100 → 0 but 001 → 1, so the rule is not mirror-symmetric and is not one of
Wolfram's 32 "legal" rules. It is still quiescent, since 000 → 0.)

**Behaviour.** Space-time diagrams show *signals*, localized structures that travel and
collide, and whose collisions make new signals.[^2] Rule 110 is in Wolfram class 4
([[classification-of-cellular-automata](pages/classification-of-cellular-automata.md)]),
and Wolfram conjectured in the 1980s that it is computationally universal.[^3]

**Universality.** Cook and Wolfram established it: **rule 110 is computationally
universal**. Information is coded in signals, and their collisions perform logic, in the
same way as [[glider](pages/glider.md)] collisions in the [[game-of-life](pages/game-of-life.md)]. One
dimension makes this harder than two, because signals cannot easily cross.[^3] Kari leaves
the exact form of universality undefined.[^4] The proof simulates Turing machines, which is
the weaker of the two kinds of universality
([[intrinsic-universality](pages/intrinsic-universality.md)]).[^5]

**What the proof needs.** Cook's construction runs on ultimately periodic configurations
with two different periodic blocks. The block extending left times the computation, and
the block extending right encodes the cyclic [[tag-system](pages/tag-system.md)] that
carries universality. On configurations of finite support, by contrast, reachability for
rule 110 is trivially decidable. Neary and Woods later removed the exponential slowdown in
the original construction. As a result, predicting the state of one cell at time t from a
finite configuration is P-complete
([[reachability-in-cellular-automata](pages/reachability-in-cellular-automata.md)]).[^6]

**A yardstick for 2D rules.** Because Rule 110 is universal, building it inside another
rule proves that rule universal too. A row or tiling of *unit cells* ([[lifewiki-unit-cell](pages/lifewiki-unit-cell.md)]), each emulating one
Rule 110 cell, is the standard route.
- [[seeds-rule](pages/seeds-rule.md)] (B2/S): a Rule 110 "unit stripe" on a periodically
  tiled grid (Peter Naszvadi, 2020).[^7]
- [[brians-brain](pages/brians-brain.md)] (B2/S/C3): a Rule 110 unit cell built from
  AND-NOT gates and toggle flip-flops (Yoel Matveyev, 2020).[^8]
- [[star-wars-rule](pages/star-wars-rule.md)] (B2/S345/C4): a Rule 110 emulator made of
  photon circuitry (FWKnightship, 2020).[^9]

These are rules where live cells barely last, or never survive at all; one dimension of
universal computation is enough to lift them into Turing-completeness (own reasoning).

**Open questions.** Is rule 110 *intrinsically* universal? And is rule 54, another
elementary class-4 rule, computationally universal?[^10]

**Against the 1983 view.** Wolfram (1983) wrote that the elementary rules he studied were
too simple for universal computation.[^11] Those were the 32 legal rules, which exclude
110, so the two claims are consistent. Still, the universality of a two-state
nearest-neighbour rule reverses the 1983 expectation for the family as a whole (own
reasoning).

## Appearances in Sources

- [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] - the periodic backgrounds in Cook's proof; P-completeness; decidable reachability on finite support
- [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] - §2.5 (rule table, Fig. 3), §2.6 (Theorem 2, Open problem 1), §6 (Open problem 5)
- [[lifewiki-seeds](pages/lifewiki-seeds.md)], [[lifewiki-brians-brain](pages/lifewiki-brians-brain.md)], [[lifewiki-star-wars](pages/lifewiki-star-wars.md)] - Rule 110 emulated in 2D rules
- [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] - the numbering; the judgement that the legal elementary rules are not universal

## Related Concepts

- [[elementary-cellular-automaton](pages/elementary-cellular-automaton.md)] - the family
- [[game-of-life](pages/game-of-life.md)] - universality from colliding moving structures in 2D
- [[intrinsic-universality](pages/intrinsic-universality.md)] - the stronger notion, open for rule 110
- [[universal-turing-machine](pages/universal-turing-machine.md)] - what the proof simulates
- [[classification-of-cellular-automata](pages/classification-of-cellular-automata.md)] - class 4 and Wolfram's universality conjecture
- [[rule-90](pages/rule-90.md)] - the canonical additive elementary rule, for contrast
- [[tag-system](pages/tag-system.md)] - the cyclic tag system Cook's construction encodes
- [[reachability-in-cellular-automata](pages/reachability-in-cellular-automata.md)] - decidable on finite support, universal on periodic backgrounds
- [[seeds-rule](pages/seeds-rule.md)], [[brians-brain](pages/brians-brain.md)], [[star-wars-rule](pages/star-wars-rule.md)] - 2D rules proved universal by emulating Rule 110

[^1]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.8 [synthesis] - "the famous rule 110 is the elementary CA where f(111) = 0, f(110) = 1, f(101) = 1, f(100) = 0, f(011) = 1, f(010) = 1, f(001) = 1, f(000) = 0, obtained from the binary expansion 110 = (01101110)b"
[^2]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.8 - "At the fine-grained plot one can clearly observe signals and collisions of signals creating new signals."
[^3]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.11 [synthesis] - "Rule 110 is in Wolfram class 4, and Wolfram conjectured in the 1980s that it is computationally universal [74]. Recently this result was established by him and Cook [76]"; signals encode information and collisions perform logic "in the same spirit" as GOL gliders; "in two dimensions it is much easier to make signals cross each other"; Theorem 2
[^4]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.12 - "We leave the exact form of universality of rule 110 undefined here."
[^5]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.23 - "The universality of GOL and rule 110 is based on performing Turing machine simulations in the CA."
[^6]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] p.270 [synthesis] — "Cook's proof of computational universality uses ultimately periodic configurations ... the left block serves to time the computation whereas the right block encodes the cyclic tag-system that is essential for universality. By contrast, Reachability for rule 110 is trivially decidable for configurations of finite support"; Neary and Woods: "it is P-complete to determine the state of a particular cell at time t of the evolution of a finite configuration under rule 110"
[^7]: [[lifewiki-seeds](pages/lifewiki-seeds.md)] L21 - "On October 30, 2020, Peter Naszvadi proved that Seeds is Turing-complete on an infinite, periodically-tiled grid by constructing a Rule 110 \"unit stripe\"."
[^8]: [[lifewiki-brians-brain](pages/lifewiki-brians-brain.md)] L18 - "On November 12, 2020, Yoel Matveyev published a Rule 110 unit cell for Brian's Brain, proving the rule Turing-complete. ... does not contain XOR gates. Instead, it uses AND-NOT gates and toggle flip-flops."
[^9]: [[lifewiki-star-wars](pages/lifewiki-star-wars.md)] L60,L67 [synthesis] - "Further constructions are possible, for instance an adder and a Rule 110 emulator"; reference 4, FWKnightship (November 18, 2020)
[^10]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.12, 23 [synthesis] - Open problem 1: "Is the elementary CA rule 54 computationally universal?", described as "another elementary CA that is in Wolfram class 4"; Open problem 5: "Is rule 110 intrinsically universal?"
[^11]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.630 - "the elementary cellular automata considered here and in Secs. II and III are not of sufficient complexity to be capable of universal computation."
