# Life-like cellular automaton - LifeWiki

Source: https://conwaylife.com/wiki/Life-like_cellular_automaton (LifeWiki; saved HTML from ~/Downloads, converted to text 2026-09-25; site navigation removed)

From LifeWiki
(Redirected from Outer-totalistic cellular automaton)
A Life-like cellular automaton[note 1] is a CA meeting the following criteria:
	•	the universe is a two-dimensional array of square cells,
	•	each cell can be in one of two states (which are referred to as "alive" and "dead", or alternatively "on" and "off"),
	•	the neighbourhood of each cell is the Moore neighbourhood,
	•	the new state of a cell in the next generation can be expressed as a function of the current state of the cell and the number of alive neighbours of the cell; that is, the rule is outer totalistic (sometimes called semitotalistic).
This class of cellular automata is named for Conway's Game of Life, the most famous cellular automaton, which meets all above criteria. It is also common to refer to this rulespace as the "Life family" or to simply use phrases like "similar to Life".
Contents
	•	1 Notation
	•	2 Description
	•	3 Generalizations
	•	4 Notes
	•	5 See also
	•	6 References
	•	7 External links
Notation
In the notation used by Golly and in the RLE format for storing patterns, Life-like rules are expressed by rulestrings in the "B0...8/S0...8" notation, with two lists of numbers giving the live neighbour counts that cause a dead cell to be born or a live cell to survive, respectively; for example, Conway's Game of Life has the rulestring B3/S23.
Description
There are 262144 (= 218) distinct Life-like rules. Each rule has a complementary rule which behaves identically under on-off reversal; namely the rule in which birth occurs on all N except those for which 8 - N is a survival condition in the original rule, and survival occurs on all N except those for which 8 - N is a birth condition in the original rule. For example, the rule complementary to Conway's Life is B0123478/S01234678. This however does not quite halve the number of effectively distinct rules, as there are 512 (= 29) self-complementary rules which are unaffected by on-off reversal.
Some straightforward inferences on the behavior of different kinds of rules can be made:
	•	In all rules where the lowest birth condition is 1 neighboring ON cell, all finite patterns grow at the speed of light in all directions. No still lifes, oscillators or spaceships are possible in these rules. Several have replicators, however. There are 65536 (= 216) rules of the B1 type.
	•	All rules where the lowest birth condition is 2 neighboring ON cells are exploding or expanding in character; this is largely due to the fact that a domino at the edge of a pattern will give rise to a new domino, also located at the edge of the daughter pattern. Spaceships (such as the moon) and oscillators (such as the duoplet) do exist in many of these rules. There are 32768 (= 215) rules of the B2 type.
	•	All rules where the lowest birth condition (if any) is 4 or more neighboring ON cells are stable in character, since no patterns can ever grow beyond their initial bounding box. In particular, no spaceships can exist. There are 16384 (= 214) rules of the B4+ type.
	•	In all rules where the lowest birth condition is 0 neighboring ON cells, and the highest survival condition is 8 neighboring ON cells, the vacuum is unstable and will be immediately filled (and remain filled) with ON cells; thus, there are no patterns that remain finite. All of these rules have distinct complementary rules, and they are not commonly studied on their own.
	•	This leaves 16384 rules in which the lowest birth condition is 3 neighboring ON cells, as well as 65536 rules in which the lowest birth condition is 0 neighboring cells, and 8 neighbors is not a survival condition. All chaotic rules must fall in either of these two areas of the rulespace. Most well-studied examples fall in the first one, since for long no commonly available software existed that could simulate the evolution of rules containing B0. Golly's QuickLife algorithm simulates them by converting them into equivalent rules to avoid having to simulate an infinite number of cells.[1]
Generalizations
See also: Non-totalistic cellular automaton, Non-isotropic cellular automaton, Generations, Larger than Life
Various generalizations of Life-like cellular automata are possible. In isotropic non-totalistic rules, the transition function considers not just the number of cells in a given cell's neighborhood but also their relative alignment; for example, a cell might be born if bordered by three live cells in a row, but not by three live cells in other configurations. Non-totalistic rules are described using Hensel notation, an extension of the birth/survival notation additionally describing allowed or forbidden configurations.
In non-isotropic rules, the transition function additionally considers the absolute placement of a given cell's neighborhood; for example, a cell might be born if it is bordered by two live neighbors on the north and northeast, but not if it is bordered by two live neighbors on the south and southwest. Non-isotropic rules are described using MAP strings, a notation unrelated to the birth/survival notation.
In Generations rules, additional states are introduced, and cells that do not survive into the next generation instead progress through the subsequent states before dying. Cells in these additional states do not count as live neighbors for the purpose of evolution.
In Larger than Life rules, the size of a cell's neighborhood is extended to include cells with a distance greater than one. As in Generations rules, non-surviving cells may decay through additional states instead of dying outright.
Notes
	1	↑ In common usage, different variations of "lifelike" are also frequently used to refer to other rules that do not necessarily meet all of the criteria listed above (example 1, example 2); a two-state non-totalistic rule, or any rule that is in some sense similar to Conway's Game of Life in behaviour, may also be referred to as life-like. However, this article follows the narrow definition, according to which a Life-like rule is a two-state outer-totalistic rule with range-1 Moore neighbourhood on the square tiling.
See also
	•	List of Life-like cellular automata
	•	Totalistic Life-like cellular automaton
	•	glider.db
References
	1	↑ QuickLife at Golly's online help
External links
	•	
	•	Life-like cellular automaton at Wikipedia
	•	Patterns for other Life-like rules at Jason’s Life Page
	•	David Eppstein. "Which "Life"-Like Systems Have Gliders?".
	•	Interesting Rules at Fano Experimental Web Server
	•	GliderDB Database
Forum threads
	•	
	•	Guns in Life-like cellular automata (discussion thread) at the ConwayLife.com forums
	•	
	•	Spaceships in Life-like cellular automata (discussion thread) at the ConwayLife.com forums
	•	
	•	Oscillators in Life-like cellular automata (discussion thread) at the ConwayLife.com forums
	•	
	•	List of the Turing-complete totalistic life-like CA (discussion thread) at the ConwayLife.com forums
	•	
	•	Knightships in Life-like CA (examples inside!) (discussion thread) at the ConwayLife.com forums
Retrieved from "https://conwaylife.com/w/index.php?title=Life-like_cellular_automaton&oldid=136908"
