---
title: Overview
tags: [overview, synthesis]
sources: [theory-of-self-reproducing-automata, tsra-editors-introduction, tsra-lecture-2, tsra-lecture-3, tsra-lecture-4, tsra-lecture-5, tsra-part2-ch1]
updated: 2026-09-24
---

# Cellular Automata — Overview

> Evolving synthesis of everything in the wiki. Updated by wiki-ingest when sources shift the understanding.

## Current Understanding

Cellular automata begin with von Neumann's [[theory-of-automata](pages/theory-of-automata.md)].
He intended it as a logical and mathematical theory of how automata, natural and
artificial, are organized. Its founding question was
[[self-reproduction](pages/self-reproduction.md)]: what logical organization is enough
for an automaton to build a copy of itself? He answered it first with a kinematic model,
and then as a cellular automaton
([[theory-of-self-reproducing-automata](pages/theory-of-self-reproducing-automata.md)]).

Two logical ingredients underlie the construction: finite networks of threshold elements
([[mcculloch-pitts-neuron](pages/mcculloch-pitts-neuron.md)]), and Turing's
[[universal-turing-machine](pages/universal-turing-machine.md)], which von Neumann carried
over from computation to construction. The theory's organizing concept is complexity.
Von Neumann claimed a [[complexity-threshold](pages/complexity-threshold.md)] exists,
below which automata can only build simpler automata. Above it, self-reproduction works
through the [[universal-constructor](pages/universal-constructor.md)] scheme: build from a description, copy the description, attach it. This
was first set out in the [[kinematic-self-reproduction](pages/kinematic-self-reproduction.md)] model. Von Neumann then
abstracted it into a [[cellular-automaton](pages/cellular-automaton.md)], a homogeneous lattice of identical finite-state cells, where
construction becomes changing cell states. The key move is to copy a quiescent
description rather than the live automaton ([[descriptions-vs-originals](pages/descriptions-vs-originals.md)]). Universality has a threshold of
the same kind: above a minimum complexity, a single automaton can do anything any
automaton can do. That same automaton cannot predict arbitrary behavior, which suggests
that complex automata may be simpler than any description of what they do ([[description-vs-object-complexity](pages/description-vs-object-complexity.md)]).

The second central problem is reliability. Von Neumann proposed a
[[probabilistic-logic](pages/probabilistic-logic.md)] in which failure is part of the axioms, bringing the theory closer to analysis
and thermodynamics. It rests on the entropy–information link illustrated by [[maxwells-demon](pages/maxwells-demon.md)]. In practice, natural
automata survive unreliable parts through [[self-repair](pages/self-repair.md)]: they operate across errors instead of
halting on the first one.

## Open Questions

- What exactly is von Neumann's complexity threshold, and does the 29-state construction
  make it precise? Von Neumann guessed millions of parts for the kinematic model.
- How do the kinematic (Part I) and cellular (Part II) models of self-reproduction differ
  in what they assume?

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
