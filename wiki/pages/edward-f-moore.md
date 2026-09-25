---
title: Edward F. Moore
category: People
summary: Bell Labs author who formalized von Neumann's cellular model as "tessellation structures", proved the sufficient direction of the Garden-of-Eden theorem (1962), and gave his name to the nine-cell neighbourhood
tags: [person, moore, garden-of-eden, self-reproduction, bell-labs]
sources: [machine-models-of-self-reproduction, converse-of-moores-garden-of-eden-theorem, planetmath-garden-of-eden-theorem]
created: 2026-09-24
updated: 2026-09-24
---

# Edward F. Moore

## Description

Edward F. Moore wrote "Machine models of self-reproduction" (1962) at Bell Telephone
Laboratories, Murray Hill, New Jersey.[^1] He had heard one of von Neumann's later lecture
series on automata and knew the rest by reading and hearsay.[^2]

**Contributions in the wiki's sources.**

- The name *tessellation structure* and a formal definition of it, the cellular
  structure now called a [[cellular-automaton](pages/cellular-automaton.md)].[^3]
- The nine-cell neighbourhood, now called the
  [[moore-neighbourhood](pages/moore-neighbourhood.md)].[^4]
- A formal definition of a self-reproducing configuration and the kT² bound on offspring
  ([[self-reproduction](pages/self-reproduction.md)]).[^5]
- The sufficient direction of the [[garden-of-eden-theorem](pages/garden-of-eden-theorem.md)]:
  [[erasable-configuration](pages/erasable-configuration.md)]s force
  [[garden-of-eden](pages/garden-of-eden.md)] configurations. He credits Shannon with the
  statement and the idea of the proof, and Tukey with the name.[^6]
  [[john-myhill](pages/john-myhill.md)] proved the converse.[^7]
- A working copy of Penrose's self-reproducing blocks, which he used in talks
  ([[kinematic-self-reproduction](pages/kinematic-self-reproduction.md)]).[^8]

**Other work he cites.** His own bibliography includes "Gedanken-experiments on sequential
machines" (*Automata Studies*, 1956), "Artificial living plants" (*Scientific American*,
1956), and a 1959 abstract of the 1962 paper in which erasable configurations were called
configurations "which can forget".[^9] These are listed, not read.

## Appearances in Sources

- [[planetmath-garden-of-eden-theorem](pages/planetmath-garden-of-eden-theorem.md)] - modern statement of the theorem in d dimensions, credited as Theorem 1
- [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] - author
- [[converse-of-moores-garden-of-eden-theorem](pages/converse-of-moores-garden-of-eden-theorem.md)] - the result Myhill completes

## Related Concepts

- [[john-myhill](pages/john-myhill.md)] - proved the converse of his theorem
- [[garden-of-eden-theorem](pages/garden-of-eden-theorem.md)] - his main result, completed by Myhill
- [[moore-neighbourhood](pages/moore-neighbourhood.md)] - named after him

[^1]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] p.33 [synthesis] - author's affiliation: Bell Telephone Laboratories, Incorporated, Murray Hill, New Jersey
[^2]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] p.17 - "I heard only one series of the later lectures, but by reading and by hearsay I am acquainted with the ideas of some of the others."
[^3]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] pp.17-18, 21 [synthesis] - the tessellation structure defined, formally a quintuple (N, T, S, q₀, f)
[^4]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] p.21 [synthesis] - neighbours are the nine cells whose coordinates differ by at most 1
[^5]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] pp.22-23 [synthesis] - definition of self-reproducing configuration; Theorem 1, f(T) < kT²
[^6]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] pp.23, 26, 31 [synthesis] - Garden-of-Eden term suggested by John W. Tukey; Theorem 2; Shannon's suggestions led to the statement of Theorem 2 and the basic idea of its proof
[^7]: [[converse-of-moores-garden-of-eden-theorem](pages/converse-of-moores-garden-of-eden-theorem.md)] p.685 - "Moore proves that the existence of two mutually erasable configurations in a tessellation universe is a sufficient condition for the existence of Garden-of-Eden configurations therein. We shall show that this condition is both necessary and sufficient."
[^8]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] p.19 [synthesis] - Moore built an exact copy of Penrose's basic model and found it useful for audiences
[^9]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] pp.25, 32-33 [synthesis] - bibliography entries 9, 11, and 43; erasable configuration called a "configuration which can forget" in [11]
