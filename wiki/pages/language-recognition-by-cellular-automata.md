---
title: Language Recognition by Cellular Automata
category: Concepts
summary: One-dimensional cellular automata as space-bounded language acceptors - CA recognize exactly the deterministic context-sensitive languages, one-way CA all context-free ones; real-time vs linear-time inclusions, closure properties, and Smith's 1972 open question whether real time equals linear time
tags: [concept, language-recognition, formal-languages, real-time, one-way-ca, smith, complexity]
sources: [theory-of-cellular-automata-a-survey]
created: 2026-09-24
updated: 2026-09-25
---

# Language Recognition by Cellular Automata

> The papers behind these results (Kasami and Fujii 1968, Smith 1972, Dyer 1980, Choffrut
> and Culik 1984, Ibarra and Jiang 1988, Terrier 1995) are cited via
> [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)]
> and have not been read.

## Description

Language recognition by space-bounded 1D CA is one of the classical topics of CA theory.
Some of its problems, posed in the early 1970s, are still unsolved.[^1]

**The model.** A 1D CA with the nearest-neighbour neighbourhood (−1, 0, 1) and a boundary
symbol # that is never created or destroyed, so the active region cannot grow past the
input. The input word w is written in cells 1 to |w|, with # everywhere else. Some states
are *accepting*. w is accepted at time t if cell 1 is in an accepting state at time t. A
CA is *one-way* (OCA) if it is equivalent to one using only the neighbourhood (0, 1), so
information flows in one direction only.[^2]

**Without a time bound.** L(CA) is exactly the deterministic context-sensitive languages.
L(OCA) contains every context-free language. Whether L(CA) = L(OCA) is unknown.[^3]

**Time bounds.** Acceptance at time T(|w|) with T(n) = cn is *linear time*. With T(n) =
n − 1 it is *real time*, the earliest moment cell 1 can have heard from every letter of w.
The families are L(LCA) and L(RCA) for CA, and L(LOCA) and L(ROCA) for one-way CA.[^4]

- Trivially L(ROCA) ⊆ L(RCA) ⊆ L(LCA).[^5]
- L(LCA) ⊆ L(OCA) (Ibarra and Jiang), and L(RCA) = L(LOCA) (Choffrut and Culik).[^5]
- {a^(2ⁿ) : n ≥ 2} is recognized in real time by a CA but not in real time by any one-way CA.[^5]
- Even L(ROCA) contains non-context-free languages such as {aⁿbⁿcⁿ : n ≥ 1} (Dyer), yet
  it misses some context-free languages (Terrier).[^6]

**Closure.** L(RCA) and L(ROCA) are closed under the Boolean operations (Smith). L(ROCA)
and L(LCA) are closed under reversal. L(ROCA) is not closed under concatenation.[^7]

**The open question.** Is L(RCA) closed under reversal? This holds iff L(RCA) = L(LCA),
that is, iff real time is as strong as linear time. Smith posed it in 1972. It is not even
known whether L(RCA) differs from L(CA).[^8]

## Appearances in Sources

- [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] - §10, Fig. 9, Open problem 9

## Related Concepts

- [[cellular-automaton](pages/cellular-automaton.md)] - the general model; one-way (radius-½) rules
- [[moore-neighbourhood](pages/moore-neighbourhood.md)] - neighbourhoods, including the one-way (0, 1)
- [[universal-turing-machine](pages/universal-turing-machine.md)] - the unbounded-space counterpart
- [[decidability-in-cellular-automata](pages/decidability-in-cellular-automata.md)] - the other open computational questions

[^1]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.29 - "Language recognition by space-bounded one-dimensional CA is among the classical research topics in CA theory. ... Some problems posed in the early 1970s remain unsolved even today."
[^2]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.29 [synthesis] - nearest-neighbour neighbourhood; one-way if equivalent to a CA with neighbourhood (0, 1); boundary symbol # with f(a, b, c) = # iff b = #, "This guarantees that the active part of the CA cannot grow"; initial configuration c_w; accepting states A; acceptance when cell 1 is in an accepting state
[^3]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.29 - "It is not known whether L(CA) and L(OCA) are the same language family. What is known is that L(CA) is exactly the family of deterministic context-sensitive languages and that L(OCA) contains all context-free languages [47]."
[^4]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.29-30 [synthesis] - T(n) = cn linear time; T(n) = n − 1 real time; "|w| − 1 is the earliest time when the leftmost cell may possibly have received information about all letters"; L(LCA), L(RCA), L(LOCA), L(ROCA)
[^5]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.30 [synthesis] - trivial inclusions L(ROCA) ⊆ L(RCA) ⊆ L(LCA); L(LCA) ⊆ L(OCA) and L(RCA) = L(LOCA) proved in [36,12]; {a^(2ⁿ) | n ≥ 2} recognized in real time by a CA but not by any OCA [12]; Fig. 9
[^6]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.30 - "even the most restricted family L(ROCA) contains non-context-free languages, e.g. language {aⁿbⁿcⁿ | n ⩾ 1} [25], while it does not contain all context-free languages [64]."
[^7]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.30 [synthesis] - L(RCA) and L(ROCA) closed under boolean operations [61]; L(ROCA) and L(LCA) closed under reversal [12,61]; L(ROCA) not closed under concatenation [64]
[^8]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.30 [synthesis] - closure of L(RCA) under reversal "is true if and only if L(RCA) = L(LCA). This is an intriguing open problem, already posed in 1972"; Open problem 9 (Smith [61]); "it is not even know whether L(RCA) and L(CA) are different"
