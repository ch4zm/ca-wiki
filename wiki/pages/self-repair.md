---
title: Self-Repair (automata)
category: Concepts
summary: An automaton's ability to detect faults in itself, isolate and bypass them, and correct them while continuing to operate — von Neumann's model of how natural automata tolerate error, and the bridge between reliability and self-reproduction
tags: [concept, self-repair, reliability, error-tolerance, von-neumann]
sources: [tsra-lecture-4, tsra-editors-introduction]
created: 2026-09-24
updated: 2026-09-24
---

# Self-Repair (automata)

## Description

Self-repair is the ability of an automaton to keep working while some of its parts fail,
by detecting, containing, and correcting the faults itself. In von Neumann's
[[theory-of-automata](pages/theory-of-automata.md)] it is how natural automata answer the
reliability problem that [[probabilistic-logic](pages/probabilistic-logic.md)] formalizes.

**Two philosophies of error.** As a system grows, the chance that some part fails stops
being negligible.[^1] Artificial automata of von Neumann's day used a single-error rule:
halt at the first fault and have the operator locate and correct it. Von Neumann argued
that a system as complex as a living organism would not run for a millisecond under that
rule.[^2] Natural automata *operate across errors*, following a protocol of four steps:

1. **Assess.** The system senses whether an error matters. If it doesn't, the system
   carries on and ignores it.
2. **Isolate.** If it does matter, the system blocks off the affected region.
3. **Bypass.** Operation continues along other channels.
4. **Repair or abandon.** The region is analyzed and corrected at leisure. If correction is
   impossible, it stays bypassed for good.

On this view, errors wear down the automaton gradually. It stays operable until enough
incurable errors and bypasses have piled up.[^2]

**Requirements.** Self-repair needs the automaton to monitor and reorganize itself, and so
needs a high degree of autonomy of its parts. Autonomy has a cost: when several parts can
each take control in an emergency, they can become antagonistic rather than
cooperative.[^3] At the level of materials, von Neumann points to the same contrast. A
damaged membrane reconstructs itself, while a shorted vacuum tube does not.[^4]

**Relation to self-reproduction.** Self-repair is closely related to
[[self-reproduction](pages/self-reproduction.md)], so much so that results on
self-reproduction were expected to help with reliability.[^5] Both are problems of high
complexity (see [[complexity-threshold](pages/complexity-threshold.md)]).

## Appearances in Sources

- [[tsra-lecture-4](pages/tsra-lecture-4.md)] — operating across errors, and autonomy of parts
- [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] — the link between self-repair and self-reproduction

## Related Concepts

- [[probabilistic-logic](pages/probabilistic-logic.md)] — the formal framework for unreliable components
- [[self-reproduction](pages/self-reproduction.md)] — the closely related constructive capacity
- [[complexity-threshold](pages/complexity-threshold.md)] — error handling becomes essential as complexity grows
- [[theory-of-automata](pages/theory-of-automata.md)] — self-repairing systems are among its natural automata

[^1]: [[tsra-lecture-4](pages/tsra-lecture-4.md)] p.70 — "In small systems the probability that the whole system will behave incorrectly is relatively small and may often be neglected, but this is not the case with large systems. Thus error considerations become more important as the system becomes more complex."
[^2]: [[tsra-lecture-4](pages/tsra-lecture-4.md)] p.71 — "a system of the complexity of the living organism would not run for a millisecond. Such a system is so well integrated that it can operate across errors. An error in it does not in general indicate a degenerative tendency. The system is sufficiently flexible and well organized that as soon as an error shows up in any part of it, the system automatically senses whether this error matters or not. If it doesn't matter, the system continues to operate without paying any attention to it. If the error seems to the system to be important, the system blocks that region out, by-passes it, and proceeds along other channels. The system then analyzes the region separately at leisure and corrects what goes on there, and if correction is impossible the system just blocks the region off and by-passes it forever. The duration of operability of the automaton is determined by the time it takes until so many incurable errors have occurred, so many alterations and permanent by-passes have been made, that finally the operability is really impaired."
[^3]: [[tsra-lecture-4](pages/tsra-lecture-4.md)] p.73 — "probably requires a very high flexibility and ability of the automaton to watch itself and reorganize itself. And this probably requires a very considerable autonomy of parts. ... When parts are autonomous and able to reorganize themselves, when there are several organs each capable of taking control in an emergency, an antagonistic relation can develop between the parts so that they are no longer friendly and cooperative."
[^4]: [[tsra-lecture-4](pages/tsra-lecture-4.md)] p.70 — "If a membrane is damaged it will reconstruct itself, but if a vacuum tube develops a short between its grid and cathode it will not reconstruct itself."
[^5]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.20 — "It is also to be expected that because of the close relation of self-reproduction to self-repair, results on self-reproduction would help solve the reliability problem."
