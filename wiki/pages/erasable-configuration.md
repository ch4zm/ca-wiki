---
title: Erasable Configuration
category: Concepts
summary: Moore's term for a finite pattern that has a different "twin" with identical surroundings and an identical next step - local information loss; it exists exactly when Garden-of-Eden configurations do
tags: [concept, erasable-configuration, moore, garden-of-eden, irreversibility]
sources: [machine-models-of-self-reproduction, converse-of-moores-garden-of-eden-theorem]
created: 2026-09-24
updated: 2026-09-24
---

# Erasable Configuration

## Description

**Erasing** is an irreversible process
([[irreversibility-and-entropy](pages/irreversibility-and-entropy.md)]): an action produces a state from which the earlier
states that led to it cannot be recovered, as with an erased blackboard.[^1] Moore makes
this precise for a cellular structure, which he calls a tessellation structure
([[cellular-automaton](pages/cellular-automaton.md)]).

**Why the definition is careful.** In a rule where each cell copies its left neighbour,
the contents of a fixed block are lost, but only because they have moved to the right.
Nothing is destroyed. The definition therefore has to check that information is not
carried out of the block into its neighbours, and that none is carried in from
outside.[^2]

**Definition.** Take two square arrays of the same size, each made of an inner block and
two boundary layers around it. At time T the inner blocks differ (F ≠ F*), while the first
layer (G) and the second layer (H) are the same in both. If at time T + 1 the inner blocks
and first layers are again identical (f and g), the two configurations are **mutually
erasable**. The outer layer h is left out at T + 1 because it depends on cells beyond all
the arrays considered.[^3] A configuration is **erasable** if some other configuration is
mutually erasable with it. Moore had earlier called this a "configuration which can
forget".[^4]

**Properties.** Being mutually erasable or a copy is an equivalence relation, which the
proof of the Garden-of-Eden theorem uses to count classes of blocks. Any pattern that
contains an erasable configuration is itself erasable, so an erasable configuration can be
taken to sit in a square array.[^5] Not every structure has erasable configurations. Where
they cannot occur, only a restricted class of construction and computation is
possible.[^6]

**Garden-of-Eden theorem.** Moore's Theorem 2: if a tessellation structure has erasable
configurations, it has [[garden-of-eden](pages/garden-of-eden.md)]
configurations.[^7] [[john-myhill](pages/john-myhill.md)] proved the converse, so the two
conditions are equivalent (the [[garden-of-eden-theorem](pages/garden-of-eden-theorem.md)]).[^8]

**Indistinguishable configurations.** Myhill restates erasability using *environments*. An
environment fixes every cell except a square hole, and two configurations of the same size
are *distinguished* by it if inserting each into the hole gives different states one step
later. His referee noted that a mutually erasable pair exists exactly when some two
configurations are distinguished by no environment. If every pair can be told apart by some
environment, every pair can be told apart by every environment of the right size, including
the all-quiescent one.[^9] In modern terms, erasability is the failure of the global rule to
be injective on finite patterns, and a Garden-of-Eden configuration is a failure of
surjectivity. That framing is the wiki's own summary, not the papers' wording.

**Open questions from Moore.** Can a structure have a self-reproducing configuration and
no erasable one? Does the fraction of n-state structures with erasable configurations tend
to 1 as n grows? In every structure Moore examined, the inner block of an erasable pair
could be a single cell. Is that always possible?[^10]

## Appearances in Sources

- [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] - definition, role in Theorem 2, and open problems
- [[converse-of-moores-garden-of-eden-theorem](pages/converse-of-moores-garden-of-eden-theorem.md)] - the equivalent notion of indistinguishable configurations, and the converse

## Related Concepts

- [[garden-of-eden](pages/garden-of-eden.md)] - exist exactly when erasable configurations do
- [[garden-of-eden-theorem](pages/garden-of-eden-theorem.md)] - the equivalence
- [[cellular-automaton](pages/cellular-automaton.md)] - the setting
- [[self-reproduction](pages/self-reproduction.md)] - whether it needs erasability is open

[^1]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] p.24 - "Erasing is an irreversible process whereby a given action produces a state from which it is impossible to determine the preceding states from which it could have arisen."
[^2]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] p.24 [synthesis] - under a shift rule the past state "has merely been shifted off to the right and not destroyed"; the definition must watch neighbouring cells so information is not carried away, and their neighbours so new information is not shifted in
[^3]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] pp.24-25 [synthesis] - Figs. 4-5: inner arrays F ≠ F* with identical boundary layers G and H at time T; identical f and g at T + 1; h cannot generally be specified
[^4]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] p.25 [synthesis] - erasable configuration defined as one with a mutually erasable partner; called a "configuration which can forget" in Moore's 1959 abstract
[^5]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] p.25 [synthesis] - configurations fall into equivalence classes of copies or mutually erasable patterns; if c contains a copy of an erasable configuration then c is erasable, so an erasable configuration can be associated with a square array
[^6]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] p.26 - "If the function f defining the transitions and the states has the property that such irreversible transitions cannot take place, then only a restricted class of methods of construction and computation can take place."
[^7]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] p.26 - "THEOREM 2. For a tessellation structure for which there exist erasable configurations, there exist Garden-of-Eden configurations."
[^8]: [[converse-of-moores-garden-of-eden-theorem](pages/converse-of-moores-garden-of-eden-theorem.md)] p.686 - "the existence of two indistinguishable configurations is a necessary as well as a sufficient condition for the existence of Garden-of-Eden configurations."
[^9]: [[converse-of-moores-garden-of-eden-theorem](pages/converse-of-moores-garden-of-eden-theorem.md)] p.685 and n.2, p.686 [synthesis] - environment, insertion, sequent, and distinguishing environments defined; the referee's equivalence of mutual erasability with indistinguishability; the strengthened Lemma that distinguishability by some environment implies by every environment; the Lemma for the all-passive environment E₀
[^10]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] p.30 [synthesis] - open problems: self-reproduction without erasable configurations; fraction of n-state structures with erasable configurations approaching 1; one-cell inner arrays in every structure examined
