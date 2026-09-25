---
title: Garden-of-Eden Configuration
category: Concepts
summary: A cellular-automaton configuration that has no predecessor and so can only occur at time zero (Moore); stub pending the Moore and Myhill ingests
tags: [concept, garden-of-eden, moore, myhill, surjectivity]
sources: [tsra-part2-ch5, statistical-mechanics-of-cellular-automata]
created: 2026-09-24
updated: 2026-09-24
---

# Garden-of-Eden Configuration

> **Stub.** Everything here comes from a footnote in Burks's Ch. 5 of
> [[theory-of-self-reproducing-automata](pages/theory-of-self-reproducing-automata.md)]
> and from Sec. IV-V of
> [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)].
> Moore (1962), Myhill (1963) and Aggarwal (1973) are cited via those sources and have not
> been read yet.

## Description

Moore called a configuration that can exist only at time zero a "Garden-of-Eden"
configuration. It cannot arise from any earlier configuration.[^1]

**Relation to constructibility.** Every Garden-of-Eden configuration is non-constructible,
since nothing can build a pattern that has no predecessor. The converse fails: a
configuration can have predecessors and still be unbuildable by any constructor. Burks
gives an example in [[von-neumann-29-state-ca](pages/von-neumann-29-state-ca.md)] (a 3 × 3
block of sensitized S₀ in C₀₀; see
[[initially-quiescent-automaton](pages/initially-quiescent-automaton.md)]).[^1][^2]

**Existence.** In Burks's words, Moore "established a necessary condition" for
Garden-of-Eden configurations to exist in a cellular structure where information takes at
least one time step to pass from a cell to its neighbors, and Myhill showed the condition is
also sufficient. Burks says the condition amounts to the structure not being "backwards
deterministic", in the sense of Burks and Wang. Which direction each paper proves is to be
checked against Moore and Myhill directly.[^1]

**How common they are.** Wolfram links Garden-of-Eden configurations to irreversibility.
When a rule sends several configurations to the same one, some configurations have no
predecessor at all. He cites Moore (1962) and Aggarwal (1973) as giving criteria for their
existence, which he calls "equivalent to irreversibility".[^3] In one dimension they are
the typical case. On a ring of N cells, the non-additive rule 126 leaves a fraction of
configurations unreachable that tends to 1 as N grows (about 1 − 0.88ᴺ). The additive
[[rule-90](pages/rule-90.md)] leaves exactly half or three quarters unreachable, and only
the identity rule 204 reaches everything.[^4] In the [[game-of-life](pages/game-of-life.md)],
the smallest known example in 1983 had about 300 cells.[^5] See
[[irreversibility-and-entropy](pages/irreversibility-and-entropy.md)].

## Appearances in Sources

- [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] — Garden-of-Eden configurations as a consequence of irreversibility, and how common they are in 1D rules and Life
- [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] — footnote 12 to §5.3.1, relating non-constructibility to Moore and Myhill

## Related Concepts

- [[irreversibility-and-entropy](pages/irreversibility-and-entropy.md)] — the many-to-one evolution that produces them
- [[initially-quiescent-automaton](pages/initially-quiescent-automaton.md)] — the class a constructor can build; Garden-of-Eden patterns lie wholly outside it
- [[universal-constructor](pages/universal-constructor.md)] — no constructor can build a Garden-of-Eden pattern
- [[cellular-automaton](pages/cellular-automaton.md)] — the general setting

[^1]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] p.291 n.12 [synthesis] — Moore called a configuration that can exist only at time zero a "Garden-of-Eden" configuration; every such configuration is non-constructible, not conversely; Moore established a necessary condition for their existence where information needs at least 1 unit of time to pass between neighbors; Myhill showed it is also sufficient; the condition is essentially non-backwards-determinism (Burks and Wang)
[^2]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] p.291 [synthesis] — the 3 × 3 configuration of sensitized S₀ surrounded by C₀₀ is not constructible
[^3]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.623 n.10 — "The existence of unreachable or 'garden-of-Eden' configurations in cellular automata is discussed in Moore (1962) and Aggarwal (1973), where criteria (equivalent to irreversibility) for their occurrence are given."
[^4]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.623 [synthesis] — rule 204 is unique in allowing all configurations to be reached; rule 90 reaches half (N odd) or ¼ (N even); rule 126 unreachable fraction tends to one, behaving as 1 − λᴺ with λ ≈ 0.88 (Martin et al. 1983, cited via this paper)
[^5]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] p.637 — "the simplest known 'unreachable' configuration contains around 300 sites"
