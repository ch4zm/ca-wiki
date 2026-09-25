---
title: Amenable Group
category: Concepts
summary: The class of groups on which the Garden-of-Eden theorem holds - cellular automata on a group satisfy both Moore's and Myhill's theorems exactly when the group is amenable
tags: [concept, amenable-group, garden-of-eden, group-theory]
sources: [planetmath-garden-of-eden-theorem]
created: 2026-09-24
updated: 2026-09-24
---

# Amenable Group

## Description

**Cellular automata on groups.** A cellular automaton does not need the grid ℤᵈ. Its cells
can be the elements of any group G, with each cell's neighbourhood a fixed finite set of
group elements translated to that cell. ℤᵈ is the case of the ordinary lattice. (Own
background, not from a read source.)

**What amenability means.** A group is amenable when it contains finite sets whose boundary
is arbitrarily small compared with their size, so-called Følner sets. In ℤᵈ, cubes of side n
have volume nᵈ and a boundary of order nᵈ⁻¹, so ℤᵈ is amenable. The free group on two
generators is the standard non-amenable group: every finite set has a boundary comparable to
its size. (Own background, not from a read source.)

**Why it matters for the Garden-of-Eden theorem.** Both of Moore's and Myhill's counting
proofs compare the patterns in a large block with the images of its interior. The boundary
lost at each step must be small next to the block
([[planetmath-garden-of-eden-theorem](pages/planetmath-garden-of-eden-theorem.md)]'s
lemma).[^1] Moore made the same point about Euclidean space, which gives regions whose
interior is arbitrarily large relative to their boundary.[^2] Amenability is exactly that
property for a general group (own reasoning).

**The theorems.** Moore's and Myhill's theorems hold for cellular automata on every amenable
group (Ceccherini-Silberstein, Machì and Scarabotti, 1999).[^3] Moore's theorem
characterizes amenability. On a non-amenable group, some cellular automaton has mutually
erasable patterns but no Garden of Eden (Bartholdi, 2010).[^3] Myhill's theorem
characterizes it too. A group is amenable if and only if every cellular automaton on it
that has Gardens of Eden also has mutually erasable patterns (Bartholdi and Kielak,
2016).[^4] So the full [[garden-of-eden-theorem](pages/garden-of-eden-theorem.md)] holds on
a group exactly when the group is amenable.

## Appearances in Sources

- [[planetmath-garden-of-eden-theorem](pages/planetmath-garden-of-eden-theorem.md)] - both theorems on amenable groups; Moore's theorem characterizes them

## Related Concepts

- [[garden-of-eden-theorem](pages/garden-of-eden-theorem.md)] - the theorem that holds exactly on amenable groups
- [[garden-of-eden](pages/garden-of-eden.md)] - orphan patterns
- [[erasable-configuration](pages/erasable-configuration.md)] - mutually erasable patterns
- [[cellular-automaton](pages/cellular-automaton.md)] - the general setting, here with a group as the lattice

[^1]: [[planetmath-garden-of-eden-theorem](pages/planetmath-garden-of-eden-theorem.md)] Lemma 1 [synthesis] L40-60 - (a^(k^d) − 1)^(n^d) < a^((kn − 2r)^d) for large n; images of side-kn patterns are patterns of side kn − 2r
[^2]: [[machine-models-of-self-reproduction](pages/machine-models-of-self-reproduction.md)] pp.28-29 [synthesis] - Euclidean space gives interiors arbitrarily large relative to boundaries, which the proof of Theorem 2 uses
[^3]: [[planetmath-garden-of-eden-theorem](pages/planetmath-garden-of-eden-theorem.md)] closing paragraph and refs [synthesis] L129-150 - Theorems 1 and 2 hold on amenable groups [Ceccherini-Silberstein, Machì, Scarabotti 1999]; "Moore's theorem, in fact, characterizes amenable groups" [Bartholdi 2010, cited via this entry, not read]
[^4]: https://arxiv.org/abs/1605.09133 abstract (abstract read, paper not read) - "A group G is amenable if and only if every cellular automaton with carrier G that has gardens of Eden also has mutually erasable patterns."
