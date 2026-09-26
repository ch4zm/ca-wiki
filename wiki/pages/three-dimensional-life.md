---
title: Three-dimensional Life (B6/S567, B5/S45, B3/S3)
category: Rules
summary: Carter Bays's three 3D rules that pass his Game of Life test - B6/S567 and B5/S45 on the 26-neighbour cubic grid and B3/S3 on the 12-neighbour grid of packed spheres; B6/S567 runs Conway's Life exactly on two adjacent planes, and walls built in it can hold infinitely many parallel copies of Life
tags: [rule, three-dimensional, gl-rule, life-5766, life-4555, life-3333, glider, sphere-packing]
sources: [bays-1987-candidates-for-the-game-of-life-in-three-dimensions]
created: 2026-09-25
updated: 2026-09-25
---

# Three-dimensional Life (B6/S567, B5/S45, B3/S3)

## Description

In three dimensions a cube touches 26 others, so there are 123,201 rules of Bays's
count-range form. Birth on 4 or fewer neighbours gives unlimited growth, and birth needing
10 or more rules out gliders. Of the rules Bays tried, two on the cubic grid pass his
Game of Life test ([[gl-rule](pages/gl-rule.md)]), and one more on a different 3D
grid.[^1] Bays names them by his four numbers E_l E_u F_l F_u (survival range, then birth
range); the B/S forms here are translations (own reasoning).

**Life 5766 (B6/S567): Conway's Life inside 3D.** It makes many small stable forms, well
over 100 that fit in a 4 × 4 × 4 cube, many of them asymmetric.[^2] Its key property:[^3]
- Copy a 2D Life pattern onto two adjacent planes. It evolves exactly as in
  [[game-of-life](pages/game-of-life.md)], generation by generation, as long as no dead
  neighbour ever has six live neighbours and no live cell has five.
- Many small Life objects meet that condition, including the [[glider](pages/glider.md)]
  and some larger oscillators. The glider gun does not.
- Collisions usually break the condition, and the pattern then swells into a rounded 3D
  mass that usually dies.
- A *time-space barrier*, a flat sheet where every live cell has seven neighbours, allows
  no births in the planes next to it. Two barriers four planes apart confine all activity
  to the two middle planes, so the whole of Conway's universe runs between them. A stack of
  barriers gives infinitely many parallel Life universes.

Bays concludes that no 3D rule of this form behaves more like Conway's Life.[^3]

**Life 4555 (B5/S45): its own universe.** It is Conway's four numbers each plus two. It
takes longer to settle than 5766, leaving more room for intermediate reactions, and its
small natural forms are usually symmetric.[^4]
- It has its own 10-cell glider of period 4, moving √2 cells per period in any of 12
  directions.
- A Conway object has an analog only if it is a still life in which every live cell has
  exactly two neighbours, so any Conway pattern that changes has none.
- Its soup residue is sparse: in one experiment, live density was about 0.0005.
- A glider hitting a small object usually destroys both, but some collisions make new
  objects; in one, a glider and a blinker turn into a glider heading a different way.
- Large stable forms can be built by hand but never arise from soup.

Both rules settle a random 70 × 70 × 70 soup in about 30 to 70 generations.[^4]

**Life 3333 (B3/S3) on packed spheres.** On the grid of densely packed spheres each cell
has 12 neighbours. Counting bounds force any Game of Life there to have birth on exactly 3,
and B3/S3 qualifies. It has a 7-cell "tadpole" glider and a larger glider that looks like
a frog, and every object found so far has some symmetry.[^5]

**Other neighbourhoods.** Counting only face, edge or corner neighbours of the cube gives
more rules. Gliders turned up only with face-plus-edge and corner-plus-edge neighbours
(both under B4/S45), and there random soups grow without bound.[^6] The face-only case is
the 3D [[von-neumann-neighbourhood](pages/von-neumann-neighbourhood.md)].

## Appearances in Sources

- [[bays-1987-candidates-for-the-game-of-life-in-three-dimensions](pages/bays-1987-candidates-for-the-game-of-life-in-three-dimensions.md)] - the whole paper

## Related Concepts

- [[gl-rule](pages/gl-rule.md)] - the test these rules pass
- [[game-of-life](pages/game-of-life.md)] - embedded exactly in Life 5766
- [[moore-neighbourhood](pages/moore-neighbourhood.md)] - its 3D form is the 26-cell neighbourhood used here
- [[triangular-neighbourhood](pages/triangular-neighbourhood.md)], [[hexagonal-neighbourhood](pages/hexagonal-neighbourhood.md)] - Bays's 2D grids

[^1]: [[bays-1987-candidates-for-the-game-of-life-in-three-dimensions](pages/bays-1987-candidates-for-the-game-of-life-in-three-dimensions.md)] p.375 [synthesis] - "a cell can have from 0 to 26 living neighbors"; 123,201 possible rules; Theorems 2 and 3; "only R = (4555) and R = (5766) satisfy definition 1"
[^2]: [[bays-1987-candidates-for-the-game-of-life-in-three-dimensions](pages/bays-1987-candidates-for-the-game-of-life-in-three-dimensions.md)] p.379 - "the three environment states allow for a large number of small stable asymmetric objects. For example, if we confine our scope to the stable forms that can be contained within a 4 x 4 x 4 cube, there are well over 100 varieties"
[^3]: [[bays-1987-candidates-for-the-game-of-life-in-three-dimensions](pages/bays-1987-candidates-for-the-game-of-life-in-three-dimensions.md)] pp.379-384 [synthesis] - Definitions 4-6 (expansion, projection, analog); Theorem 7; Corollary 8, 5766 "yields behavior that is more analogous to Conway's Life than any other three-dimensional rule that we may construct"; "Conway's glider has an analog under (5766) ... there is no analog for the 'glider gun'"; collisions form "a roundish three-dimensional mass that usually dies rather quickly"; time-space barriers, "an infinite number of parallel Conway Life universes"
[^4]: [[bays-1987-candidates-for-the-game-of-life-in-three-dimensions](pages/bays-1987-candidates-for-the-game-of-life-in-three-dimensions.md)] pp.379,384,387,390-391 [synthesis] - 4555 "is formed simply by adding 2 to Conway's rule"; "requires more time to 'settle down'"; small forms "usually exhibit symmetry"; Theorem 9 (analog iff "each living cell in the Conway object has exactly two neighbors"); Corollary 10; "both rules will stabilize after about 30 to 70 generations"; the ten-element period-4 glider moving √2 "in one of twelve directions"; Table 3 residue density about .0005; Figure 10 glider-blinker collision yielding a new glider; manufactured forms "would never be found by conducting primordial soup experiments"
[^5]: [[bays-1987-candidates-for-the-game-of-life-in-three-dimensions](pages/bays-1987-candidates-for-the-game-of-life-in-three-dimensions.md)] pp.393-396 [synthesis] - "densely packed spheres", 12 neighbours; Theorems 11 and 12; "if any Game of Life exists, it must be of the form ElEu33. The only rule that seems to exhibit gliders is (rather nicely) R = (3333)"; Figure 13, "the 10-element big glider resembles a frog. The 7-element little glider is the 'tadpole'"; "every stable or oscillating object so far discovered exhibits symmetry"
[^6]: [[bays-1987-candidates-for-the-game-of-life-in-three-dimensions](pages/bays-1987-candidates-for-the-game-of-life-in-three-dimensions.md)] p.393 - six face, twelve edge and eight corner neighbours; "Two additional gliders have been found - one in Life.011 4544 and another in Life.110 4544. These are the only rules that seem to support gliders ... primordial soup experiments with Life.110 4544 and Life.011 4544 usually lead to unbounded growth"
