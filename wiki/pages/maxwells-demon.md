---
title: Maxwell's Demon
category: Concepts
summary: Thought experiment in which a being sorting molecules seems to reduce entropy for free; Szilard's resolution ties entropy to information, the link von Neumann used to argue that information processing obeys thermodynamic-style degeneration laws
tags: [concept, thermodynamics, entropy, information]
sources: [tsra-lecture-3, statistical-mechanics-of-cellular-automata]
created: 2026-09-24
updated: 2026-09-24
---

# Maxwell's Demon

## Description

Maxwell's demon is a thermodynamic thought experiment. A gas fills a box divided by a
partition with a small door, and a "demon" watches the molecules. It opens the door only
to let fast molecules pass one way and slow ones the other. One side heats up and the
other cools without any work being done, which appears to violate the second law of
thermodynamics.

The paradox is resolved by accounting for *information*. To sort the molecules, the demon
has to acquire and hold information about them, and that has an entropy cost that at least
offsets the entropy it removes from the gas. Szilard worked out this relation between
entropy and information, and von Neumann cites his analysis as a particularly instructive
treatment of the paradox.[^1]

**Role in the theory of automata.** For von Neumann, the demon is the clearest case of
information and entropy being two faces of one quantity. Both are measured by the
logarithm of a number of alternatives: Boltzmann's entropy is proportional to the log of
the number of microstates compatible with the macroscopic information we have.[^2] From
this he draws the conjecture behind his statistical theory of automata: the degeneration
laws that hold for entropy "have valid analogs when entropy is used as a measure of
information," so there should be connections between thermodynamics and new extensions of
logic.[^3] This is the sense of "degenerative" in the
[[complexity-threshold](pages/complexity-threshold.md)], and the reason he expected
[[probabilistic-logic](pages/probabilistic-logic.md)] to resemble thermodynamics.[^4]

**Entropy in cellular automata.** Wolfram measures entropy directly in cellular automata.
Their rules are irreversible, so an ensemble's entropy can *fall* over time, and the
second law as Wolfram states it applies only to reversible systems
([[irreversibility-and-entropy](pages/irreversibility-and-entropy.md)]).[^5] (Own
reasoning: the entropy drop comes from many-to-one evolution discarding information about
the past, rather than from any sorting agent.)

## Appearances in Sources

- [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] — entropy decrease under irreversible cellular automaton evolution
- [[tsra-lecture-3](pages/tsra-lecture-3.md)] — discussed via Szilard's resolution, as the bridge from entropy to information

## Related Concepts

- [[irreversibility-and-entropy](pages/irreversibility-and-entropy.md)] — entropy measured in cellular automata
- [[probabilistic-logic](pages/probabilistic-logic.md)] — the thermodynamic-style logic of automata the demon motivates
- [[complexity-threshold](pages/complexity-threshold.md)] — "degeneration" of complexity by analogy with entropy
- [[theory-of-automata](pages/theory-of-automata.md)] — its probabilistic, information-theoretic half

[^1]: [[tsra-lecture-3](pages/tsra-lecture-3.md)] pp.59-61 [synthesis] — "He explained at length the paradox of Maxwell's demon and how Szilard resolved it by working out the relation of entropy to information"; Szilard's work "contains a particularly instructive analysis of the famous thermodynamical paradox of 'Maxwell's demon'"
[^2]: [[tsra-lecture-3](pages/tsra-lecture-3.md)] pp.60-61 — "Boltzmann found entropy to be proportional to the logarithm of the number of alternatives which are possible for a physical system after all the information that one possesses about that system macroscopically ... has been recorded. In other words, it is proportional to the logarithm of the amount of missing information."
[^3]: [[tsra-lecture-3](pages/tsra-lecture-3.md)] p.61 — "There is reason to believe that the general degeneration laws, which hold when entropy is used as a measure of the hierarchic position of energy, have valid analogs when entropy is used as a measure of information. On this basis one may suspect the existence of connections between thermodynamics and new extensions of logics."
[^4]: [[tsra-lecture-3](pages/tsra-lecture-3.md)] p.62 — "There are strong indications that information is similar to entropy and that degenerative processes of entropy are paralleled by degenerative processes in the processing of information."
[^5]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] pp.601, 625 [synthesis] — the second law applies to isolated microscopically reversible systems, while dissipative irreversible systems may evolve to more ordered states; "for irreversible systems, such as cellular automata, the entropy may decrease with time"
