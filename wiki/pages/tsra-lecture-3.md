---
title: "Theory of Self-Reproducing Automata — Part I, Lecture 3: Statistical Theories of Information"
category: Sources
summary: Von Neumann's third Illinois lecture (1949) — failure as a logical entity, probabilistic axioms for automata, and the parallel between information and thermodynamic entropy
tags: [von-neumann, probabilistic-logic, reliability, entropy, information]
sources: [tsra-lecture-3]
created: 2026-09-24
updated: 2026-09-24
---

# Theory of Self-Reproducing Automata — Part I, Lecture 3: Statistical Theories of Information

**Source:** raw/von-neumann-theory-of-self-reproducing-automata.pdf, printed pp. 57–63 (PDF pp. 73–79)
**Date ingested:** 2026-09-24
**Type:** book section (reconstructed lecture, December 1949, with editorial commentary)
**Part of:** [[theory-of-self-reproducing-automata](pages/theory-of-self-reproducing-automata.md)]

> The middle of the lecture (pp. 59–62, on entropy, Szilard, Shannon, and digitalization) is
> mostly the editor's paraphrase and quotation from other von Neumann writings.

## Summary

Having covered the rigorous half of information theory in Lecture 2, von Neumann turns to
the statistical half. He gives two reasons it matters for automata. First, no practical
automaton is really reliable, so an axiomatization that says exactly what happens in every
situation misses an essential part of the problem.[^1] Second, the structure of real
automata, natural and artificial, is shaped less by their rigorous requirements than by how
they can fail and what guards against failure. Those guards only try to make most failures
non-lethal: "palliatives of failures, not cures."[^2]

This leads to [[probabilistic-logic](pages/probabilistic-logic.md)]. Failure is admitted as
an independent logical entity, and an automaton's axioms take the form "if A and B happen,
C will follow with a certain specified probability, D with another," which amounts to a
probability matrix. Von Neumann holds that any automaton of real complexity should be
treated this way.[^3]

The second half connects information with thermodynamic entropy. Von Neumann discussed the
paradox of [[maxwells-demon](pages/maxwells-demon.md)] and Szilard's resolution of it,
which relates entropy to information.[^4] He suspects that the degeneration laws of entropy
have analogs for information, and that an automaton's function cannot be defined without a
statistical, thermodynamic-style description of its environment.[^5] He concludes that the
needed theory of information will resemble formal logic, but will also have much in common
with thermodynamics and be closer to analysis than to combinatorics.[^6]

## Key Takeaways

- **Failure shapes structure.** Real automata are organized around how they fail, and aim
  to make most failures non-lethal rather than to prevent failure.[^2]
- **Probabilistic axioms.** Automata should be axiomatized with probabilities of outcomes,
  not certainties. Complexity makes this unavoidable, since a more complex automaton is
  more likely to suffer a lethal failure.[^3][^7]
- **Information ≈ entropy.** Degenerative processes in information parallel those in
  entropy, and an automaton's efficiency depends on a statistical description of its
  environment.[^5]
- **Analysis over combinatorics.** All-or-none logic belongs to combinatorics, "that part
  of mathematics of which we know the least". A probabilistic logic of automata would be
  closer to analysis.[^6]
- **Redundancy makes checking possible.** A maximally compressed language could not convey
  complex information, because errors could never be detected.[^8]

## Entities & Concepts

- [[probabilistic-logic](pages/probabilistic-logic.md)]
- [[maxwells-demon](pages/maxwells-demon.md)]
- [[theory-of-automata](pages/theory-of-automata.md)]
- [[complexity-threshold](pages/complexity-threshold.md)]

## Relation to Other Wiki Pages

This lecture is von Neumann's own statement of the probabilistic, thermodynamic program
that [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] summarizes. It
supplies the thermodynamic sense of "degeneration" used by the
[[complexity-threshold](pages/complexity-threshold.md)], and it opens the reliability
problem, the counterpart of [[self-reproduction](pages/self-reproduction.md)].

[^1]: [[tsra-lecture-3](pages/tsra-lecture-3.md)] p.57 — "in no practical way can we imagine an automaton which is really reliable. If you axiomatize an automaton by telling exactly what it will do in every completely defined situation you are missing an important part of the problem."
[^2]: [[tsra-lecture-3](pages/tsra-lecture-3.md)] pp.57-58 — "their structure is controlled only partly by rigorous requirements and is controlled to a much larger extent by the manner in which they might fail and by the (more or less effective) precautionary measures which have been taken against their failure. ... These arrangements give palliatives of failures, not cures."
[^3]: [[tsra-lecture-3](pages/tsra-lecture-3.md)] p.58 — "To permit failure as an independent logical entity means that one does not state the axioms in a rigorous manner. ... If A and B happen, C will follow with a certain specified probability, D will follow with another specified probability, and so on. ... Both artificial and natural automata should be discussed in this system as soon as there is any degree of involvement."
[^4]: [[tsra-lecture-3](pages/tsra-lecture-3.md)] pp.59-60 — "He explained at length the paradox of Maxwell's demon and how Szilard resolved it by working out the relation of entropy to information."
[^5]: [[tsra-lecture-3](pages/tsra-lecture-3.md)] p.62 — "There are strong indications that information is similar to entropy and that degenerative processes of entropy are paralleled by degenerative processes in the processing of information. It is likely that you cannot define the function of an automaton, or its efficiency, without characterizing the milieu in which it works by means of statistical traits like the ones used to characterize a milieu in thermodynamics."
[^6]: [[tsra-lecture-3](pages/tsra-lecture-3.md)] p.62 — "It is not surprising that this new theory of information should be like formal logics, but it is surprising that it is likely to have a lot in common with thermodynamics. ... These all-or-none processes are only weakly connected to analysis, which is the best developed and best known part of mathematics, while they are closely connected to combinatorics, that part of mathematics of which we know the least."
[^7]: [[tsra-lecture-3](pages/tsra-lecture-3.md)] p.58 fn2 — "For a given probability of malfunction of a component, the more complex the automaton the more likely it is that a lethal failure will occur."
[^8]: [[tsra-lecture-3](pages/tsra-lecture-3.md)] p.60 — "a language which has maximum compression would actually be completely unsuited to conveying information beyond a certain degree of complexity, because you could never find out whether a text is right or wrong."
