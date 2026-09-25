---
title: Notation Map
category: Analyses
summary: Crosswalk from the symbols each source uses (von Neumann's lectures and manuscript, Burks's completion) onto the wiki's common concepts and notation, with a list of letters that mean different things in different places
tags: [notation, reference, von-neumann, burks, self-reproduction, 29-state]
sources: [tsra-editors-introduction, tsra-lecture-5, tsra-part2-ch1, tsra-part2-ch2, tsra-part2-ch3, tsra-part2-ch4, tsra-part2-ch5]
created: 2026-09-24
updated: 2026-09-24
---

# Notation Map

The sources letter the same ideas differently, and reuse the same letters for unrelated
ideas. Wiki pages use the common notation below. Source symbols appear only when quoted or
when a page is explicitly about a source's own construction. This page maps each source's
symbols to the concept it names. Add a column or a table when a new source brings its own
notation.

## The self-reproduction scheme

The wiki's notation is set out in [[universal-constructor](pages/universal-constructor.md)].

| Concept | Wiki | Lecture 5 (1949) | Part II Ch. 1 (1952) | Part II Ch. 5 (Burks) |
|---|---|---|---|---|
| an arbitrary automaton to be built | X | X | G (the secondary built is S) | M |
| description of X | φ(X) | φ(X) | L_X (e.g. L_D, L_G); the tape itself is L | D(M) |
| a copy of a description | — | — | L′ | — |
| universal constructor | A | A | A | M_c = CU + (MC + L) |
| description copier | B | B | B | folded into M_c* |
| controller | C | C | C | folded into M_c* |
| constructor + copier + controller | A + B + C | A + B + C | D | M_c* |
| self-reproducer | (A + B + C) + φ(A + B + C) | (A + B + C) + φ(A + B + C) | E = D + L_D | M_c* + D(M_c*) |
| payload (extra product) | P | D | F | M_u, when attached |
| mutated payload | P′ | D′ | F′ | — |
| self-reproducer with payload | (A + B + C + P) + φ(A + B + C + P) | (A + B + C + D) + φ(A + B + C + D) | E_F = D + L_(D+F) | (M_u + M_c*) + D(M_u + M_c*) |
| builder / built | — | — | primary / secondary (then ternary, …) | primary / secondary |

Sources: Lecture 5,[^1] Ch. 1,[^2] Ch. 5.[^3]

## The five questions

Von Neumann frames Part II with five lettered questions, and Burks keeps the letters.[^4]
Wiki pages name them in words:

| Book | Wiki |
|---|---|
| (A) | logical universality |
| (B) | constructibility |
| (C) | construction universality |
| (D) | self-reproduction |
| (E) | evolution |

## The description tape

| Concept | Wiki | Book symbol | Where used |
|---|---|---|---|
| the tape | description tape, [[cellular-tape](pages/cellular-tape.md)] | L (linear array) | Ch. 1[^5] |
| cell n of the tape, and its index | xₙ, n | xₙ, n (nˢ at step s) | Ch. 1, Ch. 4, Ch. 5[^6][^7] |
| target rectangle: corner and size | x₁, y₁, α, β | x₁, y₁, α, β | Ch. 1[^8] |
| state wanted in target cell (i, j) | λᵢⱼ | λᵢⱼ | Ch. 1[^8] |
| number of possible cell states | — | 𝔏 (script L) | Ch. 1[^8] |
| number base for tape digits | — | k | Ch. 1[^5] |
| contents to give the offspring's tape | — | T(M) | Ch. 5[^3] |
| connecting loop (read/write) | connecting loop | C₁ | Ch. 1, Ch. 4[^6] |
| timing loop | timing loop | C₂ | Ch. 1, Ch. 4[^6] |
| memory control | memory control | MC | Ch. 1, Ch. 4[^6] |
| constructing unit | constructing unit | CU | Ch. 5[^3] |
| tape unit | tape plus memory control | MC + L | Ch. 5[^9] |
| a finite automaton operating the tape | finite control | FA, with functions A (next state), X (bit to write), E (±1 move) | Ch. 5[^9] |
| universal Turing machine | [[universal-turing-machine](pages/universal-turing-machine.md)] | M_u (its program for M is D′(M)) | Ch. 5[^3] |

**Inside the memory control** (Ch. 4 and Ch. 5 only): RWE is the read-write-erase unit, RWEC
its control, CO the control organs, CC₁–CC₃ the sections of the coded channel, D the delay
area of each control organ, and X, Y, Z, W further areas. In Burks's constructing unit, SO
is a state organ.[^10]

## The 29 states

[[von-neumann-29-state-ca](pages/von-neumann-29-state-ca.md)] describes the states in words.
The book's symbols:[^11]

| Wiki | Book | Indices |
|---|---|---|
| ordinary / special transmission cell | T_uαε | u = 0 ordinary, 1 special; α = 0 right, 1 up, 2 left, 3 down; ε = 0 quiescent, 1 excited |
| confluent cell | C_εε′ | ε = current excitation, ε′ = next excitation |
| blank / unexcitable cell | U | — |
| sensitized (mid-build) cell | S_Σ | Σ = the bits received so far |
| ordinary / special stimulus | [0] / [1] | — |
| the tape's "1" cell (downward ordinary) | ↓ | T₀₃₀ |

The ten quiescent states that make up an
[[initially-quiescent-automaton](pages/initially-quiescent-automaton.md)] are U, T_uα0, and
C₀₀.[^12] From Ch. 5 on, Burks draws single arrows for ordinary transmission cells and double
arrows for special ones.[^13]

## Organs

Wiki pages name organs in words ([[signal-coding-organs](pages/signal-coding-organs.md)]).
The book writes a binary characteristic i¹ … iⁿ, with 1 for a stimulus and 0 for none:[^14]

| Wiki | Book |
|---|---|
| pulser | P(i¹ … iⁿ) |
| periodic pulser | PP(i¹ … iⁿ); PP(1̄) is the alternate periodic pulser |
| decoder | D(i¹ … iⁿ) |
| triple-return counter | Φ |
| 1-vs-10101 discriminator | Ψ |

## Letter collisions

Letters that change meaning between (or within) sources:

- **A**: universal constructor in Lecture 5 and Ch. 1. In Ch. 5 it is also a finite
  automaton's next-state function. As (A), it is the logical-universality question.[^1][^9][^4]
- **B**: copier. As (B), it is the constructibility question.
- **C**: controller in Lecture 5 and Ch. 1; the confluent state C_εε′ in Ch. 2; C₁ and C₂
  are the two tape loops.[^1][^11][^6]
- **D**: the most overloaded letter. It is the payload in Lecture 5, the machine A + B + C in
  Ch. 1, a decoder D(i¹ … iⁿ) in Ch. 3, the delay area of a control organ in Chs. 4–5, and
  the description D(M) in Ch. 5.[^1][^2][^14][^10][^3]
- **E**: the self-reproducer in Ch. 1, the evolution question (E), and in Ch. 5 a finite
  automaton's move function.[^2][^4][^9]
- **F**: the payload in Ch. 1. The book also uses F for the transition function of a
  cellular automaton (Ch. 2).[^2][^11]
- **L**: the tape. Script 𝔏 is the number of cell states, and L_X is a description.[^5][^8]
- **P**: the wiki's payload. In the book P(i¹ … iⁿ) is a pulser, and in the Introduction P
  is the program of Turing's universal machine, which the wiki writes π.[^14][^15]
- **S**: the secondary built in Ch. 1; S_Σ is a sensitized state.[^2][^11]
- **X**: an arbitrary automaton in Lecture 5; in Ch. 5 a finite automaton's write function
  and also an area of the memory control.[^1][^9][^10]

[^1]: [[tsra-lecture-5](pages/tsra-lecture-5.md)] pp.84-87 [synthesis] — φ(X) the chain describing X; A the universal constructor, B the copier, C the control; (A + B + C) + φ(A + B + C); X = A + B + C + D with D any automaton as by-product; mutation replaces D by D′
[^2]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] pp.118-131 [synthesis] — A, B, C with description L attached; B makes a copy L′; C builds the secondary S; D = A + B + C with description L_D; E = D + L_D is self-reproducing; F an additional automaton, E_F = D with L_(D+F); G a secondary with description L_G; primary, secondary, ternary; mutation to F′
[^3]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] pp.271, 286, 294-295 [synthesis] — universal constructor M_c = CU + (MC + L); D(M) the coded description of M; M_c* the modified constructor, with tape content T(M); M_c* + D(M_c*); (M_u + M_c*) + D(M_u + M_c*); primary and secondary automata
[^4]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] pp.266, 286-287 [synthesis] — the five main questions (A) logical universality, (B) constructibility, (C) construction universality, (D) self-reproduction, (E) evolution
[^5]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] pp.112-114 [synthesis] — the linear array L outside the primary; cells with k states for base-k digits plus comma and period
[^6]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] p.115 [synthesis] — editor: square xₙ reached by a contractable wire; memory control MC; zero represented by U, one by T₀₃₀; connecting loop C₁; timing loop C₂
[^7]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] p.259 [synthesis] — nˢ is the number of the square xₙ under scan at step s
[^8]: [[tsra-part2-ch1](pages/tsra-part2-ch1.md)] pp.116-117 [synthesis] — rectangle given by x₁, y₁, α, β; cell (i, j) with desired state λᵢⱼ; 𝔏 the number of states a cell can assume
[^9]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] pp.266-267 [synthesis] — the tape unit MC + L; a finite automaton FA with functions A (next state), X (number written), E (lengthening-shortening parameter)
[^10]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] pp.251-253, 267 [synthesis] — RWE, RWEC, control organs CO, delay area D, coded channel parts CC₁, CC₂, CC₃, areas X, Y, Z, W; state organ SO
[^11]: [[tsra-part2-ch2](pages/tsra-part2-ch2.md)] pp.148-151 [synthesis] — T_uαε with u = 0, 1 ordinary and special, α = 0, 1, 2, 3 right, up, left, down, ε = 0, 1 quiescent and excited; C_εε′; U; S_Σ; ordinary stimuli [0] and special stimuli [1]; F the transition function of Sec. 2.1.2
[^12]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] p.264 [synthesis] — the 10 quiescent states U, T_uα0, and C₀₀
[^13]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] pp.262, 274 [synthesis] — a single arrow represents an ordinary transmission state, a double arrow a special transmission state
[^14]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] p.292 [synthesis] — editor's summary of Ch. 3: pulsers P(i¹ … iⁿ), periodic pulsers PP(i¹ … iⁿ), decoders D(i¹ … iⁿ), the triple-return counter Φ, and the 1 vs. 10101 discriminator Ψ
[^15]: [[tsra-editors-introduction](pages/tsra-editors-introduction.md)] p.14 — "for any Turing machine M there is a finite program P such that machine U, operating under the direction of P, will compute the same results as M."
