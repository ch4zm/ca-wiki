---
title: Classification of Cellular Automata
category: Concepts
summary: Schemes for sorting rules by behaviour - Wolfram's simple/complex split (1983) and four classes (1984), Culik and Yu's formal four classes on finite configurations (undecidable), and Kurka's four equicontinuity classes from topological dynamics (undecidable except the open positively-expansive class)
tags: [concept, classification, wolfram-classes, culik-yu, kurka, undecidability]
sources: [eppstein-gliders-in-life-like-cellular-automata, eppstein-2010-growth-and-decay-in-life-like-ca, theory-of-cellular-automata-a-survey, statistical-mechanics-of-cellular-automata, aucm-ch12-linear-cellular-automata-and-decidability]
created: 2026-09-24
updated: 2026-09-25
---

# Classification of Cellular Automata

> Wolfram (1984), Culik and Yu (1988), Kurka (1997) and Durand, Formenti and Varouchas
> (2003) are cited via
> [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)]
> and have not been read.

## Description

**Wolfram 1983: simple and complex.** Wolfram's first split of the 32 legal
[[elementary-cellular-automaton](pages/elementary-cellular-automaton.md)] rules is by what
grows from a single 1. *Simple* rules erase it, freeze it, or grow a uniform block.
*Complex* rules grow a non-trivial self-similar pattern. From random starts, simple rules
settle to fixed points or short cycles, and complex rules behave more like strange
attractors.[^1]

**Wolfram 1984: four classes.** Running elementary rules from random starts and judging by
the space-time diagrams, Wolfram sorted them into four classes:[^2]

- **W1**: almost all starts lead to the same uniform fixed point,
- **W2**: almost all starts lead to a periodically repeating configuration,
- **W3**: almost all starts lead to essentially random-looking behaviour,
- **W4**: localized structures with complex interactions emerge.

He conjectured that class-4 rules are computationally universal. The universal
[[rule-110](pages/rule-110.md)] is consistent with that, while class-4 rule 54 is open. Localized class-4 structures are the 1D
counterpart of the gliders of the [[game-of-life](pages/game-of-life.md)].[^2][^3] Kari
calls the classification "vague".[^4]

**Culik and Yu: a formal version.** For CA with a quiescent state, a rule belongs to the
lowest class whose property holds:[^5]

- **CY1**: every finite configuration eventually becomes quiescent.
- **CY2**: every finite configuration is eventually periodic.
- **CY3**: it is decidable, for two finite configurations c and e, whether e is in the
  orbit of c ([[reachability-in-cellular-automata](pages/reachability-in-cellular-automata.md)]).
- **CY4**: no restriction.

CY1 is weaker than nilpotency, which requires *every* configuration to die. Rule 128 is
in CY1 but not nilpotent ([[limit-set](pages/limit-set.md)]).[^5] Culik and Yu proved that
**no algorithm decides which class a 1D CA belongs to**.[^4]

**Sutner: logic and degrees.** Sutner writes Wolfram class I as a sentence, FP ≡
∀x ∃y (x →* y ∧ y → y): every orbit ends in a fixed point. Whether FP holds on every
finite grid is Π⁰₁-complete. For computational questions, he suggests classifying rules
by the degree of their reachability problem, which can be any r.e. degree. That
classification is undecidable too: testing for universality is Σ⁰₄-complete
([[reachability-in-cellular-automata](pages/reachability-in-cellular-automata.md)]).[^6]
Properties that look at a bounded number of steps are all decidable in 1D
([[first-order-theory-of-cellular-automata](pages/first-order-theory-of-cellular-automata.md)]),
so any classification that captures long-term behaviour is out of automatic reach.[^7]

**Kurka: equicontinuity classes.** From topological dynamics
([[chaos-in-cellular-automata](pages/chaos-in-cellular-automata.md)]):[^8]

- **K1**: equicontinuous (every configuration is an equicontinuity point).
- **K2**: some but not all configurations are equicontinuity points.
- **K3**: sensitive to initial conditions but not positively expansive.
- **K4**: positively expansive.

Every CA is in exactly one class, because a CA with no equicontinuity points is
automatically sensitive. K4 is empty in two or more dimensions. For 1D CA, membership in
K1, K2 and K3 is undecidable. Whether K4 membership (positive expansivity) is decidable is
open.[^8][^9]

**Eppstein: growth and decay.** For 2D Life-like rules, Eppstein argues that Wolfram's
classes fail in practice. Judged from random starts, they describe a rule only after
watching it, their borders blur, Life's own class is a matter of convention, and they miss
the engineered structures that make Life rich, none of which a random field would ever
produce. B35/S236 looks class III from random starts yet supports Life-like
constructions.[^10] His site reports gliders in rules that would fall in each of the four
classes.[^11] In their place he asks two yes/no questions: is the rule *fertile* (some
finite pattern escapes every bounding box) and *mortal* (some finite pattern dies out)?
Short proofs settle these for 96% and 99.8% of the rules without B0, and the
fertile-and-mortal rules are where complex engineered patterns turn up, across several
Wolfram classes ([[fertile-and-mortal-rules](pages/fertile-and-mortal-rules.md)]).[^12]
Unlike the formal classes above, these are properties of the rule decided by proof for
whole blocks of rules at once, though each still asks an existence question with no
general algorithm promised (own reasoning).

**Comparison (own reasoning).** Wolfram's classes describe what is seen from random
starts. Culik-Yu's describe finite configurations and computability. Kurka's describe how
nearby configurations separate. The survey states no formal correspondence between them.
All the formal versions are undecidable, so none can be computed from a rule table.

## Appearances in Sources

- [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] - FP as Wolfram class I; classification by reachability degree
- [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] - §2.5 (Wolfram and Culik-Yu classes), §8 (Kurka classes)
- [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] - the 1983 simple/complex split
- [[eppstein-2010-growth-and-decay-in-life-like-ca](pages/eppstein-2010-growth-and-decay-in-life-like-ca.md)] - critique of Wolfram's classes; fertile and mortal rules
- [[eppstein-gliders-in-life-like-cellular-automata](pages/eppstein-gliders-in-life-like-cellular-automata.md)] - gliders found in rules of all four classes

## Related Concepts

- [[elementary-cellular-automaton](pages/elementary-cellular-automaton.md)] - the family first classified
- [[fertile-and-mortal-rules](pages/fertile-and-mortal-rules.md)] - Eppstein's growth-and-decay alternative for Life-like rules
- [[chaos-in-cellular-automata](pages/chaos-in-cellular-automata.md)] - the notions behind Kurka's classes
- [[limit-set](pages/limit-set.md)] - nilpotency vs CY1
- [[rule-110](pages/rule-110.md)] - the class-4 rule proved universal
- [[decidability-in-cellular-automata](pages/decidability-in-cellular-automata.md)] - where the undecidability of the classes sits
- [[self-organization](pages/self-organization.md)] - Wolfram's statistical classes from random starts
- [[reachability-in-cellular-automata](pages/reachability-in-cellular-automata.md)] - the degree of the orbit problem as a classification
- [[edge-of-chaos](pages/edge-of-chaos.md)] - Wolfram's classes placed on Langton's order-chaos axis, class IV at the transition
- [[computation-at-the-edge-of-chaos](pages/computation-at-the-edge-of-chaos.md)] - Langton's paper relating the classes to the λ sweep
- [[lambda-parameter](pages/lambda-parameter.md)] - the parameter along which the classes line up

[^1]: [[statistical-mechanics-of-cellular-automata](pages/statistical-mechanics-of-cellular-automata.md)] pp.604, 607 [synthesis] - from a single site, a 1 erased or maintained, or a uniform expanding structure: "These two classes of rules will be termed 'simple'"; "complex" rules give self-similar patterns; "simple rules exhibit simple limit points or limit cycles, while complex rules exhibit phenomena analogous to strange attractors"
[^2]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.8 [synthesis] - in [74] Wolfram experimented from random initial configurations and classified by space-time diagrams into (W1)-(W4); "Wolfram conjectured that class 4 CA are computationally universal"
[^3]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.11 - "Note that gliders in GOL are analogous to the complicated localized structures, or signals, that emerge in class 4 elementary CA."
[^4]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.8 - "The classification due to Wolfram is vague, and it was later formalized by Culik and Yu [17], and they also proved that their classification is undecidable: there is no algorithm to determine in which class a given one-dimensional CA belongs."
[^5]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.9 [synthesis] - (CY1)-(CY4) with "CA belongs to the lowest class whose defining property is satisfied"; "class (1) is not equivalent to nilpotency ... e.g. rule 128 in which the quiescent state 0 spreads killing all 1's"
[^6]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] pp.270-271 [synthesis] — "We can construe FP as a formalization of the first Wolfram class"; Theorem 7: Π⁰₁-complete; Theorem 8; "one should consider a more fine-grained hierarchy based on the complexity of Reachability. The resulting classification is again highly undecidable ... testing for computational universality is Σ⁰₄-complete"
[^7]: [[aucm-ch12-linear-cellular-automata-and-decidability](pages/aucm-ch12-linear-cellular-automata-and-decidability.md)] p.273 — "Even in the one-dimensional case, assertions about long term evolution tend to be undecidable and fully automatic classification is simply impossible."
[^8]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] pp.25-26 [synthesis] - Kurka [48] classes (K1)-(K4); "every CA belongs to exactly one class"; "In two- and higher-dimensional cases class (K4) is empty"; [23]: undecidable for 1D whether a CA belongs to K1, K2 or K3; "The membership problem for class (K4) remains an open problem"
[^9]: [[theory-of-cellular-automata-a-survey](pages/theory-of-cellular-automata-a-survey.md)] p.25 - "CA have the property that if there are no equicontinuity points then the CA is sensitive [48]."
[^10]: [[eppstein-2010-growth-and-decay-in-life-like-ca](pages/eppstein-2010-growth-and-decay-in-life-like-ca.md)] pp.1-2,4 [synthesis] - "one cannot use it to predict which rules are likely to have interesting behavior"; "may for some automata be impossible to decide"; Life "is conventionally classified as Class IV less because the description of that class best fits our observations of Life and more because Life is the archetypical rule"; "the rule B35/S236 ... appears to be in Class III, but can support many complex patterns similar to those in Life"; "many of the most interesting patterns in Life could not have been found in this way"
[^11]: [[eppstein-gliders-in-life-like-cellular-automata](pages/eppstein-gliders-in-life-like-cellular-automata.md)] raw/eppstein-ca-wolfram.md L13 - "Our investigation has turned up gliders in systems that would likely be classified in each of the four classes"
[^12]: [[eppstein-2010-growth-and-decay-in-life-like-ca](pages/eppstein-2010-growth-and-decay-in-life-like-ca.md)] pp.2,9,13-14 [synthesis] - two yes/no questions; fertility settled "in 96% of the cases"; mortality "in approximately 99.8% of the cases"; fertile-and-mortal rules "have differing Wolfram classes"
