---
title: Sliding block register
category: Patterns
summary: A Life memory device that stores a non-negative integer as the distance of one block from a fixed point - INC pushes it out, TDEC tests for zero with a grazing glider and pulls it in only if non-zero; spacing the moves 6 cells apart and parking boats beside the path gives a binary register
tags: [pattern, life, register, memory, block, computation, apgsembly, binary-register]
sources: [cgol-ch9-universal-computation]
created: 2026-09-25
updated: 2026-09-25
---

# Sliding block register

## Description

A *register* is a memory device that holds one number. A *sliding block register* (SBR)
holds a non-negative integer n as the position of a single [[block](pages/block.md)]:
the block sits n diagonal steps from its "zero" position. In the
[[apgsembly](pages/apgsembly.md)] language these registers are named U0, U1, ..., the U
standing for *unary* (base 1, a count of steps).[^1]

**Moving the block.** Stable conduits turn one input glider into small glider salvos
borrowed from slide guns (Chapter 8).[^2]
- INC: three gliders push the block one cell diagonally farther away.
- DEC: two gliders pull it one cell closer.

**Testing for zero.** It is enough to test whether the block is at zero, since any value
can be read by repeated decrementing and testing. The test uses the (2,1) block pull: a
glider that just grazes the block.[^3]
- If the block is anywhere else, the glider passes by untouched and becomes the NZ
  (non-zero) output.
- If the block is at zero, the glider pulls it and is destroyed. A second signal split
  off from the input, suppressed only by an NZ output, then emits the Z output and sends
  a glider that pulls the block back.

**TDEC for safety.** A DEC at zero would wreck the test, because the grazing glider
would hit the block head-on. So the finished register has only two inputs: INC and
TDEC (test, then decrement). TDEC ignores the decrement when the block is at zero. No
sequence of inputs can break it. Its Z and NZ output lanes are transparent, so any
number of registers can stand side by side.[^4] TDEC reports the value from before the
decrement, and INC or TDEC take longer when the block is far away.[^5]

Sliding block registers and a finite-state machine are enough on their own to compute
anything computable.[^6]

## Binary register

A *binary register* (Bn) stores a number in base 2, so n takes Θ(log n) cells instead of
Θ(n).[^7]
- A sliding block, the *read head*, moves 6 cells per INC or TDEC instead of 1. These two
  actions alone make a sliding block register.
- Every 6 cells along its path is a bit location holding either nothing (0) or a boat
  (1).
- READ returns the bit at the read head and clears it to 0. SET writes a 1.
- SET on a bit that is already 1 destroys the register, so programs READ first.
- Its four actions come as [[slow-salvo](pages/slow-salvo.md)]s from a diagonal line of
  edge-shooting [[herschel](pages/herschel.md)] conduits.

The same idea in two dimensions, with two perpendicular sliding blocks as read heads,
is the B2D 2D printer.[^8]

## Appearances in Sources

- [[cgol-ch9-universal-computation](pages/cgol-ch9-universal-computation.md)] - §9.1.1: the sliding block register; §9.4: the binary register; §9.8: Chapman's 2002 register machine used the same idea

## Related Concepts

- [[apgsembly](pages/apgsembly.md)] - the language that programs these registers
- [[block](pages/block.md)] - the stored object
- [[memory-cell](pages/memory-cell.md)] - glider-loop memory from periodic circuitry
- [[slow-salvo](pages/slow-salvo.md)] - how binary-register moves are generated

[^1]: [[cgol-ch9-universal-computation](pages/cgol-ch9-universal-computation.md)] pp.272, 275 [synthesis] - "it will be easier for us to simply store it in the position of a single block"; "a memory device called a sliding block register (SBR)"; n.4 "The 'U' stands for the word unary"
[^2]: [[cgol-ch9-universal-computation](pages/cgol-ch9-universal-computation.md)] p.272 [synthesis] - a stable conduit turns a glider into the three gliders of Fig. 8.37(c) that push the block "diagonally away by 1 cell" (INC) and the two gliders of Fig. 8.37(b) that pull it "diagonally closer by 1 cell" (DEC)
[^3]: [[cgol-ch9-universal-computation](pages/cgol-ch9-universal-computation.md)] pp.272-273 [synthesis] - "it suffices to be able to check whether or not the block is in the 'zero' (Z) position"; the (2,1) block pull "happens when a glider just barely grazes a block"; unaffected glider is the NZ output; a second signal "suppressed by a NZ output, but otherwise produces a Z output as well as a glider that resets the sliding block" (Fig. 9.1)
[^4]: [[cgol-ch9-universal-computation](pages/cgol-ch9-universal-computation.md)] pp.273-274 [synthesis] - DEC at zero would make the TEST "fail catastrophically"; "only two inputs: INC and TEST-then-DEC, which we abbreviate as TDEC"; "no longer a way to send in a series of inputs that causes a catastrophic failure"; output lanes "transparent so that multiple registers can easily be placed side-by-side" (Fig. 9.2)
[^5]: [[cgol-ch9-universal-computation](pages/cgol-ch9-universal-computation.md)] pp.278, 282 [synthesis] - TDEC return value "based on the value that was contained in it before it was decremented"; n.19 a far-away sliding block "will take a long time to INC or TDEC"
[^6]: [[cgol-ch9-universal-computation](pages/cgol-ch9-universal-computation.md)] p.283 - "sliding block registers and the computational framework that we have introduced so far are already Turing complete - they can compute anything that can be computed"
[^7]: [[cgol-ch9-universal-computation](pages/cgol-ch9-universal-computation.md)] pp.285-286, 293 [synthesis] - "n can be stored in Θ(log(n)) space instead of Θ(n) space"; shotguns "move a block 6 cells diagonally at a time"; each bit location holds "either an empty space or a single boat"; INC, TDEC, READ, SET; n.22 the INC and TDEC portions "alone make up a sliding block register"; SET on a 1 "will cause irrecoverable damage", avoided "by always sending a READ signal just before any SET"; Fig. 9.7 slow salvos; p.293 "a long diagonal line of 26 edge shooters"
[^8]: [[cgol-ch9-universal-computation](pages/cgol-ch9-universal-computation.md)] p.301 - "The way that this 2D printer works is almost the exact same as the binary register, but with two perpendicular sliding blocks to read and write the desired bits instead of just one"
