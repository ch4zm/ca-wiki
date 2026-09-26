---
title: Hexagonal neighbourhood
category: Concepts
summary: The six cells adjacent to a cell on the hexagonal (honeycomb) tiling, written with an H suffix (B2/S34H); 3n(n+1) cells at range n, plus the ray-shaped asterisk and the chiral three-cell tripod; isotropic hex rules use Paul Callahan's ortho/meta/para letters from chemistry, and the grid brings its own three- and six-fold symmetries
tags: [concept, neighbourhood, hexagonal, honeycomb, symmetry, lattice]
sources: [lifewiki-hexagonal-neighbourhood, lifewiki-higher-range-isotropic-non-totalistic-rule, lifewiki-higher-range-outer-totalistic-rule, lifewiki-apgsearch, lifewiki-rulestring]
created: 2026-09-25
updated: 2026-09-25
---

# Hexagonal neighbourhood

## Description

The *hexagonal neighbourhood*, more exactly the *honeycomb* neighbourhood, is the set of
cells adjacent to a region on the hexagonal tiling. As with the
[[von-neumann-neighbourhood](pages/von-neumann-neighbourhood.md)], the region itself may
or may not count. A single cell has six neighbours.[^1] Rules on it take an **H**
suffix, as in B2/S34H ([[rulestring](pages/rulestring.md)]).[^1]

Six sits between the square grid's two standard counts, four edge neighbours and eight
edge-or-corner neighbours. On a honeycomb every neighbour shares an edge, so the edge
versus corner split of the square grid does not arise (own reasoning).

**Shapes.**[^2]
- **Range n.** Extending outward gives a solid hexagon of 3n(n + 1) cells: 6, 18, 36.
- **Asterisk.** Six rays cast from the centre, the hexagonal counterpart of the cross or
  star neighbourhoods on the square grid.
- **Tripod.** Three of the six neighbours, which is intrinsically chiral. It has only
  half the rotational symmetry of the full neighbourhood, and a cell's tripod neighbours
  do not have it in their own tripods. That one-way relation gives rules on it "rather
  strange mechanics". It too extends by rays.

**Isotropic hex rules.** Paul Callahan's notation adds letters to neighbour counts, as
Hensel notation does on the square grid ([[isotropic-non-totalistic-rule](pages/isotropic-non-totalistic-rule.md)]).
The letters are **o**, **m** and **p**, for ortho, meta and para, borrowed from the
naming of substitution patterns on benzene rings in aromatic chemistry.[^3] The analogy
fits because a benzene ring is also a hexagon of six positions around a centre (own
reasoning). There are only 13 distinct arrangements, against 51 on the Moore
neighbourhood.[^4] With 13 each for birth and survival, that gives 2^26 two-state
isotropic hex rules, against 2^102 on the square grid (own reasoning). Range 2 has
22,668 arrangements.[^4]

**Symmetry.** Because the grid is different, isotropic rules on it have a different set
of pattern symmetries. There are three-fold and six-fold rotations (C3, C6) and
reflection groups up to D12, and the square grid's four-fold symmetries are missing.[^5]
Soup searchers treat these as separate symmetry classes
([[apgsearch](pages/apgsearch.md)], [[catagolue](pages/catagolue.md)]). All except C3_3
and D6_3 can be searched.[^5]

**Software.**[^6]
- Golly runs outer-totalistic hexagonal rules, their Generations variants, and (from
  4.0) hexagonal [[higher-range-outer-totalistic-rule](pages/higher-range-outer-totalistic-rule.md)]s
  including [[larger-than-life](pages/larger-than-life.md)] (code **NH**).
- Golly has no native Callahan notation. Isotropic hex rules there go through rule
  tables ([[ruleloader](pages/ruleloader.md)]) or MAP strings
  ([[non-isotropic-rule](pages/non-isotropic-rule.md)]).
- LifeViewer and lifelib support isotropic hex rules natively; apgsearch and Catagolue
  support hexagonal Generations and isotropic rules.

## Appearances in Sources

- [[lifewiki-hexagonal-neighbourhood](pages/lifewiki-hexagonal-neighbourhood.md)] - the whole article
- [[lifewiki-higher-range-isotropic-non-totalistic-rule](pages/lifewiki-higher-range-isotropic-non-totalistic-rule.md)] - transition counts on the hex grid
- [[lifewiki-higher-range-outer-totalistic-rule](pages/lifewiki-higher-range-outer-totalistic-rule.md)] - NH, NA (asterisk) and N3 (tripod) codes
- [[lifewiki-apgsearch](pages/lifewiki-apgsearch.md)] - hexagonal symmetries in soup search

## Related Concepts

- [[von-neumann-neighbourhood](pages/von-neumann-neighbourhood.md)], [[moore-neighbourhood](pages/moore-neighbourhood.md)] - the square-grid neighbourhoods
- [[isotropic-non-totalistic-rule](pages/isotropic-non-totalistic-rule.md)] - the square-grid counterpart of Callahan's notation
- [[margolus-neighbourhood](pages/margolus-neighbourhood.md)] - another departure from the standard neighbourhoods
- [[rulestring](pages/rulestring.md)] - the H suffix

[^1]: [[lifewiki-hexagonal-neighbourhood](pages/lifewiki-hexagonal-neighbourhood.md)] L7 - "The hexagonal neighbourhood, perhaps more correctly the honeycomb neighbourhood, ... is the set of all cells that are adjacent to the region of interest (neighbourhood) on the hexagonal tiling (the region of interest itself may or may not be considered part of the hexagonal neighbourhood, depending on context) ... These rules are typically notated using the H suffix (e.g. B2/S34H)"
[^2]: [[lifewiki-hexagonal-neighbourhood](pages/lifewiki-hexagonal-neighbourhood.md)] L21,L26,L30 [synthesis] - "the number of cells in a range n hexagonal neighbourhood has the formula 3 n (n + 1)"; the asterisk, "casting six rays outwards from the central cell", "the hexagonal-grid analogue to the cross neighbourhood or star neighbourhood"; the tripod "has an essence of intrinsic chirality; having only half of the rotational symmetry ... as well as cells in one cell's tripod neighbourhood not including the original cell in their tripod neighbourhood imparts rather strange mechanics"
[^3]: [[lifewiki-hexagonal-neighbourhood](pages/lifewiki-hexagonal-neighbourhood.md)] L36 - "a notation devised by Paul Callahan which represent the relative permutations of the cells using the letters o, m, and p ... The three letters stand for ortho, meta, and para respectively and were chosen in analogy to arene substitution patterns in aromatic chemistry"
[^4]: [[lifewiki-higher-range-isotropic-non-totalistic-rule](pages/lifewiki-higher-range-isotropic-non-totalistic-rule.md)] L138-147,L158-167,L308-317 [synthesis] - non-totalistic hexagonal (range 1, 2 states): 13 transitions; isotropic non-totalistic Moore: 51; R2 hexagonal INT: 22668
[^5]: [[lifewiki-hexagonal-neighbourhood](pages/lifewiki-hexagonal-neighbourhood.md)] L55-70 [synthesis] - the hexagonal neighbourhood "features a different set of inherent symmetries": C2, C3, C6, D2, D4, D6, D12 variants; "All of these are currently supported by both lifelib and apgsearch, except for D6_3 and C3_3"; [[lifewiki-apgsearch](pages/lifewiki-apgsearch.md)] L109 - "many of the symmetries of the Moore neighbourhood do not apply to the hexagonal grid, and hexagonal rules must therefore use a separate set of symmetries"
[^6]: [[lifewiki-hexagonal-neighbourhood](pages/lifewiki-hexagonal-neighbourhood.md)] L19,L37,L73-75 [synthesis] - Golly supports outer-totalistic Generations rules on the hexagonal grid; Golly "does not support isotropic non-totalistic hexagonal rules using this syntax, so they must instead be simulated using either rule tables or MAP strings. LifeViewer and lifelib support them natively"; hexagonal HROT including LtL "supported from v4.0 onwards"; apgsearch and Catagolue support hexagonal Generations and isotropic rules; [[lifewiki-higher-range-outer-totalistic-rule](pages/lifewiki-higher-range-outer-totalistic-rule.md)] L29 - "NH for Hexagonal"
