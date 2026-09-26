---
title: Generations rule
category: Rules
summary: A multistate extension of Life-like rules in which a live cell that fails its survival condition does not die at once but passes through a fixed sequence of dying ("refractory") states that count as neither alive nor available for birth; written Bx/Sy/Cn (or Golly's y/x/n), with Life-like rules as the n = 2 case; Brian's Brain and Star Wars are the best known
tags: [rule-family, generations, multistate, refractory, dying-states, rulestring, mcell]
sources: [lifewiki-generations, lifewiki-list-of-generations-rules, golly-help-generations]
created: 2026-09-25
updated: 2026-09-25
---

# Generations rule

## Description

A *Generations* rule is a multistate generalization of a
[[life-like-cellular-automaton](pages/life-like-cellular-automaton.md)]. A cell that would
die in the two-state rule instead advances to the next state, "getting older" before it
finally dies.[^1] The in-between states are the *dying* or *refractory* states. A cell in
one is not live for counting neighbours, and it cannot be born until it cycles back to
dead.[^2]

**The rule, with n states.**[^2]
- State 0 (dead) becomes state 1 (live) if its number of state-1 neighbours is in the
  birth set.
- State 1 stays in state 1 if its number of state-1 neighbours is in the survival set;
  otherwise it advances to state 2.
- Any state m ≥ 2 advances to (m + 1) mod n, so the last state returns to 0.

A live cell that stops surviving therefore spends n − 2 generations dying, then waits for
a birth like any other dead cell. The name refers to cells ageing and has nothing to do
with "generations" in the sense of time steps.[^3]

**Notation.**
- **Bx/Sy/n**, or the survival-first **y/x/n**. **Bx/Sy/Cn** (C for state count) and
  **Bx/Sy/Gn** are also used. n ≥ 2 counts every state, including dead and live.[^4]
- Golly uses survival/birth/states and supports 2 to 256 states. Star Wars is B2/S345/C4 =
  345/2/4.[^5]
- Every Life-like rule B.../S... is the Generations rule B.../S.../2, with no dying states.
  So [[game-of-life](pages/game-of-life.md)] is B3/S23/2.[^4]
- B0 Generations rules exist, but support is limited. Golly does not run them; CAViewer
  does.[^6]

**Examples.**[^7]

| Rule | S/B/C form | Name | Character | Author |
|---|---|---|---|---|
| B2/S/C3 | /2/3 | [[brians-brain](pages/brians-brain.md)] | chaotic | Brian Silverman |
| B2/S345/C4 | 345/2/4 | [[star-wars-rule](pages/star-wars-rule.md)] | exploding | Mirek Wójtowicz |
| B24/S345/C25 | 345/24/25 | Bombers | chaotic | Mirek Wójtowicz |
| B2/S2/C25 | 2/2/25 | Faders (a "genetic" cross of Life and Brian's Brain) | exploding | Rudy Rucker and John Walker |
| B23/S2/C8 | 2/23/8 | RainZha (simplest Zhabotinsky-style spirals) | exploding | Rudy Rucker and John Walker |
| B45678/S12345/C8 | 12345/45678/8 | Lava | expanding | Mirek Wójtowicz |
| B458/S012345/C3 | 012345/458/3 | Lines (self-organizes into linear structures) | stable | Anders Starmark |

**Behaviour.** Dying tails block births behind a moving front, so patterns tend to move
toward their live edge. Refractory states make small lightspeed spaceships common. In
Brian's Brain almost every pattern moves, and in Star Wars most spaceships travel at
c.[^8] Several rules in the family produce spirals like those of the
Belousov-Zhabotinsky reaction.[^7]

**Extensions.**[^9]
- Generations rules adapt to von Neumann, hexagonal and triangular neighbourhoods, and to
  non-totalistic ([[isotropic-non-totalistic-rule](pages/isotropic-non-totalistic-rule.md)])
  and non-isotropic ([[non-isotropic-rule](pages/non-isotropic-rule.md)]) rules. With MAP
  rules and 2-256 states, Golly supports 255 × 2^512 Generations rules.
- Larger than Life extends them to larger neighbourhoods.
- *Reverse* Generations ("snoitareneG") rules, in which cells take time to become alive,
  have been explored. Both are subsets of an Extended Generations rulespace that apgsearch
  supports.

**Software.** MCell and Golly (up to 256 states) run Generations rules, as do LifeViewer
(non-B0) and CAViewer (including B0).[^6]

## Appearances in Sources

- [[lifewiki-generations](pages/lifewiki-generations.md)] - definition, notation, software, extensions
- [[lifewiki-list-of-generations-rules](pages/lifewiki-list-of-generations-rules.md)] - rule catalogue
- [[golly-help-generations](pages/golly-help-generations.md)] - Golly's notation, neighbourhood and MAP variants

## Related Concepts

- [[life-like-cellular-automaton](pages/life-like-cellular-automaton.md)] - the n = 2 case
- [[star-wars-rule](pages/star-wars-rule.md)], [[brians-brain](pages/brians-brain.md)] - the best-known members
- [[spaceship](pages/spaceship.md)] - dying states make spaceships abundant

[^1]: [[lifewiki-generations](pages/lifewiki-generations.md)] L6-7 - "Generations rules are a multistate generalization of Life-like cellular automata in which live cells can exist in different states, and cells that would die in a 2-state cellular automaton instead advance to the next state. The name 'Generations' is due to the conceptualization of this process as cells 'getting older' before eventually dying"
[^2]: [[lifewiki-generations](pages/lifewiki-generations.md)] L19-23 [synthesis] - state 0 "will advance to state 1 ('get born') ... if the number of neighbors in state 1 ... is present in the rule's birth conditions"; state 1 remains if in the survival conditions, otherwise "Advance to state 2 ('age')"; "A cell in state m ≥ 2 will advance to state ((m + 1) mod n)"
[^3]: [[lifewiki-generations](pages/lifewiki-generations.md)] L121 - "The name 'Generations', and the different states in which cells in Generations rules can exist, should not be confused with the generations (i.e. repeated evolution) of a pattern"
[^4]: [[lifewiki-generations](pages/lifewiki-generations.md)] L18,L24,L122 [synthesis] - "rulestrings of the form Bx/Sy/n or y/x/n ... where n is any natural number ≥2"; "Any outer-totalistic cellular automaton with rulestring B.../S... is equivalent to the Generations rule with rulestring B.../S.../2"; "Bx/Sy/Cn and Bx/Sy/Gn are also sometimes used, with 'C' standing for 'Count' (of cell states)"
[^5]: [[golly-help-generations](pages/golly-help-generations.md)] L5,L18 [synthesis] - survival digits, then birth digits, then "the maximum number of cell states (from 2 to 256)"; "345/2/4 [Star Wars]"
[^6]: [[lifewiki-generations](pages/lifewiki-generations.md)] L25,L109-110 [synthesis] - "B0 is also possible for Generations rules, however software support is not widespread"; "Both MCell and Golly support Generations rules, the latter with a maximum of 256 states. Golly currently does not support Generations rules with B0"; LifeViewer supports non-B0 rules; "CAViewer can support Generations rules including those with B0"
[^7]: [[lifewiki-list-of-generations-rules](pages/lifewiki-list-of-generations-rules.md)] L44-62,L110-115,L155-167,L200-205,L237-243 [synthesis] - entries for Bombers, Brian's Brain, Faders, Lava, Lines, RainZha ("The simplest 'Zhabotinsky' style cellular automaton. It spontaneously generates spirals") and Star Wars; further Zhabotinsky-reaction rules at L30,L139
[^8]: [[lifewiki-star-wars](pages/lifewiki-star-wars.md)] L50 - "Most of the spaceships in Star Wars are at c orthogonal"; https://en.wikipedia.org/wiki/Brian%27s_Brain (2026-08-13) - "The 'dying state' cells tend to lead to directional movement, so almost every pattern in Brian's Brain is a spaceship"
[^9]: [[lifewiki-generations](pages/lifewiki-generations.md)] L112-115 [synthesis] - adaptation to other neighbourhoods and to non-totalistic and non-isotropic rules; "Larger than Life rules extend Generations rules to larger neighbourhoods"; "Reverse Generations rules (also called 'snoitareneG' rules), in which cells take time to become alive, have been explored"; "subsets of the Extended Generations rulespace, which is supported by apgsearch"; [[golly-help-generations](pages/golly-help-generations.md)] L73 - "255*2^512 (roughly 3.42x10^156) unique rules"
