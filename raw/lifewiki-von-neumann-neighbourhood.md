# von Neumann neighbourhood - LifeWiki

Source: https://conwaylife.com/wiki/Von_Neumann_neighbourhood (LifeWiki; saved HTML from ~/Downloads, converted to text 2026-09-25; site navigation removed)

From LifeWiki
The von Neumann neighbourhood (blue) of a single cell
The von Neumann neighbourhood is the set of all cells that are orthogonally adjacent to the region of interest (the region of interest itself may or may not be considered part of the von Neumann neighbourhood, depending on context). For example, the von Neumann neighbourhood of a single cell consists of the four cells orthogonally touching it. This neighbourhood is named after John von Neumann, the creator of the first self-replicating cellular automaton.[1]
The von Neumann neighbourhood naturally extends to cellular automata in higher dimensions, for example forming a 6-cell octahedral neighborhood for a cellular automaton in three dimensions. The number of cells in the von Neumann neighbourhood of a single cell in an n-dimensional cellular automaton is 2n (Sloane's  A005843).
The von Neumann neighbourhood of a cell can be thought of as the points at a Manhattan distance[2] of 1 from that cell.
Higher state counts
With two states, patterns cannot escape their bounding box without B1, which causes patterns to grow at the speed of light, so spaceships are impossible. However, a three-state rule has been found in which many spaceships (and rakes and breeders) exist.[3]
Higher ranges
The von Neumann neighbourhood can also be defined with a higher range; that is, so that it captures cells that are further than one cell away from the region of interest. The standard von Neumann neighbourhood has range 1. The von Neumann neighbourhood of range 2 is the set of all cells that are orthogonally adjacent to the von Neumann neighbourhood itself. The von Neumann neighbourhood of range n can be defined recursively as the von Neumann neighbourhood of the von Neumann neighbourhood of range n - 1. The number of cells in the von Neumann neighbourhood of range n of a single cell is given by 2 n (n + 1) (Sloane's  A046092).
Gallery
	•	 The von Neumann neighbourhood (in blue) of an eater 1
	•	 The von Neumann neighbourhood of range 2 of a single cell
	•	 The von Neumann neighbourhood of range 3 of a single cell
Rules in the Von Neumann neighbourhood
	•	Banks-I, an early two-state Von Neumann rule
See also
	•	Neighbourhood
	◦	Hexagonal neighbourhood
	◦	Margolus neighbourhood
	◦	Moore neighbourhood
	◦	Triangular Moore neighbourhood
	◦	Triangular von Neumann neighbourhood
	•	Zone of influence
References
	1	↑ Tim Tyler. "The von Neumann neighbourhood". Retrieved on June 13, 2009.
	2	↑ Manhattan distance at Wikipedia
	3	↑ calcyman (February 16, 2010). Re: B24/S13 (Von Neumann Neighborhood) , in which Artem Dergachev's rule was mentioned
External links
	•	
	•	von Neumann neighborhood at Wikipedia
	•	
	•	von Neumann neighbourhood at the Life Lexicon
	•	von Neumann neighborhood at Wolfram Mathworld
Retrieved from "https://conwaylife.com/w/index.php?title=Von_Neumann_neighbourhood&oldid=172512"
