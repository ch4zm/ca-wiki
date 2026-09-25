---
title: Descriptions vs. Originals
category: Concepts
summary: Why self-reproduction copies a passive description rather than the live automaton — descriptions are quiescent and can be read without disturbance, while probing a reactive original is unreliable and risks Richard-type paradoxes
tags: [concept, self-reproduction, description, self-reference, von-neumann]
sources: [tsra-part2-ch1, tsra-lecture-5]
created: 2026-09-24
updated: 2026-09-24
---

# Descriptions vs. Originals

## Description

A self-reproducing automaton needs some way to get the information that specifies itself.
Von Neumann's answer is that it should copy a *description* of itself, and should never
try to copy or inspect its own working body. This is the step that makes
[[self-reproduction](pages/self-reproduction.md)] possible without degeneration.[^1]

**The a priori obstacle.** A constructor seems to need a complete plan of whatever it
builds, so it would have to be more complicated than its product. If the plan is kept on
an attached tape, a self-reproducer would have to contain its own plan. That is
impossible, because a full description of an automaton takes more cells than the automaton
itself.[^2]

**The way out.** A fixed, finite copier B can copy a description φ of *any* size. Copying
is therefore exempt from the rule that the builder must be more complex than what it
builds. The [[universal-constructor](pages/universal-constructor.md)] builds the offspring
from the description, and B separately copies the description and attaches the copy. The
automaton never needs to contain a plan of the plan.[^3]

**Why copy the description rather than the original.** Copying requires *exploration*:
sending stimuli into the object and observing how it responds. A description is made of
quasi-quiescent cells, so probing it does not spread activity or change it. It stays
unchanged while it is read. A live, reactive automaton behaves differently. Stimuli sent in
to examine it spread unpredictably and alter the very states being copied, and copying
presupposes an unchanging original.[^4] In short, descriptions are quiescent, temporarily
unchanging stand-ins for reactive originals, and this is what makes copying, and so
non-degenerating reproduction, possible.[^5]

**Passive vs. active self-description.** The editor names the two options. In the
*passive* method, the automaton carries a description of itself and reads it without
interfering with its own operation. In the *active* method, it examines itself to produce a
description. Von Neumann suggested the active method would probably run into paradoxes of
the Richard type, and adopted the passive one.[^6] The editor relates this to
diagonalization: Richard's paradox and Turing's proof that halting is undecidable share
the same structure. That structure is also behind the fact that no automaton can predict
the behavior of an arbitrary automaton (see
[[universal-turing-machine](pages/universal-turing-machine.md)] and
[[description-vs-object-complexity](pages/description-vs-object-complexity.md)]).[^7] The
editor also notes a parallel with Gödel's undecidable formula, which refers to itself
through its own description.[^6]

**Descriptions as heredity.** Because the description is separate from the body, changes to
it are inherited. A mutation in the part of the description that specifies an extra
payload P yields viable offspring that produce P′ instead. This is a change of hereditary
strain.[^8]

## Appearances in Sources

- [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] — the argument for copying descriptions, and the passive vs. active methods
- [[tsra-lecture-5](pages/tsra-lecture-5.md)] — building from a description rather than copying an object, in the kinematic model

## Related Concepts

- [[construction-arm](pages/construction-arm.md)] — a fixed builder is larger than what it builds
- [[universal-constructor](pages/universal-constructor.md)] — builds from the description
- [[self-reproduction](pages/self-reproduction.md)] — made possible by this separation
- [[description-vs-object-complexity](pages/description-vs-object-complexity.md)] — the related claim about describing complex automata
- [[universal-turing-machine](pages/universal-turing-machine.md)] — the undecidability results behind the passive method
- [[cellular-automaton](pages/cellular-automaton.md)] — the medium in which quiescent descriptions are realized

[^1]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] p.122 [synthesis] — replacing reactive originals with quiescent descriptions is the decisive step that makes self-reproduction, or reproduction without degeneration, possible
[^2]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] p.118 [synthesis] — the a priori argument that the constructor is more complex than what it constructs; a self-reproducer would have to contain its own description, which is larger than the automaton
[^3]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] pp.119, 121 [synthesis] — B explores the description and makes an exact copy; although B is fixed and finite it copies a description of any size, which transcends the rule that the primary must be superior to the secondary
[^4]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] pp.121-122 [synthesis] — exploration by stimulation; quasi-quiescent description cells don't spread the diagnostic stimulation; an active automaton would be disturbed; copying presupposes an unchanging original
[^5]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] p.122 [synthesis] — descriptions are quiescent, temporarily unchanging semantic equivalents of the varying, reactive originals
[^6]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] pp.125-126 [synthesis] — editor: passive and active methods; von Neumann suggests the active method would probably lead to Richard-type paradoxes; parallel with Gödel's self-referential undecidable formula
[^7]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] pp.122-125 [synthesis] — direct copying without a description would likely lead to Richard-type antinomies; editor's exposition of Richard's paradox and the halting problem as parallel diagonal arguments
[^8]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] pp.130-131 [synthesis] — a mutation in the payload part of the description yields a viable, self-reproducing successor producing P′: a change of hereditary strain
