---
title: Billiard Ball Model
category: Concepts
summary: Fredkin and Toffoli's idealized Newtonian model of computation - elastic balls and fixed reflectors with no friction, where collisions compute; hosts reversible gates, a synchronization-free rotary element, and hence whole reversible Turing machines
tags: [concept, reversible-computing, billiard-ball, collision-based-computing, fredkin, toffoli]
sources: [aucm-ch6-reversible-turing-machines-by-rlem]
created: 2026-09-24
updated: 2026-09-24
---

# Billiard Ball Model

## Description

The billiard ball model (BBM), proposed by Fredkin and Toffoli, is an idealized model of
Newtonian mechanics made of balls and reflectors. Collisions are elastic and there is no
friction. Balls compute by colliding with each other and with reflectors, so the BBM is a
form of collision-based computing.[^1] Its standard gate is the *interaction gate*, a
2-input, 4-output reversible gate.[^2]

**Timing.** Building logic out of gates in the BBM needs two or more moving balls to be
exactly synchronized.[^3] Morita's direct realization of a rotary element
([[reversible-logic-element-with-memory](pages/reversible-logic-element-with-memory.md)])
avoids this. A stationary *state ball* sits at one of two positions, H or V, among
reflectors. A signal ball entering parallel to the stored direction passes through
untouched. One entering across it hits the state ball, and after a fixed path both
collide again, leaving the state ball at the other position and sending the signal ball
out the rotated side. The signal ball may arrive at any time and speed; only the interval
between the two collisions must be exact. The state ball could also be replaced by any
suitable reversible physical state, such as a quantum state.[^4]

Every m-state k-symbol element with k ≤ 4 can be realized in the BBM (Mukai and Morita).
Since any [[reversible-turing-machine](pages/reversible-turing-machine.md)] is a circuit
of rotary elements, a whole reversible Turing machine can be realized in the BBM.[^5]

**In cellular automata.** Margolus's 2D block rule simulates billiard balls that move,
collide and bounce off walls, and so supports arbitrary computation
([[margolus-neighbourhood](pages/margolus-neighbourhood.md)]).[^6] (Own reasoning: that
makes the BBM the bridge between reversible logic elements and
[[reversible-cellular-automaton](pages/reversible-cellular-automaton.md)]s.)

## Appearances in Sources

- [[aucm-ch6-reversible-turing-machines-by-rlem](pages/aucm-ch6-reversible-turing-machines-by-rlem.md)] - the model, the interaction gate, the synchronization-free rotary element
- [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] - billiard balls simulated in the Margolus-neighbourhood CA

## Related Concepts

- [[reversible-logic-element-with-memory](pages/reversible-logic-element-with-memory.md)] - realized directly with a stationary state ball
- [[reversible-turing-machine](pages/reversible-turing-machine.md)] - realizable as a whole in the BBM
- [[margolus-neighbourhood](pages/margolus-neighbourhood.md)] - a reversible CA that simulates billiard balls
- [[reversible-cellular-automaton](pages/reversible-cellular-automaton.md)] - reversible dynamics on a lattice

[^1]: [[aucm-ch6-reversible-turing-machines-by-rlem](pages/aucm-ch6-reversible-turing-machines-by-rlem.md)] p.130 — "we use the billiard ball model (BBM) proposed by Fredkin and Toffoli [5] as a reversible physical model. It is an idealized model of Newtonian mechanics consisting of balls and reflectors. Computation can be carried out by balls that collide with other balls or reflectors, and hence it is a kind of collision-based computing (see [1]). It is assumed that collisions are elastic, and there is no friction."
[^2]: [[aucm-ch6-reversible-turing-machines-by-rlem](pages/aucm-ch6-reversible-turing-machines-by-rlem.md)] p.130 (Fig. 6.3) — "Figure 6.3 shows a realization of an interaction gate, which is a 2-input 4-output reversible logic gate, in BBM [5]."
[^3]: [[aucm-ch6-reversible-turing-machines-by-rlem](pages/aucm-ch6-reversible-turing-machines-by-rlem.md)] p.130 — "when we want to implement a logic gate in BBM, exact synchronization of two or more moving balls is necessary."
[^4]: [[aucm-ch6-reversible-turing-machines-by-rlem](pages/aucm-ch6-reversible-turing-machines-by-rlem.md)] pp.130-131 (Fig. 6.4) [synthesis] — one stationary state ball at H or V plus reflectors; state V with input s: the signal ball passes without interaction and exits n′; state H with input s: collisions at positions 1 and 6, the state ball stops at the new position, the signal exits e′; "the signal ball can be given to an input line at any moment and at any speed ... Only the time interval between the first and the second collisions ... should be adjusted exactly"; the state ball may be "a suitable physical state that acts reversibly (such as a quantum state)"
[^5]: [[aucm-ch6-reversible-turing-machines-by-rlem](pages/aucm-ch6-reversible-turing-machines-by-rlem.md)] pp.132, 137 [synthesis] — "Mukai and Morita [17] showed any m-state k-symbol RLEM can be realized in BBM by a systematic method if k ≤ 4"; "the whole system of the RTM can be realized in the space of BBM"
[^6]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.18 [synthesis] - Margolus's rule simulates billiard balls of positive size moving and colliding, walls to bounce off, and arbitrary computation
