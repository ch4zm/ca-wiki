# Generations - LifeWiki

Source: https://conwaylife.com/wiki/Generations (LifeWiki; saved HTML from ~/Downloads, converted to text 2026-09-25; site navigation removed)

From LifeWiki
Generations rules are a multistate generalization of Life-like cellular automata in which live cells can exist in different states, and cells that would die in a 2-state cellular automaton instead advance to the next state.
The name "Generations" is due to the conceptualization of this process as cells "getting older" before eventually dying.[note 1]
Contents
	•	1 Description
	•	2 Examples
	•	3 Software support
	•	4 Extensions and variants
	•	5 See also
	•	6 Notes
	•	7 References
	•	8 External links
Description
Generations rules are described by rulestrings of the form Bx/Sy/n[note 2] or y/x/n, an extension of B/S and S/B rulestrings where n is any natural number ≥2. Patterns evolve according to the following rules:
	1	A cell in state 0 ("dead") will advance to state 1 ("get born") in the next generation of the pattern if the number of neighbors in state 1 ("live") in its Moore neighbourhood is present in the rule's birth conditions (Bx).
	2	A cell in state 1 ("live") will:
	1	Remain in state 1 ("survive") in the next generation of the pattern if the number of neighbors in state 1 ("live") in its Moore neighborhood is present in the rule's survival conditions (Sx).
	2	Advance to state 2 ("age") in the next generation of the pattern otherwise.
	3	A cell in state m ≥ 2 will advance to state ((m + 1) mod n) in the next generation of the pattern. In particular, a cell in state n will reset to state 0 ("die").
Any outer-totalistic cellular automaton with rulestring B.../S... is equivalent to the Generations rule with rulestring B.../S.../2.
B0 is also possible for Generations rules, however software support is not widespread.
Examples
Main article: List of Generations rules
Rule (B/S/C)
Rule (S/B/C equivalent)
Name
Character
Author
B34578/S237/4
345678/237/4
9:43 at Knight
Stable
EricG
B3457/S2367/5
2367/3457/5
Banners
Exploding
Mirek Wójtowicz
B34678/S234/24
234/34678/24
Bloomerang
Expanding
John Elliott
B246/S6/3
6/2/3
Brian 6
Chaotic
Michael Sweney
B2/S/3
/2/3
Brian's Brain
Chaotic
Brian Silverman
B378/S124567/4
124567/378/4
Caterpillars
Chaotic
Mirek Wójtowicz
B2/S23/8
23/2/8
Cooties
Exploding
Rudy Rucker
B13/S2/21
2/13/21
Fireworks
Exploding
John Elliott
B34/S12/3
12/34/3
Frogs
Chaotic
Scott Robert Ladd
B45678/S12345/8
12345/45678/8
Lava
Expanding
Mirek Wójtowicz
B458/S012345/3
012345/458/3
Lines
Stable
Anders Starmark
B2/S345/4
345/2/4
Star Wars
Exploding
Mirek Wójtowicz
B2/S3456/6
3456/2/6
Sticks
Exploding
Rudy Rucker
B26/S345/5
345/26/5
Transers
Exploding
John Elliott
B2356/S1456/16
1456/2356/16
Xtasy
Exploding
John Elliott
Software support
Both MCell and Golly support Generations rules, the latter with a maximum of 256 states. Golly currently does not support Generations rules with B0; a method of emulating such rules was added in beta versions of Golly 2.9, but was ultimately scrapped due to bugs and complexity.[1] Non-B0 Generations rules are also supported by Chris Rowett's LifeViewer starting with build 180.
CAViewer can support Generations rules including those with B0.
Extensions and variants
Generations rules can, in a straightforward manner, be adapted to von Neumann, hexagonal and triangular neighbourhoods and extended to non-totalistic and non-isotropic rules.
Larger than Life rules extend Generations rules to larger neighbourhoods.
Reverse Generations rules (also called "snoitareneG" rules), in which cells take time to become alive, have been explored.[2][3][4] These are not directly supported by Golly or apgsearch, although ruletables have been used for the former.
Generation and snoitareneG can be considered subsets of the Extended Generations rulespace,[5] which is supported by apgsearch.
See also
	•	BSFKL
	•	Larger than Life
	•	Neutronium
Notes
	1	↑ The name "Generations", and the different states in which cells in Generations rules can exist, should not be confused with the generations (i.e. repeated evolution) of a pattern.
	2	↑ Bx/Sy/Cn and Bx/Sy/Gn are also sometimes used, with "C" standing for "Count" (of cell states), and "G" for "Generations". If "C" is used, care must be taken to not confuse the state count with a symmetry, e.g. "B3/S23/C4".
References
	1	↑ https://conwaylife.com/forums/viewtopic.php?f=7&t=4133&p=88707#p88734
	2	↑ Martin Grant (April 10, 2010). "Reverse Generations" Rules (discussion thread) at the ConwayLife.com forums
	3	↑ Brian Prentice (June 4, 2017). Re: Thread for basic questions (discussion thread) at the ConwayLife.com forums
	4	↑ Saka (July 2, 2017). snoitareneG Rules (discussion thread) at the ConwayLife.com forums
	5	↑ M. I. Wright (August 1, 2018). "Extended" Generations rules (discussion thread) at the ConwayLife.com forums
External links
	•	Generations at Golly's online help
	•	Family: Generations at Mirek Wójtowicz's Cellebration page
Retrieved from "https://conwaylife.com/w/index.php?title=Generations&oldid=163708"
