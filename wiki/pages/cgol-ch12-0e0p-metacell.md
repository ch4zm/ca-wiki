---
title: "The 0E0P Metacell (Johnston and Greene, Ch. 12)"
category: Sources
summary: Chapter 12 of Conway's Game of Life - Mathematics and Construction - Life-like, isotropic and non-isotropic 2D rules and their exotic patterns (replicators, looping oscillators, spaceships made of spaceships, single-cell spaceships), how an 8-state von Neumann rule emulates any 2-state Moore rule, and the self-constructing 0E0P metacell that runs any such rule inside Life, with its predecessors
tags: [source, chapter, life, metacell, 0e0p, rule-emulation, isotropic, non-isotropic, highlife, replicator, rulestring]
sources: [cgol-ch12-0e0p-metacell]
created: 2026-09-25
updated: 2026-09-25
---

# The 0E0P Metacell (Johnston and Greene, Ch. 12)

**Source:** raw/johnston-greene-2022-conways-game-of-life.pdf, Chapter 12, printed pp. 385-430 (PDF pp. 399-444), with Appendix B.6-B.7 on rulestrings (printed pp. 444-448). Part of [[conways-game-of-life-mathematics-and-construction](pages/conways-game-of-life-mathematics-and-construction.md)].
**Date ingested:** 2026-09-25
**Type:** book chapter

## Summary

A *metacell* is a large Life pattern that acts as one cell of some cellular automaton.
Tiled copies then evolve, at a huge scale, like the emulated rule. The 0E0P
[[metacell](pages/metacell.md)] can run any two-state Moore-neighbourhood rule in which an
empty neighbourhood stays empty. That lets exotic patterns from other rules be "imported"
into Life.[^1] The chapter first surveys such rules, in three nested families.[^2]
- [[life-like-cellular-automaton](pages/life-like-cellular-automaton.md)] (outer-totalistic)
  rules such as [[highlife](pages/highlife.md)], whose small
  [[replicator](pages/replicator.md)] copies itself every 12 generations.
- [[isotropic-non-totalistic-rule](pages/isotropic-non-totalistic-rule.md)]s, with looping
  "reflectorless rotating oscillators" and spaceships made of spaceships.
- [[non-isotropic-rule](pages/non-isotropic-rule.md)]s, where a single cell can be a
  lightspeed spaceship or draw a Sierpiński triangle.

It then explains the key trick. The metacell does not emulate a Moore-neighbourhood rule
directly. Instead it runs an 8-state von Neumann-neighbourhood rule in which every cell
dies each generation. That keeps each metacell's diagonal neighbours empty, and it
reproduces any two-state Moore rule at half speed.[^3] The rest of the chapter walks the
metacell's anatomy (shell, kernel, a nucleus loop of about 3.6 million gliders) and its
64-stage lifecycle. In each stage it builds its children by single-channel construction,
passes its state to them, and then self-destructs.[^4] The notes trace earlier metacells:
the p5760 metacell, the OTCA metapixel and the p1 megacell.[^5]

## Key Takeaways

- The 0E0P is 2^18 cells across and runs 2^36 times slower than the rule it emulates.[^1]
- Its "off" state is empty space, so no background grid of dead metacells is needed; it
  builds its own neighbours.[^1][^5]
- There are 2^18 Life-like, 2^102 isotropic and 2^512 two-state Moore-neighbourhood
  rules.[^2]
- Importing patterns this way gave Life its first spaceship made of spaceships and first
  reflectorless rotating oscillator.[^2]

## Entities & Concepts

- [[metacell](pages/metacell.md)], [[life-like-cellular-automaton](pages/life-like-cellular-automaton.md)], [[isotropic-non-totalistic-rule](pages/isotropic-non-totalistic-rule.md)], [[non-isotropic-rule](pages/non-isotropic-rule.md)]
- [[highlife](pages/highlife.md)], [[replicator](pages/replicator.md)], [[elementary-cellular-automaton](pages/elementary-cellular-automaton.md)], [[phoenix](pages/phoenix.md)]

## Relation to Other Wiki Pages

This is where the book leaves B3/S23 for the wider rule space that is this wiki's core
scope. The metacell's construction relies on the universal-construction machinery behind
[[object-synthesis](pages/object-synthesis.md)].[^4]

[^1]: [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] pp.385-386 [synthesis] - "if we arrange copies of it on the Life plane then, at a zoomed-out macroscopic scale, it evolves in the same way that the corresponding arrangement of cells would evolve"; "2^18 = 262 144 times as large ... runs 2^36 = 68 719 476 736 times as slowly"; n.1 "(State) 0 Encoded by 0 Population"; "it can actually emulate a huge variety of 2D cellular automata besides Life ... any pattern from one of those other cellular automata can be straightforwardly 'imported' into Life"
[^2]: [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] §12.1, pp.386-391 [synthesis] - Life-like (outer-totalistic) rules, HighLife replicator; isotropic rules ("2^102 isotropic 2-state CA ... versus 'just' 2^18 outer-totalistic ones"), RRO and SMOS; non-isotropic rules ("2^512 different 2D not necessarily isotropic cellular automata"); "this method gave the first explicit construction of a spaceship made of spaceships in Life ... also gave the first reflectorless rotating oscillator in Life"
[^3]: [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] §12.2, pp.391-393 [synthesis] - the metacell "instead emulates an 8-state von-Neumann-neighborhood CA in which every cell dies in every generation"; the checkerboard pattern "ensures that the 0E0P metacell's four diagonal neighbors are dead"; 8 states "general enough to emulate arbitrary 2-state Moore-neighborhood cellular automata at half speed"
[^4]: [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] §§12.3-12.8, pp.393-421 [synthesis] - shell, kernel, nucleus; single-channel construction; 64 stages of 2^29 generations; construction, state transmission and self-destruction
[^5]: [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] §12.9, pp.422-424 [synthesis] - p5760 metacell (David Bell, 1996), OTCA metapixel (Brice Due, 2005-2006), p1 megacell (Adam P. Goucher, 2008), 0E0P (Goucher, 2014-2018), which "does not require a background grid of 'dead' cells"
