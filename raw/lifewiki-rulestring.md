# Rulestring - LifeWiki

Source: https://conwaylife.com/wiki/Rulestring (LifeWiki; saved HTML from ~/Downloads, converted to text 2026-09-25; site navigation removed)

From LifeWiki
Rulestrings are a way of describing the behavior of various classes of cellular automaton in the form of a string. Two notations are in use for Life-like rules: the birth/survival notation and S/B notation.
Birth/survival notation
The most common notation for rulestrings B{number list}/S{number list}; this is referred to as the birth/survival notation, and is sometimes called the rulestring of the CA in question. B (for birth) is a list of all the numbers of live neighbors that cause a dead cell to come alive (be born); S (for survival) is a list of all the numbers of live neighbors that cause a live cell to remain alive (survive).
As an example, the seeds rulestring is B2/S. All dead cells that have exactly two adjacent live cells will come alive in the next generation, while every live cell dies in every generation, since the survival list is empty. The rulestring of Conway's Game of Life is B3/S23.
S/B notation
The most common other format is {number list}/{number list}, called "S/B notation", where the number lists are the numbers of neighbours that cause a live cell to survive and a dead cell to be born respectively. In this format, Conway's Game of Life would have the rulestring 23/3. S/B notation used to be more common, but has fallen into disuse in recent years.
Neighbourhoods
Conventionally, a suffixed V indicates that the CA in question uses the von Neumann neighbourhood, while a suffixed H indicates use of the hexagonal neighbourhood.
Other types of rulestrings
Non-totalistic rules use a variant of the birth/survival notation called Hensel notation, after Alan Hensel, where each number in the list of birth and survival conditions is followed by an optional list of relative cell alignments.
Generations rules can use B/S or S/B notation, with the latter being more common, and add a suffix indicating the rule's number of states; when using the birth/survival notation, this may be prefixed with a C or G, so for example, B25/S03467/C6 and 03467/25/6 describe the same CA.
Finally, Larger than Life rules use rulestrings of a different form that specify the rule's range, number of states, survival and birth counts, and neighborhood type.
Other notations
Rule integers are an alternative way of describing the behavior of Life-like cellular automata, using integers rather than strings.
Non-isotropic rules, including non-isotropic Generations rules, are typically described using MAP strings: 512-bit integers encoded as base64 strings.
See also
	•	Rulespace
Retrieved from "https://conwaylife.com/w/index.php?title=Rulestring&oldid=136289"
