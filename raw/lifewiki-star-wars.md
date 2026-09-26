# OCA:Star Wars - LifeWiki

Source: https://conwaylife.com/wiki/OCA:Star_Wars (LifeWiki; saved HTML from ~/Downloads, converted to text 2026-09-25; site navigation removed)

From LifeWiki
(Redirected from Star Wars)
Star Wars
LifeViewer-generated pseudorandom soup
View static image
Rulestring
345/2/4 
B2/S345/C4
B2/S345/G4
Character
Explosive
This article is about the Generations rule. For the outer-totalistic rule, see OCA:Star Trek.
This article is a stub. You can help LifeWiki by expanding it.
Star Wars, also known as MirekGro, is a Generations rule devised by Mirek Wójtowicz in March 1999. In this rule, a state-0 cell will become state 1 iff it has two state-1 neighbours. A state-1 cell does not change if it has 3, 4 or 5 state-1 neighbours, otherwise it will enter state 2 next tick and then state 3 before dying.
Named after its behaviour that resembles deep space battle scenes, the rule can be described as follows:
“
StarWars is also an interesting rule from the low-investment standpoint. In particular, it is notable for the abundance, intricacy, and variety of its naturally-occurring glider guns. In general when running "au naturel" StarWars is active to a degree almost reminiscent of Brain, with the distinction that it likes to build fixed lego-like skeletal structures. In some orbits this latter penchant reaches its zenith, and we get large universe-spanning "shells" possessing an intricate radiate geometry.
”
— John Elliott
A collection of patterns in Star Wars rule is in Mirek's Cellebration. The rule can also run in modern simulators (e.g. Golly and LifeViewer) that support Generations rules.
Contents
	•	1 Patterns
	◦	1.1 Still lifes
	◦	1.2 Oscillators
	◦	1.3 Spaceships
	◦	1.4 Linear growth patterns
	◦	1.5 Signal circuits
	◦	1.6 Miscellaneous
	•	2 References
	•	3 External links
Patterns
Example still lifes in Star Wars
(click above to open LifeViewer)
Example oscillators in Star Wars
(click above to open LifeViewer)
Example spaceships in Star Wars (Mirek Wójtowicz, May 1999)
(click above to open LifeViewer)
Still lifes
Still lifes of population 5, 8, 10, 12 and above exists. The only 5-cell still life is the X-pentomino, or cross, which is a common extendable segment in larger still lifes.
A group of still lifes in the shape of rectangular boxes are invincible from inside, limiting the evolution similar to a finite plane; for a m × n plane the exterior has a bounding box of (m + 4) × (n + 4). An example with m = n = 16 is shown above at lower-right corner.
Oscillators
Due to the two dying states, oscillators of period 2 and 3 are impossible.
Many oscillators consist of one or more lightspeed signals, with a leading state-1 cell each, that are running on the surface of the stator. These oscillators are referred to as railroads because they look like trains running on railways. The mechanism provides at least one specimen for every period p ≥ 4. Specifically, jointing q copies of the X-pentomino orthogonally will give a still life with circumference 6q + 6 cells (which has exactly one state-1 cell each in their Moore neighbourhoods). If 6q + 6 = kp for some integer k, then k copies of the signal can be put in the circumference evenly to yield a period-p oscillator. The period-7 example is constructed accordingly.
Due to the abundance of chaotic puffers, billiard table oscillators are relatively common in this rule.
Spaceships
Most of the spaceships in Star Wars are at c orthogonal, thus are also referred to as photons. The structure is extensible to various degrees. On March 21, 2021, Rocknlol discovered a c/6 diagonal elementary spaceship[1] which Dets65 found to be extensible.[2]
Guns of period 4, 5 (right), 6 and 7 (left) in Star Wars (Stephen Silver, May 1999)
(click above to open LifeViewer)
Simple photon conduits in Star Wars, with state-3 cells marking output location. Top, left to right: eater, 90-degree reflector, 180-degree reflector, 3-tick delay, 2-tick delay. Bottom: XOR gate with two outputs, AND gate, OR gate
(click above to open LifeViewer)
Linear growth patterns
Guns (or rather, lasers) firing the smallest photon exist at all periods above 4, which can be constructed by connecting two still lifes to the aforementioned adjustable oscillator.
Usually, abundant linear growth patterns including guns, puffers, rakes, wickstretchers and wavestretchers emerge from sufficiently large soups.
Signal circuits
Technologies based on the smallest photon have been extensively developed. For instance, shooting the photon at the edge of a still life can split it into two lightspeed signals, which travel on the edge and merge into a photon elsewhere, or are turned into other signals. A small portion of photon conduits is shown above.
Further constructions are possible, for instance an adder[3] and a Rule 110 emulator.[4]
Miscellaneous
The domino in this rule expands in a diamond shape, while the block grows quadratically generating wickstretchers. Diagonal lines of at least 6 cells in length evolve into a family of p5 oscillators.
References
	1	↑ Rocknlol (March 21, 2021). Re: Star Wars Rule (discussion thread) at the ConwayLife.com forums
	2	↑ Dets65 (March 24, 2021). Re: Star Wars Rule (discussion thread) at the ConwayLife.com forums
	3	↑ Jeremy Tan (March 22, 2015). An Amsterdam Adder (discussion thread) at the ConwayLife.com forums
	4	↑ FWKnightship (November 18, 2020). Re: Star Wars Rule (discussion thread) at the ConwayLife.com forums
External links
	•	
	•	Star Wars Rule (discussion thread) at the ConwayLife.com forums
	•	Star Wars at Adam P. Goucher's Catagolue
	•	MCell built-in Generations rules: Star Wars at Mirek Wójtowicz's Cellebration page
	•	Adam P. Goucher (March 7, 2014). "Emergence". Complex Projective 4-Space. An article describing the emergence of structures from random soups in Star Wars.
Retrieved from "https://conwaylife.com/w/index.php?title=OCA:Star_Wars&oldid=164562"
