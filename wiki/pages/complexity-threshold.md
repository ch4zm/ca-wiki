---
title: Complexity Threshold
category: Concepts
summary: Von Neumann's claim that below a critical level of complexity automata can only build simpler things, while above it self-reproduction and growth of complexity become possible
tags: [concept, complexity, self-reproduction, von-neumann]
sources: [tsra-editors-introduction, tsra-lecture-1, tsra-lecture-2, tsra-lecture-3, tsra-lecture-4, tsra-lecture-5, computation-at-the-edge-of-chaos, aucm-ch5-small-universal-turing-machines]
created: 2026-09-24
updated: 2026-09-24
---

# Complexity Threshold

## Description

Von Neumann's general principle is that capability depends on minima: "Below a certain
minimum level of complexity you cannot do a certain thing, but above this minimum level
of complexity you can do it." Capability also grows faster than size, because the
interrelationships between components grow with the square of their number.[^1]

Applied to construction, complexity has a critical level. Von Neumann arrived at it from
a paradox. Organisms reproduce and, over evolution, grow more complex. Yet an automaton
that builds another seems to need a complete description of its product, which suggests
that synthesis always degrades.[^2] His resolution is a critical size.
Below it, complexity is *degenerative*: an automaton can only produce automata less
complicated than itself, so [[self-reproduction](pages/self-reproduction.md)] is
impossible.[^3] Above it, complexity and organization are no longer degenerative and can
even increase. Burks calls this an analogue of
thermodynamic degeneration within the theory of self-reproducing automata.[^4] The
analogy rests on von Neumann's view that information behaves like entropy, so that
degenerative processes of entropy have parallels in information processing (see
[[maxwells-demon](pages/maxwells-demon.md)]).[^5]

A related claim concerns descriptions: at high complexity, the automaton is simpler than
any description of its behavior. See [[description-vs-object-complexity](pages/description-vs-object-complexity.md)].[^6]

**Threshold for universality.** Turing's universal machine shows the same pattern in
computation. Below a certain minimum complexity, no instructions let an automaton
perform certain operations. At a definite finite point, an automaton given suitable
instructions can do anything any automaton can do.[^7] The self-reproduction threshold
is the counterpart of this for construction. The field of small universal Turing machines
tries to locate this threshold for program size. It is still open for 39 (states, symbols)
pairs, while for some other properties of 2-symbol machines, such as laterality (the
smaller of the left-move and right-move instruction counts), it is known exactly ([[universal-turing-machine](pages/universal-turing-machine.md)]).[^8]

As a working measure of complexity, von Neumann counts an automaton's basic switching
elements. On that measure the computing machines of 1949 were of order 10⁴, while the
human nervous system is estimated at 10¹⁰ neurons, a size for which "we have absolutely
no experience."[^9] He put the nervous system at about a million times more complicated
than the largest machines, and added that "even measuring complexity on a logarithmic
scale ... we have not yet come half the way."[^10] As complexity grows, errors also stop
being negligible, which is why [[self-repair](pages/self-repair.md)] matters for highly complex automata.[^11]

In von Neumann's view, complexity is the organizing concept of the whole
[[theory-of-automata](pages/theory-of-automata.md)], and it still needed a rigorous
definition.[^12]

**Where the threshold lies.** Measured even crudely by number of elementary parts, von
Neumann guessed the critical size is large, perhaps in the millions of parts for his
kinematic part set ([[kinematic-self-reproduction](pages/kinematic-self-reproduction.md)]). Above it, synthesis "can become explosive": each automaton can
produce others more complex than itself. He called this the decisive property of
complexity. He also held that complication cannot be properly defined until critical
examples like this are worked out, much as energy and entropy were abstracted from
simple systems.[^13] The [[universal-constructor](pages/universal-constructor.md)] scheme shows how self-reproduction works above the
threshold.

**An upper bound.** Langton (1990) quotes the critical-size passage and, using a "slightly
different sense" of complexity, adds a second limit. Above some level of complexity,
synthesis is degenerative again. Open-ended synthesis needs complexity between a lower and
an upper bound. In his cellular-automaton surveys the two bounds lie close together, near
an order-chaos phase transition ([[edge-of-chaos](pages/edge-of-chaos.md)]).[^14]

## Appearances in Sources

- [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] — Burks's summary, with the thermodynamic analogy
- [[tsra-lecture-1](pages/tsra-lecture-1.md)] — element count as the working measure of complexity
- [[tsra-lecture-2](pages/tsra-lecture-2.md)] — the minimum complexity for universality
- [[tsra-lecture-3](pages/tsra-lecture-3.md)] — the entropy analogy behind "degeneration"
- [[tsra-lecture-5](pages/tsra-lecture-5.md)] — primary statement of the threshold for synthesis and self-reproduction
- [[tsra-lecture-4](pages/tsra-lecture-4.md)] — the general principle of minima, and square-law growth of interrelationships
- [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] - Langton's upper bound, at the edge of chaos
- [[aucm-ch5-small-universal-turing-machines](pages/aucm-ch5-small-universal-turing-machines.md)] - bounds on the size of a universal Turing machine

## Related Concepts

- [[self-reproduction](pages/self-reproduction.md)] — becomes possible above the threshold
- [[universal-constructor](pages/universal-constructor.md)] — the mechanism of self-reproduction above the threshold
- [[theory-of-automata](pages/theory-of-automata.md)] — complexity is its central concept
- [[description-vs-object-complexity](pages/description-vs-object-complexity.md)] — the description-side claim about high complexity
- [[universal-turing-machine](pages/universal-turing-machine.md)] — universality also needs a minimum complexity
- [[maxwells-demon](pages/maxwells-demon.md)] — the entropy–information link behind the degeneration analogy
- [[self-repair](pages/self-repair.md)] — how highly complex automata survive the errors complexity brings
- [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] - Moore's open problem on the simplest structure with non-trivial self-reproduction
- [[probabilistic-logic](pages/probabilistic-logic.md)] — complexity also raises the odds of lethal failure
- [[edge-of-chaos](pages/edge-of-chaos.md)] - where Langton puts both bounds

[^1]: [[tsra-lecture-4](pages/tsra-lecture-4.md)] pp.65-66 — "an n-fold increase in size brings much more than an n-fold increase in what can be done. What can be done is a matter of the interrelationships between the components, and the number of interrelationships increases with the square of the number of components. And apart from this, what can be done depends on certain minima. Below a certain minimum level of complexity you cannot do a certain thing, but above this minimum level of complexity you can do it."
[^2]: [[tsra-lecture-5](pages/tsra-lecture-5.md)] pp.78-79 [synthesis] — living organisms reproduce and grow more complex phylogenetically, while an automaton A that makes B must contain a complete description of B, suggesting complication is degenerative
[^3]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.23 — "He thought, for example, that below a certain level, complexity is degenerative, and self-reproduction is impossible."
[^4]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.28 — "he found an analog of thermodynamic degeneration in the theory of self-reproducing automata: below a certain minimum level, complexity and degree of organization are degenerative, but above that level they are not degenerative and may even increase."
[^5]: [[tsra-lecture-3](pages/tsra-lecture-3.md)] p.62 — "There are strong indications that information is similar to entropy and that degenerative processes of entropy are paralleled by degenerative processes in the processing of information."
[^6]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.23 — "in the case of simple automata a symbolic description of the behavior of an automaton is simpler than the automaton itself, but that in the case of exceedingly complex automata the automaton is simpler than a symbolic description of its behavior. See the Second Lecture of Part I."
[^7]: [[tsra-lecture-2](pages/tsra-lecture-2.md)] p.50 — "... a simpler thing will never perform certain operations, no matter what instructions you give it; but there is a very definite finite point where an automaton of this complexity can, when given suitable instructions, do anything that can be done by automata at all."
[^8]: [[aucm-ch5-small-universal-turing-machines](pages/aucm-ch5-small-universal-turing-machines.md)] pp.117-120 [synthesis] — "finding the shortest programs that are capable of universal computation and showing that below this threshold such complicated behaviour is impossible"; 39 open state-symbol pairs; matching upper and lower bounds ("a frontier") for colours and laterality of 2-symbol machines
[^9]: [[tsra-lecture-1](pages/tsra-lecture-1.md)] pp.36-37 [synthesis] — "It is not completely obvious how to measure the complexity of an automaton. For computing machines, probably the reasonable way is to count how many vacuum tubes are involved"; complexity of current machines of order "10 thousand"; human nervous system "estimated to be 10 billion", and "we have absolutely no experience with such orders of magnitude"
[^10]: [[tsra-lecture-4](pages/tsra-lecture-4.md)] p.65 — "So the human nervous system is roughly a million times more complicated than these large computing machines. ... Even measuring complexity on a logarithmic scale, which is highly generous, we have not yet come half the way."
[^11]: [[tsra-lecture-4](pages/tsra-lecture-4.md)] p.70 — "Thus error considerations become more important as the system becomes more complex."
[^12]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.23 — "Von Neumann thought that the chief problems of automata theory center around the concept of complexity. This very concept needs rigorous definition."
[^13]: [[tsra-lecture-5](pages/tsra-lecture-5.md)] pp.79-80 [synthesis] — complication is degenerative below a minimum number of parts, probably in the millions for his parts; above it synthesis "can become explosive"; complication cannot be defined correctly until critical examples are studied, as with energy and entropy
[^14]: [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] pp.35-36 [synthesis] - quotes von Neumann's 1949 critical-size passage; "a slightly different sense of 'complexity'"; "above a certain level of 'complexity', the process of synthesis is also degenerative"; "there exist an upper limit as well as a lower limit"; the bounds are "fairly close together and are located in the vicinity of a phase transition"
