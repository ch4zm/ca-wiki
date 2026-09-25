---
title: Reversible Turing Machine
category: Concepts
summary: A deterministic Turing machine in which no two transitions lead into the same state with different written symbols or head moves, so every configuration has at most one predecessor; introduced by Lecerf, shown universal by Bennett, and buildable from rotary elements alone
tags: [concept, reversible-computing, turing-machines, bennett, lecerf, morita]
sources: [aucm-ch6-reversible-turing-machines-by-rlem, theory-of-cellular-automata-a-survey]
created: 2026-09-24
updated: 2026-09-24
---

# Reversible Turing Machine

## Description

**Definition (quintuple form).** A Turing machine T = (Q, S, q₀, F, s₀, δ) has
transitions [p, s, s′, d, q]: in state p reading s, write s′, move d ∈ {L, N, R}, and go to
q. T is *deterministic* if two distinct transitions from the same state read different
symbols. It is *reversible* if two distinct transitions into the same state write
different symbols and make the same move. An RTM is a machine that is both.[^1] (Own
reasoning: the current state fixes which way the head just moved, and the symbol written
in the cell it left then picks out a unique transition, so the previous configuration can
be recovered.)

**History.** Lecerf introduced RTMs (1963) and showed their halting problem unsolvable.
Bennett studied them for the thermodynamics of computing and showed that they are
universal. Bennett used the quadruple form, from which an inverse machine is easy to read
off. Morita uses quintuples because they make the circuit simpler.[^2]

**In cellular automata.** Because RTMs can be universal, Morita and Harao (1989) obtained
universal 1D [[reversible-cellular-automaton](pages/reversible-cellular-automaton.md)]s by
simulating them (reported by Kari).[^3]

**From a single logic element.** Any RTM can be built as an infinite circuit of rotary
elements ([[reversible-logic-element-with-memory](pages/reversible-logic-element-with-memory.md)]).
The tape is an infinite chain of identical memory-cell circuits, and the finite control is
another RE circuit at the left end. To stay reversible, every write also reports the
symbol it overwrote, so a read is done as "write 0" followed by a rewrite. Built in the
[[billiard-ball-model](pages/billiard-ball-model.md)], the whole machine becomes a system
of elastic balls and reflectors
([[aucm-ch6-reversible-turing-machines-by-rlem](pages/aucm-ch6-reversible-turing-machines-by-rlem.md)]).[^4]

**Example.** T_parity has states q₀, q₁, q₂, q_acc, q_rej and transitions [q₀, 0, 1, R, q₁],
[q₁, 0, 1, L, q_acc], [q₁, 1, 0, R, q₂], [q₂, 0, 1, L, q_rej], [q₂, 1, 0, R, q₁]. It decides
whether a unary input is even, complementing every symbol it reads.[^5]

## Appearances in Sources

- [[aucm-ch6-reversible-turing-machines-by-rlem](pages/aucm-ch6-reversible-turing-machines-by-rlem.md)] - definition, history, construction from rotary elements
- [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] - Bennett's universality; Morita and Harao's simulation in 1D reversible CA

## Related Concepts

- [[universal-turing-machine](pages/universal-turing-machine.md)] - RTMs can be universal
- [[reversible-cellular-automaton](pages/reversible-cellular-automaton.md)] - RTM simulation gives universal 1D reversible CA
- [[reversible-logic-element-with-memory](pages/reversible-logic-element-with-memory.md)] - the rotary element, from which any RTM can be built
- [[billiard-ball-model](pages/billiard-ball-model.md)] - a physical setting for the RE circuits
- [[irreversibility-and-entropy](pages/irreversibility-and-entropy.md)] - the thermodynamic motivation for reversibility

[^1]: [[aucm-ch6-reversible-turing-machines-by-rlem](pages/aucm-ch6-reversible-turing-machines-by-rlem.md)] p.132 (Definition 3) [synthesis] — T = (Q, S, q0, F, s0, δ), δ ⊆ Q × S × S × {L, N, R} × Q, quintuples [p, s, s′, d, q]; deterministic: if p1 = p2 then s1 ≠ s2; reversible: if q1 = q2 then s1′ ≠ s2′ ∧ d1 = d2; "by RTM we mean a deterministic and reversible TM"
[^2]: [[aucm-ch6-reversible-turing-machines-by-rlem](pages/aucm-ch6-reversible-turing-machines-by-rlem.md)] p.132 — "An RTM was first investigated by Lecerf [7] who showed unsolvability of their halting problem. Bennett [2,3] then studied them from the standpoint of thermodynamics of computing, and showed its universality. In [2] RTMs were defined in the quadruple form, since an "inverse" RTM is easily obtained from a given RTM if it is given in the quadruple form. But, here we use an RTM in the quintuple form, since this form is convenient to make a circuit that simulates the RTM simpler."
[^3]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.18 [synthesis] - Morita and Harao [54]; "reversible Turing machines can be computationally universal [4]"; Theorem 8
[^4]: [[aucm-ch6-reversible-turing-machines-by-rlem](pages/aucm-ch6-reversible-turing-machines-by-rlem.md)] pp.133-137 [synthesis] — memory cells chained rightward form the tape unit; the finite-state control is an RSM built from REs; W0/W1 return R0/R1 so that reversibility holds; "if we further implement each RE by a mechanism in the billiard ball model (BBM) as in Figure 6.4, then the whole system of the RTM can be realized in the space of BBM"
[^5]: [[aucm-ch6-reversible-turing-machines-by-rlem](pages/aucm-ch6-reversible-turing-machines-by-rlem.md)] p.132 (Example 1) — "δ = {[ q0 , 0, 1, R, q1 ], [ q1 , 0, 1, L, qacc ], [ q1 , 1, 0, R, q2 ], [ q2 , 0, 1, L, qrej ], [ q2 , 1, 0, R, q1 ]}. Tparity checks if a given unary number n is even or odd. ... All the symbols read by Tparity are complemented"
