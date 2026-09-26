---
title: APGsembly
category: Concepts
summary: Adam P. Goucher's assembly-like language for programmable Life computers - each state has a zero and a non-zero line listing actions and a next state; code compiles into a pattern of a finite-state-machine computer, a component stack of registers, arithmetic units and printers, and a power-of-two clock gun; used for the pi calculator
tags: [concept, life, computation, apgsembly, register-machine, finite-state-machine, compiler, pi]
sources: [cgol-ch9-universal-computation]
created: 2026-09-25
updated: 2026-09-25
---

# APGsembly

## Description

*APGsembly* is a programming language for computers built as Life patterns. The name
combines "assembly" (low-level machine code) with the initials of its author, Adam P.
Goucher, who used it to build the original Life π calculator in 2010.[^1] Code is designed
to compile straightforwardly into a Life pattern.[^2]

**Model: a finite-state machine with counters.** A *finite-state machine* is a computer
that is always in one of finitely many states and changes state based on its inputs. In
Life this is a single glider that sits on one of n parallel "state" lanes at each clock
tick.[^3] Memory lives outside the machine, in registers. A register is a storage device
for one number. The basic one is the [[sliding-block-register](pages/sliding-block-register.md)],
named Un, which stores a non-negative integer. Every action that returns a value returns
one bit: Z (zero) or NZ (non-zero).[^4]

**How code is written.**[^5]
- Each line has four fields separated by semicolons: state ID, input (Z or NZ), next
  state ID, and a comma-separated list of actions.
- Each state is a pair of lines, one for each possible return value from the previous
  step. The pair acts as an implicit "if", so the language has no explicit conditionals.
- Every line names its next state. Execution never falls through to the following
  line.
- The first state is always `INITIAL`, which is assumed to receive Z. A state that can
  only be reached by Z is written `ZZ`, and `*` means "either".
- A header line `#COMPONENTS` lists the components used, and `#REGISTERS` sets starting
  values.

For example, adding U0 into U1 takes three lines:[^6]

```
INITIAL; ZZ; ID1; TDEC U0
ID1;     Z;  ID1; HALT_OUT
ID1;     NZ; ID1; TDEC U0, INC U1
```

**Rules for actions.**[^7]
- All actions on one line happen at the same moment, so actions whose order matters go
  in separate states.
- An action may not appear twice on one line, and one line should not send two actions
  to the same component.
- Exactly one action per line must return a value. `NOP` ("no operation") returns Z and
  does nothing, so it pads lines whose other actions return nothing. `HALT_OUT` is the
  one exception: it stops the computer and emits a glider.
- TDEC reports the value *before* decrementing, so a register going from 1 to 0 returns
  NZ. Loops that count a register down therefore need one extra TDEC.

## The compiled pattern

A compiled APGsembly pattern has three parts.[^8]
- **Computer.** Each state is a pair of demultiplexers holding boats. The incoming Z or
  NZ glider is turned onto the lane for that line. Along the lane, *splitters* (glider
  duplicators) send one glider to each action. At the end, a transparent reflector (a
  *merge circuit*) implements the jump by setting up the next state's demultiplexers.
- **Component stack.** All memory and output devices sit in a row, each triggered by a
  glider on one of its action lanes. Exactly one component answers with a Z or NZ glider.
- **Clock gun.** A universal [[regulator](pages/regulator.md)] fed by a period-2^20 gun
  holds the answer glider back until the computer is ready. Its period is the clock
  speed, and one period is one clock tick. A power-of-two period lets Golly's HashLife
  algorithm run the pattern very fast.

The regulator lets a glider through only when a boat, made from the incoming signal by a
syringe and a Herschel-to-boat factory, suppresses one glider of a split gun stream. The
gun multiplies a p256 gun's period with six quadri-Snarks. Louis-François Handfield
built the regulator in April 2020.[^9]

## Components

The standard components are these:[^10]
- **Un**, sliding block register: `INC Un`, `TDEC Un`.
- **Bn**, binary register: `INC Bn` and `TDEC Bn` move a read head. `READ Bn` returns the
  bit there and clears it. `SET Bn` writes a 1, and it breaks the register if the bit is
  already 1.
- **ADD**, **SUB**: fed one bit pair at a time from the low end (`ADD A1`, then `ADD B0`
  or `ADD B1`). They store the carry or borrow bit and return the result bit.
- **MUL**: stores four carry bits so a binary register can be multiplied by 10 one bit
  at a time (`MUL 0`, `MUL 1`).
- **OUTPUT**: prints a digit 0-9 or "." in a font made of blocks.
- **B2D**: a 2D binary register (a 2D printer) with separate x and y read heads, writing
  boats on a diagonal grid 16 full diagonals apart. It is slow enough to need a clock
  period of at least 2^22.
- **NOP** and **HALT_OUT**, described above.

Registers can be used in any number. Every other component appears at most once per
pattern.[^11]

**The character printer.** A *row printer* either pushes a cursor block 32 full
diagonals along, or places a pixel block beside it and then pushes. Stacking one row
printer per pixel of height gives a printer for any character set. The book's example
prints "ABRACADABRA" in an 8-pixel-high font.[^12]

## Programs

- **Arithmetic on unary registers.** Multiplication is repeated addition with a
  temporary register, and division is repeated subtraction.[^13]
- **Binary arithmetic.** The ADD and SUB components walk two binary registers bit by
  bit. A sliding block register records an upper bound on the bit length, since a
  binary register cannot tell where its highest 1 is.[^14]
- **Binary ruler.** Counting up in a binary register gives a pattern whose width grows
  like log(t).[^15]
- **π calculator.** The algorithm keeps a product of 2 × 2 integer matrices. Each step
  multiplies in one more matrix, adding a term of a series for π. Every four steps it
  pulls out one more decimal digit by repeated subtraction and multiplication by 10.
  Small quantities are kept in unary registers and the growing matrix entries in binary
  registers. The finished pattern uses 10 sliding block registers, 4 binary registers,
  ADD, SUB, MUL and a printer. By generation 8.3 × 10^13 it has printed 3.1415926535897.[^16]
- **Other constants.** Changing a few lines turns the π calculator into one for e, √2,
  or any constant given by a series of the same general form.[^17]
- **2D printing.** A walk driven by counting in base 4 prints approximations to an
  8-pointed Koch snowflake. Michael Simkin wrote the code in 2019.[^18]
- **Slowest-growing pattern.** A counter that writes its bits in a growing triangle with
  the B2D has a bounding box of width Θ(√log t). No unbounded pattern can grow more
  slowly, because a pattern confined to an n × n box must repeat within 2^(n²)
  generations.[^19]

## Appearances in Sources

- [[cgol-ch9-universal-computation](pages/cgol-ch9-universal-computation.md)] - §9.1-9.7: the language, compiler output, components and example programs

## Related Concepts

- [[sliding-block-register](pages/sliding-block-register.md)] - the basic memory, and the binary register built on it
- [[regulator](pages/regulator.md)] - the clock gun
- [[universal-turing-machine](pages/universal-turing-machine.md)] - the universality these machines share
- [[game-of-life](pages/game-of-life.md)] - the rule they run in
- [[primer](pages/primer.md)] - an earlier Life pattern that computes, without a program

[^1]: [[cgol-ch9-universal-computation](pages/cgol-ch9-universal-computation.md)] p.276, n.6 - "The name 'APGsembly' is a play on the word 'assembly' (low-level code for programming computer instructions) and the initials of its author, Adam P. Goucher. Indeed, APGsembly was used by Goucher to construct the original π calculator in 2010"
[^2]: [[cgol-ch9-universal-computation](pages/cgol-ch9-universal-computation.md)] p.278 - "APGsembly code is specifically designed so that it can straightforwardly be compiled into a Life pattern"
[^3]: [[cgol-ch9-universal-computation](pages/cgol-ch9-universal-computation.md)] p.275 - "a finite-state machine is a model of computation in which the computer can be in one of a finite number of states at any given time ... a Life pattern that has a single glider traversing a set of n parallel lanes"
[^4]: [[cgol-ch9-universal-computation](pages/cgol-ch9-universal-computation.md)] pp.274-275 [synthesis] - register with "two simple inputs (INC and TDEC) and two simple outputs (Z and NZ)"; n.4 "The 'U' stands for the word unary"
[^5]: [[cgol-ch9-universal-computation](pages/cgol-ch9-universal-computation.md)] pp.275-278 [synthesis] - a jump at the end of every line; Z and NZ substates; "Each line contains four items, separated by semicolons"; INITIAL, ZZ, * (n.9), # comments; #COMPONENTS and #REGISTERS headers
[^6]: [[cgol-ch9-universal-computation](pages/cgol-ch9-universal-computation.md)] p.278 [synthesis] - APGsembly 9.2, "add the value of U0 to U1, and zero out U0" (header lines omitted here)
[^7]: [[cgol-ch9-universal-computation](pages/cgol-ch9-universal-computation.md)] pp.277-278, 287 [synthesis] - "all actions on a particular line of APGsembly code are performed simultaneously"; no repeated action on a line; "each line of APGsembly must contain exactly one action that produces a return value"; HALT_OUT "stops the computer" and emits a glider (n.12 exception); TDEC "giving a Z or NZ return value that is based on the value that was contained in it before it was decremented"; NOP "short for 'No OPeration'"
[^8]: [[cgol-ch9-universal-computation](pages/cgol-ch9-universal-computation.md)] pp.279-282 [synthesis] - states "represented by a pair of demultiplexers that have a boat"; splitters; "a merge circuit - a reflector that is transparent to signals passing through it"; component stack; clock gun "determines the speed at which the pattern computes"; period 2^20; HashLife and power-of-two periods (p.281)
[^9]: [[cgol-ch9-universal-computation](pages/cgol-ch9-universal-computation.md)] pp.281-282 [synthesis] - the input glider "is fed into a syringe and then one of the Herschel-to-boat factories"; "The resulting boat suppresses a single glider from the gun's duplicated stream"; Fig. 9.5 "6 quadri-Snarks ... to repeatedly quadruple the period of a p256 machine gun"; n.18 "Constructed by Louis-François Handfield in April 2020"
[^10]: [[cgol-ch9-universal-computation](pages/cgol-ch9-universal-computation.md)] pp.286-303 [synthesis] - binary register actions (p.286); ADD, SUB (pp.289-291); MUL "stores four carry bits" (p.291); B2D boats "with a separation of 16 full diagonals" and clock gun "with period at least 2^22" (pp.301-302); Table 9.1 (p.303)
[^11]: [[cgol-ch9-universal-computation](pages/cgol-ch9-universal-computation.md)] p.289, n.26 - "every component that we see from this point on is limited to just a single copy per Life pattern - the sliding block and binary registers are the only components that we can use multiple copies of"
[^12]: [[cgol-ch9-universal-computation](pages/cgol-ch9-universal-computation.md)] pp.293-295 [synthesis] - Fig. 9.12 pixel salvo and 14-glider salvo pushing the cursor "32 full diagonals"; Fig. 9.13 row printer; one row printer per pixel of height; Fig. 9.14 "ABRACADABRA", font "8 pixels (blocks) high"
[^13]: [[cgol-ch9-universal-computation](pages/cgol-ch9-universal-computation.md)] pp.282-283 [synthesis] - APGsembly 9.3 multiplication via temporary register U3; division by repeated subtraction
[^14]: [[cgol-ch9-universal-computation](pages/cgol-ch9-universal-computation.md)] pp.289-291 [synthesis] - bitwise addition from the least significant bit; "we need to make use of a helper sliding block register that tells us (an upper bound of) how many bits the binary registers are making use of"; APGsembly 9.6
[^15]: [[cgol-ch9-universal-computation](pages/cgol-ch9-universal-computation.md)] pp.287-288 [synthesis] - APGsembly 9.5 binary ruler; "its diameter ... in generation t is Θ(log(t))"
[^16]: [[cgol-ch9-universal-computation](pages/cgol-ch9-universal-computation.md)] pp.296-300 [synthesis] - matrices A_k and products B_n = B_(n-1) A_n; q_n/r_n approximations; "q4n/r4n based on B4n" per digit; digit extraction by subtraction and multiplying by 10; unary vs binary registers; Fig. 9.15 "10 sliding block registers, 4 binary registers, and one each of the ADD, SUB, and MUL components ... as of generation 8.3 × 10^13, has printed the first 14 digits of π: 3.1415926535897"
[^17]: [[cgol-ch9-universal-computation](pages/cgol-ch9-universal-computation.md)] pp.299-301, 309 [synthesis] - §9.6.1 general series (9.4); e from a = 1, b = 1, p = 0, q = 1, r = 1, s = 0; "changing two or three lines of code"; √2 in Exercise 9.19
[^18]: [[cgol-ch9-universal-computation](pages/cgol-ch9-universal-computation.md)] pp.302-305 [synthesis] - path rule based on base-4 digits of the step count; "the top half of an 8-pointed version of a well-known fractal called the Koch snowflake"; APGsembly 9.9; n.41 "Originally constructed by Michael Simkin in 2019"
[^19]: [[cgol-ch9-universal-computation](pages/cgol-ch9-universal-computation.md)] pp.304-306 [synthesis] - in an n × n box there are 2^(n²) patterns, so growth past generation 2^(n²) forces a larger box; bits placed in a triangle by the 2D printer; APGsembly 9.10 diameter "Θ(√log(t)) - the smallest unbounded diametric growth rate possible"; Fig. 9.17
