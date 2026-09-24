---
title: Kinematic Self-Reproduction
category: Concepts
summary: Von Neumann's first model of self-reproduction — an automaton assembling copies of itself from a sea of discrete parts (girders, logic organs, fusing/cutting organs, muscles), abstracted from energy and physics; precursor of the cellular model
tags: [concept, kinematic-model, self-reproduction, von-neumann]
sources: [tsra-lecture-5]
created: 2026-09-24
updated: 2026-09-24
---

# Kinematic Self-Reproduction

## Description

The kinematic model is von Neumann's first setting for
[[self-reproduction](pages/self-reproduction.md)]. An automaton floats in a medium with an
unlimited supply of elementary parts. It picks parts up, identifies them, and joins or
separates them to assemble new automata.[^1] It is called "kinematic" because it deals
with the geometry of movement, contact, positioning, fusing, and cutting, and ignores
forces, energy, and fuel.[^2]

**Choosing the elementary parts.** The choice of parts is a modeling decision with no
rigorous rule. If the parts are too large, they already carry the functions to be
explained, which begs the question. If they are too small, such as molecules, the model
gets lost in chemistry that doesn't bear on how the parts are organized. Von Neumann asks
only what principles organize given parts into working automata.[^3]

**The parts.** The editor reconstructs about eight kinds, all working in discrete time
with a unit delay:[^4]

- **Logic organs:** a stimulus organ (OR), a coincidence organ (AND), an inhibitory organ
  (p and not q), and a stimulus producer. These are in effect
  [[mcculloch-pitts-neuron](pages/mcculloch-pitts-neuron.md)]s.
- **Rigid member:** an insulated girder that forms the frame. Girders also carry
  information, since descriptions are chains of girders with side girders marking 1s.
- **Fusing organ and cutting organ:** weld parts together and separate them.
- **Muscle:** contracts to zero length when stimulated, which moves parts into position.

The constructing automaton holds a description of its target and identifies each part it
touches by testing it. For example, a muscle is recognized because it contracts when
stimulated.[^5] Within this model von Neumann gives the
[[universal-constructor](pages/universal-constructor.md)] scheme for self-reproduction.

**Dimension.** Von Neumann suspected that kinematic self-reproduction would need three
dimensions. The editor notes that the cellular model of Part II needs only two, which
suggests two might be enough for the kinematic model as well.[^6]

**Relation to the cellular model.** The kinematic model leaves open the mechanics of how
parts move, find each other, and connect. Part II of
[[theory-of-self-reproducing-automata](pages/theory-of-self-reproducing-automata.md)]
replaces it with a *cellular* model, a homogeneous grid of finite-state cells, where
construction becomes changing the states of neighboring cells.[^2]

## Appearances in Sources

- [[tsra-lecture-5](pages/tsra-lecture-5.md)] — the model, its parts, and the self-reproducing scheme

## Related Concepts

- [[universal-constructor](pages/universal-constructor.md)] — the self-reproducing scheme built in this model
- [[self-reproduction](pages/self-reproduction.md)] — the problem it addresses
- [[mcculloch-pitts-neuron](pages/mcculloch-pitts-neuron.md)] — its logic organs
- [[complexity-threshold](pages/complexity-threshold.md)] — estimated in terms of these parts

[^1]: [[tsra-lecture-5](pages/tsra-lecture-5.md)] p.75 [synthesis] — an unlimited supply of well-defined elementary parts floating in a container; the automaton picks up parts and puts them together, or takes aggregates apart
[^2]: [[tsra-lecture-5](pages/tsra-lecture-5.md)] p.82 [synthesis] — editor: fuel and energy are ignored; the model deals with the geometrical-kinematic problems of movement, contact, positioning, fusing, and cutting, hence "kinematic model", to be contrasted with the "cellular model" of Part II
[^3]: [[tsra-lecture-5](pages/tsra-lecture-5.md)] pp.76-77 [synthesis] — parts too large beg the question; parts too small bog down in questions of chemistry; the choice rests on common-sense criteria
[^4]: [[tsra-lecture-5](pages/tsra-lecture-5.md)] pp.81-82 [synthesis] — editor's reconstruction from the June 1948 lectures: eight kinds of parts (four logical organs, rigid member, fusing organ, cutting organ, muscle), each taking a unit of time to respond
[^5]: [[tsra-lecture-5](pages/tsra-lecture-5.md)] p.82 [synthesis] — the constructor contains a description, picks up parts, and identifies them by tests, e.g. a muscle contracts when stimulated
[^6]: [[tsra-lecture-5](pages/tsra-lecture-5.md)] p.82 [synthesis] — von Neumann suspected three dimensions (or a Riemann surface) were needed; Part II shows two suffice for the cellular model, strongly suggesting two suffice for the kinematic one
