<!-- Source: https://planetmath.org/gardenofedentheorem (fetched 2026-09-24; math converted from MathML alttext to LaTeX) -->

## Garden-of-Eden theorem

Edward F. Moore’s Garden-of-Eden theorem
was the first rigorous statement of cellular automata theory.
Though originally stated for cellular automata on the plane,
it works in arbitrary dimension.

## Theorem 1 (Moore, 1962)

Let
$\mathcal{A}=\langle Q,\mathcal{N},f\rangle$
be a cellular automaton on $\mathbb{Z}^{d}$ with finitely many states.
If $\mathcal{A}$ has two mutually erasable patterns,
then it has an orphan pattern.

In other words,
surjective $d$-dimensional cellular automata are pre-injective.

The same year, John Myhill proved the converse implication.

## Theorem 2 (Myhill, 1962)

Let
$\mathcal{A}=\langle Q,\mathcal{N},f\rangle$
be a cellular automaton on $\mathbb{Z}^{d}$ with finitely many states.
If $\mathcal{A}$ has an orphan pattern,
then it has two mutually erasable patterns.

In other words,
pre-injective $d$-dimensional cellular automata are surjective.

## Corollary 1

An injective $d$-dimensional cellular automaton is surjective.

Theorems 1 and 2 hold because of the following statement.

## Lemma 1

Let $a>0$, $d\geq 1$, $r\geq 1$, $k\geq 1$.
For every sufficiently large $n$,

$(a^{k^{d}}-1)^{n^{d}}<a^{(kn-2r)^{d}}$

(1)

Observe that,
if $a=|Q|$ and

$\mathcal{N}=\{x\in\mathbb{Z}^{d}\mid|x_{i}|\leq r\,\forall i\in\{1,\ldots,d\}%
\}\;,$

(2)

then $(a^{kn})^{d}$
is the number of possible hypercubic patterns of side $kn$,
while $(a^{kn-2r})^{d}$
is the maximum number of their images via $f$.

Proof.
The inequality (1) is in fact satisfied
precisely by those $n$ that satisfy

$\log_{a}(a^{k^{d}}-1)<\left(k-\frac{2r}{n}\right)^{d}\;,$

which is true for $n$ large enough since
$\log_{a}(a^{k^{d}}-1)<k^{d}$
while
$\lim_{n\to\infty}(k-2r/n)^{d}=k^{d}.$
$\Box$

For the rest of this entry, we will suppose
that the neighborhood index $\mathcal{N}$
has the form (2).

Proof of Moore’s theorem.
Suppose $\mathcal{A}$ has two mutually erasable patterns $p_{1}$, $p_{2}$:
it is not restrictive to suppose that their common support
is a $d$-hypercube of side $k$.
Define an equivalence relation $\rho$ on patterns of side $n$
by stating that $p\rho q$ if and only if $f(p)=f(q)$:
since $p_{1}$ and $p_{2}$ are mutually erasable,
$\rho$ has at most $|Q|^{k^{d}}-1$ equivalence classes.

By the same criterion,
we define a family $\{\rho_{n}\}_{n\geq 1}$ of equivalence relations between hypercubic patterns of side $kn$.
Each such pattern can be subdivided
into $n^{d}$ subpatterns of side $k$:
and it is clear that,
if two patterns are in relation $\rho_{n}$,
then each of those subpatterns is in relation $\rho$.

But then, the relation $\rho_{n}$
cannot have more than $(|Q|^{k^{d}}-1)^{n^{d}}$ equivalence classes:
consequently, at most $(|Q|^{k^{d}}-1)^{n^{d}}$ patterns of side $kn-2r$
can have a preimage.
By Lemma 1 with $a=|Q|$,
for $n$ large enough, some patterns of side $kn-2r$ must be orphan.
$\Box$

Proof of Myhill’s theorem.
Let $p$ be an orphan pattern for $\mathcal{A}$.
Again, it is not restrictive to suppose
that the support of $p$ is a hypercube of side $k$.
For $n\geq 1$
let $\nu_{n}$ be the number of patterns of side $kn$
that are not orphan.
Split each pattern of side $kn$
into $n^{d}$ patterns of side $k$, as we did before.
Then $\nu_{n}$ cannot exceed the number of those
that do not contain a copy of $p$,
which in turn is at most $(|Q|^{k^{d}}-1)^{n^{d}}$.

Take $n$ so large that (1) is satisfied:
for a fixed state $q_{0}\in Q$, and for $q_{1}=f(q_{0},\ldots,q_{0})$,
there are more configurations that take value $q_{0}$
outside the hypercube $\{0,\ldots,kn-2r-1\}^{d}$
than there are configurations that take value $q_{1}$
outside the hypercube $\{-r,\ldots,kn-1\}^{d}$
and are not Gardens of Eden.
As the configurations of the second type
are the images of those the first type,
there must be two with the same image:
those configurations correspond to two mutually erasable patterns.
$\Box$

Theorems 1 and  2
have been shown [2]
to hold for cellular automata on amenable groups.
Moore’s theorem, in fact, characterizes amenable groups
(cf. [1]):
whether Myhill’s theorem also does,
is an open problem.

## References

1

Bartholdi, L. (2010)
Gardens of Eden and amenability on cellular automata.
J. Eur. Math. Soc. 12(1), 141–148.
Preprint: arXiv:0709.4280v1

2

Ceccherini-Silberstein, T., Machì, A. and Scarabotti, F. (1999)
Amenable groups and cellular automata.
Annales de l’Institut Fourier, Grenoble 49(2), 673–685.

3

Moore, E.F. (1962)
Machine models of self-reproduction.
Proc. Symp. Appl. Math. 14, 17–33.

4

Myhill, J. (1962)
The converse of Moore’s Garden-of-Eden theorem.
Proc. Amer. Mat. Soc. 14, 685–686.

Title
Garden-of-Eden theorem

Canonical name
GardenofEdenTheorem

Date of creation
2013-03-22 19:22:07

Last modified on
2013-03-22 19:22:07

Owner
Ziosilvio (18733)

Last modified by
Ziosilvio (18733)

Numerical id
9

Author
Ziosilvio (18733)

Entry type
Theorem

Classification
msc 68Q80

Classification
msc 37B15
