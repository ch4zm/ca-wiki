---
title: "Conway's Game of Life: Mathematics and Construction (Johnston and Greene, 2022)"
category: Sources
summary: Nathaniel Johnston and Dave Greene's free textbook on the Game of Life, current to January 2022 - still lifes, oscillators, spaceships, glider synthesis, circuitry, guns, universal computation and construction, and Life emulating other 2D rules (the 0E0P metacell); the wiki's backbone for Life facts
tags: [source, book, life, johnston, greene, patterns, construction, circuitry]
sources: [conways-game-of-life-mathematics-and-construction]
created: 2026-09-25
updated: 2026-09-25
---

# Conway's Game of Life: Mathematics and Construction (Johnston and Greene, 2022)

**Source:** raw/johnston-greene-2022-conways-game-of-life.pdf. Johnston, N., & Greene, D. (2022). *Conway's Game of Life: Mathematics and construction*. Free PDF and pattern files at conwaylife.com/book. 494 PDF pages; printed page = PDF page - 14 in the main text.
**Date ingested:** 2026-09-25
**Type:** book

## Summary

The book introduces the Game of Life, the mathematics behind it, and the methods used to
build its most interesting patterns. Small building-block patterns in the early chapters
mostly come from computer searches, which the book does not explain; from there on it
walks through how those pieces are combined into larger constructions.[^1] It follows the
history of discoveries only because later patterns build on earlier techniques. Its stated
goal is to "demystify" Life by breaking complex patterns into pieces that can be
understood one at a time.[^1] Results are current to January 15, 2022.[^2]

The level is a first-year undergraduate: some proofs and some programming, no specialist
background. Appendix A covers the extra mathematics used: modular congruence, gcd, lcm and
Bézout's identity for oscillator periods, and big-Θ notation for growth rates.[^3] Nearly
every figure in the electronic edition links to RLE or Macrocell code that can be pasted
into simulators such as Golly, and all patterns can be viewed in a browser at the book's
website.[^4] The authors credit Golly, by Andrew Trevorrow and Tomas Rokicki, as the tool
without which many of the patterns would not have been found.[^5]

## Chapters

The wiki covers the book chapter by chapter.[^6]

| Ch. | Title | Printed pp. | Wiki page |
|---|---|---|---|
| 1 | Early Life | 3-32 | [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] |
| 2 | Still Lifes | 33-52 | [[cgol-ch2-still-lifes](pages/cgol-ch2-still-lifes.md)] |
| 3 | Oscillators | 53-82 | [[cgol-ch3-oscillators](pages/cgol-ch3-oscillators.md)] |
| 4 | Spaceships and Moving Objects | 83-120 | - |
| 5 | Glider Synthesis | 121-152 | - |
| 6 | Periodic Circuitry | 153-182 | - |
| 7 | Stable Circuitry | 183-220 | - |
| 8 | Guns and Glider Streams | 221-270 | - |
| 9 | Universal Computation | 271-310 | - |
| 10 | Self-Supporting Spaceships | 311-344 | - |
| 11 | Universal Construction | 345-384 | - |
| 12 | The 0E0P Metacell | 385-430 | - |

Appendices: A, Mathematical Miscellany; B, Extra Details (including isotropic and
non-isotropic rulestrings); C, Solutions to Selected Exercises.[^6]

## Key Takeaways

- The book is the most complete single reference on Life patterns and construction
  techniques, and it covers them from first principles.[^1]
- Figures show live cells in black and fade recently-alive cells from blue to orange,
  so motion is visible in static images.[^7]
- Chapter 12 goes past B3/S23: it covers other 2D cellular automata and a Life pattern
  that emulates them.[^6]

## Entities & Concepts

- [[game-of-life](pages/game-of-life.md)] - the subject
- [[life-like-cellular-automaton](pages/life-like-cellular-automaton.md)] - the rule family B3/S23 belongs to

## Relation to Other Wiki Pages

Each chapter page carries that chapter's content. This page holds book-level facts only.

[^1]: [[conways-game-of-life-mathematics-and-construction](pages/conways-game-of-life-mathematics-and-construction.md)] Preface, "The Goal", p.xi [synthesis] - "we provide an introduction to Conway's Game of Life, the mathematics behind it, and the methods used to construct many of its most interesting patterns"; building-block patterns "found via brute-force or other computer searches"; history followed as "a by-product"; "The goal of this book is to demystify the Game of Life"
[^2]: [[conways-game-of-life-mathematics-and-construction](pages/conways-game-of-life-mathematics-and-construction.md)] Preface, p.xi - "This book is up to date with regards to Life technology and results that were known as of January 15, 2022"
[^3]: [[conways-game-of-life-mathematics-and-construction](pages/conways-game-of-life-mathematics-and-construction.md)] Preface, "Intended Audience", pp.xi-xii [synthesis] - "aimed at the level of a first-year undergraduate university student"; gcd, lcm and Bézout's identity for oscillator periods (Appendix A.2); big-Θ notation (Appendix A.3)
[^4]: [[conways-game-of-life-mathematics-and-construction](pages/conways-game-of-life-mathematics-and-construction.md)] Preface, "How to Use", p.xiii [synthesis] - "almost every figure is actually a clickable link that will open a text file containing RLE or Macrocell code"; can be pasted into "Life simulation software like Golly"; patterns viewable on the book's website
[^5]: [[conways-game-of-life-mathematics-and-construction](pages/conways-game-of-life-mathematics-and-construction.md)] Acknowledgments, p.xiv - "Thanks to Andrew Trevorrow and Tomas Rokicki for creating the open-source cross-platform cellular automaton editor and simulator Golly ..., without which many of the patterns discussed in this book would not have been discovered"
[^6]: [[conways-game-of-life-mathematics-and-construction](pages/conways-game-of-life-mathematics-and-construction.md)] Contents, pp.v-x [synthesis] - chapter titles and starting pages; Chapter 12 §12.1 "Other 2D Cellular Automata", §12.2 "Rule Emulation"; Appendix B.6-B.7 isotropic and non-isotropic rulestrings
[^7]: [[conways-game-of-life-mathematics-and-construction](pages/conways-game-of-life-mathematics-and-construction.md)] Preface, "How to Use", p.xii [synthesis] - "alive cells in black and dead cells in white"; "a gradient from blue to orange to denote cells that were alive in past generations"
