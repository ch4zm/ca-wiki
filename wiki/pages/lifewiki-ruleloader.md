---
title: "LifeWiki: RuleLoader"
category: Sources
summary: LifeWiki's stub on RuleLoader, the Golly algorithm that runs rules defined in external .rule files (rule tables and rule trees) - how a rule name maps to a file, and the file's @RULE, @TABLE, @TREE, @COLORS and @ICONS sections
tags: [source, lifewiki, golly, ruleloader, rule-table, rule-format]
sources: [lifewiki-ruleloader]
created: 2026-09-25
updated: 2026-09-25
---

# LifeWiki: RuleLoader

**Source:** raw/lifewiki-ruleloader.md, saved from https://conwaylife.com/wiki/RuleLoader (reached through the redirect from "Ruletable")
**Date ingested:** 2026-09-25
**Type:** wiki article

## Summary

Describes [[ruleloader](pages/ruleloader.md)].[^1]
- RuleLoader is the Golly algorithm for .rule files, also called rule tables and rule
  trees; given rule "Foo" it looks for Foo.rule.
- A .rule file is text in sections headed @XXX: @RULE (mandatory), @TABLE, @TREE, @COLORS
  and @ICONS. Duplicate sections after the first, and unknown ones, are ignored.
- Golly's other algorithms are QuickLife, HashLife, Generations, Larger than Life and
  LifeSuper.

## Entities & Concepts

- [[ruleloader](pages/ruleloader.md)], [[generations-rule](pages/generations-rule.md)], [[larger-than-life](pages/larger-than-life.md)]

[^1]: [[lifewiki-ruleloader](pages/lifewiki-ruleloader.md)] L8-35 [synthesis] - definition, file lookup, section format, recognized sections, Golly algorithms navbox
