---
title: Signal-Coding Organs (Pulsers and Decoders)
category: Concepts
summary: Components that turn single pulses into timed bit patterns (pulsers), recognize patterns (decoders and recognizers), and hold state by repeating a pattern (periodic pulsers / flip-flops) — the basic signal toolkit of von Neumann's cellular machine
tags: [concept, signal-coding, pulser, decoder, flip-flop, von-neumann]
sources: [tsra-part2-ch3]
created: 2026-09-24
updated: 2026-09-24
---

# Signal-Coding Organs (Pulsers and Decoders)

## Description

In [[von-neumann-29-state-ca](pages/von-neumann-29-state-ca.md)], information travels as
*rigidly timed* pulse trains. At each time step a line carries a stimulus (1) or no
stimulus (0), so a message is a bit string laid out in time.[^1] A handful of organs
convert between single pulses and such strings. They are the signal toolkit of the whole
self-reproducing machine.

**Pulser (coder).** One input pulse produces a fixed output pattern such as 10010001. The
input is split at confluent cells into one path per 1 in the pattern. Each path's length
is tuned so its pulse arrives at the output at the right offset, and the paths merge onto
the output line. Several input pulses produce overlapping copies of the pattern, and they
don't interfere.[^2]

**Decoder (containment detector).** This is the pulser in reverse. Incoming pulses are
split into paths whose delays are chosen so that, if the target pattern arrives, all its
1s reach one point at the same moment. There an AND (a confluent cell) detects the
coincidence. A single confluent cell handles at most three inputs, so larger patterns are
combined pairwise along a chain of confluent cells. The decoder fires when the input
*contains* all the target's 1s, not only on an exact match.[^3] The editor adds a general
**recognizer** that does test for an exact match, using decoders to veto patterns with
extra 1s.[^4]

**Periodic pulser (repeater and flip-flop).** A pulser feeds a closed transmission loop,
which then emits the pattern repeatedly. The rule has no inhibitory state, so "stop" works
by sending special stimuli that kill a cell of the loop and then rebuild it, which clears
the circulating signal.[^5] The simplest case repeats a single 1. It emits a continuous
stream from a "start" pulse until a "stop" pulse, so it acts as a **flip-flop**, a one-bit
memory that can hold a gate (a confluent cell) open.[^6]

**Built from these.** A *triple-return counter* uses three flip-flops as a count memory to
route a signal out and back through another organ three times.[^7] A *discriminator*
separates a lone pulse from the pattern 10101 by combining a decoder with a kill signal.
The machine uses it to read bits from its tape.[^8] Pulsers and decoders also make up the
[[coded-channel](pages/coded-channel.md)].

These organs are the cellular version of the idealized neurons of the
[[mcculloch-pitts-neuron](pages/mcculloch-pitts-neuron.md)] tradition. Coincidence
detection is AND, merging is OR, and memory is a recirculating loop.

## Appearances in Sources

- [[tsra-part2-ch3](pages/tsra-part2-ch3.md)] — designs of the pulser, decoder, periodic pulser, counter, and discriminator

## Related Concepts

- [[cellular-tape](pages/cellular-tape.md)] — where the counter and discriminator are used
- [[coded-channel](pages/coded-channel.md)] — built from pulsers and decoders
- [[von-neumann-29-state-ca](pages/von-neumann-29-state-ca.md)] — the rule these organs are built in
- [[mcculloch-pitts-neuron](pages/mcculloch-pitts-neuron.md)] — the logical elements they realize
- [[universal-constructor](pages/universal-constructor.md)] — whose control is assembled from these organs

[^1]: [[tsra-part2-ch3](pages/tsra-part2-ch3.md)] p.157 [synthesis] — rigid timing; stimulus-no-stimulus sequences written as strings of 1s and 0s
[^2]: [[tsra-part2-ch3](pages/tsra-part2-ch3.md)] pp.159-162 [synthesis] — the pulser: the input is split through confluent cells into k paths, one per 1 in the characteristic, with delays set so the pulses emerge at the right relative times; repeated inputs overlap without corruption
[^3]: [[tsra-part2-ch3](pages/tsra-part2-ch3.md)] pp.175-179 [synthesis] — the decoding organ responds to any sequence containing all the 1s of its characteristic; paths with delays bring the stimuli into coincidence; a confluent cell handles at most three inputs, so coincidences are taken pairwise; a pulser is a coder and the decoder is similar
[^4]: [[tsra-part2-ch3](pages/tsra-part2-ch3.md)] pp.189-190 [synthesis] — editor: a recognizer that responds to a given sequence exactly, blocking responses when extra 1s are present
[^5]: [[tsra-part2-ch3](pages/tsra-part2-ch3.md)] pp.162-166 [synthesis] — the periodic pulser: a pulser feeding a periodic repeater (closed loop); stopping by special stimuli that kill a loop cell, followed by the direct process restoring it
[^6]: [[tsra-part2-ch3](pages/tsra-part2-ch3.md)] p.174 [synthesis] — editor: the simplest periodic pulser functions as a flip-flop, on at the start input and off at the stop input, emitting a continuous stream used to operate a gate
[^7]: [[tsra-part2-ch3](pages/tsra-part2-ch3.md)] pp.181-182 [synthesis] — triple-return counter: three periodic pulsers mark the three count-periods, with confluent cells as gates
[^8]: [[tsra-part2-ch3](pages/tsra-part2-ch3.md)] pp.187-188 [synthesis] — the 1 vs. 10101 discriminator distinguishes a single stimulus from the sequence 10101; used in reading cells of the tape
