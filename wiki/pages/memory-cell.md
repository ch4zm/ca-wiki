---
title: Memory cell
category: Patterns
summary: A glider loop fitted with a duplicator, so it replays a stored bit pattern forever as a spaceship stream, and with deletion and inverted-segment insertion points so bits can be rewritten; stacked loops make ticker-tape guns that print images
tags: [pattern, life, memory, glider-loop, ticker-tape, circuitry, computation]
sources: [cgol-ch9-universal-computation, cgol-ch6-periodic-circuitry]
created: 2026-09-25
updated: 2026-09-26
---

# Memory cell

## Description

**Replaying a bit pattern.** Attach a glider duplicator to a glider loop, and the loop's
arrangement of gliders and gaps is copied out forever as an irregular stream. A glider
means "1" and a gap "0". A twin-bees-shuttle reflector that also duplicates does this at
period 46. Johnston and Greene's example loop replays 100111000011111000000, converted to
lightweight spaceships so it is easy to see.[^1]

**Ticker tapes.** Treat each output ship as a pixel. Stack n such loop guns, each
holding one row of an image in its m gliders, and the result prints an n × m picture over
and over. One example spells "HI!" in 8 × 21 ships. Alan Hensel built the first ticker
tape in 1994; an adapted one printing the Golly logo was
made for the Golly home page.[^2]

**Writable memory.** To be real memory the loop must be editable.[^3]
- *Deleting* a bit: fire a glider from outside to collide with one in the loop.
- *Inserting* a bit: place two stream inverters on the loop ([[inverter](pages/inverter.md)]).
  Deleting a glider on the inverted stretch then adds one to the loop proper.
- Johnston and Greene's example is a period 12 × 46 = 552 memory cell holding a 12-bit
  string, with separate inputs for clearing and setting bits.

Loops like this serve as storage for the computers built in Life.[^3] The programmable computers of Johnston and Greene's Chapter 9 use a different,
unbounded memory: a block whose position stores a number ([[sliding-block-register](pages/sliding-block-register.md)]),
or rows of boats read by a sliding block (a binary register).[^4]

## Appearances in Sources

- [[cgol-ch9-universal-computation](pages/cgol-ch9-universal-computation.md)] - sliding-block and binary registers
- [[cgol-ch6-periodic-circuitry](pages/cgol-ch6-periodic-circuitry.md)] - §6.3.1: ticker tapes and memory cells

## Related Concepts

- [[sliding-block-register](pages/sliding-block-register.md)] - unbounded memory for Life computers
- [[apgsembly](pages/apgsembly.md)] - programs the Chapter 9 computers that use sliding block and boat registers
- [[inverter](pages/inverter.md)] - makes insertion possible
- [[reflector](pages/reflector.md)] - glider loops are built from reflectors
- [[twin-bees](pages/twin-bees.md)] - the p46 duplicating reflector

[^1]: [[cgol-ch6-periodic-circuitry](pages/cgol-ch6-periodic-circuitry.md)] pp.165-166 [synthesis] - Fig. 6.25 "A twin bees shuttle reflecting and duplicating a glider"; attaching a duplicator to a glider loop produces "any (finite) irregular sequence of gliders of our choosing"; Fig. 6.26 bitstring 100111000011111000000 via glider-to-LWSS conversion
[^2]: [[cgol-ch6-periodic-circuitry](pages/cgol-ch6-periodic-circuitry.md)] pp.165-166 [synthesis] - "ticker tape guns, which emit any visual message of our choosing"; "n of the guns with m gliders each in the loops to create an n × m image"; Fig. 6.27 "HI!" in an 8 × 21 array; n.13 Alan Hensel's first ticker tape (June 1994), adapted by Brice Due and Dave Greene for the Golly logo on the Golly homepage
[^3]: [[cgol-ch6-periodic-circuitry](pages/cgol-ch6-periodic-circuitry.md)] pp.166-167 [synthesis] - loops "can serve as pieces of memory for the computer"; deletion by colliding a glider; insertion by placing "two stream inverters along the loop"; Fig. 6.28 "A period 12 × 46 = 552 memory cell for which the 12-bit string '111010111011' is encoded"
[^4]: [[cgol-ch9-universal-computation](pages/cgol-ch9-universal-computation.md)] pp.272,285 [synthesis] - integer stored "in the position of a single block"; binary register bit locations hold "either an empty space or a single boat"
