---
title: "Periodic Circuitry (Johnston and Greene, Ch. 6)"
category: Sources
summary: Chapter 6 of Conway's Game of Life - Mathematics and Construction - oscillator-based glider circuitry at periods 30 and 46 - reflectors, inverters, duplicators, toggles, a prime-number gun, ticker tapes and memory cells, Heisenburps that copy gliders without touching them, bumpers and bouncers, and a universal regulator that aligns gliders of any timing
tags: [source, chapter, life, circuitry, inverter, primer, memory-cell, heisenburp, regulator, reflector]
sources: [cgol-ch6-periodic-circuitry]
created: 2026-09-25
updated: 2026-09-25
---

# Periodic Circuitry (Johnston and Greene, Ch. 6)

**Source:** raw/johnston-greene-2022-conways-game-of-life.pdf, Chapter 6, printed pp. 153-182 (PDF pp. 167-196). Part of [[conways-game-of-life-mathematics-and-construction](pages/conways-game-of-life-mathematics-and-construction.md)].
**Date ingested:** 2026-09-25
**Type:** book chapter

## Summary

Large Life patterns are designed in two steps: first a *schematic* of where gliders
should go, then the components that make them go there.[^1] This chapter supplies
components built from oscillators. They are smaller than still-life circuitry, but
everything connected must share a period.[^2] Period-30 circuitry grows out of the
[[queen-bee](pages/queen-bee.md)] shuttle and [[gosper-glider-gun](pages/gosper-glider-gun.md)]:
pentadecathlon reflectors, glider pushers, glider-to-LWSS converters and toggles. Its
[[inverter](pages/inverter.md)]s, which swap gliders and gaps in a stream, give
duplicators and guns of any period 120n.[^3] That kit is enough to build a
[[primer](pages/primer.md)], a gun whose lightweight spaceships appear exactly at the
prime positions.[^4]

Period-46 circuitry grows out of the [[twin-bees](pages/twin-bees.md)] shuttle and
Tanner's p46. It adds reflections that merge streams into period 23, small LWSS, MWSS
and HWSS guns, edge-shooting guns, and loops that store and replay bit patterns: ticker
tapes and [[memory-cell](pages/memory-cell.md)]s.[^5] A [[heisenburp](pages/heisenburp.md)]
copies a passing glider without touching it.[^6] Spark-based [[reflector](pages/reflector.md)]s,
the bumper and bouncer, work with low-period oscillators.[^7] A [[regulator](pages/regulator.md)]
takes a glider of unknown timing and emits one aligned to a chosen period.[^8]

## Key Takeaways

- Periodic circuits are compact but tie a whole mechanism to one period (or its
  multiples).[^2]
- Inverters plus a loop give glider streams of arbitrary length and guns of arbitrary
  period.[^3]
- A Life pattern can compute and output the primes.[^4]
- Detection need not disturb what is detected: Heisenburps copy gliders untouched.[^6]

## Entities & Concepts

- [[inverter](pages/inverter.md)], [[primer](pages/primer.md)], [[memory-cell](pages/memory-cell.md)], [[heisenburp](pages/heisenburp.md)], [[regulator](pages/regulator.md)]
- [[reflector](pages/reflector.md)], [[gosper-glider-gun](pages/gosper-glider-gun.md)], [[twin-bees](pages/twin-bees.md)], [[queen-bee](pages/queen-bee.md)], [[pentadecathlon](pages/pentadecathlon.md)], [[breeder](pages/breeder.md)]

## Relation to Other Wiki Pages

The primer needs the [[breeder](pages/breeder.md)] of
[[cgol-ch5-glider-synthesis](pages/cgol-ch5-glider-synthesis.md)] to lay ever-longer
guns, and the regulator reuses the boat-bit from
[[cgol-ch2-still-lifes](pages/cgol-ch2-still-lifes.md)].[^4][^8]

[^1]: [[cgol-ch6-periodic-circuitry](pages/cgol-ch6-periodic-circuitry.md)] p.153 [synthesis] - "we typically construct large patterns that do unusual things via a two-step process": design a schematic, then "fill in the details"
[^2]: [[cgol-ch6-periodic-circuitry](pages/cgol-ch6-periodic-circuitry.md)] p.154 - periodic circuitry "is typically smaller and simpler than stationary circuitry ... However, it has the disadvantage that it can be difficult or impossible to make circuitry based on different periods work together"
[^3]: [[cgol-ch6-periodic-circuitry](pages/cgol-ch6-periodic-circuitry.md)] §6.1, pp.154-159 [synthesis] - pentadecathlon reflectors, inverters, inline inverter, guns of period 120n, stream inverter, glider duplicator, glider pusher, glider-LWSS conversions, toggle
[^4]: [[cgol-ch6-periodic-circuitry](pages/cgol-ch6-periodic-circuitry.md)] §6.2, pp.159-163 [synthesis] - primer construction
[^5]: [[cgol-ch6-periodic-circuitry](pages/cgol-ch6-periodic-circuitry.md)] §6.3, pp.163-168 [synthesis] - twin bees reflections and conversions, p23 gun, LWSS and MWSS guns, ticker tapes and memory cells, Tanner's p46 edge shooter and MWSS gun, HWSS gun
[^6]: [[cgol-ch6-periodic-circuitry](pages/cgol-ch6-periodic-circuitry.md)] §6.3.3, pp.168-171 [synthesis] - Heisenburps
[^7]: [[cgol-ch6-periodic-circuitry](pages/cgol-ch6-periodic-circuitry.md)] §6.4, pp.171-172 [synthesis] - bumpers and bouncers
[^8]: [[cgol-ch6-periodic-circuitry](pages/cgol-ch6-periodic-circuitry.md)] §6.5, pp.172-175 [synthesis] - regulators; a universal regulator built on the boat bit
