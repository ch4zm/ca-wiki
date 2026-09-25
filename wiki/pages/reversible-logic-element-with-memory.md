---
title: Reversible Logic Element with Memory
category: Concepts
summary: A reversible sequential machine with as many output symbols as input symbols (RLEM); the rotary element is the standard 2-state 4-symbol example, and every non-degenerate 2-state element with three or more symbols is universal for reversible computing
tags: [concept, reversible-computing, rlem, rotary-element, universality, morita]
sources: [aucm-ch6-reversible-turing-machines-by-rlem]
created: 2026-09-24
updated: 2026-09-24
---

# Reversible Logic Element with Memory

## Description

**Definition.** A *sequential machine* (Mealy type) is M = (Q, Σ, Γ, δ), with state set
Q, input and output alphabets Σ and Γ, and move function δ: Q × Σ → Q × Γ. It is a
*reversible* sequential machine (RSM) when δ is injective, which forces |Σ| ≤ |Γ|. A
reversible logic element with memory (RLEM) is an RSM with |Σ| = |Γ|, called a |Q|-state
|Γ|-symbol RLEM.[^1] Reversible logic *gates*, by contrast, have no memory.[^2]

**The rotary element (RE).** The RE is a 2-state, 4-symbol RLEM with states H and V and
inputs n, e, s, w:[^3]

| State | n | e | s | w |
|---|---|---|---|---|
| H | V, w′ | H, w′ | V, e′ | H, e′ |
| V | V, s′ | H, n′ | V, n′ | H, s′ |

Pictured as a box with a rotatable bar, a particle arriving parallel to the bar goes
straight through, and one arriving across it turns right and rotates the bar 90°
counterclockwise.[^4] Any RSM can be built from REs alone, and so can any
[[reversible-turing-machine](pages/reversible-turing-machine.md)], as an infinite
circuit. In that sense the RE is universal.[^5]

**How many elements, and which are universal.** There are (2k)! two-state k-symbol RLEMs,
which gives 24, 720 and 40,320 for k = 2, 3, 4. Up to renaming of states and symbols, the
classes number 8, 24 and 82. A *degenerate* element is equivalent to a 1-state element (a
set of wires) or to a 2-state element with fewer symbols. Leaving those out gives 4, 14 and
55 non-degenerate classes.[^6]

| Symbols k | 2-state RLEMs | Classes | Non-degenerate | Universal |
|---|---|---|---|---|
| 2 | 24 | 8 | 4 | 3 proved not; 1 open |
| 3 | 720 | 24 | 14 | all |
| 4 | 40,320 | 82 | 55 | all |

Every non-degenerate 2-state RLEM with k > 2 can simulate the RE, so all of them are
universal.[^7] The line between k = 2 and k = 3 is a universality frontier of the kind
Margenstern studied for small Turing machines
([[aucm-ch5-small-universal-turing-machines](pages/aucm-ch5-small-universal-turing-machines.md)]).[^7]

**Physical realization.** The RE can be built directly in the
[[billiard-ball-model](pages/billiard-ball-model.md)] with a stationary state ball, so
input timing does not matter. Any m-state k-symbol RLEM with k ≤ 4 can be realized in that
model by a systematic method (Mukai and Morita).[^8]

## Appearances in Sources

- [[aucm-ch6-reversible-turing-machines-by-rlem](pages/aucm-ch6-reversible-turing-machines-by-rlem.md)] - definitions, the RE, counts and universality, billiard-ball realization

## Related Concepts

- [[reversible-turing-machine](pages/reversible-turing-machine.md)] - built as an infinite RE circuit
- [[billiard-ball-model](pages/billiard-ball-model.md)] - a physical model in which RLEMs can be realized
- [[reversible-cellular-automaton](pages/reversible-cellular-automaton.md)] - the cellular side of reversible computing
- [[universal-turing-machine](pages/universal-turing-machine.md)] - universality frontiers for small machines, the analogue of the k = 2 / k = 3 line

[^1]: [[aucm-ch6-reversible-turing-machines-by-rlem](pages/aucm-ch6-reversible-turing-machines-by-rlem.md)] p.128 (Definitions 1-2) [synthesis] — sequential machine M = (Q, Σ, Γ, δ) with δ: Q × Σ → Q × Γ; "If δ is injective, M is called a reversible sequential machine (RSM). Note that if M is reversible, |Σ| ≤ |Γ| must hold"; an RLEM is an RSM with |Σ| = |Γ|, "also called a |Q|-state |Γ|-symbol RLEM"
[^2]: [[aucm-ch6-reversible-turing-machines-by-rlem](pages/aucm-ch6-reversible-turing-machines-by-rlem.md)] p.127 — "There are two types of reversible logic elements: one without memory, which is commonly called a reversible logic gate [5, 19, 20], and one with memory [10, 16]."
[^3]: [[aucm-ch6-reversible-turing-machines-by-rlem](pages/aucm-ch6-reversible-turing-machines-by-rlem.md)] p.128 (Table 6.1) [synthesis] — δ_RE: H row n → Vw′, e → Hw′, s → Ve′, w → He′; V row n → Vs′, e → Hn′, s → Vn′, w → Hs′
[^4]: [[aucm-ch6-reversible-turing-machines-by-rlem](pages/aucm-ch6-reversible-turing-machines-by-rlem.md)] pp.128-129 [synthesis] — box with a rotatable bar; parallel particle exits the opposite side without changing the bar; orthogonal particle "makes a right turn, and rotates the bar by 90 degrees counterclockwise"
[^5]: [[aucm-ch6-reversible-turing-machines-by-rlem](pages/aucm-ch6-reversible-turing-machines-by-rlem.md)] p.129 — "It is shown that any RSM can be built using only REs [11], and that any reversible Turing machine is realized as an infinite circuit composed only of REs [10]. Hence, in such a sense RE is universal."
[^6]: [[aucm-ch6-reversible-turing-machines-by-rlem](pages/aucm-ch6-reversible-turing-machines-by-rlem.md)] p.129 [synthesis] — "There are (2k)! kinds of 2-state k-symbol RLEMs"; totals 24, 720, 40,320; equivalence classes 8, 24, 82; degenerate RLEMs equivalent to a 1-state RLEM ("mere connecting wires") or a 2-state RLEM with fewer symbols; non-degenerate 4, 14, 55
[^7]: [[aucm-ch6-reversible-turing-machines-by-rlem](pages/aucm-ch6-reversible-turing-machines-by-rlem.md)] p.129 [synthesis] — "As discussed in [9] by Margenstern, it is important to know the frontier between universality and non-universality"; "every non-degenerate 2-state k-symbol RLEM is universal if k > 2"; "for four non-degenerate 2-state 2-symbol RLEMs, three of them has been proved to be non-universal [18], but it is left open for the remaining one"
[^8]: [[aucm-ch6-reversible-turing-machines-by-rlem](pages/aucm-ch6-reversible-turing-machines-by-rlem.md)] pp.130-132 [synthesis] — direct BBM realization of RE with a stationary state ball, no input synchronization needed; "Mukai and Morita [17] showed any m-state k-symbol RLEM can be realized in BBM by a systematic method if k ≤ 4"
