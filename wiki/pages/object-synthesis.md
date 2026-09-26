---
title: Glider synthesis (object synthesis)
category: Concepts
summary: Building a Life object by colliding gliders that could arrive from arbitrarily far away - all 71 two-glider collisions, three-glider syntheses of spaceships and oscillators, incremental synthesis in stages, and reverse-engineering from soups; every still life up to 23 cells has a synthesis, any constructible pattern can be built from 15 gliders, and some still lifes can never be synthesized
tags: [concept, life, glider-synthesis, construction, incremental-synthesis, seed]
sources: [tsra-part2-ch5, tsra-lecture-5, cgol-ch5-glider-synthesis]
created: 2026-09-25
updated: 2026-09-26
---

# Glider synthesis (object synthesis)

## Description

A *glider synthesis* builds an object by colliding [[glider](pages/glider.md)]s. Its
value is that guns and rakes already produce gliders. For example, three Gosper glider
guns aimed at each other make a period-30 lightweight spaceship gun. Synthesizing
stationary objects needs a moving glider source, so later gliders do not hit the new
object.[^1] The gliders must be able to arrive from arbitrarily far away. A collision
whose gliders would have hit each other on the way in does not count.[^2]

**Why it matters.** Gliders are the one thing Life can mass-produce and send any distance
unchanged. So an object with a glider synthesis can be built remotely, by aiming guns or
rakes at a chosen spot. It can also be manufactured indefinitely, by a gun for it or a
machine that builds such guns ([[breeder](pages/breeder.md)]). This is von Neumann's
question in Life's terms. Von Neumann asked for a [[universal-constructor](pages/universal-constructor.md)],
an automaton that builds any automaton from its description, as the construction
analogue of a universal Turing machine. In his 29-state rule
([[von-neumann-29-state-ca](pages/von-neumann-29-state-ca.md)]) such a constructor builds
every initially quiescent machine from its tape description.[^3][^4] In Life the parts
are gliders and assembly is collision. "Every constructible pattern has a glider
synthesis" is the Life form of universal construction, and the number of gliders an
object needs works as a measure of how complex it really is (own reasoning, from the
sources on this page).

**Two gliders.** There are exactly 71 ways two gliders can collide, found by trying every
arrangement.[^5]
- Products include the block, boat, beehive, blinker, loaf, pond, eater 1, bi-block,
  traffic light, honey farm, B-heptomino, pi-heptomino and lumps of muck. Some collisions
  leave nothing.
- The *two-glider mess* takes 530 generations to stabilize.
- The *kickback* produces a glider moving in a new direction, useful for routing gliders
  around tight spots.

**Three or more.** Three-glider collisions are too many to catalogue.[^6]
- Useful ones make the LWSS, MWSS, HWSS, pentadecathlon, pulsar, queen bee, R-pentomino
  and switch engine.
- *Tees* make a glider perpendicular to all three inputs.
- One makes a glider-producing switch engine plus junk, the only known three-glider route
  to infinite growth.
- Twin bees need at least four gliders. Spread-out syntheses with one glider per direction
  (such as a 4-glider HWSS) are often easier to use than tighter ones with fewer gliders.
- The [[gosper-glider-gun](pages/gosper-glider-gun.md)] can be built from its parts with
  10 gliders; 8 is the known minimum.

**Incremental synthesis.** Rather than timing many gliders at once, build a simple still
life first, then change it a few gliders at a time. The stages can be arbitrarily far
apart.[^7]
- A 12-glider incremental synthesis of the fumarole needs at most 3 synchronized gliders
  per stage.
- A pond becomes a ship, then a queen bee, giving a Gosper gun with never more than two
  synchronized gliders.
- Oscillators are usually synthesized stator first, then rotor, which is why billiard
  tables are hard to synthesize.
- Composite moving objects (rakes, Schick engines, Coe ships, Corderships) are built by
  synthesizing their components with compatible timing ([[puffer](pages/puffer.md)],
  [[cordership](pages/cordership.md)]).

**Finding new syntheses.** The most common method starts from a soup that happened to
produce the object. Rewind it until only familiar reactions remain, then rebuild those
from known syntheses, swapping awkward pieces for easier ones with the same active cells.
Rich's p16, found in soup, got an 18-glider synthesis within a day this way.[^8]

**Coverage.**
- Every still life with up to 23 live cells now has a glider synthesis; the 23-cell
  project finished in December 2025.[^9]
- For still lifes of 14-17 cells, syntheses of fewer gliders than cells are known.[^10]
- Any pattern that can be built by gliders at all can be built from just 15 gliders. The
  method is a universal constructor that encodes the rest of the recipe in the distance of
  an incoming object, the [[reverse-caber-tosser](pages/reverse-caber-tosser.md)].[^11]
- Not every pattern is synthesizable. Törmä and Salo (2022) found a configuration that, if
  it occurs at any generation, must have been in the same place in every earlier one. A
  306-cell still life containing it cannot be built by any method. It answers a question
  on which Conway had set a $50 prize.[^12]

The largest database of cheapest-known glider conversions, Shinjuku, underlies the
syntheses listed on Catagolue.[^13] The one-direction, one-at-a-time form of synthesis
is a [[slow-salvo](pages/slow-salvo.md)].

## Appearances in Sources

- [[cgol-ch5-glider-synthesis](pages/cgol-ch5-glider-synthesis.md)] - the whole chapter

## Related Concepts

- [[universal-constructor](pages/universal-constructor.md)] - von Neumann's question that glider synthesis answers for Life
- [[reverse-caber-tosser](pages/reverse-caber-tosser.md)] - the 15-glider universal constructor
- [[slow-salvo](pages/slow-salvo.md)] - the restricted form, equally powerful
- [[breeder](pages/breeder.md)] - rakes synthesizing guns
- [[soup-search](pages/soup-search.md)] - soups are the main source of new syntheses
- [[still-life](pages/still-life.md)] - the objects most syntheses start from
- [[garden-of-eden](pages/garden-of-eden.md)] - a related limit on what can arise
- [[catagolue](pages/catagolue.md)] - keeps the cheapest known glider syntheses and takes submissions
- [[construction-arm](pages/construction-arm.md)] - Life's construction machinery, a block elbow moved by gliders
- [[initially-quiescent-automaton](pages/initially-quiescent-automaton.md)] - the class von Neumann's constructor builds from tape descriptions

[^1]: [[cgol-ch5-glider-synthesis](pages/cgol-ch5-glider-synthesis.md)] pp.121-122 [synthesis] - Fig. 5.1 3-glider synthesis of an LWSS; Fig. 5.2 "a period 30 lightweight spaceship gun" from three Gosper glider guns; for stationary objects "the glider source has to be moving"
[^2]: [[cgol-ch5-glider-synthesis](pages/cgol-ch5-glider-synthesis.md)] p.122 - "we require that the gliders in a synthesis could arrive at their positions from arbitrarily far away"; Fig. 5.3 is "not a valid 3-glider synthesis"
[^3]: [[tsra-lecture-5](pages/tsra-lecture-5.md)] pp.83-84 [synthesis] - the approach is modeled on Turing's universal automata; given a description chain φ(X), the constructing automaton consumes it and builds X from free parts
[^4]: [[tsra-part2-ch5](pages/tsra-part2-ch5.md)] pp.280-286 [synthesis] - the construction algorithm driving the two-path arm; M_c constructs every initially quiescent M from D(M)
[^5]: [[cgol-ch5-glider-synthesis](pages/cgol-ch5-glider-synthesis.md)] pp.122-124, Table 5.1 [synthesis] - "all 71 possible 2-glider collisions"; the two-glider mess "takes 530 generations to stabilize"; "the kickback reaction, since it produces an output glider traveling in a different direction"; n.1 no mathematical way to arrive at 71
[^6]: [[cgol-ch5-glider-synthesis](pages/cgol-ch5-glider-synthesis.md)] pp.124-126, Tables 5.2-5.3 [synthesis] - 3-glider syntheses; tees; glider-producing switch engine "the only known way of generating infinite growth with just 3 gliders"; twin bees "requires at least 4 gliders"; 4-glider HWSS with one glider from each direction; n.4 Gosper gun from parts needs 10 gliders, "as few as 8 gliders"
[^7]: [[cgol-ch5-glider-synthesis](pages/cgol-ch5-glider-synthesis.md)] pp.126-131 [synthesis] - incremental synthesis; the different stages "can take place as many generations apart from each other as we like"; Fig. 5.5 12-glider fumarole; Fig. 5.6 Gosper glider gun via pond, ship, queen bee; stator first then rotor; billiard tables; syntheses of the ecologist, Schick engine, Coe ship and Cordership
[^8]: [[cgol-ch5-glider-synthesis](pages/cgol-ch5-glider-synthesis.md)] pp.131-134 [synthesis] - reverse-engineering from a soup; Rich's p16 from honey farm predecessors, B-heptominoes, blocks and beehives; B-heptominoes replaced by eater 1s; 18-glider synthesis (n.6 Charlie Neder, "less than a day after the oscillator's discovery")
[^9]: https://conwaylife.com/wiki/Glider_synthesis (2026-06-07) - projects "to complete syntheses for all still lifes up to specific populations were completed for ... 21 bits in November 2022, 22 bits in August 2024, and 23 bits in December 2025"
[^10]: [[cgol-ch5-glider-synthesis](pages/cgol-ch5-glider-synthesis.md)] p.147 [synthesis] - "synthesize all small still lifes in fewer than 1 glider per live cell. This project was completed for 14-, 15-, 16-, and 17-cell still lifes"
[^11]: https://en.wikipedia.org/wiki/Glider_(Conway's_Game_of_Life) (2026-08-18) - "anything that can be synthesized with gliders, can be synthesized with certain constructions called 'universal constructors'. There is a universal constructor that starts with only 15 gliders"; https://conwaylife.com/wiki/Reverse_caber_tosser (2025-06-01) - "a recipe is encoded in the distance between an approaching c/12 diagonal object ... and the origin"
[^12]: [[cgol-ch5-glider-synthesis](pages/cgol-ch5-glider-synthesis.md)] p.147 [synthesis] - Törmä and Salo (January 2022): a configuration that "if it occurs at any generation, then it must occur at the same location in all previous generations"; "a 306-cell still life that contains this configuration of cells, and thus cannot be constructed by glider synthesis or any other method"; n.21 Conway's $50 prize (October 1972)
[^13]: [[cgol-ch5-glider-synthesis](pages/cgol-ch5-glider-synthesis.md)] p.147 [synthesis] - "The largest database of glider syntheses that is currently maintained, Shinjuku, contains hundreds of thousands of the cheapest-known ways of using gliders to convert one object into another"; n.22 catagolue.hatsya.com/syntheses
