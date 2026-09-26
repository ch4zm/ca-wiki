---
title: Life-like cellular automaton
category: Rules
summary: The family of 2^18 = 262,144 two-state rules on the square grid's eight-cell neighbourhood whose next state depends only on the number of live neighbours, written as B/S rulestrings (Life is B3/S23); a rule's lowest birth count largely fixes its character, so chaotic rules live only at B3 or B0; each rule has a black/white complement; hub for Life's sibling rules and the extensions beyond them
tags: [rule-family, life-like, rulestring, outer-totalistic, two-state]
sources: [eppstein-gliders-in-life-like-cellular-automata, eppstein-2010-growth-and-decay-in-life-like-ca, lifewiki-life-like-cellular-automaton, lifewiki-rulestring, lifewiki-star-trek, lifewiki-seeds, lifewiki-generations, cgol-ch12-0e0p-metacell, cgol-ch1-early-life]
created: 2026-09-25
updated: 2026-09-25
---

# Life-like cellular automaton

## Description

A Life-like cellular automaton is a rule on the 2D square grid, with cells alive or dead,
in which whether a dead cell is born and whether a live cell survives depends only on how
many of its eight neighbours ([[moore-neighbourhood](pages/moore-neighbourhood.md)]) are
alive. There are 2^18 = 262,144 of them.[^1] The count follows because each of the nine
possible neighbour counts, 0 through 8, can independently cause birth or not, and
independently allow survival or not (own reasoning).

**Outer-totalistic.** In the precise terms, these rules are *outer-totalistic*: the new
state depends on the cell's own state and the number of live neighbours. A *totalistic*
rule would depend only on the count including the cell itself. "Life-like" adds the square
grid and the eight-cell neighbourhood.[^2]

**Rulestrings.** A rule is written **Bx/Sy**, where x lists the neighbour counts that
cause birth and y the counts that allow survival. [[game-of-life](pages/game-of-life.md)]
is **B3/S23**.[^3] Golly and the RLE pattern format use this form; the fuller story of
rule notation is on [[rulestring](pages/rulestring.md)].[^4]

**Where the lowest birth count puts a rule.** Much of a rule's character follows from the
smallest neighbour count that causes birth.[^5]

| Lowest birth | Rules | Character |
|---|---|---|
| B1 | 2^16 | Every finite pattern grows at lightspeed in all directions; no still lifes, oscillators or spaceships, though some have replicators |
| B2 | 2^15 | Exploding or expanding: a domino on a pattern's edge breeds a new domino on the daughter's edge. Spaceships and oscillators still exist in many |
| B3 | 2^14 | Where chaos is possible, and where most studied rules live, Life among them |
| B4 or higher | 2^14 | Stable: no pattern can grow past its bounding box, so no spaceships |
| B0 with S8 | - | The vacuum fills at once; nothing stays finite |
| B0 without S8 | 2^16 | The other home of chaotic rules |

So a chaotic rule must have B3 or B0 (without S8).[^5] Johnston and Greene's balance
argument (see **Why Life among them**, below) reads the same map from Life's side: birth
on 2 is too explosive, and rules without birth on 3 or fewer die off too fast (own
reasoning linking the two sources). The counts come from fixing the lowest
birth: for B1, birth on 1 and no birth on 0, which leaves 16 of the 18 choices free,
giving 2^16 (own reasoning). [[seeds-rule](pages/seeds-rule.md)] (B2/S) is a B2 rule whose
patterns mostly explode even though no cell ever survives.[^6]

B0 rules were long neglected because no common software could simulate an infinite
plane that flashes on. Golly's QuickLife runs them by converting each into an equivalent
rule that avoids simulating infinitely many live cells.[^7]

**Growth and decay.** Eppstein sharpens the lowest-birth map into two yes/no questions
for the rules without B0: can a finite pattern escape every bounding box (*fertile*), and
can one die out (*mortal*)? B1 and B2 rules are fertile outright and rules without B1, B2
or B3 are not, so the open questions all sit in B3. There, spaceship searches show 10,736
of the 16,384 rules fertile, and mortality is settled for every one. His hypothesis is
that the fertile-and-mortal rules are where Life-style engineering lives, whatever their
behaviour from random starts ([[fertile-and-mortal-rules](pages/fertile-and-mortal-rules.md)]).[^8]
The same survey finds gliders commonplace across the family, and each known spaceship
works in a whole interval of rules, not just one ([[rule-range](pages/rule-range.md)]).[^9]

**Black/white complements.** Every rule has a complementary rule that behaves identically
with on and off swapped: birth on every N except where 8 - N is a survival count of the
original, and survival on every N except where 8 - N is a birth count.[^10] Life's
complement is B0123478/S01234678. Seeds' is B012345678/S01234578, and Star Trek's is
B12357/S01234678; both follow from the formula (own reasoning check).[^11] 512 = 2^9 rules
are their own complement, so the 262,144 rules do not quite pair off into halves.[^10]

**Why Life among them.** Johnston and Greene single Life out, "special (but by no means
unique)", on three grounds:[^12]
- *Simple rules.* Dying of overcrowding with too many neighbours and of isolation with
  too few is the natural shape for a model of living things.
- *Balance.* Almost any rule with birth on 2 has too many births for anything to
  stabilize. Most rules without birth on 3 or fewer die off too fast. Life's patterns
  typically stay alive without taking over the grid.
- *History.* It is the most studied rule, and pushing one rule far is its own interest.

**Notable members.**[^13]
- [[highlife](pages/highlife.md)] (B36/S23), with its 12-cell [[replicator](pages/replicator.md)].
- The replicator rule B1357/S1357, where every pattern replicates in 8 directions.
- B12345678/S012345678, where a single cell fills the plane.
- B34568/S15678, with a spiral-growth pattern.

**The rule hierarchy.** There are 2^18 Life-like rules, inside the 2^102
[[isotropic-non-totalistic-rule](pages/isotropic-non-totalistic-rule.md)]s, inside the 2^512 [[non-isotropic-rule](pages/non-isotropic-rule.md)]s on the
same neighbourhood. Any Life-like rule can be emulated inside Life by the OTCA metapixel or
the 0E0P [[metacell](pages/metacell.md)].[^14]

**Multistate extension.** Every Life-like rule is the two-state case of a
[[generations-rule](pages/generations-rule.md)]. Bx/Sy/C2 is Bx/Sy, and adding dying states gives rules such as
[[star-wars-rule](pages/star-wars-rule.md)] (B2/S345/C4) and [[brians-brain](pages/brians-brain.md)] (B2/S/C3).[^15]
Star Wars has a two-state namesake, [[star-trek-rule](pages/star-trek-rule.md)], though the
link is only in the name: Star Trek is the Life-like rule B3/S0248, born on 3 and
surviving on 0, 2, 4 or 8.[^16]

**Beyond Life-like rules.** Other variations change what counts as a neighbour (the
four-cell von Neumann neighbourhood), the grid (hexagonal, triangular, 1D, 3D), or let the
relative *positions* of live neighbours matter, not just their number. The last are
*isotropic non-totalistic* (INT) rules.[^17] The main generalizations:[^18]
- [[isotropic-non-totalistic-rule](pages/isotropic-non-totalistic-rule.md)]s count
  arrangements, written in Hensel notation.
- [[non-isotropic-rule](pages/non-isotropic-rule.md)]s also see absolute directions,
  written as MAP strings.
- [[generations-rule](pages/generations-rule.md)]s add dying states.
- [[larger-than-life](pages/larger-than-life.md)] and
  [[higher-range-outer-totalistic-rule](pages/higher-range-outer-totalistic-rule.md)]s
  widen the neighbourhood past distance 1.
- Other neighbourhoods and grids: the [[von-neumann-neighbourhood](pages/von-neumann-neighbourhood.md)]
  and [[hexagonal-neighbourhood](pages/hexagonal-neighbourhood.md)].

**Narrow and loose senses.** Strictly, a Life-like rule is a two-state outer-totalistic
rule on the range-1 Moore neighbourhood of the square grid. In everyday use "lifelike"
also covers non-totalistic rules or anything that behaves like Life.[^19]

**Soup search in other rules.** The soup-search programs TOLLCASS and apgsearch both run on
several Life-like rules, not only B3/S23 ([[soup-search](pages/soup-search.md)]).[^20]

## Appearances in Sources

- [[lifewiki-life-like-cellular-automaton](pages/lifewiki-life-like-cellular-automaton.md)] - definition, rule-space map by lowest birth count, complements, generalizations
- [[lifewiki-star-trek](pages/lifewiki-star-trek.md)], [[lifewiki-seeds](pages/lifewiki-seeds.md)] - two members and their complements
- [[eppstein-2010-growth-and-decay-in-life-like-ca](pages/eppstein-2010-growth-and-decay-in-life-like-ca.md)] - fertile/mortal map of the rules without B0
- [[eppstein-gliders-in-life-like-cellular-automata](pages/eppstein-gliders-in-life-like-cellular-automata.md)] - spaceships across the family, with their rule ranges
- [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] - outer-totalistic definition, notable rules, emulation
- [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] - the count of Life-like rules, B/S rulestrings, why B3/S23, INT and other variants

## Related Concepts

- [[generations-rule](pages/generations-rule.md)] - the multistate extension with dying states
- [[rulestring](pages/rulestring.md)] - how rules are named
- [[fertile-and-mortal-rules](pages/fertile-and-mortal-rules.md)], [[rule-range](pages/rule-range.md)] - mapping which rules grow, decay and carry which spaceships
- [[seeds-rule](pages/seeds-rule.md)], [[star-trek-rule](pages/star-trek-rule.md)] - members in the B2 and B3 regions
- [[larger-than-life](pages/larger-than-life.md)], [[higher-range-outer-totalistic-rule](pages/higher-range-outer-totalistic-rule.md)] - higher-range generalizations
- [[von-neumann-neighbourhood](pages/von-neumann-neighbourhood.md)], [[hexagonal-neighbourhood](pages/hexagonal-neighbourhood.md)] - other neighbourhoods
- [[highlife](pages/highlife.md)], [[replicator](pages/replicator.md)] - a notable member and its pattern
- [[isotropic-non-totalistic-rule](pages/isotropic-non-totalistic-rule.md)], [[non-isotropic-rule](pages/non-isotropic-rule.md)] - the larger rule families
- [[metacell](pages/metacell.md)] - emulates any Life-like rule inside Life
- [[game-of-life](pages/game-of-life.md)] - B3/S23, the best-known member
- [[moore-neighbourhood](pages/moore-neighbourhood.md)] - the neighbourhood the family is defined on
- [[cellular-automaton](pages/cellular-automaton.md)] - the general notion
- [[soup-search](pages/soup-search.md)] - census tools that also cover other Life-like rules

[^1]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.4 - "there are 2^18 = 262 144 distinct Life-like cellular automata: rules that can be applied to a 2D square grid of alive and dead cells that simply depend on the numbers of live and dead neighbors that lead to a cell staying alive or coming to life"
[^2]: [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] p.387 [synthesis] - "A 2-state cellular automaton is called outer-totalistic if the birth and death rules depend only on the state of the current cell, as well the number of live neighbors that it has"; n.4 "In contrast with totalistic cellular automata, in which the birth and death rules depend only on the number of live neighbors including the cell itself"; Life-like adds the 2D square grid and the Moore neighborhood
[^3]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.5 - "a rulestring of the form Bx/Sy, where we replace 'x' by all numbers of live neighbors that lead to the birth of a dead cell, and we replace 'y' by all numbers of live neighbors that lead to the survival of a live cell. For example, the Game of Life is described by the rulestring B3/S23"
[^4]: [[lifewiki-life-like-cellular-automaton](pages/lifewiki-life-like-cellular-automaton.md)] L22 - "In the notation used by Golly and in the RLE format for storing patterns, Life-like rules are expressed by rulestrings in the 'B0...8/S0...8' notation"
[^5]: [[lifewiki-life-like-cellular-automaton](pages/lifewiki-life-like-cellular-automaton.md)] L26-30 [synthesis] - B1: "all finite patterns grow at the speed of light in all directions. No still lifes, oscillators or spaceships are possible ... Several have replicators", 65536 rules; B2: "exploding or expanding in character ... a domino at the edge of a pattern will give rise to a new domino", spaceships and oscillators exist in many, 32768 rules; B4+: "stable in character, since no patterns can ever grow beyond their initial bounding box. In particular, no spaceships can exist", 16384 rules; B0 with S8: "the vacuum is unstable and will be immediately filled"; "This leaves 16384 rules in which the lowest birth condition is 3 ... as well as 65536 rules in which the lowest birth condition is 0 ... and 8 neighbors is not a survival condition. All chaotic rules must fall in either of these two areas"; "Most well-studied examples fall in the first one"
[^6]: [[lifewiki-seeds](pages/lifewiki-seeds.md)] L20 - "Even though all the living cells die in every generation (turning every pattern into a phoenix), most patterns are still exploding quadratically"
[^7]: [[lifewiki-life-like-cellular-automaton](pages/lifewiki-life-like-cellular-automaton.md)] L30 - "for long no commonly available software existed that could simulate the evolution of rules containing B0. Golly's QuickLife algorithm simulates them by converting them into equivalent rules to avoid having to simulate an infinite number of cells"
[^8]: [[eppstein-2010-growth-and-decay-in-life-like-ca](pages/eppstein-2010-growth-and-decay-in-life-like-ca.md)] pp.7-9,13-15 [synthesis] - fertile and mortal definitions; B1 and B2 fertile, no B1/B2/B3 infertile; "10736 out of the 16384 possible B3 rules have spaceships"; mortality "covers all rules that include B3"; "the rules most likely to support interesting patterns are the ones that are both fertile and mortal"
[^9]: [[eppstein-gliders-in-life-like-cellular-automata](pages/eppstein-gliders-in-life-like-cellular-automata.md)] raw/eppstein-ca-index.md L7 - "The results show that the existence of gliders is commonplace"; https://www.ics.uci.edu/~eppstein/ca/glider.db header - "minrule and maxrule are of the form B3/S23"
[^10]: [[lifewiki-life-like-cellular-automaton](pages/lifewiki-life-like-cellular-automaton.md)] L24 - "Each rule has a complementary rule which behaves identically under on-off reversal; namely the rule in which birth occurs on all N except those for which 8 - N is a survival condition in the original rule, and survival occurs on all N except those for which 8 - N is a birth condition in the original rule. For example, the rule complementary to Conway's Life is B0123478/S01234678. This however does not quite halve the number of effectively distinct rules, as there are 512 ... self-complementary rules"
[^11]: [[lifewiki-seeds](pages/lifewiki-seeds.md)] L18-19 - "Black/white reversal B012345678/S01234578"; [[lifewiki-star-trek](pages/lifewiki-star-trek.md)] L15-16 - "Black/white reversal B12357/S01234678"
[^12]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.4 [synthesis] - "the following three properties make Life special (but by no means unique)": simple rules (death from overcrowding and isolation); "almost any rule in which a cell is born when it has 2 live neighbors" is too chaotic, rules without birth on 3 or fewer are "too stable"; "historically it is the most well-studied rule"
[^13]: [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] pp.386-388 [synthesis] - HighLife (B36/S23) replicator; "the appropriately named replicator rule (B1357/S1357)"; B12345678/S012345678 single-cell replicator; spiral growth in B34568/S15678
[^14]: [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] pp.389,391,422 [synthesis] - 2^102 isotropic versus 2^18 outer-totalistic; 2^512 not necessarily isotropic; the OTCA metapixel "can be used to emulate any of the 2^18 different outer-totalistic (i.e., Life-like) cellular automata"
[^15]: [[lifewiki-generations](pages/lifewiki-generations.md)] L24 - "Any outer-totalistic cellular automaton with rulestring B.../S... is equivalent to the Generations rule with rulestring B.../S.../2"
[^16]: [[lifewiki-star-trek](pages/lifewiki-star-trek.md)] L19 - "Star Trek is a Life-like cellular automaton with rulestring B3/S0248. Dead cells are born if they have 3 neighbours and alive cells survive if they have no, 2, 4 or 8 neighbours"; [[lifewiki-star-wars](pages/lifewiki-star-wars.md)] L16 - "This article is about the Generations rule. For the outer-totalistic rule, see OCA:Star Trek"
[^17]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.5 [synthesis] - "this 4-cell neighborhood is called the von Neumann neighborhood"; "a hexagonal or triangular grid instead of a square one, or a 1D or 3D grid"; "not only the number of live neighbors matters, but also their relative positions--such rules are known as isotropic rules, or INT rules (short for 'isotropic non-totalistic')"
[^18]: [[lifewiki-life-like-cellular-automaton](pages/lifewiki-life-like-cellular-automaton.md)] L33-36 [synthesis] - isotropic non-totalistic rules "described using Hensel notation"; non-isotropic rules "described using MAP strings"; Generations rules add states; in Larger than Life rules "the size of a cell's neighborhood is extended to include cells with a distance greater than one"
[^19]: [[lifewiki-life-like-cellular-automaton](pages/lifewiki-life-like-cellular-automaton.md)] L38 - "a two-state non-totalistic rule, or any rule that is in some sense similar to Conway's Game of Life in behaviour, may also be referred to as life-like. However, this article follows the narrow definition, according to which a Life-like rule is a two-state outer-totalistic rule with range-1 Moore neighbourhood on the square tiling"
[^20]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.28 [synthesis] - TOLLCASS "also worked not just with Conway's Game of Life, but also with a handful of other Life-like cellular automata"; apgsearch "can be used with several different Life-like CA"
