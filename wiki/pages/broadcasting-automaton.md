---
title: Broadcasting Automaton
category: Concepts
summary: A network of finite machines placed in a metric space (usually the square lattice) where each machine's state sets a transmission radius and a message reaches everyone within that distance - a dynamic-topology cousin of cellular automata that computes with waves
tags: [concept, broadcasting-automata, networks-of-automata, ad-hoc-networks, waves, nickson, potapov]
sources: [aucm-ch14-broadcasting-automata]
created: 2026-09-24
updated: 2026-09-24
---

# Broadcasting Automaton

## Description

**Definition.** A broadcasting automaton A = (Q, Σ, Λ, δ, Δ, τ, q₀, F) is a Moore machine
extended with a set of final states F and a radius function τ: Q → ℝ. The output alphabet
Λ also gains an empty symbol ε. A *broadcasting automata model* BA = ((M, d), A, C₀) places
a copy of A at every point of a metric space (M, d), with initial configuration
C₀: M → Q.[^1] At each synchronous step, the automaton at u receives the set
Γ_u = {Δ(c(v)) | d(u, v) ≤ τ(c(v))} of messages from all automata whose current radius
reaches it, and moves to δ(Γ_u). The messages form a set, so how many copies of each
arrived is lost.[^2] The model is inspired by ad-hoc radio networks. Because radii depend
on states, the connectivity graph can change at every step. A network of finite automata,
by contrast, has a fixed graph.[^3] Transmission is assumed to be error-free.[^4]

**Timing.** In the synchronous version, an automaton that is activated at time t sends at
t + 1 and ignores input at t + 2, so the wave moves only outward. In the asynchronous
version the relayed symbol advances mod |Σ| at each hop. The two versions can simulate
each other, trading alphabet size against time.[^5]

**The lattice case.** On ℤ² with Euclidean distance, one broadcast of radius r reaches a
*discrete disc*. Radius 1 gives the von Neumann neighbourhood and radius √2 the
[[moore-neighbourhood](pages/moore-neighbourhood.md)]. Repeated broadcasts give waves
whose shapes are studied as broadcasting sequences
([[neighbourhood-sequence](pages/neighbourhood-sequence.md)]).[^6]

**Relation to cellular automata.** A [[cellular-automaton](pages/cellular-automaton.md)]
extended to allow variable neighbourhoods can simulate a broadcasting automaton. Each
transmitter's state spreads to the cells whose neighbourhood contains it. The authors
claim only BA ⊆ CA, not an exact translation in the other direction.[^7] (Own reasoning:
the difference from an ordinary CA is that the neighbourhood of a cell is chosen by its
neighbours' states, much as the links of a
[[cellular-automaton-with-write-access](pages/cellular-automaton-with-write-access.md)] are
chosen by the cell itself.)

**Uses.** Standing-wave patterns partition robot swarms and locate the centre of a
digital disc. Aggregating two wave trains produces non-convex patterns
([[aucm-ch14-broadcasting-automata](pages/aucm-ch14-broadcasting-automata.md)]).[^8]

## Appearances in Sources

- [[aucm-ch14-broadcasting-automata](pages/aucm-ch14-broadcasting-automata.md)] - definition, timing variants, relation to CA, wave geometry

## Related Concepts

- [[neighbourhood-sequence](pages/neighbourhood-sequence.md)] - the shapes of its waves
- [[cellular-automaton](pages/cellular-automaton.md)] - simulates it once neighbourhoods may vary
- [[moore-neighbourhood](pages/moore-neighbourhood.md)] - the radius-√2 broadcast
- [[cellular-automaton-with-write-access](pages/cellular-automaton-with-write-access.md)] - another CA variant with dynamic links

[^1]: [[aucm-ch14-broadcasting-automata](pages/aucm-ch14-broadcasting-automata.md)] pp.300-301 [synthesis] — Definition 1 (Moore machine); Definition 4: the Broadcasting Automaton extends the Moore machine with final states F and τ: Q → ℝ, "the radius of transmission for the output symbol", with ε added to Λ; Definition 5: BA = ((M, d), A, C₀)
[^2]: [[aucm-ch14-broadcasting-automata](pages/aucm-ch14-broadcasting-automata.md)] pp.301-302 [synthesis] — "If several messages are transmitted to an automaton, A, it will receive only a set of unique messages"; Definition 7: Γ_u = {Δ(c(v)) | v ∈ M ∧ d(u, v) ≤ τ(c(v))}; the new state is δ_u(Γ_u); Definition 8: the global transition function
[^3]: [[aucm-ch14-broadcasting-automata](pages/aucm-ch14-broadcasting-automata.md)] pp.300-301 [synthesis] — Definition 2: a network of finite automata (G, A, C₀) has a fixed topology; Broadcasting Automata as "a network of finite automata with a dynamic network topology" inspired by ad hoc wireless networks; "the topology, or connectivity graph ... is able to change at each time step"
[^4]: [[aucm-ch14-broadcasting-automata](pages/aucm-ch14-broadcasting-automata.md)] pp.304-305 — "It is assumed that there will be no error in transmission, the receipt or sending of messages across the network is guaranteed"
[^5]: [[aucm-ch14-broadcasting-automata](pages/aucm-ch14-broadcasting-automata.md)] pp.305-306 [synthesis] — synchronous model: receive at t, send at t + 1, ignore at t + 2; asynchronous: broadcast σ_{(i+1) mod |Σ|}; minimal alphabet favours the synchronous model at a cost in time; Proposition 1: each simulates the other
[^6]: [[aucm-ch14-broadcasting-automata](pages/aucm-ch14-broadcasting-automata.md)] pp.306-309 [synthesis] — M = ℤ × ℤ with the Euclidean distance; radius 1 reaches four neighbours, √2 all eight, "identical to the well studied neighbourhoods von Neumann and Moore"; broadcast of radius r reaches a discrete disc; broadcasting sequences
[^7]: [[aucm-ch14-broadcasting-automata](pages/aucm-ch14-broadcasting-automata.md)] p.306 [synthesis] — variable-radius CA simulate Broadcasting Automata by giving transmitters unique states that spread to cells having them in their neighbourhood; "it is only possible to say that BA ⊆ CA"
[^8]: [[aucm-ch14-broadcasting-automata](pages/aucm-ch14-broadcasting-automata.md)] pp.298-299, 326-328 [synthesis] — standing waves partition a cluster of robots; finding the centre of a digital disk; moiré and anti-moiré aggregation generates non-convex polygons
