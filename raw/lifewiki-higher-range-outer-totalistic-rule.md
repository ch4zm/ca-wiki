# Higher-range outer-totalistic rule - LifeWiki

Source: https://conwaylife.com/wiki/Higher-range_outer-totalistic_rule (LifeWiki; saved HTML from ~/Downloads, converted to text 2026-09-25; site navigation removed)

From LifeWiki
(Redirected from Higher-range outer-totalistic cellular automata)
Higher-range outer-totalistic (abbreviated as HROT) is a natural generalization of Larger than Life (LtL) rules, and separately a generalization of outer-totalistic rules.
As defined by Kellie Michele Evans in her 1996 thesis, the historical Larger than Life rules only allow to define one range of birth and one range of survival conditions. Unlike LtL, HROT rules allow to define any list of birth and survival conditions. The new state of a cell in the next generation is a function of the number of cells in its neighbourhood and the cell's own state. If the cell is alive, the survival conditions are followed; If the cell is empty, the birth conditions are followed. Like LtL, It also supports higher range Generations rules.
HROT rules are supported by Golly 4.0 and onwards and by LifeViewer.[1]
Notation
HROT rules can be described using the general-range outer-totalistic notation:
Rr,Cc,Slist,Blist,Nn
	•	Rr specifies the neighborhood range (Golly supports r from 1 to 500, except for the Triangular neighbourhood where r is from 1 to 250).
	•	Cc specifies the number of states (Golly supports c from 0 to 256).
	•	Ss specifies the counts for a state 1 cell to survive.
	•	Bb specifies the counts for a dead cell to become a birth.
	•	Nn specifies the extended neighborhood type and can be omitted for the Moore neighbourhood.
The Nn code may be, as defined in Golly:
	•	NM for Moore neighbourhood (optional).
	•	NN for von Neumann neighbourhood.
	•	NC for Circular neighborhood.
	•	N2 for L2/Euclidean neighborhood.
	•	NB for Checkerboard neighborhood.
	•	ND for Aligned Checkerboard neighborhood.
	•	N# for Hash neighborhood.
	•	N+ for Cross neighborhood.
	•	NX for Saltire neighborhood.
	•	N* for Star neighborhood.
	•	NH for Hexagonal.
	•	NA for Asterisk.
	•	N3 for Tripod.
	•	NL for Triangular.
	•	N@ for Custom.
	•	NW for Weighted.
LifeViewer also supports:
	•	NF for Far Corners/Edges.
See also
	•	Generations
	•	Larger than Life
References
	1	↑ Chris Rowett (January 2, 2019). Re: Pattern viewer for forum threads (discussion thread) at the ConwayLife.com forums
External links
	•	Higher-range outer-totalistic rule at Golly's online help
	•	
	•	Larger than Life (discussion thread) at the ConwayLife.com forums
	•	
	•	HROT,NW (Higher-range outer-totalistic, weighted) (discussion thread) at the ConwayLife.com forums
Retrieved from "https://conwaylife.com/w/index.php?title=Higher-range_outer-totalistic_rule&oldid=154964"
