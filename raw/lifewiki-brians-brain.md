# OCA:Brian's Brain - LifeWiki

Source: https://conwaylife.com/wiki/OCA:Brian%27s_Brain (LifeWiki; saved HTML from ~/Downloads, converted to text 2026-09-25; site navigation removed)

From LifeWiki
Brian's Brain
LifeViewer-generated pseudorandom soup
View static image
View animated image
Rulestring
/2/3 
B2/S/C3
B2/S/G3
Character
Chaotic
Brian's Brain (also called BB, or simply Brain) is a cellular automaton and one of the best-known Generations rules. It is similar to Seeds, but with an additional state; dead cells get born if they have exactly two live neighbors, and live cells never survive, but instead of dying immediately, they advance to a third state, not considered "live" for the purpose of cell birth, before dying. The rule was first considered by Brian Silverman in the mid-1990s.
Brian's Brain can be thought of as emulating a neural network, with state 0 representing "ready", state 1 representing "firing", and state 2 representing "refractory"; the rule can then be stated as "only a cell in the ready state may fire and it will only do so if exactly 2 of its neighbors are firing. After firing for one step, a cell spends a step in the refractory state before regaining readiness".
On November 12, 2020, Yoel Matveyev published a Rule 110 unit cell for Brian's Brain, proving the rule Turing-complete.[1] The unit's design follows the model of the Rule 110 unit cell constructed by Matveyev for his rule Fireworld and does not contain XOR gates. Instead, it uses AND-NOT gates and toggle flip-flops.
Contents
	•	1 Patterns
	•	2 See also
	•	3 References
	•	4 External links
Patterns
A period-3 oscillator
(click above to open LifeViewer)
Usually, a random starting configuration in Brian's Brain will explode at the speed of light, emitting many spaceships, rakes, breeders, puffers and wavestretchers. Additionally, there is a common c/4 diagonal spaceship called the butterfly.
Although the rule is relatively old, it has never been systematically explored. Due to all patterns being phoenixes, it is not very easy to construct stable patterns in it. The first oscillators were discovered by Michael Sweney in December 1999. No period-2 oscillators exist (as in any Generations rule with more than two states); an example of a period-3 oscillator is shown to the left. Period-4 oscillators are also known to exist.[2] Larger period oscillators with periods divisible by 3 can be constructed by gun reactions. Some periodic agars and wicks have also been constructed in Brian's Brain.
A group of lasers shooting the smallest photon were discovered by Giles Edkins no later than May 2001, based on which signal reflectors, duplicator, AND gate, OR gate and XOR gate have been explicitly constructed,[3] as well as gun constructions shooting various other spaceships and rakes at different periods. Brian's Brain is Turing complete, as demonstrated by an infinitely extendable tiling of Rule 110 units.[1] The tiling also demonstrates a usage of gun period doublers, flip-flops, arbitrary length memory units and custom spaceship flotilla generators used for Rule 110's output display.
On December 31, 2020, Rocknlol found a c/5 orthogonal spaceship in Brian's Brain - the first orthogonal non-light-speed spaceship in this rule.[4]
A collection of patterns in this rule can be found in Mirek's Cellebration.
A period-4 oscillator
(click above to open LifeViewer)
A two-sided wickstrecher
(click above to open LifeViewer)
Another wickstrecher producing a different wick
(click above to open LifeViewer)
See also
	•	Brain 6
	•	Star Wars
	•	Seeds
References
	1	↑ Jump up to:  1.0 1.1 Yoel Matveyev (November 15, 2020). Re: Turing - complete Generations rules (discussion thread) at the ConwayLife.com forums
	2	↑ praosylen (April 16, 2020). Re: Brian's Brain (discussion thread) at the ConwayLife.com forums
	3	↑ FWKnightship (May 12, 2020). Re: Turing - complete Generations rules (discussion thread) at the ConwayLife.com forums
	4	↑ Rocknlol (December 31, 2020). Re: Brian's Brain (discussion thread) at the ConwayLife.com forums
External links
	•	
	•	Brian's Brain (discussion thread) at the ConwayLife.com forums
	•	Brian's Brain at Adam P. Goucher's Catagolue
	•	MCell built-in Generations rules: Brian's Brain at Mirek Wójtowicz's Cellebration page
	•	
	•	Brian's Brain at Wikipedia
Retrieved from "https://conwaylife.com/w/index.php?title=OCA:Brian%27s_Brain&oldid=167670"
