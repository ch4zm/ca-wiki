---
title: Wang Tiles
category: Concepts
summary: Unit squares with coloured edges that must match their neighbours; the tiling problem (Berger 1966) is undecidable, aperiodic sets exist (smallest known has 13 tiles), and NW-deterministic sets, the finite tiling problem and Kari's SNAKES set carry that undecidability into cellular automata
tags: [concept, wang-tiles, tiling, aperiodic, undecidability, snakes, kari]
sources: [theory-of-cellular-automata-a-survey]
created: 2026-09-24
updated: 2026-09-24
---

# Wang Tiles

## Description

A **Wang tile** is a unit square with a colour on each edge. A tile set T is a finite
collection of them. A tiling puts a copy of some tile at every point of ℤ², without
rotating or reflecting, and it is *valid* when every pair of touching edges has the same
colour. Wang introduced them in 1961.[^1] By compactness, a tile set that can tile
arbitrarily large squares can tile the whole plane.[^1]

**Why they matter for cellular automata.** Kari gives three reasons. Some CA decision
problems can be phrased as tiling problems, so the undecidability of tiling carries over.
Aperiodic tile sets give interesting 2D CA. And the space-time diagram of a 1D CA *is* a
tiling, which gives a way to study 1D dynamics.[^2]

**The tiling problem.** Does a given tile set admit a valid tiling? Berger proved in 1966
that no algorithm decides this. The survey credits the theorem jointly to Berger and to
Robinson (1971).[^3]

**Aperiodic sets.** A tiling is periodic if it is invariant under two non-parallel
translations. A tile set is *aperiodic* if it tiles the plane but never periodically.
Wang saw that without aperiodic sets the tiling problem would be decidable: tile larger
and larger squares until one fails or a period appears. So undecidability implies that
aperiodic sets exist, and Berger's proof contains one. The smallest known set has 13
tiles (Culik; Kari, 1996). Whether one of those 13 is superfluous is open.[^4]

**NW-deterministic sets.** A tile set is *NW-deterministic* if a tile is fixed by the
colours of its north and west edges. Any valid tiling by such a set can then be read as
the space-time diagram of a 1D CA whose states are the tiles, with configurations along
the SW-NE diagonals. Kari proved that the tiling problem stays undecidable for
NW-deterministic sets, and that some of them are aperiodic.[^5] This is what makes
nilpotency undecidable in one dimension ([[limit-set](pages/limit-set.md)]).[^6]

**The finite tiling problem.** Add a blank tile B with all edges the same colour. A
*finite* tiling has only finitely many non-blank tiles. The problem asks whether any valid
finite tiling other than the all-blank one exists. A simple reduction from the halting
problem shows it undecidable, which is much easier than Berger's theorem. The two problems
are undecidable from opposite sides: a finite tiling, if one exists, can be found by
search, while in the general problem it is the *absence* of a tiling that can be
confirmed.[^7]

**SNAKES.** Kari's SNAKES set is aperiodic, and each tile also carries an arrow pointing
to one of its four neighbours. Following the arrows gives a path. The set has a
*plane-filling property*: if the tiling is valid at every tile an infinite path visits,
then the path covers arbitrarily large squares, even if the tiling is invalid elsewhere.
The paths follow the Hilbert curve.[^8] SNAKES drives the proof that 2D injectivity is
undecidable ([[reversible-cellular-automaton](pages/reversible-cellular-automaton.md)]),
and the SNAKE-XOR rule that separates injectivity from injectivity on periodic
configurations ([[garden-of-eden-theorem](pages/garden-of-eden-theorem.md)]). 2D
surjectivity is handled by an analogous reduction from the finite tiling problem.[^9]

## Appearances in Sources

- [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] - §2.8, and the reductions in §§3-5 and 7

## Related Concepts

- [[decidability-in-cellular-automata](pages/decidability-in-cellular-automata.md)] - the CA problems that tiling makes undecidable
- [[limit-set](pages/limit-set.md)] - nilpotency via tiling (2D) and NW-deterministic tiling (1D)
- [[reversible-cellular-automaton](pages/reversible-cellular-automaton.md)] - 2D injectivity via SNAKES
- [[garden-of-eden-theorem](pages/garden-of-eden-theorem.md)] - SNAKE-XOR separates injectivity on periodic configurations from injectivity
- [[conserved-quantity](pages/conserved-quantity.md)] - 2D conserved quantities via the finite tiling problem
- [[jarkko-kari](pages/jarkko-kari.md)] - NW-determinism, SNAKES, the 13-tile set
[^1]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.13 [synthesis] - "Wang tiles were introduced by logician Wang in 1961"; tile, tile set, tiling t : ℤ² → T "without rotating or flipping the tiles"; the four matching conditions; "if a tile set admits valid tilings of arbitrarily large squares then it admits a valid tiling of the entire infinite plane"
[^2]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.13 [synthesis] - CA decision problems formulated as tiling problems; aperiodic tiles give interesting 2D CA; 1D space-time diagrams viewed as tilings
[^3]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.13 - "Theorem 4 (Berger [5] and Robinson [58]). It is undecidable whether a given finite tile set T admits a valid tiling."
[^4]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.13-14 [synthesis] - periodic tilings; aperiodic sets; Wang's observation that without aperiodic sets tiling would be decidable; Corollary 2; Berger's proof contains an aperiodic set; "Currently, the smallest aperiodic set of Wang tiles contains 13 tiles [16,44], and it is an open problem whether one of the tiles in this set is in fact superfluous"
[^5]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.14 [synthesis] - NW-deterministic definition; tilings as space-time diagrams read along SW/NE diagonals; Theorem 5 (Kari)
[^6]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.24 [synthesis] - "To show the undecidability in the one-dimensional case [40] we use NW-deterministic tiles"; valid tilings are valid space-time diagrams read along SW/NE diagonals; contradiction with Theorem 5
[^7]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.14 [synthesis] - the finite tiling problem with blank tile B; undecidable "through a simple reduction from the halting problem of Turing machines"; "much easier to establish than Theorem 4"; semi-algorithm for existence of a finite tiling vs semi-decidability of non-existence in the general problem
[^8]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.14-15 [synthesis] - SNAKES from [41] is aperiodic, tiles carry arrows, paths; plane-filling property: valid along an infinite path P implies P covers arbitrarily large squares; "SNAKES forces the paths to follow the well-known Hilbert-curve"
[^9]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.17, 19-20 [synthesis] - SNAKE-XOR uses the SNAKES tile set; the injectivity proof uses a control layer with T and SNAKES tiles; "The proof concerning the surjectivity is an analogous reduction from the finite tiling problem"
