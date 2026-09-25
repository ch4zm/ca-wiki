---
title: Overview
tags: [overview, synthesis]
sources: [theory-of-self-reproducing-automata, tsra-editors-introduction, tsra-lecture-2, tsra-lecture-3, tsra-lecture-4, tsra-lecture-5, tsra-part2-ch1, tsra-part2-ch2, tsra-part2-ch3, tsra-part2-ch4, tsra-part2-ch5, statistical-mechanics-of-cellular-automata]
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

**Reliability.** Von Neumann proposed a [[probabilistic-logic](pages/probabilistic-logic.md)] in which failure is part
of the axioms, bringing the theory closer to analysis and thermodynamics, via the
entropy–information link illustrated by [[maxwells-demon](pages/maxwells-demon.md)]. Natural automata survive
unreliable parts through [[self-repair](pages/self-repair.md)]: they operate across errors instead of halting
on the first one.

**The statistical turn.** Wolfram (1983) reverses von Neumann's approach. Instead of
designing one huge rule for a purpose, he surveys every rule in the smallest family, the
[[elementary-cellular-automaton](pages/elementary-cellular-automaton.md)], and asks what
the rules do statistically, as models of [[self-organization](pages/self-organization.md)].
The rules split into simple and complex. From a single seed, complex rules grow
self-similar patterns ([[fractal-dimension](pages/fractal-dimension.md)] log₂3 ≈ 1.59,
with [[rule-90](pages/rule-90.md)] the canonical case). From random noise they reach
equilibria whose densities and structure spectra do not depend on the start. These fall
into two universality classes: the
[[additive-cellular-automaton](pages/additive-cellular-automaton.md)] rules, which are
exactly solvable, and all the others. The mechanism is
[[irreversibility-and-entropy](pages/irreversibility-and-entropy.md)]. Trajectories
merge, entropy falls, and [[garden-of-eden](pages/garden-of-eden.md)] configurations
become the typical case. Von Neumann's expectation that a theory of automata would
resemble thermodynamics becomes something measurable. The
[[game-of-life](pages/game-of-life.md)] enters as a universal two-state rule built from
glider-stream circuits.

## Open Questions

- Why exactly two universality classes? Wolfram conjectures it is because rules simulate each
  other under short encodings. Is that the whole story?
- Wolfram judged elementary rules too simple for universal computation. Rule 110 is outside
  his 32 legal rules, and Cook (2004), on the reading list, is the test of this claim.
- What exactly is von Neumann's complexity threshold, and does the 29-state construction
  make it precise? Von Neumann guessed millions of parts for the kinematic model.
- How do the kinematic (Part I) and cellular (Part II) models of self-reproduction differ
  in what they assume?
- Von Neumann's design is serial and ignores the medium's parallelism. How much smaller could
  a parallel self-reproducer be?
- Which cellular structures have Garden-of-Eden configurations? (Moore and Myhill are next.)

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
- [[elementary-cellular-automaton](pages/elementary-cellular-automaton.md)]
- [[additive-cellular-automaton](pages/additive-cellular-automaton.md)]
- [[rule-90](pages/rule-90.md)]
- [[fractal-dimension](pages/fractal-dimension.md)]
- [[self-organization](pages/self-organization.md)]
- [[irreversibility-and-entropy](pages/irreversibility-and-entropy.md)]
- [[game-of-life](pages/game-of-life.md)]
