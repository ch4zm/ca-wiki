# Hexagonal neighbourhood - LifeWiki

Source: https://conwaylife.com/wiki/Hexagonal_neighbourhood (LifeWiki; saved HTML from ~/Downloads, converted to text 2026-09-25; site navigation removed)

From LifeWiki
(Redirected from Hexagonal neighborhood)
The hexagonal neighbourhood, perhaps more correctly the honeycomb neighbourhood,[1] (not to be confused with tessellations such as the cubic honeycomb), is the set of all cells that are adjacent to the region of interest (neighbourhood) on the hexagonal tiling (the region of interest itself may or may not be considered part of the hexagonal neighbourhood, depending on context). Currently, these rules are partially supported by both Golly and apgsearch. These rules are typically notated using the H suffix (e.g. B2/S34H).
Contents
	•	1 Generalizations
	◦	1.1 Higher ranges
	◦	1.2 Subsets and alternate extensions
	◦	1.3 Isotropic non-totalistic rules
	•	2 Symmetries
	•	3 Software support
	•	4 See also
	•	5 References
	•	6 External links
Generalizations
As mentioned above, Golly also has the ability to support outer-totalistic Generations rules using the hexagonal grid. Larger than Life and BSFKL rules are also possible, but they are not currently supported by apgsearch as of January 2022. However, LifeViewer and Golly support Larger than Life rules in this neighbourhood.
Higher ranges
The hexagonal neighbourhood can be defined with a higher range; that is, so that it captures cells that are further than one cell away from the region of interest. The higher range hexagonal neighbourhood take the shape of a symmetric honeycomb[2] and the number of cells in a range n hexagonal neighbourhood has the formula 3 n (n + 1).
Range = 1
Range = 2
Range = 3
Subsets and alternate extensions
Rather than extending the hexagonal neighbourhood outwards as to form a large, solid hexagon, it can be extended by casting six rays outwards from the central cell to form what is referred to as the "asterisk" neighbourhood. This can be seen as the hexagonal-grid analogue to the cross neighbourhood or star neighbourhood depending on the analysis used.
range = 1
range = 2
range = 3
A subset of the hexagonal range 1 neighbourhood known as the tripod neighbourhood has also been investigated.[3] This neighbourhood has an essence of intrinsic chirality; having only half of the rotational symmetry of the usual hexagonal and asterisk neighbourhoods as well as cells in one cell's tripod neighbourhood not including the original cell in their tripod neighbourhood imparts rather strange mechanics upon rules which use it. Like with the asterisk neighbourhood, it can be extended via casting three rays from a central cell.
range = 1
range = 2
range = 3
Isotropic non-totalistic rules
See also: Isotropic non-totalistic cellular automaton
Like in the Moore neighborhood, isotropic cellular automata using the hexagonal neighbourhood can be defined using a notation devised by Paul Callahan which represent the relative permutations of the cells using the letters o, m, and p, as shown in the table below. The three letters stand for ortho, meta, and para respectively and were chosen in analogy to arene substitution patterns[4] in aromatic chemistry.[5][6]
Golly does not support isotropic non-totalistic hexagonal rules using this syntax, so they must instead be simulated using either rule tables or MAP strings. LifeViewer and lifelib support them natively.
0
1
2
3
4
5
6
—
(no letter)
o
(ortho)
m
(meta)
p
(para)
Symmetries
Main article: Static symmetry#On a hexagonal or triangular grid
The hexagonal neighbourhood relies on a different grid than the Moore and von Neumann neighborhoods and thus features a different set of inherent symmetries when dealing with isotropic rules:
	•	Asymmetric (C1, 8x32, 4x64, 2x128, 1x256)
	•	C2_1
	•	C2_4
	•	C3_1
	•	C3_3 (unsupported by apgsearch)
	•	C6
	•	D2_xo
	•	D2_x
	•	D4_x1
	•	D4_x4
	•	D6_1
	•	D6_1o
	•	D6_3 (unsupported by apgsearch)
	•	D12
All of these are currently supported by both lifelib and apgsearch, except for D6_3 and C3_3. Catagolue's /hashsoup endpoint currently does not understand any of the C3, C6, D6 or D12 symmetries,[7] but the samples soups can nonetheless be correctly retrieved using lifelib's pattern.download_samples() function.[8]
Hexagonal rules can also support gutter symmetry,[9] however apgsearch does not support searching with these.
Software support
LifeViewer supports outer-totalistic hexagonal rules and also supports isotropic non-totalistic hexagonal rulestrings from build 313,[10] and supports hexagonal Higher-range outer-totalistic (including Larger than Life) rules.
Golly also simulates outer-totalistic hexagonal rules, although it does not natively support isotropic non-totalistic hexagonal rules with the usual notation. They both also have the ability to support Generations variants of hexagonal rules. In addition, hexagonal Higher-range outer-totalistic (including Larger than Life) rules are supported from v4.0 onwards.
apgsearch and Catagolue also support the hexagonal neighbourhood. They support hexagonal Generations rules, but they also support isotropic non-totalistic rules (see Generalizations below). Since version 4.71, all possible symmetries are available for searching except for C3_3 and D6_3 (see Symmetries below).[11][12]
See also
	•	Neighbourhood
	◦	Margolus neighbourhood
	◦	Moore neighbourhood
	◦	von Neumann neighbourhood
	◦	Triangular Moore neighbourhood
	◦	Triangular von Neumann neighbourhood
	•	Zone of influence
	•	Gallery of neighbourhoods/Images
	•	Hexagonal tiling
References
	1	↑ https://cell-auto.com/neighbourhood/honeycomb/
	2	↑ Chris Rowett. "LifeViewer Plugin Tests". Retrieved on November 21, 2020.
	3	↑ EricG (September 9, 2012). Triangular & Tripod von Neuman neighborhoods (discussion thread) at the ConwayLife.com forums
	4	↑ Arene substitution pattern at Wikipedia
	5	↑ Experiments with a somewhat "Life-like" hexagonal CA (long) at Paul Callahan's Page of Conway's Life Miscellany
	6	↑ "ExtendedCallahanHexagonal.gif". ConwayLife.com forums. Retrieved on December 8, 2018.
	7	↑ https://gitlab.com/apgoucher/catagolue/-/issues/2
	8	↑ Re: apgsearch v4.0 (discussion thread) at the ConwayLife.com forums
	9	↑ Connor Steppie (December 5, 2018). Re: Non-totalistic hex rules (discussion thread) at the ConwayLife.com forums
	10	↑ Chris Rowett (March 17, 2019). Re: Pattern viewer for forum threads (discussion thread) at the ConwayLife.com forums
	11	↑ Adam P. Goucher (December 20, 2018). Re: apgsearch v4.0 (discussion thread) at the ConwayLife.com forums
	12	↑ Connor Steppie (January 15, 2020). "C3_3 and D6_3 hex symmetries are not supported". GitLab.
External links
	•	
	•	Hexagonal tiling at Wikipedia
Forum threads:
	•	Hexagonal self-complementary rules (discussion thread) at the ConwayLife.com forums
	•	Hexagonal rules (discussion thread) at the ConwayLife.com forums
	•	Hex rule B2o/S2m34: 1997 write-up with viewable patterns (discussion thread) at the ConwayLife.com forums
	•	B2-m3-o/S2m3-p4-m5H (discussion thread) at the ConwayLife.com forums
	•	Outer-totalistic hexagonal rules with spaceships (discussion thread) at the ConwayLife.com forums
	•	Non-totalistic hex rules (discussion thread) at the ConwayLife.com forums
	•	B2o3m56/S2om4oH (Hex Life) (discussion thread) at the ConwayLife.com forums
	•	B2/S34H (Hexagonal Life) (discussion thread) at the ConwayLife.com forums
	•	Hex rule B2o45/S2o45 (discussion thread) at the ConwayLife.com forums
	•	22da (Hexagonal Grid) (discussion thread) at the ConwayLife.com forums
	•	Hexagonal Generations (discussion thread) at the ConwayLife.com forums
	•	Kinetic symmetries on the hexagonal and triangular grids (discussion thread) at the ConwayLife.com forums
Retrieved from "https://conwaylife.com/w/index.php?title=Hexagonal_neighbourhood&oldid=164010"
