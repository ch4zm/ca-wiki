---
title: Catagolue
category: Concepts
summary: Adam P. Goucher's ongoing distributed census of the ash of random soups (catagolue.hatsya.com), fed by apgsearch since 2015 - hundreds of trillions of Life soups, thousands of trillions of objects of over half a million kinds, peer-reviewed hauls, 20,000+ other rules, and a general inventory of patterns, glider syntheses and guns
tags: [concept, census, soup-search, catagolue, apgsearch, natural-history, glider-synthesis]
sources: [lifewiki-catagolue, lifewiki-apgsearch]
created: 2026-09-25
updated: 2026-09-25
---

# Catagolue

## Description

**What it is.** Catagolue (from "catalogue" and "GoL") is an ongoing distributed census
of naturally occurring ash objects, run by Adam P. Goucher since February 2015 at
catagolue.hatsya.com. It is fed mainly by [[apgsearch](pages/apgsearch.md)]: every
contributor's machine evolves random soups and uploads a tally of the objects left,
keyed by apgcode. The site gives an overview of each class of object, a page per object,
and sample soups that produce it.[^1] The full tables live there; this page is about what
the census is and what it makes possible.

**Scale.** For Life's asymmetric 16 × 16 soups at density 0.5, the census has passed about
5.9 × 10^14 soups and 7.3 × 10^15 objects of 553,848 distinct types, from over a hundred
contributors. Counting every official symmetry, the distinct types number about four
million.[^2] The totals grow every day, so the live figures are on the site.

**A natural history of Life.** The census turns "what does Life do on its own?" into
frequencies.[^3]
- Every still life up to 15 cells has appeared in asymmetric soups, but above that the
  census reaches only a shrinking fraction of the still lifes that exist, down to a few
  thousand of the billions of 33-cell ones.
- Asymmetric soups produce mostly period-2 and period-3 oscillators, plus rarities such as
  the p14 tumbler and Rob's p16.
- Beyond the glider and the LWSS, MWSS and HWSS
  ([[light-middle-heavyweight-spaceships](pages/light-middle-heavyweight-spaceships.md)]),
  asymmetric soups have produced the sidecar, the loafer (period 7), the Schick engine
  (period 12) and the Coe ship (period 16).
- Symmetric soups reach much further: oscillators of dozens of periods, the copperhead and
  other rare [[spaceship](pages/spaceship.md)]s, and far larger still lifes.
- A census can even have an "index fossil": 23 symmetric soups lasting about 128,000
  generations, all from the same [[switch-engine](pages/switch-engine.md)] pair killed by
  a glider.

**Other rules.** Over 20,000 rules have been censused, including close Life variants
([[highlife](pages/highlife.md)], EightLife, Pedestrian Life), Day & Night, and
[[larger-than-life](pages/larger-than-life.md)] rules such as Bosco's Rule. As with
apgsearch, only non-exploding rules are practical unless a symmetry is known never to
explode.[^4]

**Trust.** Submissions, called *hauls*, to large Life-like censuses are checked
statistically and peer-reviewed before being committed. The check can backfire: for
B3/S2, whose ash is a few extremely common objects, the verifier mistook real rare finds
for fakes, so verification is off there.[^5] The site checks that an object behaves as its
code says, but accepts non-canonical codes and odd rule names.[^6]

**More than a soup census.** Catagolue accepts any rule name, symmetry and object code, so
any search that can emit tallies can become a distributed census. Goucher's example is a
depth-first spaceship search whose search-tree positions play the role of soups.[^7]
- *Slow salvos.* A pseudo-symmetry records what [[slow-salvo](pages/slow-salvo.md)]s build.
- *stdin symmetries.* apgsearch can take patterns from another program in place of random
  soups. Piping the spaceship searcher ikpx into it found a c/4 diagonal tubstretcher that
  neither program could find alone.
- *Syntheses and guns.* It keeps the cheapest known glider syntheses of objects
  ([[object-synthesis](pages/object-synthesis.md)]) and a database of glider [[gun](pages/gun.md)]s, with a box for submitting improvements.

**Community.** Contributors get user pages, credit for being among the first 20 finders of
an interesting object, and badges such as "Conchita" for a soup containing a
[[phoenix](pages/phoenix.md)].[^8]

## Appearances in Sources

- [[lifewiki-catagolue](pages/lifewiki-catagolue.md)] - the whole article
- [[lifewiki-apgsearch](pages/lifewiki-apgsearch.md)] - the client that feeds it

## Related Concepts

- [[apgsearch](pages/apgsearch.md)] - its main client
- [[soup-search](pages/soup-search.md)] - the method, and the earlier censuses Catagolue succeeds
- [[still-life](pages/still-life.md)], [[oscillator](pages/oscillator.md)], [[spaceship](pages/spaceship.md)], [[methuselah](pages/methuselah.md)] - what it counts

[^1]: [[lifewiki-catagolue](pages/lifewiki-catagolue.md)] L31-33,L64,L523 [synthesis] - "an ongoing distributed census of naturally occurring ash objects conducted by Adam P. Goucher, started in late February 2015"; "Catagolue is primarily fed by apgsearch 5.x (apgluxe). Each resulting object is identified by apgsearch by its unique apgcode; the Catagolue website gives overviews over the various classes of objects found, and provides further information as well as sample soups for each object"; n.7 name "an amalgam of "Catalogue" and "GoL""
[^2]: [[lifewiki-catagolue](pages/lifewiki-catagolue.md)] L31-32,L216 [synthesis] - "Over 100 users have contributed"; soups "of size 16×16 with density 0.5 in an infinite planar universe"; at least 587,443,221,069,880 soups, 7,315,050,809,532,447 objects of 553,848 distinct types; all official symmetries "3,968,879 distinct types"
[^3]: [[lifewiki-catagolue](pages/lifewiki-catagolue.md)] L73-128,L219-296,L330 [synthesis] - C1 still lifes "All still lifes up to 15 bits" down to "2,570 of the 14,223,867,298 33-bit still lifes"; C1 oscillators dominated by p2 and p3, with tumbler (p14) and Rob's p16; C1 spaceships sidecar, loafer (p7), Schick engine (p12), Coe ship (p16); higher symmetries' oscillators, copperhead and large D8 still lifes; "23 methuselahs lasting between 128,000 and 128,999 generations, caused by a switch engine pair that gets killed by a glider; this is an index fossil"
[^4]: [[lifewiki-catagolue](pages/lifewiki-catagolue.md)] L421,L434-454 [synthesis] - "only non-exploding rules can reasonably be investigated unless a certain symmetry can be assured to never explode"; "20,644 rules have been investigated"; close Life variants; Day & Night; Bosco's Rule
[^5]: [[lifewiki-catagolue](pages/lifewiki-catagolue.md)] L32,L457-458 [synthesis] - "Submissions of new results (called hauls) are subjected to both statistical tests and peer-review"; "B3/S2, despite having more than a trillion objects, has verification disabled. This is because there are relatively few but extremely common objects, so the verification system (Parmenides) mistook rare objects and new discoveries as being fake"
[^6]: [[lifewiki-catagolue](pages/lifewiki-catagolue.md)] L495 - "Although Catagolue verifies that an object in a given rule behaves as specified by its code, the site makes no attempt to reject non-canonical codes"
[^7]: [[lifewiki-catagolue](pages/lifewiki-catagolue.md)] L387,L460-470 [synthesis] - slow salvo data via "the SS pseudo-symmetry"; "[Catagolue] basically accepts anything that you choose to pass off as a rule name, symmetry type, and apgcode"; zfind example; "Arie Paap found a c/4 diagonal tubstretcher in this manner by piping the output of ikpx into apgsearch ... the tubstretcher could neither be found by ikpx ... nor apgsearch ... in isolation"; database of cheapest known glider syntheses; database of glider guns
[^8]: [[lifewiki-catagolue](pages/lifewiki-catagolue.md)] L472-475 [synthesis] - user pages; "Users are credited for discoveries if they find one of the first 20 occurrences of an interesting object"; "Conchita: find a soup containing a phoenix"
