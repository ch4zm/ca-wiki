---
title: Star Trek (B3/S0248)
category: Rules
summary: The Life-like rule B3/S0248 - Life's birth-on-three with survival on 0, 2, 4 or 8 neighbours; stable in character, with spaceships at c/2 through c/6 orthogonally and c/3 through c/5 diagonally; its name pairs it with the Generations rule Star Wars, to which it is not mathematically related
tags: [rule, life-like, star-trek, b3-s0248, stable, spaceships]
sources: [eppstein-2010-growth-and-decay-in-life-like-ca, lifewiki-star-trek, lifewiki-star-wars]
created: 2026-09-25
updated: 2026-09-26
---

# Star Trek (B3/S0248)

## Description

**The rule.** Star Trek is the
[[life-like-cellular-automaton](pages/life-like-cellular-automaton.md)] **B3/S0248** (S/B
form **0248/3**, rule integer 141832). A dead cell is born with exactly 3 live
neighbours, as in [[game-of-life](pages/game-of-life.md)]; a live cell survives with 0, 2,
4 or 8. LifeWiki classes its character as stable. Its black/white reversal is
B12357/S01234678.[^1]

**Survival on zero.** S0 means an isolated live cell survives. A lone cell's neighbours
each see only one live cell, so nothing is born: a single cell is a [[still-life](pages/still-life.md)] (own
reasoning, from the rule).

**Spaceships.** Despite the stable character, it supports a spread of speeds.[^2]
- Orthogonal: c/2, c/3, c/4, c/5 (found by Rocknlol) and c/6.
- Diagonal: c/3d and c/5d (both found by LaundryPizza03) and c/4d.

Any one of these spaceships makes Star Trek fertile in Eppstein's sense, a finite pattern
that escapes every bounding box ([[fertile-and-mortal-rules](pages/fertile-and-mortal-rules.md)]; own
reasoning, applying the definition).[^3]

**Star Trek and Star Wars.** The names are a pair. LifeWiki's Star Wars page points to
Star Trek as "the outer-totalistic rule", and Star Trek's page points back to
[[star-wars-rule](pages/star-wars-rule.md)] as "the Generations rule".[^4] The rules
themselves share nothing: Star Wars is B2/S345/C4, with birth on two, survival on 3-5 and
two dying states, while Star Trek has birth on three, survival on 0, 2, 4, 8 and no dying
states (own reasoning, comparing the rulestrings). The link is in the names, a wink between
two space-opera franchises; the mathematics goes separate ways.

## Appearances in Sources

- [[lifewiki-star-trek](pages/lifewiki-star-trek.md)] - the rule and its spaceships
- [[lifewiki-star-wars](pages/lifewiki-star-wars.md)] - disambiguation note naming Star Trek

## Related Concepts

- [[star-wars-rule](pages/star-wars-rule.md)] - its namesake counterpart
- [[life-like-cellular-automaton](pages/life-like-cellular-automaton.md)] - its family
- [[game-of-life](pages/game-of-life.md)] - shares the birth condition B3
- [[spaceship](pages/spaceship.md)] - its best-documented objects
- [[fertile-and-mortal-rules](pages/fertile-and-mortal-rules.md)] - its spaceships make it fertile

[^1]: [[lifewiki-star-trek](pages/lifewiki-star-trek.md)] L8-16,L19 - rulestrings "0248/3", "B3/S0248"; rule integer 141832; character "Stable"; black/white reversal "B12357/S01234678"; "Star Trek is a Life-like cellular automaton with rulestring B3/S0248. Dead cells are born if they have 3 neighbours and alive cells survive if they have no, 2, 4 or 8 neighbours."
[^2]: [[lifewiki-star-trek](pages/lifewiki-star-trek.md)] L27-53 [synthesis] - spaceship gallery: orthogonal c/2, c/3, c/4, "c/5, found by Rocknlol in 2020", c/6; diagonal "c/3d, found by LaundryPizza03 in 2020", c/4d, "c/5d, found by LaundryPizza03 in 2021"
[^3]: [[eppstein-2010-growth-and-decay-in-life-like-ca](pages/eppstein-2010-growth-and-decay-in-life-like-ca.md)] p.7 - "We define a cellular automaton rule to be fertile if it has a finite pattern that eventually escapes any of its bounding boxes"
[^4]: [[lifewiki-star-wars](pages/lifewiki-star-wars.md)] L16 - "This article is about the Generations rule. For the outer-totalistic rule, see OCA:Star Trek."; [[lifewiki-star-trek](pages/lifewiki-star-trek.md)] L17 - "This article is about the outer-totalistic rule. For the Generations rule, see OCA:Star Wars."
