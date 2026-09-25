---
title: Overview
tags: [overview, synthesis]
sources: [theory-of-self-reproducing-automata, tsra-editors-introduction, tsra-lecture-2, tsra-lecture-3, tsra-lecture-4, tsra-lecture-5, tsra-part2-ch1, tsra-part2-ch2, tsra-part2-ch3, tsra-part2-ch4, tsra-part2-ch5, machine-models-of-self-reproduction, converse-of-moores-garden-of-eden-theorem]
updated: 2026-09-24
---

# Cellular Automata — Overview

> Evolving synthesis of everything in the wiki. Updated by wiki-ingest when sources shift the understanding.

## Current Understanding

Cellular automata begin with von Neumann's [[theory-of-automata](pages/theory-of-automata.md)], a logical and
mathematical theory of how automata, natural and artificial, are organized. Its organizing
concept is complexity, and its two central problems are
[[self-reproduction](pages/self-reproduction.md)] and reliability.

**Foundations.** Two logical ingredients underlie everything: networks of idealized
threshold elements ([[mcculloch-pitts-neuron](pages/mcculloch-pitts-neuron.md)]) and Turing's
[[universal-turing-machine](pages/universal-turing-machine.md)]. Universality has a threshold: above a minimum complexity,
one automaton can do anything any automaton can do. It still cannot predict arbitrary
behavior, which suggests that complex automata may be simpler than any description of what
they do ([[description-vs-object-complexity](pages/description-vs-object-complexity.md)]).

**Self-reproduction.** Below a [[complexity-threshold](pages/complexity-threshold.md)], automata can only build simpler
automata. Above it, self-reproduction works through the [[universal-constructor](pages/universal-constructor.md)]
scheme: build from a description, copy the description, attach the copy. Von Neumann first
set this out in a [[kinematic-self-reproduction](pages/kinematic-self-reproduction.md)] model. He then abstracted it into a
[[cellular-automaton](pages/cellular-automaton.md)], a homogeneous lattice of identical finite-state cells where
construction means changing cell states. The key move is to copy a quiescent description
rather than the live automaton ([[descriptions-vs-originals](pages/descriptions-vs-originals.md)]).

**The cellular machine.** The concrete medium is [[von-neumann-29-state-ca](pages/von-neumann-29-state-ca.md)]. Ordinary
stimuli do logic, special stimuli build and destroy, and a [[construction-arm](pages/construction-arm.md)] places
cells at a distance. From the rule von Neumann builds a library of organs:
[[signal-coding-organs](pages/signal-coding-organs.md)] for timed bit patterns and one-bit memory, and a
[[coded-channel](pages/coded-channel.md)] that gets around wire-crossing in 2D. These are assembled into a
[[cellular-tape](pages/cellular-tape.md)]: unbounded memory reached by an extendible wire loop, with position and timing
both measured relative to the tape. Controller plus tape is a Turing machine inside the CA.

**The completed machine.** Burks finishes the design. A two-path [[construction-arm](pages/construction-arm.md)] makes
every construction step a fixed pulse sequence, and a [[crossing-organ](pages/crossing-organ.md)] lets signals truly
cross. Every buildable machine has to be an [[initially-quiescent-automaton](pages/initially-quiescent-automaton.md)], laid down
inert and switched on afterwards. Within that constraint the 29-state rule holds a universal
Turing machine, a universal constructor, and a self-reproducer, which may carry a Turing
machine as payload. Construction and computation turn out to be the same kind of activity.
Some patterns can never be built, the extreme case being [[garden-of-eden](pages/garden-of-eden.md)]
configurations, which have no predecessor.

**Moore's formalization.** Moore recasts the cellular model as a *tessellation structure*
on the nine-cell [[moore-neighbourhood](pages/moore-neighbourhood.md)] and gives
self-reproduction a formal definition, which admits trivial crystal-like cases. Locality
caps offspring at quadratic growth in time. His Garden-of-Eden theorem says that wherever
an [[erasable-configuration](pages/erasable-configuration.md)] exists, so do patterns with
no predecessor, and no self-reproducer can contain one. Myhill proved the converse, so the
[[garden-of-eden-theorem](pages/garden-of-eden-theorem.md)] is an equivalence: Garden-of-Eden patterns exist exactly
when two different patterns can be indistinguishable after one step. He also surveys working kinematic
reproducers (Penrose's shaken blocks, Jacobson's model trains).

**Reliability.** Von Neumann proposed a [[probabilistic-logic](pages/probabilistic-logic.md)] in which failure is part
of the axioms, bringing the theory closer to analysis and thermodynamics, via the
entropy–information link illustrated by [[maxwells-demon](pages/maxwells-demon.md)]. Natural automata survive
unreliable parts through [[self-repair](pages/self-repair.md)]: they operate across errors instead of halting
on the first one.

## Open Questions

- What exactly is von Neumann's complexity threshold, and does the 29-state construction
  make it precise? Von Neumann guessed millions of parts for the kinematic model.
- How do the kinematic (Part I) and cellular (Part II) models of self-reproduction differ
  in what they assume?
- Von Neumann's design is serial and ignores the medium's parallelism. How much smaller could
  a parallel self-reproducer be?
- How small can the smallest Garden-of-Eden pattern be? Moore always found one within
  5 × 5, while the Moore-Myhill counting argument gives enormous ones.
- Can self-reproduction happen in a structure with no erasable configurations?
- How can "less trivial" self-reproduction be made precise?

## Key Entities / Concepts

- [[theory-of-automata](pages/theory-of-automata.md)]
- [[self-reproduction](pages/self-reproduction.md)]
- [[complexity-threshold](pages/complexity-threshold.md)]
- [[mcculloch-pitts-neuron](pages/mcculloch-pitts-neuron.md)]
- [[universal-turing-machine](pages/universal-turing-machine.md)]
- [[description-vs-object-complexity](pages/description-vs-object-complexity.md)]
- [[probabilistic-logic](pages/probabilistic-logic.md)]
- [[maxwells-demon](pages/maxwells-demon.md)]
- [[self-repair](pages/self-repair.md)]
- [[universal-constructor](pages/universal-constructor.md)]
- [[kinematic-self-reproduction](pages/kinematic-self-reproduction.md)]
- [[cellular-automaton](pages/cellular-automaton.md)]
- [[descriptions-vs-originals](pages/descriptions-vs-originals.md)]
- [[von-neumann-29-state-ca](pages/von-neumann-29-state-ca.md)]
- [[construction-arm](pages/construction-arm.md)]
- [[signal-coding-organs](pages/signal-coding-organs.md)]
- [[coded-channel](pages/coded-channel.md)]
- [[cellular-tape](pages/cellular-tape.md)]
- [[initially-quiescent-automaton](pages/initially-quiescent-automaton.md)]
- [[crossing-organ](pages/crossing-organ.md)]
- [[garden-of-eden](pages/garden-of-eden.md)]
- [[garden-of-eden-theorem](pages/garden-of-eden-theorem.md)]
- [[edward-f-moore](pages/edward-f-moore.md)]
- [[john-myhill](pages/john-myhill.md)]
- [[erasable-configuration](pages/erasable-configuration.md)]
- [[moore-neighbourhood](pages/moore-neighbourhood.md)]
