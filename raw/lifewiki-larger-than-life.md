# Larger than Life - LifeWiki

Source: https://conwaylife.com/wiki/Larger_than_Life (LifeWiki; saved HTML from ~/Downloads, converted to text 2026-09-25; site navigation removed)

From LifeWiki
Larger than Life (abbreviated as LTL or LtL) is an algorithm that supports a specific family of higher-range outer-totalistic cellular automata with an extendable neighbourhood, as defined by Kellie Michele Evans in her 1996 thesis.
Larger than Life rules are supported by Golly 3.0 and onwards and LifeViewer build 260 and onwards.
Contents
	•	1 Notation
	◦	1.1 HROT notation
	•	2 Examples
	•	3 Alternative rule notations
	•	4 Generalizing LtL rules to different amounts of neighbors
	◦	4.1 Example
	•	5 See also
	•	6 Notes
	•	7 References
	•	8 Further reading
	•	9 External links
Notation
The following notation was created by Mirek Wójtowicz for Mirek's Cellebration (MCell):
Rr,Cc,Mm,Ssmin..smax,Bbmin..bmax,Nn
Here:
	•	Rr specifies the range (r is from 1 to 500 in Golly and LifeViewer; 1 to 10 in MCell).
	•	Cc specifies the number of states (c is from 0 to 255 in Golly, LifeViewer and MCell[note 1])
	•	Mm specifies if the middle cell is included in the neighborhood count (m is 0 or 1).
	•	Ssmin..smax specifies the count limits for a state 1 cell to survive.
	•	Bbmin..bmax specifies the count limits for a dead cell to become a birth.
	•	Nn specifies the extended neighborhood type. MCell only supports Moore and von Neumann. Cannot be omitted.
This diagram shows the extended Moore and von Neumann neighborhoods for range 3:
HROT notation
However, the notation above is now superseded by the general higher-range outer-totalistic notation:
Rr,Cc,Ssranges,Bbranges,Nn
Here:
	•	Rr specifies the range (r is from 1 to 500 in Golly and LifeViewer; 1 to 10 in MCell).
	•	Cc specifies the number of states (c is from 0 to 255 in Golly and LifeViewer)
	•	Ss specifies the survival conditions, which are numbers separated by commas. Ranges of consecutive numbers can be contracted via dashes; e.g. S6,7,8,13,14,18 can be expressed as S6-8,13-14,18
	•	Bb specifies the birth conditions, which are numbers separated by commas. Ranges of consecutive numbers can be contracted via dashes; e.g. B6,7,8,13,14,18 can be expressed as B6-8,13-14,18
	•	Nn specifies the extended neighborhood type (n is M for Moore or N for von Neumann. Golly and LifeViewer also support C for Circular neighborhood, 2 for L2, + for Cross, X for Saltire and * for Star neighborhoods, @ for custom neighbourhoods and more). For Moore, this parameter is omitted.
The difference between Larger than Life rules and other higher-range outer-totalistic cellular automata is mostly in the birth and survival condition. While the former defines only one continuous range of birth and one continuous range of survival conditions, the latter allows for any list of birth and survival conditions to be defined.
If the number of states (specified after C) is greater than 2, then states 1 and above don't die immediately but gradually decay. Note that state values above 1 are not included in the neighborhood counts and thus play no part in deciding the survival of a state 1 cell, nor the birth of an empty cell. C0 and C1 are equivalent to C2.
Examples
The Patterns/Larger-than-Life folder included with Golly contains a number of example patterns (mostly from the MCell collection). The following table shows a number of example rules (expressed using outer-totalistic notation rather than Larger than Life notation for brevity) along with their commonly used names:
Rule
B/S equivalent
Name
Remarks
R1,C2,S2-3,B3
B3/S23
Life
the default rule for this algorithm in Golly.
R1,C2,S0,B1,NN
B1/S0V
Gnarl
an exploding rule by Kellie Evans.
R4,C2,S40-80,B41-81
—
Majority
a stable rule by David Griffeath.
R5,C2,S33-57,B34-45
—
Bosco's Rule
a chaotic rule by Kellie Evans.
R7,C2,S99-199,B75-170
—
Waffle
an expanding rule by Kellie Evans.
R7,C2,S112-224,B113-225
—
Majorly
an expanding rule by David Griffeath.
R8,C2,S163-223,B74-252
—
Globe
an expanding rule by Mirek Wójtowicz.
R10,C2,S122-211,B123-170
—
Bugsmovie
a chaotic rule by David Griffeath.
R10,C255,S1-2,B3
—
ModernArt
a chaotic rule by Charles A. Rockafellor.
R2,C2,S4,6-9,B6-8,N@03ddef
—
Marine
a chaotic rule by MathAndCode.
R3,C2,S2,B3,N+
—
Factorio
a semistable rule by H. H. P. M. P. Cole.
R4,C2,S9,14,16-17,21,23-24,30-31,37-38,44-45,51-52,58-59,B3,10,17,21,24,31,38,45,52,59,
NW100010001000000000000000000000777000100707001000777000000000000000000000100010001
—
Coexistence
a chaotic rule by bubblegum.
R2,C2,S4-6,B5-6,N#
—
Hash
a chaotic rule by b-engine.
Notable patterns which are frequently found within Larger than Life rules include "bugs", which are patterns (usually spaceships, but sometimes oscillators) which are hollow, characterised by those from Bosco's Rule, "solid ships", which are typically extremely slow circular spaceships first noted in 2002 (such as this one), and "roomba bugs", travelling patterns that usually stabilise into low-period oscillators after intense amounts of generations but are infrequently found to be real spaceships.
Alternative rule notations
Golly and LifeViewer also allow rules to be entered using the notation defined by Kellie Evans in her thesis. The range, birth limits and survival limits are specified by five integers separated by commas:
r,bmin,bmax,smin,smax
Catagolue, apgsearch and LifeViewer use a related notation in which the letter t ("to") is used to indicate birth/survival condition ranges; the initial gC is optional, with the number of states defaulting to two:
gCrRbBmintBmaxsSmintSmax
These notations assume an extended Moore neighbourhood in which a live middle cell is included in the neighbourhood count. For example, Life can be entered as 1,3,3,3,4 in Evans' notation.
Generalizing LtL rules to different amounts of neighbors
Larger than Life rules can be generalized ("converted") to different ranges and even neighborhoods. To convert the range-r0 n0-neighborhood rule Rr0,Cc,Mm,Ssmin0..smax0,Bbmin0..bmax0,Nn0 to a range-r1 n1-neighborhood rule:
	1	Compute N to equal the ratio of the number of neighbors in a range-r1 n1-neighborhood to the number of neighbors in a range-r0 n0 neighborhood.
	2	Multiply the original rule's minimum and maximum birth/survival conditions by N and round off, to wit:
	1	Compute smin1 = round(smin0 · N).
	2	Compute smax1 = round(smax0 · N).
	3	Compute bmin1 = round(bmin0 · N).
	4	Compute bmax1 = round(bmax0 · N).
The converted rule is Rr1,Cc,Mm,Ssmin1..smax1,Bbmin1..bmax1,Nn1.
Example
For example, converting the range-2 rule R2,C2,M1,S5..9,B7..9,NM to range 7 with the same neighborhood, with the formula for the number of neighbors in a range-r Moore neighborhood being (2 · r + 1)2, we obtain:
	1	N = (2 · 7 + 1)2 / (2 · 2 + 1)2 = 225 / 25 = 9.
	2	smin1 = 5 · 9 = 45.
	3	smax1 = 9 · 9 = 81.
	4	bmin1 = 7 · 9 = 63.
	5	bmax1 = 9 · 9 = 81.
The converted rule is, therefore, R7,C2,M1,S45..81,B63..81,NM.
See also
	•	Generations
	•	Higher-range outer-totalistic cellular automaton
Notes
	1	↑ The documentation for MCell specifies a maximum of 25 states; this is a typo.
References
	•	Cellular Automata rules lexicon: Family: Larger than Life at Mirek Wójtowicz's Cellebration page
	•	Kellie Michele Evans: Larger than Life: it's so nonlinear (1996 Ph.D. thesis)
Further reading
	•	Kellie Michele Evans: Larger than Life's Extremes: Rigorous Results for Simplified Rules and Speculation on the Phase Boundaries, in: Andrew Adamatzky (ed.), Game of Life Cellular Automata, Springer (London) (2010), ISBN 978-1-84996-216-2, OCLC 619946115
	•	Kellie Michele Evans: Larger than Life, in: Andrew Adamatzky, Genaro J. Martínez (eds.): Designing Beauty: The Art of Cellular Automata, Springer (2016), ISBN 978-3-319-27269-6, OCLC 934720008
External links
	•	Larger than Life at Golly's online help
	•	
	•	Larger than Life (discussion thread) at the ConwayLife.com forums
Retrieved from "https://conwaylife.com/w/index.php?title=Larger_than_Life&oldid=144616"
