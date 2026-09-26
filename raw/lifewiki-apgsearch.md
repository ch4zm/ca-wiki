# apgsearch - LifeWiki

Source: https://conwaylife.com/wiki/Apgsearch (LifeWiki; saved HTML from ~/Downloads, converted to text 2026-09-25; site navigation removed)

From LifeWiki
apgsearch
Homepage
Click here
Purpose
Soup search program
Created by
Adam P. Goucher
Platform
Unix; platform-independent
The Ash Pattern Generator Search program, more commonly known as apgsearch, is an automated search program created by Adam P. Goucher. It generates soups, which by default are asymmetric and 16 × 16, and runs them until stabilization, recording any resulting still lifes, oscillators, spaceships, periodic linear infinite growth patterns, and "unusual growth" patterns. More recent versions also detect soups which are long-lived methuselahs and diehards as well as soups with large final populations.[note 1][note 2] Version 1.x and later upload the results to the online database Catagolue and have a peer-review process for verifying hauls submitted to the site.
Versions 4.x and later of apgsearch use a backend known as lifelib to simulate soups, and can simulate various types of rules and symmetric soups.
Contents
	•	1 Higher symmetries
	◦	1.1 GPU searching
	•	2 Notable patterns
	•	3 Other rules
	◦	3.1 Hexagonal symmetries
	•	4 Limitations
	•	5 Version history
	◦	5.1 Python versions
	▪	5.1.1 Version 0.x
	▪	5.1.2 Version 1.x
	◦	5.2 C++ versions
	▪	5.2.1 Version 2.x
	▪	5.2.2 Version 3.x
	▪	5.2.3 Version 4.x
	▪	5.2.4 Version 5.x
	•	6 Upcoming features
	•	7 See also
	•	8 Notes
	•	9 References
	•	10 External links
	◦	10.1 Code repositories
	◦	10.2 Forum threads
Higher symmetries
112P15
(click above to open LifeViewer)
RLE: here Plaintext: here
Also see: Symmetry
In addition to asymmetric (C1) soups, apgsearch can also run various types of symmetric soup searches and submit the data to Catagolue:
	•	C2_1, C2_2, C2_4: 180° (two-fold) rotational symmetry
	•	C4_1, C4_4: 90° (four-fold) rotational symmetry
	•	D2_+1, D2_+2: reflectional symmetry along an orthogonal line
	•	D2_x: reflectional symmetry along a diagonal line
	•	D4_+1, D4_+2, D4_+4: reflectional symmetry along two perpendicular orthogonal lines
	•	D4_x1, D4_x4: reflectional symmetry along two perpendicular diagonal lines
	•	D8_1, D8_4: reflectional symmetry along four orthogonal/diagonal through a common center
Furthermore, the following pseudo-symmetries are used for asymmetric soups of different sizes:
	•	8x32, 4x64, 2x128, 1x256: for 256-cell soups of size 8 × 32, 4 × 64, 2 × 128 and 1 × 256
8x32 was one of the initial (pseudo-)symmetries the site handled; support for 4x64, 2x128 and 1x256 was added in August 2017.[1]
Inflation of a toy 4 × 4 soup.
All symmetries can be "inflated" using the "i" prefix, replacing each cell in the sample soup with a 2 × 2 alignment of cells in the same state and resulting in soups of size e.g. 32 × 32 for iC1 instead of 16 × 16 for C1. Multiple "i" prefixes can be stacked to "inflate" cells to 4 × 4, 8 × 8, etc.[2]
The 25pct and 75pct pseudo-symmetries were used in the past to investigate soups with initial densities of 0.25 and 0.75 respectively, but they fell into disuse and are not supported by v3.x and above.[note 3] Other pseudo-symmetries such as 25p, 32x32, 1x256X2+1 etc. have been used, but are not considered standard. apgsearch and Catagolue encourage users to use designated "test" symmetries to test modifications to the client.[3]
Although various orthogonal and diagonal gutter symmetries are possible in Conway's Game of Life, apgsearch does not currently have official support for searching with them. However, various users have modified apgsearch in order to search these symmetries and have submitted the results to Catagolue under custom symmetry names.
GPU searching
Since version 5.x, apgsearch supports soup searching on a GPU using CUDA which, depending on the GPU used, can process soups several times faster than a standard CPU search. The GPU deems soups "interesting" which meet certain criteria, and these are then fully censused by the CPU.[note 4] Therefore, the results are uploaded to separate symmetries on Catagolue to avoid distorting the main census statistics, with C and D replaced with G and H respectively.[4] The symmetries currently supported are:
	•	G1 (counterpart to C1)
	•	G2_1, G2_2, G2_4[5]
	•	H2_+1, H2_+2 (D2_+1 and D2_+2)[6]
	•	H4_+1, H4_+2, H4_+4[7]
	•	H2_x, H4_x1, H4_x1, G4_1, G4_4, H8_1, H8_4 (added on October 22, 2025)
Versions 5.061 and above allow GPU searching for any outer-totalistic rule, but not all of them can be searched easily in practice due to common objects meeting the criteria for "interestingness."[6]
Notable patterns
Rich's p16
(click above to open LifeViewer)
RLE: here Plaintext: here
Also see: Catagolue#Results in Conway's Game of Life
A variety of notable natural and semi-natural (i.e. appearing in symmetric soups) patterns were first discovered using apgsearch:
	•	The first known natural occurrence of a nonstandard spaceship was found during alpha testing of the script. The soup, which produced an LWSS on HWSS 1, was posted to the ConwayLife.com forums on August 26, 2014 by Adam P. Goucher.[8] Many other nontrivial spaceship flotillae have since been found.
	•	The pufferfish was discovered in the ash of a symmetric soup in November 2014 by Richard Schank.[9]
	•	The first known natural occurrence of a puffer other than the block-laying or glider-producing switch engine, a p1152 made from two switch engines dubbed the pony express, was found in September 2015 by Apple Bottom.[10]
	•	112P15 was first discovered in the ash of a symmetric soup in April 2016 by Maia Karpovich.[11]
	•	Rich's p16 was first discovered in the ash of a symmetric soup in July 2016 by Rich Holmes.[12]
	•	Maia Karpovich's discovery of a period 28 pre-pulsar-shuttle variant in November 2016 enabled the construction of smaller (in terms of minimum population) period 26 and period 28 pre-pulsar-shuttles.[13]
	•	34P14.1 was first discovered in the ash of a symmetric soup in September 2018 by carybe, but was not noticed on Catagolue until October.[14]
	•	68P9 was first discovered in the ash of a symmetric soup in October 2018 by carybe.[15]
	•	42100M was first discovered in October 2018 by Dave Greene, only two days after apgsearch added support for detecting methuselahs, becoming the longest-lasting known methuselah within a 16 × 16 bounding box at the time.[16] A month later, this was followed by Homer, discovered by Adam P. Goucher and lasting 42883 generations.[17]
	•	Dueling banjos was first discovered in the ash of a symmetric soup in January 2019, in a tetramer form by Apple Bottom.[18]
	•	The record-breaking methuselah 47575M was first discovered in February 2019 by Adam P. Goucher, outlasting Homer by nearly 5000 generations.[19]
	•	Rob's p16 was first discovered by Rob Liston in February 2020 via GPU search, becoming the smallest known p16 oscillator and the first asymmetric object discovered by soup search since the 1980s.[20]
	•	The record-breaking methuselah 49768M was first discovered in April 2020 by Rob Liston, outlasting 47575M by over 2000 generations.[21]
	•	The record-breaking methuselah 50093M was first discovered in January 2021 by Rob Liston, outlasting 49768M by about 300 generations.[22]
	•	The record-breaking methuselah 52513M was first discovered in January 2021 by Dylan Chen, outlasting 50093M by over 2000 generations.[23]
	•	32P21 was first discovered by the Charity Engine distributed computing project in February 2022 using apgsearch, becoming the smallest known p21 oscillator.[24]
	•	30P25 was first discovered by the Charity Engine distributed computing project in May 2022 using apgsearch, becoming the smallest known p25 oscillator.[25]
Other rare objects found by apgsearch in asymmetric soups are smiley, Achim's p8, Elkies' p5, heart, Silver's p5, phoenix 1, the Coe ship, the lightweight Schick engine, the sidecar, the loafer, and a burloaferimeter variant. Sample soups submitted to Catagolue have also led to cheaper glider syntheses for many patterns, including tumbler, eater 2, smiley, and unix. Additionally, the copperhead first emerged from a D2_+2 soup in April 2016 only a month after its initial discovery by zdr, followed by several more later in the year.[26]
Other rules
apgsearch has the ability to run soup searches for various rules other than Conway's Game of Life. In the past, this was restricted to outer-totalistic rules with two states, but versions v4.x and later have added support for various families of rules over time. However, only non-exploding rules can reasonably be investigated in practice unless a certain symmetry can be assured to never explode.
Since v4.86, apgsearch officially supports the following types of cellular automata:
	•	Arbitrary outer-totalistic rules.
	•	Isotropic non-totalistic rules. (in Hensel notation)
	•	Isotropic von Neumann neighbourhood rules. (implicitly by isotropic non-totalistic Moore neighbourhood rules)
	•	Higher-range outer totalistic (HROT) rules. (up to range 5)
	•	Larger than Life rules. (up to range 7)
	•	Totalistic and isotropic hexagonal neighbourhood rules.
	•	Generations variants of all rules listed above.
	•	Outer-totalistic B0 rules with two states.
	•	BSFKL rules.
	•	Deficient rules.
	•	Extended Generations rules.
	•	Custom Golly ruletables.
The Moore neighbourhood and hexagonal neighbourhood are the currently the only directly supported neighbourhoods, although the von Neumann neighbourhood can be indirectly simulated by isotropic Moore rules and the Margolus neighbourhood (specifically block cellular automata) can be simulated by inflated soups on specific rules.
Hexagonal symmetries
Symmetric soups can also be run for rules other than Conway's Game of Life. However, many of the symmetries of the Moore neighbourhood do not apply to the hexagonal grid, and hexagonal rules must therefore use a separate set of symmetries. As of January 2019, this includes the following:
	•	C1, 8x32, 4x64, 2x128: for asymmetric 256-cell soups of size 16 × 16, 8 × 32, 4 × 64, and 2 × 128 respectively
	•	C2_1, C2_2: 180° (two-fold) rotational symmetry
	•	C3_1: 120° (three-fold) rotational symmetry
	•	C6: 60° (six-fold) rotational symmetry
	•	D2_x, D2_xo, 1x256: reflectional symmetry along a single line
	•	D4_x1, D4_x4: reflectional symmetry along two perpendicular lines
	•	D6_1, D6_1o: reflectional symmetry along three lines through a common center
	•	D12: reflectional symmetry along six lines through a common center
The symmetries C3_3 and D6_3, as well as various gutter symmetries, are also possible but have yet to be implemented.[27]
Limitations
Also see: Catagolue#Limitations
Although apgsearch has bespoke support for flotillae composed of standard spaceships in Conway's Life,[note 5] it can fail to properly separate larger non-interacting groups, or groups of any size in non-Life rules. Pseudo still lifes composed of many constituent parts may also fail to be separated properly.[29]
The maximum period for spaceships and oscillators is 1,000 in apgsearch 1.x, 4,000 in apgnano (apgsearch 2.x), 1,280 in apgmera (apgsearch 3.x), and 1,048,576 in apgluxe (apgsearch 4.x and 5.x); higher-period objects are classified as PATHOLOGICAL. High-period linear-growth patterns may not be identified and instead reported as zz_LINEAR. Additionally, the maximum bounding box for any spaceship, oscillator or still life in versions 3.x and before is 40 × 40 due to the limits of the standard apgcode format; larger objects are classified as ov_ (oversized) in these versions.
Version history
Python versions
Two versions of apgsearch, versions 0.x and 1.x, were written in Python for use in Golly.
Version 0.x
apgsearch v0.x was the initial version of the script, first published on September 8, 2014. When running the script, the user is first prompted to enter the number of soups to be searched, the rule under which to search, and the initial seed for soup generation. The script proceeds to search soups in sets of 100 until either the specified number of soups has been exceeded, or the user stops the search by pressing <q>. After the search finishes, Golly opens an HTML window which displays the results.[30] praosylen modified this version to allow soup-searching non-totalistic cellular automata, and made a later modification to allow the results to be uploaded to Catagolue.
Version 1.x
apgsearch v1.x was first released on February 20, 2015. The main improvements from version 0.x are the ability to search symmetrical soups and the periodic uploading of results to Catagolue.[31] apgsearch 1.x supports the following different (pseudo-)symmetries:
	•	C1
	•	C2_1, C2_2, C2_4
	•	C4_1, C4_4
	•	D2_+1, D2_+2
	•	D2_x
	•	D4_+1, D4_+4
	•	D4_x1, D4_x4
	•	D8_1, D8_4
	•	8x32
C++ versions
Four versions of apgsearch, versions 2.x through 5.x, were written in C++. These versions are much faster, and are intended to be run from the command line of a Unix shell.
Version 2.x
apgsearch v2.x, codenamed apgnano, was first published on July 19, 2015 and released onto the conwaylife.com forums on July 28. It uses a bespoke algorithm called Life128, partially written in assembly language for speed, and can utilize both the SSE2 instruction set on x86_64 CPUs. It can only search asymmetric (C1) 16 × 16 soups in Conway Life (B3/S23).[32]
Version 3.x
apgsearch v3.x, codenamed apgmera, was first published on March 3, 2016 and released onto the conwaylife.com forums on March 19. It uses an algorithm called vlife, and unlike version 2.x, it supports arbitrary outer-totalistic rules, as well as the full range of symmetries from apgsearch 1.1. It can use any of the SSE2, AVX1 and AVX2 instruction sets on x86_64 CPUs.
Although the main program is written in C++, version 3.x contains a shell script and a Python file to generate assembly code for different rules and symmetries.[33]
Version 4.x
apgsearch v4.x, codenamed apgluxe and based on lifelib, introduced the following features:
	•	Support for B0 rules.[34][35]
	•	Support for Generations rules (without B0).[36]
	•	Cleaner separation of the different algorithmic layers.[37]
	•	Support for two different containers, based on HashLife and vlife respectively.[37]
	•	Support for 4 × 64, 2 × 128 and 1 × 256 soups.[38]
	◦	Indirect support for some one-dimensional cellular automata using one-cell-thick soups (for example, b026s1 simulates Wolfram rule 2166637080)
	•	An 8% increase in speed in lifelib compared to vlife in version 3.x.
	•	Improved object detection, including:
	◦	Support for extended ("greedy") apgcodes
	◦	Proper detection of oscillator and spaceship periods up to 1,048,576 (220)[39]
Version 4.1 was released on August 21, 2017, and incorporated another rule family, namely:
	•	Support for Larger than Life rules with a range of up to 7.[36][40]
	•	Support for "inflating" soups of arbitrary symmetry (v4.15).[2][41]
	◦	Indirect support for certain Margolus rules, using said inflated soups alongside rules simulating block cellular automata.
Version 4.2 was released on September 10, 2017:
	•	Support for isotropic non-totalistic rules.[34][42]
	◦	Support for the von Neumann neighbourhood (implicitly as isotropic rules).[36]
Version 4.3 was released in June, 2018:
	•	Support for Larger than Life rules with >2 states (i.e. Generations-LtL rules).[43]
	•	Support for isotropic non-totalistic Generations rules (v4.32).[44]
	•	Support for custom backends.[45][46]
Version 4.4 was released in June, 2018:
	•	General speed improvements:
	◦	Special backend for Conway's Game of Life based on a 19-operation circuit by Tomas Rokicki.[47]
	◦	Much faster handling of slow 'tail' soups across all rules.
	◦	Faster oscillator and spaceship classification.
	•	Reduced memory consumption.[48]
Version 4.5 was released in August, 2018:
	•	Detection of methuselahs lasting longer than 25,000 generations in Conway's Game of Life. (v4.54)[49][50][note 2]
	•	Support for BSFKL rules. (v4.56)[51][52]
Version 4.6 was released in October, 2018:
	•	Support for higher-range outer-totalistic cellular automata, up to a range of 5. (v4.63)[53][54]
	•	Support for totalistic, isotropic non-totalistic, and Generations rules using a hexagonal neighbourhood, though with higher symmetries disabled as they had yet to be redesigned to be compatible with the hexagonal grid. (v4.66)[55][56]
	•	Detection of diehards lasting longer than 500 generations in Conway's Game of Life. (v4.69)[57][58]
Version 4.7 was released in December, 2018:
	•	Support for certain higher symmetries in hexagonal neighbourhood rules, particularly:
	◦	D2_x and D2_xo.[59][60]
	◦	C2_1, C2_4, C3_1, C6, D4_x1, D4_x4, D6_1, D6_1o, and D12. (v4.71)[27][61]
Version 4.8 was released in January, 2019:
	•	Support for custom cellular automata using Golly rule tables and trees.[62]
	•	Native support for Deficient and Extended Generations rules. (v4.83)[63]
Version 4.9 was released in February, 2019:
	•	Approximate 50% speed improvement for Conway's Game of Life and certain related rules due to detection of escaping gliders.[64][65]
Version 5.x
apgsearch v5.x was first published on March 20, 2019.[4] The salient new features are:
	•	Improved methodology for splitting work between CPU cores, ensuring threads are not idle.
	•	Support for soup searching on a GPU using CUDA.[66]
	•	Various refactoring and simplification of the underlying code.
	•	Detection of 'megasized' methuselahs with a final population exceeding 3000 in Conway's Game of Life. (v5.03)[67][68]
Version 5.1 was released in April, 2020:
	•	Improved CUDA implementation, making b3s23/G1 searching roughly twice as fast as before.[69][70]
Version 5.2 was released in October, 2020:
	•	Improved object separation.[71]
Version 5.3 was released in January, 2022:
	•	Improved object separation.[72][73]
	•	Improved CUDA implementation for H2 and H4 symmetries. (v5.34)[74][75]
	•	Support for G2_1, G2_2, and G2_4 symmetries. (v5.35)[5][76]
Support for the following features was added in an unknown update:
	•	Support for range-2 far corners, range-3 far edges and range-2 von Neumann isotropic non-totalistic rules.
Upcoming features
The following features are planned for subsequent releases:
	•	Support for additional GPU symmetries.
	•	Support for C3_3 and D6_3 symmetries for the hexagonal neighbourhood.[27]
	•	Support for searching toroidal universes.[77]
	◦	May come with a new "mc" pattern class, for wicks, agars and other infinite patterns.
See also
	•	apgcode
	•	Tutorials/Contributing to Catagolue
Notes
	1	↑ Only methuselahs lasting at least 25,000 generations, diehards lasting at least 500 generations, and soups with final populations of at least 3,000 are reported, and only in Conway's Game of Life.
	2	↑ Jump up to:  2.0 2.1 apgsearch estimates the lifespan of each soup before testing it more precisely, and is not guaranteed to detect all methuselahs with a lifespan of less than 26,000 generations.
	3	↑ The 25% pseudo-symmetry was also briefly used but abandoned due to conflicts with percent-encoding for URIs/URLs.
	4	↑ A soup is deemed interesting if it fails to stabilize with period 6 within 21,000 generations or reaches the boundary of the finite universe (excluding escaping gliders and standard spaceships) considered by the GPU. Large still lifes, low-period oscillators, and diehards are therefore usually ignored.
	5	↑ This formerly excluded MWSS on HWSS 15 and HWSS on HWSS 10.[28] The issue has since been fixed, but it means that the frequency statistics for these two spaceships are somewhat skewed.
References
	1	↑ Adam P. Goucher (August 4, 2017). Re: Hacking apgsearch (discussion thread) at the ConwayLife.com forums
	2	↑ Jump up to:  2.0 2.1 Adam P. Goucher (September 2, 2017). Re: apgsearch v4.0 (discussion thread) at the ConwayLife.com forums
	3	↑ "Census results for B3/S23/"Saka_Test"". Catagolue. Retrieved on December 21, 2016.
	4	↑ Jump up to:  4.0 4.1 Adam P. Goucher (March 20, 2019). apgsearch v5.0 (discussion thread) at the ConwayLife.com forums
	5	↑ Jump up to:  5.0 5.1 Adam P. Goucher (August 5, 2022). Message in #general-discussion on the Conwaylife Lounge Discord server
	6	↑ Jump up to:  6.0 6.1 Adam P. Goucher (March 30, 2019). Re: apgsearch v5.0 (discussion thread) at the ConwayLife.com forums
	7	↑ Arie Paap (April 1, 2019). Re: apgsearch v5.0 (discussion thread) at the ConwayLife.com forums
	8	↑ Adam P. Goucher (August 26, 2014). Re: Thread For Your Accidental Discoveries (discussion thread) at the ConwayLife.com forums
	9	↑ Richard Schank (November 24, 2014). Re: Soup search results (discussion thread) at the ConwayLife.com forums
	10	↑ gameoflifeboy (September 28, 2015). Re: Soup search results (discussion thread) at the ConwayLife.com forums
	11	↑ Maia Karpovich (April 5, 2016). Re: Soup search results (discussion thread) at the ConwayLife.com forums
	12	↑ Ivan Fomichev (July 5, 2016). Re: Soup search results (discussion thread) at the ConwayLife.com forums
	13	↑ Apple Bottom (November 17, 2016). Re: Soup search results (discussion thread) at the ConwayLife.com forums
	14	↑ praosylen (October 11, 2018). Re: Soup search results (discussion thread) at the ConwayLife.com forums
	15	↑ praosylen (October 2, 2018). Re: Soup search results (discussion thread) at the ConwayLife.com forums
	16	↑ Ian07 (October 31, 2018). Re: Soup search results (discussion thread) at the ConwayLife.com forums
	17	↑ Adam P. Goucher (November 30, 2018). Re: Soup search results (discussion thread) at the ConwayLife.com forums
	18	↑ Matthias Merzenich (January 11, 2019). Re: Oscillator Discussion Thread (discussion thread) at the ConwayLife.com forums
	19	↑ Ian07 (February 10, 2019). Re: Soup search results (discussion thread) at the ConwayLife.com forums
	20	↑ Matthias Merzenich (February 10, 2020). Re: Oscillator Discussion Thread (discussion thread) at the ConwayLife.com forums
	21	↑ Ian07 (April 23, 2020). Re: Soup search results (discussion thread) at the ConwayLife.com forums
	22	↑ Ian07 (January 9, 2021). Re: Soup search results (discussion thread) at the ConwayLife.com forums
	23	↑ creeperman7002 (January 17, 2021). Re: Soup search results (discussion thread) at the ConwayLife.com forums
	24	↑ David Raucci (February 11, 2022). Re: Oscillator Discussion Thread (discussion thread) at the ConwayLife.com forums
	25	↑ cvojan (May 18, 2022). Re: Soup search results (discussion thread) at the ConwayLife.com forums
	26	↑ Apple Bottom (April 4, 2016). Re: Soup search results (discussion thread) at the ConwayLife.com forums
	27	↑ Jump up to:  27.0 27.1 27.2 Adam P. Goucher (December 20, 2018). Re: apgsearch v4.0 (discussion thread) at the ConwayLife.com forums
	28	↑ Adam P. Goucher (July 18, 2019). Re: Thread for basic questions (discussion thread) at the ConwayLife.com forums
	29	↑ Park Shinhwan (박신환) (November 28, 2016). Re: Soup search results (discussion thread) at the ConwayLife.com forums
	30	↑ Adam P. Goucher (September 8, 2014). apgsearch: a high-performance soup searcher (discussion thread) at the ConwayLife.com forums
	31	↑ Adam P. Goucher (February 20, 2015). apgsearch v1.0 (discussion thread) at the ConwayLife.com forums
	32	↑ Adam P. Goucher (July 28, 2015). apgsearch v2.2 (discussion thread) at the ConwayLife.com forums
	33	↑ Adam P. Goucher (March 19, 2016). apgsearch v3.1 (discussion thread) at the ConwayLife.com forums
	34	↑ Jump up to:  34.0 34.1 Adam P. Goucher (August 3, 2017). Re: apgsearch v3.1 (discussion thread) at the ConwayLife.com forums
	35	↑ Adam P. Goucher (August 19, 2017). "B0 support". GitLab.
	36	↑ Jump up to:  36.0 36.1 36.2 Adam P. Goucher (August 4, 2017). Re: apgsearch v3.1 (discussion thread) at the ConwayLife.com forums
	37	↑ Jump up to:  37.0 37.1 Adam P. Goucher (August 13, 2017). Re: Extending apgcodes to larger patterns (discussion thread) at the ConwayLife.com forums
	38	↑ Adam P. Goucher (August 11, 2017). "More symmetries". GitLab.
	39	↑ lifelib v1.22, classifier.h line 434
	40	↑ Adam P. Goucher (August 21, 2017). "Larger than Life". GitLab.
	41	↑ Adam P. Goucher (September 2, 2017). "Inflated symmetries". GitLab.
	42	↑ Adam P. Goucher (September 10, 2017). "Supports non-totalistic rules". GitLab.
	43	↑ Adam P. Goucher (June 3, 2018). "LtL Generations". GitLab.
	44	↑ Adam P. Goucher (June 3, 2018). "Isotropic Generations". GitLab.
	45	↑ Adam P. Goucher (June 3, 2018). Re: apgsearch v4.0 (discussion thread) at the ConwayLife.com forums
	46	↑ Adam P. Goucher (June 3, 2018). "Support genera". GitLab.
	47	↑ Adam P. Goucher (June 12, 2018). "Merge branch 'b3s23life' into 'master'". GitLab.
	48	↑ Adam P. Goucher (June 4, 2018). Re: apgsearch v4.0 (discussion thread) at the ConwayLife.com forums
	49	↑ Adam P. Goucher (October 28, 2018). Re: apgsearch 4.0 (discussion thread) at the ConwayLife.com forums
	50	↑ Adam P. Goucher (October 28, 2018). "Preliminary support for methuselahs". GitLab.
	51	↑ Apple Bottom (2018-11-03). Re: apgsearch v4.0 (discussion thread) at the ConwayLife.com forums
	52	↑ Adam P. Goucher (October 29, 2018). "BSFKL rulespace". GitLab.
	53	↑ Adam P. Goucher (November 6, 2018). Re: Thread for basic non-CGOL questions (discussion thread) at the ConwayLife.com forums
	54	↑ Adam P. Goucher (November 7, 2018). "Higher-range outer-totalistic rules". GitLab.
	55	↑ Adam P. Goucher (December 1, 2018). Re: Non-totalistic hex rules (discussion thread) at the ConwayLife.com forums
	56	↑ Adam P. Goucher (December 1, 2018). "Hexagonal rules". GitLab.
	57	↑ Ian07 (December 11, 2018). Re: apgsearch v4.0 (discussion thread) at the ConwayLife.com forums
	58	↑ Adam P. Goucher (December 11, 2018). "Detect messless methuselahs". GitLab.
	59	↑ Adam P. Goucher (December 19, 2018). Re: apgsearch v4.0 (discussion thread) at the ConwayLife.com forums
	60	↑ Adam P. Goucher (December 19, 2018). "Support two more hexagonal symmetries". GitLab.
	61	↑ Adam P. Goucher (December 20, 2018). "More hexagonal symmetries". GitLab.
	62	↑ Adam P. Goucher (January 9, 2019). "Support for custom rules and neighbourhoods". GitLab.
	63	↑ Adam P. Goucher (January 15, 2019). "Native support for Extended Generations and Deficient rules courtesy of M. I. Wright". GitLab.
	64	↑ Adam P. Goucher (February 4, 2019). Re: apgsearch v4.9 (discussion thread) at the ConwayLife.com forums
	65	↑ Adam P. Goucher (February 4, 2019). "Escaping glider detection". GitLab.
	66	↑ Adam P. Goucher (March 20, 2019). "Working GPU version". GitLab.
	67	↑ Adam P. Goucher (March 24, 2019). Re: apgsearch v5.0 (discussion thread) at the ConwayLife.com forums
	68	↑ Adam P. Goucher (March 24, 2019). "Log soups with final population exceeding 3000 -- thanks to 'testitemqlstudop' for the suggestion". GitLab.
	69	↑ Adam P. Goucher (April 24, 2020). Message in #tools on the Conwaylife Lounge Discord server
	70	↑ Adam P. Goucher (April 24, 2020). "Include faster GPU implementation". GitLab.
	71	↑ Adam P. Goucher (October 15, 2020). "Better object separation". GitLab.
	72	↑ Adam P. Goucher (January 18, 2022). Re: apgsearch v5.0 (discussion thread) at the ConwayLife.com forums
	73	↑ Adam P. Goucher (January 18, 2022). "Correct object separation". GitLab.
	74	↑ Adam P. Goucher (August 5, 2022). Message in #general-discussion on the Conwaylife Lounge Discord server
	75	↑ Adam P. Goucher (August 5, 2022). "Make higher symmetries 3x faster on GPU for b3s23". GitLab.
	76	↑ Adam P. Goucher (August 5, 2022). "Add new GPU symmetries: G2_1, G2_2, G2_4". GitLab.
	77	↑ Adam P. Goucher (August 5, 2017). Re: Hacking apgsearch (discussion thread) at the ConwayLife.com forums
External links
	•	About - Catagolue
	•	apgsearch - Catagolue (contains links to both v5.x and v1.x)
	•	
	•	apgsearch at the Life Lexicon
Code repositories
	•	apgmera (apgsearch 3.x) / apgluxe (apgsearch 4.x / 5.x) code repository
	•	lifelib code repository
	•	Catagolue code repository
Forum threads
	•	
	•	apgsearch v5.0 (discussion thread) at the ConwayLife.com forums
	•	
	•	apgsearch v4.0 (discussion thread) at the ConwayLife.com forums
	•	
	•	apgsearch v3.1 (discussion thread) at the ConwayLife.com forums
	•	
	•	apgsearch v2.2 (discussion thread) at the ConwayLife.com forums
	•	
	•	apgsearch v1.0 (discussion thread) at the ConwayLife.com forums
	•	
	•	apgsearch: a high-performance soup searcher (discussion thread) at the ConwayLife.com forums (original discussion thread)
	•	
	•	Hacking apgsearch (discussion thread) at the ConwayLife.com forums
	•	
	•	Soup search results (discussion thread) at the ConwayLife.com forums
[show]
Adam P. Goucher's Catagolue
[show]
Golly
Retrieved from "https://conwaylife.com/w/index.php?title=Apgsearch&oldid=167237"
