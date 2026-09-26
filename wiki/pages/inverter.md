---
title: Inverter
category: Patterns
summary: A Life mechanism that turns the gliders of an irregular stream into gaps and its gaps into gliders; gun-versus-stream inverters, the Gosper-gun inline inverter and the non-destructive stream inverter give glider duplicators, finite glider streams, guns of any period 120n, and (with a toggle) pseudo-random guns
tags: [pattern-class, life, circuitry, inverter, duplicator, toggle, glider-stream]
sources: [cgol-ch6-periodic-circuitry]
created: 2026-09-25
updated: 2026-09-25
---

# Inverter

## Description

An *irregular* glider stream has a fixed spacing but some gliders missing. To *invert* it
is to replace every glider with a gap and every gap with a glider.[^1]

**Kinds of inverter.**[^2]
- **Gun against stream.** Aim a gun's regular stream so its gliders annihilate the input's.
  Wherever the input has a glider both vanish; wherever it has a gap the gun's glider
  passes. This works at any period.
- **Inline inverter** (David Bell). A glider fired into the small explosion between a
  [[gosper-glider-gun](pages/gosper-glider-gun.md)]'s two queen bees stops that glider
  being made. The inverted output continues in nearly the same direction as the input.
  Tanner's p46 edge-shooting gun works as a period-46 inline inverter.
- **Stream inverter.** A regular stream of any period 20 or more crossing an irregular
  one passes where the irregular stream has a gap and is deflected where it has a glider.
  That gives two outputs, a copy and an inverse, without using up the input: a
  *non-destructive* inverter.

**What inverters build.**[^3]
- **Glider duplicators.** A stream inverter followed by a second inversion copies any
  stream, so one signal can trigger several reactions.
- **Finite streams and big-period guns.** One Gosper gun feeding an inline inverter holds
  a glider stream of any chosen length as a period-30 oscillator. Deleting one of its
  gliders releases one. A glider bouncing between two such streams gives glider guns of
  period 120n for any n ≥ 1.
- **Re-timing.** A glider on a known schedule can be moved to any chosen place and time by
  having it delete one glider from a gun's stream just before an inverter
  ([[regulator](pages/regulator.md)]).

**Toggle.** A toggle (Dean Hickerson, 1996) is a glider gun switched on and off by single
gliders. It bounces gun gliders off an LWSS stream, and one input glider turns the output
off until the next turns it back on.[^4] Fed back into itself around a loop of n gliders,
it makes the output bits obey b(k) = b(k−1) ⊕ b(k−n). With n = 25 the sequence has period
10,961,685, which gives a pseudo-random glider gun of period 328,850,550.[^5]

## Appearances in Sources

- [[cgol-ch6-periodic-circuitry](pages/cgol-ch6-periodic-circuitry.md)] - §6.1.2 inverters and duplicators; §6.1.3 toggle; §6.6 the pseudo-random gun

## Related Concepts

- [[gun](pages/gun.md)] - the pattern class
- [[caber-tosser](pages/caber-tosser.md)] - its duplicator uses the gun-against-stream blocking trick
- [[gosper-glider-gun](pages/gosper-glider-gun.md)] - the p30 inline inverter
- [[primer](pages/primer.md)] - built from inline-inverter guns
- [[memory-cell](pages/memory-cell.md)] - inverted loop segments allow writing 1s
- [[heisenburp](pages/heisenburp.md)] - duplication without touching the glider
- [[regulator](pages/regulator.md)] - re-timing gliders

[^1]: [[cgol-ch6-periodic-circuitry](pages/cgol-ch6-periodic-circuitry.md)] p.155 - "If we have an irregular glider stream--one in which gliders are separated by a fixed period, except some gliders are missing--it is often useful to invert the stream. That is, we would like to have a mechanism for replacing the gliders in the stream by empty gaps, and replacing the empty gaps by gliders"
[^2]: [[cgol-ch6-periodic-circuitry](pages/cgol-ch6-periodic-circuitry.md)] pp.155-157,168 [synthesis] - Fig. 6.5 gun-against-stream inversion "works at any period"; inline inverter "in which the gun fails to produce a glider if it receives a glider as input" (n.2 David Bell); Fig. 6.29(b) Tanner's p46 edge shooter as a p46 inline inverter; Fig. 6.9 stream inverter for period 20 or higher with two outputs, "a non-destructive inverter"
[^3]: [[cgol-ch6-periodic-circuitry](pages/cgol-ch6-periodic-circuitry.md)] pp.156-157,172 [synthesis] - Fig. 6.10 "glider duplicators"; Fig. 6.7 finite stream between two Gosper guns released by deleting a glider; Fig. 6.8 "glider guns with period equal to 120n for any integer n ≥ 1"; Fig. 6.37 re-timing an input glider with a gun and inverter
[^4]: [[cgol-ch6-periodic-circuitry](pages/cgol-ch6-periodic-circuitry.md)] p.158 - "the toggle, which is a glider gun that can be switched on and off by firing a single glider into it"; n.5 constructed by Dean Hickerson in April 1996; Fig. 6.14
[^5]: [[cgol-ch6-periodic-circuitry](pages/cgol-ch6-periodic-circuitry.md)] pp.176-177 [synthesis] - toggle output fed back gives "b(k) = b(k − 1) ⊕ b(k − n) for all k > n"; Fig. 6.42 "A period 30 × 10 961 685 = 328 850 550 pseudo-random glider gun" with n = 25
