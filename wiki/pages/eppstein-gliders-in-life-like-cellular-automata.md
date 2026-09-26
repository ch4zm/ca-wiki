---
title: "Eppstein, Gliders in Life-Like Cellular Automata (web site and glider.db)"
category: Sources
summary: David Eppstein's long-running site asking which Life-like rules have gliders - a database of spaceships, each tagged with the minimum and maximum rule it works in, maps of known spaceship speeds across the B3 and B2 rules, a critique of Wolfram's classes, and a "most wanted" list of rules that seem like they should have gliders
tags: [source, web, eppstein, glider-db, spaceships, rule-space, rule-range, wolfram-classes]
sources: [eppstein-gliders-in-life-like-cellular-automata]
created: 2026-09-25
updated: 2026-09-26
---

# Eppstein, Gliders in Life-Like Cellular Automata (web site and glider.db)

**Source:** raw/eppstein-ca-index.md, raw/eppstein-ca-lifelike.md, raw/eppstein-ca-wolfram.md, raw/eppstein-ca-wanted.md, raw/eppstein-ca-map-b3.md, raw/eppstein-ca-map2.md, saved from https://www.ics.uci.edu/~eppstein/ca/; the database itself is https://www.ics.uci.edu/~eppstein/ca/glider.db (a local copy was read, header and sample entries only; not tracked in raw/).
**Date ingested:** 2026-09-25
**Type:** web site and data file

## Summary

The site starts from a claim of Wolfram's that outside a few variants of Life no definite
class-4 rules turned up among thousands of outer-totalistic rules, and asks whether
gliders are really that rare. Eppstein's answer, from years of searching, is that
gliders are commonplace in Life-like rules.[^1] He finds gliders in rules that would
fall in each of Wolfram's four classes, and offers a simpler three-way screen: rules
where patterns cannot contract, rules where they cannot expand, and the rest, where
alone gliders can exist ([[classification-of-cellular-automata](pages/classification-of-cellular-automata.md)]).[^2]
The later chapter [[eppstein-2010-growth-and-decay-in-life-like-ca](pages/eppstein-2010-growth-and-decay-in-life-like-ca.md)]
sharpens this screen into [[fertile-and-mortal-rules](pages/fertile-and-mortal-rules.md)].

The core is `glider.db`. Each line records a spaceship's name, discoverer, a **minimum
and maximum rule**, its period, displacement and pattern; the file runs to over 20,000 lines (own count of the local copy). The aim is not every glider,
since most rules with one glider have infinitely many, but one example for every known
pairing of speed and rule, plus unusually small gliders and gliders that work unchanged
in many rules ([[rule-range](pages/rule-range.md)]).[^3] Two maps lay the B3 and B2 rules
out in a Gray-code order, so similar rules sit side by side, and show how many distinct
spaceship speeds are known for each. Eppstein warns that the counts reflect search effort
as much as the rules themselves.[^4] A "most wanted" list names rules that look as if they
should have moving patterns but have resisted search, and asks for proofs that whole
blocks of rules cannot have gliders.[^5]

## Key Takeaways

- Gliders are common in Life-like rules, including rules of every Wolfram class, for
  example B367/S3678, B3/S256, B3/S234, B345678/S12468 and B3/S23.[^2]
- Each database entry is valid across a whole interval of rules, from its minimum to its
  maximum rule; Life's glider runs unchanged from B3/S23 to B3678/S0235678.[^6]
- The maps turn rule space into a picture: where spaceships are known, and how many
  speeds, rule by rule.[^4]
- Open questions include rules such as "land rush" B35/S234578 and "longlife" B345/S5,
  and proofs that rules with B23, or B3 with no survival on 0-5, cannot have gliders.[^5]

## Entities & Concepts

- [[rule-range](pages/rule-range.md)] - the minimum/maximum-rule idea the database is built on
- [[fertile-and-mortal-rules](pages/fertile-and-mortal-rules.md)] - the classification the site's screen grew into
- [[classification-of-cellular-automata](pages/classification-of-cellular-automata.md)] - Wolfram's classes, which the site argues against
- [[spaceship](pages/spaceship.md)], [[glider](pages/glider.md)] - what the database lists
- [[life-like-cellular-automaton](pages/life-like-cellular-automaton.md)], [[rulestring](pages/rulestring.md)] - the rule family and its notation
- [[eppstein-2002-searching-for-spaceships](pages/eppstein-2002-searching-for-spaceships.md)] - Eppstein's account of the searches that find such ships

## Relation to Other Wiki Pages

The database is the evidence behind the fertility counts in
[[eppstein-2010-growth-and-decay-in-life-like-ca](pages/eppstein-2010-growth-and-decay-in-life-like-ca.md)],
and its min/max-rule field is the same idea behind "polyglot" unit cells that run in
several rules at once ([[metacell](pages/metacell.md)]).

[^1]: [[eppstein-gliders-in-life-like-cellular-automata](pages/eppstein-gliders-in-life-like-cellular-automata.md)] raw/eppstein-ca-index.md L6-7 - "Except for a few simple variants on the Game of Life, no other definite class-4 two-dimensional cellular automata were found in a random sample of several thousand outer totalistic rules. Are gliders really so rare?"; "The results show that the existence of gliders is commonplace, contradicting Wolfram and calling into question his classification"
[^2]: [[eppstein-gliders-in-life-like-cellular-automata](pages/eppstein-gliders-in-life-like-cellular-automata.md)] raw/eppstein-ca-wolfram.md L13,L82-84 [synthesis] - "Our investigation has turned up gliders in systems that would likely be classified in each of the four classes: e.g. ... B367/S3678 (class 1), B3/S256 or B3/S234 (both class 2 ...), B345678/S12468 (class 3), and B3/S23 (class 4)"; "Contraction impossible", "Expansion impossible", "Both expansion and contraction possible. Only in the remaining cases can gliders exist"
[^3]: https://www.ics.uci.edu/~eppstein/ca/glider.db header - "name:discoverer:minrule:maxrule:period:dx:dy:x:y:rle"; "there are usually infinitely many types of gliders whenever there is any). The primary reason for including a glider in this list is to cover every known combination of speed and rules. Secondarily, I am also including particularly small gliders, or gliders that work unchanged in many different rules"
[^4]: [[eppstein-gliders-in-life-like-cellular-automata](pages/eppstein-gliders-in-life-like-cellular-automata.md)] raw/eppstein-ca-map-b3.md L6-7 - "the number of different velocities listed in my glider database for each rule of the form B3xxxx/Sxxxx"; "a form of Gray code designed to make rules with similar behavior tend to line up next to each other"; "My searches for gliders to list here have not been systematic -- if one rule has more gliders than another, it may mean that it's easier to find gliders for it, but it also may merely mean that I used more powerful search tools on it"; raw/eppstein-ca-map2.md L6 - the same chart for rules of the form B2xxxx/Sxxxx
[^5]: [[eppstein-gliders-in-life-like-cellular-automata](pages/eppstein-gliders-in-life-like-cellular-automata.md)] raw/eppstein-ca-wanted.md L6-13,L55 [synthesis] - rules which "'seem like' they should have moving patterns ... but for which my search software has been unsuccessful"; B35/S234578 "land rush"; B345/S5 "longlife"; "I would like a mathematical proof that certain rules (e.g. rules with B23, with B3 and none of S0-S5, or with all of B3/S34567) are unable to support gliders"
[^6]: https://www.ics.uci.edu/~eppstein/ca/glider.db entry "Glider" - "Glider:John Conway, 1970:B3/S23:B3678/S0235678:4/2:-1:-1:3:3:bo$o$3o!"
