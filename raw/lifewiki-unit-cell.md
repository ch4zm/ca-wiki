# Unit cell - LifeWiki

Source: https://conwaylife.com/wiki/Unit_cell (LifeWiki; saved HTML from ~/Downloads, converted to text 2026-09-25; site navigation removed)

From LifeWiki
A unit cell (or metacell) is a subset (usually rectangular or square) of the Life plane that tiles over the plane, along with a fixed number of distinct patterns, with each tile assuming one of the patterns, such that it simulates a cellular automaton, possibly itself. A unit Life cell is a unit cell that simulates the Game of Life. To avoid single cells themselves being considered unit cells, the size of a unit cell must be greater than 1 × 1. It is also a restriction that only finite sized patterns are accepted as unit cells excluding infinite one-cell thick bars in HighLife for example, which simulates Rule 54; many amphichiral 1D elementary automata can be embedded in other rules via this method.
Contents
	•	1 Simulating a 2D cellular automaton
	•	2 Simulating a 1D cellular automaton
	◦	2.1 Natural occurrences
	◦	2.2 Constructions
	▪	2.2.1 Selection of Life-like rules with constructed W110 unit cells
	•	3 References
	•	4 External links
Simulating a 2D cellular automaton
The first unit Life cell was constructed by David Bell in 1996.[1] It employs standard glider logic to determine whether or not a glider should be present. The two states differ by a single glider. In 2004, Jared James Prince modified David Bell's unit Life cell to support two (and therefore multiple) layers of Life universes, coined "deep cell".[2]
Around 2005, the OTCA metapixel was constructed, which can simulate any Life-like cellular automaton.[3] Designed to run quickly in HashLife, it has the advantage of having two states that are clearly distinct when zoomed out.
The p1 megacell, designed in 2008, has clearly visible states like the OTCA metapixel. It is capable of simulating any rule, including non-totalistic and asymmetric rules, that uses the standard eight-cell neighborhood. It also has unusual positioning, being a square with diagonal edges. This allows much of its information to be transmitted with gliders.
The 0E0P metacell is currently the largest unit cell. Unlike other unit cells, it can function without any form of support circuitry, allowing it to produce the first examples of exotic patterns such as parity-rule replicators and reflectorless rotating oscillators in Life when programmed correctly. Rather than having an "on" state or an "off" state, it deconstructs itself when it turns off and is built by its neighbors when it is turned on.
Simulating a 1D cellular automaton
Natural occurrences
Parity rule replicators can be described as simulating a one-dimensional cellular automaton. For example, the replicator in HighLife can be described as simulating Rule 6 on a range-1/2 one-dimensional neighbourhood. If considered as being period 24 rather than period 12, it could be considered as following Rule 90, to which the replicator's habit is commonly, if erroneously, simplified to.
Certain basic infinite-growth patterns could arguably be considered replicators that simulate rules such as Rule 50[4] and Rule 254[5].
Interestingly, the U-pentomino is a period-8 natural replicator that emulates Rule 110 in rules between B2ei3aci4aei5kqr7e/S01c2-kn3ijry4citwy5aeiq and B2ein3acikq4-jrty5-ceiy6-ck78/S01c2-k3-acen4-a5-jny6-c78. This pattern was found by iNoMed[6] and ranked second place in the OCA Discovery of the Year 2020 competition on the ConwayLife.com forums, behind a collection of Day and Night knightships.[7] In the 1st of January 2021, AforAmpere found[8] a faster one, the T-tetromino with period 2 in rules supporting rules from B2ai3aeir4r5ei/S3e5e6i to B2-c34-i56-i78/S2-ai3-i4-e5678.
So far, the following 1D rules are known:
	•	Rule 0[9]
	•	Rule 2[9]
	•	Rule 4[9]
	•	Rule 16[9]
	•	Rule 22[9]
	•	Rule 32[9]
	•	Rule 50[9]
	•	Rule 90[9]
	•	Rule 110[6][8]
	•	Rule 128[9]
	•	Rule 150[9]
	•	Rule 254[9]
Rules of larger ranges are also known:
	•	Rule W1208925819614629174771760[9]
Constructions
Complex one-dimensional cellular automata usually can be simulated via constructed unit cells. Purpose of this is basically the containing automaton inherits some useful properties of the embedded, which is usually not trivial to prove. Such properties are logic universality, Turing-completeness, etc. It is known that many examples are constructed in order to simulate Rule 110 and allegedly Rule 30 in one case. One is constructed in CGoL by Jason Summers[10] and later it was trivially shown using Golly that it is a polyglot (works in EightLife, too).
Selection of Life-like rules with constructed W110 unit cells
	•	B3[8]/S23[8] polyglot: works in Life, EightLife, Pedestrian Life and HoneyLife[11]
	•	Banks-I: proves logic universality using Matthew Cook's results,[12] simplifying Roger Banks' proofs from 1971[13]
	•	B35/S236[14]
	•	DryLife and 3 more[15]
	•	2×2[16]
	•	Move[17]
	•	B36[8]/S236[8] polyglot: HighLife, LowDeath, and others[18]
	•	Life without death[19]
	•	Live Free or Die[20]
	•	Day & Night[21]
	•	Seeds[22]
	•	DotLife using a two-dimensional emulator[23]
	•	Grounded Life using a beehive and block fuse[24]
	•	Brian's Brain[25]
	•	Sqrt replicator rule[26]
	•	Star Wars using a cyclical emulator[27]
	•	Bosco's Rule[28]
References
	1	↑ The Unit Life Cell at Paul Callahan's Page of Conway's Life Miscellany
	2	↑ Jared Prince (September 27, 2004). "Game of Life Deep Cell".
	3	↑ Brice Due (May 28, 2006). "How Does It Work?". OTCAmetapixel. Retrieved on March 26, 2009.
	4	↑ Re: Thread for basic non-CGOL questions (discussion thread) at the ConwayLife.com forums
	5	↑ Re: Thread for basic non-CGOL questions (discussion thread) at the ConwayLife.com forums
	6	↑ Jump up to:  6.0 6.1 toroidalet (December 19, 2020). Re: Rules with interesting replicators (discussion thread) at the ConwayLife.com forums
	7	↑ Peter Naszvadi (May 2, 2021). Re: OCA DOTY 2020 Voting (discussion thread) at the ConwayLife.com forums
	8	↑ Jump up to:  8.0 8.1 AforAmpere (January 1, 2021). Re: Rules with interesting replicators (discussion thread) at the ConwayLife.com forums
	9	↑ Jump up to:  9.00 9.01 9.02 9.03 9.04 9.05 9.06 9.07 9.08 9.09 9.10 9.11 Connor Steppie (June 29, 2018). Replicators and other patterns that simulate even 1D rules (discussion thread) at the ConwayLife.com forums
	10	↑ "Rule 110" Unit Cell at Game of Life News. Posted by Heinrich Koenig on December 21, 2005.
	11	↑ Peter Naszvadi (November 21, 2017). FWSS-less MWSS-track-only Rule-110 Unit Cell (discussion thread) at the ConwayLife.com forums
	12	↑ Wikipedia:Rule 110
	13	↑ Peter Naszvadi (November 1, 2017). Re: List of the Turing-complete totalistic life-like CA (discussion thread) at the ConwayLife.com forums
	14	↑ Peter Naszvadi (October 14, 2017). Re: List of the Turing-complete totalistic life-like CA (discussion thread) at the ConwayLife.com forums
	15	↑ Peter Naszvadi (March 29, 2018). Re: List of the Turing-complete totalistic life-like CA (discussion thread) at the ConwayLife.com forums
	16	↑ FWKnightship (February 4, 2021). Re: List of the Turing-complete totalistic life-like CA (discussion thread) at the ConwayLife.com forums
	17	↑ Layz Boi (August 20, 2020). Re: List of the Turing-complete totalistic life-like CA (discussion thread) at the ConwayLife.com forums
	18	↑ Peter Naszvadi (July 29, 2018). Re: List of the Turing-complete totalistic life-like CA (discussion thread) at the ConwayLife.com forums
	19	↑ Peter Naszvadi (October 13, 2020). Re: List of the Turing-complete totalistic life-like CA (discussion thread) at the ConwayLife.com forums
	20	↑ FWKnightship (October 20, 2020). Re: List of the Turing-complete totalistic life-like CA (discussion thread) at the ConwayLife.com forums
	21	↑ Peter Naszvadi (August 14, 2020). Re: List of the Turing-complete totalistic life-like CA (discussion thread) at the ConwayLife.com forums
	22	↑ Peter Naszvadi (October 30, 2020). Re: List of the Turing-complete totalistic life-like CA (discussion thread) at the ConwayLife.com forums
	23	↑ FWKnightship (December 30, 2020). Re: List of the Turing-complete totalistic life-like CA (discussion thread) at the ConwayLife.com forums
	24	↑ Anivec (August 3, 2023). Re: B35/S23 (discussion thread) at the ConwayLife.com forums
	25	↑ Yoel Matveyev (November 15, 2020). Re: Turing - complete Generations rules (discussion thread) at the ConwayLife.com forums
	26	↑ Peter Naszvadi (August 19, 2020). Re: List of the Turing-complete totalistic life-like CA (discussion thread) at the ConwayLife.com forums
	27	↑ FWKnightship (November 18, 2020). Re: Star Wars Rule (discussion thread) at the ConwayLife.com forums
	28	↑ Yoel Matveyev (February 12, 2023). Re: Larger than Life (discussion thread) at the ConwayLife.com forums
External links
	•	
	•	Unit cell at the Life Lexicon
	•	
	•	Metacell at the Life Lexicon
Retrieved from "https://conwaylife.com/w/index.php?title=Unit_cell&oldid=163941"
