---
title: Probabilistic Logic (automata)
category: Concepts
summary: Von Neumann's logic of unreliable automata — failure treated as a logical entity, with axioms giving probabilities of outcomes rather than certainties; the framework for the reliability problem
tags: [concept, probabilistic-logic, reliability, von-neumann]
sources: [tsra-lecture-3, tsra-editors-introduction, tsra-lecture-4]
created: 2026-09-24
updated: 2026-09-24
---

# Probabilistic Logic (automata)

## Description

Probabilistic logic is von Neumann's framework for the *reliability* problem, the second of
the two central problems of his [[theory-of-automata](pages/theory-of-automata.md)]: how to
build reliable systems from unreliable components.[^1]

**Motivation.** No practical automaton is truly reliable, so an axiomatization that fixes
exactly what happens in every situation misses part of the problem.[^2] Real automata are
organized mostly around how they can fail. Their safeguards aim to make most failures
non-lethal rather than to eliminate failure: "palliatives of failures, not cures."[^3]

**Form of the axioms.** Failure is admitted as an independent logical entity. Instead of
rules of the form "if A and B happen, C will follow", the axioms say "if A and B happen, C
will follow with a certain specified probability, D will follow with another specified
probability, and so on", in effect a probability matrix. Von Neumann holds that any
automaton of real complexity, natural or artificial, should be treated in this system.[^4]

**Why complexity forces it.** For a fixed chance of malfunction per component, the more
complex the automaton, the more likely a lethal failure.[^5] Reliability therefore limits
the complexity of the automata that can be built.[^6] Von Neumann saw this as the deeper
cause of the gap between natural and artificial automata. Artificial machines halt at the
first error, while natural automata operate across errors ([[self-repair](pages/self-repair.md)]).[^7] How reliable
an automaton is, like how fast or how good, is meaningful only relative to the milieu it
operates in.[^8]

**Mathematical character.** Probabilistic axioms would move the theory of automata away
from all-or-none, combinatorial logic and toward analysis, and would give it much in common
with thermodynamics.[^9] Von Neumann saw probability here as an extension of logic, not only
as a matter of frequencies.[^10] He developed the framework fully in the separate paper
"Probabilistic Logics and the Synthesis of Reliable Organisms from Unreliable Components,"
which this wiki has not ingested.[^11]

## Appearances in Sources

- [[tsra-lecture-3](pages/tsra-lecture-3.md)] — motivation and the form of the probabilistic axioms
- [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] — reliability as one of the two central problems
- [[tsra-lecture-4](pages/tsra-lecture-4.md)] — reliability as the limit on artificial complexity; milieu-relativity

## Related Concepts

- [[theory-of-automata](pages/theory-of-automata.md)] — reliability is one of its two central problems
- [[self-reproduction](pages/self-reproduction.md)] — the other central problem; self-repair links the two
- [[complexity-threshold](pages/complexity-threshold.md)] — complexity drives both problems
- [[maxwells-demon](pages/maxwells-demon.md)] — the entropy–information link behind the thermodynamic view of logic
- [[mcculloch-pitts-neuron](pages/mcculloch-pitts-neuron.md)] — the rigorous, all-or-none elements that probabilistic logic generalizes
- [[self-repair](pages/self-repair.md)] — how natural automata tolerate error in practice

[^1]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.19 — "How can reliable systems be constructed from unreliable components?"
[^2]: [[tsra-lecture-3](pages/tsra-lecture-3.md)] p.57 — "in no practical way can we imagine an automaton which is really reliable. If you axiomatize an automaton by telling exactly what it will do in every completely defined situation you are missing an important part of the problem."
[^3]: [[tsra-lecture-3](pages/tsra-lecture-3.md)] p.58 — "they are arrangements by which it is attempted to achieve a state where at least a majority of all failures will not be lethal. ... These arrangements give palliatives of failures, not cures."
[^4]: [[tsra-lecture-3](pages/tsra-lecture-3.md)] p.58 — "To permit failure as an independent logical entity means that one does not state the axioms in a rigorous manner. The axioms are not of the form: if A and B happen, C will follow. The axioms are always of this variety: If A and B happen, C will follow with a certain specified probability, D will follow with another specified probability, and so on. ... Both artificial and natural automata should be discussed in this system as soon as there is any degree of involvement."
[^5]: [[tsra-lecture-3](pages/tsra-lecture-3.md)] p.58 fn2 — "For a given probability of malfunction of a component, the more complex the automaton the more likely it is that a lethal failure will occur."
[^6]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.xvi — "The reliability of components limits the complexity of the automata we can build"
[^7]: [[tsra-lecture-4](pages/tsra-lecture-4.md)] pp.70-71 [synthesis] — error considerations "become more important as the system becomes more complex"; under the philosophy "that every error has to be caught, explained, and corrected, a system of the complexity of the living organism would not run for a millisecond. Such a system is so well integrated that it can operate across errors."
[^8]: [[tsra-lecture-4](pages/tsra-lecture-4.md)] p.72 — "it's meaningless to say that an automaton is good or bad, fast or slow, reliable or unreliable, without telling in what milieu it operates."
[^9]: [[tsra-lecture-3](pages/tsra-lecture-3.md)] p.62 [synthesis] — the new theory of information "is likely to have a lot in common with thermodynamics" and "will be closer to analysis, because all axioms are likely to be of a probabilistic and not of a rigorous character"
[^10]: [[tsra-lecture-3](pages/tsra-lecture-3.md)] p.58 — "Now this inclines one to view probability as a branch of logics, or rather, to view logics affected with probability as an extension of ordinary rigorous logics."
[^11]: [[tsra-lecture-3](pages/tsra-lecture-3.md)] p.58 fn1 — "See von Neumann's 'Probabilistic Logics and the Synthesis of Reliable Organs from Unreliable Components' for a detailed treatment of automata from this point of view."
