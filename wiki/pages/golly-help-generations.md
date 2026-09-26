---
title: "Golly Help: Generations"
category: Sources
summary: Golly's documentation for its Generations algorithm - the survival/birth/states rule notation (e.g. 345/2/4 for Star Wars), example rules with authors, von Neumann and hexagonal variants, Hensel-notation non-totalistic Generations rules, and MAP rules with 2-256 states
tags: [source, golly, documentation, generations, rulestring, simulator]
sources: [golly-help-generations]
created: 2026-09-25
updated: 2026-09-25
---

# Golly Help: Generations

**Source:** raw/golly-help-generations.md, a text copy of https://golly.sourceforge.io/Help/Algorithms/Generations.html (fetched 2026-09-25; two image tables omitted).
**Date ingested:** 2026-09-25
**Type:** software documentation

## Summary

Golly's Generations algorithm runs Life-like rules with an extra "history" component,
allowing up to 256 cell states.[^1] Rules are written survival/birth/states, for example
"345/2/4". Survival digits come first, then birth digits, then the number of states n, from
2 to 256. This is the older S/B ordering, the reverse of B/S rulestrings.[^1] The page
lists example rules with their authors and points to Mirek Wójtowicz's MCell site for
more.[^2]
- Brian's Brain (/2/3, Brian Silverman), Star Wars (345/2/4, Mirek Wójtowicz)
- Banners, Caterpillars and Lava (Wójtowicz)
- Cooties and Sticks (Rudy Rucker)
- Bloomerang, Fireworks, Transers and Xtasy (John Elliott)
- Frogs (Scott Robert Ladd) and Lines (Anders Starmark)

The same notation extends to other neighbourhoods and rule families.[^3]
- Append "V" for the four-cell von Neumann neighbourhood, or "H" for a hexagonal one
  emulated on the square grid by ignoring the NE and SW corners.
- Hensel's letters give non-totalistic Generations rules.
- "MAP" strings give fully general ones. With 255 choices of state count, that makes
  255 × 2^512 rules.

## Key Takeaways

- Golly, the standard simulator, supports Generations rules up to 256 states.[^1]
- Rule notation in Golly is survival first: 345/2/4 is B2/S345/C4.[^1]
- Golly calls count-based rules "totalistic", in the looser sense that also covers
  outer-totalistic rules.[^4]

## Entities & Concepts

- [[generations-rule](pages/generations-rule.md)], [[star-wars-rule](pages/star-wars-rule.md)], [[brians-brain](pages/brians-brain.md)]
- [[isotropic-non-totalistic-rule](pages/isotropic-non-totalistic-rule.md)], [[non-isotropic-rule](pages/non-isotropic-rule.md)], [[life-like-cellular-automaton](pages/life-like-cellular-automaton.md)]

## Relation to Other Wiki Pages

Johnston and Greene's Hensel and MAP notations ([[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)])
are the two-state case of the notations here.

[^1]: [[golly-help-generations](pages/golly-help-generations.md)] L5 - "The Generations algorithm supports rules similar to Life but with an extra history component that allows cells to have up to 256 states. The rule notation is '0..8/1..8/n' where the 1st set of digits specify the live neighbor counts necessary for a cell to survive to the next generation. The 2nd set of digits specify the live neighbor counts necessary for a cell to be born in the next generation. The final number n specifies the maximum number of cell states (from 2 to 256)"
[^2]: [[golly-help-generations](pages/golly-help-generations.md)] L9-23 [synthesis] - example rules with names and authors; "Other rules in this family, along with more detailed descriptions, can be found at Mirek Wojtowicz's MCell website"
[^3]: [[golly-help-generations](pages/golly-help-generations.md)] L27,L39,L43-45,L69-75 [synthesis] - append "V" for von Neumann with counts 0 to 4; append "H" for hexagonal by ignoring the NE and SW corners; non-totalistic rules "based on a notation developed by Alan Hensel"; MAP rules "rule = MAP<base64_string>/<states>"; "255*2^512 (roughly 3.42x10^156) unique rules"
[^4]: [[golly-help-generations](pages/golly-help-generations.md)] L43 - "All of the above rules are classified as 'totalistic' because the outcome depends only on the total number of neighbors"
