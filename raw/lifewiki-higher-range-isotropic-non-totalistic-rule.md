# Higher-range isotropic non-totalistic rule - LifeWiki

Source: https://conwaylife.com/wiki/Higher-range_isotropic_non-totalistic_rule (LifeWiki; saved HTML from ~/Downloads, converted to text 2026-09-25; site navigation removed)

From LifeWiki
Higher-range isotropic non-totalistic (abbreviated as HRINT) are a generalization of range-1 isotropic non-totalistic rules and of higher-range outer-totalistic rules; a rulespace with a range greater than 1 where isotropy is observed, but transitions are not necessarily totalistic.
There are a very wide variety of such rules, with limited software support.
Classes
"Exploded" Moore neighbourhood
The range-1, 8-cell Moore neighbourhood can be "exploded" into other neighbourhoods consisting of four orthogonal cells of distance E and four diagonal cells of distance C.[1] Isotropic non-totalistic rules can be run using this neighbourhood using standard Hensel notation.
Neighbourhoods with orthogonal cells of distance 1 and diagonal cells of distance 2, as well as with orthogonal cells of distance 3 and diagonal cells of distance 1, can be run using CAViewer.
Range-2 cross neighbourhood
A proposal for a notation for this neighbourhood was created in 2017 as a result of a misunderstanding of how the range-2 von Neumann neighbourhood was to be defined.[2] A second notation for this neighbourhood was created in mid-2020,[3] however a 3-cell transition and its corresponding 5-cell transition was mistakenly omitted.[4]
The following notation is supported by CAViewer. Whether other programs will implement support for this rulespace currently remains unknown.
0
1
2
3
4
5
6
7
8
—
(no letter)
a
c
e
h
i
j
n
o
p
q
r
t
u
v
w
Range-2 knight neighbourhood
A proposal for a notation for this neighbourhood was created in mid-2020.[3] However, the proposal duplicated one of the 4-cell transitions.[4]
The following notation is supported by CAViewer. Whether other programs will implement support for this rulespace currently remains unknown.
0
1
2
3
4
5
6
7
8
—
(no letter)
a
c
e
h
i
j
n
o
p
q
r
t
u
4-cell extensions
A notation system exists that can be used for extending existing isotropic non-totalistic rules by adding four equidistant cells, either orthogonally or diagonally aligned with the center. This can be used for notating isoptropic non-totalistic rules with the range-2 von Neumann neighbourhood, or any of the other three equivalent neighbourhoods below. It is also used for notating the range-3 cross neighbourhood by extending the range-2 cross neighbourhood.
These four neighbourhoods are effectively equivalent
(click above to open LifeViewer)
The extension-based notation was initially proposed on February 24, 2019 by AforAmpere and Milo Jacquet for range-2 von Neumann isotropic non-totalistic rules.[5] Prior to this, a two-letter system was proposed for said rulespace, in which two letters were used for each of the 618 possible transitions; this ultimately was not adopted.[6][5]
A table for the extensions notation is as follows:
a
c
d
e
f
g
i
j
k
l
m
n
o
p
q
r
For each transition, use the transition corresponding to the configuration of the center 8 cells, aligned with the canonical directions in the table above. Then take the outside 4 cells, and depending on the configurations in the table below, add that letter.
For transitions that are the same under reflections or rotations, the canonical transition is the lowest alphabetically.
'x' is used after a totalistic number. An example range-2 von Neumann rulestring is 'B3x2ic1ei5x-3kr/S0x8x'.
bubblegum has also proposed to use the 'v' character to represent outer totalistic transitions for the inner 8 cells for range-2 von Neumann rules.[7]
CAViewer supports this notation for the range-2 von Neumann neighbourhood.[8]
3-state, range-1 Moore neighbourhood
Several notations have been proposed historically. The currently accepted notation, which does not currently have software support, was published by Cyclotrons in 2023.[9]
Table of isotropic non-totalistic rulespaces
It has been suggested that this page or section be split into List of rulespaces. (Discuss)
The number of unique transitions for higher ranges tends to be extremely large, and the development of notations for such rules is generally infeasible. The following table documents notable examples (grids are notated with Schläfli symbols as to simultaneously convey grid type and dimension):
Common name
Rulespace definitions
Transitions
Notated?
Major software support
Grid
Range
States
Neighbourhood
Golly
LifeViewer
lifelib
Block cellular automata
{4,4}
1/2
2
Moore
6
Yes
(Unnecessary)
-
{4,4}
1
2
von Neumann
6
Trivial
(Unnecessary)
3D vN non-totalistic
{4,3,4}
1
2
von Neumann
10
No
No
No
No
Non-totalistic hexagonal
{6,3}
1
2
hexagonal
13
Yes
No[n 1]
Yes
Yes
Knight INT
{4,4}
2
2
knight
43
Yes
No
No
No
Isotropic non-totalistic
{4,4}
1
2
Moore
51
Yes
Yes
Yes
Yes
Exploded
{4,4}
≥1
2
variable[n 2]
51
Yes
No
Some[n 3]
Some[n 4]
Cross INT
{4,4}
2
2
cross
55
Yes
No
No
No
9-cell triangular
{3,6}
2
2
biohazard[n 5]
104
Yes
No
No
No
-[n 6]
{4,4}
2
2
nonstandard[n 7]
570
No
No
No
No
R2 von Neumann INT
{4,4}
2
2
von Neumann
618
Yes
No
No
Yes
-
{6,3}
2
2
nonstandard[n 8]
860
No
No
No
No
-
{4,4}
2
2
nonstandard[n 9]
570
No
No
No
No
3-state knight INT
{4,4}
2
3
knight
873
No
No
No
No
3-state INT
{4,4}
1
3
Moore
954
Yes
No[n 10]
No[n 10]
No[n 10]
3-state cross INT
{4,4}
2
3
cross
1035
No
No
No
No
Triangular INT
{3,6}
1
2
triangular Moore
1504
No
No
No
No
4-state knight INT
{4,4}
2
4
knight
8356
No
No
No
No
4-state INT
{4,4}
1
4
Moore
8740
Yes
No[n 10]
No[n 10]
No[n 10]
4-state cross INT
{4,4}
2
4
cross
9316
No
No
No
No
R2 hexagonal INT
{6,3}
2
2
hexagonal
22668
No
No
No
No
3-state R2 vN INT
{4,4}
2
3
von Neumann
68715
No
No
No
No
R2 Moore-without-corners
{4,4}
2
2
circular
132744
No
No
No
No
3D non-totalistic
{4,3,4}
1
2
Moore
1426144[n 11]
No
No
No
No
R2 Moore INT
{4,4}
2
2
Moore
2105872
No
No
No
No
24-cell honeycomb
{3,4,3,3}
1
2
Moore
?
No
No
No
No
4D non-totalistic
{4,3,3,4}
1
2
Moore
3148244699232062849152[n 12]
No
No
No
No
16-cell honeycomb
{3,3,4,3}
1
2
Moore
?
No
No
No
No
	1	↑ The rulespace can be simulated via MAP strings, or, less preferably, ruletables, however no direct support for the notation exists.
	2	↑ Based on the Moore neighbourhood, with the four edge cells and/or the four corner cells moved away from the origin a defined distance.
	3	↑ The range-N "far corners" + range-M "far edges" cases are supported, but the general case of exploded Moore neighbourhoods are not.
	4	↑ The range-2 "far corners" and range-3 "far edges" cases are supported, but the general case of exploded Moore neighbourhoods are not.
	5	↑ could equivalently apply to the vertices neighbourhood
	6	↑ it has been suggested to call this the R2 ring neighborhood
	7	↑ The number is the same for a "circle" formed of four three-cell lines at distance 2 from the center, and four "pre-blocks" with the gaps all facing the center or all facing outwards (or any configuration of eight eightfold neighbours and two fourfold ones)
	8	↑ 12 cells: 6 orthogonal and 6 diagonal
	9	↑ The number is the same for a "circle" formed of four three-cell lines at distance 2 from the center, and four "pre-blocks" with the gaps all facing the center or all facing outwards (or any configuration of eight eightfold neighbours and two fourfold ones)
	10	↑ Jump up to:  10.0 10.1 10.2 10.3 10.4 10.5 The rulespace can be simulated via ruletables, however no direct support for the notation exists.
	11	↑ first calculated by Milo Jacquet
	12	↑ first calculated using the Pólya enumeration theorem by DroneBetter's dimensional_INT_enumerator.py (explained here)
The number of unique transitions in rulespaces with range-1 von Neumann neighbourhoods (or equivalent) with n states follows the doubly-triangular numbers ,  A002817(n).
A rule with an n-dimensional range-k Moore neighbourhood has  A361870(n,2*k+1) transitions.
Soup-searching non-totalistic rules
Range 2 von Neumann isotropic rules can be searched using Adam P. Goucher's apgsearch by means of a ruletable using a custom neighbourhood.[10] However, note that GPU censuses support only outer-totalistic rules.
See also
	•	Generations
	•	Larger than Life
References
	1	↑ Connor Steppie (April 23, 2021). Re: Lemon41625's Cellular Automaton (discussion thread) at the ConwayLife.com forums
	2	↑ toroidalet (September 2, 2017). Re: Golly suggestions (discussion thread) at the ConwayLife.com forums
	3	↑ Jump up to:  3.0 3.1 lemon41625 (July 23, 2020). Re: Pattern viewer for forum threads (discussion thread) at the ConwayLife.com forums
	4	↑ Jump up to:  4.0 4.1 Re: Pattern viewer for forum threads (discussion thread) at the ConwayLife.com forums
	5	↑ Jump up to:  5.0 5.1 AforAmpere (February 23, 2019). Re: Range-2 von Neumann isotropic non-totalistic rulespace (discussion thread) at the ConwayLife.com forums
	6	↑ Connor Steppie (February 9, 2019). Range-2 von Neumann isotropic non-totalistic rulespace (discussion thread) at the ConwayLife.com forums
	7	↑ bubblegum (August 26, 2020). Re: Range-2 von Neumann isotropic non-totalistic rulespace (discussion thread) at the ConwayLife.com forums
	8	↑ lemon41625 (November 29, 2020). Re: CAViewer - A Cellular Automaton Simulator written in Java (discussion thread) at the ConwayLife.com forums
	9	↑ https://conwaylife.com/forums/viewtopic.php?p=164994#p164994
	10	↑ lemon41625 (June 19, 2020). Re: Range-2 von Neumann isotropic non-totalistic rulespace (discussion thread) at the ConwayLife.com forums
Retrieved from "https://conwaylife.com/w/index.php?title=Higher-range_isotropic_non-totalistic_rule&oldid=167693"
