---
title: Rule 110
category: Rules
summary: Elementary cellular automaton 110 (01101110) - Wolfram class 4, full of colliding localized signals, and proved computationally universal by Cook and Wolfram; whether it is intrinsically universal is open, as is the universality of its class-4 cousin rule 54
tags: [rule, rule-110, elementary-ca, class-4, universality, cook, wolfram]
sources: [theory-of-cellular-automata-a-survey, statistical-mechanics-of-cellular-automata, aucm-ch5-small-universal-turing-machines]
created: 2026-09-24
updated: 2026-09-24
---

# Rule 110

> The universality proof is cited via
> [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)]
> (as Wolfram's *A New Kind of Science*, 2002) and
> [[aucm-ch5-small-universal-turing-machines](pages/aucm-ch5-small-universal-turing-machines.md)]
> (as Cook, "Universality in elementary cellular automata", *Complex Systems* 15(1), 2004).
> Neither has been read.

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
same way as glider collisions in the [[game-of-life](pages/game-of-life.md)]. One
dimension makes this harder than two, because signals cannot easily cross.[^3] Kari leaves
the exact form of universality undefined.[^4] The proof simulates Turing machines, which is
the weaker of the two kinds of universality
([[intrinsic-universality](pages/intrinsic-universality.md)]).[^5] Neary and Woods cite Cook
(2004) for the result and list rule 110 with small universal Turing machines and tag
systems ([[tag-system](pages/tag-system.md)]) as standard stepping stones: simulating one
of them is now the usual way to prove another model universal.[^6]

**Open questions.** Is rule 110 *intrinsically* universal? And is rule 54, another
elementary class-4 rule, computationally universal?[^7]

**Against the 1983 view.** Wolfram (1983) wrote that the elementary rules he studied were
too simple for universal computation.[^8] Those were the 32 legal rules, which exclude
110, so the two claims are consistent. Still, the universality of a two-state
nearest-neighbour rule reverses the 1983 expectation for the family as a whole (own
reasoning).

## Appearances in Sources

- [[aucm-ch5-small-universal-turing-machines](pages/aucm-ch5-small-universal-turing-machines.md)] - Cook (2004) as the universality proof; rule 110 as a standard route to universality proofs
- [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] - §2.5 (rule table, Fig. 3), §2.6 (Theorem 2, Open problem 1), §6 (Open problem 5)
- [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] - the numbering; the judgement that the legal elementary rules are not universal

## Related Concepts

- [[elementary-cellular-automaton](pages/elementary-cellular-automaton.md)] - the family
- [[game-of-life](pages/game-of-life.md)] - universality from colliding moving structures in 2D
- [[intrinsic-universality](pages/intrinsic-universality.md)] - the stronger notion, open for rule 110
- [[universal-turing-machine](pages/universal-turing-machine.md)] - what the proof simulates
- [[classification-of-cellular-automata](pages/classification-of-cellular-automata.md)] - class 4 and Wolfram's universality conjecture
- [[rule-90](pages/rule-90.md)] - the canonical additive elementary rule, for contrast
- [[tag-system](pages/tag-system.md)] - a fellow stepping stone for universality proofs

[^1]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.8 [synthesis] - "the famous rule 110 is the elementary CA where f(111) = 0, f(110) = 1, f(101) = 1, f(100) = 0, f(011) = 1, f(010) = 1, f(001) = 1, f(000) = 0, obtained from the binary expansion 110 = (01101110)b"
[^2]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.8 - "At the fine-grained plot one can clearly observe signals and collisions of signals creating new signals."
[^3]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.11 [synthesis] - "Rule 110 is in Wolfram class 4, and Wolfram conjectured in the 1980s that it is computationally universal [74]. Recently this result was established by him and Cook [76]"; signals encode information and collisions perform logic "in the same spirit" as GOL gliders; "in two dimensions it is much easier to make signals cross each other"; Theorem 2
[^4]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.12 - "We leave the exact form of universality of rule 110 undefined here."
[^5]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.23 - "The universality of GOL and rule 110 is based on performing Turing machine simulations in the CA."
[^6]: [[aucm-ch5-small-universal-turing-machines](pages/aucm-ch5-small-universal-turing-machines.md)] pp.117-118 — "Simulation of small universal Turing machines and other simple universal models such as Post's tag systems [36] and the cellular automaton rule 110 [4] is by now a standard way to prove that a large number of other models of computation, including a variety of physically-inspired systems, are computationally universal."; [4] = Cook, M.: Universality in elementary cellular automata. Complex Systems 15(1), 1–40 (2004)
[^7]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.12, 23 [synthesis] - Open problem 1: "Is the elementary CA rule 54 computationally universal?", described as "another elementary CA that is in Wolfram class 4"; Open problem 5: "Is rule 110 intrinsically universal?"
[^8]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.630 - "the elementary cellular automata considered here and in Secs. II and III are not of sufficient complexity to be capable of universal computation."
