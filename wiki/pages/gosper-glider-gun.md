---
title: Gosper glider gun
category: Patterns
summary: The period-30 Life gun made of two queen bees bouncing between two blocks, emitting a glider every 30 generations; found by Bill Gosper in November 1970, it was the first pattern found to grow without limit
tags: [pattern, life, gun, glider-gun, period-30, gosper, infinite-growth]
sources: [cgol-ch1-early-life, fantastic-combinations-of-john-conways-life, theory-of-cellular-automata-a-survey]
created: 2026-09-25
updated: 2026-09-25
---

# Gosper glider gun

## Description

A *glider gun* is a pattern that creates an endless stream of
[[glider](pages/glider.md)]s. The Gosper glider gun is two
[[queen-bee](pages/queen-bee.md)]s bouncing back and forth between two
[[block](pages/block.md)]s. Their collisions produce a glider in place of the beehives
a lone queen bee would leave, so the pattern oscillates with period 30 and fires a glider
every cycle.[^1] Kari's survey uses a period-30 glider gun as its example of the class.[^2]

**Unbounded growth.** The gun was the first pattern ever found that grows without limit.[^1]
Conway had conjectured that no finite pattern could, offered $50 for a proof or
disproof, and named a gun as one way to disprove it.[^3] Bill Gosper found the gun in
November 1970 and received the $50 from Conway.[^4]

Three queen bees and two blocks can make a "double" gun that emits two glider
streams.[^5]

## Appearances in Sources

- [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] - §1.3: construction, first infinitely growing pattern, discovery and prize
- [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] - the growth conjecture and prize the gun settled
- [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] - §2.6: period-30 glider gun as the example gun

## Related Concepts

- [[queen-bee](pages/queen-bee.md)] - its moving parts
- [[twin-bees](pages/twin-bees.md)] - the period-46 gun built the same way
- [[switch-engine](pages/switch-engine.md)] - puffers, the other kind of infinite growth
- [[glider](pages/glider.md)] - what it emits

[^1]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.11 [synthesis] - two queen bees and stabilizing blocks give "a pattern that oscillates at period 30, but also creates an endless stream of gliders"; "Patterns that create glider streams are called glider guns, and this particular one is called the Gosper glider gun"; "This is the first pattern that we have seen that grows indefinitely (and indeed, it was the first such pattern ever to be discovered)"
[^2]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.10-11 [synthesis] - glider gun defined as periodic and emitting gliders each period; Fig. 5: a period 30 glider gun
[^3]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.3 [synthesis] - "Conway conjectures that no pattern can grow without limit"; $50 prize; a "gun" (a configuration that repeatedly shoots out moving objects such as the glider) would disprove it
[^4]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.11, nn.9-10 - "Named after Bill Gosper, who found it in November 1970"; "this glider gun's discovery earned Gosper a $50 reward from Conway himself"
[^5]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.29, Ex. 1.6 - "Use two blocks and three queen bees to create a 'double' Gosper glider gun: a gun that emits two streams of gliders"
