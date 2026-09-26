---
title: Rulestring
category: Concepts
summary: The text names that identify cellular-automaton rules - B3/S23 birth/survival notation and the older 23/3 survival/birth form, V and H suffixes for von Neumann and hexagonal neighbourhoods, Hensel letters for arrangements, a state count for Generations, range-and-interval forms for Larger than Life and HROT, rule integers, and base-64 MAP strings for fully general rules
tags: [concept, notation, rulestring, hensel-notation, map-rulestring, rule-integer]
sources: [eppstein-gliders-in-life-like-cellular-automata, lifewiki-rulestring, lifewiki-seeds, lifewiki-star-trek, lifewiki-catagolue, lifewiki-life-like-cellular-automaton, lifewiki-larger-than-life, lifewiki-higher-range-outer-totalistic-rule, lifewiki-von-neumann-neighbourhood, lifewiki-hexagonal-neighbourhood]
created: 2026-09-25
updated: 2026-09-26
---

# Rulestring

## Description

A *rulestring* describes a cellular automaton's behaviour as a short string.[^1] The
notation grows in layers, and each layer matches a step outward in the rule families
the wiki covers: count-based two-state rules, then other neighbourhoods, arrangements,
extra states, larger ranges, and finally the fully general rule.

**Birth/survival.** The standard form is **B{counts}/S{counts}**. B lists the numbers of
live neighbours that bring a dead cell to life; S lists those that keep a live cell
alive.[^2]
- [[game-of-life](pages/game-of-life.md)] is **B3/S23**.
- [[seeds-rule](pages/seeds-rule.md)] is **B2/S**: the empty S means no cell ever survives.
- Golly and the RLE pattern format use this form, with counts 0 to 8.[^3]

**Survival/birth.** The older **S/B** form writes the lists the other way round with no
letters, so Life is **23/3**. It used to be the common form and is now rarely used.[^4]
It remains the more common form for [[generations-rule](pages/generations-rule.md)]s.[^5]

**Layers on top.**
- **Neighbourhood suffix.** A trailing **V** means the four-cell
  [[von-neumann-neighbourhood](pages/von-neumann-neighbourhood.md)]; a trailing **H**
  means the six-cell [[hexagonal-neighbourhood](pages/hexagonal-neighbourhood.md)], as
  in B2/S34H.[^6]
- **Arrangements (Hensel notation).** Letters after a count pick out particular
  arrangements of that many neighbours, as in B3-j6i/S23-c4i. This describes
  [[isotropic-non-totalistic-rule](pages/isotropic-non-totalistic-rule.md)]s and is named
  after Alan Hensel.[^5]
- **States.** Generations rules add a state count, as B25/S03467/C6 or 03467/25/6; C or
  G may prefix the count in B/S form.[^5]
- **Range.** [[larger-than-life](pages/larger-than-life.md)] and
  [[higher-range-outer-totalistic-rule](pages/higher-range-outer-totalistic-rule.md)]
  rules use comma-separated fields for range, states, survival and birth counts, and
  neighbourhood type: Life is R1,C2,S2-3,B3.[^7]

**Beyond strings.**[^8]
- **Rule integers** encode a Life-like rule as one number. Seeds is 4 and Star Trek
  (B3/S0248, [[star-trek-rule](pages/star-trek-rule.md)]) is 141832.[^9] Both fit a
  simple scheme: birth on n adds 2^n and survival on n adds 2^(9+n). For Star Trek,
  2^3 + 2^9 + 2^11 + 2^13 + 2^17 = 141832 (own reasoning, checked against these two
  values only).
- **MAP strings** describe [[non-isotropic-rule](pages/non-isotropic-rule.md)]s,
  including non-isotropic Generations rules, as a 512-bit number written in base 64.

**Ranges of rules.** A pattern usually works in many rules at once, so tools record a
*minimum* and *maximum* rulestring for it: Eppstein's spaceship database gives Life's
glider the range B3/S23 to B3678/S0235678 ([[rule-range](pages/rule-range.md)]).[^10]

**Same rule, many names.** A rule can have several valid rulestrings: Hensel strings are
not unique, and every Life-like rule is also the Generations rule with two states
([[life-like-cellular-automaton](pages/life-like-cellular-automaton.md)]). Rulestrings also
serve as keys for search tools. [[catagolue](pages/catagolue.md)] files its census results
under rule names such as b3s23.[^11]

## Appearances in Sources

- [[lifewiki-rulestring](pages/lifewiki-rulestring.md)] - the whole article
- [[lifewiki-life-like-cellular-automaton](pages/lifewiki-life-like-cellular-automaton.md)] - Golly and RLE notation
- [[lifewiki-larger-than-life](pages/lifewiki-larger-than-life.md)], [[lifewiki-higher-range-outer-totalistic-rule](pages/lifewiki-higher-range-outer-totalistic-rule.md)] - range-based notations
- [[lifewiki-hexagonal-neighbourhood](pages/lifewiki-hexagonal-neighbourhood.md)] - the H suffix
- [[lifewiki-seeds](pages/lifewiki-seeds.md)], [[lifewiki-star-trek](pages/lifewiki-star-trek.md)] - rule integers
- [[cgol-ch12-0e0p-metacell](pages/cgol-ch12-0e0p-metacell.md)] - Appendix B.6-B.7: rulestrings and Hensel notation
- [[golly-help-generations](pages/golly-help-generations.md)] - Golly's survival/birth/states notation for Generations rules

## Related Concepts

- [[life-like-cellular-automaton](pages/life-like-cellular-automaton.md)] - the family B/S notation was made for
- [[isotropic-non-totalistic-rule](pages/isotropic-non-totalistic-rule.md)] - Hensel notation
- [[non-isotropic-rule](pages/non-isotropic-rule.md)] - MAP strings
- [[generations-rule](pages/generations-rule.md)] - state-count suffix
- [[larger-than-life](pages/larger-than-life.md)], [[higher-range-outer-totalistic-rule](pages/higher-range-outer-totalistic-rule.md)] - range notation
- [[rule-range](pages/rule-range.md)] - a pattern's minimum and maximum rulestring
- [[notation-map](pages/notation-map.md)] - the symbol crosswalk for the von Neumann, Hedlund and Kari sources
- [[ruleloader](pages/ruleloader.md)] - for rules that no string can describe, Golly reads a rule file

[^1]: [[lifewiki-rulestring](pages/lifewiki-rulestring.md)] L6 - "Rulestrings are a way of describing the behavior of various classes of cellular automaton in the form of a string"
[^2]: [[lifewiki-rulestring](pages/lifewiki-rulestring.md)] L8-9 [synthesis] - "B (for birth) is a list of all the numbers of live neighbors that cause a dead cell to come alive (be born); S (for survival) is a list of all the numbers of live neighbors that cause a live cell to remain alive"; "the seeds rulestring is B2/S"; "The rulestring of Conway's Game of Life is B3/S23"
[^3]: [[lifewiki-life-like-cellular-automaton](pages/lifewiki-life-like-cellular-automaton.md)] L22 - "In the notation used by Golly and in the RLE format for storing patterns, Life-like rules are expressed by rulestrings in the 'B0...8/S0...8' notation"
[^4]: [[lifewiki-rulestring](pages/lifewiki-rulestring.md)] L11 - "In this format, Conway's Game of Life would have the rulestring 23/3. S/B notation used to be more common, but has fallen into disuse in recent years"
[^5]: [[lifewiki-rulestring](pages/lifewiki-rulestring.md)] L15-16 [synthesis] - Hensel notation "after Alan Hensel, where each number in the list of birth and survival conditions is followed by an optional list of relative cell alignments"; Generations rules add a state-count suffix, "B25/S03467/C6 and 03467/25/6 describe the same CA"
[^6]: [[lifewiki-rulestring](pages/lifewiki-rulestring.md)] L13 - "a suffixed V indicates that the CA in question uses the von Neumann neighbourhood, while a suffixed H indicates use of the hexagonal neighbourhood"; [[lifewiki-hexagonal-neighbourhood](pages/lifewiki-hexagonal-neighbourhood.md)] L7 - "These rules are typically notated using the H suffix (e.g. B2/S34H)"
[^7]: [[lifewiki-rulestring](pages/lifewiki-rulestring.md)] L17 - "Larger than Life rules use rulestrings of a different form that specify the rule's range, number of states, survival and birth counts, and neighborhood type"; [[lifewiki-larger-than-life](pages/lifewiki-larger-than-life.md)] L48-51 - "R1,C2,S2-3,B3 B3/S23 Life"
[^8]: [[lifewiki-rulestring](pages/lifewiki-rulestring.md)] L19-20 [synthesis] - rule integers describe Life-like rules "using integers rather than strings"; non-isotropic rules "are typically described using MAP strings: 512-bit integers encoded as base64 strings"
[^9]: [[lifewiki-seeds](pages/lifewiki-seeds.md)] L11-15 [synthesis] - Rulestring /2, B2/S, Rule integer 4; [[lifewiki-star-trek](pages/lifewiki-star-trek.md)] L8-12 [synthesis] - Rulestring 0248/3, B3/S0248, Rule integer 141832
[^10]: https://www.ics.uci.edu/~eppstein/ca/glider.db header and entry "Glider" - "minrule and maxrule are of the form B3/S23"; "Glider:John Conway, 1970:B3/S23:B3678/S0235678"
[^11]: [[lifewiki-catagolue](pages/lifewiki-catagolue.md)] L540 - census endpoint "https://catagolue.hatsya.com/census/<rule>/<symmetry>"; [[lifewiki-apgsearch](pages/lifewiki-apgsearch.md)] L198 - "making b3s23/G1 searching roughly twice as fast"
