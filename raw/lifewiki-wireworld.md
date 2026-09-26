# OCA:WireWorld - LifeWiki

Source: https://conwaylife.com/wiki/OCA:WireWorld (LifeWiki; saved HTML from ~/Downloads, converted to text 2026-09-25; site navigation removed)

From LifeWiki
(Redirected from Wireworld)
Two WireWorld diodes, the above one in conduction direction, the lower one in reverse-biasing
(click above to open LifeViewer)
WireWorld is a 4-state cellular automaton operating in a range-1 2-dimensional Moore neighborhood. It was first proposed by Brian Silverman in 1987 and included in his program PHANTOM FISH TANK. It became widely known after A. K. Dewdney publicized WireWorld in his "Computer Recreations" column.[1] WireWorld is particularly suited for simulating digital electronic circuits. Given an infinite tiling of properly put "wires", WireWorld is Turing-complete.
Unlike Life-like cellular automata, the entire evolution of WireWorld patterns is confined within so-called wires, static structures, which may not be created, modified or destroyed, but may change the state of their cells in a way resembling the behavior of electronic circuits. Oscillators in WireWorld are wire structures that pass "electrons" as signals periodically, while clocks, electron-producing circuits, may be considered an analogue of guns.
Rules
The WireWorld universe has the following states:
	•	State 0: empty (black),
	•	State 1: electron head (blue),
	•	State 2: electron tail (red),
	•	State 3: conductor (yellow).
Cells behave as follows:
	•	empty → empty,
	•	electron head → electron tail,
	•	electron tail → conductor,
	•	conductor → electron head if exactly one or two of the neighboring cells are electron heads, otherwise remains conductor.
In other words, patterns composed of state 1 and state 2 cells in a pure state 3 background behave like /12/3, an explosive Generations rule.
WireWorld computer
WireWorld rules allow to construct very small and robust logic gates, triggers, memory banks etc., from which complex computational devices could be easily built.
In September 2004 David Moore and Mark Owen released a WireWorld computer, in which the results of calculations are shown in seven-segment displays by running "electrons". The computer's instruction set is a highly orthogonal RISC architecture. The program, CPU status and data are stored in a bank of 64 16-bit registers. According to the authors, the computer was designed, with the help of many others, between 1990 and 1992. The version of it included in Golly is preprogrammed to compute and display the sequence of prime numbers.
See also
	•	Unit cell
	•	Universal computer
	•	FireWorld
References
	1	↑ Dewdney, A. K. (January 1990), "Computer recreations: The cellular automata programs that create Wireworld, Rugworld and other diversions", Scientific American 262 (1): 146–149
External links
	•	
	•	WireWorld at Wikipedia
	•	MCell built-in Rules tables:Wire World at Mirek Wójtowicz's Cellebration page
	•	Nyles Heise. "World Wide WireWorld". Retrieved on November 19, 2022.
	•	Mark Owen. "The WireWorld computer". quinapalus. Retrieved on November 19, 2022.
	•	Ed Pegg Jr.‏‎ (May 24, 2004). "WireWorld Multiplication". Math Games. Retrieved on May 17, 2021.
	•	"Wireworld". Rosetta Code.
Retrieved from "https://conwaylife.com/w/index.php?title=OCA:WireWorld&oldid=167120"
