---
title: RuleLoader
category: Concepts
summary: Golly's algorithm for rules defined in external .rule files (rule tables and rule trees) - rule "Foo" loads Foo.rule, a text file of @RULE, @TABLE, @TREE, @COLORS and @ICONS sections; the escape hatch for any rule no rulestring or built-in algorithm covers, and the format apgsearch and Catagolue accept for custom rules
tags: [concept, golly, ruleloader, rule-table, rule-tree, rule-format, software]
sources: [lifewiki-ruleloader, lifewiki-apgsearch, lifewiki-catagolue, lifewiki-higher-range-isotropic-non-totalistic-rule, lifewiki-hexagonal-neighbourhood]
created: 2026-09-25
updated: 2026-09-25
---

# RuleLoader

## Description

*RuleLoader* is the Golly algorithm that simulates rules defined in **.rule files**, also
known as rule tables and rule trees.[^1] Golly's other algorithms are QuickLife, HashLife,
Generations, Larger than Life and LifeSuper.[^2] Each is built for rule families that a
[[rulestring](pages/rulestring.md)] can name, such as
[[life-like-cellular-automaton](pages/life-like-cellular-automaton.md)]s,
[[generations-rule](pages/generations-rule.md)]s and
[[larger-than-life](pages/larger-than-life.md)] rules; RuleLoader is the open end (own
reasoning). A rule that none of them covers can still be run if someone
writes it out as a file.

**The file.**[^3]
- Given the rule name "Foo", RuleLoader looks for **Foo.rule**.
- A .rule file is plain text in sections, each starting with a line **@XXX** (uppercase).
  It carries everything about the rule: name, documentation, the transition data, and
  display colours and icons.
- Recognized sections are **@RULE** (mandatory), **@TABLE** and **@TREE** (the transition
  data), **@COLORS** and **@ICONS**. Only the first of any duplicated section is used, and
  unrecognized sections are silently ignored.

**What it makes possible.**
- **Rules with no notation.** Several isotropic rulespaces, including three- and
  four-state isotropic Moore rules, have no direct software support. They can still be
  simulated through rule tables ([[isotropic-non-totalistic-rule](pages/isotropic-non-totalistic-rule.md)]).[^4]
  Golly also has no native notation for isotropic
  [[hexagonal-neighbourhood](pages/hexagonal-neighbourhood.md)] rules, so they run as rule
  tables or MAP strings.[^5]
- **Custom soup searches.** [[apgsearch](pages/apgsearch.md)] accepts Golly rule tables and
  trees, and [[catagolue](pages/catagolue.md)] lists custom ruletables among its supported
  rule types.[^6] Range-2 von Neumann isotropic rules, for example, are soup-searched this
  way with a custom neighbourhood.[^7]

A shared collection of rule files is kept in the GollyGang "Rule Table Repository" on
GitHub, and the ConwayLife forums keep a thread on RuleLoader's quirks with B0 rules (rules
where empty neighbourhoods give birth).[^8]

## Appearances in Sources

- [[lifewiki-ruleloader](pages/lifewiki-ruleloader.md)] - the whole article
- [[lifewiki-higher-range-isotropic-non-totalistic-rule](pages/lifewiki-higher-range-isotropic-non-totalistic-rule.md)] - rulespaces simulated only through ruletables
- [[lifewiki-hexagonal-neighbourhood](pages/lifewiki-hexagonal-neighbourhood.md)] - isotropic hex rules in Golly
- [[lifewiki-apgsearch](pages/lifewiki-apgsearch.md)], [[lifewiki-catagolue](pages/lifewiki-catagolue.md)] - custom rules in soup search

## Related Concepts

- [[rulestring](pages/rulestring.md)] - the compact alternative when a rule family has a notation
- [[non-isotropic-rule](pages/non-isotropic-rule.md)] - MAP strings, the other route for rules without a notation
- [[generations-rule](pages/generations-rule.md)], [[larger-than-life](pages/larger-than-life.md)] - families with their own built-in Golly algorithms

[^1]: [[lifewiki-ruleloader](pages/lifewiki-ruleloader.md)] L8 - "RuleLoader is the algorithm that Golly uses to simulate .rule files, also known as rule tables and rule trees"
[^2]: [[lifewiki-ruleloader](pages/lifewiki-ruleloader.md)] L35 - "Algorithms QuickLife • HashLife • Generations • Larger than Life • LifeSuper • RuleLoader"
[^3]: [[lifewiki-ruleloader](pages/lifewiki-ruleloader.md)] L10-18 [synthesis] - "Given the rule string 'Foo', RuleLoader will search for a file called Foo.rule"; "A .rule file contains all the information about a rule: its name, documentation, table/tree data ..., and any color/icon information"; sections start "@XXX... where X is an uppercase letter. If there is more than one section with the same name then only the first one is used. Any unrecognized sections are silently ignored"; @RULE (mandatory), @TABLE, @TREE, @COLORS, @ICONS (optional)
[^4]: [[lifewiki-higher-range-isotropic-non-totalistic-rule](pages/lifewiki-higher-range-isotropic-non-totalistic-rule.md)] L248-257,L288-297,L397 [synthesis] - 3-state INT and 4-state INT rows marked with note 10: "The rulespace can be simulated via ruletables, however no direct support for the notation exists"
[^5]: [[lifewiki-hexagonal-neighbourhood](pages/lifewiki-hexagonal-neighbourhood.md)] L37 - "Golly does not support isotropic non-totalistic hexagonal rules using this syntax, so they must instead be simulated using either rule tables or MAP strings"
[^6]: [[lifewiki-apgsearch](pages/lifewiki-apgsearch.md)] L187 - "Support for custom cellular automata using Golly rule tables and trees"; [[lifewiki-catagolue](pages/lifewiki-catagolue.md)] L433 - "Custom Golly ruletables"
[^7]: [[lifewiki-higher-range-isotropic-non-totalistic-rule](pages/lifewiki-higher-range-isotropic-non-totalistic-rule.md)] L403 - "Range 2 von Neumann isotropic rules can be searched using Adam P. Goucher's apgsearch by means of a ruletable using a custom neighbourhood"
[^8]: [[lifewiki-ruleloader](pages/lifewiki-ruleloader.md)] L28-29 [synthesis] - "RuleLoader's B0 handling quirks (discussion thread)"; "'Rule Table Repository'. github.com/GollyGang"
