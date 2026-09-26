---
title: Breeder
category: Patterns
summary: A Life pattern whose population grows quadratically - rakes that synthesize guns, each of which then fires gliders; the standard example uses twelve p60 space rakes to build a Gosper glider gun every 60 generations, filling an expanding triangle with gliders
tags: [pattern-class, life, breeder, quadratic-growth, rake, gosper-glider-gun, glider-synthesis]
sources: [cgol-ch5-glider-synthesis]
created: 2026-09-25
updated: 2026-09-25
---

# Breeder

## Description

A *breeder* is an object that grows quadratically. Guns and rakes grow linearly, filling
a strip of the plane; a breeder fills an ever-expanding region.[^1] The standard idea:
rakes build guns at a linear rate, and each gun then makes gliders at a linear rate.[^1]

**A Gosper-gun breeder.** Johnston and Greene build one from the incremental synthesis of
the [[gosper-glider-gun](pages/gosper-glider-gun.md)] ([[object-synthesis](pages/object-synthesis.md)]):[^2]
- Period-20 space rakes place objects only 10 cells apart, too close for Gosper guns, so
  period-60 space rakes are used, placing guns 30 cells apart ([[puffer](pages/puffer.md)]).
- Four rakes make two lines of ponds, four more add the blocks, two turn the ponds into
  ships, and two turn the ships into queen bees, completing each gun. That is twelve
  rakes in all.
- The pattern starts with 2,038 cells. Every 60 generations it adds a 44-cell gun, and
  each gun adds two 5-cell gliders per 60 generations, so the population at generation
  60n is 5n² + 44n + 2038.
- It is deliberately unoptimized. The rakes can sit much closer together, and clever use
  of rake debris halves them to six.

Bill Gosper built the first breeder in the early 1970s on the same plan, using a
different puffer in place of the space rakes.[^3]

## Appearances in Sources

- [[cgol-ch5-glider-synthesis](pages/cgol-ch5-glider-synthesis.md)] - §5.6: construction, population formula, history

## Related Concepts

- [[gosper-glider-gun](pages/gosper-glider-gun.md)] - what it builds
- [[puffer](pages/puffer.md)] - the rakes it is built from
- [[object-synthesis](pages/object-synthesis.md)] - the method underneath

[^1]: [[cgol-ch5-glider-synthesis](pages/cgol-ch5-glider-synthesis.md)] p.134 - "our first breeder: an object that grows quadratically (as opposed to objects like guns or rakes, which grow linearly)"; "Since the rakes will create Gosper glider guns at a linear rate, and the Gosper glider guns will then each create gliders at a linear rate, the overall growth of our pattern will be quadratic"
[^2]: [[cgol-ch5-glider-synthesis](pages/cgol-ch5-glider-synthesis.md)] pp.134-135 [synthesis] - period 20 rakes "can only be used to construct objects that are 10 cells apart"; p60 rakes give guns "30 cells apart"; four rakes for ponds, four for blocks, two for ships, two for queen bees (Fig. 5.18); "a population of 2038 cells"; "5n² + 44n + 2038"; "halving the total number of space rakes from 12 to 6"
[^3]: [[cgol-ch5-glider-synthesis](pages/cgol-ch5-glider-synthesis.md)] p.135, n.7 - "The first breeder was found by Bill Gosper in the early 1970s. It used the exact same ideas that we used in the construction of our breeder, but used a different puffer in place of the space rakes"
