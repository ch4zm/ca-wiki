---
title: Collatz Function
category: Concepts
summary: The 3x+1 map (3x+1 on odd x, x/2 on even x) and its open conjecture that every orbit reaches 1; tiny Turing machines that iterate it make questions about machines of their size at least as hard as the conjecture
tags: [concept, collatz, 3x+1, turing-machines, undecidability]
sources: [aucm-ch5-small-universal-turing-machines]
created: 2026-09-24
updated: 2026-09-24
---

# Collatz Function

## Description

The Collatz function is[^1]

f(x) = 3x + 1 if x is odd, x/2 if x is even.

The **Collatz conjecture** says that for every x ∈ ℕ there is an n with fⁿ(x) = 1. It is
conjectured true and has resisted every attempt at a proof.[^2]

**As a hardness yardstick for small machines.** The sizes of Turing machines between the
smallest known universal ones and the largest known decidable ones form an open gap
([[universal-turing-machine](pages/universal-turing-machine.md)]). Margenstern built
machines inside that gap, with (states, symbols) = (11, 2), (5, 3), (4, 4), (3, 6) and
(2, 10), that iterate f. Baiocchi later reduced some of the sizes. For any machine at least
that large, a reachability question becomes at least as hard as the conjecture: decide,
given the machine, a start configuration and a target configuration, whether the target is
reached.[^3] A machine that can iterate f needs no universality to be hard to analyse
(own reasoning).

**Encoding and speed.** Machines that write x in unary take O(x) time per iteration.
Margenstern's (11, 2) and (5, 3) machines write x in binary and take O(log x).[^4]

## Appearances in Sources

- [[aucm-ch5-small-universal-turing-machines](pages/aucm-ch5-small-universal-turing-machines.md)] - the function, Margenstern's and Baiocchi's Collatz machines, the hardness consequence

## Related Concepts

- [[universal-turing-machine](pages/universal-turing-machine.md)] - the open gap in universal program size where the Collatz machines sit
- [[tag-system](pages/tag-system.md)] - another simple iterated system simulated by small machines

[^1]: [[aucm-ch5-small-universal-turing-machines](pages/aucm-ch5-small-universal-turing-machines.md)] p.119 (Eq. 5.1) — "f(x) = 3x + 1 if x = 1 mod 2, x/2 if x = 0 mod 2."
[^2]: [[aucm-ch5-small-universal-turing-machines](pages/aucm-ch5-small-universal-turing-machines.md)] p.119 — "for each x ∈ N is there an n such that f^n(x) = 1? The answer is conjectured to be yes. The question has drawn the interest of many authors and has resisted all attempts at a solution"
[^3]: [[aucm-ch5-small-universal-turing-machines](pages/aucm-ch5-small-universal-turing-machines.md)] pp.119-120 [synthesis] — Margenstern's (11, 2), (5, 3), (4, 4), (3, 6), (2, 10) Collatz simulators inside the gap between the universal and non-universal curves; Baiocchi's (10, 2), (5, 3), (4, 4), (3, 5), (2, 8); deciding whether a machine of at least that size reaches a target configuration "is at least as difficult as solving the Collatz conjecture"
[^4]: [[aucm-ch5-small-universal-turing-machines](pages/aucm-ch5-small-universal-turing-machines.md)] p.120 [synthesis] — unary encodings simulate an iteration in time O(x); Margenstern's (11, 2) and (5, 3) machines use a binary encoding and take O(log x)
