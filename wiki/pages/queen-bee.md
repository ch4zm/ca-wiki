---
title: Queen bee
category: Patterns
summary: A common unstable Life object that reflects itself every 15 generations, leaving a beehive each time; blocks that eat the beehives turn it into the period-30 queen bee shuttle, and two queen bees make the Gosper glider gun
tags: [pattern, life, queen-bee, shuttle, period-30, engineered]
sources: [cgol-ch1-early-life]
created: 2026-09-25
updated: 2026-09-25
---

# Queen bee

## Description

The queen bee is a commonly occurring unstable object. Every 15 generations it reflects
itself and leaves a [[beehive](pages/beehive.md)] behind. After 30 generations it is back
where it started with a beehive on each side, and shortly after it collides with the first
one and destroys itself.[^1]

**Queen bee shuttle.** A [[block](pages/block.md)] placed next to a beehive destroys the
beehive in 7 generations and survives unharmed; the block *eats* the beehive. Putting a
block at each end of the queen bee's path gives the **queen bee shuttle**, a period-30
[[oscillator](pages/oscillator.md)]: the queen bee bounces between the blocks, and each
beehive it drops is eaten before it can interfere.[^2] A *shuttle* is an oscillator in
which an unstable object moves back and forth between stabilizing objects.[^3] The queen
bee shuttle is the book's first *engineered* object, built by combining observed
reactions, which is how most Life discoveries are now made.[^4] Objects other than blocks
can also stabilize it.[^5]

**Two queen bees.** Two carefully timed queen bees bounce off each other, and their
collision makes a [[glider](pages/glider.md)] in place of beehives. Adding stabilizing
blocks on the outer sides gives the [[gosper-glider-gun](pages/gosper-glider-gun.md)].[^6]

## Appearances in Sources

- [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] - §1.3: the queen bee, the block-eats-beehive reaction, the shuttle, the gun

## Related Concepts

- [[gosper-glider-gun](pages/gosper-glider-gun.md)] - two queen bees and two blocks
- [[twin-bees](pages/twin-bees.md)] - the period-46 analogue
- [[beehive](pages/beehive.md)] - what it leaves behind
- [[oscillator](pages/oscillator.md)] - the shuttle's class

[^1]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.10 - "the queen bee, which is a commonly occurring object that reflects itself after 15 generations, but leaves behind a beehive in the process. It follows that after 30 generations, the queen bee is back where it started, but with an additional beehive on either side of it"; "Shortly after 30 generations, the queen bee collides with the first beehive that it created, resulting in its self-destruction"
[^2]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.10-11 [synthesis] - "a block being placed next to a beehive results in the beehive being destroyed and the block surviving unharmed (we thus say that the block eats the beehive)"; Fig. 1.16: destroys the beehive in 7 generations; "This period 30 oscillator is called the queen bee shuttle"
[^3]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.11, n.8 - "The term 'shuttle' typically refers to oscillators in which an unstable object moves back and forth between stabilizing objects"
[^4]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.11 - "The queen bee shuttle is our first example of an engineered object--a pattern that we didn't discover 'naturally', but rather one that we specifically constructed by piecing together simpler reactions that we had observed. This is how most recent discoveries in the Game of Life have been made"
[^5]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.11 - "The queen bee can also be stabilized by some objects other than blocks"
[^6]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.11 - "If lined up and timed just right, the queen bees bounce off of each other, and instead of each producing a beehive, their collision produces a glider"
