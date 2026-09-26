---
title: "Universal Computation (Johnston and Greene, Ch. 9)"
category: Sources
summary: Chapter 9 of Conway's Game of Life - Mathematics and Construction - Adam P. Goucher's APGsembly toolkit for building programmable computers in Life - sliding block and binary registers, a finite-state-machine computer, a clock gun, adder, subtractor and times-10 components, a block-font character printer, a pi calculator, a 2D printer, and a pattern whose bounding box grows as slowly as possible
tags: [source, chapter, life, computation, apgsembly, register, universality, printer, pi]
sources: [cgol-ch9-universal-computation]
created: 2026-09-25
updated: 2026-09-25
---

# Universal Computation (Johnston and Greene, Ch. 9)

**Source:** raw/johnston-greene-2022-conways-game-of-life.pdf, Chapter 9, printed pp. 271-310 (PDF pp. 285-324). Part of [[conways-game-of-life-mathematics-and-construction](pages/conways-game-of-life-mathematics-and-construction.md)].
**Date ingested:** 2026-09-25
**Type:** book chapter

## Summary

Life has been known to be computationally universal since the early 1970s, but the
original constructions were enormous and only partly assembled. This chapter builds
explicit computer patterns that run in ordinary Life software, using a toolkit that Adam
P. Goucher developed in 2009 and 2010.[^1] A Life computer needs three things: memory
that holds bits, programs of simple instructions whose flow can depend on stored values,
and a way to store arbitrarily complex programs.[^2]

The basic memory is a [[sliding-block-register](pages/sliding-block-register.md)]: a
single [[block](pages/block.md)] whose distance from a fixed point stores a non-negative
integer, with an increment input and a test-then-decrement input that reports "zero" or
"non-zero".[^3] Programs are written in [[apgsembly](pages/apgsembly.md)], a small
language in which each line is one state of a finite-state machine, and are compiled
into a pattern with three parts: a computer that tracks the state, a stack of memory
components, and a clock gun.[^4] With sliding block registers alone the framework is
already Turing complete, meaning it can compute anything that can be computed.[^5]

The rest of the chapter adds components that make computation faster or more visible:[^6]
- binary registers, which store numbers as rows of boats;
- adder, subtractor and times-10 components that hold carry bits;
- a character printer that writes digits in a font made of blocks;
- a 2D printer that places boats anywhere in a quadrant of the plane.

Together they give a pattern that computes and prints the decimal digits of π forever,
using a streaming, integer-only algorithm from Gibbons (cited via the chapter, not read).
The same pattern can be changed to print e and other constants.[^7] A binary ruler that
counts in binary has a bounding box whose width grows like log(t). A 2D-printer version
grows like the square root of log(t), the slowest growth any unbounded pattern can
have.[^8]

## Key Takeaways

- Programmable computers exist as explicit Life patterns, and Golly can run them.[^1]
- One block plus a test-if-zero circuit is a usable unbounded counter, and counters
  like this are enough for universality.[^3][^5]
- A power-of-two clock period lets Golly's HashLife algorithm run these computers
  quickly.[^9]
- There is a slowest possible bounding-box growth rate for an unbounded pattern, and a
  Life computer reaches it.[^8]

## Entities & Concepts

- [[apgsembly](pages/apgsembly.md)], [[sliding-block-register](pages/sliding-block-register.md)]
- [[regulator](pages/regulator.md)] (the clock gun), [[slow-salvo](pages/slow-salvo.md)] (how the binary register and printer move blocks), [[herschel](pages/herschel.md)]
- [[game-of-life](pages/game-of-life.md)], [[universal-turing-machine](pages/universal-turing-machine.md)]

## History

- Conway's and Gosper's groups showed in the early 1970s that Life could in principle do
  any computation. Patterns small enough for a desktop computer came about three decades
  later.[^10]
- Paul Rendell built a Turing machine from period-30 circuitry in April 2000 and
  extended it to a universal Turing machine in February 2010.[^10]
- Paul Chapman built a register machine in 2002. It used sliding-block unary registers
  and zero/non-zero branching like APGsembly, but it sent signals with lightweight
  spaceships and ran on period-30 circuitry.[^11]
- Goucher's toolkit was completed in 2010. His original π calculator (February 2010) had
  a bounding box about 12 times larger than the book's rebuilt version, but almost the
  same function and speed. About a week earlier he built a calculator for the golden
  ratio φ that finds n digits in Θ(n³) generations, against Θ(n⁶) for π.[^12]
- Nicolas Loizeau built an 8-bit programmable computer in 2016. It cannot handle values
  above 255, but it is much simpler to program.[^12]

## Relation to Other Wiki Pages

The sliding block register reuses the block-moving salvos behind slide guns (Chapter 8)
and the (2,1) block pull from [[cgol-ch2-still-lifes](pages/cgol-ch2-still-lifes.md)].
The clock gun is a universal [[regulator](pages/regulator.md)] of the kind introduced in
[[cgol-ch6-periodic-circuitry](pages/cgol-ch6-periodic-circuitry.md)].[^3][^9] The
printers move blocks by [[slow-salvo](pages/slow-salvo.md)]s from
[[cgol-ch5-glider-synthesis](pages/cgol-ch5-glider-synthesis.md)].[^13]

[^1]: [[cgol-ch9-universal-computation](pages/cgol-ch9-universal-computation.md)] p.271 [synthesis] - Life "is computationally universal (also sometimes referred to as 'Turing complete') [Wai74, BCG82]. However, the constructions that were used to originally demonstrate this fact were monstrously large and only mostly pieced together"; n.1 toolkit "Developed by Adam P. Goucher in 2009 and 2010"
[^2]: [[cgol-ch9-universal-computation](pages/cgol-ch9-universal-computation.md)] pp.271-272 [synthesis] - three requirements: mechanisms that store information in binary, programs of simple instructions whose flow memory values can affect, and mechanisms to represent arbitrarily complex programs
[^3]: [[cgol-ch9-universal-computation](pages/cgol-ch9-universal-computation.md)] pp.272-274 [synthesis] - block position stores the integer; INC and DEC salvos from slide-gun block moves (Fig. 8.37); TEST by the (2,1) block pull of Fig. 2.20; the redesign to two inputs "INC and TEST-then-DEC, which we abbreviate as TDEC" (Fig. 9.2)
[^4]: [[cgol-ch9-universal-computation](pages/cgol-ch9-universal-computation.md)] pp.275-279 [synthesis] - finite-state machine model; APGsembly states split into Z and NZ substates; "three main parts: a computer (in the southeast), a component stack (in the northwest), and a clock gun (in the north)"
[^5]: [[cgol-ch9-universal-computation](pages/cgol-ch9-universal-computation.md)] p.283 - "sliding block registers and the computational framework that we have introduced so far are already Turing complete - they can compute anything that can be computed"
[^6]: [[cgol-ch9-universal-computation](pages/cgol-ch9-universal-computation.md)] pp.284-303 [synthesis] - §9.4 binary register and ADD, SUB, MUL components; §9.5 character printer; §9.7 B2D 2D printer; Table 9.1 summary of components
[^7]: [[cgol-ch9-universal-computation](pages/cgol-ch9-universal-computation.md)] pp.296-301 [synthesis] - §9.6 π calculator; algorithm "originally developed in [Gib06]", integer-only and "streaming"; Fig. 9.15; §9.6.1 the same method for any series of form (9.4), including e
[^8]: [[cgol-ch9-universal-computation](pages/cgol-ch9-universal-computation.md)] pp.288, 304-306 [synthesis] - binary ruler diameter "Θ(log(t))" (Fig. 9.8); counting argument that an infinitely growing pattern's bounding box can be no smaller than √log2(t) × √log2(t); APGsembly 9.10 and Fig. 9.17 attain diameter Θ(√log(t)), "the smallest unbounded diametric growth rate possible"
[^9]: [[cgol-ch9-universal-computation](pages/cgol-ch9-universal-computation.md)] p.281 - "if we choose the universal regulator to align to some high power-of-two period, then Golly's HashLife algorithm is able to evolve these patterns extremely quickly"
[^10]: [[cgol-ch9-universal-computation](pages/cgol-ch9-universal-computation.md)] pp.306-307 [synthesis] - early-1970s theoretical universality [Wai74, BCG82]; "it wasn't until almost three decades later" that desktop-sized universal computers existed; "Paul Rendell developed the first such device in April 2000 [Ren16] - a Turing machine based on period 30 circuitry"; extended to a universal Turing machine in February 2010
[^11]: [[cgol-ch9-universal-computation](pages/cgol-ch9-universal-computation.md)] pp.307-308 [synthesis] - "Paul Chapman constructed the next universal computer in 2002 - a register machine"; sliding-block unary registers, zero/non-zero branching; "it used lightweight spaceships to transmit information instead of gliders, it made use of period 30 circuitry instead of stable circuitry"
[^12]: [[cgol-ch9-universal-computation](pages/cgol-ch9-universal-computation.md)] p.308 [synthesis] - toolkit "completed by Adam P. Goucher in 2010"; Loizeau's 8-bit programmable computer (2016) "cannot compute quantities larger than 2^8 − 1 = 255" but "is significantly simpler to program"; original π calculator (February 2010) "roughly 12 times as large"; φ calculator a week earlier, Θ(n³) vs Θ(n⁶) generations
[^13]: [[cgol-ch9-universal-computation](pages/cgol-ch9-universal-computation.md)] p.293 [synthesis] - the printer moves and positions blocks "via slow salvos like the ones that we introduced back in Section 5.7", generated by edge-shooting Herschel conduits, "the same technique that we used to construct the binary register"
