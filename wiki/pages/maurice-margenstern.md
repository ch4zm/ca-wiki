---
title: Maurice Margenstern
category: People
summary: French computer scientist (b. 1947, University of Lorraine at Metz) who made the frontier between decidable and universal small Turing machines a central theme of computability, founded the Machines, Computations and Universality conference, and developed cellular automata in hyperbolic space
tags: [person, margenstern, small-universal-machines, hyperbolic-cellular-automata, computability]
sources: [automata-universality-computation, aucm-ch5-small-universal-turing-machines]
created: 2026-09-24
updated: 2026-09-24
---

# Maurice Margenstern

## Description

Margenstern was born in Paris on 6 June 1947. He started out in constructive mathematics,
studying in Leningrad with N. A. Shanin. His interests then moved to computability. In the
late 1980s he joined the LITP computer-science laboratory in Paris, and there he began
studying the simplest machines with an undecidable halting problem and the most complex
ones with a decidable one. His 1994 habilitation was on that frontier. He then became a
professor at the University of Lorraine at Metz, where he founded the LITA laboratory. He
is now emeritus there.[^1] The volume's preface credits him with putting small machines
forward as one of the important themes in computability. He did it through his own results
and through the conference series *Machines, Computations and Universality*, which he set
up in 1995.[^2]

**Small universal Turing machines.** Margenstern built small universal programs for
several Turing-machine models, together with lower bounds on universal program size. He
also built machines that iterate the [[collatz-function](pages/collatz-function.md)] inside
the open gap between the two. He found exact frontiers for the colours and the laterality
of 2-symbol machines, some of them with Pavlotskaya. And he designed 2-tag simulations
([[tag-system](pages/tag-system.md)]) that need only 6 or 3 left-move instructions
([[universal-turing-machine](pages/universal-turing-machine.md)]).[^3]

**Hyperbolic cellular automata.** In the early 2000s he developed computation with
cellular automata in the hyperbolic plane and in hyperbolic spaces of dimension 3 and 4,
and solved long-open tiling problems. The usual tool in hyperbolic geometry is group
theory, but he invented combinatorial tools instead. The preface also says he proved that
hyperbolic computation gets around some infeasibility results that hold in the Euclidean
setting.[^4]

## Appearances in Sources

- [[automata-universality-computation](pages/automata-universality-computation.md)] - the tribute volume; Grigorieff's biographical preface
- [[aucm-ch5-small-universal-turing-machines](pages/aucm-ch5-small-universal-turing-machines.md)] - Neary and Woods' survey of his small-machine work

## Related Concepts

- [[universal-turing-machine](pages/universal-turing-machine.md)] - his frontier results on small universal machines
- [[tag-system](pages/tag-system.md)] - his left-move-sparing simulation algorithms
- [[collatz-function](pages/collatz-function.md)] - his Collatz-iterating machines

[^1]: [[automata-universality-computation](pages/automata-universality-computation.md)] pp.V-VI (Preface) [synthesis] — "Maurice was born in Paris on June 6, 1947"; constructive mathematics in Leningrad with Nicolaï A. Shanin; "In the late 80's he joined the computer science laboratory LITP (now LIAFA) in Paris and started his amazing investigation of the simplest (resp. most complex) machines with an undecidable (resp. decidable) halting problem"; Habilitation 1994; professor at the university of Lorraine at Metz, created the LITA laboratory; "now emeritus professor at the university of Lorraine"
[^2]: [[automata-universality-computation](pages/automata-universality-computation.md)] pp.V-VI (Preface) — "Maurice is to be credited for putting it up as one of the important themes in computability. He did so via his own contributions and via a triennial international conference Machines, Computations and Universality he set up in 1995"
[^3]: [[aucm-ch5-small-universal-turing-machines](pages/aucm-ch5-small-universal-turing-machines.md)] pp.117-124 [synthesis] — small universal programs and lower bounds; Collatz machines (11, 2), (5, 3), (4, 4), (3, 6), (2, 10); colour and laterality frontiers, partly with Pavlotskaya; 59-state/6-left-move, 190-state/3-left-move and 218-state non-erasing/3-left-move machines
[^4]: [[automata-universality-computation](pages/automata-universality-computation.md)] p.VI (Preface) — "In the early 2000's Maurice developed the subject of computation with cellular automata in the hyperbolic world (dimension 2, 3 or 4) and brought solutions to long open difficult tiling problems. Besides these technical achievements, Maurice proved that hyperbolic computability allows to overcome known unfeasibility results of the Euclidean world. The classical tool in hyperbolic geometry is the theory of groups but Maurice invented completely new tools: combinatorial ones."
