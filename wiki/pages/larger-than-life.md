---
title: Larger than Life
category: Rules
summary: Kellie Evans's 1996 family of range-r outer-totalistic rules in which a cell is born or survives when its neighbour count falls in a single interval; at large range an LtL rule acts like a pair of density thresholds and can be rescaled to any range; hollow "bugs" in Bosco's Rule, slow circular "solid ships"; run by Golly's Larger than Life algorithm, generalized by HROT
tags: [rule-family, larger-than-life, ltl, higher-range, outer-totalistic, bugs, golly, mcell]
sources: [lifewiki-larger-than-life, lifewiki-higher-range-outer-totalistic-rule, lifewiki-rulestring, lifewiki-catagolue, lifewiki-apgsearch, lifewiki-unit-cell, lifewiki-hexagonal-neighbourhood]
created: 2026-09-25
updated: 2026-09-25
---

# Larger than Life

## Description

*Larger than Life* (LtL) is a family of rules defined by Kellie Michele Evans in her 1996
thesis. Each cell looks at an extended neighbourhood of range r, and counts its live
cells.[^1] What sets the family apart is the shape of the rule: a dead cell is born if
the count lies in **one interval** [bmin, bmax], and a live cell survives if it lies in
**one interval** [smin, smax].[^2] Rules that allow any list of counts, not just one
interval, are the broader
[[higher-range-outer-totalistic-rule](pages/higher-range-outer-totalistic-rule.md)]
family (HROT).

**Life is the smallest case.** At range 1 on the Moore neighbourhood, birth on [3, 3] and
survival on [2, 3] is [[game-of-life](pages/game-of-life.md)]; R1,C2,S2-3,B3 is the default
rule of Golly's Larger than Life algorithm.[^3] Life's survival set {2, 3} happens to be an
interval. So Life is Larger than Life at its smallest scale (own reasoning).

**Intervals as densities.** At large range a cell sees hundreds of neighbours, and an
interval of counts says what *fraction* of the neighbourhood must be alive. Evans's
range-conversion rule makes this concrete: to move a rule to another range or
neighbourhood, multiply all four limits by the ratio of neighbourhood sizes and round.[^4]
For example, range 2 to range 7 on the Moore neighbourhood multiplies by 225/25 = 9,
turning S5..9, B7..9 into S45..81, B63..81.[^4] The recipe is built to keep the
fraction of the neighbourhood each limit stands for, so at large range an LtL rule reads
as a statement about local density (own reasoning). David Griffeath's rule Majority,
R4,C2,S40-80,B41-81, is the plainest example.[^5] A range-4 Moore neighbourhood has 80
cells around the centre, so survival needs at least half of them alive and birth needs
more than half: a majority vote (own reasoning from the rule's numbers).

**Notations.** There are several, differing mainly in whether the middle cell counts.[^6]
- **HROT form** (current): Rr,Cc,Ssurvival,Bbirth,Nn, with dashes for runs.
- **MCell form** (Mirek Wójtowicz): Rr,Cc,Mm,Ssmin..smax,Bbmin..bmax,Nn. M1 means the
  middle cell counts toward its own total.
- **Evans's form**: r,bmin,bmax,smin,smax, with the middle cell counted. Life is 1,3,3,3,4:
  a live cell with 2 or 3 live neighbours sees 3 or 4 counting itself.
- **Catagolue/apgsearch form**: letters t ("to") mark intervals, with an optional state
  count.

The middle-cell convention shifts survival limits by one. Bosco's Rule is R5,C2,S33-57,B34-45
in HROT form and R5,C0,M1,S34..58,B34..45,NM in the MCell form Catagolue lists. Only the
survival interval moves (own reasoning from the two strings).[^7]

**States.** With more than two states (Cc, c > 2), cells that fail to survive decay
through the extra states, as in a [[generations-rule](pages/generations-rule.md)]; decaying
cells do not count as live. C0 and C1 mean the same as C2.[^8]

**Patterns.**[^9]
- **Bugs**: hollow travelling patterns, usually spaceships, typified by those of Bosco's
  Rule (range 5, chaotic, by Evans).
- **Solid ships**: extremely slow, circular spaceships.
- **Roomba bugs**: travelling patterns that usually settle into low-period oscillators
  after very long runs, though a few turn out to be true spaceships.

Bosco's Rule has also been shown universal: a Rule 110 unit cell has been built in it
([[rule-110](pages/rule-110.md)]).[^10]

**Where it runs.** Golly (from 3.0) and LifeViewer simulate LtL with range up to 500 and up
to 256 states, on the Moore, von Neumann, circular and other neighbourhoods, including
the [[hexagonal-neighbourhood](pages/hexagonal-neighbourhood.md)].[^11] Golly ships a
folder of example patterns, mostly from MCell.[^5] [[apgsearch](pages/apgsearch.md)] can
soup-search LtL rules up to range 7, and [[catagolue](pages/catagolue.md)] holds results
for Bosco's Rule.[^12]

## Appearances in Sources

- [[lifewiki-larger-than-life](pages/lifewiki-larger-than-life.md)] - the whole article
- [[lifewiki-higher-range-outer-totalistic-rule](pages/lifewiki-higher-range-outer-totalistic-rule.md)] - LtL as the one-interval case of HROT
- [[lifewiki-rulestring](pages/lifewiki-rulestring.md)] - LtL rulestrings
- [[lifewiki-catagolue](pages/lifewiki-catagolue.md)], [[lifewiki-apgsearch](pages/lifewiki-apgsearch.md)] - soup search in LtL
- [[lifewiki-unit-cell](pages/lifewiki-unit-cell.md)] - Bosco's Rule unit cell

## Related Concepts

- [[higher-range-outer-totalistic-rule](pages/higher-range-outer-totalistic-rule.md)] - the generalization to any count lists
- [[life-like-cellular-automaton](pages/life-like-cellular-automaton.md)] - the range-1 two-state case
- [[generations-rule](pages/generations-rule.md)] - the decay mechanism for extra states
- [[moore-neighbourhood](pages/moore-neighbourhood.md)], [[von-neumann-neighbourhood](pages/von-neumann-neighbourhood.md)] - the two neighbourhoods MCell supports
- [[rulestring](pages/rulestring.md)] - how LtL rules are written

[^1]: [[lifewiki-larger-than-life](pages/lifewiki-larger-than-life.md)] L6 - "an algorithm that supports a specific family of higher-range outer-totalistic cellular automata with an extendable neighbourhood, as defined by Kellie Michele Evans in her 1996 thesis"
[^2]: [[lifewiki-larger-than-life](pages/lifewiki-larger-than-life.md)] L40 - "While the former defines only one continuous range of birth and one continuous range of survival conditions, the latter allows for any list of birth and survival conditions to be defined"
[^3]: [[lifewiki-larger-than-life](pages/lifewiki-larger-than-life.md)] L48-51 - "R1,C2,S2-3,B3 B3/S23 Life the default rule for this algorithm in Golly"
[^4]: [[lifewiki-larger-than-life](pages/lifewiki-larger-than-life.md)] L109-124 [synthesis] - compute N as the ratio of neighbour counts, multiply the four limits by N and round; example R2,C2,M1,S5..9,B7..9,NM to range 7: N = 225 / 25 = 9, giving R7,C2,M1,S45..81,B63..81,NM
[^5]: [[lifewiki-larger-than-life](pages/lifewiki-larger-than-life.md)] L43,L56-59 [synthesis] - "The Patterns/Larger-than-Life folder included with Golly contains a number of example patterns (mostly from the MCell collection)"; "R4,C2,S40-80,B41-81 - Majority a stable rule by David Griffeath"
[^6]: [[lifewiki-larger-than-life](pages/lifewiki-larger-than-life.md)] L22-39,L103-107 [synthesis] - MCell notation Rr,Cc,Mm,Ssmin..smax,Bbmin..bmax,Nn with "Mm specifies if the middle cell is included in the neighborhood count"; superseded by HROT notation Rr,Cc,Ssranges,Bbranges,Nn; Evans's notation r,bmin,bmax,smin,smax; the Catagolue/apgsearch/LifeViewer form with t for ranges; "These notations assume an extended Moore neighbourhood in which a live middle cell is included in the neighbourhood count. For example, Life can be entered as 1,3,3,3,4 in Evans' notation"
[^7]: [[lifewiki-larger-than-life](pages/lifewiki-larger-than-life.md)] L60-63 - "R5,C2,S33-57,B34-45 - Bosco's Rule a chaotic rule by Kellie Evans"; [[lifewiki-catagolue](pages/lifewiki-catagolue.md)] L454 - "R5,C0,M1,S34..58,B34..45,NM (Bosco's Rule)"
[^8]: [[lifewiki-larger-than-life](pages/lifewiki-larger-than-life.md)] L41 - "If the number of states (specified after C) is greater than 2, then states 1 and above don't die immediately but gradually decay. Note that state values above 1 are not included in the neighborhood counts ... C0 and C1 are equivalent to C2"
[^9]: [[lifewiki-larger-than-life](pages/lifewiki-larger-than-life.md)] L60-63,L101 [synthesis] - Bosco's Rule, R5, chaotic, by Kellie Evans; "'bugs', which are patterns (usually spaceships, but sometimes oscillators) which are hollow, characterised by those from Bosco's Rule, 'solid ships', which are typically extremely slow circular spaceships ..., and 'roomba bugs', travelling patterns that usually stabilise into low-period oscillators after intense amounts of generations but are infrequently found to be real spaceships"
[^10]: [[lifewiki-unit-cell](pages/lifewiki-unit-cell.md)] L42,L59 [synthesis] - "Selection of Life-like rules with constructed W110 unit cells" includes "Bosco's Rule"
[^11]: [[lifewiki-larger-than-life](pages/lifewiki-larger-than-life.md)] L7,L35-39 [synthesis] - supported by "Golly 3.0 and onwards and LifeViewer build 260 and onwards"; range 1 to 500; C for Circular and other neighbourhoods; [[lifewiki-higher-range-outer-totalistic-rule](pages/lifewiki-higher-range-outer-totalistic-rule.md)] L14 - "Golly supports c from 0 to 256"; [[lifewiki-hexagonal-neighbourhood](pages/lifewiki-hexagonal-neighbourhood.md)] L19 - "LifeViewer and Golly support Larger than Life rules in this neighbourhood"
[^12]: [[lifewiki-apgsearch](pages/lifewiki-apgsearch.md)] L99 - "Larger than Life rules. (up to range 7)"; [[lifewiki-catagolue](pages/lifewiki-catagolue.md)] L454 - "R5,C0,M1,S34..58,B34..45,NM (Bosco's Rule)"
