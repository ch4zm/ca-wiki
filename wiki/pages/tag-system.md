---
title: Tag System
category: Concepts
summary: Post's string-rewriting model - repeatedly delete the first β symbols of a word and append the production of the first one; 2-tag systems are universal (Cocke and Minsky) and are a common intermediate model for building small universal Turing machines
tags: [concept, tag-system, post, universality, turing-machines]
sources: [aucm-ch5-small-universal-turing-machines]
created: 2026-09-24
updated: 2026-09-24
---

# Tag System

## Description

A tag system, introduced by Post, has a finite alphabet Σ = {σ₁, …, σₗ}, one production
σ → P(σ) for each symbol (P(σ) a word over Σ), and a deletion number β ≥ 1. It acts on a
*dataword* w, which is the whole configuration. In a step, the first β symbols are deleted
and the production of the first symbol is appended at the right end. A **2-tag system**
has β = 2:[^1]

σᵢ₁ σᵢ₂ σᵢ₃ … σᵢₙ ⊢ σᵢ₃ … σᵢₙ P(σᵢ₁)

**Universality.** Cocke and Minsky showed that 2-tag systems are universal.[^2] That makes
them a convenient target for small universal Turing machines
([[universal-turing-machine](pages/universal-turing-machine.md)]). Such a machine only has
to simulate a tag step, not an arbitrary Turing machine. Minsky's 7-state, 4-symbol
machine takes this route, and its simulation algorithm inspired many of the small
universal machines that followed.[^3] Tag systems also sit next to Turing machines and
[[rule-110](pages/rule-110.md)] as standard intermediate models for proving other systems
universal.[^4]

**Simulating a step.** In Minsky's layout the productions sit on the left of the tape and
the dataword on the right, with σᵢ written in unary as eⁱd. The unary count of the first
symbol indexes its production, which is then copied to the right end. Each step needs
several left scans that must not destroy what they pass over. Margenstern redesigned the
algorithm so that 2-symbol machines need only 6, or even 3, left-move instructions
([[aucm-ch5-small-universal-turing-machines](pages/aucm-ch5-small-universal-turing-machines.md)]).[^5]

## Appearances in Sources

- [[aucm-ch5-small-universal-turing-machines](pages/aucm-ch5-small-universal-turing-machines.md)] - definition; Minsky's and Margenstern's simulation algorithms

## Related Concepts

- [[universal-turing-machine](pages/universal-turing-machine.md)] - many small universal machines are 2-tag simulators
- [[collatz-function](pages/collatz-function.md)] - another iterated map run on small Turing machines
- [[rule-110](pages/rule-110.md)] - another standard stepping stone for universality proofs

[^1]: [[aucm-ch5-small-universal-turing-machines](pages/aucm-ch5-small-universal-turing-machines.md)] p.121 (Definition 1) [synthesis] — "A tag system consists of a finite alphabet of symbols Σ = {σ1, σ2, . . . σl}, a finite set of rules of the form σ → P(σ) with P(σ) ∈ Σ∗, and a deletion number β ∈ N, β ⩾ 1. For a 2-tag system, β = 2."; a computation step deletes the first two symbols and appends P(σi1)
[^2]: [[aucm-ch5-small-universal-turing-machines](pages/aucm-ch5-small-universal-turing-machines.md)] p.121 — "Tag systems where introduced by Post [36], and 2-tag systems were shown to be universal by Cocke and Minsky [3]."
[^3]: [[aucm-ch5-small-universal-turing-machines](pages/aucm-ch5-small-universal-turing-machines.md)] p.121 — "Minsky [28] constructed a 7-state, 4-symbol universal Turing machine that simulates 2-tag systems and his machine's simulation algorithm was the inspiration for many of the small universal machines to follow"
[^4]: [[aucm-ch5-small-universal-turing-machines](pages/aucm-ch5-small-universal-turing-machines.md)] pp.117-118 — "Simulation of small universal Turing machines and other simple universal models such as Post's tag systems [36] and the cellular automaton rule 110 [4] is by now a standard way to prove that a large number of other models of computation ... are computationally universal."
[^5]: [[aucm-ch5-small-universal-turing-machines](pages/aucm-ch5-small-universal-turing-machines.md)] pp.122-124 [synthesis] — Fig. 5.2 (Minsky: productions left, dataword right, σi as e^i d, three stages); leftward scans must not destroy information; Margenstern's 59-state machine with 6 left-move instructions and 190-state machine with 3
