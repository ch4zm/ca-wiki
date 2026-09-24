---
title: "Theory of Self-Reproducing Automata — Part I, Lecture 4: The Role of High and of Extremely High Complication"
category: Sources
summary: Von Neumann's fourth Illinois lecture (1949) — complexity minima and square-law growth of interrelationships, reliability as the limit on artificial complexity, operating across errors, and autonomy of parts
tags: [von-neumann, complexity, reliability, self-repair, digital]
sources: [tsra-lecture-4]
created: 2026-09-24
updated: 2026-09-24
---

# Theory of Self-Reproducing Automata — Part I, Lecture 4: The Role of High and of Extremely High Complication

**Source:** raw/von-neumann-theory-of-self-reproducing-automata.pdf, printed pp. 64–73 (PDF pp. 80–89)
**Date ingested:** 2026-09-24
**Type:** book section (reconstructed lecture, December 1949, with editorial commentary)
**Part of:** [[theory-of-self-reproducing-automata](pages/theory-of-self-reproducing-automata.md)]

> Several passages (energy dissipation, memory devices, error-rate calculations) are the
> editor's paraphrase. This page leaves out the hardware and energy figures.

## Summary

Von Neumann compares natural and artificial automata in terms of complexity and asks why
the gap between them is so large. The human nervous system is roughly a million times more
complicated than the largest machines of his day, and "even measuring complexity on a
logarithmic scale ... we have not yet come half the way."[^1] Size matters more than
proportionally. Capability grows with the interrelationships between components, which go
up with the square of their number, and some capabilities exist only above a minimum level
of complexity ([[complexity-threshold](pages/complexity-threshold.md)]).[^2]

He locates the deeper cause of the gap in reliability. In a small system the chance that
the whole thing misbehaves can be neglected. In a large one it cannot, so error
considerations become more important as complexity grows.[^3] Artificial automata stop at
the first error and wait for it to be located and corrected. Von Neumann argues that a
system as complex as a living organism run on that principle "would not run for a
millisecond." Natural automata instead *operate across errors*: they judge whether an
error matters, and they isolate, bypass, and later repair the damaged region
([[self-repair](pages/self-repair.md)]).[^4] That ability needs the automaton to watch and
reorganize itself, and so needs considerable autonomy of its parts. Autonomous parts can
in turn become antagonistic to one another.[^5]

Two further claims bear on the abstract theory. First, complicated functions need
*digital* mechanisms. Pure analog mechanisms cannot handle very complicated situations
except by breaking them into parts handled separately and in turn, which is "a digital
trick."[^6] Second, an automaton cannot be assessed apart from its milieu. Speed,
reliability, and quality are meaningful only relative to the statistical character of the
environment or problems it faces.[^7]

## Key Takeaways

- **Complexity is superlinear and thresholded.** Interrelationships grow as the square of
  component count, and "below a certain minimum level of complexity you cannot do a
  certain thing."[^2]
- **Reliability limits artificial complexity.** Errors that can be ignored in small systems
  come to dominate large ones.[^3]
- **Operate across errors.** Natural automata sense, isolate, bypass, and repair faults
  instead of halting on the first one.[^4]
- **Autonomy of parts.** Self-monitoring and reorganization need autonomous parts, which
  can become antagonistic.[^5]
- **Complexity needs digital.** Handling complicated situations requires splitting them
  into discrete parts.[^6]
- **Milieu-relativity.** An automaton's properties are defined only relative to its
  environment.[^7]

## Entities & Concepts

- [[complexity-threshold](pages/complexity-threshold.md)]
- [[self-repair](pages/self-repair.md)]
- [[probabilistic-logic](pages/probabilistic-logic.md)]
- [[theory-of-automata](pages/theory-of-automata.md)]

## Relation to Other Wiki Pages

This lecture gives von Neumann's own general statement of the complexity minima behind the
[[complexity-threshold](pages/complexity-threshold.md)]. The specific threshold for
self-reproduction comes in Lecture 5. It also turns the reliability problem of
[[probabilistic-logic](pages/probabilistic-logic.md)] into a concrete account of how
natural automata tolerate error, which connects to [[self-reproduction](pages/self-reproduction.md)]
through [[self-repair](pages/self-repair.md)].

[^1]: [[tsra-lecture-4](pages/tsra-lecture-4.md)] p.65 — "So the human nervous system is roughly a million times more complicated than these large computing machines. ... Even measuring complexity on a logarithmic scale, which is highly generous, we have not yet come half the way. I think that in any sensible definition of complexity, it would be much less than half way."
[^2]: [[tsra-lecture-4](pages/tsra-lecture-4.md)] pp.65-66 — "an n-fold increase in size brings much more than an n-fold increase in what can be done. What can be done is a matter of the interrelationships between the components, and the number of interrelationships increases with the square of the number of components. And apart from this, what can be done depends on certain minima. Below a certain minimum level of complexity you cannot do a certain thing, but above this minimum level of complexity you can do it."
[^3]: [[tsra-lecture-4](pages/tsra-lecture-4.md)] p.70 — "In small systems the probability that the whole system will behave incorrectly is relatively small and may often be neglected, but this is not the case with large systems. Thus error considerations become more important as the system becomes more complex."
[^4]: [[tsra-lecture-4](pages/tsra-lecture-4.md)] p.71 — "on the basis of the philosophy that every error has to be caught, explained, and corrected, a system of the complexity of the living organism would not run for a millisecond. Such a system is so well integrated that it can operate across errors. ... If the error seems to the system to be important, the system blocks that region out, by-passes it, and proceeds along other channels. The system then analyzes the region separately at leisure and corrects what goes on there, and if correction is impossible the system just blocks the region off and by-passes it forever."
[^5]: [[tsra-lecture-4](pages/tsra-lecture-4.md)] p.73 — "The ability of a natural organism to survive in spite of a high incidence of error ... probably requires a very high flexibility and ability of the automaton to watch itself and reorganize itself. And this probably requires a very considerable autonomy of parts. ... an antagonistic relation can develop between the parts so that they are no longer friendly and cooperative."
[^6]: [[tsra-lecture-4](pages/tsra-lecture-4.md)] pp.69-70 — "digital mechanisms are necessary for complicated functions. Pure analog mechanisms are usually not suited for very complicated situations. The only way to handle a complicated situation with analog mechanisms is to break it up into parts and deal with the parts separately and alternately, and this is a digital trick."
[^7]: [[tsra-lecture-4](pages/tsra-lecture-4.md)] p.72 — "An automaton can not be separated from the milieu to which it responds. By that I mean that it's meaningless to say that an automaton is good or bad, fast or slow, reliable or unreliable, without telling in what milieu it operates."
