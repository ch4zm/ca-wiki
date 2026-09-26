---
title: Lightweight, middleweight and heavyweight spaceships
category: Patterns
summary: The LWSS, MWSS and HWSS - three period-4 Life spaceships that move orthogonally 2 cells every 4 generations (c/2); with the glider they are the spaceships that ordinary random soups produce
tags: [pattern, life, spaceship, lwss, mwss, hwss, orthogonal, c-over-2]
sources: [cgol-ch5-glider-synthesis, cgol-ch4-spaceships-and-moving-objects, cgol-ch1-early-life, fantastic-combinations-of-john-conways-life]
created: 2026-09-25
updated: 2026-09-25
---

# Lightweight, middleweight and heavyweight spaceships

## Description

The **lightweight spaceship** (LWSS), **middleweight spaceship** (MWSS) and
**heavyweight spaceship** (HWSS) are [[spaceship](pages/spaceship.md)]s that move
orthogonally, directly north, south, east or west, unlike the diagonal
[[glider](pages/glider.md)]. All three have period 4 and move 2 cells every 4
generations.[^1] That is c/2, the fastest possible orthogonal speed for a finite
pattern moving into empty space.[^2]

The LWSS is common in random soup; the MWSS and HWSS are rarer.[^3] These three and the
glider are the only spaceships that asymmetric random soups have produced in large-scale
searches; symmetric soups have also produced rarer ones such as the copperhead.[^4][^5] Following the naming, the glider was once called the "featherweight
spaceship".[^6]

**Sparks.** Every second generation the LWSS gives off a dot and a thumb spark, the MWSS
two dots and a thumb, and the HWSS a dot, a domino and a thumb. These sparks destroy
small objects such as blocks and blinkers, which is how puffer debris is trimmed down to
wanted outputs ([[puffer](pages/puffer.md)]).[^7] An [[eater](pages/eater.md)] 1 or eater 2 eats an LWSS or
MWSS. Eating an HWSS takes a large stable eater, a pond and block that rebuild
themselves, or the period-2 *killer toads*.[^8]

**Flotillae and tagalongs.** An *xWSS* means any of the three.[^9]
- Two xWSSes whose sparks interact form a *flotilla*. Flotillae keep the same speed and
  period, so they add little that is new.
- Some pairings are only *pseudo spaceships*: nothing interacts, yet a dead cell is
  overcrowded.
- Tagalongs such as the sidecar and hivenudger ride along; the MWSS tagalong rides in
  front (a *pushalong*).
- The *overweight spaceship* (OWSS), a longer version of the pattern, is unstable alone
  because its 3-cell "spark" survives. Neighbouring xWSSes suppress it, making the OWSS
  one of the most versatile tagalongs; overweight ships of any length can be stabilized.
- The Schick engine and Coe ship are xWSS-based spaceships with large pulsating sparks,
  used to build rakes ([[puffer](pages/puffer.md)]).

**From gliders.** Each can be synthesized from three gliders. Aiming three Gosper glider
guns at each other gives a period-30 LWSS gun. A 4-glider HWSS synthesis with one glider
from each direction is easier to use than the tight 3-glider one ([[object-synthesis](pages/object-synthesis.md)]).[^10]

## Appearances in Sources

- [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] - §4.2: sparks, eaters for them, flotillae, tagalongs, the overweight spaceship
- [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] - period, speed and frequency in soup
- [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] - the c/2 orthogonal limit

## Related Concepts

- [[puffer](pages/puffer.md)] - rakes built from xWSSes
- [[spaceship](pages/spaceship.md)] - the class
- [[glider](pages/glider.md)] - the diagonal counterpart
- [[soup-search](pages/soup-search.md)] - where their natural frequency is measured

[^1]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] pp.7-8 [synthesis] - "the lightweight spaceship (or LWSS for short) ... moves orthogonally (i.e., directly north, south, east, or west), unlike the glider, which moves diagonally"; Fig. 1.10: "a lightweight, middleweight, and heavyweight spaceship. They all have period 4 and travel to the right 2 cells every 4 generations"
[^2]: [[fantastic-combinations-of-john-conways-life](pages/fantastic-combinations-of-john-conways-life.md)] p.5 - "Movement of a finite figure horizontally or vertically into empty space, Conway has also shown, cannot exceed half the speed of light"
[^3]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.7 - "commonly occurring objects, such as the lightweight spaceship"; "Slightly more rare than the lightweight spaceship are the middleweight spaceship (or MWSS) and the heavyweight spaceship (or HWSS)"
[^4]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.28 - Okrasinski's screensaver catalogued over 4.7 × 10^11 ash objects, "but still the only spaceships that turned up were the four that we have already seen (the glider, LWSS, MWSS, and HWSS)"
[^5]: [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] p.111, n.41 - the copperhead "was then found in random ash generated by apgsearch less than a month after its initial discovery"; "The copperhead was found from evolving a random symmetric soup"
[^6]: [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] p.7, n.4 - "the glider was sometimes called the featherweight spaceship in the early days of Life, though this name is very rarely used now"
[^7]: [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] pp.87-88 [synthesis] - "Every second generation, the LWSS emits a dot spark and a thumb spark, the MWSS emits two dot sparks and a thumb spark, and the HWSS emits a dot spark, a domino spark, and a thumb spark"; Fig. 4.12 destroying small objects; used "to adjust the debris left behind by puffers"
[^8]: [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] p.88 [synthesis] - eater 1 and eater 2 destroy an LWSS or MWSS; Fig. 4.13 three HWSS eaters: large stable eater, pond and block reconstructed via a honey bit, and period-2 "killer toads"
[^9]: [[cgol-ch4-spaceships-and-moving-objects](pages/cgol-ch4-spaceships-and-moving-objects.md)] pp.88-90 [synthesis] - "it is often convenient to refer to any of these components as an xWSS"; flotillae; "every flotilla constructed from them will also have the same period and speed"; pseudo spaceships (Fig. 4.15); sidecar, HWSS tagalong, MWSS tagalong, hivenudger (Fig. 4.14); pushalongs; overweight spaceship "is not actually a spaceship at all"; "one of the most versatile of known tagalongs"; "Overweight spaceships of any length can be stabilized"
[^10]: [[cgol-ch5-glider-synthesis](pages/cgol-ch5-glider-synthesis.md)] pp.121,124-126 [synthesis] - Fig. 5.2 period 30 LWSS gun from three Gosper glider guns; Table 5.2 3-glider syntheses of LWSS, MWSS, HWSS; the 3-glider HWSS synthesis "is actually quite difficult to make use of"; "4-glider syntheses of a heavyweight spaceship that consist of one glider coming from each direction"
