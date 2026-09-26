---
title: Reverse caber tosser
category: Patterns
summary: A universal constructor with a small, bounded starting population that reads its construction recipe from the distance to a receding c/12 object, one bit per glider round trip; its 15-glider form shows that any glider-constructible pattern can be built from just 15 gliders, though running a real recipe takes exponentially many generations
tags: [pattern, life, universal-constructor, rct, glider-synthesis, switch-engine, gpse, cordership]
sources: [cgol-ch5-glider-synthesis]
created: 2026-09-25
updated: 2026-09-25
---

# Reverse caber tosser

> All sources on this page were read as web-search excerpts; the full LifeWiki pages
> could not be fetched.

## Description

A *reverse caber tosser* (RCT) is a universal constructor with a small, bounded
population. It encodes the recipe for what it builds in the *distance* between the
origin and an approaching c/12 diagonal object, such as a
[[cordership](pages/cordership.md)] or a puffer.[^1]
- One or more gliders shuttle between that object and fixed circuitry, and the time
  between collisions halves on each trip.
- Each trip consumes the least significant bit of the recipe, which is usually routed to a
  universal construction arm.
- The recipe is stored in a single number, the starting distance, so a fixed handful of
  gliders can hold a recipe of any length.

The name comes from the [[caber-tosser](pages/caber-tosser.md)], a pattern that behaves like a time-reversed
RCT.[^1] Caber tossers are patterns whose population grows like log(t); Dean Hickerson
built one.[^2] The first constructed logarithmic-growth pattern was a caber tosser, whose
population grows logarithmically while its bounding box still grows linearly.[^3]
Corderships' rear sparks can turn gliders back the way they came, which is what these
constructions rely on.[^4]

**Why it matters.** The construction arm makes the RCT a universal constructor, and the
RCT plus arm is itself glider-synthesizable. So there is a fixed number N such that every
glider-constructible pattern can be synthesized from at most N gliders.[^5]
- The best known bound is **N = 15**.[^6]
- Combined with a universal computer, it implies arbitrarily slow spaceships that in one
  phase consist of only N gliders.[^5]
- Johnston and Greene call the method an "extremely convoluted process" that places some
  gliders "unimaginably far away".[^7]
- It made every constructible still life synthesizable with at most one glider per live
  cell ([[object-synthesis](pages/object-synthesis.md)]).[^8]

**Impractical to run.** Building anything takes a number of generations exponential in
the recipe length, which defeats even HashLife. In April 2022 Adam P. Goucher published an
example with a 2-kilobit recipe. It produces a shillelagh, amid a vast amount of debris,
after about 5.23 × 10^615 generations. It takes two hours to run in Golly with a helper
script, and wall-clock time grows roughly with the cube of the recipe length.[^9]

**How the bound came down.**
- **2015.** Gustavo Ramos Rehermann conjectured that the 11.8-million-cell caterpillar
  spaceship could be built from 386 or fewer gliders.[^10]
- **June 2018.** The first RCT assembly was synthesized by Goldtiger997, giving N ≤ 329
  and settling that conjecture. Dave Greene announced it on his blog three days
  later.[^10]
- **June 2018.** Goucher noted that a glider-producing
  [[switch-engine](pages/switch-engine.md)] (GPSE) emits the same stream as a period-256
  glider gun but is far cheaper to synthesize.[^11]
  - Chris Cain rebuilt the fixed circuitry from 12 GPSEs with a 4-glider GPSE synthesis.
  - On 28 June 2018 he completed a 59-glider RCT. Its minimum population, 278, implies an
    extremely high-period knightship smaller than the 282-cell Sir Robin.
- **July 2018.** Cain and Greene reduced it to 35 gliders using 6 GPSEs, with minimum
  population 143, which also implies a 143-cell sawtooth.[^12]
- **2020.** Cain reached 33 gliders, and on 21 July 2020 Goucher reached 32 by modifying
  the "Sakapuffer" ark synthesis.[^13]
- **September 2020.** MathAndCode replaced the ark with a cheaper GPSE and dropped the
  circuit that told the approaching glider's timing apart, since a GPSE can do that
  itself. Four GPSEs at 4 gliders each plus one glider for the construction arm gave 17
  gliders. Goucher showed the arm universal the same day.[^13]
- **21 April 2022.** dani found a 7-glider synthesis of two GPSEs together, giving 16.
  Oscar Cunningham and Goucher showed the extra "dirty" gliders could help build the
  construction arm at no cost.[^14]
- **2022.** The 15-glider version, the current bound.[^6]

The RCT placed third in the ConwayLife.com Pattern of the Year vote for 2018, behind the
0E0P metacell and Sir Robin. Its 15-glider version tied for first in 2022.[^15]

## Appearances in Sources

- [[cgol-ch5-glider-synthesis](pages/cgol-ch5-glider-synthesis.md)] - p.147, n.20: the reverse caber tosser method behind the bounded-glider result
- https://conwaylife.com/wiki/Reverse_caber_tosser - definition, applications, runtime, history (search excerpts)

## Related Concepts

- [[caber-tosser](pages/caber-tosser.md)] - the forward version
- [[object-synthesis](pages/object-synthesis.md)] - the RCT bounds every synthesis at 15 gliders
- [[switch-engine](pages/switch-engine.md)] - glider-producing switch engines are its fixed circuitry
- [[cordership](pages/cordership.md)] - the receding c/12 object that encodes the recipe
- [[slow-salvo](pages/slow-salvo.md)] - construction arms build from slow salvos

[^1]: https://conwaylife.com/wiki/Reverse_caber_tosser (2025-06-01, search excerpt) - "a universal constructor with a small bounded population, where a recipe is encoded in the distance between an approaching c/12 diagonal object (such as a Cordership or puffer) and the origin. One or more gliders shuttle between the Cordership and the fixed circuitry, causing the times between collisions to repeatedly halve"; "named by analogy with the caber tosser which behaves as a time-reversed version thereof. Each iteration, the least significant bit of the recipe is consumed by the circuitry and typically routed to a universal construction arm"
[^2]: https://conwaylife.com/wiki/Sublinear_growth (search excerpt) - "Caber tossers are a family of patterns that have population in generation T asymptotically proportional to log(T)"; http://www.conwaylife.com/ref/lexicon/lex_i.htm (search excerpt) - "Dean Hickerson has found many patterns with unusual growth rates, such as sawtooths and a caber tosser"
[^3]: https://conwaylife.com/wiki/Logarithmic_growth (2020-10-27, search excerpt) - "The first such pattern constructed was the caber tosser whose population is logarithmic, but whose bounding box still grows linearly"
[^4]: https://playgameoflife.com/lexicon/Cordership (search excerpt) - "Some perturbations reflect gliders back the way they came, and can be used for constructions such as the caber tosser"
[^5]: https://conwaylife.com/wiki/Reverse_caber_tosser (2025-06-01, search excerpt) - "a bounded-population initial setup can construct an arbitrary glider-constructible pattern. Since the reverse caber-tosser (together with the attached construction arm) is itself synthesisable, this implies the existence of some fixed integer N such that any glider-constructible pattern can be synthesised in at most N gliders. In combination with a universal computer, this implies the existence of arbitrarily slow spaceships which, in one phase, consist only of N gliders"
[^6]: https://conwaylife.com/wiki/Reverse_caber_tosser (2025-06-01, search excerpt) - "Currently, the best upper bound on N is 15 gliders"; https://en.wikipedia.org/wiki/Glider_(Conway's_Game_of_Life) (2026-08-18, search excerpt) - "There is a universal constructor that starts with only 15 gliders, with a construction algorithm published in 2022"
[^7]: [[cgol-ch5-glider-synthesis](pages/cgol-ch5-glider-synthesis.md)] p.147, n.20 - "This can only be done via an extremely convoluted process known as the reverse caber tosser method, or RCT for short, which involves putting some of the gliders unimaginably far away, in a way that encodes an arbitrarily long slow-salvo construction recipe"
[^8]: https://conwaylife.com/wiki/Reverse_caber_tosser (2025-06-01, search excerpt) - "Because all still lifes up to 17 bits have explicit constructions with no more than 16 gliders, this discovery had the side effect of proving that all constructible still lifes can be synthesized with no more than one glider per bit"
[^9]: https://conwaylife.com/wiki/Reverse_caber_tosser (2025-06-01, search excerpt) - "it takes a number of generations exponential in the recipe length to construct a given glider synthesis, thereby cancelling out any potential speedup from Hashlife"; "On April 16, 2022, Goucher published an example pattern with a 2-kilobit recipe ... which produces a shillelagh (along with a massive amount of additional debris) after approximately 5.23 × 10^615 generations. As this takes two hours to run, and the total wall-clock runtime appears to be cubic in the recipe length"
[^10]: https://conwaylife.com/wiki/Reverse_caber_tosser (2025-06-01, search excerpt) - "The assembly was later synthesised by Goldtiger997, providing the explicit upper bound of N <= 329. This settled a 2015 conjecture by Gustavo Ramos Rehermann that the Caterpillar can be built in 386 gliders or fewer"; "Three days later, Dave Greene wrote a blog post announcing this discovery"
[^11]: https://conwaylife.com/wiki/Reverse_caber_tosser (2025-06-01, search excerpt) - "the glider stream produced by a glider-producing switch engine is identical to that of a period-256 glider gun, but much cheaper to synthesise. Chris Cain proceeded to redesign the reverse caber-tosser to replace all of the fixed circuitry with just 12 glider-producing switch engines"; "On 28 June 2018, Chris Cain completed a 59-glider synthesis ... The minimum population attained is 278, which implies the existence of an extremely high-period knightship with a smaller population than the 282-cell Sir Robin"
[^12]: https://conwaylife.com/forums/viewtopic.php?start=175&t=3347 (2018-07-06, search excerpt) - "Here is the 35 glider synthesis"; "Just 6 GPSE's now and the minimum population is 143"; "this implies the existence of a 143-cell sawtooth"; https://conwaylife.com/wiki/Chris_Cain (search excerpt) - "Together with Dave Greene, he reduced the size of the reverse caber-tosser to 35 gliders, a record that remained unbroken until 2020, when he reduced it again to 33 gliders"
[^13]: https://conwaylife.com/wiki/Reverse_caber_tosser (2025-06-01, search excerpt) - "On 21st July 2020, Adam P. Goucher was able to remove a glider by modifying the 'Sakapuffer' ark synthesis, reducing the total cost to 32 gliders"; MathAndCode (September 2020) replaced the ark with a GPSE and eliminated the timing-detection circuitry; "universal construction can be performed with 17 gliders: 4 for each of the 4 GPSEs, and a final glider to create the construction arm"; universality "demonstrated by Adam P. Goucher later that day"
[^14]: https://conwaylife.com/wiki/Reverse_caber_tosser (2025-06-01, search excerpt) - "On 21st April 2022, dani improved this to 16 gliders, by finding a 7 glider synthesis for two GPSEs together ... Oscar Cunningham and Adam P. Goucher showed that these could be used in the creation of the construction arm at no extra cost"
[^15]: https://conwaylife.com/wiki/Reverse_caber_tosser (2025-06-01, search excerpt) - "ranked third place in the Pattern of the Year 2018 competition on the ConwayLife.com forums, behind the 0E0P metacell and Sir Robin. Its 15-glider version tied for first in 2022"
