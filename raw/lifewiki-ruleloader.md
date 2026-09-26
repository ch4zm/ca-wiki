# RuleLoader - LifeWiki

Source: https://conwaylife.com/wiki/RuleLoader (LifeWiki; saved HTML from ~/Downloads, converted to text 2026-09-25; site navigation removed)

From LifeWiki
(Redirected from Ruletable)
This article is a stub. You can help LifeWiki by expanding it.
RuleLoader is the algorithm that Golly uses to simulate .rule files, also known as rule tables and rule trees. A description of the file format is provided in Golly's built-in help.[1][2]
Description
See also: Tutorials/Creating custom rules
The RuleLoader algorithm allows rules to be specified in external files. Given the rule string "Foo", RuleLoader will search for a file called Foo.rule.[1]
A .rule file contains all the information about a rule: its name, documentation, table/tree data (used by the RuleLoader algorithm), and any color/icon information. The .rule format is textual and consists of one or more sections. Each section starts with a line of the form @XXX... where X is an uppercase letter. If there is more than one section with the same name then only the first one is used. Any unrecognized sections are silently ignored.[2]
The currently recognized sections are:[2]
	•	@RULE (mandatory)
	•	@TABLE (optional)
	•	@TREE (optional)
	•	@COLORS (optional)
	•	@ICONS (optional)
See also
	•	Nutshell
References
	1	↑ Jump up to:  1.0 1.1 RuleLoader at Golly's online help (Help → Algorithms → RuleLoader)
	2	↑ Jump up to:  2.0 2.1 2.2 Rule format at Golly's online help (Help → File formats → Rule format)
External links
	•	
	•	Rule request thread (discussion thread) at the ConwayLife.com forums
	•	
	•	RuleLoader's B0 handling quirks (discussion thread) at the ConwayLife.com forums
	•	"Rule Table Repository". github.com/GollyGang.
[hide]
Golly
People
Golly Gang (Andrew Trevorrow • Tomas Rokicki • Dave Greene • Jason Summers • Tim Hutton • Maks Verver • Robert Munafo • Chris Rowett • Dongook Lee)
Algorithms
QuickLife • HashLife • Generations • Larger than Life • LifeSuper • RuleLoader
Formats
Pattern formats (RLE • Macrocell • MCell • Life 1.05 • Life 1.06) • Rule formats (Rule table • Rule tree)
Scripts
apgsearch v0.x and v1.x
Tutorials
Golly • More Golly • Creating custom rules • Scripts (Your first Python script • Glider syntheses • Contributing to 5S • Contributing to Catagolue with Golly)
Related
Cellular automaton simulation programs by supported rulespaces • LifeLab
Retrieved from "https://conwaylife.com/w/index.php?title=RuleLoader&oldid=126407"
