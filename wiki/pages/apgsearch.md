---
title: apgsearch
category: Concepts
summary: Adam P. Goucher's Ash Pattern Generator Search - the soup-search program that runs random 16 × 16 soups to stability, names every ash object by its apgcode and uploads the tallies to Catagolue; symmetric, inflated and GPU-screened soups, dozens of rule families, and the source of most natural discoveries in Life since 2014
tags: [concept, software, soup-search, census, apgsearch, catagolue, apgcode, symmetry]
sources: [lifewiki-apgsearch, lifewiki-catagolue, cgol-ch1-early-life]
created: 2026-09-25
updated: 2026-09-25
---

# apgsearch

## Description

**What it is.** apgsearch, the Ash Pattern Generator Search, is Adam P. Goucher's
automated [[soup-search](pages/soup-search.md)] program. It generates soups (16 × 16 and
asymmetric by default), runs each until it stabilizes, and records what is left: still
lifes, oscillators, spaceships, periodic linear-growth patterns and "unusual growth". In
Life it also flags methuselahs, diehards and soups with very large final populations.
Results are uploaded to the [[catagolue](pages/catagolue.md)] census, where they are
peer-reviewed.[^1] Each object is identified by a unique code, its *apgcode*, which is
what lets billions of independent searches be added together.[^2]

**Symmetry as a search lever.** Asymmetric soups (C1) sample what Life does "naturally".
apgsearch can also force soups to be symmetric: two- and four-fold rotations (C2, C4) and
one, two or four reflection lines (D2, D4, D8), with suffixes for where the centre sits.
Long thin soups (8 × 32 up to 1 × 256) and "inflated" soups, in which each cell becomes a
2 × 2 block, are further variants.[^3] Symmetry makes large symmetric objects far more
likely, which is why many oscillators first turned up in symmetric soups (112P15, Rich's
p16), and why the copperhead appeared from a D2 soup a month after it was first
found.[^4]

**GPU screening.** Since version 5, a CUDA GPU mode runs soups quickly and passes only the
"interesting" ones (those that fail to settle to period 6 within 21,000 generations, or
reach the edge of the GPU's finite universe) to the CPU for a full census. Because this
skips ordinary soups, its results go to separate symmetries named G and H in place of C
and D, so they do not distort the main statistics.[^5]

**Other rules.** Versions 4 and later, built on the lifelib simulation library, search far
beyond Life: arbitrary outer-totalistic rules,
[[isotropic-non-totalistic-rule](pages/isotropic-non-totalistic-rule.md)]s,
[[higher-range-outer-totalistic-rule](pages/higher-range-outer-totalistic-rule.md)]s up
to range 5, [[larger-than-life](pages/larger-than-life.md)] up to range 7, the
[[hexagonal-neighbourhood](pages/hexagonal-neighbourhood.md)], two-state B0 rules,
[[generations-rule](pages/generations-rule.md)] variants of all of these, and custom Golly
rule tables ([[ruleloader](pages/ruleloader.md)]).[^6]
- The von Neumann neighbourhood is reached indirectly, as a special case of isotropic
  Moore rules. Inflated soups on suitable rules emulate block cellular automata on the
  [[margolus-neighbourhood](pages/margolus-neighbourhood.md)].
- In practice only non-exploding rules can be censused, unless a symmetry is known never
  to explode.

**Limits.** Separation of objects can fail for large non-interacting groups, for most
groups outside Life, and for pseudo still lifes. Oscillators and spaceships with periods
over 1,048,576 are classed as PATHOLOGICAL, and high-period linear growth may be reported
only as zz_LINEAR.[^7]

**What it found.**[^8]
- The first natural nonstandard spaceship flotilla (an LWSS on an HWSS), during alpha
  testing, and many flotillas since.
- The pufferfish, from symmetric soup ash, and the pony express, the first natural
  [[puffer](pages/puffer.md)] other than the basic [[switch-engine](pages/switch-engine.md)]
  forms, made from two switch engines.
- Rob's p16, found by GPU search: the smallest known period-16
  [[oscillator](pages/oscillator.md)] and the first asymmetric object found by soup search
  since the 1980s. The Charity Engine distributed project found the smallest known p21
  and p25 oscillators (32P21, 30P25).
- The longest-lived known 16 × 16 [[methuselah](pages/methuselah.md)], 52513M.
- In asymmetric soups, rare objects such as the loafer, the Coe ship, the lightweight
  Schick engine and the sidecar. Soups submitted to Catagolue have also given cheaper
  glider syntheses ([[object-synthesis](pages/object-synthesis.md)]).

**Lineage.** Versions 0.x and 1.x (2014-2015) were Python scripts run inside Golly; 1.x
added symmetric soups and uploading. Versions 2.x-5.x are C++ command-line programs:
apgnano (Life only, hand-tuned assembly), apgmera (any outer-totalistic rule), and apgluxe
(lifelib, with every later rule family and the GPU mode).[^9]

## Appearances in Sources

- [[lifewiki-apgsearch](pages/lifewiki-apgsearch.md)] - the whole article
- [[lifewiki-catagolue](pages/lifewiki-catagolue.md)] - apgsearch as Catagolue's main client
- [[cgol-ch1-early-life](pages/cgol-ch1-early-life.md)] - the state of the art in soup searching

## Related Concepts

- [[catagolue](pages/catagolue.md)] - the census it feeds
- [[soup-search](pages/soup-search.md)] - the method it automates
- [[methuselah](pages/methuselah.md)], [[spaceship](pages/spaceship.md)], [[oscillator](pages/oscillator.md)] - the object classes it records

[^1]: [[lifewiki-apgsearch](pages/lifewiki-apgsearch.md)] L15 - "It generates soups, which by default are asymmetric and 16 × 16, and runs them until stabilization, recording any resulting still lifes, oscillators, spaceships, periodic linear infinite growth patterns, and "unusual growth" patterns. More recent versions also detect soups which are long-lived methuselahs and diehards as well as soups with large final populations. ... Version 1.x and later upload the results to the online database Catagolue and have a peer-review process for verifying hauls submitted to the site."
[^2]: [[lifewiki-catagolue](pages/lifewiki-catagolue.md)] L33 - "Each resulting object is identified by apgsearch by its unique apgcode"
[^3]: [[lifewiki-apgsearch](pages/lifewiki-apgsearch.md)] L45-57 [synthesis] - C2, C4, D2, D4 and D8 symmetric soups; 8x32, 4x64, 2x128 and 1x256 pseudo-symmetries; "All symmetries can be "inflated" using the "i" prefix, replacing each cell in the sample soup with a 2 × 2 alignment of cells in the same state"
[^4]: [[lifewiki-apgsearch](pages/lifewiki-apgsearch.md)] L77-78,L91 [synthesis] - 112P15 and Rich's p16 "first discovered in the ash of a symmetric soup"; "the copperhead first emerged from a D2_+2 soup in April 2016 only a month after its initial discovery by zdr"
[^5]: [[lifewiki-apgsearch](pages/lifewiki-apgsearch.md)] L61,L220 [synthesis] - "Since version 5.x, apgsearch supports soup searching on a GPU using CUDA"; "the results are uploaded to separate symmetries on Catagolue to avoid distorting the main census statistics, with C and D replaced with G and H respectively"; n.4 "A soup is deemed interesting if it fails to stabilize with period 6 within 21,000 generations or reaches the boundary of the finite universe"
[^6]: [[lifewiki-apgsearch](pages/lifewiki-apgsearch.md)] L16,L93-107 [synthesis] - "Versions 4.x and later of apgsearch use a backend known as lifelib"; "only non-exploding rules can reasonably be investigated in practice unless a certain symmetry can be assured to never explode"; list of supported rule types; von Neumann "indirectly simulated by isotropic Moore rules and the Margolus neighbourhood (specifically block cellular automata) can be simulated by inflated soups on specific rules"
[^7]: [[lifewiki-apgsearch](pages/lifewiki-apgsearch.md)] L121-122 [synthesis] - "it can fail to properly separate larger non-interacting groups, or groups of any size in non-Life rules"; maximum period "1,048,576 in apgluxe"; "higher-period objects are classified as PATHOLOGICAL. High-period linear-growth patterns may not be identified and instead reported as zz_LINEAR"
[^8]: [[lifewiki-apgsearch](pages/lifewiki-apgsearch.md)] L74-91 [synthesis] - LWSS on HWSS 1 found "during alpha testing"; pufferfish; pony express "a p1152 made from two switch engines"; Rob's p16 "via GPU search, becoming the smallest known p16 oscillator and the first asymmetric object discovered by soup search since the 1980s"; 52513M; 32P21 and 30P25 by Charity Engine; "Other rare objects found by apgsearch in asymmetric soups are ... the Coe ship, the lightweight Schick engine, the sidecar, the loafer"; "cheaper glider syntheses for many patterns"
[^9]: [[lifewiki-apgsearch](pages/lifewiki-apgsearch.md)] L125-196 [synthesis] - Python versions 0.x (September 2014) and 1.x (February 2015, symmetric soups and Catagolue upload); C++ versions 2.x apgnano (Life128, C1 B3/S23 only), 3.x apgmera (arbitrary outer-totalistic rules), 4.x apgluxe (lifelib), 5.x (CUDA)
