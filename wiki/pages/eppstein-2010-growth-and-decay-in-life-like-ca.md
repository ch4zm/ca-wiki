---
title: "Eppstein (2010), Growth and Decay in Life-Like Cellular Automata"
category: Sources
summary: Eppstein's chapter replacing Wolfram's random-start classes with two yes/no questions - can a finite pattern escape every bounding box (fertile), and can one die out (mortal) - which settle 96% and 99.8% of the Life-like rules without B0; fertile-and-mortal rules are where engineered complexity lives, shown by a tour of HighLife, B36/S245, Morley, B37/S23, Day & Night, Diamoeba, B35/S236 and others
tags: [source, paper, eppstein, classification, fertile, mortal, life-like, rule-space, wolfram-classes, replicators]
sources: [eppstein-2010-growth-and-decay-in-life-like-ca]
created: 2026-09-25
updated: 2026-09-26
---

# Eppstein (2010), Growth and Decay in Life-Like Cellular Automata

**Source:** raw/eppstein-2010-growth-and-decay-in-life-like-ca.pdf (Eppstein, D., "Growth and Decay in Life-Like Cellular Automata", in A. Adamatzky (ed.), *Game of Life Cellular Automata*, Springer, 2010, pp. 71-97, https://doi.org/10.1007/978-1-84996-217-9_6; the file is the arXiv preprint 0911.2890, and page numbers below are its pages 1-30).
**Date ingested:** 2026-09-25
**Type:** paper (book chapter)

## Summary

Eppstein asks how one would recognize another rule as rich as Life, and argues that
Wolfram's four classes are the wrong tool. They are judged from random starts, so they
describe a rule only after watching it, have blurry and possibly undecidable borders, and
miss the engineered patterns (guns, metapixels, the Caterpillar) that make Life
interesting, none of which would ever appear from a random field.[^1] He proposes two
yes/no questions instead, restricted to the 2^17 [[life-like-cellular-automaton](pages/life-like-cellular-automaton.md)]
rules without B0: is the rule **fertile** (some finite pattern escapes every bounding
box) and is it **mortal** (some finite pattern dies out completely)? Short proofs settle
most rules. B1 and B2 rules are fertile, rules with none of B1, B2, B3 are not, and
spaceship searches plus one diamond argument settle all but 5,584 of the B3 rules, so 96%
of all rules are settled. Hickerson's duality
between fading and still lifes settles mortality for 99.8% of rules, including every B3
rule ([[fertile-and-mortal-rules](pages/fertile-and-mortal-rules.md)]).[^2]

The hypothesis is that fertile-and-mortal rules are where complex engineered patterns
live. A tour of rules backs it: HighLife's replicator-built oscillators, guns and rakes,
B36/S245's shuttle replicator and slow spaceships, Morley's puffers and breeders, B37/S23's
puddlejumper, Day & Night's gun-antigun boundaries, Diamoeba's spacefiller, B35/S236's
quadratic growth, and B2 rules with photons and a photon-replicator random walk. These
rules span Wolfram classes II, III and IV, so the Wolfram class does not predict where the
engineering is.[^3] Infertile or immortal rules can still be interesting, but in narrower
ways: Life without Death computes with ladders, and Fredkin's B1357/S1357 is nothing but
replicators.[^4] The chapter closes by extending both notions to rules whose background is
not empty but periodic, such as the strobing B0 rules.[^5]

## Key Takeaways

- Random-start classification cannot see engineered structure. Life's random ash is
  mostly still lifes and period-2 oscillators, while its famous patterns are built.[^1]
- Fertile means some finite pattern escapes every bounding box, which is the same as
  saying not every finite pattern ends periodic. Mortal means some finite pattern dies
  out in one step.[^2]
- Of the 16,384 B3 rules, 10,736 have known spaceships and 64 are provably infertile,
  leaving 5,584 open. Of the 131,072 rules without B0, 77,563 are immortal and 53,214
  mortal, with 295 unclassified.[^2]
- A pattern fades in a rule exactly when it is a still life in the rule with the same
  births and complementary survivals (Hickerson).[^6]
- Immortality does not rule out spaceships (B3456/S013 has them), but most immortality
  proofs also show a pattern's bounding box can never shrink, which does.[^7]
- The rules with the richest engineering are fertile and mortal, and they fall in
  different Wolfram classes.[^3]

## Entities & Concepts

- [[fertile-and-mortal-rules](pages/fertile-and-mortal-rules.md)] - the classification this paper introduces
- [[classification-of-cellular-automata](pages/classification-of-cellular-automata.md)] - Wolfram's classes, which it criticizes
- [[life-like-cellular-automaton](pages/life-like-cellular-automaton.md)] - the rule family surveyed
- [[highlife](pages/highlife.md)], [[replicator](pages/replicator.md)], [[seeds-rule](pages/seeds-rule.md)] - rules and patterns in the tour
- [[spaceship](pages/spaceship.md)], [[glider](pages/glider.md)] - fertility is shown mostly by exhibiting spaceships
- [[metacell](pages/metacell.md)] - the OTCA metapixel as an engineered pattern random soup would never make
- [[eppstein-gliders-in-life-like-cellular-automata](pages/eppstein-gliders-in-life-like-cellular-automata.md)] - the spaceship database behind the fertility counts
- [[edge-of-chaos](pages/edge-of-chaos.md)] - Langton's rival rule-space criterion for where complexity lives

## Relation to Other Wiki Pages

The fertile/mortal split refines the lowest-birth-count map on
[[life-like-cellular-automaton](pages/life-like-cellular-automaton.md)]: B1 and B2 are
fertile outright, B4 and up is infertile, and the real questions sit in B3. It adds a
second, rule-space classification beside the random-start and topological schemes on
[[classification-of-cellular-automata](pages/classification-of-cellular-automata.md)], and
its point about engineered patterns is the same one made by the undecidability of whether
a Life pattern dies ([[game-of-life](pages/game-of-life.md)]), which depends on patterns
that fade.[^8]

[^1]: [[eppstein-2010-growth-and-decay-in-life-like-ca](pages/eppstein-2010-growth-and-decay-in-life-like-ca.md)] pp.1-6 [synthesis] - Wolfram's classes; "the classification depends strongly on the specific behavior of an individual rule, so that one cannot use it to predict which rules are likely to have interesting behavior"; "may for some automata be impossible to decide"; random Life fields "consist overwhelmingly of small still lifes and small period-two oscillators"; Greene's 2c/5 gun, the OTCA meta-pixel and the Caterpillar as engineered patterns; "it is very difficult to say anything that can be backed up by rigorous mathematics"
[^2]: [[eppstein-2010-growth-and-decay-in-life-like-ca](pages/eppstein-2010-growth-and-decay-in-life-like-ca.md)] pp.2,7-9,10,13-14 [synthesis] - "do there exist patterns that eventually escape any finite bounding box placed around them? And do there exist patterns that die out completely?"; without B0 "we need consider only 2^17 possible rules"; fertility definition and its equivalence with not every pattern becoming periodic; B1 and B2 fertile, no B1/B2/B3 not fertile; "10736 out of the 16384 possible B3 rules have spaceships"; 64 B3 rules proved infertile; "There remain only 5584 rules ... in 96% of the cases"; mortal if a finite pattern's next state has no live cells; "77563 of them are immortal and 53214 of them are mortal. There remain 295 rules ... approximately 99.8% of the cases. In particular this classification covers all rules that include B3"
[^3]: [[eppstein-2010-growth-and-decay-in-life-like-ca](pages/eppstein-2010-growth-and-decay-in-life-like-ca.md)] pp.14-22 [synthesis] - "the rules most likely to support interesting patterns are the ones that are both fertile and mortal"; "these rules are both fertile and mortal, but they have differing Wolfram classes"; HighLife, B368/S12578, B36/S245, Morley, B37/S23, Day & Night, Diamoeba, B35/S236, B27/S0, B25/S4, B24/S, B2/S7
[^4]: [[eppstein-2010-growth-and-decay-in-life-like-ca](pages/eppstein-2010-growth-and-decay-in-life-like-ca.md)] pp.22-25 [synthesis] - Anneal "mortal but infertile"; B1357/S1357 "fertile but immortal ... in this rule there is nothing but replicators"; B1/S012345678 snowflake; B4/S01234 "both infertile and immortal"; Life Without Death ladders "can be arranged to simulate any Boolean circuit, showing that it is P-complete"
[^5]: [[eppstein-2010-growth-and-decay-in-life-like-ca](pages/eppstein-2010-growth-and-decay-in-life-like-ca.md)] pp.25-27 [synthesis] - periodic backgrounds; B0-with-death-on-8 rules alternate live and dead backgrounds; B01245/S0125 "a strobing version of Day & Night"; "a fertile combination of a rule and a background is one for which some finite perturbation to the background escapes any bounding box"
[^6]: [[eppstein-2010-growth-and-decay-in-life-like-ca](pages/eppstein-2010-growth-and-decay-in-life-like-ca.md)] p.11 - "a pattern fades in rule r if and only if the same pattern forms a still life in the rule r̄ with the same birth conditions and complementary survival conditions"
[^7]: [[eppstein-2010-growth-and-decay-in-life-like-ca](pages/eppstein-2010-growth-and-decay-in-life-like-ca.md)] p.14 - "the immortal rule B3456/S013 has spaceships"; "in many of the cases for which we can prove that a rule is immortal, the proof shows something stronger, that the minimal bounding box or minimal bounding diamond of a pattern can never shrink. When this is true, it is impossible for a spaceship to exist"
[^8]: [[eppstein-2010-growth-and-decay-in-life-like-ca](pages/eppstein-2010-growth-and-decay-in-life-like-ca.md)] p.10 - "the proof that determining the eventual fate of a Life pattern is undecidable depends on patterns that fade"
