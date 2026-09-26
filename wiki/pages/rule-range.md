---
title: Rule range (minimum and maximum rule)
category: Concepts
summary: Every pattern consults only some of a rule's birth and survival conditions, so it behaves identically across a whole interval of rules, from a minimum rule (the conditions it uses) to a maximum rule (those plus every condition it never meets); Life's glider works in 256 rules, the Caterpillar in one; the interval lets a single spaceship prove many rules fertile and a single "polyglot" unit cell prove many rules universal
tags: [concept, rule-space, rule-range, minrule, maxrule, polyglot, life-like, spaceships]
sources: [eppstein-gliders-in-life-like-cellular-automata, lifewiki-unit-cell, eppstein-2010-growth-and-decay-in-life-like-ca]
created: 2026-09-25
updated: 2026-09-25
---

# Rule range (minimum and maximum rule)

## Description

**The idea.** A [[life-like-cellular-automaton](pages/life-like-cellular-automaton.md)]
rule is a list of yes/no answers: for each neighbour count 0-8, does a dead cell with that
count get born, and does a live cell survive? A particular pattern, followed through its
whole evolution, only ever asks some of those questions. Answers to the questions it
never asks cannot affect it. So the pattern behaves the same in every rule that agrees on
the questions it does ask (own reasoning, from the rule definition). Eppstein's spaceship
database records exactly this for each entry: a **minimum rule** and a **maximum
rule**.[^1] Read as rulestrings, the pattern works in every rule that contains the
minimum and is contained in the maximum (own reasoning, reading the two fields as bounds).

- The **minimum rule** holds the births and survivals the pattern actually uses.
- The **maximum rule** adds every birth and survival condition the pattern never meets.
- The rules in between form a box: each unused condition can be switched on or off freely,
  so the number of rules is 2 to the number of unused conditions (own reasoning).

**Life's glider.** The [[glider](pages/glider.md)] runs unchanged from B3/S23 to
B3678/S0235678.[^2] The difference is three births (6, 7, 8) and five survivals (0, 5, 6,
7, 8), eight free conditions, so the glider works in 2^8 = 256 rules. Read the other way,
the interval says that during the glider's cycle no dead cell ever sees 6, 7 or 8 live
neighbours, and no live cell sees 0 or more than 4 (own reasoning, from the two
rulestrings).

**Endemic patterns.** At the other extreme, a large engineered pattern exercises almost
every condition. The Caterpillar spaceship's minimum and maximum are both B3/S23: it
works in Life alone.[^3]

**Why the interval matters.**
- **Fertility for free.** One spaceship proves every rule in its range
  [[fertile-and-mortal-rules](pages/fertile-and-mortal-rules.md)]. The database
  deliberately keeps gliders that work unchanged in many rules, and its maps count known
  speeds rule by rule across the B3 and B2 rules, so a few wide-range spaceships cover
  large blocks of rule space.[^4] This is how spaceship search can settle fertility for
  10,736 B3 rules without searching each one (own reasoning, connecting the database to
  the count in Eppstein 2010).[^5]
- **Universality for free.** A unit cell that emulates [[rule-110](pages/rule-110.md)] is a
  proof of Turing-completeness for every rule it runs in. Such *polyglot* unit cells are
  known: Jason Summers' Rule 110 cell for Life also runs in EightLife, a B3[8]/S23[8]
  polyglot works in Life, EightLife, Pedestrian Life and HoneyLife, and a B36[8]/S236[8]
  one covers HighLife, LowDeath and others ([[metacell](pages/metacell.md)]).[^6] The
  bracketed 8 marks a condition that may be on or off, the rulestring form of a range of
  four rules (own reasoning, from the listed rules B3/S23, B3/S238, B38/S23 and
  B38/S238).
- **Beyond Life-like rules.** The same interval idea carries to
  [[isotropic-non-totalistic-rule](pages/isotropic-non-totalistic-rule.md)]s, whose
  conditions are finer. The U-pentomino, a period-8 natural
  [[replicator](pages/replicator.md)] that emulates Rule 110, works in every rule between
  two long Hensel-notation rulestrings.[^7]

**A map of rule space from the pattern's side.** A rule's page lists the patterns that
live in it; a pattern's range lists the rules it lives in. Together they turn rule space
into a lattice in which every object occupies a box, and the overlaps of boxes are where
technology built in one rule transfers to its neighbours (own reasoning). The database
format was designed for the first half of this picture, one example per speed and rule;
its maximum-rule field already carries the second.[^1]

## Appearances in Sources

- [[eppstein-gliders-in-life-like-cellular-automata](pages/eppstein-gliders-in-life-like-cellular-automata.md)] - the minrule/maxrule fields of glider.db; the glider and Caterpillar entries; the rule maps
- [[lifewiki-unit-cell](pages/lifewiki-unit-cell.md)] - polyglot Rule 110 unit cells; the U-pentomino's isotropic range
- [[eppstein-2010-growth-and-decay-in-life-like-ca](pages/eppstein-2010-growth-and-decay-in-life-like-ca.md)] - spaceship-based fertility counts

## Related Concepts

- [[rulestring](pages/rulestring.md)] - the notation in which ranges are written
- [[fertile-and-mortal-rules](pages/fertile-and-mortal-rules.md)] - one wide-range spaceship certifies fertility across its range
- [[metacell](pages/metacell.md)], [[rule-110](pages/rule-110.md)] - polyglot unit cells carry a universality proof across rules
- [[glider](pages/glider.md)], [[spaceship](pages/spaceship.md)] - the entries whose ranges the database records
- [[life-like-cellular-automaton](pages/life-like-cellular-automaton.md)] - the rule lattice the ranges live in

[^1]: https://www.ics.uci.edu/~eppstein/ca/glider.db header - "name:discoverer:minrule:maxrule:period:dx:dy:x:y:rle"; "minrule and maxrule are of the form B3/S23"; "The primary reason for including a glider in this list is to cover every known combination of speed and rules"
[^2]: https://www.ics.uci.edu/~eppstein/ca/glider.db entry "Glider" - "Glider:John Conway, 1970:B3/S23:B3678/S0235678:4/2:-1:-1:3:3:bo$o$3o!"
[^3]: https://www.ics.uci.edu/~eppstein/ca/glider.db entry "Caterpillar" - "Caterpillar:Jason Summers, Gabriel Nivasch, and David Bell, 2005:B3/S23:B3/S23:270:0:102"
[^4]: https://www.ics.uci.edu/~eppstein/ca/glider.db header - "Secondarily, I am also including particularly small gliders, or gliders that work unchanged in many different rules"; [[eppstein-gliders-in-life-like-cellular-automata](pages/eppstein-gliders-in-life-like-cellular-automata.md)] raw/eppstein-ca-map-b3.md L6 - "the number of different velocities listed in my glider database for each rule of the form B3xxxx/Sxxxx"
[^5]: [[eppstein-2010-growth-and-decay-in-life-like-ca](pages/eppstein-2010-growth-and-decay-in-life-like-ca.md)] p.8 - "We have used our search software, together with searches using small random seeds, to search for spaceships in these B3 rules; so far, we have found that 10736 out of the 16384 possible B3 rules have spaceships and therefore are fertile"
[^6]: [[lifewiki-unit-cell](pages/lifewiki-unit-cell.md)] L41,L43,L49 - "One is constructed in CGoL by Jason Summers and later it was trivially shown using Golly that it is a polyglot (works in EightLife, too)"; "B3[8]/S23[8] polyglot: works in Life, EightLife, Pedestrian Life and HoneyLife"; "B36[8]/S236[8] polyglot: HighLife, LowDeath, and others"
[^7]: [[lifewiki-unit-cell](pages/lifewiki-unit-cell.md)] L24 - "the U-pentomino is a period-8 natural replicator that emulates Rule 110 in rules between B2ei3aci4aei5kqr7e/S01c2-kn3ijry4citwy5aeiq and B2ein3acikq4-jrty5-ceiy6-ck78/S01c2-k3-acen4-a5-jny6-c78"
