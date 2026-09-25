---
title: Kinematic Self-Reproduction
category: Concepts
summary: Von Neumann's first model of self-reproduction — an automaton assembling copies of itself from a sea of discrete parts (girders, logic organs, fusing/cutting organs, muscles), abstracted from energy and physics; precursor of the cellular model
tags: [concept, kinematic-model, self-reproduction, von-neumann]
sources: [tsra-lecture-5, tsra-part2-ch1, machine-models-of-self-reproduction]
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
replaces it with a *cellular* model ([[cellular-automaton](pages/cellular-automaton.md)]), a homogeneous grid of finite-state cells, where
construction becomes changing the states of neighboring cells.[^2] Von Neumann gets there by
removing motion, making the medium discrete and homogeneous, and treating growth as the
conversion of unexcitable cells into excitable ones.[^7]

**Built kinematic models.** By 1962 several kinematic self-reproducers had actually been
built. Jacobson used a model railroad: the machine is a train of different kinds of cars,
with relay logic aboard and sidetracks for rearranging parts. Penrose's basic model uses two
kinds of rigid units, A and B, cut with hooks and interlocks. Shaken in a box with loose
units, an AB machine makes more AB machines and a BA machine more BA machines, by mechanical
force, friction, and gravity alone. Without a seed nothing forms, except under unusually
violent shaking.[^8] Moore built a copy of Penrose's model and used it in talks. He stresses
that A and B are not male and female: one AB machine is an individual, and the units
correspond to the molecules of a single chromosome, so reproduction is asexual.[^9] Morowitz
proposed a model of electromagnets and electrets floating in a liquid, which was not
built.[^10] Moore's open problems include measuring how trivial such a model is and making
reproduction run in parallel.[^11]

## Appearances in Sources

- [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] — Jacobson's, Penrose's, and Morowitz's models
- [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] — why and how the kinematic model is replaced by the cellular one
- [[tsra-lecture-5](pages/tsra-lecture-5.md)] — the model, its parts, and the self-reproducing scheme

## Related Concepts

- [[cellular-automaton](pages/cellular-automaton.md)] — the model that replaced it
- [[universal-constructor](pages/universal-constructor.md)] — the self-reproducing scheme built in this model
- [[self-reproduction](pages/self-reproduction.md)] — the problem it addresses
- [[mcculloch-pitts-neuron](pages/mcculloch-pitts-neuron.md)] — its logic organs
- [[complexity-threshold](pages/complexity-threshold.md)] — estimated in terms of these parts
- [[edward-f-moore](pages/edward-f-moore.md)] - built a copy of Penrose's model
- [[john-myhill](pages/john-myhill.md)] - a model between the kinematic and tessellation models

[^1]: [[tsra-lecture-5](pages/tsra-lecture-5.md)] p.75 [synthesis] — an unlimited supply of well-defined elementary parts floating in a container; the automaton picks up parts and puts them together, or takes aggregates apart
[^2]: [[tsra-lecture-5](pages/tsra-lecture-5.md)] p.82 [synthesis] — editor: fuel and energy are ignored; the model deals with the geometrical-kinematic problems of movement, contact, positioning, fusing, and cutting, hence "kinematic model", to be contrasted with the "cellular model" of Part II
[^3]: [[tsra-lecture-5](pages/tsra-lecture-5.md)] pp.76-77 [synthesis] — parts too large beg the question; parts too small bog down in questions of chemistry; the choice rests on common-sense criteria
[^4]: [[tsra-lecture-5](pages/tsra-lecture-5.md)] pp.81-82 [synthesis] — editor's reconstruction from the June 1948 lectures: eight kinds of parts (four logical organs, rigid member, fusing organ, cutting organ, muscle), each taking a unit of time to respond
[^5]: [[tsra-lecture-5](pages/tsra-lecture-5.md)] p.82 [synthesis] — the constructor contains a description, picks up parts, and identifies them by tests, e.g. a muscle contracts when stimulated
[^6]: [[tsra-lecture-5](pages/tsra-lecture-5.md)] p.82 [synthesis] — von Neumann suspected three dimensions (or a Riemann surface) were needed; Part II shows two suffice for the cellular model, strongly suggesting two suffice for the kinematic one
[^7]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] pp.102-103, 109 [synthesis] — avoiding geometry and kinematics: stationary quiescent/active cells, discrete homogeneous medium, growth as transformation of unexcitable into excitable cells
[^8]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] pp.18-19 [synthesis] - Jacobson's model railroad layout and cars with relay circuits; Penrose's basic model of A and B units that build more AB or BA machines when shaken; no "spontaneous generation" without a seed except by shaking with unusual force
[^9]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] p.19 [synthesis] - Moore built an exact copy of Penrose's basic model; the units are not male and female; an AB or BA machine is an individual, the units are molecules of one chromosome, the reproduction asexual
[^10]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] p.20 [synthesis] - Morowitz's proposed model of electromagnets and electrets floating in a liquid, apparently not designed in detail or built
[^11]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] pp.29-30 [synthesis] - making "more general or less trivial" precise; parallel rather than serial reproduction in the machines of Penrose, von Neumann, and Jacobson
