# How Much Can Gaussian Dependence Inflate the Benjamini-Hochberg Procedure's FDR?

> AI-generated working transcription. The user-supplied PDF is authoritative. All 96 pages retain their source-page markers below. PDFKit's embedded text loses mathematical bars, square roots, integral signs and display order; **every raw PDF text block is uncertain mathematical extraction**. Key formulas in this guide and the extracted nodes were checked against the exact supplied LaTeX and selected rendered pages. The complete supplied LaTeX appears at the end, byte-for-byte inside its code block, so an uncorrected PDF text formula must never be used in preference to the LaTeX or PDF. This is an import, not an independent proof audit or researcher approval.

Lihua Lei. arXiv:2607.14812v4, revised 9 October 2026. The supplied PDF's title page displays 12 October 2026; the supplied TeX uses `\date{\today}`. These are different date fields, retained without silently reconciling them.

[Primary version record](https://arxiv.org/abs/2607.14812v4) · [local authoritative PDF](../../../research-local/raw_papers/lei2026_gaussian_bh.pdf).

## Source and reading map

The full 8,233-line source was inspected, including the lower-construction transfer arguments, both one-sided and two-sided population analyses, the full Section 4 proofs, discussion and auxiliary lemmas. All 96 PDF pages have usable embedded text. Rendered pages checked: 1, 3, 4, 5, 43, 59, 60, 66, 71, 80, 83, 87, 88, 89 and 94. The two figures on pp. 3-4 are lower-bound inflation plots on the stated grid, not simulations establishing unrestricted optimality. Figure pixels are not reproduced in the text blocks; their captions and the source figure inclusions are retained.

- Introduction, pp. 1-5: Gaussian model; both null conventions; Conjecture 1 on p. 5.
- Section 2, pp. 5-42: finite two-sided construction, population crossing transfer, proof of lower bound and asymptotics.
- Section 3, pp. 42-58: sign-reversed one-sided construction and finite transfer.
- Section 4.1, p. 59: common-factor model and conditional leave-one-out Lemma 4.1.
- Section 4.2, pp. 59-87: two-sided upper Theorem 4.2; localization, scalar crossing geometry, rank concentration and PRDN remark.
- Section 4.3, pp. 87-90: one-sided upper Theorem 4.10, Corollary 4.11 and explicit composite-null treatment.
- Discussion and disclosure, pp. 90-91; references, pp. 91-92; Appendix A, pp. 92-96.

## Verified scope correspondence

The paper's model is jointly Gaussian with unit diagonal and arbitrary positive semidefinite correlation in its unrestricted conjecture. It uses ordinary BH. The two-sided null is $\theta_i=0$, and the one-sided null is the full composite hypothesis $\theta_i\leq0$ (p. 1). Conjecture 1 proposes unrestricted leading constants $1/(2\sqrt\pi)$ and $1/\sqrt\pi$; the source's proved upper bounds cover only covariance matrices of the form $aa^{\mathsf T}+\operatorname{diag}(1-a_i^2)$, including $|a_i|=1$. No unrestricted upper bound is asserted by the extracted source nodes.

## Normalized principal formulas from the supplied TeX

Write $\phi(y)=(2\pi)^{-1/2}e^{-y^2/2}$, $\Phi$ for the standard normal CDF, and $\overline\Phi=1-\Phi$. The two-sided envelope and lower bound (equations (3)-(5), p. 5) are
$$
M(y)=\sup_{a\geq0}e^{-a^2/2}\cosh(ay),\qquad qM(y_q)=1,
$$
$$
\ell_{=}(q)=q\Phi(1)+q\int_1^{y_q}M(y)\phi(y)\,dy+\overline\Phi(y_q)=\frac{q\sqrt{\log(1/q)}}{2\sqrt\pi}+c_\ell q+o(q),\quad c_\ell=0.6492828\ldots.
$$
The one-sided bound (equations (140)-(141), pp. 42-43) is
$$
y_q^+=\sqrt{2\log(1/q)},\qquad \ell_{\leq}(q)=\frac{q\sqrt{\log(1/q)}}{\sqrt\pi}+\frac q2+\overline\Phi(y_q^+).
$$
Both are approached by finite positive definite Gaussian models. All one-sided true nulls in the lower construction happen to have mean zero; that choice does not narrow the target's true-null set.

The conditional leave-one-out lemma (Lemma 4.1, equation (190), p. 59) assumes conditional independence of all p-values given $Z$ and gives
$$
\mathbb E(\operatorname{FDP}\mid Z=z)\leq\frac qm\sum_{i\in\mathcal H_0}\sup_{0<t\leq q}\frac{F_{i,z}(t)}t,\qquad F_{i,z}(t)=\mathbb P(P_i\leq t\mid Z=z).
$$
For one-common-factor models, Theorem 4.2(b) (p. 60) states
$$
\operatorname{FDR}^{(2)}\leq q\left[1+\frac{\pi_0}{2\sqrt\pi}\sqrt{\log(1/q)}+C\pi_0\{\log(1/q)\}^{1/4}\right],
$$
where $\pi_0=m_0/m$, $m_0$ is the number of two-sided true nulls and $C$ is universal. Theorem 4.10 (p. 87), for $u_q^+=\overline\Phi^{-1}(q)$ and one-sided $\pi_0$, states
$$
\operatorname{FDR}^{(1)}\leq q\left\{2+\pi_0\left(\frac12+\frac{u_q^+}{\sqrt{2\pi}}\right)\right\},\qquad 0<q<1/2.
$$
These constants are sharp within the stated common-factor class; the unrestricted covariance conjecture is separate.

## Mathematical bottlenecks for the unrestricted conjecture

**Conditional reduction.** The pointwise BH leave-one-out identity needs no Gaussian assumption, but converting it to the conditional CDF expression requires independence of $P_i$ and its leave-one-out rejection count given the conditioning variable. In Section 4 this follows from independent residuals after conditioning on a scalar factor. A general Gaussian correlation matrix does not generally admit the same scalar diagonal-plus-rank-one representation. Conditioning on a higher-dimensional Gaussian factor can restore independence, but the scalar integrated-envelope and crossing-geometry bounds are then unproved in that setting. Merely writing a general factor representation does not extend Theorem 4.2 or 4.10.

**The two-sided factor of two.** The simple tail-ratio envelope of Theorem 4.2(a) gives a leading upper constant $1/\sqrt\pi$, twice the conjectured $1/(2\sqrt\pi)$. Part (b) obtains the half factor by retaining the BH rank weights, imposing first-crossing restrictions on the conditional mixture CDF, and proving a scalar geometric range bound. Lemma 4.5 transports affine scalar paths between positive and negative factor values and excludes simultaneous far reflected crossings. Lemma 4.6 controls small-loading components by an adjusted log-convex mixture density ratio and rapid tail growth. Lemma 4.7 integrates only the admissible crossings; Lemma 4.8 transfers observed large-rank counts to conditional means through Poisson-binomial concentration. The final proof separately controls small ranks, bad events and $|Z|>u_q$. Extending this machinery needs a replacement for the one-dimensional order and reflected-sign geometry, as well as uniform dimension-free control.

**One-sided negative means and loading signs.** Theorem 4.10 explicitly includes all $\theta_i\leq0$. Its proof (p. 88) dominates the actual conditional null CDF at a negative mean by the boundary-mean CDF, and uses that domination inside the conditional leave-one-out bound while retaining the actual leave-one-out distribution. It does not assume the full BH FDP is monotone in the null mean vector. Scalar loadings have two sign groups; each contributes at most one $q$ tail remainder, producing the $2q$ term. In a multidimensional factor model, conditioning directions vary between nulls, so the same two-group integration argument is not a ready-made uniform bound.

**Uniformity and lower-bound transfer.** The target supremum allows $N$, means, covariance and null proportion to vary with $q$, including singular covariance. Fixed-dimension expansions or a limiting population crossing without finite transfer do not settle that target. The source's lower construction takes a small design parameter after a large finite dimension, uses compact-uniform first-crossing brackets, and only then perturbs the covariance to positive definite. Its exact constants are asymptotic lower benchmarks, not finite-level rejection criteria for the conjecture.

## Citation and extraction checks

The primary arXiv record was opened successfully on 3 November 2026 and matched title, author, arXiv identifier, v4 date, subject class and the 96-page description. The one matching existing BibTeX entry `Lei2026GaussianBH` was reused and given the version-specific URL. This is a scoped primary-source check, not a whole-bibliography or retraction audit. Original-file checksums were verified before import; a remote PDF checksum comparison was not performed. Source statements remain draft; extraction accuracy and source identity do not establish proof correctness.

## Full page-marked PDF working transcription

Every following block preserves PDFKit's complete extracted page text. In particular, a plain `Φ` in a block may mean $\overline\Phi$ in the source, and missing radicals can change an asymptotic rate. Use the normalized principal formulas, exact TeX appendix or PDF for mathematics.

<!-- source-page: 1 -->

### PDF page 1

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
arXiv:2607.14812v4 [math.ST] 9 Oct 2026
How Much Can Gaussian Dependence Inflate the
Benjamini-Hochberg Procedure’s FDR?
Lihua Lei
Graduate School of Business, Stanford University
lihualei@stanford.edu
October 12, 2026
Abstract
We study the worst-case false discovery rate (FDR) of the Benjamini-Hochberg procedure for
both one- and two-sided Gaussian tests with general correlation matrices. For each setting and
given target FDR level q, we construct a family of finite Gaussian models whose FDR divided
by q diverges as q ↓0. This disproves any universal multiplicative FDR bound. Moreover,
we establish new FDR lower bounds that are independent of the number of hypotheses. For
two-sided tests, the worst-case FDR over the number of hypotheses, mean vector, and correlation
matrix is at least an explicit ℓ=(q) >q:
ℓ=(q) = q log(1/q)
+ cℓq+ o(q), cℓ = 0.6492828....
2√π
For one-sided tests, we show a lower bound ℓ≤(q) >q:
ℓ≤(q) = q log(1/q)
√π
+ q
2 + o(q).
Finally, we prove the leading constants are sharp for a class of correlation matrices for both one-
and two-sided tests.
p(x) = 2Φ(x) = 2{1−Φ(x)}.
1 Introduction
We observe a Gaussian vector T = (T1,...,TN) with mean θand covariance matrix Σ, where Σii = 1
for i= 1,...,N. We consider two testing problems. For two-sided tests, Hi : θi = 0 and
Pi = p(|Ti|), For one-sided tests, Hi : θi ≤0 and
Pi = p+(Ti), p+(x) = Φ(x) = 1−Φ(x).
Here Φ and ϕ= Φ′are the standard normal CDF and density. The normal hazard is
λ(x) = ϕ(x)
Φ(x). (1)
We use the conventions p−1(0) = p−1
+ (0) = ∞. The Benjamini-Hochberg procedure [Benjamini and
Hochberg, 1995] at level q orders the p-values as
P(1) ≤···≤P(N)
1
```

<!-- source-page: 2 -->

### PDF page 2

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
and rejects the hypotheses corresponding to
P(1),...,P(R), R= max{1 ≤k≤N : P(k) ≤qk/N},
with R= 0 if the set is empty. If V is the number of rejected true nulls, then the false discovery
proportion (FDP) and false discovery rate (FDR) are
FDP = V
R∨1, FDR = E(FDP).
A long-standing conjecture for correlated two-sided Gaussian z-tests is that BH controls the
FDR at its nominal level q, regardless of the correlation matrix [Reiner-Benaim, 2007, Benjamini,
2010, Roux, 2018, Sarkar, 2023, Sarkar and Zhang, 2025]. Benjamini [2010, p. 407] summarized the
evidence as follows:
“The modification to general dependence is often not needed: convincing simutheoret-
ical evidence indicates that the same holds for two-sided z-tests with any correlation
structure.”
Benjamini then noted that a complete theoretical proof was still missing. These works stated
or supported this conjecture. However, recently, Dobriban [2026] found a counterexample where
FDR >0.0104 when q= 0.01.
In this paper, we ask a more refined question in each testing problem: how large can the FDR
be as a function of q? For two-sided tests, we seek a lower bound ℓ=(q) such that
sup
N∈N, θ∈RN
, Σ∈SN
+
Σii=1, 1≤i≤N
FDRθ,Σ(BHq) ≥ℓ=(q). (2)
Here SN
+ denotes the cone of N ×N symmetric positive semidefinite matrices. A relaxed folklore
conjecture is that the worst-case FDR in (2) is bounded above by Cq for some universal constant
C >0. However, Theorem 2.1 and Proposition 2.2 together show that the worst-case FDR is at
least a quantity satisfying, as q↓0,
ℓ=(q) = q log(1/q)
2√π
+ cℓq+ o(q), cℓ = 0.6492828....
In particular, the ratio of the supremum in (2) to q diverges as q↓0.
Moreover, we derive an exact formula for ℓ=(q). We prove that ℓ=(q) >q for every q∈(0,1).
Instead of seeking a counterexample for a given nominal level q, Theorem 2.1 and Proposition 2.3
together disprove the conjecture that BH controls the FDR for correlated two-sided Gaussian tests.
Figure 1 illustrates the resulting two-sided FDR inflation.
2
```

<!-- source-page: 3 -->

### PDF page 3

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
= (q) q
0.10
0.08
0.06
0.04
0.02
0.00
1.8
1.6
= (q)/q
1.4
1.2
1.0
0.0 0.2 0.4 0.6 0.8 1.0
q
0.0 0.2 0.4 0.6 0.8 1.0
q
Figure 1: Numerical evaluation of ℓ=(q)−q and ℓ=(q)/q over the grid q= 0.005k, k= 1,...,199.
q 0.01 0.05 0.10 0.20
ℓ=(q)−q 0.0036 0.0129 0.0209 0.0314
ℓ=(q)/q 1.3553 1.2571 1.2094 1.1570
Table 1: The absolute inflation ℓ=(q)−q and relative inflation ℓ=(q)/q at commonly used nominal
levels.
For one-sided Gaussian tests, the classical negatively correlated examples of Hochberg and Rom
[1995] and Samuel-Cahn [1996] show that the Simes inequality, and hence BH under the global
null, can be anticonservative. Chi et al. [2025] prove useful upper bounds under several notions of
negative dependence, but the adversarial construction used in their sharpness comparison, due to Su
[2018], is not jointly Gaussian. Our one-sided construction instead retains positively correlated nulls
and reverses the loading of the non-nulls. Theorem 3.1 and Proposition 3.3 give, for every q∈(0,1),
ℓ≤(q) = q log(1/q)
√π
+ q
2 + Φ 2 log(1/q) >q,
and Proposition 3.2 gives
ℓ≤(q) = q log(1/q)
+ q
√π
2 + o(q).
This is a larger leading constant than in the two-sided construction and again implies that the
worst-case FDR ratio diverges. Figure 2 illustrates the resulting one-sided FDR inflation.
3
```

<!-- source-page: 4 -->

### PDF page 4

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
(q) q
0.10
0.08
0.06
0.04
0.02
0.00
1.8
1.6
(q)/q
1.4
1.2
1.0
0.0 0.2 0.4 0.6 0.8 1.0
q
0.0 0.2 0.4 0.6 0.8 1.0
q
Figure 2: Numerical evaluation of ℓ≤(q)−q and ℓ≤(q)/q over the grid q= 0.005k, k= 1,...,199.
Table 2: The absolute inflation ℓ≤(q)−q and relative inflation ℓ≤(q)/q at commonly used nominal
levels.
q 0.01 0.05 0.10 0.20
ℓ≤(q)−q 0.00831 0.03101 0.05155 0.07955
ℓ≤(q)/q 1.8311 1.6203 1.5155 1.3977
The dependence structures differ sharply between the two constructions. Every covariance in the
two-sided construction is positive, but the map Ti →2Φ(|Ti|) is not monotone and need not make
the full vector of two-sided p-values satisfy positive regression dependence on a subset (PRDS) with
respect to the true nulls. For one-sided Gaussian p-values, by contrast, nonnegative correlations
between every true null and every other hypotheses imply that p-values are PRDS and hence FDR
control [Benjamini and Yekutieli, 2001]. Negative dependence among the test statistics is therefore
essential for the one-sided lower bound. In particular, our example has positive correlations between
null pairs and negative correlations between a pair of null and non-null. Thus, the full vector of
one-sided p-values in our construction is not PRDS; Section 3 verifies this directly.
The lower-bound rate q log(1/q) should be compared with the FDR-linking theorem of Su [2018].
Positive regression dependence within nulls (PRDN) relaxes PRDS by imposing the relevant positive
dependence assumption only on the null p-values. Under PRDN, the FDR-linking argument gives an
O(qlog(1/q)) bound. Section 4 proves sharper Gaussian bounds. For two-sided one-common-factor
models,
sup
m∈N, θ∈Rm
FDRθ,a(BHq) = 1
,
2√π
+ o(1) q log(1/q),
a∈[−1,1]m
so the lower construction attains the sharp leading constant in this class. This bound improves on
the general PRDN linking rate. Moreover, as explained in Remark 4.9, the two-sided null p-values in
this class satisfy the PRDN property by the absolute-value Gaussian multivariate total positivity of
order two (MTP2) criterion of Karlin and Rinott [1981]. For one-sided one-common-factor models,
4
```

<!-- source-page: 5 -->

### PDF page 5

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
Theorem 4.10 and Corollary 4.11 give
sup
m∈N, θ∈Rm
FDRθ,a(BHq) = 1
,
√π
a∈[−1,1]m
+ o(1) q log(1/q).
This matches the leading constant in ℓ≤(q). Both bounds are uniform over the number of hypotheses,
means, and scalar loadings.
We conclude the section with a new conjecture that neither the author nor GPT 5.6 Sol was
able to disprove after significant efforts.
Conjecture 1. The unrestricted Gaussian worst-case FDR satisfies
sup
N∈N, θ∈RN
, Σ∈SN
+
Σii=1, 1≤i≤N
FDRθ,Σ(BHq)
lim
q↓0
=

1
q log(1/q)
, for two-sided tests,
2√π
1
√π
, for one-sided tests.
2 Lower bound for two-sided tests
2.1 Main result
M(y) = sup
e−a2/2 cosh(ay). (3)
a≥0
Appendix A identifies the likelihood-ratio envelope: M = 1 on [0,1], and M is continuous, strictly
increasing, and unbounded on (1,∞). Hence there is a unique yq >1 such that
qM(yq) = 1. (4)
Set
ℓ=(q) = qΦ(1) + q
yq
M(y)ϕ(y) dy+ Φ(yq). (5)
1
The next theorem shows that the lower bound can be approached arbitrarily closely by finite-
dimensional Gaussian models with positive definite correlation matrices.
Theorem 2.1. For T∼N(θ,Σ), let FDRθ,Σ(BHq) denote the FDR of BHq applied to the two-sided
p-values p(|T1|),...,p(|TN|). For every q ∈(0,1) and δ > 0, there are N ∈N, θ ∈RN, and a
positive definite correlation matrix Σ such that
FDRθ,Σ(BHq) >ℓ=(q)−δ. (6)
Consequently,
sup
N∈N, θ∈RN
,
Σ≻0, diag(Σ)=1N
The next proposition gives the small-q expansion of the lower bound.
Proposition 2.2. As q↓0,
FDRθ,Σ(BHq) ≥ℓ=(q). (7)
where
cℓ = Φ(1)−
2√2π
= 0.6492828....
ℓ=(q) = q log(1/q)
2√π
1
+ cℓq+ o(q),
+
∞
1
M(y)ϕ(y)−
1
2√2π
5
dy
```

<!-- source-page: 6 -->

### PDF page 6

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
Proposition 2.3 further shows that ℓ=(q) >q for every q∈(0,1). Together with Theorem 2.1,
this implies that BH fails to control the FDR at every nontrivial nominal level in the correlated
two-sided Gaussian setting.
Proposition 2.3. For every q∈(0,1),
ℓ=(q) >q.
Figure 1 in the Introduction displays the numerical behavior of the two-sided lower bound.
Table 1 gives the absolute inflation ℓ=(q)−q and relative inflation ℓ=(q)/q for commonly used
nominal levels.
2.2 Roadmap
Fix q ∈(0,1) and a design law νq. Let ΩN = ((Θ1,B1),...,(ΘN,BN)), where the pairs are i.i.d.
i.i.d.
draws from νq, independently of Z,ε1,...,εN
∼N(0,1), and set
Ti = Θi + BiZ+ 1−B2
i εi, i= 1,...,N.
Conditional on a realization of ΩN, this is a finite deterministic Gaussian design. Since BH is
a step-up procedure, its rejection set is {i : |Ti|≥CN}. We will show in Subsection 2.4 that,
conditional on Z= z, CN →C(z) and FDP →D(z), where convergence is defined in an appropriate
sense. Consequently,
EΩN[FDRΩN(BHq)] = EΩN,Z,ε[FDP] −→E[D(Z)].
Thus, for any δ >0 and all sufficiently large N, at least one deterministic realization ωN of ΩN
satisfies
FDRωN(BHq) ≥E[D(Z)]−δ.
We next construct a family of laws νq,r. Write Dr for the conditional FDP limit associated with
νq,r. For every z /∈{−1,−yq}, we prove that Dr(z) →D∗(z) as r↓0, where
D∗(z) =

q, z≥−1,
qM(−z),−yq <z<−1,
1, z≤−yq.
Because 0 ≤Dr,D∗≤1, dominated convergence then gives
E[Dr(Z)] −→E[D∗(Z)] = ℓ=(q).
Then we can prove the lower bound (7) in Theorem 2.1 by taking N to approach infinity first and
r to approach zero. To convert the supremum to a bound in (6), we just need to The argument
therefore takes the iterated limit limr↓0 limN→∞: first N →∞for each fixed r, and then r↓0. To
obtain a single finite example, we choose r sufficiently small and then N sufficiently large. A small
independent Gaussian perturbation finally makes its covariance matrix positive definite.
6
```

<!-- source-page: 7 -->

### PDF page 7

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
2.3 Population quantities
Put uq = p−1(q). Let νq be a probability measure on R ×[−1,1]. Write
π0 = νq({0}×[−1,1]), (8)
and assume π0 >0.
For (θ,b) ∈R ×[−1,1], z∈R, and s∈(0,1], let us = p−1(s) and define
Fθ,b,z(s) = P{p(|Ti|) ≤s|Θi = θ, Bi = b, Z= z}.
If |b|<1, then
Fθ,b,z(s) = Φ us−θ−bz
√1−b2 + Φ us + θ+ bz
√1−b2. (9)
If |b|= 1, then
Fθ,b,z(s) = 1{p(|θ+ bz|) ≤s}. (10)
Set Fθ,b,z(0) = 0.
Conditional on Z= z, the CDFs of the mixture p-value and the null p-value are
Rz(s) = Fθ,b,z(s) νq( dθ, db), (11)
R0,z(s) = 1
π0 {0}×[−1,1]
F0,b,z(s) νq( dθ, db). (12)
For c≥uq, define the normalized quantities
¯
Rz(c) = qRz{p(c)}
p(c), (13)
¯
R0,z(c) = qπ0R0,z{p(c)}
p(c). (14)
Then the limiting cutoff can be written as
C(z) = inf{c≥uq :
¯
Rz(c) ≥1}. (15)
Here and below, inf ∅= ∞. The limiting conditional FDP is defined by
D(z) =
¯
R0,z{C(z)}, C(z) <∞,
0, C(z) = ∞.
(16)
We call a finite cutoff a regular first crossing when it satisfies the following requirements.
Definition 2.4. A finite cutoff C(z) >uq is regular if
sup
uq≤c≤C(z)−ρ
sup
C(z)<c<C(z)+ρ
¯
Rz(c) <1 for every 0 <ρ<C(z)−uq, (17)
¯
Rz(c) >1 for every ρ>0, (18)
and c→¯
R0,z(c) is continuous at C(z).
The following proposition reduces regularity to a local monotonicity check.
7
```

<!-- source-page: 8 -->

### PDF page 8

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
Proposition 2.5. Let C(z) >uq be finite. Suppose there exist uq <a<C(z) <b such that the
map c→¯
Rz(c) is differentiable on (a,b) and satisfies
¯
R′
z(c) >0, a<c<b. (19)
Suppose also that c→¯
R0,z(c) is continuous at C(z). Then C(z) is regular.
Proof. The map c →Rz{p(c)}is a survival function and hence is upper semicontinuous. Since
p is positive and continuous, c→¯
Rz(c) is also upper semicontinuous. By the definition of C(z),
¯
Rz(c) <1 for every c<C(z). Therefore, for every 0 <ρ<C(z)−uq, upper semicontinuity and
compactness give
¯
sup
Rz(c) <1,
uq≤c≤C(z)−ρ
which proves (17).
By the definition of C(z), there is a sequence cn ≥C(z) decreasing to C(z) such that¯
Rz(cn) ≥1.
Continuity on (a,b) gives¯
Rz{C(z)}≥1. On the other hand, for any sequence dn <C(z) increasing
to C(z), the first-crossing definition gives¯
Rz(dn) < 1, so continuity gives¯
Rz{C(z)}≤1. Hence
¯
Rz{C(z)}= 1. The mean value theorem and (19) imply strict monotonicity on (a,b), which yields
¯
Rz(c) >1 for C(z) <c<b.
This gives (18). Continuity of the null contribution at C(z) completes Definition 2.4.
2.4 Limiting cutoff and FDR
Let
ΩN = ((Θ1,B1),...,(ΘN,BN)), (Θi,Bi)i.i.d.
∼νq. (20)
Since the distribution of (T1,...,TN) is fully determined by ΩN, we write FDRθ,Σ(BHq) as
FDRΩN(BHq).
Define Pi = p(|Ti|).
RN(s) = 1
N
N
i=1
1{Pi ≤s}, (21)
R0,N(s) = 1
N
N
1{Θi = 0, Pi ≤s}. i=1
The following lemma gives a uniform conditional empirical-CDF bound. For a function f on
[0,1], write ∥f∥∞,[0,1] = sup0≤s≤1 |f(s)|.
Lemma 2.6. For every z∈R and t>0,
P max ∥RN−Rz∥∞,[0,1],∥R0,N−π0R0,z∥∞,[0,1] >t Z= z ≤4e−2Nt2
. (23)
Proof. Conditional on Z= z, the Pi are i.i.d. with CDF Rz. Also define
Wi = Pi1{Θi = 0}+ 21{Θi ̸= 0}.
(22)
For 0 ≤s≤1,
1{Wi ≤s}= 1{Θi = 0, Pi ≤s}, P(Wi ≤s|Z= z) = π0R0,z(s).
Apply the Dvoretzky-Kiefer-Wolfowitz inequality twice and take a union bound.
8
```

<!-- source-page: 9 -->

### PDF page 9

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
The next lemma gives an exact characterization of the BH cutoff and FDP through the empirical
CDFs.
Lemma 2.7. Let RN be the number of BH rejections and put
qRN
τN =
. (24)
. (25)
N
If RN ≥1, then
RN(τN) = RN
N , FDP = qR0,N(τN)
τN
With CN = p−1(τN),
CN = inf c≥uq :
qRN{p(c)}
p(c) ≥1. (26)
Then the BH rejection set is {i: |Ti|≥CN}. If RN = 0, the set in (26) is empty and CN = ∞.
Proof. Let P(1) ≤···≤P(N). If more than RN values were at most qRN/N, then
P(RN+1) ≤qRN/N <q(RN + 1)/N,
contradicting the maximality of RN. Hence NRN(τN) = RN, and (25) follows. Since pis decreasing,
the BH step-up definition is equivalent to (26).
The next theorem establishes the limiting cutoff conditional on the common factor Z.
Theorem 2.8. Assume that C(z) is regular for almost every z. Then, for every z at which C(z) is
regular, conditional on Z= z,
CN −→C(z), FDP −→D(z) =
¯
R0,z{C(z)}=
qπ0R0,z[p{C(z)}]
p{C(z)} (27)
in probability. Consequently,
lim
N→∞
EΩN FDRΩN(BHq) = E[D(Z)], (28)
where
FDRΩN(BHq) = EZ,ε[FDP |ΩN]. (29)
¯
Proof. Fix a regular z and ρ,τ > 0. Since D(z) =
R0,z{C(z)}and c →¯
R0,z(c) is continuous at
C(z), choose
0 <ρ(z) <min{ρ,C(z)−uq}
so that
sup
C(z)−ρ(z)≤c≤C(z)+ρ(z)
Set A(z) = C(z)−ρ(z). Equation (17) gives supuq≤c≤A(z)
B(z) ∈(C(z),C(z) + ρ(z)) with¯
Rz{B(z)}>1. Set
|¯
R0,z(c)−D(z)|≤τ. (30)
¯
Rz(c) <1, and (18) permits a choice of
γ(z) = 1
2
min 1− sup
uq≤c≤A(z)
¯
Rz(c),
¯
Rz{B(z)}−1 >0.
9
```

<!-- source-page: 10 -->

### PDF page 10

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
Put
By the empirical curve we mean
EN(z) = max ∥RN−Rz∥∞,[0,1],∥R0,N−π0R0,z∥∞,[0,1].
Lemma 2.6 gives EN(z) →0 in probability conditional on Z= z. For every uq ≤c≤B(z),
qRN{p(c)}
¯
p(c)−
Rz(c) ≤ qEN(z)
p{B(z)},
qR0,N{p(c)}
¯
p(c)−
R0,z(c) ≤ qEN(z)
p{B(z)}.
(31)
c−→qRN{p(c)}
p(c).
On the event qEN(z)/p{B(z)}<γ(z), the definition of γ(z) and (31) give
qRN{p(c)}
sup
uq≤c≤A(z)
p(c) ≤ sup
uq≤c≤A(z)
¯
Rz(c) + qEN(z)
p{B(z)}
<1−2γ(z) + γ(z) <1,
whereas
qRN{p(B(z))}
p(B(z)) ≥¯
Rz{B(z)}− qEN(z)
p{B(z)}>1 + 2γ(z)−γ(z) >1.
Lemma 2.7 and (30) therefore give
A(z) <CN ≤B(z), |FDP−D(z)|≤τ + qEN(z)
p{B(z)}.
Because ρ,τ >0 were arbitrary, this proves (27) at every regular z.
For completeness, the quantities in the expectation can be taken to be measurable without
making a measurable selection of B(z). The maps (z,c) →¯
Rz(c) and (z,c) →¯
R0,z(c) are jointly
Borel measurable, and the first is left-continuous in c. Define
C◦(z) = inf{c∈Q : c≥uq,
¯
Rz(c) >1}.
At every regular z, left continuity and (18) imply C◦(z) = C(z). Thus C has a measurable version.
Moreover, for c < C(z),¯
R0,z(c) ≤¯
Rz(c) < 1; continuity of the null contribution at the crossing
gives 0 ≤D(z) ≤1. Hence
D◦(z) = min 1,
¯
R0,z{C◦(z)}, C◦(z) <∞,
0, C◦(z) = ∞,
is a measurable [0,1]-valued version of D(z) at almost every z. Use these versions below. Conditional
convergence in probability, together with boundedness, now yields
E |FDP−D(z)||Z= z −→0 for almost every z.
Dominated convergence and the tower property give
EΩN,Z,ε |FDP−D(Z)| −→0,
and a second application of the tower property yields (28).
10
```

<!-- source-page: 11 -->

### PDF page 11

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
Lastly, we show that Σ can be made positive definite by an independent Gaussian perturbation.
For a fixed realization ω= ((θi,bi))N
i=1, let ξ∼N(0,IN) be independent and define
T(η)
i = θi + 1−η2 biZ+ 1−b2
i εi + ηξi, 0 <η<1. (32)
Then
Σω,η = (1−η2) bb⊤+ diag(1−b2
1,...,1−b2
N) + η2IN. (33)
The following lemma shows that the perturbation makes the correlation matrix positive definite
while preserving the FDR in the limit.
Lemma 2.9. For every fixed ω,
diag(Σω,η) = 1N, Σω,η ⪰η2IN, (34)
and
FDR(η)
ω (BHq) −→FDRω(BHq) (η↓0). (35)
Proof. Equation (34) is immediate from (33). Under the coupling (32), T(η) →T almost surely.
Define P(η)
i = p(|T(η)
i |). Then P(η)
i →Pi = p(|Ti|) almost surely. Each Pi has a continuous marginal
law, so
P Pi ∈ qk
N
: 1 ≤k≤N for some i = 0.
Outside of this event, P(η)
i ≤qk/N if and only if Pi ≤qk/N for when η is sufficiently small. Hence
the BH rejection set remains constant for sufficiently small η. Bounded convergence proves (35).
2.5 Construction of νq,r
We construct a family of laws νq,r indexed by r↓0. For a,y≥0, put
La(y) = e−a2/2 cosh(ay).
For y>1, let
a(y) = arg max
α≥0
Lα(y), y(α) = a−1(α), α>0.
Set
aq = a(yq). (36)
Appendix A establishes the properties of these functions that we use below.
The quantities br,τr,µr,π0,r, and cr are defined below. The law νq,r has the three components
displayed in Table 3.
Table 3: Two-sided population construction defining νq,r.
Type Mass Θ B
Nulls π0,r 0 r
Primary non-nulls r cr + y(br) 1
Secondary non-nulls τrµr( da) a/r+ y(a) 1, a∈[br,aq]
11
```

<!-- source-page: 12 -->

### PDF page 12

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
Equivalently, for every bounded measurable f : R ×[−1,1] →R,
f dνq,r = π0,rf(0,r) + rf(cr + y(br),1) + τr
aq
br
f a
r
+ y(a),1 µr( da). (37)
Definition of secondary non-nulls. For small r, set
br = rp−1(r2).
For the remaining definitions, take r small enough that 0 <br <aq. For a∈[br,aq], define
Wr(a) = 1−qM{y(a)}p(a/r)
. (38)
q
By Lemma A.1 and (292), the factor 1−qM{y(a)}is nonnegative and decreasing on [br,aq]; the
factor p(a/r) is decreasing in a. Hence Wr is continuous and decreasing, with Wr(aq) = 0. Set
τr := Wr(br) = 1−qM{y(br)}r2
= O(r2). (39)
q
We therefore call this the secondary non-null block; its total mass is O(r2) = o(r). Let µr be the
probability measure on [br,aq] determined by
µr([a,aq]) = Wr(a)
τr
In particular, µr([br,aq]) = Wr(br)/τr = 1.
Definition of nulls. Put
, br ≤a≤aq. (40)
π0,r = 1−r−τr.
Since π0,r + r+ τr = 1, the masses in (37) define a probability measure.
Definition of primary non-nulls. For all sufficiently small r, π0,r >0. Define cr by
p(cr) = q(r+ τr)
1−qπ0,r
. (41)
The numerator is positive. Since τr = O(r2) and π0,r = 1−r−τr,
1−qπ0,r = 1−q+ qr+ qτr −→1−q>0, q(r+ τr) −→0.
Thus the right side of (41) is positive and smaller than one for small r, so cr is well-defined.
2.6 Population FDR analysis under νq,r
2.6.1 Preliminaries
Apply Subsection 2.3 with νq = νq,r. Denote the resulting quantities by
Rr,z, R0,r,z,
¯
Rr,z,
¯
R0,r,z, Cr(z).
For c≥uq,
¯
Rr,z(c) =
¯
R0,r,z(c) +
¯
R1,r,z(c) +
¯
R2,r,z(c), (42)
12
```

<!-- source-page: 13 -->

### PDF page 13

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
where
¯
R0,r,z{p(c)}
R0,r,z(c) = qπ0,r
p(c), (43)
¯
R1,r,z(c) = qr
p(c)1{|cr + y(br) + z|≥c},
¯
R2,r,z(c) = qτr
p(c)
aq
br
1
a
+ y(a) + z ≥c µr( da).
For a measurable definition at every z, put
C◦
r(z) = inf{c∈Q : c≥uq,
¯
Rr,z(c) >1}
r
and define
Dr(z) = min 1,
¯
R0,r,z{C◦
r(z)}, C◦
r(z) <∞,
0, C◦
r(z) = ∞.
The joint Borel measurability of (z,c) →¯
Rr,z(c) and (z,c) →¯
R0,r,z(c) makes both C◦
r and Dr Borel
measurable. At every regular crossing, the rational-cutoff argument in the proof of Theorem 2.8
gives C◦
r(z) = Cr(z), and¯
R0,r,z{Cr(z)}≤1. Hence
¯
Dr(z) =
R0,r,z{Cr(z)}. (44)
Moreover, 0 ≤Dr(z) ≤1 for every z.
We next state two asymptotic lemmas that will be applied in the following analysis. The first
gives the order of br and cr as r↓0.
Lemma 2.10. As r↓0,
br
br ↓0,
= p−1(r2) →∞, p(br/r) = r2, y(br) ↓1. (45)
r
Moreover,
p(cr)∼
qr
1−q
, cr →∞, rcr →0,
br
r−cr →∞. (46)
Proof. The identity p(br/r) = r2 follows directly from br = rp−1(r2). Applying (301) in Lemma A.2
gives
br
r
= p−1(r2)∼ 4 log(1/r) →∞, br ∼2r log(1/r) →0.
The last limit in (45) follows from Lemma A.1: a(y) is continuous and strictly increasing from
(1,∞) onto (0,∞), with limy↓1 a(y) = 0. Since y(·) is its inverse and br ↓0, we have y(br) ↓1.
By (41) and (39),
p(cr) = q(r+ τr)
qr
∼
1−qπ0,r
1−q
For every fixed δ∈(0,q/(1−q)), for all sufficiently small r,
q
1−q
−δ r≤p(cr) ≤ q
1−q
.
Since p−1 is decreasing,
+ δ r.
p−1 q
1−q
+ δ r ≤cr ≤p−1 q
1−q
13
−δ r .
```

<!-- source-page: 14 -->

### PDF page 14

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
Equation (301) in Lemma A.2, applied to the two fixed positive constants, shows that both endpoints
are asymptotic to 2 log(1/r). Hence
cr ∼ 2 log(1/r).
br
= p−1(r2)∼ 4 log(1/r)
Hence cr →∞and rcr →0. Combining this with
r
gives
br
r−cr ∼ 2−√2 log(1/r) −→∞.
The next lemma gives a uniform approximation to the normalized conditional FDP contribution
rz
from nulls.
Lemma 2.11. For every A>0 and T ≥0, as r↓0,
sup
|z|≤T
0≤c≤A/r
sup
R0,r,z{p(c)}
p(c)−Lrc(|z|) −→0. (47)
Proof. For 0 <r<1, the null pair (Θ,B) = (0,r) gives
R0,r,z{p(c)}= P{|rz+ 1−r2 ε|≥c}.
Write
x±=
c∓rz
√1−r2.
Then
R0,r,z{p(c)}= Φ(x+) + Φ(x−).
Fix C >0. Uniformly for |z|≤T and C ≤c≤A/r,
x±−c= c
=
1
√1−r2−1 ∓
√1−r2
cr2
√1−r2{1 + √1−r2}∓
rz
√1−r2.
Therefore,
|x±−c|≤ Ar
Tr
√1−r2{1 + √1−r2}+
= OA,T(r).
√1−r2
Consequently, for all sufficiently small r, the shifts x±−c are uniformly bounded and x±≥C/2.
The uniform expansion (300) in Lemma A.2 therefore gives remainders ρr,C,±(c,z) such that
−
Φ(x±)
Φ(c)
x2
±−c2
2
=
c
x±
=−
exp−
x2
±−c2
2 {1 + ρr,C,±(c,z)},
(rc)2
±rcz+ OA,T(r2).
2
(48)
14
```

<!-- source-page: 15 -->

### PDF page 15

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
and
lim
C→∞
lim sup
r↓0
sup
sup
max
± |ρr,C,±(c,z)|= 0. (49)
|z|≤T
C≤c≤A/r
For each fixed C >0, c/x±→1 uniformly for |z|≤T and C ≤c≤A/r as r↓0. To identify the
leading term, put t= rc, so that 0 ≤t≤A. Then
1
2 exp−
t2
2 + tz + exp−
t2
2−tz= e−t2/2 cosh(tz) = Lt(|z|).
Because t and z range over compact sets, these exponential factors are uniformly bounded. Thus,
after summing the two tails in (48) and using p(c) = 2Φ(c), the errors from c/x±−1 and from the
OA,T(r2) term vanish uniformly for each fixed C. Consequently, there is a constant KA,T < ∞,
independent of C, such that, for
η(C) = lim sup
r↓0
sup
|z|≤T
C≤c≤A/r
sup
R0,r,z{p(c)}
p(c)−Lrc(|z|),
we have
η(C) ≤KA,T lim sup
sup
sup
max
± |ρr,C,±(c,z)|.
r↓0
|z|≤T
C≤c≤A/r
The right side tends to zero as C →∞by (49). Hence η(C) →0.
It remains to control 0 ≤c≤C. On this range, p(c) ≥p(C) >0. Also, uniformly over 0 ≤c≤C
and |z|≤T,
R0,r,z{p(c)}= Φ c−rz
√1−r2 + Φ c+ rz
√1−r2
= p(c) + OC,T(r),
because the two arguments differ from c by OC,T(r) and Φ has bounded derivative. Hence
sup
|z|≤T
0≤c≤C
R0,r,z{p(c)}
sup
p(c)−1 −→0.
Moreover, Lrc(|z|) = e−(rc)2/2 cosh(rc|z|) →1 uniformly for |z|≤T and 0 ≤c≤C. Thus
R0,r,z{p(c)}
lim sup
r↓0
Letting C →∞proves the claim.
sup
|z|≤T
0≤c≤A/r
sup
p(c)−Lrc(|z|) ≤η(C).
The following lemma provides a generic criterion for deriving the limit of Cr(z).
Lemma 2.12. Let K be compact. For z ∈K, let mr(z) >uq and wr(z) >0. Suppose that, for
every fixed H >0,
inf
z∈K{mr(z)−Hwr(z)}>uq (50)
for all sufficiently small r, and
sup
z∈K
sup
|h|≤H
¯
Rr,z{mr(z) + wr(z)h}−d(z) −{1−d(z)}eξ(z)h −→0, (51)
where d: K →[0,1) and ξ: K →(0,∞) are continuous. Suppose also that, for every h0 >0,
¯
lim sup
r↓0
sup
z∈K
sup
uq≤c≤mr(z)−wr(z)h0
Rr,z(c) <1. (52)
Then
z∈K
sup
Cr(z)−mr(z)
wr(z) −→0. (53)
15
```

<!-- source-page: 16 -->

### PDF page 16

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
Proof. Fix h0 >0. Compactness gives
inf
z∈K{1−d(z)}{eξ(z)h0
−1}>0.
Hence (51) gives¯
Rr,z{mr(z) + wr(z)h0}>1 uniformly on K, while (52) excludes a crossing at or
before mr(z)−wr(z)h0. Thus
mr(z)−wr(z)h0 <Cr(z) ≤mr(z) + wr(z)h0
uniformly on K. Letting h0 ↓0 proves (53).
The next lemma gives regularity and the limiting null contribution once the localized cutoff has
been identified.
Lemma 2.13. Under the assumptions and notation of Lemma 2.12, assume in addition that, for
every fixed H >0,
sup
z∈K
sup
|h|≤H
¯
R0,r,z{mr(z) + wr(z)h}−d(z) −→0. (54)
If, for some H∗>0 and all sufficiently small r, the map
h−→¯
Rr,z{mr(z) + wr(z)h}
is differentiable with positive derivative on (−H∗,H∗), and the map h→¯
R0,r,z{mr(z) + wr(z)h}is
continuous there for every z∈K, then Cr(z) is regular and
sup
z∈K
|Dr(z)−d(z)|−→0. (55)
Proof. For all sufficiently small r, (53) gives
mr(z)−wr(z)H∗<Cr(z) <mr(z) + wr(z)H∗.
With c= mr(z) + wr(z)h, the chain rule gives
d
¯
¯
Rr,z{mr(z) + wr(z)h}= wr(z)
R′
dh
r,z(c).
Since wr(z) >0,
0 <
d
¯
¯
Rr,z{mr(z) + wr(z)h}= wr(z)
R′
dh
r,z(c) =⇒¯
R′
r,z(c) >0.
Thus
¯
R′
r,z(c) >0, mr(z)−wr(z)H∗<c<mr(z) + wr(z)H∗. (56)
Equations (53) and (50), together with (56), verify the hypotheses of Proposition 2.5, which gives
regularity. Finally, put
hr(z) = Cr(z)−mr(z)
wr(z).
Equation (53) gives hr(z) →0 uniformly. By (44),
Dr(z) =
¯
R0,r,z{Cr(z)}=
¯
R0,r,z{mr(z) + wr(z)hr(z)}.
Evaluating (54) at h= hr(z) therefore proves (55).
16
```

<!-- source-page: 17 -->

### PDF page 17

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
The next lemma derives the derivatives of the null and secondary non-null contributions.
Lemma 2.14. For c>0, put
c∓rz
√1−r2 , Q±(c,z) = Φ(x±)
Φ(c).
x±=
The null contribution¯
R0,r,z(c) satisfies
¯
R′
0,r,z(c) = qπ0,r
2
σ∈{−,+}
d
¯
log
R0,r,z(c) = λ(c)−
Qσ(c,z) λ(c)−
λ(xσ)
√1−r2 , (57)
Q+(c,z)λ(x+) + Q−(c,z)λ(x−)
√1−r2{Q+(c,z) + Q−(c,z)}. (58)
dc
Define
gr(a) = a+ ry(a). (59)
For 0 <a<aq,
′
g
r(a) = 1 + ry
′(a) >1,
so gr is strictly increasing on [br,aq]. Finally, fix y>1 and c>0, and suppose that
gr(br) >r(y−c). (60)
If
gr(br) <r(c+ y) <gr(aq),
let βr,y(c) ∈(br,aq) be the unique solution of
gr{βr,y(c)}= r(c+ y). (61)
Conditional on Z=−y, a secondary non-null indexed by a∈[br,aq] is then rejected at cutoff c if
and only if
a∈[βr,y(c),aq]. (62)
Whenever 1−qM{y(βr,y(c))}>0, the secondary non-null contribution¯
R2,r,−y(c) satisfies
∂βr,y(c)
∂c=
r
1 + ry′{βr,y(c)}, (63)
¯
qM′{y(βr,y(c))}y′{βr,y(c)}
log
R2,r,−y(c) =−
1−qM{y(βr,y(c))}
r
1 + ry′{βr,y(c)}
λ{βr,y(c)/r}
−
1 + ry′{βr,y(c)}+ λ(c), (64)
¯
R′
2,r,−y(c) =
¯
R2,r,−y(c) d
¯
log
R2,r,−y(c). (65)
dc
If r(c+ y) ≤gr(br), the secondary non-null block is fully rejected. Under the strict inequality
r(c+ y) <gr(br),
d
dc
¯
R2,r,−y(c) = qτr
p(c),
qτrp′(c)
¯
R′
2,r,−y(c) =−
17
¯
= λ(c)
R2,r,−y(c).
p(c)2
```

<!-- source-page: 18 -->

### PDF page 18

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
If r(c+y) ≥gr(aq), the secondary non-null contribution vanishes: at equality the rejected set is {aq},
which has µr-measure zero by (40) and Wr(aq) = 0. Under the strict inequality r(c+ y) >gr(aq),
¯
R2,r,−y(c) =
¯
R′
2,r,−y(c) = 0.
As r(c+ y) ↓gr(br), βr,y(c) ↓br; as r(c+ y) ↑gr(aq), βr,y(c) ↑aq. Since Wr is continuous,
Wr(br) = τr, and Wr(aq) = 0, the interior expression
¯
R2,r,−y(c) = qWr{βr,y(c)}
p(c)
matches the endpoint values. Thus the contribution is continuous at both equalities. Its one-sided
derivatives need not agree there, so a two-sided derivative is not asserted.
Proof. Since
dx±
1
=
dc
√1−r2 ,
we have
d
dc
log Q±(c,z) =−
Multiplying by Q±(c,z) and summing gives
¯
R′
0,r,z(c) = qπ0,r
2 {Q′
+(c,z) + Q′
−(c,z)}
qπ0,r
=
2
Qσ(c,z) λ(c)−
σ∈{−,+}
d
dtlog Φ(t) =−λ(t),
λ(x±)
√1−r2 + λ(c).
λ(xσ)
√1−r2 ,
which is (57), and
¯
R′
0,r,z(c)
Q′
+(c,z) + Q′
−(c,z)
¯
R0,r,z(c)
=
Q+(c,z) + Q−(c,z)
Q+(c,z)λ(x+) + Q−(c,z)λ(x−)
= λ(c)−
√1−r2{Q+(c,z) + Q−(c,z)},
which is (58).
For a secondary non-null indexed by a, conditional on Z=−y,
T(a) = a
r
+ y(a)−y, r{T(a) + y}= gr(a).
By (59) and the positivity of y′in Lemma A.1, g′
r(a) = 1 + ry′(a) >1, proving the asserted strict
monotonicity. Equation (60) gives
gr(a) ≥gr(br) >r(y−c) =⇒ T(a) >−c,
so rejection can occur only through T(a) ≥c. In the interior case, (61) and strict monotonicity give
T(a) ≥c ⇐⇒ gr(a) ≥r(c+ y) ⇐⇒ a≥βr,y(c).
18
```

<!-- source-page: 19 -->

### PDF page 19

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
This proves (62). Thus
¯
R2,r,−y(c) = qτr
p(c)µr [βr,y(c),aq]
qWr{βr,y(c)}
=
p(c)
= 1−qM{y(βr,y(c))}p{βr,y(c)/r}
p(c),
by (40) and (38).
Differentiating the threshold equation yields
1 + ry
′{βr,y(c)}∂βr,y(c)
∂c= r,
which proves (63). Since p′(t)/p(t) =−λ(t),
d
¯
qM′{y(βr,y(c))}y′{βr,y(c)}
log
R2,r,−y(c) =−
1−qM{y(βr,y(c))}
−λ{βr,y(c)/r}1
∂βr,y(c)
r
∂c + λ(c).
∂βr,y(c)
dc
∂c
Substitution of (63) gives (64), and
¯
R′
2,r,−y(c) =
¯
R2,r,−y(c) d
log
dc
¯
R2,r,−y(c)
gives (65). The same equivalence T(a) ≥c⇐⇒gr(a) ≥r(c+ y) gives the endpoint cases:
¯
R2,r,−y(c) = qτr/p(c), r(c+ y) ≤gr(br),
0, r(c+ y) ≥gr(aq),
¯
R′
2,r,−y(c) = λ(c)
¯
R2,r,−y(c), r(c+ y) <gr(br),
0, r(c+ y) >gr(aq).
Because Wr is continuous, (40) implies that µr has no atoms. Thus the displayed endpoint values
agree with the limits from the interior, so the contribution is continuous at both thresholds.
2.6.2 The regime z>−1
Lemma 2.15. For every compact K ⊂(−1,∞) and every H >0, uniformly for z∈K and |h|≤H,
¯
Rr,z cr +
h
cr
−→q+ (1−q)eh
. (66)
Moreover, for every h0 >0,
lim sup
r↓0
sup
z∈K
sup
uq≤c≤cr−h0/cr
¯
Rr,z(c) ≤q+ (1−q)e−h0 <1. (67)
Consequently,
Cr(z) = cr + o(c−1
r ) (68)
and
Dr(z) −→q, (69)
uniformly on K. Moreover, for sufficiently small r, Cr(z) is regular for every z∈K.
19
```

<!-- source-page: 20 -->

### PDF page 20

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
ηK
=
Proof. Proof of (66). Fix H >0, take z∈K, and take |h|≤H. The primary non-null has B = 1
and Θ = cr + y(br), so conditional on Z= z its value is cr + y(br) + z. Since K ⊂(−1,∞) is
compact,
ηK := inf
z∈K(1 + z) >0.
By Lemma 2.10, cr →∞and y(br) ↓1. For the fixed H, this implies H/cr →0. Combining these
limits, for sufficiently small r,
|y(br)−1|≤ηK
H
≤ηK
4 ,
cr
4. (70)
For z∈K and |h|≤H, the definition of ηK gives z≥−1 + ηK, while (70) gives y(br) ≥1−ηK/4
and−h/cr ≥−H/cr ≥−ηK/4. Therefore
h
y(br) + z−
cr
≥ 1−
ηK
4 + (−1 + ηK)−
4
ηK
2 , z∈K, |h|≤H.
Equivalently, y(br) + z≥h/cr + ηK/2. Hence the conditional value of the primary non-null satisfies
|cr + y(br) + z|= cr + y(br) + z
h
= cr +
≥cr +
+ y(br) + z−
+ ηK
2 >cr +
h
cr
h
cr
,
(71)
cr
so the primary non-null is rejected at cutoff cr + h/cr, uniformly for z∈K and |h|≤H.
Next consider a secondary non-null indexed by a∈[br,aq]. Its conditional value at Z= z is
a/r+ y(a) + z. Since a≥br, we have a/r≥br/r. Also, Lemma A.1 shows that y(·), the inverse of
the strictly increasing map a(·), is increasing; hence y(a) ≥y(br). Together with z≥infu∈K u and
h≤H, this gives
cr
h
a
h
cr
H
. (72)
r
+ y(a) + z− cr +
≥
br
r−cr + y(br) + inf
u−
u∈K
cr
Here br
r−cr →∞by (46), while
H
y(br) + inf
u∈K
u−
cr
−→1 + inf
u∈K
u (73)
because y(br) ↓1 and H/cr →0. Equations (46) and (73) show that the right side of (72) tends to
+∞. Hence it is positive for sufficiently small r, uniformly in z∈K, |h|≤H, and a∈[br,aq]. Thus
every secondary non-null is rejected at cutoff cr + h/cr.
Lastly, we analyze the nulls. Since |h|≤H and rcr →0 by (46),
r cr +
h
cr
rh
= rcr +
−→0. (74)
cr
Let TK = supz∈K |z|< ∞. Since cr →∞by (46) in Lemma 2.10, while (74) gives a vanishing
rescaled cutoff, we have
h
1
uq ≤cr +
≤
cr
r
for all sufficiently small r, uniformly for z ∈K and |h|≤H. Applying (47) in Lemma 2.11 with
A= 1 and T= TK gives
R0,r,z{p(cr + h/cr)}
p(cr + h/cr)
= Lr(cr+h/cr)(|z|) + o(1).
20
```

<!-- source-page: 21 -->

### PDF page 21

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
Moreover,
Lr(cr+h/cr)(|z|) = exp−
r2(cr + h/cr)2
2 cosh(r(cr + h/cr)|z|) = 1 + o(1),
uniformly for z∈K and |h|≤H. Since π0,r = 1−r−τr →1, it follows that
¯
R0,r,z(cr + h/cr) = q+ o(1).
By (41),
h0
a
r
cr
q(r+ τr)
p(cr + h/cr) = (1−qπ0,r) p(cr + h/cr) −→(1−q)eh
p(cr)
by (305) in Lemma A.2. This proves (66).
Proof of (67). Fix h0 >0. Equation (71), evaluated at h= h0, gives
|cr + y(br) + z|>cr +
,
cr
so the primary non-null is rejected at cutoff cr + h0/cr. Equations (72), (46), and (73) give
h0
+ y(a) + z>cr +
, a∈[br,aq],
for sufficiently small r, uniformly in z ∈K. Thus every secondary non-null is also rejected at
cutoff cr + h0/cr. Since rejection at cutoff c means |Ti|≥c, all non-nulls are rejected for every
uq ≤c≤cr + h0/cr. Therefore, on this interval,
¯
Rr,z(c) =
¯
R0,r,z(c) + q(r+ τr)
p(c).
For uq ≤c≤cr−h0/cr, Lemma 2.11 and rcr →0 from (46) give
¯
sup
sup
R0,r,z(c) ≤q+ o(1).
z∈K
uq≤c≤cr−h0/cr
Also p(c) ≥p(cr−h0/cr), so (41) and (305) in Lemma A.2 give
sup
uq≤c≤cr−h0/cr
q(r+ τr)
p(c) ≤ q(r+ τr)
p(cr−h0/cr) = (1−qπ0,r) p(cr)
p(cr−h0/cr) −→(1−q)e−h0
.
Taking the supremum over z∈K and then the limsup in r proves (67).
Proof of (68). Apply Lemma 2.12 with
mr(z) = cr, wr(z) = c−1
r , d(z) = q, ξ(z) = 1.
The set K is compact by hypothesis. Since cr →∞, for all sufficiently small r, mr(z) = cr >uq and
wr(z) = c−1
r >0. Moreover, d≡q and ξ≡1 are continuous on K, with d(z) ∈[0,1) and ξ(z) >0.
For every fixed H >0,
H
inf
z∈K{mr(z)−Hwr(z)}= cr−
>uq
cr
21
```

<!-- source-page: 22 -->

### PDF page 22

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
for all sufficiently small r, which verifies (50). Under these choices, (51) becomes
sup
z∈K
|h|≤H
¯
sup
Rr,z cr +
h
cr
−q−(1−q)eh −→0,
which is exactly (66). Its left-of-crossing assumption (52) becomes, for every h0 >0,
¯
lim sup
r↓0
sup
z∈K
sup
Rr,z(c) <1.
uq≤c≤cr−h0/cr
This follows from (67), because q+ (1−q)e−h0 <1. Hence all assumptions of Lemma 2.12 hold,
and (53) gives
z∈K
sup
Cr(z)−cr
c−1
r
= sup
z∈K
cr|Cr(z)−cr|−→0,
which is (68) uniformly on K.
Proof of (69). Fix H >0. On |c−cr|≤H/cr, all non-nulls are rejected, uniformly over z ∈K,
and hence
¯
Rr,z(c) =
¯
R0,r,z(c) + q(r+ τr)
p(c). (75)
In the notation of Lemma 2.14, uniformly for |c−cr|≤H/cr and z∈K, (46) gives
c−→∞, rc−→0.
For all sufficiently small r, this range lies in [C,1/r], with C →∞. Thus (48)-(49) in Lemma 2.11
give, for either sign,
(rc)2
±rcz+ O(r2) {1 + o(1)}
Q±(c,z) = c
x±
exp−
= 1 + o(1),
2
because c/x±→1, rc→0, and z ranges over the compact set K. Also x±/cr →1, c/cr →1, and
√1−r2 →1. Thus (296) in Lemma A.2, applied directly to (57) in Lemma 2.14, gives
sup
z∈K
sup
|¯
R′
0,r,z(c)|= o(cr).
|c−cr|≤H/cr
For |c−cr|≤H/cr, write c= cr + h/cr, where |h|≤H. By (41),
q(r+ τr)
p(c) = (1−qπ0,r)p(cr)
p(c),
and (305) in Lemma A.2 gives
p(cr)
=
p(c)
p(cr)
p(cr + h/cr) −→eh
,
uniformly for |h|≤H. Since eh ≥e−H on this range and 1−qπ0,r →1−q>0, for all sufficiently
small r,
inf
|c−cr|≤H/cr
q(r+ τr)
p(c) ≥
1−q
2·
e−H
22
2.
```

<!-- source-page: 23 -->

### PDF page 23

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
mH
dc
2
Thus we may take mH = (1−q)e−H/4 >0. Since all non-nulls are fully rejected for |c−cr|≤H/cr,
their combined contribution is q(r+ τr)/p(c), whose derivative is λ(c)q(r+ τr)/p(c). Together with
λ(c)∼cr uniformly for |c−cr|≤H/cr, this gives
d
inf
|c−cr|≤H/cr
q(r+ τr)
p(c) ≥
cr
for all sufficiently small r. By contrast,¯
R′
0,r,z(c) = o(cr) uniformly over z∈K and |c−cr|≤H/cr.
Differentiating (75) therefore shows that
inf
z∈K
¯
inf
R′
r,z(c) >0 (76)
|c−cr|≤H/cr
for all sufficiently small r. By (68), uniformly for z∈K,
H
cr−
<Cr(z) <cr +
cr
cr
for all sufficiently small r; moreover, cr−H/cr >uq. Equation (76) and the smoothness of the null
contribution on this interval therefore verify the hypotheses of Proposition 2.5, so Cr(z) is regular.
Equation (44) gives
¯
Dr(z) =
R0,r,z{Cr(z)}.
Put hr(z) = cr{Cr(z)−cr}. Equation (68) gives hr(z) →0 uniformly on K. The null limit
established in the proof of (66), evaluated at h= hr(z), now gives
sup
z∈K
|Dr(z)−q|= sup
z∈K
¯
R0,r,z{Cr(z)}−q −→0,
H
which is (69).
2.6.3 The regime z∈(−yq,−1)
Let y=−z. For 1 <y<yq, put
κ(y) = a(y)y
′{a(y)}>0. (77)
The positivity follows from Lemma A.1, since a(y) >0 and y′{a(y)}>0 for 1 <y <yq. For the
remainder of the population analysis, define
sr(y) = cr + y(br)−y. (78)
The next lemma separates the primary non-null value from the cutoffs on the r−1 scale.
Lemma 2.16. For every compact I ⊂(1,∞) and every H >0, if aI = infy∈I a(y) >0, then
sup
y∈I
a(y)
r|sr(y)|≤rcr + rsup
|y(br)−y|−→0,
inf
y∈I
|h|≤H
r
y∈I
+ h= aI−rH −→aI >0.
(79)
Consequently, the primary non-null is not rejected at cutoff a(y)/r+ h for all sufficiently small r,
uniformly for y∈I and |h|≤H.
r
23
```

<!-- source-page: 24 -->

### PDF page 24

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
Proof. Conditional on Z=−y, the primary non-null value is sr(y) by (78). The two limits in (79)
follow from (45) and (46) in Lemma 2.10. Their limiting bounds are separated by aI >0, which
proves the rejection claim.
Lemma 2.17. For every compact I ⊂(1,∞),
¯
sup
sup
Rr,−y(s) ≤q+ o(1) <1. (80)
y∈I
uq≤s≤sr(y)
Proof. Put yI = inf I >1 and δshift
I = (yI−1)/2 >0. Since y(br) ↓1,
δshift
I ≤y−y(br) ≤sup
u−1 =: ∆I <∞ (81)
u∈I
for all sufficiently small r, uniformly for y∈I. Hence sr(y) ≤cr−δshift
I . From (42) and the bound
by one on each non-null rejection probability,
¯
Rr,−y(s) ≤¯
R0,r,−y(s) + q(r+ τr)
p(s) , uq ≤s≤sr(y).
Uniformly on this range, 0 ≤rs≤rcr →0. Therefore (47) in Lemma 2.11 gives
¯
R0,r,−y(s) = q+ o(1).
Since p is decreasing, (41) yields
q(r+ τr)
p(s) ≤q(r+ τr)
p{sr(y)}
= (1−qπ0,r) p(cr)
p{cr + y(br)−y}.
Here sr(y) →∞uniformly and the shift y−y(br) lies in [δshift
I ,∆I]. Thus (306) in Lemma A.2 gives
p(cr)
p{cr + y(br)−y}−→0.
sup
y∈I
Combining the bounds proves (80).
We first prove a lemma that is useful for the key result in this regime.
Lemma 2.18. For every compact I ⊂(1,yq) and every H >0, there is an interval UI whose closure
is contained in (0,aq) and contains {a(y) : y∈I}. For all sufficiently small r, with gr as in (59),
the equation
gr{˜
αr(y,h)}= gr{a(y)}+ rh (82)
has a unique solution˜
αr(y,h) ∈UI, uniformly for y∈I and |h|≤H, and
˜
αr(y,h) = a(y) + O(r). (83)
Conditional on Z=−y, a secondary non-null with a=
˜
a is rejected at cutoff a(y)/r+ h if and
only if
˜
a∈[˜αr(y,h),aq].
Finally,
log p{˜
αr(y,h)/r}
p(a(y)/r+ h)
= κ(y)h+ o(1), (84)
uniformly for y∈I and |h|≤H.
24
```

<!-- source-page: 25 -->

### PDF page 25

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
Proof. Fix a compact I ⊂(1,yq) and H >0 as in the statement. Let
AI = {a(y) : y∈I}.
Because I ⊂(1,yq) is compact, AI is a compact subset of (0,aq). Choose an interval UI whose
closure is contained in (0,aq) and such that AI ⊂UI. By (45) in Lemma 2.10, br →0, so
UI ⊂(br,aq) for all sufficiently small r. Lemma 2.14 then shows that gr is strictly increasing on UI.
Put dI = dist(AI,Uc
I) >0. If rH <dI/2, then a(y) ±rH ∈UI for all y ∈I. Since g′
r ≥1 on
UI, the intermediate value theorem gives a unique solution to (82) in UI, and
|˜
αr(y,h)−a(y)|≤rH.
Hence, (83) is proved.
Put c= a(y)/r+ h and β = ˜αr(y,h). If aI = infu∈I a(u) >0, then
r(y−c) = ry−a(y)−rh≤rsup
u−aI + rH <0 <gr(br)
u∈I
for all sufficiently small r, uniformly for y∈I and |h|≤H. Thus (60) holds uniformly. Moreover,
(82) and y{a(y)}= y give
gr(β) = gr{a(y)}+ rh= r(c+ y).
This is (61), so (62) shows that a secondary non-null is rejected exactly when its index lies in
[˜αr(y,h),aq].
Write β = ˜αr(y,h). Differentiating (82) with respect to h gives
∂β
∂h=
r
1 + ry′(β).
Since p′(x)/p(x) =−λ(x),
∂
∂hlog p(β/r)
p{a(y)/r+ h}= λ a(y)
r
Moreover, (82) and y{a(y)}= y imply
β
a(y)
+ h−
λ(β/r)
1 + ry′(β). (85)
=
+ h+ y−y(β). (86)
r
r
The function a(y) is bounded away from zero on I, and (83) gives β= a(y) + O(r) uniformly. Hence
both arguments of λ in (85) are of order r−1. Using λ(x) = x+ O(x−1) from (296) in Lemma A.2
and then (86), we obtain
λ a(y)
r
+ h−
λ(β/r)
1 + ry′(β)
=
a(y)
r
β/r
+ h−
1 + ry′(β) + O(r)
{a(y) + rh}y′(β) + y(β)−y
=
1 + ry′(β) + O(r)
−→a(y)y
′{a(y)}= κ(y)
uniformly for y∈I and |h|≤H. At h= 0, uniqueness in (82) gives β= a(y), so the logarithm in
(85) is zero. Integrating from 0 to h proves (84).
25
```

<!-- source-page: 26 -->

### PDF page 26

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
Lemma 2.19. For every compact I ⊂(1,yq) and every H >0, uniformly for y∈I and |h|≤H,
¯
Rr,−y
a(y)
r
+ h −→qM(y) + {1−qM(y)}eκ(y)h
. (87)
Moreover, for every h0 >0, there is γ >0 such that, for all sufficiently small r,
sup
y∈I
sup
uq≤c≤a(y)/r−h0
¯
Rr,−y(c) ≤1−γ. (88)
Consequently, uniformly for y∈I,
Cr(−y)−
a(y)
−→0 (89)
r
and
Dr(−y) −→qM(y). (90)
Moreover, for sufficiently small r, Cr(−y) is regular for every y∈I.
Proof. Proof of (87). Fix H > 0, take y ∈I, and take |h|≤H. By Lemma 2.18, a secondary
non-null with a= ˜a is rejected at cutoff a(y)/r+ h if and only if
˜
a∈[˜αr(y,h),aq].
By (40), their mass under the secondary component is
τrµr([˜αr(y,h),aq]) = Wr{˜
αr(y,h)}.
The definition (38) therefore gives
qWr{˜
αr(y,h)}
p(a(y)/r+ h)
= 1−qM{y(˜αr(y,h))} p{˜
αr(y,h)/r}
p(a(y)/r+ h).
By (83), y(˜αr(y,h)) →y uniformly for y∈I and |h|≤H. Equation (84) gives
p{˜
αr(y,h)/r}
p(a(y)/r+ h) −→eκ(y)h
,
uniformly for y∈I and |h|≤H. Hence
qWr{˜
αr(y,h)}
p(a(y)/r+ h)
= 1−qM{y(˜αr(y,h))} p{˜
αr(y,h)/r}
p(a(y)/r+ h) −→{1−qM(y)}eκ(y)h (91)
Lemma 2.16, through (79), shows that the primary non-null is not rejected at cutoff a(y)/r+ h,
uniformly for y∈I and |h|≤H.
Since a(y) is bounded away from zero on I and a(y) ≤aq, for all sufficiently small r,
uq ≤
a(y)
r
+ h≤
aq + 1
r
uniformly for y ∈I and |h|≤H. Thus (47) in Lemma 2.11, applied with A= aq + 1 and
T = supu∈I u, gives
¯
Combining (91) and (92) proves (87).
R0,r,−y(a(y)/r+ h) −→qLa(y)(y) = qM(y). (92)
26
```

<!-- source-page: 27 -->

### PDF page 27

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
Proof of (88). Lemma 2.17, through (80), excludes a crossing on uq ≤s≤sr(y), uniformly for
y∈I. Fix h0 >0. The complementary range sr(y) <s≤a(y)/r−h0 is nonempty uniformly on I,
because
inf
y∈I
a(y)
r−h0−sr(y) ≥
infy∈I a(y)
r−cr−OI(1) −→∞,
where rcr →0 by (46) in Lemma 2.10. It remains to prove that there is γ >0 such that, for all
sufficiently small r,
sup
sup
¯
Rr,−y(s) ≤1−γ (93)
y∈I
sr(y)<s≤a(y)/r−h0
For s > sr(y), the identity Ti = sr(y) > 0 gives |Ti|= Ti < s. For sufficiently small r, every
secondary non-null value is positive uniformly over y ∈I and˜
a ∈[br,aq]. For every y > 1 and
s>sr(y), define
Ar,y,s := {˜
a∈[br,aq] : gr(˜a) ≥r(s+ y)}, βr,y,s := inf Ar,y,s ∪{aq}. (94)
On the range sr(y) <s≤a(y)/r−h0, the set is nonempty for sufficiently small r, since˜
a= aq
satisfies the inequality uniformly over y ∈I. By (59) and Lemma 2.14, gr is strictly increasing.
Thus a secondary non-null with a= ˜a is rejected if and only if˜
a∈[βr,y,s,aq]. Therefore, by (42),
¯
Rr,−y(s) =
¯
R0,r,−y(s) + qτr
p(s)µr([βr,y,s,aq]). (95)
Suppose (93) fails for this h0. Then there are
rn ↓0, yn ∈I, srn(yn) <sn ≤a(yn)/rn−h0, lim inf
n→∞
¯
Rrn,−yn(sn) ≥1. (96)
After taking a subsequence,
yn →y∈I, a(yn) →a(y), xn = rnsn →x∈[0,a(y)]. (97)
Define
a(yn)
hn := sn−
.
rn
Then hn ≤−h0 by (96). If hn = O(1), then after passing to a further subsequence hn →h≤−h0.
Equation (87) gives
¯
Rrn,−yn(sn) −→qM(y) + {1−qM(y)}eκ(y)h ≤qM(y) + {1−qM(y)}e−κ(y)h0 <1,
contradicting lim infn→∞¯
Rrn,−yn(sn) ≥1. Hence, after passing to a further subsequence if necessary,
it remains to consider
hn →−∞. (98)
We next identify the rejected secondary non-nulls at cutoff sn. A secondary non-null with index
˜
a∈[brn,aq] has (Θ,B) = (˜a/rn + y(˜a),1). Conditional on Z=−yn, its value is
T˜
a,n =
˜
a
rn
+ y(˜a)−yn.
For all large n, this value is positive uniformly in˜
a∈[brn,aq], because brn/rn →∞and y(˜
a)−yn
is bounded below. Hence |T˜
a,n|= T˜
a,n, and the rejection rule |T˜
a,n|≥sn is equivalent to
˜
a
+ y(˜a)−yn ≥sn.
rn
27
```

<!-- source-page: 28 -->

### PDF page 28

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
The rejected set is nonempty because the endpoint˜
a = aq is rejected. Indeed, compactness of
I ⊂(1,yq) and continuity of a(·) give
∆I := aq−sup
u∈I
a(u) >0.
Since sn ≤a(yn)/rn−h0 by (96),
aq
+ yq−yn−sn ≥
rn
aq−a(yn)
rn
+ yq−yn + h0 >0
for large n, because aq−a(yn) ≥∆I and yn ≤sup I <yq. Define
Gn(˜a) := grn(˜a)−rn(sn + yn),˜
a∈[brn,aq],
where gr is defined in (59). Multiplying the rejection inequality by rn, a secondary non-null with
index˜
a is rejected if and only if
Gn(˜a) ≥0.
By (59) and Lemma 2.14, Gn is continuous and strictly increasing on [brn,aq] for all large n.
Therefore a secondary non-null with a= ˜a is rejected if and only if˜
a∈[βn,aq], where
βn := inf {˜
a∈[brn,aq] : Gn(˜a) ≥0}. (99)
Put dn := yn−y(βn). If βn >brn, then Gn(βn) = 0. Thus, in this case,
βn
rn
−sn = dn. (100)
If βn = brn, then Gn(βn) ≥0, so (100) is replaced by
βn
rn
−sn ≥dn. (101)
Moreover, sn →∞, because sn > srn(yn) = crn + y(brn)−yn, crn →∞, y(brn) →1, and I is
compact. Also dn > 0 eventually. If βn = brn, this follows from the definition of dn and (81) in
Lemma 2.17, which give
dn = yn−y(brn) ≥δshift
I >0.
If βn >brn, then
grn(βn) = rn(sn + yn) = grn{a(yn)}+ rnhn ≤grn{a(yn)}−rnh0.
The strict monotonicity of grn therefore gives βn <a(yn), and hence dn = yn−y(βn) >0. null contribution term in (95) already has a limit along this subsequence:
The
qπ0,rn
R0,rn,−yn{p(sn)}
p(sn) −→qLx(y) ≤qM(y) <1. (102)
Indeed, (47) in Lemma 2.11 applies because rnsn →x, yn →y, and π0,rn →1. The inequality
follows from M(y) = supα≥0 Lα(y), the strict monotonicity of M on (1,∞), y ∈I ⊂(1,yq), and
qM(yq) = 1. Equations (95) and (102), together with the threshold characterization in (99), imply
¯
Rrn,−yn(sn) = qLx(y) + o(1) + qτrn
p(sn)µrn([βn,aq]). (103)
28
```

<!-- source-page: 29 -->

### PDF page 29

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
Moreover, (40), (38), (292) in Lemma A.1, and the bound from (100)-(101) give
qτrn
p(sn)µrn([βn,aq]) = qWrn(βn)
= 1−qM{y(βn)}p(βn/rn)
p(sn)
p(sn) ≤p(sn + dn)
p(sn). (104)
It remains only to prove that
sndn −→∞. (105)
Equations (104), (105), and (307) in Lemma A.2 imply
qτrn
p(sn)µrn([βn,aq]) = o(1).
Substituting this into (103) gives
¯
Rrn,−yn(sn) −→qLx(y) <1,
which yields a contradiction to (96).
To prove (105), we now consider three cases under (96), (97), and (98).
Case (a): 0 <x<a(y). Suppose x>0. Since brn →0 by (45) in Lemma 2.10 and rnsn →x, the
endpoint case βn = brn cannot occur for large n: multiplying (101) by rn would give
brn−rnsn ≥rn{yn−y(brn)},
whose left side tends to−x<0, while the right side is nonnegative for large n. Hence (100) holds
eventually. Multiplying it by rn gives
βn−rnsn = rndn.
The factor dn is bounded. Indeed, I is compact, so |yn|≤supu∈I |u|. Also βn ∈[brn,aq], and y(·) is
increasing by Lemma A.1; hence
y(brn) ≤y(βn) ≤y(aq) = yq. (106)
Since y(brn) ↓1 by (45) in Lemma 2.10, the sequence y(βn) is bounded. Thus rndn →0, so
βn−rnsn →0. Since rnsn →x, we have βn →x. Since x<a(y) and y(·) is strictly increasing by
Lemma A.1, y(x) <y. Together, yn →y from (97) and βn →x imply, by continuity of y(·), that
dn →d:= y−y(x) >0. Also, (100) gives βn/rn = sn + dn. Therefore, for all large n,
βn
d
= sn + dn, 0 <
2 ≤dn ≤2d, sn →∞.
rn
As a result, (105) is proved.
Case (b): x= 0. Then rnsn →0. Since
sn >srn(yn) = crn + y(brn)−yn,
(46) gives crn →∞, while (45) gives y(brn) ↓1 and compactness of I keeps yn bounded. Hence
sn →∞. If βn = brn, then βn →0 by (45). If βn > brn, then (100) holds; multiplying it by rn,
using compactness of I, and applying (106) gives
βn−rnsn = rndn →0.
29
```

<!-- source-page: 30 -->

### PDF page 30

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
Since rnsn →0, this also gives βn →0. Thus βn →0 in both cases. By (97), yn →y, and by the
inverse relation together with (290) in Lemma A.1, y(βn) →1. Hence
dn →y−1 >0.
Moreover, (100) in the interior case and (101) in the endpoint case give βn/rn ≥sn + dn. Since
dn →d:= y−1 >0 and sn →∞, (105) is proved.
Case (c): x = a(y). By (98), this is the only remaining subcase. Since rnsn → a(y) and
a(yn) →a(y), we have
rnhn = rnsn−a(yn) →a(y)−a(y) = 0.
The threshold equation Gn(˜a) = 0 is
grn(˜a) = rn(sn + yn) = a(yn) + rnyn + rnhn = grn{a(yn)}+ rnhn,
where y{a(yn)}= yn. Since hn < 0 and grn is strictly increasing by (59) and Lemma 2.14, the
corresponding threshold lies below a(yn). To justify the existence and location of this threshold,
choose η>0 such that
[a(yn)−η,a(yn)] ⊂(0,aq)
for all large n; this is possible because a(yn) →a(y) ∈(0,aq). Since−rnhn →0 and g′
rn ≥1, for all
large n,
grn{a(yn)−η}<grn{a(yn)}+ rnhn <grn{a(yn)}.
Continuity and strict monotonicity of grn therefore give a unique˜
βn ∈(a(yn)−η,a(yn)) satisfying
˜
grn(
βn) = grn{a(yn)}+ rnhn.
Moreover, the mean-value theorem and g′
rn ≥1 give
˜
0 <a(yn)−
βn ≤−rnhn −→0.
Because a(yn) remains bounded away from 0 and aq, and brn →0 by (45) in Lemma 2.10, it follows
that
brn <˜
βn <aq
eventually. Thus˜
βn is the threshold βn in (99), so Gn(βn) = 0. The mean-value theorem applied to
grn now gives, for some ξn between βn and a(yn),
−rnhn = grn{a(yn)}−grn(βn) = (a(yn)−βn){1 + rny
′(ξn)}.
Therefore βn <a(yn) and
a(yn)−βn =−rnhn
1 + rny′(ξn). (107)
For some ζn between βn and a(yn),
βn
−sn = dn = y
′(ζn){a(yn)−βn}. (108)
rn
Combining (107) and (108) gives
sndn = (rnsn) y′(ζn)
1 + rny′(ξn)(−hn). (109)
30
```

<!-- source-page: 31 -->

### PDF page 31

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
Here rnsn →a(y) > 0. Also βn →a(y) and a(yn) →a(y), so ξn,ζn →a(y); hence y′(ζn) →
y′{a(y)}>0, while 1 + rny′(ξn) →1. Since hn →−∞by (98), (109) yields
sndn −→∞.
Thus (105) is proved.
This proves (93). Combining (80) and (93), and reducing γ if necessary, proves (88).
Proof of (89). Apply Lemma 2.12 to¯
Rr,−y, with
mr(y) = a(y)
r
, wr(y) = 1, d(y) = qM(y), ξ(y) = κ(y).
The set I is compact, and aI = infy∈I a(y) >0; hence, for every fixed H >0,
inf
y∈I
a(y)
r−H ≥
aI
r−H >uq
for all sufficiently small r. Because I ⊂(1,yq) and M is continuous and strictly increasing there,
0 <d(y) = qM(y) <1, ξ(y) = κ(y) >0,
and both functions are continuous on I. Equation (87) is exactly (51), while (88) is (52). Thus all
hypotheses of Lemma 2.12 hold, and (53) gives (89) uniformly on I.
Proof of (90). Fix H = 1. For y∈I and |h|≤H, let˜
αr(y,h) be the threshold defined by (82).
Write
¯
R2,r,−y
a(y)
r
+ h=
qWr{˜
αr(y,h)}
= 1−qM{y(˜αr(y,h))} p{˜
αr(y,h)/r}
p(a(y)/r+ h)
p(a(y)/r+ h).
Equation (79) shows that the primary non-null is not rejected for y∈I and |h|≤H. Consequently,
(42) gives
¯
Rr,−y
a(y)
r
+ h=
¯
R0,r,−y
a(y)
r
+ h +
¯
R2,r,−y
a(y)
r
+ h .
We first differentiate the secondary non-null contribution¯
R2,r,−y{a(y)/r+ h}. Equation (60)
holds uniformly, since
for all sufficiently small r. term in (64),
r
gr(br) >0 >ry−a(y)−rh= r y−
a(y)
r
+ h
Apply (64) in Lemma 2.14 with c= a(y)/r+ h and β=
˜
αr(y,h). The
qM′{y(β)}y′(β)
−
1−qM{y(β)}
1 + ry′(β),
is O(r) uniformly by (83) and (292) in Lemma A.1. Indeed, (83) places β, uniformly over y∈I and
|h|≤H, in a fixed compact subinterval of (0,aq). On this subinterval,
|M′{y(β)}|y′(β)
1−qM{y(β)}= O(1),
r
= O(r),
1 + ry′(β)
by (292) in Lemma A.1; hence their product is O(r) uniformly.
31
```

<!-- source-page: 32 -->

### PDF page 32

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
The last two terms in (64) are
−
λ(β/r)
1 + ry′(β) + λ(c).
For these terms, (61) implies
β
1 + ry′(β)
= c+ y−y(β).
r
Because a(y) is bounded away from zero on I, (83) gives c≍β/r≍r−1 uniformly. Thus (296) in
Lemma A.2 gives
λ(β/r)
β/r
λ(c)−
= c−
1 + ry′(β) + O(r)
rcy′(β) + y(β)−y
=
1 + ry′(β) + O(r).
Now rc= a(y) + rh→a(y), while (83) and continuity of y and y′give
y(β)−y= o(1), y
′(β) = y
′{a(y)}+ o(1)
uniformly. Consequently,
λ(c)−
λ(β/r)
1 + ry′(β) −→a(y)y
′{a(y)}= κ(y)
uniformly, by (77). Combining this with (91) yields
∂
¯
∂h
R2,r,−y
a(y)
r
+ h −→κ(y){1−qM(y)}eκ(y)h (110)
uniformly for y∈I and |h|≤H.
It remains to differentiate the null contribution. Use the notation of Lemma 2.14 at c= a(y)/r+h.
Since a(y) is bounded away from zero on I and a(y) ≤aq, for all sufficiently small r,
uq ≤
a(y)
r
+ h≤
aq + 1
r
uniformly for y∈I and |h|≤H. Applying (47) in Lemma 2.11 with A= aq + 1 and T= supu∈I u
shows that
¯
R0,r,−y
a(y)
sup
y∈I
sup
|h|≤H
Equation (58) in Lemma 2.14 can be written as
+ h= O(1). (111)
∂
∂hlog
¯
R0,r,−y(c) =
Qσ
Q+ + Q−
λ(c)−
σ∈{−,+}
λ(xσ)
√1−r2 ,
because ∂c/∂h= 1. Moreover, (296) in Lemma A.2 gives, for either sign,
λ(c)−
λ(x±)
√1−r2
= c−
c±ry
1−r2 + O(r) = O(r)
uniformly for y∈I and |h|≤H. Since the nonnegative weights Qσ/(Q+ + Q−) sum to one,
sup
y∈I
|h|≤H
sup
∂
∂hlog
¯
R0,r,−y
a(y)
+ h= O(r). (112)
32
r
r
```

<!-- source-page: 33 -->

### PDF page 33

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
Multiplying (111) and (112) gives
∂
sup
y∈I
|h|≤H
sup
∂h
¯
R0,r,−y
a(y)
r
+ h −→0. (113)
Since I is compact and κ(y){1−qM(y)}eκ(y)h is strictly positive on I×[−H,H], (110) and (113)
imply
inf
y∈I
inf
|h|≤H
∂
∂h
¯
Rr,−y
a(y)
r
+ h >0 (114)
for all sufficiently small r. For every fixed H >0, (92) verifies (54) with d(y) = qM(y). The null
contribution is smooth, and (114), with H = 1, gives the positive derivative required by Lemma 2.13.
That lemma therefore shows that Cr(−y) is regular for every y∈I when r is sufficiently small, and
(55) gives
sup
y∈I
|Dr(−y)−qM(y)|−→0,
which is (90).
2.6.4 The regime z<−yq
Let y=−z. For y>yq, let αq(y) ∈(0,aq) be the unique solution of
qLαq(y)(y) = 1. (115)
For fixed y, the map a→La(y) is continuous and
∂
∂alog La(y) =−a+ ytanh(ay). (116)
By Lemma A.1, this derivative is positive on (0,a(y)). Since y>yq, the same lemma gives a(y) >aq,
so a→La(y) is strictly increasing on [0,aq]. Moreover, by the definition of aq in (36),
qL0(y) = q<1, qLaq(y) >qLaq(yq) = qM(yq) = 1,
where the strict inequality follows from aq >0, y>yq, and the monotonicity of cosh(aqy) in y>0.
Thus continuity and strict monotonicity give exactly one solution to (115).
Lemma 2.20. For every compact I ⊂(yq,∞), uniformly for y∈I,
rCr(−y) −→αq(y) (117)
and
Dr(−y) −→1. (118)
Proof. Proof of (117). Fix a compact I ⊂(yq,∞), and put
δI = inf
y∈I(y−yq) >0.
Use sr(y) from (78) and (Ar,y,s,βr,y,s) from (94). By (59) and Lemma 2.14, g′
r(˜
a) = 1 + ry′(˜
a) >1.
For all sufficiently small r, the primary non-null is not rejected when s > sr(y). To verify the
33
```

<!-- source-page: 34 -->

### PDF page 34

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
corresponding sign assertion for the secondary non-nulls, note that, conditional on Z=−y, the
value associated with˜
a∈[br,aq] is
˜
a
br
+ y(˜a)−y≥
r
r
+ y(br)−sup
u∈I
u. (119)
The monotonicity of y(·) gives (119). Its right-hand side tends to infinity as r ↓0, by (45) in
Lemma 2.10. Hence every secondary non-null value is positive for all sufficiently small r, uniformly
over y∈I and˜
a∈[br,aq]. Thus the rejected secondary non-nulls are indexed by Ar,y,s. If this set
is nonempty, continuity and strict monotonicity of gr show that it is the closed interval [βr,y,s,aq]
and that
gr(βr,y,s) ≥r(s+ y).
Consequently, in the nonempty case,
βr,y,s
r−s≥y−y(βr,y,s) ≥y−yq ≥δI. (120)
If Ar,y,s = ∅, its µr-mass is zero. Since µr({aq}) = 0 by (40), the convention in (94) gives in both
cases
µr(Ar,y,s) = µr([βr,y,s,aq]).
Using (40), (292) in Lemma A.1, and (120) when the set is nonempty, we obtain
0 ≤ qτr
p(s)µr([βr,y,s,aq]) ≤p(s+ δI)
p(s).
Moreover,
inf
y∈I
sr(y) = cr + y(br)−sup
y−→∞,
y∈I
because cr →∞, y(br) →1, and I is compact. Therefore (306) in Lemma A.2 gives
sup
y∈I
sup
s>sr(y)
qτr
p(s)µr([βr,y,s,aq]) −→0. (121)
The function (a,y) →La(y) is C∞. Equation (116), together with αq(y) < aq < a(y) and
Lemma A.1, shows that
∂
∂alog La(y)
>0.
a=αq(y)
The implicit function theorem therefore shows that y→αq(y) is continuous on (yq,∞). Since I is
compact,
mI := inf
y∈I
min{αq(y),aq−αq(y)}>0. (122)
Fix any 0 <δ<mI/2. For every y∈I, continuity and strict monotonicity in a give
qLαq(y)−δ(y) <qLαq(y)(y) = 1 <qLαq(y)+δ(y).
Both strict gaps are continuous functions of y. Their minima over the compact set I are positive, so
there is γ >0 such that, uniformly on I,
qLαq(y)−δ(y) ≤1−2γ, qLαq(y)+δ(y) ≥1 + 2γ (123)
34
```

<!-- source-page: 35 -->

### PDF page 35

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
The choice δ<mI/2 also gives
αq(y) + δ≤αq(y) + mI
2 ≤
αq(y) + aq
2 <aq <a(y), (124)
uniformly for y∈I.
Write ψy(x) = log Lx(y). The proof of Lemma A.1, through (293), shows that ψ′
y(x) > 0 for
0 <x<a(y). By (124), every x∈(0,αq(y) + δ) lies in (0,a(y)). Hence ∂xLx(y) = Lx(y)ψ′
y(x) >0
throughout (0,αq(y) + δ), and therefore x→Lx(y) is increasing on [0,αq(y) + δ].
On uq ≤s≤sr(y), (80) in Lemma 2.17 gives
¯
sup
sup
Rr,−y(s) ≤q+ o(1).
y∈I
uq≤s≤sr(y)
For s>sr(y), the term in (42) that corresponds to the primary non-nulls is zero, and (121) and
(47) in Lemma 2.11 give, uniformly for y∈I and sr(y) <s≤(αq(y) + δ)/r,
¯
Rr,−y(s) =
¯
R0,r,−y(s) + qτr
p(s)µr([βr,y,s,aq]) = qLrs(y) + o(1).
Combining these two ranges gives
¯
sup
uq≤s≤(αq(y)−δ)/r
Rr,−y(s) ≤qLαq(y)−δ(y) + o(1) ≤1−γ. (125)
Since rsr(y) →0 uniformly on I and αq(y) + δ is bounded away from zero, we have
αq(y) + δ
r
>sr(y)
for all sufficiently small r, uniformly on I. At the cutoff (αq(y) + δ)/r, the term in (42) that
corresponds to the primary non-nulls is zero, while the secondary term is nonnegative. Therefore
(47) in Lemma 2.11 gives, uniformly for y∈I,
¯
Rr,−y
αq(y) + δ
r
≥¯
R0,r,−y
αq(y) + δ
r
= qLαq(y)+δ(y) + o(1). (126)
By (123), the right side is at least 1 + γ for all sufficiently small r. Hence
αq(y)−δ<rCr(−y) ≤αq(y) + δ.
Letting δ↓0 gives
rCr(−y) −→αq(y),
uniformly for y∈I.
Proof of (118). We now verify regularity for each fixed sufficiently small r. Fix one 0 <δ<mI/2
as in (122) and consider the interval
αq(y)−δ
αq(y) + δ
≤s≤
.
The primary non-null has conditional value
r
r
Ti = cr + y(br)−y= sr(y).
35
```

<!-- source-page: 36 -->

### PDF page 36

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
It is positive for sufficiently small r, uniformly in y∈I, and it is rejected at cutoff s exactly when
s≤sr(y). Since δ<mI/2 and mI ≤αq(y), we have αq(y)−δ≥mI/2. On the other hand,
rsr(y) = rcr + r{y(br)−y}−→0
uniformly for y∈I, by (46), y(br) →1, and compactness of I. Therefore, for all sufficiently small r,
for every y∈I and every cutoff s satisfying
αq(y)−δ
αq(y) + δ
,
≤s≤
r
r
we have
αq(y)−δ
sr(y) <
r
≤s.
Thus every cutoff in this interval lies strictly to the right of the primary value sr(y), so the primary
non-null is not rejected there. Moreover, uniformly for these y and s,
r(s+ y)−gr(br) ≥αq(y)−δ+ r{y−y(br)}−br ≥
gr(aq)−r(s+ y) ≥aq−αq(y)−δ+ r(yq−y) ≥
mI
2−o(1) >0,
mI
2−o(1) >0.
Strict monotonicity of gr therefore implies that Ar,y,s ̸= ∅, that βr,y,s ∈(br,aq). and strict monotonicity of gr give
By (94), continuity
gr(βr,y,s) = r(s+ y).
Using gr(a) = a+ ry(a) from (59), this equality yields
βr,y,s = rs+ r{y−y(βr,y,s)}= rs+ O(r)
uniformly. Hence, for all sufficiently small r,
mI
mI
4 ≤βr,y,s ≤aq−
4 ,
so the thresholds remain in a fixed compact subinterval of (0,aq).
For y∈I and cutoffs s in the local crossing interval
αq(y)−δ
αq(y) + δ
≤s≤
r
write the secondary non-null contribution as
¯
R2,r,−y(s) = 1−qM{y(βr,y,s)}p(βr,y,s/r)
p(s).
,
r
Then
¯
¯
¯
Rr,−y(s) =
R0,r,−y(s) +
R2,r,−y(s).
Abbreviate β= βr,y,s. Equation (60) holds uniformly because gr(br) >0 >r(y−s) for all sufficiently
small r. The term in (64) of Lemma 2.14, evaluated at c= s and βr,y(s) = βr,y,s = β, is
−
qM′{y(β)}y′(β)
1−qM{y(β)}
r
1 + ry′(β).
36
```

<!-- source-page: 37 -->

### PDF page 37

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
Because
mI
4 ≤β ≤aq−
mI
4 ,
(292) in Lemma A.1 and continuity give a constant CI <∞such that
mI/4≤a≤aq−mI/4
sup
qM′{y(a)}y′(a)
1−qM{y(a)} ≤CI.
Since y′(β) >0,
0 <
qM′{y(β)}y′(β)
and therefore
The expressions in (64) are
1−qM{y(β)}
r
1 + ry′(β) ≤r,
r
1 + ry′(β) ≤CIr.
mI
−
λ(β/r)
1 + ry′(β) and λ(s).
To bound their sum, write
λ(t) = t+ ε(t), by (296) in Lemma A.2. On the cutoff range,
0 <ε(t) <t−1
,
s≥
mI
2r
,
β
r
≥
4r
,
and hence ε(s) = O(r) and ε(β/r) = O(r) uniformly. Using β/r= s+ y−y(β), we obtain
λ(β/r)
λ(s)−
1 + ry′(β)
β/r
= s−
1 + ry′(β) + O(r)
rsy′(β) + y(β)−y
=
1 + ry′(β) + O(r) = O(1),
uniformly, because rs, y, y(β), and y′(β) are uniformly bounded. Hence
sup
y∈I
|rs−αq(y)|≤δ
sup
∂
∂slog
¯
R2,r,−y(s) = O(1). (127)
Moreover, βr,y,s/r−s≥δI by (120), so βr,y,s/r≥s+ δI. Since pis decreasing on [0,∞), and since
(292) in Lemma A.1 gives 0 ≤1−qM{y(βr,y,s)}≤1, we have
0 ≤¯
R2,r,−y(s) ≤p(s+ δI)
p(s).
Applying (303) in Lemma A.2 with x= s and δ= δI gives
0 ≤¯
R2,r,−y(s) ≤p(s+ δI)
p(s) ≤(1 + s−2) exp−sδI−
δ2
I
2
= o(r), (128)
uniformly on the interval. The last o(r) follows because (122) and 0 <δ<mI/2 imply
αq(y)−δ
mI
s≥
≥
r
2r
37
```

<!-- source-page: 38 -->

### PDF page 38

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
Φ(x±)
Φ(s).
whenever y∈I and |rs−αq(y)|≤δ, and therefore
r−1(1 + s−2) exp−sδI−
δ2
I
2 ≤r−1(1 + o(1)) exp−
mIδI
2r−
δ2
I
2
−→0
¯
uniformly. Since ∂s
R2,r,−y(s) =
¯
R2,r,−y(s)∂slog
¯
R2,r,−y(s), (127) and (128) imply
sup
y∈I
|rs−αq(y)|≤δ
sup
∂
¯
∂s
R2,r,−y(s) = o(r). (129)
For the null contribution term, put
x+ =
s+ ry
√1−r2 , x−
=
s−ry
√1−r2 , Q±=
Because αq(y)−δ≥mI/2, the range in (127) implies
s≥
mI
2r
−→∞,
while rsand yrange over compact sets. Therefore (48) in Lemma 2.11, with z=−y, gives uniformly
Q+ = e−(rs)2/2−rsy + o(1), Q−
= e−(rs)2/2+rsy + o(1).
Indeed, s/x±= 1 + o(1), the O(r2) term in (48) is uniform, and its remainder tends to zero because
s→∞uniformly.
Next, (297) in Lemma A.2 gives
1
r
λ(s)−
1
r
λ(s)−
λ(x+)
√1−r2
λ(x−)
√1−r2
(130)
More precisely, for either sign,
λ(s)−
λ(x±)
√1−r2
s±ry
= s−
1−r2 +
1
s−
+ O(r3),
s±ry
where
1
s−
1
= O(r3),
s±ry
1
r
s−
s±ry
1−r2
=−rs∓y
1−r2.
This proves (130).
Substitution of these four expansions into (57) in Lemma 2.14, together with π0,r →1, yields
1
r
∂
¯
R0,r,−y(s) = q
e−(rs)2/2 e−rsy(−rs−y) + ersy(−rs+ y) + o(1)
∂s
2
= qe−(rs)2/2{−rscosh(rsy) + ysinh(rsy)}+ o(1).
Finally, differentiating La(y) = e−a2/2 cosh(ay) gives
∂
∂aLa(y) = e−a2/2{−acosh(ay) + ysinh(ay)}.
38
=−rs−y+ o(1),
=−rs+ y+ o(1).
1
```

<!-- source-page: 39 -->

### PDF page 39

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
1
r
Evaluating at a= rs proves
∂
¯
R0,r,−y(s) = qe−(rs)2/2{−rscosh(rsy) + ysinh(rsy)}+ o(1) = q
∂
∂s
∂aLa(y)
+ o(1). (131)
a=rs
By (122) and (124), the pairs (rs,y) under consideration range over a compact subset of {(a,y) :
y ∈I, 0 < a < a(y)}. Continuity, (116), and Lemma A.1 therefore show that ∂aLa(y)|a=rs is
bounded away from zero uniformly. Combining (129) and (131) yields
inf
y∈I
inf
|rs−αq(y)|≤δ
∂
∂s
¯
Rr,−y(s) >0 (132)
for all sufficiently small r. Equation (117) gives, uniformly for y∈I,
αq(y)−δ
r
<Cr(−y) <
αq(y) + δ
r
for all sufficiently small r. Equation (132) and the smoothness of the null contribution for |rs−
αq(y)|≤δ verify the hypotheses of Proposition 2.5; hence Cr(−y) is regular.
Equation (44) gives
¯
Dr(−y) =
R0,r,−y{Cr(−y)}.
Because rCr(−y) → αq(y) uniformly and αq(y) stays in a compact subset of (0,aq), (47) in
Lemma 2.11 applies at c= Cr(−y) and gives
Dr(−y) = qLrCr(−y)(y) + o(1) −→qLαq(y)(y) = 1,
uniformly for y∈I, where the equality follows from (115). This proves (118).
2.6.5 Conditional limit of Dr
The following lemma establishes the limit of Dr(z) as r↓0, with D∗defined in Section 2.2.
Lemma 2.21. For every z /∈{−1,−yq},
Dr(z) −→D∗(z). (133)
Consequently,
E[Dr(Z)] −→E[D∗(Z)] = ℓ=(q). (134)
Proof. If z >−1, Lemma 2.15 gives Dr(z) →q. If−yq < z <−1, put y=−z and apply
Lemma 2.19. If z<−yq, apply Lemma 2.20. This proves (133).
At every regular crossing, 0 ≤Dr ≤1; the value assigned at nonregular points also lies in [0,1].
Dominated convergence gives the convergence in (134). Finally,
E[D∗(Z)] = qP(Z >−1) + q
−1
−yq
= qΦ(1) + q
yq
M(y)ϕ(y) dy+ Φ(yq)
1
= ℓ=(q).
M(−z)ϕ(z) dz+ P(Z <−yq)
39
```

<!-- source-page: 40 -->

### PDF page 40

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
2.7 Proofs of Theorem 2.1 and Propositions 2.2 and 2.3
Proof of Theorem 2.1. Lemma 2.21 gives E{D∗(Z)}= ℓ=(q). Fix δ>0. Choose a compact set
E ⊂R \{−1,−yq}
δ
such that
D∗(z)ϕ(z) dz>ℓ=(q)−
E
4.
Because E is compact and separated from−1 and−yq, the sets
E+ = E∩(−1,∞), E0 = E∩(−yq,−1), E−
= E∩(−∞,−yq)
are compact after discarding the empty ones. Apply the compact-uniform regime estimates on these
pieces: (66)-(67) on E+, (87)-(88) on E0, and (125)-(126) on E−, together with the corresponding
null limits (47) and (92). Taking the minimum of the positive crossing margins over the nonempty
pieces and then taking r sufficiently small, we obtain brackets
Ar(z) <Br(z), z∈E,
and a constant γ >0, such that
sup
z∈E
sup
uq≤c≤Ar(z)
sup
z∈E
¯
Rr,z(c) ≤1−γ, inf
z∈E
¯
Rr,z{Br(z)}≥1 + γ,
|¯
R0,r,z(c)−D∗(z)|≤δ
8.
Fix such an r and put
sup
Ar(z)≤c≤Br(z)
C∗= sup
z∈E
Br(z) <∞.
For z∈E, define
EN(z) = max ∥RN−Rr,z∥∞,[0,1],∥R0,N−π0,rR0,r,z∥∞,[0,1]
and
p(C∗)
t∗=
q
min γ
δ
2 ,
16 >0.
Following the argument in the proof of Theorem 2.8, on the event EN(z) <t∗, for uq ≤c≤C∗,
qRN{p(c)}
¯
p(c)−
Rr,z(c) ≤qEN(z)
p(C∗),
qR0,N{p(c)}
¯
p(c)−
R0,r,z(c) ≤qEN(z)
p(C∗).
The first bound and the two crossing margins imply
Ar(z) <CN ≤Br(z).
The second bound, (25), and the null bracket then give
FDP ≥¯
R0,r,z(CN)−
δ
16 ≥D∗(z)−
40
3δ
16.
```

<!-- source-page: 41 -->

### PDF page 41

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
2.
δ
2.
Lemma 2.6 gives, uniformly for z∈E,
P{EN(z) ≥t∗|Z= z}≤ηN := 4e−2Nt2
∗ −→0.
Since FDP ≥0 and 0 ≤D∗≤1, conditional expectation and integration over E yield
EΩN,Z,ε[FDP] ≥(1−ηN)
E
D∗(z)−
≥
D∗(z)ϕ(z) dz−
E
3δ
16 +
ϕ(z) dz
3δ
16−ηN.
Choose N large enough that ηN <δ/16. Using the choice of E and (29), we obtain
δ
EΩN[FDRΩN(BHq)] >ℓ=(q)−
For such an N, some realization ω⋆ satisfies
FDRω⋆(BHq) >ℓ=(q)−
By Lemma 2.9, choose η>0 so small that
FDR(η)
ω⋆(BHq) >FDRω⋆(BHq)−
δ
2 >ℓ=(q)−δ. (135)
The perturbed vector T(η) has finite dimension N, mean vector (θi)N
i=1 ∈RN, and covariance
matrix Σω⋆,η, which has unit diagonal and is strictly positive definite by (34) in Lemma 2.9. Thus
the bound (135) establishes (6). Since δ>0 was arbitrary, taking the supremum proves (7).
Proof of Proposition 2.2. Recall from Lemma A.1 that, for y > 1, a(y) is the unique positive
maximizer of a→La(y), equivalently the unique positive solution of
a(y) = ytanh{a(y)y}.
By the monotonicity of a(·) established in that lemma, a(y) ≥a(2) >0 for y≥2, so a(y)y→∞.
Moreover,
0 ≤y−a(y) = y[1−tanh{a(y)y}] ≤2ye−2a(y)y −→0.
Because a(y) is the maximizer defining M(y), we have M(y) = La(y)(y). Substituting the definitions
of La(y)(y) and ϕ(y), expanding cosh(t) = (et + e−t)/2, and completing the two squares gives
M(y)ϕ(y) = e−a(y)2/2 cosh{a(y)y}e−y2/2
√2π
1
=
2√2π
e−{a(y)2+y2}/2+a(y)y + e−{a(y)2+y2}/2−a(y)y
1
=
2√2π
e−{y−a(y)}2/2 + e−{y+a(y)}2/2
.
Consequently, M(y)ϕ(y) →1/(2√2π). The difference M(y)ϕ(y)−1/(2√2π) is integrable on [1,∞).
Indeed, for all sufficiently large y, a(y) ≥y/2, so
y−a(y) ≤2ye−y2
41
(136)
,
```

<!-- source-page: 42 -->

### PDF page 42

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
+ cℓ−Φ(1) + o(1). (137)
= o(q). (139)
while
e−{y−a(y)}2/2
−1 ≤{y−a(y)}2
2 , e−{y+a(y)}2/2 ≤e−y2/2
.
Y
It follows from the definition of cℓ that, as Y →∞,
Y
M(y)ϕ(y) dy=
1
2√2π
Next, (136) gives
M(y) = 1
2
ey2/2 e−{y−a(y)}2/2 + e−{y+a(y)}2/2
=
1
2
ey2/2{1 + o(1)}.
Since M(yq) = 1/q→∞, (290) in Lemma A.1 implies yq →∞. The identity qM(yq) = 1 therefore
gives
y2
q = 2 log(1/q) + 2 log 2 + o(1), yq = 2 log(1/q) + o(1). (138)
Equations (308) in Lemma A.2 and (138) give
Φ(yq) ≤ϕ(yq)
yq
= O q
yq
Substituting (137), (138), and (139) into (5) yields
ℓ=(q) = qΦ(1) + q
yq
2√2π
+ cℓ−Φ(1) + o(1) + o(q)
q log(1/q)
=
+ cℓq+ o(q).
2√π
Numerical quadrature of the absolutely convergent integral defining cℓ gives cℓ = 0.6492828....
Proof of Proposition 2.3. Since q ∈(0,1), (4) gives M(yq) = 1/q >1. By Lemma A.1, M = 1 on
[0,1] and M is strictly increasing on (1,∞), so yq >1 and M(y) ≥1 for 1 ≤y≤yq. Using (5),
ℓ=(q)−q= qΦ(1) + q
yq
M(y)ϕ(y) dy+ Φ(yq)
1
−q Φ(1) +
yq
1
ϕ(y) dy+ Φ(yq)
= q
yq
{M(y)−1}ϕ(y) dy+ (1−q)Φ(yq).
1
The integral is nonnegative, and (1−q)Φ(yq) >0 because q<1 and yq <∞. Hence ℓ=(q) >q.
3 Lower bound for one-sided tests
3.1 Main result
For 0 <q<1, define
and
y+
q
= 2 log(1/q) (140)
ℓ≤(q) = q log(1/q)
√π
+ q
2 + Φ(y+
q ). (141)
The quantities in (140) and (141) determine the finite-dimensional one-sided Gaussian lower
bound.
42
```

<!-- source-page: 43 -->

### PDF page 43

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
Theorem 3.1. For every q∈(0,1) and δ>0, there are N <∞, θ∈RN, and a positive definite
correlation matrix Σ such that BH at level q, applied to the one-sided p-values Pi = Φ(Ti) from
T∼N(θ,Σ), satisfies
FDRθ,Σ(BHq) >ℓ≤(q)−δ.
Every true null in the construction has θi = 0, and every non-null has θi >0.
The first proposition gives the small-q expansion of the one-sided lower bound.
Proposition 3.2. As q↓0,
ℓ≤(q) = q log(1/q)
√π
+ q
2 + o(q).
In particular, ℓ≤(q)/q→∞.
The next proposition shows strict anticonservativeness at every nontrivial nominal level.
Proposition 3.3. For every q∈(0,1), ℓ≤(q) >q.
Figure 2 in the Introduction plots ℓ≤(q)−q and ℓ≤(q)/q over the grid q= 0.005k, k= 1,...,199.
Table 2 gives the absolute inflation ℓ≤(q)−q and relative inflation ℓ≤(q)/q for commonly used
nominal levels.
3.2 Roadmap
Fix q. For a small r > 0, let (Θi,Bi)N
i=1 be i.i.d. from a law ν+
q,r, independently of Z,ε1,...,εN,
which are independent standard normal variables, and set
Ti = Θi + BiZ+ 1−B2
i εi. (142)
In the model (142), the law ν+
q,r has one null component and two non-null components. We first
analyze the population BH crossing conditional on Z= z. For every z /∈{0,y+
q }, its conditional
FDP converges, as r↓0, to

q, z≤0,
qez2/2
, 0 <z<y+
q ,
(143)
1, z≥y+
q.
The definition (143) specifies the values at {0,y+
q }; these values do not affect the expectation because
the boundary points have zero probability. Therefore
E{D∗
+(Z)}=
q
2 + q
y+
q
ez2/2ϕ(z) dz+ Φ(y+
q ) = ℓ≤(q).
0
We reuse the machinery and use similar notation in Subsections 2.3 and 2.4. Throughout this
section, put p+(x) = Φ(x) and u+
s
= p−1
+ (s). For x≥0 and 0 <s≤1/2,
p+(x) = p(x)
2 , p−1
+ (s) = p−1(2s). (144)
Therefore, all bounds for p in Lemma A.2 remain to apply to p+ up to a constant. Use the symbols
π+
0 , R+
z , R+
0,z,
¯
R+
z ,
¯
R+
0,z, C+(z), D+(z)
D∗
+(z) =
43
```

<!-- source-page: 44 -->

### PDF page 44

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
as the one-sided analogues of the quantities in (8) and (11)-(16). In particular, the one-sided
population cutoff is
C+(z) = inf{c≥u+
q :
¯
R+
z (c) ≥1},
and every one-sided use of Definition 2.4 has lower endpoint u+
q in place of uq. The only change to
(9)-(10) is
F+
θ,b,z(s) = Φ u+
s−θ−bz
√1−b2 , |b|<1, (145)
while F+
θ,b,z(s) = 1{θ+ bz≥u+
s }for |b|= 1. We retain the empty-crossing convention C+(z) = ∞,
D+(z) = 0, and the regularity definition in Definition 2.4.
The proofs of Lemmas 2.6 and 2.7 and Theorem 2.8 are p-value agnostic and apply after
(145); the one-sided rejection set in Lemma 2.7 is {i: Ti ≥CN}. We also use the localized DKW
bracketing in the proof of Theorem 2.8. Finally, the perturbation (32)-(33) and Lemma 2.9 apply to
the one-sided p-values as well, because their continuity argument does not use the two-sided form of
p.
3.3 Construction of ν+
q,r
This is the one-sided, sign-reversed specialization of the three-component construction in
Subsection 2.4: the signal offset y(a) is replaced by a, the envelope term M{y(a)}by ea2/2, and the
non-null loading +1 by−1.
Take r>0, and set
b+
r
= rp−1
+ (r2). (146)
We henceforth assume r is sufficiently small that r2 <1/2 and b+
r <y+
q . For b+
r ≤a≤y+
q , define
W+
r (a) = {1−qea2/2}p+(a/r)
q
. (147)
Both factors in the numerator are nonnegative and decreasing in a, and the first vanishes at a= y+
q.
Hence W+
r is continuous and decreasing. Put
τ+
r
= W+
r (b+
r ), µ+
r ([a,y+
q ]) = W+
r (a)
τ+
r
, b+
r ≤a≤y+
q. (148)
Thus µ+
r is a probability measure on [b+
r ,y+
q ]. Since p+(b+
r /r) = r2
, (144) and the quantile expansion
(301) in Lemma A.2 gives b+
r →0, and hence
τ+
r
∼
1−q
r2
. (149)
q
Finally, set
π+
0,r = 1−r−τ+
r , p+(c+
r ) = q(r+ τ+
r )
. (150)
1−qπ+
0,r
For all sufficiently small r, these quantities are well-defined and π+
0,r >0.
The law ν+
q,r is displayed in Table 4. Equivalently, for bounded measurable f,
f dν+
= π+
q,r
0,rf(0,r) + rf(c+
r + b+
r ,−1) + τ+
r
y+
q
f(a/r+ a,−1) µ+
r ( da). (151)
b+
r
44
```

<!-- source-page: 45 -->

### PDF page 45

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
Table 4: One-sided population construction. The opposite loading signs are essential.
Type Mass Θ B
Nulls π+
0,r 0 r
Primary non-nulls r c+
r + b+
r−1
Secondary non-nulls τ+
r µ+
r ( da) a/r+ a−1, a∈[b+
r ,y+
q ]
Under (151), the nulls become more significant when Z is positive. Every non-null statistic is
deterministic conditional on Z and decreases with Z. The construction is not PRDS. To see this
directly, pair a null iwith a non-null j, and fix v∈(0,1). Conditional on Pi = s, the event {Pj ≥v},
which is increasing in the p-values, has probability
Φ p−1
+ (v)−θj + rp−1
+ (s)
√1−r2 ,
strictly decreasing in s. This also exhibits the negative null-to-non-null covariance, opposite to
the nonnegative covariance assumption that guarantees Gaussian one-sided PRDS [Benjamini and
Yekutieli, 2001, Chi et al., 2025]. On the other hand, all null-null correlations equal r2, so the null
p-values are positively regression dependent and the full vector is PRDN in the terminology of Su
[2018].
3.4 Population analysis
3.4.1 Preliminaries
The next lemma gives the one-sided counterparts of (45)-(46).
Lemma 3.4. As r↓0,
b+
r →0, b+
r /r→∞, c+
r →∞, rc+
r →0, b+
r /r−c+
r →∞. (152)
Proof. By (146) and the quantile expansion (301) in Lemma A.2,
b+
r
= p−1
+ (r2)∼2 log(1/r) →∞, b+
r
∼2r log(1/r) →0.
Moreover, (149) gives τ+
r
= O(r2) and hence π+
0,r →1. Therefore (150) yields
p+(c+
qr
r )∼
Another application of (301) in Lemma A.2 gives
c+
r
∼ 2 log(1/r).
r
.
1−q
Thus c+
r →∞and rc+
r →0, while
b+
r
r−c+
r
∼(2−√2) log(1/r) −→∞.
45
```

<!-- source-page: 46 -->

### PDF page 46

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
Apply the reused population notation to ν+
q,r, and write the resulting quantities as R+
r,z, R+
0,r,z,
¯
R+
r,z,¯
R+
0,r,z,¯
R+
1,r,z,¯
R+
2,r,z, C+
r (z), and D+
r (z). Then
¯
R+
r,z(c) =
¯
R+
0,r,z(c) +
¯
R+
¯
1,r,z(c) +
R+
2,r,z(c), (153)
¯
p+{(c−rz)/√1−r2}
R+
0,r,z(c) = qπ+
0,r
p+(c). (154)
¯
R+
1,r,z(c)= qr
p+(c)1{c≤c+
r + b+
r−z}, (155)
¯
R+
r
2,r,z(c) = qτ+
p+(c)µ+
r
r(c+ z)
1 + r
,y+
q. (156)
The next lemma derives the derivatives of the null and secondary non-null contributions.
Lemma 3.5. For c>0, put
u=
c−rz
√1−r2.
The null contribution satisfies
d
Define
If βr,z(c) ∈(b+
r ,y+
q ), then
and
d
log
dc
Proof. Since
log
dc
¯
R+
0,r,z(c) = λ(c)−
d
¯
R+
dc
0,r,z(c) =
λ(u)
√1−r2 , (157)
¯
R+
0,r,z(c) λ(c)−
λ(u)
√1−r2. (158)
βr,z(c) = r(c+ z)
1 + r
.
¯
R+
2,r,z(c) = 1−qe{βr,z(c)}2/2 p+{βr,z(c)/r}
p+(c) (159)
¯
R+
2,r,z(c) =−
qrβr,z(c)e{βr,z(c)}2/2
(1 + r) 1−qe{βr,z(c)}2/2
λ{βr,z(c)/r}
+ λ(c)−
. (160)
du
1
d
dtlog p+(t) = p′
+(t)
p+(t)
1 + r
Equation (154) gives
d
dc
log
dc
which is (157). Therefore
=
=−λ(t),
√1−r2 ,
¯
R+
0,r,z(c) = d
dc log(qπ+
0,r) + log p+(u)−log p+(c)
λ(u)
=−
√1−r2 + λ(c),
d
¯
R+
dc
0,r,z(c) =
=
¯
R+
0,r,z(c) d
log
dc
¯
R+
0,r,z(c) λ(c)−
¯
R+
0,r,z(c)
λ(u)
√1−r2 ,
46
```

<!-- source-page: 47 -->

### PDF page 47

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
which proves (158).
Now suppose that βr,z(c) ∈(b+
r ,y+
q ). By (156), (148), and (147),
¯
R+
r
2,r,z(c) = qτ+
p+(c)µ+
r ([βr,z(c),y+
q ])
qW+
r {βr,z(c)}
=
p+(c)
= 1−qe{βr,z(c)}2/2 p+{βr,z(c)/r}
p+(c).
This proves (159). Moreover,
∂βr,z(c)
r
∂c=
.
1 + r
Since βr,z(c) <y+
q , we have 1−qe{βr,z(c)}2/2 >0, and hence
d
dc
¯
log
R+
qβr,z(c)e{βr,z(c)}2/2
∂βr,z(c)
2,r,z(c) =−
1−qe{βr,z(c)}2/2
∂c
−λ{βr,z(c)/r}1
∂βr,z(c)
r
∂c + λ(c)
qrβr,z(c)e{βr,z(c)}2/2
=−
(1 + r)[1−qe{βr,z(c)}2/2] + λ(c)−
λ{βr,z(c)/r}
.
1 + r
This proves (160).
The next lemma gives the limit of the null contribution.
Lemma 3.6. For every compact X ⊂[0,∞) and K ⊂R, as r ↓0 and c →∞, uniformly over
z∈K subject to rc∈X,
¯
R+
0,r,z(c) = qexp (rc)z−
(rc)2
2 + o(1). (161)
In particular, if c= c(r) →∞and rc→x≥0, then the left-hand side converges to qexp(xz−x2/2),
uniformly for z in compact sets.
Proof. Set
rzc
√1−r2
c−rz
∆r =
√1−r2−c.
Because rc and z range over compact sets while c →∞, uniformly over the stated range, ∆r =
O(r) = o(1) and
c∆r = c2 1
√1−r2−1−
1
=
2(rc)2
−z(rc) + o(1),
where the remainder is uniform. The hazard expansion (297) in Lemma A.2, together with c→∞
and ∆r = o(1), gives
log p+(c+ ∆r)
p+(c)
=−
c+∆r
λ(t) dt=−c∆r + o(1)
c
uniformly on the same range. Exponentiating, using (c−rz)/√1−r2 = c+ ∆r, and then applying
(154) together with π+
0,r →1 proves (161).
47
```

<!-- source-page: 48 -->

### PDF page 48

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
The following lemma is the one-sided analogue of Lemma 2.12.
Lemma 3.7. Let K be compact. For z ∈K, let mr(z) > u+
q and wr(z) > 0. Suppose that, for
every fixed H >0,
inf
z∈K{mr(z)−Hwr(z)}>u+
q (162)
for all sufficiently small r, and
sup
z∈K
sup
|h|≤H
¯
R+
r,z{mr(z) + wr(z)h}−d(z) −{1−d(z)}eξ(z)h −→0, (163)
where d: K →[0,1) and ξ: K →(0,∞) are continuous. Suppose also that, for every h0 >0,
lim sup
r↓0
sup
z∈K
sup
u+
q ≤c≤mr(z)−wr(z)h0
¯
R+
r,z(c) <1. (164)
Then
z∈K
sup
C+
r (z)−mr(z)
wr(z) −→0. (165)
Proof. The proof of Lemma 2.12 applies with uq,¯
Rr,z, and Cr(z) replaced by u+
q ,¯
R+
r,z, and C+
r (z),
respectively.
The following lemma is the one-sided analogue of Lemma 2.13.
Lemma 3.8. Under the assumptions and notation of Lemma 3.7, assume in addition that, for
every fixed H >0,
sup
z∈K
sup
|h|≤H
¯
R+
0,r,z{mr(z) + wr(z)h}−d(z) −→0. (166)
If, for some H∗>0 and all sufficiently small r, the map
h−→¯
R+
r,z{mr(z) + wr(z)h}
is differentiable with positive derivative on (−H∗,H∗), and the map
h−→¯
R+
0,r,z{mr(z) + wr(z)h}
is continuous there for every z∈K, then C+
r (z) is regular and
sup
z∈K
|D+
r (z)−d(z)|−→0. (167)
Proof. The proof of Lemma 2.13 applies with uq,¯
Rr,z,¯
R0,r,z, Cr(z), and Dr(z) replaced by u+
q ,
¯
R+
r,z,¯
R+
0,r,z, C+
r (z), and D+
r (z), respectively.
The next lemma shows that the primary non-null contribution is negligible uniformly away from
z= 0.
Lemma 3.9. For every compact K ⊂(0,∞), uniformly for z∈K, the primary non-null contribution
in (153), whenever nonzero, is bounded by
qr
= o(1). (168)
p+(c+
r + b+
r−z)
48
```

<!-- source-page: 49 -->

### PDF page 49

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
qr
Proof. Whenever the primary non-null contribution is nonzero, the indicator in (155) equals one, so
¯
R+
1,r,z(c) = qr/p+(c). Equation (155) also gives c≤c+
r + b+
r−z. Since p+ is decreasing,
qr
p+(c) ≤ qr
p+(c+
r + b+
r−z).
The right-hand side is the expression in (168). By (150), it can be written as
=
p+(c+
r + b+
r−z)
r(1−qπ+
0,r)
r+ τ+
r
p+(c+
r )
p+(c+
r + b+
r−z).
Fix a compact K ⊂(0,∞), and put δr,z = z−b+
r . By (152) in Lemma 3.4, δr,z remains in a fixed
compact subset of (0,∞), uniformly for z ∈K, and c+
r−δr,z →∞uniformly. Therefore (306) in
Lemma A.2, applied with x= c+
r−δr,z, gives
p+(c+
r )
p+(c+
r + b+
r−z)
=
p+(x+ δr,z)
p+(x) −→0
uniformlyforz∈K. Since0 <r(1−qπ+
0,r)/(r+τ+
r ) ≤1, theexpressionin(168)iso(1) uniformly.
The next lemma bounds the secondary non-null contribution in the two positive- z regimes.
Lemma 3.10. For all c,z∈R,
0 ≤ qτ+
r
p+(c)µ+
r
r(c+ z)
Proof. If r(c+ z)/(1 + r) ≤b+
r , then
qτ+
r ≤p+(b+
r /r) ≤p+{(c+ z)/(1 + r)}.
If b+
r <r(c+ z)/(1 + r) <y+
q , then
qτ+
r µ+
r
r(c+ z)
1 + r
,y+
q
1 + r
,y+
q ≤p+{(c+ z)/(1 + r)}
p+(c). (169)
r2(c+ z)2
2(1 + r)2 p+
c+ z
1 + r
= 1−qexp
≤p+
c+ z
1 + r
.
If r(c+ z)/(1 + r) ≥y+
q , the contribution is zero. Dividing these bounds by p+(c) proves (169).
3.4.2 The regime z<0
Lemma 3.11. For every compact K ⊂(−∞,0), uniformly for z∈K,
C+
r (z) = c+
r + o{(c+
r )−1} (170)
and
D+
r (z) −→q. (171)
Moreover, for all sufficiently small r, C+
r (z) is regular for every z∈K.
49
```

<!-- source-page: 50 -->

### PDF page 50

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
Proof. Proof of (170). Fix a compact K ⊂(−∞,0). Uniformly for z ∈K and bounded h, all
primary and secondary non-nulls are rejected at the cutoff c+
r + h/c+
r . Indeed, the primary statistic
equals c+
r + b+
r−z, so its distance above the cutoff is b+
r−z−h/c+
r . This converges to−z > 0
because b+
r →0, c+
r →∞, and h is bounded.
Among the secondary non-nulls, the smallest statistic is attained at a= b+
r . Its distance above
the cutoff is
b+
r
r
h
+ b+
r−z−c+
r−
c+
r
=
b+
r
r−c+
r + b+
r−z−
h
c+
r
,
which tends to infinity by (152) in Lemma 3.4. Thus both gaps are positive for all sufficiently small
r, uniformly when z ranges over a compact subset of (−∞,0) and h remains bounded.
Since every non-null is rejected,
¯
R+
r,z c+
r +
h
c+
r
=
¯
R+
0,r,z c+
r +
h
c+
r
+ q(r+ τ+
r )
p+(c+
r + h/c+
r ).
For every fixed H >0, (152) in Lemma 3.4 gives, uniformly for z∈K and |h|≤H,
c+
r +
h
c+
r
−→∞, r c+
r +
h
c+
r
−→0.
Therefore (161) in Lemma 3.6 directly yields
¯
R+
0,r,z c+
r +
−→q
uniformly for z ∈K and |h|≤H. For the combined non-null contribution, the calibration (150)
gives the exact identity
h
c+
r
q(r+ τ+
r )
p+(c+
r + h/c+
r ) = (1−qπ+
0,r) p+(c+
r )
p+(c+
r + h/c+
r ). (172)
The tail ratio in (172) tends to eh by (305) in Lemma A.2, whereas 1−qπ+
0,r →1−q. Combining
the two contributions gives
¯
R+
r,z(c+
r + h/c+
r ) −→q+ (1−q)eh
¯
R+
,
0,r,z(c+
r + h/c+
r ) −→q. (173)
The first limit is below one for h<0, equals one at zero, and is above one for h>0.
We next exclude earlier crossings. By (152) in Lemma 3.4, uniformly for z ∈K, all non-nulls
are rejected when u+
q ≤c≤c+
r , and (c−rz)/√1−r2 >c for small r. Hence
¯
R+
r,z(c) <qπ+
0,r + q(r+ τ+
r )
p+(c) ≤qπ+
0,r + q(r+ τ+
r )
p+(c+
r ) = 1. (174)
For every fixed h0 >0, (174) and the calibration (150) give, uniformly for z∈K,
¯
sup
R+
r,z(c) ≤qπ+
0,r + (1−qπ+
0,r) p+(c+
r )
u+
q ≤c≤c+
r−h0/c+
p+(c+
r−h0/c+
r )
r
(175)
−→q+ (1−q)e−h0 <1.
Thus Lemma 3.7 applies with
mr(z) = c+
r , wr(z) = 1
c+
r
, d(z) = q, ξ(z) = 1.
50
```

<!-- source-page: 51 -->

### PDF page 51

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
√1−r2
Equations (173) and (175) verify (163) and (164), respectively. Equation (165) therefore gives (170).
Proof of (171). To apply Lemma 3.8, it remains to prove that the derivative of¯
R+
r,z(c+
r + h/c+
r )
with respect to h is positive there. Fix H <∞. Uniformly for z∈K and |h|≤H, put
c= c+
r +
h
c+
r
, u=
c−rz
√1−r2.
Equation (152) in Lemma 3.4 gives c/c+
r →1 and u/c+
r →1 uniformly. Hence (296) in Lemma A.2
gives
λ(u)
u
λ(c)−
= c−
√1−r2 + O{(c+
r )−1}
rz−r2c
=
1−r2 + O{(c+
r )−1}
= OK,H r+ r2c+
1
r +
c+
r
= o(c+
r ).
Thus the hazard difference in (158) is o(c+
r ) uniformly. Applying (158) in Lemma 3.5, differentiating
the fully rejected non-null contribution directly using p′
+(c) =−λ(c)p+(c), and then using (173),
the calibration (150), and (305) in Lemma A.2, gives
∂
∂h
∂
∂h
¯
R+
0,r,z c+
r +
¯
R+
r,z c+
r +
h
c+
r
h
c+
r
∂
−→0,
−→(1−q)eh
.
Since inf|h|≤H(1−q)eh = (1−q)e−H >0, for all sufficiently small r,
inf
z∈K
inf
|h|≤H
∂
∂h
¯
R+
r,z c+
r +
h
c+
r
>0. (176)
The second limit in (173) verifies (166). The derivative bound (176) and continuity of the null
contribution verify the remaining hypotheses of Lemma 3.8. That lemma therefore gives regularity,
and (167) gives (171), uniformly on K.
3.4.3 The regime z∈(0,y+
q )
Lemma 3.12. For every compact K ⊂(0,y+
q ), uniformly for z∈K,
C+
r (z) = z
r
q(r+ τ+
r )
∂h
p+(c+
r + h/c+
r ) −→(1−q)eh
,
+ o(1) (177)
and
D+
r (z) −→qez2/2
. (178)
Moreover, for all sufficiently small r, C+
r (z) is regular for every z∈K.
Proof. Proof of (177). Fix a compact K ⊂(0,y+
q ) and H >0, and put c= z/r+ h. On z ∈K
and |h|≤H, the primary non-null contribution in (153) is nonzero only if
z
c+
r + b+
r−z≥
+ h.
r
51
```

<!-- source-page: 52 -->

### PDF page 52

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
by (152) in Lemma 3.4. Hence
Let δK = infz∈K z>0. Uniformly for z∈K and |h|≤H,
r
z
r
+ h−(c+
r + b+
r−z) = z+ rh−rc+
r−rb+
r + rz
≥δK−rH−rc+
r−rb+
r + rδK −→δK >0
z
c+
r + b+
r−z<
+ h (179)
r
for all sufficiently small r, uniformly for z∈K and |h|≤H, so the primary non-null contribution
is absent.
A secondary non-null is rejected if and only if
a≥βr,z(c) = z+
rh
1 + r
.
Compactness of K ⊂(0,y+
q ) implies that βr,z(c) ∈(b+
r ,y+
q ) for all sufficiently small r, uniformly for
z∈K and |h|≤H. In the formula for¯
R+
2,r,z(c) in Lemma 3.5,
βr,z(c) −→z,
βr,z(c)
r
=
z
r
+
h
1 + r
,
uniformly on K ×[−H,H], so its first factor converges to 1−qez2/2. With x = z/r, (300) in
Lemma A.2 and the identity p+(x+ u)/p+(x+ v) = p(x+ u)/p(x+ v) give
log p+{x+ h/(1 + r)}
p+(x+ h) = log x+ h
x+ h/(1 + r)−x
h
1 + r−h−
1
2
h2
(1 + r)2−h2 + o(1)
= log 1 + hr
(1 + r)x+ h +
zh
h2r(2 + r)
+
1 + r
2(1 + r)2 + o(1)
= zh+ o(1) uniformly on K×[−H,H].
Consequently,
¯
R+
2,r,z(z/r+ h) −→{1−qez2/2}ezh
. (180)
For c= z/r+ h, uniformly for z∈K and |h|≤H, we have c→∞and rc= z+ rh. By uniformity
of (161) in Lemma 3.6,
sup
z∈K
sup
|h|≤H
¯
R+
0,r,z(z/r+ h)−qez2/2 −→0.
Combining this with (180) and the absence of the primary non-null contribution for z ∈K and
|h|≤H gives
¯
R+
r,z(z/r+ h) −→qez2/2 + {1−qez2/2}ezh
,
¯
R+
0,r,z(z/r+ h) −→qez2/2
. (181)
Because qez2/2 <1 uniformly away from one on K, the first limit crosses one strictly at h= 0.
We now verify (164) in Lemma 3.7. For every fixed η>0, we show that
lim sup
r↓0
sup
z∈K
sup
u+
q ≤c≤z/r−η
¯
R+
r,z(c) <1. (182)
Suppose instead that this assertion failed. Then there would be sequences satisfying
rn ↓0, zn ∈K, u+
q ≤cn ≤
zn
rn
−η,
¯
R+
rn,zn(cn) ≥1−o(1).
52
```

<!-- source-page: 53 -->

### PDF page 53

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
After passing to subsequences,
By (153),
1 + rn
zn −→z0, rncn −→x∈[0,z0].
We consider three cases to get a contradiction.
Case (a). If cn = O(1), then, since zn ∈K,
∆n :=
cn−rnzn
1−r2
n
−cn = cn
1
1−r2
n
−1−
rnzn
1−r2
n
= o(1).
Moreover, infnp+(cn) >0. Hence continuity of p+, π+
0,rn
→1, and (154) give
p+(cn + ∆n)
p+(cn) = 1 + o(1),
¯
R+
0,rn,zn(cn) = qπ+
0,rn
p+(cn + ∆n)
p+(cn)
= q+ o(1).
0 ≤¯
R+
rn,zn(cn)−
qrn
=
p+(cn)1{c+
rn
¯
R+
0,rn,zn(cn)
−zn ≥cn}+ qτ+
rn
p+(cn)µ+
rn
rn(cn + zn)
+ b+
rn
,y+
q
≤q(rn + τ+
rn)
= O(rn) = o(1),
p+(cn)
The equality q(rn+τ+
rn)/p+(cn) = O(rn) uses (149). Thus¯
R+
rn,zn(cn) = q+o(1) <1, a contradiction.
Case (b). cn →∞and x<z0. Put dn = (cn + zn)/(1 + rn). Then
dn−cn =
zn−rncn
1 + rn
−→z0−x>0, cn(dn−cn) −→∞.
By (169) in Lemma 3.10 and (296) in Lemma A.2, the secondary non-null contribution satisfies
0 ≤ qτ+
rn
p+(cn)µ+
rn
rn(cn + zn)
1 + rn
,y+
q ≤p+(dn)
p+(cn) = exp−
dn
cn
λ(t) dt ≤e−cn(dn−cn) = o(1).
Equations (168) and (161) in Lemmas 3.9 and 3.6 therefore yield
¯
R+
rn,zn(cn) = qexp xz0−
x2
2 + o(1) ≤qez2
0 /2 + o(1) <1,
again a contradiction.
Case (c). strictly below one. If hn →−∞, then
cn →∞and x= z0. Write hn = cn−zn/rn ≤−η. If hn is bounded, (181) gives a limit
rnhn
dn−cn =−
1 + rn
>0, cn(dn−cn)∼−z0hn −→∞.
The hazard bound (296) in Lemma A.2 gives
p+(dn)
p+(cn) = exp−
dn
cn
λ(t) dt ≤exp{−cn(dn−cn)}−→0.
53
```

<!-- source-page: 54 -->

### PDF page 54

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
Hence (169) makes the secondary non-null contribution o(1), while (168) makes the primary non-null
contribution o(1). Since rncn →x= z0 and zn →z0, (161) gives
¯
R+
0,rn,zn(cn) −→qexp z2
0−
z2
0
2
= qez2
0 /2 <1.
Therefore
¯
R+
rn,zn(cn) =
¯
R+
0,rn,zn(cn) + o(1) −→qez2
0 /2 <1,
again a contradiction.
Since all three cases lead to a contradiction, (182) holds. Apply Lemma 3.7 with
mr(z) = z
, wr(z) = 1, d(z) = qez2/2, ξ(z) = z.
r
Equations (181) and (182) verify (163) and (164), respectively. Therefore (165) yields (177).
Proof of (178). We apply Lemma 3.8. Fix H >0, put
c=
z
r
+ h, βr,z(c) = z+
rh
1 + r
, |h|≤H.
Equation (179) shows that the primary non-null contribution is absent uniformly on this set. Put
u= (c−rz)/√1−r2. The hazard expansion (297) in Lemma A.2 gives
λ(c)−
λ(u)
√1−r2
= o(1)
uniformly for z∈K and |h|≤H. In the secondary log derivative (160), the first term is O(r), while
the same hazard expansion gives
λ(c)−
λ{βr,z(c)/r}
1 + r
= z+ o(1)
uniformly. Combining these two estimates with (180) yields
sup
z∈K
|h|≤H
sup
∂
∂h
¯
R+
r,z(z/r+ h)−z{1−qez2/2}ezh −→0.
Since
inf
z∈K
inf
z{1−qez2/2}ezh >0,
|h|≤H
the derivative is positive on every fixed local window for all sufficiently small r. Equation (177)
verifies (165), and the second limit in (181) verifies (166). Continuity follows from (154). Lemma 3.8
therefore gives regularity, and (167) gives (178), uniformly on K.
3.4.4 The regime z>y+
q
For z>y+
q , define
α+
q (z) = z− z2
−(y+
q )2 ∈(0,z).
54
```

<!-- source-page: 55 -->

### PDF page 55

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
Lemma 3.13. For every compact K ⊂(y+
q ,∞), uniformly for z∈K,
rC+
r (z) −→α+
q (z) (183)
and
x2
2 , (185)
D+
r (z) −→1. (184)
Moreover, for all sufficiently small r, C+
r (z) is regular for every z∈K.
Proof. Proof of (183). Fix a compact K ⊂(y+
q ,∞). Fix z∈K and x∈(0,z). The limits below
also hold uniformly when (x,z) ranges over a compact subset of {(x,z) : z∈K, 0 <x<z}. Then
(152) in Lemma 3.4 implies that the primary non-null is not rejected at c= x/r. For the secondary
non-null contribution, put d= (x/r+ z)/(1 + r). Then
x
d−
=
r
z−x
1 + r
>0,
and (169) together with (296) in Lemma A.2 gives
0 ≤¯
R+
2,r,z(x/r) ≤ p+(d)
p+(x/r) ≤exp{−(x/r)(d−x/r)}−→0.
Equation (161) in Lemma 3.6, applied with c= x/r, gives
¯
R+
r,z(x/r) −→qexp xz−
with the same limit for the null contribution. The equation
qexp xz−
x2
2
= 1
has smaller positive solution α+
q (z). The limit in (185) is below one for x<α+
q (z) and above one
for α+
q (z) <x<z.
We now establish the uniform gap needed to exclude earlier crossings. Fix η>0 uniformly small
enough that
0 <α+
q (z)−η<α+
q (z) + η<z, z∈K.
We claim that
lim sup
r↓0
sup
sup
z∈K
u+
q ≤c≤{α+
q (z)−η}/r
¯
R+
r,z(c) <1. (186)
If (186) failed, there would be sequences
rn ↓0, zn ∈K, u+
q ≤cn ≤
,
¯
R+
rn,zn(cn) ≥1−o(1).
rn
After taking a subsequence,
zn −→z0 ∈K, rncn −→x∈[0,α+
q (z0)−η].
If (cn) is bounded, then p+(cn) is bounded away from zero, (154) gives¯
R+
0,rn,zn(cn) = q+ o(1), and
(153) and (149) give
α+
q (zn)−η
0 ≤¯
R+
rn,zn(cn)−
¯
R+
0,rn,zn(cn) ≤q(rn + τ+
rn)
p+(cn)
55
= o(1).
```

<!-- source-page: 56 -->

### PDF page 56

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
Thus¯
R+
rn,zn(cn) →q<1, a contradiction.
Suppose instead that cn →∞, and define dn = (cn + zn)/(1 + rn). Since
dn−cn =
zn−rncn
1 + rn
−→z0−x≥z0−α+
q (z0) + η>0,
(169) in Lemma 3.10 and (296) in Lemma A.2 give
0 ≤¯
R+
2,rn,zn(cn) ≤exp{−cn(dn−cn)}= o(1).
Equation (168) in Lemma 3.9 gives¯
R+
1,rn,zn(cn) = o(1), and (161) in Lemma 3.6 gives
¯
R+
rn,zn(cn) −→qexp xz0−
x2
2 ≤qexp {α+
q (z0)−η}z0−
{α+
q (z0)−η}2
2 <1,
where the inequality uses x≤α+
q (z0)−η <z0. This is again a contradiction, so (186) holds. In
particular, no crossing occurs at or before {α+
q (z)−η}/r. At c= {α+
q (z)+η}/r, the null contribution
alone is larger than one for all sufficiently small r, uniformly on K. Therefore
α+
q (z)−η<rC+
r (z) <α+
q (z) + η.
Letting η↓0 proves
rC+
r (z) −→α+
q (z)
uniformly on K.
Proof of (184). It remains to prove regularity. Choose η>0 such that, for every z∈K,
0 <α+
q (z)−2η<α+
q (z) + 2η<min{z,y+
q }.
For any x∈[α+
q (z)−η,α+
q (z) + η], uniformly over z∈K,
r{x/r−(c+
r + b+
r−z)}= x−rc+
r−rb+
r + rz>0
by (152) in Lemma 3.4, so the primary non-null contribution is zero. Applying (297) in Lemma A.2
directly to (157) in Lemma 3.5 gives, uniformly for z∈K and x∈[α+
q (z)−η,α+
q (z) + η],
d
¯
log
R+
0,r,z(c)
= r(z−x) + o(r). (187)
c=x/r
dc
Set
c1 = inf
α+
q (z)−η>0, δ=
z∈K
1
2
inf
z∈K[z−α+
q (z)]−η >0.
The null limit (161) in Lemma 3.6 and (187) imply that, for some c0 >0,
inf
z∈K
¯
inf
inf
R+
0,r,z(x/r) ≥c0,
z∈K
x∈[α+
q (z)−η,α+
q (z)+η]
d
inf
x∈[α+
q (z)−η,α+
q (z)+η]
dc
¯
R+
0,r,z(c)
c=x/r
≥c0δr.
(188)
56
```

<!-- source-page: 57 -->

### PDF page 57

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
for all sufficiently small r. For the secondary non-null contribution, put d= (x/r+ z)/(1 + r). Here
rd ∈(b+
r ,y+
q ), x/r ≥c1/r, and d−x/r ≥δ. Thus (160) in Lemma 3.5 and (296) in Lemma A.2
yield
0 ≤¯
R+
2,r,z(x/r) ≤ p+(d)
p+(x/r) ≤e−(x/r)(d−x/r) ≤e−c1δ/r
d
,
¯
R+
dc
2,r,z(c)
c=x/r
= O(r−1e−c1δ/r) = o(r).
Combining this bound with (188),
inf
inf
z∈K
x∈[α+
q (z)−η,α+
q (z)+η]
d
dc
¯
R+
r,z(c)
c=x/r
>0.
Equation (183) gives
α+
q (z)−η
r
<C+
r (z) <
α+
q (z) + η
r
for all sufficiently small r, uniformly for z∈K. Hence Proposition 2.5 proves regularity uniformly
on K.
At the population cutoff, regularity gives¯
R+
r,z{C+
r (z)}= 1. By (183), uniformly for z∈K,
rC+
r (z) −→α+
q (z), inf
z∈K
α+
q (z) >0.
In contrast, (152) in Lemma 3.4 gives
r(c+
r + b+
r−z) = rc+
r + rb+
r−rz−→0
uniformly on K. Hence C+
r (z) >c+
r + b+
r−z for all sufficiently small r, and the indicator in (155)
is zero. Thus the primary non-null contribution vanishes at C+
r (z). With d= {C+
r (z) + z}/(1 + r),
(183) gives
C+
r (z) −→∞, d−C+
r (z) = z−rC+
r (z)
1 + r
−→z−α+
q (z) >0
uniformly on K. Hence Lemma 3.10 and (296) in Lemma A.2 give
0 ≤¯
R+
2,r,z{C+
r (z)}≤exp[−C+
r (z){d−C+
r (z)}] −→0.
It follows that¯
R+
0,r,z{C+
r (z)}→1. By the definition of D+
r (z), uniformly on K,
D+
r (z) =
¯
R+
0,r,z{C+
r (z)}−→1.
3.5 Proofs of Theorem 3.1 and Propositions 3.2 and 3.3
Proof of Theorem 3.1. Choose a compact set
such that
E ⊂R \{0,y+
q }
E{D∗
+(Z)1{Z ∈E}}>ℓ≤(q)−
δ
4.
57
```

<!-- source-page: 58 -->

### PDF page 58

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
The proofs of Lemmas 3.11, 3.12, and 3.13 give, for all sufficiently small r, brackets
Ar(z) <Br(z), z∈E,
8.
and a constant γ >0 such that
sup
z∈E
sup
u+
q ≤c≤Ar(z)
¯
R+
r,z(c) ≤1−γ, inf
z∈E
¯
R+
r,z{Br(z)}≥1 + γ,
sup
sup
z∈E
Ar(z)≤c≤Br(z)
¯
R+
0,r,z(c)−D∗
+(z) ≤
δ
Fix such an r, and put C∗= supz∈EBr(z) <∞. For z∈E, define
EN(z) = max ∥RN−R+
r,z∥∞,[0,1], ∥R0,N−π+
0,rR+
0,r,z∥∞,[0,1]
and
p+(C∗)
t∗=
2q
min γ,
δ
8.
Following the same argument in the proof of Theorem 2.8, Lemma 2.6 gives
sup
P{EN(z) >t∗|Z= z}≤4e−2Nt2
∗
.
z∈E
Onthe complementary event, theempirical andpopulation curves differ byat mostqEN(z)/p+(C∗) ≤
1
2 min{γ,δ/8}throughout [u+
q ,C∗]. The two population brackets and Lemma 2.7 therefore imply
Ar(z) <CN ≤Br(z), FDP ≥D∗
+(z)−
δ
4.
Consequently,
EΩN{FDRΩN(BHq)}= EΩN,Z,ε(FDP)
≥
E
δ
D∗
+(z)−
∗
4 ϕ(z) dz−4e−2Nt2
δ
>ℓ≤(q)−
∗
2−4e−2Nt2
.
3δ
For all sufficiently large N, this gives
EΩN{FDRΩN(BHq)}>ℓ≤(q)−
4.
Therefore some deterministic realization ω satisfies the same inequality. The one-sided analogue
of Lemma 2.9 permits an η>0 for which the perturbed model has a positive definite correlation
matrix and
FDR(η)
ω (BHq) >ℓ≤(q)−δ.
All means and null labels are unchanged by the perturbation. Table 4 gives the pre-perturbation
sign pattern, and (33) shows that every off-diagonal covariance is multiplied by the positive factor
1−η2. Thus the perturbation preserves that sign pattern.
Proof of Proposition 3.2. Since e−(y+
q )2/2 = q, the Mills expansion in Lemma A.2 gives
Φ(y+
q
q )∼
= o(q).
√2πy+
q
Substitute y+
q
= 2 log(1/q) into (141).
Proof of Proposition 3.3. By (143), D∗
+(z) = q for z ≤0 and D∗
+(z) > q for every z > 0. Hence
ℓ≤(q) = E{D∗
+(Z)}>q.
58
```

<!-- source-page: 59 -->

### PDF page 59

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
4 Upper bounds
4.1 Preliminaries
The upper bounds concern the common-factor Gaussian model
Ti = θi + aiZ+ 1−a2
i εi, 1 ≤i≤m, (189)
where Z,ε1,...,εm are i.i.d. standard normal random variables and |ai|≤1. Its covariance matrix
is diagonal plus rank one. Conditional on Z, the coordinates and their corresponding p-values are
independent.
The following conditional leave-one-out bound will be used for both types of tests. Let P1,...,Pm
be conditionally independent given Z, let H0 denote the true-null indices, and apply BH at level q.
For i∈H0, write Fi,z(t) = P(Pi ≤t|Z= z).
Lemma 4.1. For almost every z,
E(FDP |Z= z) ≤ q
mi∈H0
sup
0<t≤q
Fi,z(t)
t (190)
Proof. Let R be the BH rejection count. For i∈H0, let Ri be the rejection count after replacing
Pi by zero; in particular, Ri ≥1. The standard leave-one-out argument [Benjamini and Yekutieli,
2001] starts from the pointwise identity
1{i is rejected}
1{Pi ≤qRi/m}
=
.
R∨1
Ri
In fact, if i is rejected, replacing Pi by any value below, including zero, does not change other
rejections because of the step-up rejection rule for BH. Taking conditional expectations given Z= z
and summing gives, for almost every z,
E(FDP |Z= z) =
E 1{Pi ≤qRi/m}
Ri
Z= z . (191)
i∈H0
Conditional independence implies that Pi and Ri are independent given Z= z. Since 0 <
qRi/m≤q, conditioning gives, for every i∈H0 and almost every z,
E 1{Pi ≤qRi/m}
Ri
Z= z =
q
E Fi,z(qRi/m)
qRi/m Z= z
Fi,z(t)
(192)
sup
0<t≤q
m
≤ q
m
.
t
Summing (192) over i∈H0 proves (190).
4.2 Upper bound for two-sided tests
The common-factor class (189) contains the lower-bound construction in Subsection 2.4. The
following theorem shows that this construction attains the sharp leading constant as q ↓0. All
constants below are universal and all asymptotic statements are uniform over the common-factor
model.
59
```

<!-- source-page: 60 -->

### PDF page 60

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
Theorem 4.2. For ordinary BH applied to the two-sided p-values Pi = p(|Ti|), let H0 = {i: θi = 0},
m0 = |H0|, and π0 = m0/m. Throughout 0 <q≤2Φ(1), let uq be defined by p(uq) = 2Φ(uq) = q.
If m0 = 0, then FDR(BHq) = 0. If m0 > 0, then the following bounds hold uniformly over the
common-factor model.
(a)
1−q
2 +
uq
√2π
FDR(BHq) ≤q 1 + π0
.
(b) There is a universal constant C <∞such that
FDR(BHq) ≤q 1 + π0
2√π
log(1/q) + Cπ0{log(1/q)}1/4
.
4.2.1 Proof of Theorem 4.2 (a)
Proof. If m0 = 0, then V = 0 identically and hence FDR = 0. Assume henceforth that m0 ≥1.
Conditional on Z= z, each Pi is a function of εi alone, or is deterministic when |ai|= 1. Thus the
p-values are conditionally independent, and Lemma 4.1 gives (190).
To average (190) over Z, it remains to control
uq
ϕ(z) sup
−uq
0<t≤q
Fi,z(t)
t
dz
for each true null i. We do this on |z|≤uq; the event |Z|>uq is handled at the end by FDP ≤1.
Fix a true null index i. Put r = |ai|and s = √1−r2, and first suppose s > 0. Conditional on
Z= z, Ti ∼N(aiz,s2). The inequality t= p(u) = 2Φ(u) ≤q holds if and only if u≥uq, and in
this case
Fi,z(p(u)) =∞
u
s−1ϕ{(x−aiz)/s}dx+
∞
s−1ϕ{(x+ aiz)/s}dx.
u
Since s2 = 1−a2
i,
s−1ϕ{(x−aiz)/s}
ϕ(x)
1
=
s
exp−
(x−aiz)2
x2
2s2 +
2
1
=
s
exp
z2
2−
(aix−z)2
2s2.
The second tail is the same calculation with z replaced by−z. Choose η+,η− ∈{−1,1}with
{η+,η−}= {−1,1}so that η+aiz≥0 and η−aiz≤0. For x≥u,
|aix−η+z|≥(ru−|z|)+, |aix−η−z|≥ru+ |z|.
Both right-hand sides are nondecreasing in u, so for u≥uq,
ϕ(z)Fi,z(p(u))
p(u) ≤ϕ(z)
ez2/2
p(u)
s
e−(ruq−|z|)2
+/(2s2) + e−(ruq+|z|)2/(2s2)
∞
u
1
=
2s√2π
e−(ruq−|z|)2
+/(2s2) + e−(ruq+|z|)2/(2s2)
,
ϕ(x) dx
because ∞
u ϕ(x) dx= p(u)/2. Taking the supremum gives
ϕ(z) sup
0<t≤q
Fi,z(t)
t ≤
1
2s√2π
e−(ruq−|z|)2
+/(2s2) + e−(ruq+|z|)2/(2s2)
. (193)
60
```

<!-- source-page: 61 -->

### PDF page 61

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
e−(ruq+z)2/(2s2) dz . (194)
Integrating (193) over |z|≤uq and using symmetry gives
uq
Fi,z(t)
1
ϕ(z) sup
dz≤
0<t≤q
t
−uq
s√2π
uq
e−(ruq−z)2
0
+/(2s2) dz+
uq
0
The two integrals on the right-hand side of (194) are
uq
e−(ruq−z)2
0
+/(2s2) dz=
ruq
0
0
e−y2/(2s2) dy+ (1−r)uq,
uq
e−(ruq+z)2/(2s2) dz=
(1+r)uq
e−y2/(2s2) dy.
ruq
Consequently, writing γr = (1−r)/(1 + r) ∈(0,1],
uq
Fi,z(t)
1
ϕ(z) sup
dz≤
0<t≤q
t
−uq
s√2π
(1+r)uq
0
e−y2/(2s2) dy+ (1−r)uq
= Φ (1 + r)uq
s−
1
2 + (1−r)uq
s√2π
1
uqγr
= Φ(uq/γr)−
2 +
√2π
,
(195)
where the final equality in (195) uses s2 = 1−r2 = (1−r)(1 + r), so (1 + r)/s = 1/γr and
(1−r)/s= γr. The right-hand side of (195) is increasing in γr ∈(0,1]. Its derivative with respect
to γr is
uq
√2π
1−γ−2
r exp{−u2
q/(2γ2
r)} ≥0,
because uq ≥1 and, on putting w= γ−2
r ≥1,
we−u2
qw/2 ≤we−w/2 ≤2/e<1.
Hence (195) is at most
1
uq
1−q
uq
Φ(uq)−
2 +
=
√2π
2 +
. (196)
√2π
When r= 1, the conditional p-value is deterministic. For |z|<uq, it exceeds q, and the boundary
|z|= uq has Lebesgue measure zero; hence (196) remains valid. When r= 0, the conditional null
p-value is uniform and independent of Z; (196) remains valid, although it is not sharp.
Let A= {|Z|≤uq}. Decomposing over A and Ac
,
FDR = E(FDP 1A) + E(FDP 1Ac).
For the first term, integrate (190) over z ∈[−uq,uq] and use (196). For the second term, no
conditional tail bound is needed: since 0 ≤FDP ≤1,
E(FDP 1Ac) ≤P(Ac) = P(|Z|>uq) = 2Φ(uq) = q. (197)
Combining (190), (196), and (197) yields
FDR ≤q+ q
mi∈H0
1−q
2 +
1−q
2 +
uq
√2π
,
uq
√2π
= q 1 + π0
as claimed.
61
```

<!-- source-page: 62 -->

### PDF page 62

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
4.2.2 Proof of Theorem 4.2 (b)
The proof of part (b) has two parts. First we prove a deterministic statement for the rank-weighted
contribution that will arise from the finite BH threshold. We then verify its hypotheses from the
finite threshold by a uniform concentration argument for Poisson-binomial counts, that is, sums of
independent Bernoulli random variables with possibly different success probabilities. Throughout
the proof, C and c denote positive universal constants whose values may change from line to line.
For 0 ≤r<1, define
ρr(u,z) = Φ{(u−rz)/√1−r2}+ Φ{(u+ rz)/√1−r2}
2Φ(u). (198)
For r= 1, set ρ1(u,z) = 1{|z|≥u}/p(u); the convention on the measure-zero boundary |z|= u is
immaterial. For every true null i, this is its conditional two-sided tail ratio:
Fi,z{p(u)}
p(u)
= ρ|ai|(u,z), (199)
because the two Gaussian tails are unchanged when ai is replaced by |ai|. Integrating (199) over
the common factor gives the unconditional normalization: for every true null i and every u>0,
1
ρ|ai|(u,z)ϕ(z) dz=
R
p(u) R
P(Pi ≤p(u))
Fi,z{p(u)}ϕ(z) dz=
p(u) = 1. (200)
The middle equality follows because
Fi,z{p(u)}= P(Pi ≤p(u) |Z= z),
1
2 + (1−r)uq
√1−r2√2π
.
and Z has density ϕ. Hence
Fi,z{p(u)}ϕ(z) dz= E{P(Pi ≤p(u) |Z)}= P(Pi ≤p(u)),
R
which is the tower property. The last equality in (200) uses that Pi is a two-sided null p-value.
We first give a useful bound on ρr(u,z) without restrictions on r.
Lemma 4.3. If uq ≥1 and 0 ≤r<1, then
uq
ϕ(z) sup
−uq
u≥uq
ρr(u,z) dz≤Φ (1 + r)uq
√1−r2−
For r= 1, the integral on the left is zero.
Proof. Assume first that 0 ≤r<1. For ξ∈{−1,1}, using ϕ(t) = (2π)−1/2 exp(−t2/2),
ϕ{(x−ξrz)/√1−r2}
=
=
1
√1−r2 exp−
1
√1−r2 exp
(x−ξrz)2
2(1−r2) +
x2
2
(rx−ξz)2
2(1−r2).
√1−r2 ϕ(x)
z2
2−
The second equality uses the identity
(1−r2)z2
−(rx−ξz)2 = (1−r2)x2
−(x−ξrz)2
=−r2x2 + 2ξrxz−r2z2
.
62
```

<!-- source-page: 63 -->

### PDF page 63

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
dx
If ξz= |z|, then
|rx−ξz|= |rx−|z||≥(rx−|z|)+ ≥(ruq −|z|)+,
while if ξz= −|z|, then
|rx−ξz|= rx+ |z|≥ruq + |z|.
For fixed u≥uq, each conditional tail in the numerator of ρr(u,z) can be written as
Φ{(u−ξrz)/ 1−r2}=
∞
ϕ{(x−ξrz)/√1−r2}
dx.
u
√1−r2
Multiplying the density-ratio identity above by ϕ(z) and using the two lower bounds on |rx−ξz|,
we get, for |z|≤uq,
ϕ(z)ρr(u,z) = 1
p(u) ξ∈{−1,1}
∞
ϕ(x)ϕ(z)ϕ{(x−ξrz)/√1−r2}
u
√1−r2 ϕ(x)
≤
∞
u ϕ(x) dx
1
p(u)
√1−r2√2π
e−(ruq−|z|)2
+/{2(1−r2)}+ e−(ruq+|z|)2/{2(1−r2)}
.
Since p(u) = 2∞
u ϕ(x) dx, and the right side no longer depends on u, taking the supremum over
u≥uq gives
ϕ(z) sup
u≥uq
ρr(u,z) ≤
1
2√1−r2√2π
e−(ruq−|z|)2
+/{2(1−r2)}+ e−(ruq+|z|)2/{2(1−r2)}
.
Integrating this bound over z∈[−uq,uq] and using symmetry reduces the right side to the integral
over 0 ≤z≤uq without the factor 1/2. The first exponential contributes
uq
e−(ruq−z)2
0
+/{2(1−r2)}dz=
ruq
0
e−(ruq−z)2/{2(1−r2)}dz+
uq
1 dz
ruq
=
ruq
e−y2/{2(1−r2)}dy+ (1−r)uq,
0
where the last line uses y= ruq−z in the first integral. The second exponential contributes
uq
0
e−(ruq+z)2/{2(1−r2)}dz=
(1+r)uq
e−y2/{2(1−r2)}dy,
ruq
using y= ruq + z. Therefore
uq
ϕ(z) sup
ρr(u,z) dz
−uq
u≥uq
1
≤
√1−r2√2π
ruq
0
e−y2/{2(1−r2)}dy+
(1+r)uq
ruq
= Φ{(1 + r)uq/ 1−r2}−1
2 + (1−r)uq
√1−r2√2π
,
which is the asserted bound.
When r= 1, the conditional residual variance 1−r2 is zero. Thus a null statistic with |ai|= 1
is Ti = aiZ, so conditional on Z= z it equals ±z and has absolute value |z|. For |z|≤uq,
{u≥uq : |z|≥u}=
∅, |z|<uq,
{uq}, |z|= uq.
(201)
63
e−y2/{2(1−r2)}dy+ (1−r)uq
```

<!-- source-page: 64 -->

### PDF page 64

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
By (201) and p(uq) = q,
sup
ρ1(u,z) = 1{|z|= uq}
u≥uq
q
, |z|≤uq, (202)
uq
1
ϕ(z) sup
ρ1(u,z) dz=
−uq
u≥uq
q {−uq,uq}
ϕ(z) dz= 0. (203)
Changing the convention at |z|= u affects (202) only at z= ±uq, so (203) is unchanged.
Define
Kq = 8 log uq, Lq = Kq + √uq. (204)
The following lemma shows a refined bound on ρr(u,z) for small r.
Lemma 4.4. With Kq and Lq as defined in (204), uniformly for 0 ≤r≤3/5, u≥uq, and |z|≤uq,
ϕ(z)ρr(u,z) ≤C e−(z−ru)2/{2(1−r2)}+ e−(z+ru)2/{2(1−r2)}
. (205)
Moreover, there are universal constants C <∞and q0 >0 such that, whenever q≤q0, if |z|≥Lq
and |z|−ru ≤Kq, then
ϕ(z)ρr(u,z) ≤1 + C(Kq + 1)/uq
2√2π√1−r2 + Cexp{−uq}. (206)
Proof. Since r≤3/5, u≥uq, and |z|≤uq,
2
u−rz≥u−r|z|≥u−ruq ≥(1−r)u≥
Since √1−r2 ≤1, this gives
2
5
u≥
5
uq.
2
u−rz
√1−r2 ≥
uq.
5
Hence the upper Mills bound (308) in Appendix A applies to (u−rz)/√1−r2, while the lower
Mills bound (309) applies to u. These two inequalities give
ϕ(z)Φ{(u−rz)/√1−r2}
2Φ(u) ≤ϕ(z)ϕ{(u−rz)/√1−r2}
√1−r2(u2 + 1)
2ϕ(u)
u(u−rz)
1
√1−r2(u2 + 1)
=
u(u−rz) exp−
z2
(u−rz)2
u2
2−
2(1−r2) +
2
√1−r2(u2 + 1)
=
u(u−rz) exp−
(1−r2)z2 + (u−rz)2
−(1−r2)u2
2(1−r2)
√1−r2(u2 + 1)
=
2√2π
u(u−rz) exp−
(z−ru)2
2(1−r2). (207)
Using a similar argument, we can prove
ϕ(z)Φ{(u+ rz)/√1−r2}
2Φ(u) ≤
2√2π
1
2√2π
1
1
2√2π
√1−r2(u2 + 1)
u(u+ rz) exp−
(z+ ru)2
2(1−r2). (208)
64
```

<!-- source-page: 65 -->

### PDF page 65

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
2
u.
5
For both signs, |z|≤uq ≤u implies
u∓rz≥u−r|z|≥(1−r)u≥
Also √1−r2 ≤1 and u≥uq ≥1. Therefore
max
√1−r2(u2 + 1)
u(u−rz),
√1−r2(u2 + 1)
u(u+ rz) ≤
u2 + 1
(2/5)u2 ≤5.
This bound is uniform over 0 ≤r≤3/5, u≥uq, and |z|≤uq. Substituting it into (207) and (208),
and increasing C, proves (205). If |z|= ru+ d with |d|≤Kq, then the first term in (207)-(208) has
prefactor
√1−r2(u2 + 1)
1
1 + u−2
u{(1−r2)u−rd}=
√1−r2
1−rd/{(1−r2)u}. (209)
Because r≤3/5, one has 1−r2 ≥16/25. Hence, when |d|≤Kq ≤uq/4,
rd
(1−r2)u
≤ (3/5)Kq
15
≤
(16/25)uq
64.
Since (1−x)−1 ≤1 + C|x|for |x|≤15/64, and since u≥uq ≥1,
1 + u−2
1−rd/{(1−r2)u}≤(1 + u−1
q ) 1 + CKq
uq
.
Combining this estimate with (209) gives
√1−r2(u2 + 1)
u{(1−r2)u−rd}=
≤1 + CKq + 1
uq
1
1 + u−2
≤
=
√1−r2
1−rd/{(1−r2)u}
1
√1−r2 1 + CKq + 1
uq
1 + C(Kq + 1)/uq
√1−r2.
Note that
z≥0 : |z+ ru|= |z|+ ru= 2|z|−d≥2Lq−Kq,
z<0 : |z−ru|= |z|+ ru= 2|z|−d≥2Lq−Kq.
Therefore, with the + sign when z≥0 and the−sign when z<0,
exp−
(z±ru)2
2(1−r2) ≤exp−
(2Lq−Kq)2
2(1−r2) ≤exp{−uq}, (210)
because 1−r2 ≤1 and (2Lq−Kq)2/2 ≥uq. The proof is then completed by (207) - (210).
For the next three lemmas, fix 0 < r ≤3/5 and use Kq,Lq from (204). Let Π be a positive
measure of mass at most one on (θ,α) ∈R ×[−1,1], let ε∼N(0,1), and define
Gz(u) = P{|θ+ αz+ 1−α2 ε|≥u}dΠ(θ,α). (211)
65
```

<!-- source-page: 66 -->

### PDF page 66

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
For z and u, write
P{|θ+ αz+ 1−α2 ε|≥u}dΠ(θ,α),
P{|θ+ αz+ 1−α2 ε|≥u}dΠ(θ,α).
Glarge
z (u) =
{|α|≥r/uq}
Gsmall
z (u) =
{|α|<r/uq}
Then
Gz(u) = Glarge
z (u) + Gsmall
z (u).
For each z, let Cz be a finite set satisfying
Cz ⊆ u≥uq : Gz(u) ≥p(u)
2q
, Gz(v) ≤3p(v)
q
∀uq ≤v<u . (212)
Define
Elarge
± (r) = z: ±z∈[Lq,uq], ∃u such that u∈Cz, |z|−ru ≤Kq,
and Glarge
z (u) ≥p(u)/(4q),
(213)
and
Esmall
± (r) = z: ±z∈[Lq,uq], ∃u such that u∈Cz, |z|−ru ≤Kq,
and Gsmall
z (u) ≥p(u)/(4q).
(214)
The next lemma bounds |Elarge
± (r)|.
Lemma 4.5. There are universal constants C <∞and q0 >0 such that, whenever q ≤q0, the
following bound holds uniformly over all positive measures Π on R ×[−1,1] with Π(R ×[−1,1]) ≤1,
and over all families (Cz) satisfying (212):
|Elarge
+ (r)|+ |Elarge
− (r)|≤(1−r)uq + C√uq. (215)
Proof. Set
Yz = Yz(θ,α,e) = θ+ αz+ 1−α2 e,
dν(θ,α,e) = 1
3 dΠ(θ,α)ϕ(e) de.
(216)
Then
ν{|Yz|≥v}=
ν{|α|≥r/uq, |Yz|≥v}=
1
3Gz(v),
1
3Glarge
z (v). (217)
If u∈Cz and uq ≤v<u, then (212) gives
. (218)
ν{|Yz|≥v}≤p(v)
q
If z∈Elarge
+ (r) and u∈Cz is as in (213), then by (217),
ν{|α|≥r/uq, |Yz|≥u}≥p(u)
12q
. (219)
66
```

<!-- source-page: 67 -->

### PDF page 67

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
r
(z1 + z3). (220)
The same result holds with z∈Elarge
− (r) and u∈Cz.
Fix any z1 ∈Elarge
+ (r). Consider z2 ∈Elarge
+ (r) and−z3 ∈Elarge
− (r) with z2 > z1. Choose
v1 ∈Cz1 , v2 ∈Cz2 , and v3 ∈C−z3 as in (213), and put
d2 =
r
uq
(z2−z1), d3 =
Split {|α|≥r/uq, |Yz1 |≥v1}= A+˙
∪A−, where
A+ = {|α|≥r/uq, |Yz1 |≥v1, αYz1 ≥0},
A−
= {|α|≥r/uq, |Yz1 |≥v1, αYz1 <0}.
uq
Then (219) gives
ν(A+) + ν(A−) = ν{|α|≥r/uq, |Yz1 |≥v1}≥p(v1)
.
12q
Moreover,
A+ ⊆{|Yz2 |≥v1 + d2}, A−⊆{|Y−z3 |≥v1 + d3}.
Indeed, on A+,
|Yz2 |= |Yz1 + α(z2−z1)|≥|Yz1 |+ |α|(z2−z1) ≥v1 + d2,
while on A−,
|Y−z3 |= |Yz1−α(z1 + z3)|≥|Yz1 |+ |α|(z1 + z3) ≥v1 + d3.
Let
Elarge
− (r) = {−z: z∈Elarge
− (r)}.
It is enough to bound |Elarge
+ (r)|+ |Elarge
− (r)|. If Elarge
+ (r) ∪Elarge
− (r) is empty, there is nothing to
prove. Otherwise choose z1 ∈Elarge
+ (r) ∪Elarge
− (r) arbitrarily close to
inf{z: z∈Elarge
+ (r) ∪Elarge
− (r)}.
Choose v1 ∈Cz1 if z1 ∈Elarge
+ (r), and v1 ∈C−z1 if z1 ∈Elarge
− (r). In the first case, (213) gives
z1 ∈[Lq,uq], |z1−rv1|≤Kq.
In the second case,−z1 ∈Elarge
− (r), so the same definition gives
z1 = |−z1|∈[Lq,uq], |z1−rv1|≤Kq.
Thus, in either case,
rv1
z1−Kq
z1 ≥Lq, |z1−rv1|≤Kq =⇒
Lq−Kq
. (221)
uq
≥
≥
uq
uq
Set
2Kq + 2r2
4uq
Bq =
+
. (222)
1−r2/uq
Lq−Kq
We claim that, to the right of z1 + Bq, the two reflected sets cannot overlap:
Elarge
+ (r) ∩(z1 + Bq,uq] ∩ Elarge
− (r) ∩(z1 + Bq,uq] = ∅. (223)
67
```

<!-- source-page: 68 -->

### PDF page 68

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
Therefore
Since z2,z3 >z1 + Bq,
Therefore
r
.
We prove (223) by contradiction. Assume (223) fails. Then there exist
z2 ∈Elarge
+ (r), z3 ∈Elarge
− (r), z2,z3 >z1 + Bq. (224)
If z1 ∈Elarge
+ (r), assume (224) and choose v2 ∈Cz2 and v3 ∈C−z3 . By (213),
|z1−rv1|≤Kq, |z2−rv2|≤Kq, |z3−rv3|≤Kq,
where the last inequality uses−z3 ∈Elarge
− (r), so that |−z3|= z3. Hence
r(v2−v1) = (rv2−z2) + (z2−z1) + (z1−rv1) ≥z2−z1−2Kq,
r(v3−v1) = (rv3−z3) + (z3−z1) + (z1−rv1) ≥z3−z1−2Kq.
v2−v1 ≥
z2−z1−2Kq
r
z3−z1−2Kq
, v3−v1 ≥
. (225)
z2−z1, z3−z1 >
2Kq + 2r2
1−r2/uq
(z2−z1) 1−
r2
uq
>2Kq,
(z3−z1) 1−
r2
uq
>2Kq + 2r2 ≥2Kq +
Equivalently,
z2−z1−2Kq
r
r
>
(z2−z1),
uq
r
Combining these inequalities with (225) gives
r
v2−v1 >
(z2−z1), v3−v1 >
uq
that is,
v1 + d2 <v2, v1 + d3 <v3. (226)
Also, (221) gives
rv1
uq
≥
Lq−Kq
uq
.
Since z2,z3 >z1 + Bq and the second term in Bq is 4uq/(Lq−Kq),
z2−z1 >
4uq
Lq−Kq
, z1 + z3 >z3−z1 >
4uq
Lq−Kq
and, using z1 ≤uq,
2r2z1
.
z3−z1−2Kq
uq
r
r
>
uq
(z1 + z3),
(z1 + z3).
uq
.
Consequently
rv1
uq
min{z2−z1,z1 + z3}≥Lq−Kq
uq
min{z2−z1,z1 + z3}>4
68
```

<!-- source-page: 69 -->

### PDF page 69

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
and hence, by (220),
12q
4
min{d2,d3}>
v1. (227)
The ordering in (226), together with v1 ≥uq and d2,d3 ≥0, gives
uq ≤v1 + d2 <v2, uq ≤v1 + d3 <v3. (228)
Thus v2 ∈Cz2 , v3 ∈C−z3 , so (218) applies with (z,u,v) = (z2,v2,v1 +d2) and (z,u,v) = (−z3,v3,v1 +
d3). Hence
p(v1)
≤ν(A+) + ν(A−)
≤ν{|Yz2 |≥v1 + d2}+ ν{|Y−z3 |≥v1 + d3}
≤p(v1 + d2) + p(v1 + d3)
, by (218).
q
Multiplying by q and substituting the definitions of d2 and d3 in (220) imply
p(v1)
12 ≤p{v1 + (r/uq)(z2−z1)}+ p{v1 + (r/uq)(z1 + z3)}. (229)
For u>0 and d≥0, p= 2Φ and the normal hazard λ(t) = ϕ(t)/Φ(t) give
p(u+ d)
p(u)
Φ(u+ d)
=
Φ(u) = exp−
u+d
u
λ(t) dt
≤exp−
u+d
u
t dt = exp{−ud−d2/2}≤e−ud
,
(230)
where the inequality uses λ(t) >t for t>0, as stated in (296) of Appendix Lemma A.2. Thus the
right side of (229) is at most
p(v1)
48 + p(v1)
48 < p(v1)
12 ,
which is impossible. Equivalently, the tail calculation gives
min{z2−z1,z1 + z3}= min{d2,d3}≤ 4
v1. (231)
This contradicts (227). By the same argument with signs reversed, if−z1,−z3 ∈Elarge
− (r), z2 ∈
Elarge
+ (r), and z3 >z1, then, for v1 ∈C−z1 chosen as in (213),
r
uq
min{z3−z1,z1 + z2}≤ 4
v1. (232)
If z1 ∈Elarge
− (r), the same contradiction uses (232). Together with the preceding case z1 ∈Elarge
+ (r),
this proves (223).
Put
r
uq
a= inf{z: z∈Elarge
+ (r) ∪Elarge
− (r)}.
Since z1 can be chosen arbitrarily close to a, (223) gives, after letting z1 ↓a,
Elarge
+ (r) ∩(a+ Bq,uq] ∩ Elarge
− (r) ∩(a+ Bq,uq] = ∅.
69
```

<!-- source-page: 70 -->

### PDF page 70

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
By (213) and (212), both sets are contained in
Iq = [max{Lq,ruq−Kq},uq].
Indeed, for any signed point s∈Elarge
+ (r) ∪Elarge
− (r), and for its associated u∈Cs,
|s|∈[Lq,uq], |s|≥ru−Kq ≥ruq−Kq.
Recall the definition of Bq in (222). Set
J0 = Iq ∩[a,a+ Bq], J1 = Iq ∩(a+ Bq,uq].
Since both reflected sets are contained in Iq and have no points below a, their total length decomposes
as
|Elarge
+ (r)|+ |Elarge
− (r)|= |Elarge
+ (r) ∩J0|+ |Elarge
− (r) ∩J0|
+ |Elarge
+ (r) ∩J1|+ |Elarge
− (r) ∩J1|.
On the set J0, each set contributes at most |J0|with
|J0|≤min{Bq,|Iq|}.
On J1, the disjointness above gives
Elarge
+ (r) ∩J1 ∩ Elarge
− (r) ∩J1 = ∅,
so
|Elarge
+ (r) ∩J1|+ |Elarge
− (r) ∩J1|= |Elarge
+ (r) ∪Elarge
− (r) ∩J1|≤|J1|.
Since Iq = [max{Lq,ruq−Kq},uq], the containment of Elarge
+ (r) and Elarge
− (r) in Iq gives a ≥
max{Lq,ruq−Kq}. Hence
|J1|= |Iq ∩(a+ Bq,uq]|
≤(uq−a−Bq)+
≤(uq−max{Lq,ruq−Kq}−Bq)+ = (|Iq|−Bq)+.
Therefore
|Elarge
+ (r)|+ |Elarge
− (r)|= |Elarge
+ (r)|+ |Elarge
− (r)|
≤2|J0|+ |Elarge
+ (r) ∪Elarge
− (r) ∩J1|
≤2 min{Bq,|Iq|}+ (|Iq|−Bq)+
≤Bq + |Iq|
= Bq + uq−max{Lq,ruq−Kq}
≤(1−r)uq + Kq + Bq.
After decreasing q0 if necessary, 1−r2/uq ≥1/2. Thus (222) gives
Bq ≤2(2Kq + 2r2) + 4√uq ≤C{Kq + √uq + 1}.
Consequently, since Kq = 8 log uq,
Kq + Bq ≤C{Kq + √uq + 1}≤C√uq,
which proves (215).
70
```

<!-- source-page: 71 -->

### PDF page 71

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
The next lemma bounds |Esmall
± (r)|.
Lemma 4.6. With Esmall
± (r) defined in (214), there are universal constants C < ∞and q0 > 0
such that, whenever q≤q0,
|Esmall
+ (r)|+ |Esmall
− (r)|≤C(Kq + 1) ≤C√uq (233)
uniformly over all positive measures Π on R ×[−1,1] such that Π(R ×[−1,1]) ≤1, and over all
families (Cz) satisfying (212).
Proof. Put
r
b=
, η= Π{(θ,α) : |α|<b}.
uq
For each z and u, put
Qz(u) = Gsmall
z (u)
1
=
p(u)
p(u) {|α|<b}
P{|θ+ αz+ 1−α2 ε|≥u}dΠ(θ,α), (234)
where ε∼N(0,1). If z ∈Esmall
+ (r) ∪Esmall
− (r) and u∈Cz is one of the values appearing in (214),
then
Qz(u) ≥
1
. (235)
4q
If Esmall
+ (r) ∪Esmall
− (r) is empty, there is nothing to prove. Otherwise choose z1 ∈Esmall
+ (r) ∪
Esmall
− (r) so that |z1|is arbitrarily close to
inf{|z|: z∈Esmall
+ (r) ∪Esmall
− (r)}.
Choose v1 ∈Cz1 as in (214). Since Qz1 (v1) ≥1/(4q) >0, necessarily η>0; if η= 0, then Qz ≡0
for every z. By (214), |z1|≤uq and |z1|−rv1 ≤Kq. Therefore
rv1 ≤|z1|+ Kq ≤uq + Kq, and hence bv1 ≤1 + Kq/uq. (236)
Define
H1 = log Qz1 (v1)√1−b2
2η
.
H1 ≥log √1−b2
8q
For q0 small enough, uq ≥2. Since 0 ≤r≤1, this gives
b=
r
uq
≤
1
2, 1−b2 ≥
1
Therefore, using q= p(uq) ≤e−u2
q/2 from (302),
H1 ≥log 1
16q
≥
u2
q
2−log 16 ≥
after decreasing q0, if necessary. Moreover, by (236),
9b2v2
1
1−b2 ≤9(1 + Kq/uq)2
1−u−2
q
71
Using (235) and η≤1,
.
2.
u2
q
3 ≥4, (237)
≤C.
```

<!-- source-page: 72 -->

### PDF page 72

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
uq
Since H1 ≥u2
q/3, decreasing q0 once more makes this last constant at most H1. Hence
H1 = log Qz1 (v1)√1−b2
2η
≥4,
9b2v2
1
1−b2 ≤H1. (238)
We will show the following result at the end of the proof:
∃v≥v1 : Qz1 (v) ≥
3e10uq
q
, 0 ≤v−v1 ≤Cv1
. (239)
Now we prove (233) under (239). For any |z′|≤uq, put
∆ = b|z
′
−z1|≤2r. (240)
Fix a component (θ,α) with |α|< b, and use the same residual ε to form the two conditional
statistics at z1 and at z′:
Yz1
= θ+ αz1 + 1−α2 ε, Yz′ = θ+ αz
′+ 1−α2 ε.
Then
−z1|= ∆,
|Yz′−Yz1 |= |α||z
′
−z1|≤b|z
′
and hence
{|Yz1 |≥v}⊆{|Yz′|≥v−∆}.
For this fixed (θ,α), the inclusion gives
Pε{|Yz′|≥v−∆}≥Pε{|Yz1 |≥v}.
Integrating the last inequality with respect to Π over the small-coefficient set {|α|<b}gives, by
the definition of Gsmall
z ,
Gsmall
z′ (v−∆) =
{|α|<b}
≥
{|α|<b}
Pε{|Yz′|≥v−∆}dΠ(θ,α)
Pε{|Yz1 |≥v}dΠ(θ,α) = Gsmall
z1 (v).
Dividing by p(v−∆) and using Gsmall
z1 (v) = Qz1 (v)p(v) gives
Qz′(v−∆) ≥Qz1 (v) p(v)
p(v−∆). (241)
Since p= 2Φ, p′(t)/p(t) =−λ(t), where λ(t) = ϕ(t)/Φ(t). Also, by (240), r≤3/5, and v≥v1 ≥uq,
v−∆ ≥v1−∆ ≥uq−2r≥uq−
6
5 >0
after decreasing q0, if necessary. Thus the interval [v−∆,v] lies in (0,∞), and
p(v)
p(v−∆) = exp−
v
v−∆
λ(t) dt .
By (296) of Lemma A.2, for v−∆ ≤t≤v,
λ(t) ≤t+
1
t ≤v+
72
1
v−∆.
```

<!-- source-page: 73 -->

### PDF page 73

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
Therefore
By (214),
Also, (239) and (236) give
p(v)
p(v−∆) ≥exp−∆ v+
1
v−∆. (242)
rv1 ≤|z1|+ Kq ≤uq + Kq.
r(v−v1) ≤Crv1
uq
≤C 1 +
Kq
uq
= O(1).
Therefore
rv= rv1 + r(v−v1) ≤uq + Kq + O(1).
Since ∆ ≤2r and v−∆ ≥uq−2r, the exponent in (242) satisfies
∆ v+
1
v−∆ ≤2rv+
2r
uq−2r
≤2uq + 2Kq + O(1) ≤3uq,
after decreasing q0, if necessary, where the last step uses Kq = o(uq) from (204). Combining (241),
(239), and (242),
Qz′(v−∆) ≥Qz1 (v) p(v)
p(v−∆)
3e10uq
≥
exp−∆ v+
3e7uq
1
v−∆
3
≥
e−3uq =
>
.
q
q
Hence
. (243)
q
3e10uq
q
Qz′(v−∆) >
3
q
If v−∆ <uq, then
v1 ≤v<uq + ∆ ≤uq + 2r. Since r≤3/5, (300) in Lemma A.2 gives, uniformly over 0 ≤h≤2r,
log p(uq + h)
p(uq)
=−uqh−
≥−2ruq−2r2
6
≥−
uq−
5
h2
2 + log uq
uq + h + o(1)
−log 1 +
2r
uq
18
25−log 1 + 6
5uq
+ o(1)
+ o(1)
≥−2uq,
(244)
after decreasing q0, if necessary. The last step uses uq →∞as q↓0, and the o(1) term is uniform
over 0 ≤h≤2r≤6/5. Taking h= 2r and using (244) together with the monotonicity of p,
p(v) ≥p(uq + 2r) ≥p(uq)e−2uq = qe−2uq
.
73
```

<!-- source-page: 74 -->

### PDF page 74

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
e2uq
Because Gsmall
z1 (v) ≤Π(R ×[−1,1]) ≤1,
Qz1 (v) = Gsmall
z1 (v)
p(v) ≤
1
p(v) ≤
This contradicts (239), which gives Qz1 (v) ≥3e10uq/q. Hence
q
.
v−∆ ≥uq. (245)
We next show
Cz′∩(v−∆,∞) = ∅. (246)
Suppose, to the contrary, that u′∈Cz′ and u′>v−∆. Since (245) holds, the defining upper-tail
condition in (212), applied with w= v−∆ <u′, gives
Gz′(v−∆) ≤3p(v−∆)
.
q
On the other hand, (243) gives
Gsmall
z′ (v−∆) = p(v−∆)Qz′(v−∆) >3p(v−∆)
q
,
and Gz′(v−∆) ≥Gsmall
z′ (v−∆). This is a contradiction. Therefore every u′∈Cz′ satisfies
u
′≤v−∆ ≤v. (247)
Therefore, (247) is proved.
Now let z′∈Esmall
+ (r) ∪Esmall
− (r). By (214), there exists u′∈Cz′ such that
|z
′|−ru
′ ≤Kq.
Together with (247), this gives
|z
′|≤ru
′+ Kq ≤rv+ Kq ≤|z1|+ 2Kq + C. Here the last inequality follows from
rv= rv1 + r(v−v1) ≤|z1|+ Kq + C,
using |z1|−rv1 ≤Kq from (214) and the bound r(v−v1) ≤C proved above.
Let
a= inf{|z|: z∈Esmall
+ (r) ∪Esmall
− (r)}.
The point z1 was chosen with |z1|arbitrarily close to a. Thus (248) shows that
{|z|: z∈Esmall
+ (r) ∪Esmall
− (r)}⊆[a,a+ 2Kq + C].
(248)
By (214),
Esmall
+ (r) ⊆[Lq,uq], Esmall
− (r) ⊆[−uq,−Lq].
On Esmall
+ (r), the map z→|z|is the identity. On Esmall
− (r), it is the reflection z→−z. Thus,
|Esmall
± (r)|= {|z|: z∈Esmall
± (r)}.
74
```

<!-- source-page: 75 -->

### PDF page 75

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
As a result,
|Esmall
+ (r)|+ |Esmall
− (r)|≤2(2Kq + C) ≤C(Kq + 1).
This proves (233).
Proof of (239). Put
.
1
R= 12e10uq, H1 = log Qz1 (v1)√1−b2
2η
The choice of v1 in (214), together with (235), gives
Qz1 (v1) ≥
.
4q
Also, (237) gives H1 ≥u2
q/3. Thus it is enough to find v≥v1 such that
Qz1 (v) ≥RQz1 (v1), v−v1 ≤Cv1
uq
.
For z∈R and x≥0, define
κz(x) =
{|α|<b}
By definition of Qz in (234),
ϕx−(θ+αz)
√1−α2 + ϕx+(θ+αz)
√1−α2
2ϕ(x)√1−α2 dΠ(θ,α).
Qz1 (u) =∞
u 2ϕ(x)κz1 (x) dx
∞
u 2ϕ(x) dx
.
λ(x) = ϕ(x)/Φ(x).
1
2Qz1 (x). (249)
v1
2 Qz1 (x).
Using straightforward algebra,
Q′
z1 (x) = λ(x){Qz1 (x)−κz1 (x)}, Define
˜
v= inf x≥v1 : Qz1 (x) ≥RQz1 (v1) or κz1 (x) ≥
Before˜
v, we have κz1 (x) <Qz1 (x)/2, and therefore
Q′
z1 (x) ≥
1
λ(x)Qz1 (x) ≥
2
x
2 Qz1 (x) ≥
Thus
log Qz1
′(x) = Q′
z1 (x)
Qz1 (x) ≥
2.
Let T= v1 + 2 log R/v1. If˜v>T, then (log Qz1 )′(x) ≥v1/2 on [v1,T], so
log Qz1 (T)
Qz1 (v1)
=
v1
T
(log Qz1 )′(x) dx≥
v1
2 (T−v1) = log R.
Thus Qz1 (T) ≥RQz1 (v1), contradicting T <˜
v in (249). Hence
v≤v1 + 2 log R
˜
v1. (250)
75
v1
```

<!-- source-page: 76 -->

### PDF page 76

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
Continuity of Qz1 and κz1 ensures that at least one condition in (249) holds at˜
v.
Now we consider two cases depending on which inequality is binding in (249). If Qz1 (˜
v) ≥
RQz1 (v1), take v= ˜v. Since v1 ≥uq by (212),
log R
≤Cuq
v1
,
v1
≤Cv1
uq
Together with (250), this gives
˜
v≤v1 + Cuq
v1
≤v1 1 + C
uq
. (251)
Then (239) holds due to (251).
It remains to consider the case κz1 (˜
v) ≥Qz1 (˜
v)/2. Since Qz1 is increasing on [v1,˜
v], this gives
κz1 (˜v) ≥Qz1 (v1)/2. We will show that (239) is satisfied with
˜
v
v= ˜v+ 72
. (252)
uq
For z∈R and x≥0, define
κz(x) = exp b2x2
2(1−b2) κz(x). (253)
For a fixed pair (θ,α) with |α|<b, the corresponding integrand in κz1 (x) is
1
2ϕ(x)√1−α2 ϕ x−(θ+ αz1)
√1−α2 + ϕ x+ (θ+ αz1)
√1−α2
1
=
2√1−α2 exp−
{x−(θ+ αz1)}2
x2
2(1−α2) +
2
+ exp−
{x+ (θ+ αz1)}2
x2
2(1−α2) +
2
1
=
√1−α2 exp−
α2x2
(θ+ αz1)2
2(1−α2)−
2(1−α2) cosh (θ+ αz1)x
1−α2.
Multiplying by the factor in (253), the corresponding integrand in κz1 (x) is denoted by fθ,α(x),
where
fθ,α(x) = 1
√1−α2 exp−
(θ+ αz1)2
2(1−α2) exp
b2
2(1−b2)−
α2
2(1−α2) x2
(254)
×cosh (θ+ αz1)x
1−α2.
The first two factors are positive and independent of x. The coefficient of x2 in the second term is
b2
α2
b2
−α2
a=
2(1−b2)−
=
2(1−α2)
2(1−b2)(1−α2) ≥0,
because |α|<b. Thus, taking logarithms in (254) and dropping the additive constant independent
of x, the logarithm of the integrand has the form
ax2 + log cosh(cx), c=
76
θ+ αz1
1−α2.
```

<!-- source-page: 77 -->

### PDF page 77

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
On [0,∞),
fθ,α(y) dΠ(θ,α)
1−t
d
dx{ax2 + log cosh(cx)}= 2ax+ ctanh(cx)
= 2ax+ |c|tanh(|c|x) ≥0,
d2
dx2 {ax2 + log cosh(cx)}= 2a+ c2 sech2(cx) ≥0.
Thus fθ,α is log-convex.
To pass from each integrand to the mixture, fix 0 ≤t≤1 and x,y≥0. Log-convexity gives
fθ,α{tx+ (1−t)y}≤fθ,α(x)tfθ,α(y)1−t
.
After integrating over {|α|<b}, Hölder’s inequality gives
κz1 {tx+ (1−t)y}≤
fθ,α(x)tfθ,α(y)1−t dΠ(θ,α)
{|α|<b}
≤
{|α|<b}
fθ,α(x) dΠ(θ,α)
t
{|α|<b}
= κz1 (x)tκz1 (y)1−t
.
Hence κz1 is log-convex. Equivalently,
x→log κz1 (x) + b2x2
2(1−b2) is convex on [0,∞). (255)
Fix M <∞and restrict 0 ≤x≤M. From (254), for a constant CM <∞,
0 ≤fθ,α(x) ≤CM exp−
The last inequality follows from
(θ+ αz1)2
−
2(1−α2) +
M|θ+ αz1|
1−α2
Differentiating the integrand gives
d
dx
fθ,α(x) = fθ,α(x) 2 b2
2(1−b2)−
(θ+ αz1)2
2(1−α2) +
M|θ+ αz1|
1−α2 ≤CM. (256)
α2
2(1−α2) x+
θ+ αz1
1−α2 tanh (θ+ αz1)x
1−α2.
The bracketed factor is controlled by 1 + |θ+ αz1|. Indeed, on 0 ≤x≤M,
2 b2
α2
2(1−b2)−
2(1−α2) x+
θ+ αz1
1−α2 tanh (θ+ αz1)x
1−α2 ≤CM{1 + |θ+ αz1|},
because |tanh |≤1, 1−α2 ≥1−b2, and |α|<b. Combining this with (256) gives
d
dx
fθ,α(x) ≤CM{1 + |θ+ αz1|}exp−
(θ+ αz1)2
M|θ+ αz1|
2(1−α2) +
1−α2.
=−
{|θ+ αz1|−M}2
2(1−α2) +
M2
2(1−α2) ≤
M2
2(1−b2).
77
```

<!-- source-page: 78 -->

### PDF page 78

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
Moreover,
{1 + |θ+ αz1|}exp−
(θ+ αz1)2
M|θ+ αz1|
2(1−α2) +
1−α2
= {1 + |θ+ αz1|}exp−
{|θ+ αz1|−M}2
2(1−α2) +
uniformly in (θ,α) with |α|<b, because 1−α2 ∈[1−b2
,1]. Therefore
M2
2(1−α2) ≤CM,
0≤x≤M
sup
d
dx
fθ,α(x) ≤CM.
Thus, on each compact interval, both fθ,α and dfθ,α/dx are dominated by an integrable bound
with respect to the finite measure Π. Hence κz1 , and therefore κz1 , is differentiable on [0,∞).
When x= 0,
κz1 (0) =
{|α|<b}
≤
{|α|<b}
Together with κz1 (˜v) ≥Qz1 (v1)/2, this gives
ϕ θ+αz1
√1−α2
ϕ(0)√1−α2 dΠ(θ,α)
1
√1−α2 dΠ(θ,α) ≤ η
√1−b2.
κz1 (˜v)
κz1 (0) ≥Qz1 (v1)√1−b2
2η
= eH1
,
by the definition of H1. By (255), the derivative at˜
v is at least the secant slope from 0 to˜
v:
d
dx log κz1 (x) + b2x2
2(1−b2) x=˜v
≥log κz1 (˜v)−log κz1 (0) + b2˜
v2/{2(1−b2)}
˜
v
≥
H1
˜
v
.
The derivative of the convex function in (255) is nondecreasing.
By (251), (236), and (237), we have˜
v≤v1 + Cuq/v1, bv1 ≤1 + Kq/uq, and H1 ≥u2
q/3. Since
v1 ≥uq, the first two bounds imply
b˜
v≤bv1 1 + C
uq
≤ 1 +
Kq
uq
1 + C
uq
≤2
after decreasing q0, if necessary. Also, if˜
v ≤x≤˜
v+ 72˜v/uq + 1, then x≤2˜
v. Therefore, using
b˜
v≤2 and b≤u−1
q ,
b2x˜
v
2b2˜
v2
1−b2 ≤
1−b2 ≤C.
Because H1 ≥u2
q/3, decreasing q0 once more makes this constant at most H1/2. Thus,
b2x˜
v
1−b2 ≤
H1
2
˜
v≤x≤˜
v+ 72
˜
v
uq
+ 1.
(log κz1 )′(x) ≥
H1
˜
v−
b2x
1−b2 ≥
H1
78
Hence, on this interval,
. (257)
2˜v
```

<!-- source-page: 79 -->

### PDF page 79

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
For v defined in (252),
log κz1 (v)
κz1 (˜v)
H1
dx
2˜v
36H1
uq
.
36H1
uq
v
=
˜
v
H1
2˜v(v−
(log κz1 )′(x) dx≥
v
˜
v
v) = H1
˜
v
˜
=
72
=
2˜v
uq
Thus,
κz1 (v) ≥κz1 (˜v) exp 36H1
uq
Since H1 ≥u2
q/3, after decreasing q0, if necessary,
≥Qz1 (v1)
2 exp
. (258)
1−e−1
2 exp
36H1
uq
≥
1−e−1
2
e12uq ≥12e10uq = R. (259)
Also, v≥˜
v≥v1 ≥uq, so v−1 ≤1 after decreasing q0, if necessary. By (252),
[v,v+ v−1] ⊆˜
v,˜
v+ 72
˜
v
uq
+ 1.
The lower bound (257) therefore gives
(log κz1 )′(x) ≥0, v≤x≤v+ v−1
,
and hence κz1 is nondecreasing on [v,v+ v−1]. By the definition of Qz1 ,
Qz1 (v) ≥
v+v−1
v 2ϕ(x)κz1 (x) dx
2Φ(v)
≥κz1 (v)Φ(v)−Φ(v+ v−1)
Φ(v)
Moreover, by (296) of Lemma A.2,
Φ(v+ v−1)
Φ(v) = exp−
v+v−1
v
λ(t) dt ≤exp−
v+v−1
v
t dt ≤e−1
. (260)
Therefore
Qz1 (v) ≥(1−e−1)κz1 (v) ≥RQz1 (v1),
where the first inequality uses (260), and the second uses (258) and (259). Finally, by (252) and
(251),
v−v1 = (˜v−v1) + 72
≤Cuq
v1
˜
v
uq
+ 72 v1
uq
1 + C
uq
.
Since v1 ≥uq from v1 ∈Cz1 and (212),
uq
v1
≤
v1
uq
, 72 v1
uq
1 + C
uq
79
≤Cv1
uq
,
```

<!-- source-page: 80 -->

### PDF page 80

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
after increasing C and decreasing q0, if necessary. Therefore
v−v1 ≤Cv1
uq
.
Thus v defined in (252) satisfies (239).
The following lemma is the deterministic input needed for the good-event part of the finite BH
proof.
Lemma 4.7. There are universal constants C <∞and q0 >0 with the following property. Let Π,
ε, and Gz be as in (211). Let m≥1 and J ≥2. Define
tk =
qk
m
, uk = p−1(tk). (261)
For each z, let wk(z), J <k≤m, be nonnegative measurable weights satisfying
wk(z) ≤1.
k>J
and
k
2j
Gz(uk) ≥
, Gz(uj) ≤
2m
m (j >k) if wk(z) >0. Then, whenever q≤q0, uniformly over m,J,Π, the weights (wk(z)), and 0 ≤r≤1,
uq
ϕ(z)
uq
wk(z)ρr(uk,z) dz≤
+ C√uq.
−uq
k>J
2√2π
(262)
Proof of Lemma 4.7. For each z, put
Cz = {uk : J <k≤m, wk(z) >0}.
If uk ∈Cz, then the first condition in (262) gives
Gz(uk) ≥
k
2m
=
p(uk)
2q
. (263)
For uq ≤v<uk, let j= ⌈mp(v)/q⌉. Then j >k, uj ≤v, and by monotonicity of Gz,
Gz(v) ≤Gz(uj) ≤
2j
m
≤2 1 +
1
J
p(v)
q
≤3p(v)
q
,
where J ≥2. Thus Cz satisfies (212). Also, since the weights are nonnegative and sum to at most
one,
wk(z)ρr(uk,z) ≤sup
ρr(u,z),
k>J
u∈Cz
with the right side interpreted as zero when Cz is empty. It remains to prove
uq
uq
ϕ(z) sup
ρr(u,z) dz≤
+ C√uq. (264)
−uq
u∈Cz
2√2π
If r= 1, then Lemma 4.3 gives
uq
ϕ(z) sup
−uq
u∈Cz
ρ1(u,z) dz≤
uq
−uq
ϕ(z) sup
u≥uq
ρ1(u,z) dz= 0.
80
```

<!-- source-page: 81 -->

### PDF page 81

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
ρr(u,z) dz
ρr(u,z) dz.
This proves the desired bound in this case.
Next suppose 3/5 ≤r<1. Since (1−r)/√1−r2 ≤1/2, Lemma 4.3 gives
uq
1
uq
uq
ϕ(z) sup
ρr(u,z) dz≤
2 +
≤
+ C√uq. (265)
−uq
u≥uq
2√2π
2√2π
This upper-bounds the smaller supremum over Cz and proves the desired bound in this range.
It remains to consider 0 ≤r<3/5. For r= 0, the integral is at most 1−q, which is bounded by
the displayed right side after increasing C. Hence assume 0 <r<3/5. Use Lq,Kq defined in (204).
When q is sufficiently small, (204) implies Lq <uq. We will consider the following decomposition of
(264):
uq
−uq
ϕ(z) sup
u∈Cz
ρr(u,z) dz
≤
|z|<Lq
ϕ(z) sup
u∈Cz
ρr(u,z) dz
+
Lq≤|z|≤uq
ϕ(z) sup
u∈Cz:
|z|−ru >Kq
(266)
+
Lq≤|z|≤uq
ϕ(z) sup
u∈Cz:
|z|−ru ≤Kq
All empty suprema in (266) are interpreted as zero.
By construction, every u∈Cz satisfies u≥uq. When |z|<Lq, Lemma 4.4 gives
ϕ(z)ρr(u,z) ≤C e−(z−ru)2/{2(1−r2)}+ e−(z+ru)2/{2(1−r2)} ≤C
uniformly over u∈Cz. Taking the supremum over Cz, with value zero when Cz is empty, and then
integrating over a set of length at most 2Lq gives
ϕ(z) sup
ρr(u,z) dz≤CLq. (267)
|z|<Lq
u∈Cz
On Lq ≤|z|≤uq, if u∈Cz and |z|−ru >Kq, then
min{|z−ru|,|z+ ru|}= |z|−ru >Kq.
Therefore (205) in Lemma 4.4 gives
ϕ(z)ρr(u,z) ≤Cexp−
K2
q
2(1−r2) ≤Ce−K2
q/2
.
Taking the supremum over such u, with value zero if there is no such u, and integrating over a set
of length at most 2uq, gives
Lq≤|z|≤uq
where we use the definition Kq =ϕ(z) sup
u∈Cz:
|z|−ru >Kq
 8 log uq in (204).
ρr(u,z) dz≤Cuqe−K2
q/2
= O(u−3
q ). (268)
81
```

<!-- source-page: 82 -->

### PDF page 82

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
Now consider the remaining term in (266). For any contributing pair, |z| ∈ [Lq,uq] and
|z|−ru ≤Kq. Since u∈Cz,
Glarge
z (u) + Gsmall
z (u) = Gz(u) ≥p(u)
.
2q
Thus
Glarge
z (u) ≥p(u)
4q
or Gsmall
z (u) ≥p(u)
4q
z∈Elarge
sgn(z)(r) ∪Esmall
sgn(z)(r),
.
ρr(u,z) dz
ρr(u,z) dz
ρr(u,z) dz.
Thus,
and the last integral in (266) satisfies
ϕ(z) sup
Lq≤|z|≤uq
u∈Cz:
|z|−ru ≤Kq
≤
z∈Elarge
+ (r)∪Elarge
− (r)
ϕ(z) sup
u∈Cz:
|z|−ru ≤Kq
+
z∈Esmall
+ (r)∪Esmall
− (r)
ϕ(z) sup
u∈Cz:
|z|−ru ≤Kq
Lemma 4.5 gives
|Elarge
+ (r)|+ |Elarge
− (r)|≤(1−r)uq + C√uq.
Lemma 4.6 gives
|Esmall
+ (r)|+ |Esmall
− (r)|≤C(Kq + 1) ≤C√uq.
Combining the two bounds, the total combined length of the corresponding aligned factor values is
at most
(1−r)uq + C√uq. (269)
Combining (206) in Lemma 4.4 and (269), and using 0 <r <3/5, hence (1−r2)−1/2 ≤5/4, we
obtain
ϕ(z) sup
Lq≤|z|≤uq
u∈Cz:
|z|−ru ≤Kq
≤ 1 + C(Kq + 1)/uq
2√2π√1−r2 + Ce−uq (1−r)uq + C√uq
1−r
Kq + 1 + √uq
≤
uq + C
2√1−r2√2π
√1−r2 + Cuqe−uq
1−r
≤
uq + C{Kq + 1 + √uq + uqe−uq}.
2√1−r2√2π
Here the middle line expands the product and absorbs the term (Kq + 1)/√uq into Kq + 1. Since
Lq = Kq + √uq, Kq = O( log uq), and uqe−uq is negligible, combining this with (266), (267), and
(268) yields
uq
uq
−uq
ϕ(z) sup
u∈Cz
ρr(u,z) dz≤
1−r
uq + C√uq ≤
2√1−r2√2π
where the last inequality uses (1−r)/√1−r2 = (1−r)/(1 + r) ≤1. This proves Lemma 4.7.
82
ρr(u,z) dz
+ C√uq, (270)
2√2π
```

<!-- source-page: 83 -->

### PDF page 83

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
The next lemma converts observed rejection counts into bounds for their conditional means.
Lemma 4.8. There are universal constants C,c>0 with the following property. Let J ≥1, and let
Nj be Poisson-binomial with mean µj; the counts may be nested in j. For j ≥J, define the bad
events
(271)
(272)
B+
j= {Nj ≥j−1, µj <j/2}, B−
j= {Nj ≤j−2, µj >2j}. Then
P j≥J
(B+
j ∪B−
j )≤Ce−cJ
.
The constants are universal and the bound is uniform in the number and success probabilities of the
Bernoulli variables.
Proof. If µj <j/2, the Chernoff upper-tail inequality bounds P(B+
j ) = P(Nj ≥j−1) by C0e−c0j;
if µj ≥j/2, then B+
j is empty. Similarly, if µj > 2j, the Chernoff lower-tail inequality bounds
P(B−
j ) = P(Nj ≤j−2) by C0e−c0j, while if µj ≤2j, then B−
j is empty. Enlarging C0, if necessary,
absorbs the finitely many small values of j. Sum these bounds over j ≥J.
Proof of Theorem 4.2 (b). If m0 = 0, then FDR(BHq) = 0. Hence assume m0 >0. Let Ri be the
BH rejection count after replacing the true-null p-value Pi by zero, as in the proof of Lemma 4.1.
For every hypothesis ℓ, define
Fℓ,z(t) = P(Pℓ ≤t|Z= z), tk =
qk
, uk = p−1(tk).
m
The leave-one-out identity (191) and the same conditional-independence argument give, for almost
every z,
Fi,z(tk)
P(Ri = k|Z= z)
FDR(z) = q
mi∈H0
=
q
mi∈H0
m
k=1
m
k=1
tk
ρ|ai|(uk,z)P(Ri = k|Z= z). (273)
Thus FDR = R FDR(z)ϕ(z) dz. The second equality follows from (199). Let
Aq = {|Z|>uq}.
Decompose
FDR = E{FDR(Z) 1Aq}+ E{FDR(Z) 1Ac
q}.
The first term is at most q:
E{FDR(Z) 1Aq}≤P(Aq) = 2Φ(uq) = p(uq) = q,
because 0 ≤FDR(Z) ≤1 and uq = p−1(q). It remains to prove
E{FDR(Z) 1Ac
q}≤π0q
uq
83
2√2π
+ C√uq. (274)
```

<!-- source-page: 84 -->

### PDF page 84

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
Define
J= ⌈√uq⌉.
Then J ≥2 when q is sufficiently small. We split the summands in (274) into two parts. It suffices
to prove
Ac
q
q
mi∈H0 1≤k≤J
ρ|ai|(uk,z)P(Ri = k|Z= z)ϕ(z) dz
≤π0qJ ≤π0q(√uq + 1),
(275)
and
Ac
q
q
mi∈H0 k>J
ρ|ai|(uk,z)P(Ri = k|Z= z)ϕ(z) dz
(276)
≤π0q
uq
2√2π
+ C√uq.
We first prove (275). Its left-hand side is bounded directly from (273). Using (200) with u= uk,
1Ac
q ≤1, and P(Ri = k|Z= z) ≤1, it is at most
q
mi∈H0 1≤k≤J
1 = π0qJ ≤π0q(√uq + 1).
We next prove (276). For each i and z, and for 1 ≤j ≤m, let
Ni,j=
ℓ̸=i
1{Pℓ ≤qj/m}, µi,j(z) = E(Ni,j |Z= z). (277)
Define the good event corresponding to (271)-(272) as follows. Let
B+
i,j(z) = {Ni,j ≥j−1, µi,j(z) <j/2}, B−
i,j(z) = {Ni,j ≤j−2, µi,j(z) >2j},
and set
Ai,z :=
m
j=J
(B+
i,j(z))c ∩(B−
i,j(z))c
. (278)
We split the conditional probability in the left-hand side of (276) according to this event:
P(Ri = k|Z= z) = P{Ri = k,Ai,z |Z= z}+ P{Ri = k,Ac
i,z |Z= z}.
It is enough to prove the bad-event bound
q
Ac
q
mi∈H0 k>J
ρ|ai|(uk,z)P{Ri = k,Ac
i,z |Z= z}ϕ(z) dz
≤Cπ0q,
(279)
and the good-event bound
Ac
q
q
mi∈H0 k>J
ρ|ai|(uk,z)P{Ri = k,Ai,z |Z= z}ϕ(z) dz
≤π0q
uq
2√2π
+ C√uq.
(280)
We first prove the bad-event bound (279). Set δJ = Ce−cJ. Fix i and z, and condition on
Z= z. The residuals of the hypotheses ℓ̸= i are then independent, so the indicators in (277) are
84
```

<!-- source-page: 85 -->

### PDF page 85

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
independent Bernoulli random variables, with success probabilities depending on ℓ, j, and z. Hence
each Ni,j is Poisson-binomial with mean µi,j(z), and the family may be nested in j, exactly as
allowed in Lemma 4.8. Moreover, Ac
i,z is the union over J ≤j ≤m of the two events
{Ni,j ≥j−1, µi,j(z) <j/2} and {Ni,j ≤j−2, µi,j(z) >2j},
which are exactly the bad events in Lemma 4.8 with Nj= Ni,j and µj= µi,j(z). Thus the lemma
gives, uniformly in z,
P(Ac
i,z |Z= z) ≤δJ. (281)
Using (281), and since uk ≥uq for k>J, for each i and z,
ρ|ai|(uk,z)P{Ri = k,Ac
i,z |Z= z}
k>J
≤sup
u≥uq
≤sup
u≥uq
ρ|ai|(u,z)
P{Ri = k,Ac
i,z |Z= z}
k>J
ρ|ai|(u,z)P(Ac
i,z |Z= z) ≤δJ sup
u≥uq
ρ|ai|(u,z).
Since Ac
q
= {|z|≤uq}, inserting this pointwise bound into the left-hand side of (279) gives
q
Ac
q
mi∈H0 k>J
ρ|ai|(uk,z)P{Ri = k,Ac
i,z |Z= z}ϕ(z) dz
≤ q
mi∈H0
δJ
uq
ϕ(z) sup
ρ|ai|(u,z) dz
−uq
u≥uq
≤ q
m|H0|δJCq = π0qδJCq ≤Cπ0q(1 + uq)e−c√uq ≤Cπ0q.
(282)
Here Lemma 4.3 gives
uq
√2π
Cq := sup
0≤r≤1
uq
−uq
ϕ(z) sup
u≥uq
ρr(u,z) dz≤
1−q
2 +
.
Lastly, we prove the good-event bound (280). Here Ai,z is defined in (278). On {Ri = k},
Ni,k= k−1, Ni,j ≤j−2 (j >k). (283)
Consequently, on {Ri = k}∩Ai,z, the exclusions in (278) applied with j= k and then with each
j >k give
µi,k(z) ≥k/2, µi,j(z) ≤2j (j >k). (284)
Define the averaged conditional sub-CDF of the other hypotheses and its scale version by
F−i,z(t) = 1
m ℓ̸=i
Fℓ,z(t), Gi,z(u) = F−i,z{p(u)}. (285)
For each ℓ̸= i, the common-factor representation (189) gives, conditionally on Z= z,
Fℓ,z{p(u)}= P{|Tℓ|≥u|Z= z}= P{|θℓ + aℓz+ 1−a2
ℓ εℓ|≥u}.
Therefore
Gi,z(u) = P{|θ+ αz+ 1−α2 ε|≥u}dΠi(θ,α), Πi =
1
m ℓ̸=i
δ(θℓ,aℓ).
85
```

<!-- source-page: 86 -->

### PDF page 86

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
This is exactly the form (211).
We now verify the hypotheses of Lemma 4.7, one true null i at a time. For this fixed i, define
wi,k(z) = P{Ri = k,Ai,z |Z= z}, J <k≤m,
and take Gz = Gi,z. First, the weights are nonnegative and, because the events {Ri = k}, 1 ≤k≤m,
are disjoint,
wi,k(z) ≤1.
k>J
Second, whenever wi,k(z) >0, the event {Ri = k,Ai,z}has positive conditional probability. Since
the quantities µi,j(z) are fixed after conditioning on Z= z, the implication above gives (284) for
this i,z,k. Using µi,j(z) = mGi,z(uj), these inequalities become
Gi,z(uk) ≥
k
, Gi,z(uj) ≤
2m
2j
m (j >k).
Thus (262) holds for every k with wi,k(z) > 0, with Gz = Gi,z and wk(z) = wi,k(z). Applying
Lemma 4.7 with r= |ai|gives
uq
−uq k>J
wi,k(z)ρ|ai|(uk,z)ϕ(z) dz≤
uq
+ C√uq,
2√2π
where Ac
q
(280).
= {|z|≤uq}. Summing the preceding bound over i∈H0 and using |H0|/m= π0 gives
¯
We have proved part (b) for q≤q0. If q0 <q≤2
Φ(1), part (a) gives
FDR(BHq) ≤q 1 + π0
1−q
2 +
uq
√2π
.
¯
When q∈[q0,2
Φ(1)], the quantities uq and log(1/q) are bounded above and log(1/q) is bounded
away from zero. Hence, after enlarging the universal constant C,
1−q
2 +
uq
√2π
≤
1
2√π
log(1/q) + C{log(1/q)}1/4
,
which closes part (b) on the remaining q-range.
Remark 4.9 (PRDN for the two-sided null p-values). The theorem imposes no sign restriction on the
loadings ai, so the null correlations aiaj may be negative. Nevertheless, the two-sided null p-values
satisfy PRDN. Let
T0 = (Ti : i∈H0), a0 = (ai : i∈H0), ε0 = (εi : i∈H0).
Put
D0 = diag(1−a2
i : i∈H0).
Since θi = 0 for i∈H0,
T0 = a0Z+ D0 ε0.
Hence T0 is centered Gaussian with covariance matrix
Σ0 = D0 + a0a⊤
0.
86
```

<!-- source-page: 87 -->

### PDF page 87

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
Assume first that |ai|<1 for every null coordinate. Let
B = diag{sign(ai) : i∈H0}, r0 = (|ai|: i∈H0)⊤
,
BΣ0B= D0 + r0r⊤
0.
with sign(0) = 1. Then
By the Sherman-Morrison formula,
D−1
(D0 + r0r⊤
0 )−1
= D−1
0 r0r⊤
0 D−1
0
0−
1 + r⊤
0 D−1
0 r0.
Thus every off-diagonal entry of (D0 + r0r⊤
0 )−1 is nonpositive. The Karlin-Rinott absolute-value
multinormal criterion for multivariate total positivity of order two (MTP2) [Karlin and Rinott, 1981]
therefore applies to BT0, and (|(BT0)i|: i∈H0) is MTP2. Since |(BT0)i|= |Ti|, coordinatewise sign
changes do not alter the absolute null statistics. Applying the same decreasing map g(x) = p(x) =
2Φ(x) to every coordinate preserves MTP2. Indeed, for u,v∈(0,1)m0 , coordinatewise monotonicity
of g−1 gives
g−1(u∧v) = g−1(u) ∨g−1(v), g−1(u∨v) = g−1(u) ∧g−1(v).
If f is the density of (|(BT0)i|: i∈H0), the density after the transformation is
f(u) = f{g−1(u)}
|(g−1)′(ui)|.
i∈H0
For each coordinate, {ui ∧vi,ui ∨vi}= {ui,vi}; hence the two products of Jacobian factors are
equal. Therefore the MTP2 inequality for f implies
f(u∧v)f(u∨v) = f{g−1(u) ∨g−1(v)}f{g−1(u) ∧g−1(v)}
|(g−1)′(ui)(g−1)′(vi)|
≥f{g−1(u)}f{g−1(v)}
i∈H0
|(g−1)′(ui)(g−1)′(vi)|
i∈H0
= f(u)f(v).
Thus the vector of two-sided null p-values is MTP2, which implies PRDN.
If some |ai|= 1, define a(η)
i = (1−η)ai for all i∈H0, and let η↓0. The corresponding absolute
null vectors converge weakly to (|Ti|: i∈H0). Under the measure-theoretic definition of MTP2,
the class of MTP2 probability measures is closed under weak convergence [Colangelo et al., 2006].
Hence the limiting absolute-value law remains MTP2. Appendix A.1 of Su [2018] then implies that
the induced vector of two-sided null p-values satisfies PRDN.
4.3 Upper bounds for one-sided tests
We derive an FDR upper bound for one-sided tests under the common-factor model and show that
its leading constant cannot be improved within this class.
Theorem 4.10. Consider the common-factor model (189). Test Hi : θi ≤0 with Pi = Φ(Ti). Let
H0 = {i: θi ≤0}, m0 = |H0|, and π0 = m0/m. For 0 <q<1/2, put u+
q
= Φ−1(q) >0. The FDR
is zero when m0 = 0, and otherwise
FDR(BHq) ≤q 2 + π0
1
u+
q
2 +
√2π
. (286)
Consequently, the worst-case FDR in this common-factor class is O{q log(1/q)}, uniformly in m,
the means (θ1,...,θm), and the loadings (a1,...,am), as q↓0.
87
```

<!-- source-page: 88 -->

### PDF page 88

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
The following corollary identifies the exact leading constant for the common-factor class.
Corollary 4.11. For the common-factor model (189), where FDRθ,a denotes the FDR under that
model, as q↓0,
+ O(q).
sup
m∈N, θ∈Rm
,
a∈[−1,1]m
FDRθ,a(BHq) = q log(1/q)
√π
Thus the constant 1/√π in Proposition 3.2 is optimal in the common-factor class.
Proof of Theorem 4.10. If there are no true nulls, the FDR is zero. Partition the true nulls into the
two sign groups
H0,1 = {i∈H0 : ai ≥0}, H0,−1 = {i∈H0 : ai <0}.
Let S⊆{−1,1}index the nonempty groups. The leave-one-out identity (191) and conditional
reduction (192) are independent of the particular form of the p-values.
Suppose i∈H0,σ, where σ ∈S, and write r= |ai|and Yσ = σZ∼N(0,1). Define the actual
conditional CDF by
Fθi
i,y(t) = Pθi(Pi ≤t|Yσ = y)
and let F0
r,y denote the corresponding conditional CDF at the boundary mean θi = 0. Conditional
on Yσ = y, Ti ∼N(θi + ry,1−r2). Since θi ≤0 and rejection is increasing in Ti,
Fθi
i,y(t) ≤F0
r,y(t), 0 <t<1.
Thus it suffices in the conditional leave-one-out bound to control the boundary CDF F0
r,y.
For r<1, the one-tail Gaussian density-ratio calculation gives
ϕ(y) sup
0<t≤q
F0
r,y(t)
t ≤
1
√1−r2√2π
exp−
(ru+
q−y)2
+
2(1−r2). (287)
Indeed, write t= p+(u), where u≥u+
q . The bivariate normal density identity
ϕ(y) 1
√1−r2 ϕ x−ry
√1−r2
= ϕ(x) 1
√1−r2 ϕ y−rx
√1−r2
and p+(u) =∞
u ϕ(x) dx give
ϕ(y)
F0
r,y{p+(u)}
p+(u)
=
u
∞
ϕ(x) 1
√1−r2 ϕ y−rx
√1−r2
u
dx
∞
ϕ(x) dx
1
≤sup
x≥u
√1−r2 ϕ y−rx
√1−r2
≤
1
√1−r2√2π
exp−
(ru−y)2
+
2(1−r2). (288)
The final inequality in (288) follows because, for every x≥u,
(rx−y)2 ≥(ru−y)2
+.
88
```

<!-- source-page: 89 -->

### PDF page 89

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
Since r ≥0, the map u →(ru−y)+ is nondecreasing. Thus the right-hand side of (288) is
nonincreasing in uand is maximized over u≥u+
q at u= u+
q , proving (287). Integrating over y≤u+
q
yields
1 dy
.
q
I(r) :=u+
F0
r,y(t)
ϕ(y) sup
−∞
0<t≤q
t
1
≤
√1−r2√2π
ru+
q
−∞
1
=
√1−r2√2π
∞
0
1
q
=
2 + (1−r)u+
√1−r2√2π
1
u+
≤
q
2 +
√2π
dy
u+
e−(ru+
q−y)2/{2(1−r2)}dy+
q
ru+
q
e−v2/{2(1−r2)}dv+ (1−r)u+
q
. (289)
The inequality (1−r)u+
q /{√1−r2√2π}≤u+
q /√2π in (289) follows from (1−r)/√1−r2 =
(1−r)/(1 + r) ≤1. If r = 1, then on Yσ < u+
q the boundary-null p-value is larger than q, so
(289) remains valid.
Let Vσ be the false rejections in sign group σ and FDPσ = Vσ/(R∨1). On Aσ = {Yσ ≤u+
q },
sum the per-null conditional bound over H0,σ and apply (289). This gives
E(FDPσ1Aσ) ≤q|H0,σ|
m
1
2 +
u+
q
√2π
On Ac
σ, use 0 ≤FDPσ ≤1 and P(Ac
σ) = q. Summing over σ ∈S, using |S|≤2 and FDP =
σ∈SFDPσ, proves (286).
Proof of Corollary 4.11. Theorem 3.1 gives the lower bound within the common-factor class. Indeed,
for the perturbed model (32), set
a(η)
i = 1−η2 bi, ε(η)
i =
(1−η2)(1−b2
i) εi + ηξi
1 −{a(η)
i }2.
The variables ε(η)
i are independent standard normal variables and are independent of Z, and
T(η)
i = θi + a(η)
i Z+ 1 −{a(η)
i }2 ε(η)
i.
Thus the perturbation is of the form (189). Together with Proposition 3.2, this gives
sup
m∈N, θ∈Rm
,
FDRθ,a(BHq) ≥ℓ≤(q) = q log(1/q)
√π
+ q
2 + o(q).
a∈[−1,1]m
For the matching upper bound, note first that u+
q
= p−1(2q), so (301) in Lemma A.2 gives
∼ 2 log(1/q). More precisely, (298) in Lemma A.2 and q= Φ(u+
q ) imply
(u+
q )2 = 2 log(1/q)−2 log u+
q−log(2π) + o(1) = 2 log(1/q) + O{log log(1/q)}.
89
u+
q
```

<!-- source-page: 90 -->

### PDF page 90

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
Consequently,
u+
q
= 2 log(1/q) + O log log(1/q)
log(1/q)
= 2 log(1/q) + o(1).
Theorem 4.10, with π0 ≤1, now gives the reverse inequality up to an O(q) term, proving the
claim.
5 Discussion
For two-sided problems, Theorem 2.1 and Proposition 2.2 show that no bound of the form Cq,
with C independent of q, can hold uniformly over all Gaussian correlation matrices. Because the
example that achieves the lower bound belongs to the one-common-factor class studied in Section 4,
Theorem 4.2 shows that the worst-case FDR within this class has the sharp leading constant
1/(2√π). Similarly, For one-sided tests, Theorem 3.1 and Corollary 4.11 give the optimal leading
constant 1/√π within the same class.
In the literature, there are procedures with finite-sample FDR guarantees for arbitrary depen-
dent two-sided Gaussian tests. The conditional-calibration framework of Fithian and Lei [2022]
decomposes FDR into hypothesis-specific contributions and, for each null i, conditions on a null
sufficient statistic under which the ith p-value remains conditionally valid, often eliminating nuisance
parameters. The resulting guarantees depend on the procedure and the dependence assumptions:
under PRDS, the procedure controls FDR and its rejection set contains that of BH. Under arbitrary
dependence, the procedure controls FDR and its rejection set contains that of the Benjamini-
Yekutieli procedure [Benjamini and Yekutieli, 2001]. Conditional calibration can therefore exploit
known dependence without automatically paying the full O(log N) correction of Benjamini and
Yekutieli [2001]. Another route is the fixed-X knockoff filter of Barber and Candès [2015]. In
a Gaussian linear model, knockoffs augment the covariate matrix with synthetic variables that
mimic the correlation structure of the original variables, and achieve the FDR control through the
symmetry between the original test statistic and its knockoff. Li and Fithian [2021] recast fixed-X
knockoffs as adding user-generated Gaussian noise to a Gaussian estimator to obtain a whitened
estimator, followed by conditional inference. This whitening can substantially reduce power when
the covariance has large leading eigenvalues associated with dense leading eigenvectors, because
it then requires enough added noise to erase much of the signal. Knockoffs also face a threshold
phenomenon when the rejection set is small. The calibrated knockoff method of Luo et al. [2025]
uses conditional calibration to uniformly improve knockoff procedures, with especially large gains in
small-rejection regimes.
This discussion points to two complementary directions: identifying restrictions of dependence
structures under which the standard BH remains reliable, and developing other procedures that
leverage the dependence structures to control FDR without further restrictions.
Acknowledgments and disclosure
The author thanks Will Fithian for encouraging him to work on the two-sided problems, Ruodu
Wang for encouraging him to work on the one-sided problems, and Edgar Dobriban for the surprising
initial counterexample that reignited interest in this project. The author used OpenAI GPT-5.6
Sol for assistance with proof exploration, exposition, and editing. The author has been working
on this problem for over five years and the results in this paper could not have been developed
without the significant input of GPT 5.6 Sol. Nevertheless, the human input is equally important
90
```

<!-- source-page: 91 -->

### PDF page 91

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
for the research paper: the author spent about 180 hours on idea generation, verification, correction,
simplification, and writing. From the author’s perspective, it is a remarkably rewarding experience
of Human-AI collaboration.
References
Rina Foygel Barber and Emmanuel J. Candès. Controlling the false discovery rate via knockoffs.
The Annals of Statistics, 43(5):2055–2085, 2015. doi: 10.1214/15-AOS1337.
Yoav Benjamini. Discovering the false discovery rate. Journal of the Royal Statistical Society: Series
B (Statistical Methodology), 72(4):405–416, 2010. doi: 10.1111/j.1467-9868.2010.00746.x. URL
https://doi.org/10.1111/j.1467-9868.2010.00746.x.
Yoav Benjamini and Yosef Hochberg. Controlling the false discovery rate: A practical and powerful
approach to multiple testing. Journal of the Royal Statistical Society: Series B, 57(1):289–300,
1995. doi: 10.1111/j.2517-6161.1995.tb02031.x.
Yoav Benjamini and Daniel Yekutieli. The control of the false discovery rate in multiple testing
under dependency. The Annals of Statistics, 29(4):1165–1188, 2001. doi: 10.1214/aos/1013699998.
Ziyu Chi, Aaditya Ramdas, and Ruodu Wang. Multiple testing under negative dependence. Bernoulli,
31(2):1230–1255, 2025. doi: 10.3150/24-BEJ1768.
Antonio Colangelo, Alfred Müller, and Marco Scarsini. Positive dependence and weak convergence.
Journal of Applied Probability, 43(1):48–59, 2006. doi: 10.1239/jap/1143936242.
Edgar Dobriban. The Benjamini–Hochberg procedure can fail to control the FDR for correlated
two-sided Gaussian tests, 2026. URL https://arxiv.org/abs/2607.12208.
William Fithian and Lihua Lei. Conditional calibration for false discovery rate control under
dependence. The Annals of Statistics, 50(6):3091–3118, 2022. doi: 10.1214/21-AOS2137.
Yosef Hochberg and Dror Rom. Extensions of multiple testing procedures based on simes’ test.
Journal of Statistical Planning and Inference, 48(2):141–152, 1995.
Samuel Karlin and Yosef Rinott. Total positivity properties of absolute value multinormal variables
with applications to confidence interval estimates and related probabilistic inequalities. The
Annals of Statistics, 9(5):1035–1049, 1981. doi: 10.1214/aos/1176345583.
Xiao Li and William Fithian. Whiteout: When do fixed-X knockoffs fail?, 2021. URL https:
//arxiv.org/abs/2107.06388.
Yixiang Luo, William Fithian, and Lihua Lei. Improving knockoffs with conditional calibration.
The Annals of Statistics, 53(5):2283–2302, 2025. doi: 10.1214/25-AOS2543.
Anat Reiner-Benaim. FDR control by the BH procedure for two-sided correlated tests with
implications to gene expression data analysis. Biometrical Journal, 49(1):107–126, 2007. doi:
10.1002/bimj.200510313.
Marine Roux. Inférence de graphes par une procédure de test multiple avec application en
Neuroimagerie. PhD thesis, Université Grenoble Alpes (ComUE), September 2018. URL
https://theses.fr/2018GREAT058. Thesis no. 2018GREAT058.
91
```

<!-- source-page: 92 -->

### PDF page 92

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
Ester Samuel-Cahn. Is the simes improved bonferroni procedure conservative? Biometrika, 83(4):
928–933, 1996.
Sanat K. Sarkar. On controlling the false discovery rate in multiple testing of the means of correlated
normals against two-sided alternatives, 2023. URL https://arxiv.org/abs/2304.05261.
Sanat K. Sarkar and Shiyu Zhang. Shifted BH methods for controlling false discovery rate in
multiple testing of the means of correlated normals against two-sided alternatives. Journal of
Statistical Planning and Inference, 236:106238, 2025. doi: 10.1016/j.jspi.2024.106238.
Weijie J. Su. The FDR-linking theorem, 2018. URL https://arxiv.org/abs/1812.08965.
A Auxiliary lemmas
This appendix collects the properties of the envelope and Gaussian tails used to define and analyze
νq,r.
The following lemma characterizes the likelihood-ratio envelope.
Lemma A.1. For 0 ≤y≤1, M(y) = 1. For y>1, a→La(y) has a unique maximizer a(y) >0,
characterized by
a(y) = ytanh{a(y)y}.
The maps a: (1,∞) →(0,∞) and M : (1,∞) →(1,∞) are continuous and strictly increasing, with
lim
y↓1
a(y) = 0, lim
y→∞
M(y) = ∞. (290)
The inverse y= y(a) is continuously differentiable on (0,∞), and
y
′(a) = 1−y(a)2 sech2{ay(a)}
tanh{ay(a)}+ ay(a) sech2{ay(a)}>0. (291)
Moreover, with aq = a(yq), the deficit in the secondary survival mass satisfies
1−qM{y(a)}>0 (0 <a<aq), 1−qM{y(aq)}= 0,
d
da
1−qM{y(a)} <0. (292)
Proof. Let
a2
gy(a) = log La(y) =−
2 + log cosh(ay).
Then
′
g
y(a) =−a+ ytanh(ay). (293)
If y≤1, then ytanh(ay) ≤ay2 ≤a, so M(y) = L0(y) = 1.
For y>1, put t= ay. Equation g′
y(a) = 0 is equivalent to
y2
=
. (294)
tanh t
To prove that the map t →t/tanh t in (294) is strictly increasing, let H(t) = tanh t−tsech2 t.
Then H(0) = 0 and H′(t) = 2tsech2 ttanh t>0 for t>0. Hence
d
dt
t
tanh t=
tanh t−tsech2 t
>0.
t
tanh2 t
92
```

<!-- source-page: 93 -->

### PDF page 93

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
Moreover, t/tanh t→1 as t↓0 and t/tanh t→∞as t→∞. Because y2 >1, (294) in Lemma A.1
therefore has a unique positive solution. The sign of g′
y changes from positive to negative there, so
the solution is the unique maximizer. Moreover,
a(y) = √ttanh t, y=
t
tanh t, (295)
Both parameter functions in (295) in Lemma A.1 are smooth and strictly increasing in t > 0.
They tend respectively to zero and one as t↓0, and both tend to infinity as t→∞. Thus a(y) is
continuous and strictly increasing on (1,∞), with a(y) →0 as y↓1; the inverse function theorem
applied to the second parameter function also shows that a(y) is continuously differentiable. Since
M(y) = La(y)(y), the chain rule and ∂aLa(y)(y) = 0 give
M′(y) = M(y)a(y) tanh{a(y)y}>0.
Thus M is continuous and strictly increasing. Also
M(y) ≥Ly(y) ≥
Finally, apply the implicit function theorem to
F(a,y) = a−ytanh(ay) = 0.
At the maximizer, with t= ay>0, equation (294) in Lemma A.1 gives
y2 sech2(ay) = tsech2 t
tanh t=
2t
sinh(2t) <1.
1
ey2/2 →∞.
2
Consequently,
Fa = 1−y2 sech2(ay) >0, Fy =−tanh(ay)−aysech2(ay) <0.
Thus (291) in Lemma A.1 follows from y′
=−Fa/Fy.
It remains to prove (292) in Lemma A.1. Since aq = a(yq), we have y(aq) = yq, and therefore
1−qM{y(aq)}= 0 by (4). If 0 <a<aq, then y(a) <yq; since M is strictly increasing on (1,∞),
qM{y(a)}<qM(yq) = 1. Finally,
d
da
1−qM{y(a)}=−qM′{y(a)}y
′(a) <0,
because M′>0 on (1,∞) and y′>0 on (0,∞).
The final lemma collects the Mills bounds and quantile asymptotics used to control Gaussian
tails.
Lemma A.2. The normal hazard λ is increasing on R and satisfies
x<λ(x) <x+ x−1 (x>0). (296)
Moreover, as x→∞,
λ(x) = x+ x−1 + O(x−3). (297)
93
```

<!-- source-page: 94 -->

### PDF page 94

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
As x→∞,
Φ(x) = ϕ(x)
x {1 + o(1)}. (298)
For every fixed 0 <σ<1, as x→∞,
1
Φ(σx)
Φ(x)∼
σ
exp (1−σ2)x2
2. (299)
For every 0 <H <∞, uniformly over |u|∨|v|≤H, as x→∞,
p(x+ u)
x+ v
=
exp−x(u−v)−
u2
−v2
2 {1 + o(1)}. (300)
p(x+ v)
If c>0 is fixed, then, as q↓0,
x+ u
p−1(cq)∼ 2 log(1/q). (301)
In particular, for every fixed c1,c2 >0,
p−1(c1q)
p−1(c2q) −→1 (q↓0).
Finally, for x≥0,
2Φ(x) ≤e−x2/2
. (302)
For x>0 and δ≥0,
p(x+ δ)
p(x) ≤ 1 + x−2 exp−xδ−
Consequently, if x→∞, then the following tail-ratio limits hold.
δ2
2. (303)
(i) For every 0 <H <∞, uniformly over |u|∨|v|≤H,
log p(x+ u)
p(x+ v)
=−x(u−v)−
u2
−v2
2 + o(1). (304)
(ii) For every 0 <H <∞, uniformly over |h|≤H,
p(x)
p(x+ h/x) −→eh
. (305)
(iii) If 0 <δ0 ≤δ≤δ1 <∞, then
p(x+ δ)
p(x) −→0 (306)
uniformly in δ.
(iv) If δx ≥0 and xδx →∞, then
p(x+ δx)
p(x) −→0. (307)
94
```

<!-- source-page: 95 -->

### PDF page 95

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
Proof. For x>0, the upper Mills bound follows from
1
x
∞
x
tϕ(t) dt=
ϕ(x)
Φ(x) <
. (308)
x
Integration by parts gives
Φ(x) = ϕ(x)
x−
∞
x
ϕ(t)
t2 dt> ϕ(x)
x−
Φ(x)
x2 ,
which proves the lower Mills bound
x
1 + x2 ϕ(x) <Φ(x). (309)
A further integration by parts gives
ϕ(t)
t4 dt,
where
Hence
Φ(x) = ϕ(x)
x−
ϕ(x)
x3 + 3
∞
x
0 <
∞
x
ϕ(t)
t4 dt< ϕ(x)
x5.
Φ(x) = ϕ(x)
x {1−x−2 + O(x−4)},
and inversion proves (297) in Lemma A.2. Equations (308) and (309) imply (296) in Lemma A.2
for x>0. Since λ(x)−x>0 also holds trivially for x≤0, the identity
λ′(x) = λ(x){λ(x)−x}
shows that λ is increasing on R.
Equations (308) and (309) give (298) in Lemma A.2. Applying this at x and σx proves (299) in
Lemma A.2. Applying (298) in Lemma A.2 at x+ u and x+ v gives (300) in Lemma A.2, for every
0 <H <∞, uniformly over |u|∨|v|≤H. Moreover, as x→∞,
−log p(x) = x2
2 + O(log x),
which yields (301) in Lemma A.2 by inversion. To prove 2Φ(x) ≤e−x2/2, set
d(x) = e−x2/2
−2Φ(x).
Then d(0) = 0, limx→∞d(x) = 0, and
d′(x) = e−x2/2 2
π−x .
Thus d first increases and then decreases to zero, so d(x) ≥0 for all x≥0. Finally, (308) and (309)
imply
p(x+ δ)
p(x) ≤ 1 + x2
x(x+ δ) exp−xδ−
δ2
2 ≤ 1 + x−2 exp−xδ−
δ2
2 ,
which proves (303) in Lemma A.2.
95
```

<!-- source-page: 96 -->

### PDF page 96

> [uncertain: embedded-text mathematical layout and glyphs; compare the exact supplied LaTeX and PDF.]

```text
It remains to prove the four stated tail-ratio consequences. Taking logarithms in (300) in
Lemma A.2 gives (304) in Lemma A.2, because
log x+ v
x+ u
= o(1)
for every 0 < H < ∞, uniformly over |u|∨|v|≤H. For (305) in Lemma A.2, apply (300) in
Lemma A.2 with u= 0 and v= h/x. For every 0 <H <∞, uniformly over |h|≤H,
p(x)
p(x+ h/x)
=
x+ h/x
x
exp h+
h2
2x2 {1 + o(1)}−→eh
.
For (306) in Lemma A.2, apply (304) in Lemma A.2 with u= δ and v= 0. If 0 <δ0 ≤δ≤δ1 <∞,
then
log p(x+ δ)
p(x) ≤−xδ0 + O(1) −→−∞
uniformly in δ. Finally, (307) in Lemma A.2 follows from (303) in Lemma A.2 with δ= δx, because
xδx →∞.
96
```

## Exact user-supplied LaTeX source

The following code block preserves the supplied `FDR_BH_v4.tex` bytes exactly between its opening newline and closing fence. Internal LaTeX labels and citations are source-document identifiers, not research-node IDs or independently verified bibliography entries. Use the original PDF for rendered page locations.

```latex
\documentclass[11pt]{article}
\usepackage[margin=1in]{geometry}
\usepackage[T1]{fontenc}
\usepackage{lmodern}
\usepackage{microtype}
\usepackage{amsmath,amssymb,amsthm,mathtools}
\usepackage{enumitem}
\usepackage{graphicx}
\usepackage{booktabs}
\usepackage{float}
\usepackage{natbib}
\usepackage{xcolor}
\usepackage[hidelinks]{hyperref}
\newtheorem{theorem}{Theorem}[section]
\newtheorem{proposition}[theorem]{Proposition}
\newtheorem{lemma}[theorem]{Lemma}
\newtheorem{corollary}[theorem]{Corollary}
\newtheorem{conjecture}{Conjecture}
\theoremstyle{definition}
\newtheorem{definition}[theorem]{Definition}
\theoremstyle{remark}
\newtheorem{remark}[theorem]{Remark}
\newcommand{\R}{\mathbb R}
\newcommand{\N}{\mathbb N}
\newcommand{\1}{\mathbf 1}
\newcommand{\Phib}{\overline\Phi}
\newcommand{\FDR}{\operatorname{FDR}}
\newcommand{\FDP}{\operatorname{FDP}}
\newcommand{\BH}{\operatorname{BH}}
\newcommand{\diag}{\operatorname{diag}}
\newcommand{\sech}{\operatorname{sech}}
\newcommand{\dd}{\,\mathrm d}

\begin{document}

\title{How Much Can Gaussian Dependence Inflate the
Benjamini-Hochberg Procedure's FDR?}
\author{Lihua Lei\\
Graduate School of Business, Stanford University\\
\texttt{lihualei@stanford.edu}}
\date{\today}
\maketitle

\begin{abstract}
We study the worst-case false discovery rate (FDR) of the Benjamini-Hochberg
procedure for both one- and two-sided Gaussian tests with general correlation matrices.
For each setting and given target FDR level $q$,  we construct
a family of finite Gaussian models whose FDR divided by $q$
diverges as $q\downarrow0$. This disproves any universal multiplicative FDR
bound.  Moreover, we establish new FDR lower bounds that are independent of the number of hypotheses.
For two-sided tests, the worst-case FDR over the number of hypotheses, mean vector, and
correlation matrix is at least an explicit ${\ell_{=}}(q)>q$:
\[
 \ell_{=}(q)=\frac{q\sqrt{\log(1/q)}}{2\sqrt{\pi}}+c_\ell q+o(q),
 \qquad c_\ell=0.6492828\ldots.
\]
For one-sided tests, we show a lower bound $\ell_{\le}(q)>q$: 
\[
 \ell_{\le}(q)=\frac{q\sqrt{\log(1/q)}}{\sqrt\pi}
 +\frac q2+o(q).
\]
Finally, we prove the leading constants are sharp for a
class of correlation matrices for both one- and two-sided tests.
\end{abstract}

\section{Introduction}


We observe a Gaussian vector $T=(T_1,\ldots,T_{N})$ with mean
$\theta$ and covariance matrix $\Sigma$, where
$\Sigma_{ii}=1$ for $i=1,\ldots,N$.  We consider two testing problems.  For
two-sided tests, $H_i:\theta_i=0$ and
\[
 P_i=p(|T_i|),\qquad p(x)=2\Phib(x)=2\{1-\Phi(x)\}.
\]
For one-sided tests, $H_i:\theta_i\leq0$ and
\[
 P_i=p_+(T_i),\qquad p_+(x)=\Phib(x)=1-\Phi(x).
\]
Here $\Phi$ and $\phi=\Phi'$ are the standard normal CDF and density.
The normal hazard is
\begin{equation}
\lambda(x)=\frac{\phi(x)}{\Phib(x)}.
\end{equation}
We use the conventions $p^{-1}(0)=p_+^{-1}(0)=\infty$.
The Benjamini-Hochberg procedure \citep{BenjaminiHochberg1995} at level $q$
orders the $p$-values as
\[
 P_{(1)}\leq\cdots\leq P_{(N)}
\]
and rejects the hypotheses corresponding to
\[
 P_{(1)},\ldots,P_{(R)},\quad
 R=\max\{{1\leq k\leq N}:P_{(k)}\leq qk/N\},
\]
with $R=0$ if the set is empty.  If $V$ is the number of rejected true
nulls, then the false discovery proportion (FDP) and false discovery rate
(FDR) are
\[
 \FDP=\frac{V}{R\vee1},
 \quad
 \FDR=\mathbb E(\FDP).
\]

A long-standing conjecture for correlated two-sided Gaussian
$z$-tests is that BH
controls the FDR at its nominal level $q$, regardless of the correlation
matrix
\citep{ReinerBenaim2007,benjamini2010discovering,roux2018inference,Sarkar2023,SarkarZhang2025}.
\citet[p.~407]{benjamini2010discovering} summarized the evidence
as follows:
\begin{quote}
``The modification to general dependence is often not needed: convincing
simutheoretical evidence indicates that the same holds for two-sided
$z$-tests with any correlation structure.''
\end{quote}
Benjamini then noted that a complete theoretical proof was still missing.
These works stated or supported this conjecture.  However, recently,
\citet{Dobriban2026} found a counterexample where
$\FDR>0.0104$ when $q=0.01$.


In this paper, we ask a more refined question in each testing problem: how
large can the FDR be as a function of $q$?  For two-sided tests, we seek a
lower bound ${\ell_{=}}(q)$ such that
\begin{equation}
 \sup_{\substack{
   N\in\N,\ \theta\in\mathbb R^N,\
   \Sigma\in\mathbb S_+^N\\
   \Sigma_{ii}=1,\ 1\leq i\leq N}}
 \FDR_{\theta,\Sigma}(\BH_q)\geq \ell_{=}(q).
 \label{eq:worst-case-fdr}
\end{equation}
Here $\mathbb S_+^N$ denotes the cone of $N\times N$
symmetric positive semidefinite matrices.
A relaxed folklore conjecture is that the worst-case FDR in
\eqref{eq:worst-case-fdr} is bounded above by $Cq$ for some universal
constant $C>0$.  However, Theorem~\ref{thm:main} and
Proposition~\ref{prop:ell-expansion} together show that the worst-case FDR is
at least a quantity satisfying, as $q\downarrow0$,
\[
 \ell_{=}(q)
 =\frac{q\sqrt{\log(1/q)}}{2\sqrt{\pi}}+{c_\ell}q+o(q),
 \qquad c_\ell=0.6492828\ldots.
\]
In particular, the ratio of the supremum in
\eqref{eq:worst-case-fdr} to $q$ diverges as $q\downarrow0$.

Moreover, we derive an exact formula for ${\ell_{=}}(q)$.  We prove that
${\ell_{=}}(q)>q$ for every $q\in(0,1)$.  Instead of seeking a counterexample
for a given nominal level $q$, Theorem~\ref{thm:main} and
Proposition~\ref{prop:ell-strict} together disprove the conjecture that BH
controls the FDR for correlated two-sided Gaussian tests.
Figure~\ref{fig:ellq} illustrates the resulting two-sided FDR
inflation.
\begin{figure}[H]
\centering
\includegraphics[width=\linewidth]{ell_q_plots.pdf}
\caption{Numerical evaluation of ${\ell_{=}}(q)-q$ and ${\ell_{=}}(q)/q$ over the grid $q=0.005k$, $k=1,\ldots,199$.}
\label{fig:ellq}
\end{figure}

\begin{table}[H]
\centering

\begin{tabular}{@{}ccccc@{}}
\toprule
$q$&0.01&0.05&0.10&0.20\\
\midrule
${\ell_{=}}(q)-q$&0.0036&0.0129&0.0209&0.0314\\
${\ell_{=}}(q)/q$&1.3553&1.2571&1.2094&1.1570\\
\bottomrule
\end{tabular}
\caption{The absolute inflation ${\ell_{=}}(q)-q$ and relative
inflation ${\ell_{=}}(q)/q$ at commonly used nominal levels.}
\label{tab:common-q}
\end{table}


For one-sided Gaussian tests, the classical negatively correlated examples
of \citet{hochberg1995extensions} and \citet{samuel1996simes}
show that the Simes inequality, and hence BH under the global
null, can be anticonservative.  \citet{chi2025multiple} prove useful upper bounds under
several notions of negative dependence, but the adversarial construction used
in their sharpness comparison, due to \citet{Su2018}, is not jointly
Gaussian.  Our one-sided construction instead retains positively
correlated nulls and reverses the loading of the non-nulls.
Theorem~\ref{thm:one-lower} and
Proposition~\ref{prop:one-strict} give, for every $q\in(0,1)$,
\[
 \ell_{\le}(q)
 =\frac{q\sqrt{\log(1/q)}}{\sqrt\pi}+\frac q2
  +\Phib\!\left(\sqrt{2\log(1/q)}\right)>q,
\]
and Proposition~\ref{prop:one-expansion} gives
\[
 \ell_{\le}(q)
 =\frac{q\sqrt{\log(1/q)}}{\sqrt\pi}+\frac q2+o(q).
\]
This is a larger leading constant than in the two-sided construction and
again implies that the worst-case FDR ratio diverges.
Figure~\ref{fig:one-ellq} illustrates the resulting one-sided FDR
inflation.
\begin{figure}[H]
\centering
\includegraphics[width=\linewidth]{one_sided_ell_q_plots.pdf}
\caption{Numerical evaluation of $\ell_{\le}(q)-q$ and
$\ell_{\le}(q)/q$ over the grid $q=0.005k$, $k=1,\ldots,199$.}
\label{fig:one-ellq}
\end{figure}

\begin{table}[H]
\centering
\caption{The absolute inflation $\ell_{\le}(q)-q$ and relative
inflation $\ell_{\le}(q)/q$ at commonly used nominal levels.}
\label{tab:one-ell}
\begin{tabular}{ccccc}
\toprule
$q$ & $0.01$ & $0.05$ & $0.10$ & $0.20$\\
\midrule
$\ell_{\le}(q)-q$ & $0.00831$ & $0.03101$ & $0.05155$ & $0.07955$\\
$\ell_{\le}(q)/q$ & $1.8311$ & $1.6203$ & $1.5155$ & $1.3977$\\
\bottomrule
\end{tabular}
\end{table}


The dependence structures differ sharply between the two constructions.
Every covariance in the two-sided construction is positive, but the map
$T_i\mapsto2\Phib(|T_i|)$ is not monotone and
need not make the full vector of two-sided $p$-values satisfy
positive regression dependence on a subset (PRDS) with respect to the true
nulls.  For
one-sided Gaussian $p$-values, by contrast, nonnegative correlations between
every true null and every other hypotheses imply that $p$-values are PRDS
and hence FDR control
\citep{BenjaminiYekutieli2001}.  Negative dependence among the test statistics is
therefore essential for the one-sided lower bound. In particular, our example
has positive correlations between null pairs and negative correlations
between a pair of null and non-null.  Thus,
{the full vector of one-sided $p$-values in our construction is
not PRDS; Section~\ref{sec:one-sided-lower} verifies this directly}.

The lower-bound rate $q\sqrt{\log(1/q)}$ should be compared
with the FDR-linking theorem of \citet{Su2018}.
Positive regression dependence within nulls (PRDN) relaxes PRDS by imposing the relevant positive
dependence assumption only on the null $p$-values.  Under PRDN, the
FDR-linking argument gives an $O(q\log(1/q))$ bound.
Section~\ref{sec:upper-bound} proves sharper Gaussian bounds.  For two-sided
one-common-factor models,
\[
 \sup_{\substack{m\in\N,\ \theta\in\R^m,\\
                    a\in[-1,1]^m}}
 \FDR_{\theta,a}(\BH_q)
 =\left\{\frac1{2\sqrt\pi}+o(1)\right\}
 q\sqrt{\log(1/q)},
\]
so the lower construction attains the sharp leading constant in this
class.  This bound improves on the general PRDN linking rate.  Moreover,
as explained in
Remark~\ref{rem:prdn-pvalues}, the two-sided null $p$-values in this class
satisfy the PRDN property by the
absolute-value Gaussian multivariate total positivity of order
two (MTP$_2$) criterion of \citet{KarlinRinott1981}.
For one-sided one-common-factor models,
Theorem~\ref{thm:one-upper} and Corollary~\ref{cor:one-sharp} give
\[
 \sup_{\substack{m\in\N,\ \theta\in\R^m,\\
                    a\in[-1,1]^m}}
 \FDR_{\theta,a}(\BH_q)
 =\left\{\frac1{\sqrt\pi}+o(1)\right\}
 q\sqrt{\log(1/q)}.
\]
This matches the leading constant in $\ell_{\le}(q)$.  Both bounds are
uniform over the number of hypotheses, means, and scalar loadings.

We conclude the section with a new conjecture that neither the author nor
GPT 5.6 Sol was able to disprove after significant efforts.

\begin{conjecture}
The unrestricted Gaussian worst-case FDR satisfies
\[
\lim_{q\downarrow0}
\frac{
\displaystyle
\sup_{\substack{N\in\N,\ \theta\in\R^N,\ \Sigma\in\mathbb S_+^N\\
\Sigma_{ii}=1,\ 1\le i\le N}}
\FDR_{\theta,\Sigma}(\BH_q)}
{q\sqrt{\log(1/q)}}
=
\begin{cases}
\dfrac{1}{2\sqrt{\pi}},&\text{for two-sided tests},\\[4pt]
\dfrac{1}{\sqrt{\pi}},&\text{for one-sided tests}.
\end{cases}
\]
\end{conjecture}

\section{\texorpdfstring{Lower bound for two-sided tests}{Lower bound for two-sided tests}}

\subsection{Main result}

\begin{equation}
M(y)=\sup_{a\ge0}e^{-a^2/2}\cosh(ay).
\end{equation}
Appendix~\ref{app:envelope} identifies the likelihood-ratio envelope: $M=1$ on $[0,1]$, and $M$ is continuous, strictly increasing, and unbounded on $(1,\infty)$.  Hence there is a unique $y_q>1$ such that
\begin{equation}
qM(y_q)=1.
\label{eq:yq}
\end{equation}
Set
\begin{equation}
\ell_{=}(q)=q\Phi(1)+q\int_1^{y_q}M(y)\phi(y)\dd y+\Phib(y_q).
\label{eq:ell}
\end{equation}

The next theorem shows that the lower bound can be approached
arbitrarily closely by finite-dimensional Gaussian models with positive
definite correlation matrices.
\begin{theorem}
\label{thm:main}
For $T\sim N(\theta,\Sigma)$, let
$\FDR_{\theta,\Sigma}(\BH_q)$ denote the FDR of $\BH_q$ applied to the
two-sided $p$-values $p(|T_1|),\ldots,p(|T_N|)$.
For every $q\in(0,1)$ and $\delta>0$, there are $N\in\N$,
$\theta\in\R^N$, and a positive definite correlation matrix
$\Sigma$ such that
\begin{equation}
\FDR_{\theta,\Sigma}(\BH_q)>{\ell_{=}}(q)-\delta.
\label{eq:main}
\end{equation}
Consequently,
\begin{equation}
\sup_{\substack{N\in\N,\ \theta\in\R^N,\\
\Sigma\succ0,\ \diag(\Sigma)=\mathbf 1_N}}
\FDR_{\theta,\Sigma}(\BH_q)
\ge \ell_{=}(q).
\label{eq:sup}
\end{equation}
\end{theorem}

The next proposition gives the small-$q$ expansion of the lower bound.
\begin{proposition}
\label{prop:ell-expansion}
As $q\downarrow0$,
\[
\ell_{=}(q)
=
\frac{q\sqrt{\log(1/q)}}{2\sqrt{\pi}}
+{c_\ell}q+o(q),
\]
where
\[
\begin{aligned}
c_\ell
&=
\Phi(1)-\frac{1}{2\sqrt{2\pi}}
+\int_1^\infty
\left\{
M(y)\phi(y)-\frac{1}{2\sqrt{2\pi}}
\right\}\dd y\\
&=0.6492828\ldots.
\end{aligned}
\]
\end{proposition}

Proposition~\ref{prop:ell-strict} further shows that
${\ell_{=}}(q)>q$ for every $q\in(0,1)$.
Together with Theorem~\ref{thm:main}, this implies that BH fails
to control the FDR at every nontrivial nominal level in the correlated
two-sided Gaussian setting.
\begin{proposition}
\label{prop:ell-strict}
For every $q\in(0,1)$,
\[
\ell_{=}(q)>q.
\]
\end{proposition}

Figure~\ref{fig:ellq} in the Introduction displays the numerical
behavior of the two-sided lower bound.
Table~\ref{tab:common-q} gives the absolute inflation
${\ell_{=}}(q)-q$ and relative inflation ${\ell_{=}}(q)/q$ for commonly
used nominal levels.

\subsection{Roadmap}
\label{sec:roadmap}


Fix $q\in(0,1)$ and a design law $\nu_q$.  Let
$\Omega_N=((\Theta_1,B_1),\ldots,(\Theta_N,B_N))$, where the pairs are
i.i.d. draws from $\nu_q$, independently of
$Z,\varepsilon_1,\ldots,\varepsilon_N
{\stackrel{\text{i.i.d.}}{\sim}}N(0,1)$,
and set
\[
T_i=\Theta_i+B_iZ+\sqrt{1-B_i^2}\,\varepsilon_i,
\quad i=1,\ldots,N.
\]
Conditional on a realization of $\Omega_N$, this is a finite deterministic
Gaussian design.  Since BH is a step-up procedure, its rejection set is
$\{i:|T_i|\ge\widehat C_N\}$.  We will show in
Subsection~\ref{sec:finite-transfer} that, conditional on $Z=z$,
$\widehat C_N\to C(z)$ and $\FDP\to D(z)$, where convergence is defined
in an appropriate sense.  Consequently,
\[
\mathbb E_{\Omega_N}\!\left[\FDR_{\Omega_N}(\BH_q)\right]
=
\mathbb E_{\Omega_N,Z,\varepsilon}[\FDP]
\longrightarrow
\mathbb E[D(Z)].
\]
Thus, for any $\delta>0$ and all sufficiently large $N$, at least one
deterministic realization $\omega_N$ of $\Omega_N$ satisfies
\[
\FDR_{\omega_N}(\BH_q)\ge\mathbb E[D(Z)]-\delta.
\]

We next construct a family of laws $\nu_{q,r}$.  Write $D_r$ for the
conditional FDP limit associated with $\nu_{q,r}$.  For every
$z\notin\{-1,-y_q\}$, we prove that $D_r(z)\to D_*(z)$ as
$r\downarrow0$, where
\[
D_*(z)=
\begin{cases}
q,&z\ge-1,\\
qM(-z),&-y_q<z<-1,\\
1,&z\le-y_q.
\end{cases}
\]
Because $0\le D_r,D_*\le1$, dominated convergence then gives
\[
\mathbb E[D_r(Z)]\longrightarrow\mathbb E[D_*(Z)]=\ell_{=}(q).
\]
Then we can prove the lower bound \eqref{eq:sup} in
Theorem~\ref{thm:main} by taking $N$ to approach infinity first and $r$
to approach zero. To convert the supremum to a bound in \eqref{eq:main},
we just need to The argument therefore takes the iterated limit
$\lim_{r\downarrow0}\lim_{N\to\infty}$: first $N\to\infty$ for each
fixed $r$, and then $r\downarrow0$.  To obtain a single finite example,
we choose $r$ sufficiently small and then $N$ sufficiently large.  A
small independent Gaussian perturbation finally makes its covariance matrix
positive definite.


\subsection{Population quantities}
\label{sec:generic}

Put $u_q=p^{-1}(q)$.  Let $\nu_q$ be a probability measure on $\R\times[-1,1]$.  Write
\begin{equation}
\pi_0=\nu_q(\{0\}\times[-1,1]),
\label{eq:pi0-generic}
\end{equation}
and assume $\pi_0>0$.

For $(\theta,b)\in\R\times[-1,1]$, $z\in\R$, and $s\in(0,1]$, let $u_s=p^{-1}(s)$ and define
\[
F_{\theta,b,z}(s)
=
\mathbb P\!\left\{
p(|T_i|)\le s
\,\middle|\,
\Theta_i=\theta,\ B_i=b,\ Z=z
\right\}.
\]
If $|b|<1$, then
\begin{equation}
F_{\theta,b,z}(s)
=
\Phib\!\left(\frac{u_s-\theta-bz}{\sqrt{1-b^2}}\right)
+
\Phib\!\left(\frac{u_s+\theta+bz}{\sqrt{1-b^2}}\right).
\label{eq:Ftheta-formula}
\end{equation}
If $|b|=1$, then
\begin{equation}
F_{\theta,b,z}(s)
=
\1\{p(|\theta+bz|)\le s\}.
\label{eq:Ftheta-degenerate}
\end{equation}
Set $F_{\theta,b,z}(0)=0$.

Conditional on $Z=z$, the CDFs of the mixture $p$-value
and the null $p$-value are
\begin{align}
R_z(s)
&=
\int F_{\theta,b,z}(s)\,\nu_q(\dd\theta,\dd b),
\label{eq:Rz-generic}\\
R_{0,z}(s)
&=
\frac1{\pi_0}
\int_{\{0\}\times[-1,1]}
F_{0,b,z}(s)\,\nu_q(\dd\theta,\dd b).
\end{align}
For $c\ge u_q$, define the normalized quantities
\begin{align}
\bar R_z(c)
&=
\frac{qR_z\{p(c)\}}{p(c)},
\\
\bar R_{0,z}(c)
&=
\frac{q\pi_0R_{0,z}\{p(c)\}}{p(c)}.
\end{align}
Then the limiting cutoff can be written as
\begin{equation}
C(z)
=
\inf\{c\ge u_q:\bar R_z(c)\ge1\}.
\end{equation}
Here and below, $\inf\varnothing=\infty$.  The limiting conditional
FDP is
defined by
\begin{equation}
D(z)=
\begin{cases}
\bar R_{0,z}\{C(z)\},&C(z)<\infty,\\
0,&C(z)=\infty.
\end{cases}
\label{eq:D-generic}
\end{equation}

We call a finite cutoff a regular first crossing when it satisfies the following requirements.
\begin{definition}
\label{def:regular}
A finite cutoff $C(z)>u_q$ is regular if
\begin{align}
\sup_{u_q\le c\le C(z)-\rho}\bar R_z(c)&<1
&&\text{for every }0<\rho<C(z)-u_q,
\label{eq:regular-left}\\
\sup_{C(z)<c<C(z)+\rho}\bar R_z(c)&>1
&&\text{for every }\rho>0,
\label{eq:regular-right}
\end{align}
and $c\mapsto\bar R_{0,z}(c)$ is continuous at $C(z)$.
\end{definition}

The following proposition reduces regularity to a local monotonicity
check.
\begin{proposition}
\label{prop:local-regularity}
Let $C(z)>u_q$ be finite.  Suppose there exist
$u_q<a<C(z)<b$ such that the map
$c\mapsto\bar R_z(c)$ is differentiable on $(a,b)$ and
satisfies
\begin{equation}
 \bar R_z'(c)>0,
 \qquad a<c<b.
 \label{eq:local-regularity-positive-derivative}
\end{equation}
Suppose also that $c\mapsto\bar R_{0,z}(c)$ is continuous at $C(z)$.
Then $C(z)$ is regular.
\end{proposition}

\begin{proof}
The map $c\mapsto R_z\{p(c)\}$ is a survival function and hence is
upper semicontinuous.  Since $p$ is positive and continuous,
$c\mapsto\bar R_z(c)$ is also upper semicontinuous.  By the definition
of $C(z)$, $\bar R_z(c)<1$ for every $c<C(z)$.  Therefore, for every
$0<\rho<C(z)-u_q$, upper semicontinuity and compactness give
\[
 \sup_{u_q\le c\le C(z)-\rho}\bar R_z(c)<1,
\]
which proves \eqref{eq:regular-left}.

By the definition of $C(z)$, there is a sequence
$c_n\geq C(z)$ decreasing to $C(z)$ such that
$\bar R_z(c_n)\geq1$.  Continuity on $(a,b)$ gives
$\bar R_z\{C(z)\}\geq1$.  On the other hand, for any sequence
$d_n<C(z)$ increasing to $C(z)$, the first-crossing definition gives
$\bar R_z(d_n)<1$, so continuity gives
$\bar R_z\{C(z)\}\leq1$.  Hence
$\bar R_z\{C(z)\}=1$.  The mean value theorem and
\eqref{eq:local-regularity-positive-derivative} imply strict monotonicity
on $(a,b)$, which yields
\[
 \bar R_z(c)>1\quad\text{for }C(z)<c<b.
\]
This gives \eqref{eq:regular-right}.  Continuity of the null contribution at
$C(z)$ completes Definition~\ref{def:regular}.
\end{proof}

\subsection{Limiting cutoff and FDR}
\label{sec:finite-transfer}

Let
\begin{equation}
\Omega_N=((\Theta_1,B_1),\ldots,(\Theta_N,B_N)),
\quad
(\Theta_i,B_i){\stackrel{\text{i.i.d.}}{\sim}}\nu_q.
\end{equation}
Since the distribution of $(T_1,\ldots,T_N)$ is fully determined by $\Omega_N$, we write $\FDR_{\theta,\Sigma}(\BH_q)$ as $\FDR_{\Omega_N}(\BH_q)$.

Define $P_i=p(|T_i|)$.

\begin{align}
\widehat R_N(s)
&=
\frac1N\sum_{i=1}^N\1\{P_i\le s\},
\\
\widehat R_{0,N}(s)
&=
\frac1N\sum_{i=1}^N\1\{\Theta_i=0,\ P_i\le s\}.
\end{align}

The following lemma gives a uniform conditional empirical-CDF bound.
For a function $f$ on $[0,1]$, write
$\|f\|_{\infty,[0,1]}=\sup_{0\le s\le1}|f(s)|$.
\begin{lemma}
\label{lem:DKW}
For every $z\in\R$ and $t>0$,
\begin{equation}
\mathbb P\!\left(
\max\left\{
\|\widehat R_N-R_z\|_{\infty,[0,1]},
\|\widehat R_{0,N}-\pi_0R_{0,z}\|_{\infty,[0,1]}
\right\}>t
\,\middle|\,Z=z
\right)
\le4e^{-2Nt^2}.
\end{equation}
\end{lemma}

\begin{proof}
Conditional on $Z=z$, the $P_i$ are i.i.d. with CDF $R_z$.  Also define
\[
W_i=P_i\1\{\Theta_i=0\}+2\1\{\Theta_i\ne0\}.
\]
For $0\le s\le1$,
\[
\1\{W_i\le s\}
=
\1\{\Theta_i=0,\ P_i\le s\},
\quad
\mathbb P(W_i\le s\mid Z=z)=\pi_0R_{0,z}(s).
\]
Apply the Dvoretzky-Kiefer-Wolfowitz inequality twice and take a union bound.
\end{proof}

The next lemma gives an exact characterization of the BH cutoff and FDP through the empirical CDFs.
\begin{lemma}
\label{lem:exact-BH}
Let $R_N$ be the number of BH rejections and put
\begin{equation}
\widehat\tau_N=\frac{qR_N}{N}.
\end{equation}
If $R_N\ge1$, then
\begin{equation}
\widehat R_N(\widehat\tau_N)=\frac{R_N}{N},
\quad
\FDP
=
\frac{q\widehat R_{0,N}(\widehat\tau_N)}{\widehat\tau_N}.
\label{eq:exact-FDP}
\end{equation}
With $\widehat C_N=p^{-1}(\widehat\tau_N)$,
\begin{equation}
\widehat C_N
=
\inf\left\{
 c\ge u_q:
 \frac{q\widehat R_N\{p(c)\}}{p(c)}\ge1
\right\}.
\label{eq:exact-C}
\end{equation}
Then the BH rejection set is $\{i:|T_i|\ge\widehat C_N\}$.
If $R_N=0$, the set in \eqref{eq:exact-C} is empty and $\widehat C_N=\infty$.
\end{lemma}

\begin{proof}
Let $P_{(1)}\le\cdots\le P_{(N)}$.  If more than $R_N$ values were at most $qR_N/N$, then
\[
P_{(R_N+1)}\le qR_N/N<q(R_N+1)/N,
\]
contradicting the maximality of $R_N$.  Hence $N\widehat R_N(\widehat\tau_N)=R_N$, and \eqref{eq:exact-FDP} follows.  Since $p$ is decreasing, the BH step-up definition is equivalent to \eqref{eq:exact-C}.
\end{proof}

The next theorem establishes the limiting cutoff conditional
on the common factor $Z$.
\begin{theorem}
\label{thm:population-transfer}
Assume that $C(z)$ is regular for almost every $z$.  Then, for every
$z$ at which $C(z)$ is regular, conditional on $Z=z$,
\begin{equation}
\widehat C_N\longrightarrow C(z),
\quad
\FDP\longrightarrow D(z)
=\bar R_{0,z}\{C(z)\}
=\frac{q\pi_0R_{0,z}[p\{C(z)\}]}{p\{C(z)\}}
\label{eq:conditional-transfer}
\end{equation}
in probability.  Consequently,
\begin{equation}
\lim_{N\to\infty}
\mathbb E_{\Omega_N}
\bigl[\FDR_{\Omega_N}(\BH_q)\bigr]
=
\mathbb E[D(Z)],
\label{eq:expected-transfer}
\end{equation}
where
\begin{equation}
\FDR_{\Omega_N}(\BH_q)
=
\mathbb E_{Z,\varepsilon}\!\left[
\FDP\mid\Omega_N
\right].
\label{eq:FDRomega}
\end{equation}
\end{theorem}

\begin{proof}
Fix a regular $z$ and $\rho,\tau>0$.  Since $D(z)=\bar R_{0,z}\{C(z)\}$ and $c\mapsto\bar R_{0,z}(c)$ is continuous at $C(z)$, choose
\[
0<\rho(z)<\min\{\rho,C(z)-u_q\}
\]
so that
\begin{equation}
\sup_{C(z)-\rho(z)\le c\le C(z)+\rho(z)}
|\bar R_{0,z}(c)-D(z)|\le\tau.
\label{eq:crossing-bracket}
\end{equation}
Set $A(z)=C(z)-\rho(z)$.  Equation~\eqref{eq:regular-left} gives
$\sup_{u_q\le c\le A(z)}\bar R_z(c)<1$, and
\eqref{eq:regular-right} permits a choice of
$B(z)\in(C(z),C(z)+\rho(z))$ with $\bar R_z\{B(z)\}>1$.
Set
\[
\gamma(z)
=
\frac12\min\left\{
1-\sup_{u_q\le c\le A(z)}\bar R_z(c),\quad
\bar R_z\{B(z)\}-1
\right\}>0.
\]
Put
\[
E_N(z)=
\max\left\{
\|\widehat R_N-R_z\|_{\infty,[0,1]},
\|\widehat R_{0,N}-\pi_0R_{0,z}\|_{\infty,[0,1]}
\right\}.
\]
Lemma~\ref{lem:DKW} gives $E_N(z)\to0$ in probability conditional on
$Z=z$.  For every $u_q\le c\le B(z)$,
\begin{equation}
\begin{aligned}
\left|
\frac{q\widehat R_N\{p(c)\}}{p(c)}-\bar R_z(c)
\right|
&\le \frac{qE_N(z)}{p\{B(z)\}},\\
\left|
\frac{q\widehat R_{0,N}\{p(c)\}}{p(c)}-\bar R_{0,z}(c)
\right|
&\le \frac{qE_N(z)}{p\{B(z)\}}.
\end{aligned}
\label{eq:empirical-uniform-bound}
\end{equation}
By the empirical curve we mean
\[
c\longmapsto
\frac{q\widehat R_N\{p(c)\}}{p(c)}.
\]
On the event $qE_N(z)/p\{B(z)\}<\gamma(z)$, the definition of
$\gamma(z)$ and \eqref{eq:empirical-uniform-bound} give
\[
\begin{aligned}
\sup_{u_q\le c\le A(z)}
\frac{q\widehat R_N\{p(c)\}}{p(c)}
&\le
\sup_{u_q\le c\le A(z)}\bar R_z(c)
+\frac{qE_N(z)}{p\{B(z)\}}\\
&<1-2\gamma(z)+\gamma(z)<1,
\end{aligned}
\]
whereas
\[
\frac{q\widehat R_N\{p(B(z))\}}{p(B(z))}
\ge
\bar R_z\{B(z)\}
-\frac{qE_N(z)}{p\{B(z)\}}
>1+2\gamma(z)-\gamma(z)>1.
\]
Lemma~\ref{lem:exact-BH} and \eqref{eq:crossing-bracket} therefore give
\[
A(z)<\widehat C_N\le B(z),
\qquad
|\FDP-D(z)|
\le
\tau+\frac{qE_N(z)}{p\{B(z)\}}.
\]
Because $\rho,\tau>0$ were arbitrary, this proves
\eqref{eq:conditional-transfer} at every regular $z$.

For completeness, the quantities in the expectation can be taken to be
measurable without making a measurable selection of $B(z)$.  The maps
$(z,c)\mapsto\bar R_z(c)$ and
$(z,c)\mapsto\bar R_{0,z}(c)$ are jointly Borel measurable, and the first
is left-continuous in $c$.  Define
\[
C^\circ(z)
=
\inf\{c\in\mathbb Q:c\ge u_q,\ \bar R_z(c)>1\}.
\]
At every regular $z$, left continuity and
\eqref{eq:regular-right} imply $C^\circ(z)=C(z)$.  Thus $C$ has a
measurable version.  Moreover, for $c<C(z)$,
$\bar R_{0,z}(c)\le\bar R_z(c)<1$; continuity of the null contribution at the
crossing gives $0\le D(z)\le1$.  Hence
\[
D^\circ(z)
=
\begin{cases}
\min\bigl[1,\bar R_{0,z}\{C^\circ(z)\}\bigr],&C^\circ(z)<\infty,\\
0,&C^\circ(z)=\infty,
\end{cases}
\]
is a measurable $[0,1]$-valued version of $D(z)$ at almost every
$z$.  Use these versions below.  Conditional convergence in probability,
together with boundedness, now yields
\[
\mathbb E\bigl[|\FDP-D(z)|\mid Z=z\bigr]\longrightarrow0
\quad\text{for almost every }z.
\]
Dominated convergence and the tower property give
\[
\mathbb E_{\Omega_N,Z,\varepsilon}
\bigl[|\FDP-D(Z)|\bigr]\longrightarrow0,
\]
and a second application of the tower property yields
\eqref{eq:expected-transfer}.
\end{proof}

Lastly, we show that $\Sigma$ can be made positive definite
by an independent Gaussian perturbation.  For a fixed realization
$\omega=((\theta_i,b_i))_{i=1}^N$, let $\xi\sim N(0,I_N)$ be independent and define
\begin{equation}
T_i^{(\eta)}
=
\theta_i
+
\sqrt{1-\eta^2}
\left(
 b_iZ+\sqrt{1-b_i^2}\,\varepsilon_i
\right)
+
\eta\xi_i,
\quad 0<\eta<1.
\label{eq:eta-model}
\end{equation}
Then
\begin{equation}
\Sigma_{\omega,\eta}
=
(1-\eta^2)
\left[
bb^\top+\diag(1-b_1^2,\ldots,1-b_N^2)
\right]
+
\eta^2I_N.
\label{eq:eta-cov}
\end{equation}

The following lemma shows that the perturbation makes the
correlation matrix positive definite while preserving the FDR in the limit.
\begin{lemma}
\label{lem:eta}
For every fixed $\omega$,
\begin{equation}
\diag(\Sigma_{\omega,\eta})=\mathbf 1_N,
\quad
\Sigma_{\omega,\eta}\succeq\eta^2I_N,
\label{eq:eta-PD}
\end{equation}
and
\begin{equation}
\FDR_{\omega}^{(\eta)}(\BH_q)
\longrightarrow
\FDR_{\omega}(\BH_q)
\quad(\eta\downarrow0).
\label{eq:eta-continuity}
\end{equation}
\end{lemma}

\begin{proof}
Equation \eqref{eq:eta-PD} is immediate from \eqref{eq:eta-cov}.  Under the coupling \eqref{eq:eta-model}, $T^{(\eta)}\to T$ almost surely.  Define
$P_i^{(\eta)}=p(|T_i^{(\eta)}|)$.  Then
$P_i^{(\eta)}\to P_i=p(|T_i|)$ almost surely.  Each $P_i$ has a continuous marginal law, so
\[
\mathbb P\left\{
P_i\in\left\{\frac{qk}{N}:1\le k\le N\right\}
\text{ for some }i
\right\}=0.
\]
Outside of this event,
$P_i^{(\eta)}\le qk/N$ if and only if
$P_i\le qk/N$ for when $\eta$ is sufficiently small.  Hence the BH rejection
set remains constant for sufficiently small $\eta$.  Bounded convergence proves \eqref{eq:eta-continuity}.
\end{proof}

{\subsection{Construction of
\texorpdfstring{$\nu_{q,r}$}{nu(q,r)}}}
\label{sec:continuum-design}

We construct a family of laws $\nu_{q,r}$ indexed by $r\downarrow0$.  For $a,y\ge0$, put
{\[
L_a(y)=e^{-a^2/2}\cosh(ay).
\]}
For $y>1$, let
{\[
a(y)=\operatorname*{arg\,max}_{\alpha\ge0} L_\alpha(y),
\quad
y(\alpha)=a^{-1}(\alpha),\quad \alpha>0.
\]}
Set
\begin{equation}
a_q=a(y_q).
\label{eq:aq-def}
\end{equation}
Appendix~\ref{app:envelope} establishes the properties of these functions that we use below.

The quantities $b_r,\tau_r,\mu_r,\pi_{0,r}$, and $c_r$ are defined below.  The law $\nu_{q,r}$ has the three components displayed in Table~\ref{tab:two-construction}.

\begin{table}[ht]

\centering
\caption{Two-sided population construction defining $\nu_{q,r}$.}
\label{tab:two-construction}
\begin{tabular}{lccc}
\toprule
Type & Mass & $\Theta$ & $B$\\
\midrule
Nulls & $\pi_{0,r}$ & $0$ & $r$\\
Primary non-nulls & $r$ & $c_r+y(b_r)$ & $1$\\
Secondary non-nulls & $\tau_r\mu_r(\dd a)$ & $a/r+y(a)$ &
$1$, $a\in[b_r,a_q]$\\
\bottomrule
\end{tabular}
\end{table}

Equivalently, for every bounded measurable $f:\R\times[-1,1]\to\R$,
\begin{equation}
\int f\,\dd\nu_{q,r}
=\pi_{0,r}f(0,r)+r f(c_r+y(b_r),1)
+\tau_r\int_{b_r}^{a_q}f\!\left(\frac ar+y(a),1\right)\mu_r(\dd a).
\label{eq:nuqr}
\end{equation}

\noindent\textbf{Definition of secondary non-nulls.}
For small $r$, set
{\[
b_r=r\,p^{-1}(r^2).
\]}
For the remaining definitions, take $r$ small enough that $0<b_r<a_q$.
For $a\in[b_r,a_q]$, define
\begin{equation}
W_r(a)=\frac{\bigl[1-qM\{y(a)\}\bigr]p(a/r)}q.
\label{eq:Wr}
\end{equation}
By Lemma~\ref{lem:envelope} and \eqref{eq:deficit-properties}, the factor $1-qM\{y(a)\}$ is nonnegative and decreasing on $[b_r,a_q]$; the factor $p(a/r)$ is decreasing in $a$.  Hence $W_r$ is continuous and decreasing, with $W_r(a_q)=0$.
Set
\begin{equation}
\tau_r
:=
W_r(b_r)
=
\frac{\bigl[1-qM\{y(b_r)\}\bigr]r^2}{q}
=O(r^2).
\label{eq:taur}
\end{equation}
We therefore call this the secondary non-null block; its total
mass is $O(r^2)=o(r)$.
Let $\mu_r$ be the probability measure on $[b_r,a_q]$ determined by
\begin{equation}
\mu_r([a,a_q])=\frac{W_r(a)}{\tau_r},
\quad b_r\le a\le a_q.
\label{eq:mur-survival}
\end{equation}
In particular, $\mu_r([b_r,a_q])=W_r(b_r)/\tau_r=1$.
~\\
~\\
\noindent\textbf{Definition of nulls.}
Put
\[
\pi_{0,r}=1-r-\tau_r.
\]
Since $\pi_{0,r}+r+\tau_r=1$, the masses in \eqref{eq:nuqr} define a probability measure.

\medskip
\noindent\textbf{Definition of primary non-nulls.}
For all sufficiently small $r$, $\pi_{0,r}>0$.  Define $c_r$ by
\begin{equation}
p(c_r)
=
\frac{q(r+\tau_r)}{1-q\pi_{0,r}}.
\label{eq:cr}
\end{equation}
The numerator is positive.  Since $\tau_r=O(r^2)$ and $\pi_{0,r}=1-r-\tau_r$,
\[
1-q\pi_{0,r}=1-q+qr+q\tau_r\longrightarrow1-q>0,
\quad
q(r+\tau_r)\longrightarrow0.
\]
Thus the right side of \eqref{eq:cr} is positive and smaller than one for small $r$, so $c_r$ is well-defined.

\subsection{Population FDR analysis under \texorpdfstring{$\nu_{q,r}$}{nu(q,r)}}

\subsubsection{Preliminaries}

Apply Subsection~\ref{sec:generic} with $\nu_q=\nu_{q,r}$.  Denote the resulting quantities by
\[
R_{r,z},
\quad
R_{0,r,z},
\quad
\bar R_{r,z},
\quad
\bar R_{0,r,z},
\quad
C_r(z).
\]
For $c\ge u_q$,
\begin{equation}
\bar R_{r,z}(c)
=\bar R_{0,r,z}(c)+\bar R_{1,r,z}(c)+\bar R_{2,r,z}(c),
\label{eq:population-curve}
\end{equation}
where
\begin{align}
\bar R_{0,r,z}(c)
&=
q\pi_{0,r}
\frac{R_{0,r,z}\{p(c)\}}{p(c)},
\\
\bar R_{1,r,z}(c)
&=
\frac{qr}{p(c)}
\1\{|c_r+y(b_r)+z|\ge c\},
\notag\\
\bar R_{2,r,z}(c)
&=
\frac{q\tau_r}{p(c)}
\int_{b_r}^{a_q}
\1\!\left\{
\left|\frac ar+y(a)+z\right|\ge c
\right\}
\mu_r(\dd a).
\notag
\end{align}
For a measurable definition at every $z$, put
\[
 C_r^\circ(z)
 =\inf\{c\in\mathbb Q:c\ge u_q,\ \bar R_{r,z}(c)>1\}
\]
and define
\[
 D_r(z)=
 \begin{cases}
 \min\bigl[1,\bar R_{0,r,z}\{C_r^\circ(z)\}\bigr],
     &C_r^\circ(z)<\infty,\\
 0,&C_r^\circ(z)=\infty.
 \end{cases}
\]
The joint Borel measurability of $(z,c)\mapsto\bar R_{r,z}(c)$ and
$(z,c)\mapsto\bar R_{0,r,z}(c)$ makes both $C_r^\circ$ and $D_r$
Borel measurable.  At every regular crossing, the rational-cutoff argument
in the proof of Theorem~\ref{thm:population-transfer} gives
$C_r^\circ(z)=C_r(z)$, and $\bar R_{0,r,z}\{C_r(z)\}\le1$.  Hence
\begin{equation}
D_r(z)=\bar R_{0,r,z}\{C_r(z)\}.
\label{eq:Dr}
\end{equation}
Moreover, $0\le D_r(z)\le1$ for every $z$.

We next state two asymptotic lemmas that will be applied in the following
analysis.  The first gives the order of $b_r$ and $c_r$ as
$r\downarrow0$.
\begin{lemma}
\label{lem:scale-properties}
As $r\downarrow0$,
\begin{equation}
b_r\downarrow0,
\quad
\frac{b_r}{r}=p^{-1}(r^2)\to\infty,
\quad
p(b_r/r)=r^2,
\quad
y(b_r)\downarrow1.
\label{eq:br-properties}
\end{equation}
Moreover,
\begin{equation}
p(c_r)\sim\frac{qr}{1-q},
\quad
c_r\to\infty,
\quad
rc_r\to0,
\quad
\frac{b_r}{r}-c_r\to\infty.
\label{eq:cr-properties}
\end{equation}
\end{lemma}

\begin{proof}
The identity $p(b_r/r)=r^2$ follows directly from $b_r=r\,p^{-1}(r^2)$.  Applying \eqref{eq:mills-quantile} in Lemma~\ref{lem:mills} gives
\[
\frac{b_r}{r}
=p^{-1}(r^2)
\sim
\sqrt{4\log(1/r)}
\to\infty,
\quad
b_r
\sim
2r\sqrt{\log(1/r)}
\to0.
\]
The last limit in \eqref{eq:br-properties} follows from Lemma~\ref{lem:envelope}: $a(y)$ is continuous and strictly increasing from $(1,\infty)$ onto $(0,\infty)$, with $\lim_{y\downarrow1}a(y)=0$.  Since $y(\cdot)$ is its inverse and $b_r\downarrow0$, we have $y(b_r)\downarrow1$.

By \eqref{eq:cr} and \eqref{eq:taur},
\[
p(c_r)
=
\frac{q(r+\tau_r)}{1-q\pi_{0,r}}
\sim
\frac{qr}{1-q}.
\]
{For every fixed
$\delta\in(0,q/(1-q))$, for all sufficiently small $r$,
\[
 \left\{\frac{q}{1-q}-\delta\right\}r
 \le p(c_r)\le
 \left\{\frac{q}{1-q}+\delta\right\}r.
\]
Since $p^{-1}$ is decreasing,
\[
 p^{-1}\!\left(\left\{\frac{q}{1-q}+\delta\right\}r\right)
 \le c_r
 \le p^{-1}\!\left(\left\{\frac{q}{1-q}-\delta\right\}r\right).
\]
Equation~\eqref{eq:mills-quantile} in Lemma~\ref{lem:mills}, applied to
the two fixed positive constants, shows that both endpoints are
asymptotic to $\sqrt{2\log(1/r)}$.  Hence
\[
c_r\sim\sqrt{2\log(1/r)}.
\]}
Hence $c_r\to\infty$ and $rc_r\to0$.  Combining this with
\[
\frac{b_r}{r}
=p^{-1}(r^2)
\sim
\sqrt{4\log(1/r)}
\]
gives
\[
\frac{b_r}{r}-c_r
\sim
\left(2-\sqrt2\right)\sqrt{\log(1/r)}
\longrightarrow\infty.
\]
\end{proof}

The next lemma gives a uniform approximation to the normalized
conditional FDP contribution from nulls.
\begin{lemma}
\label{lem:null-tail}
For every $A>0$ and $T\ge0$, as $r\downarrow0$,
\begin{equation}
\sup_{|z|\le T}
\sup_{0\le c\le A/r}
\left|
\frac{R_{0,r,z}\{p(c)\}}{p(c)}
-L_{rc}(|z|)
\right|
\longrightarrow0.
\label{eq:null-tail}
\end{equation}
\end{lemma}

\begin{proof}
For $0<r<1$, the null pair $(\Theta,B)=(0,r)$ gives
\[
R_{0,r,z}\{p(c)\}
=
\mathbb P\{|rz+\sqrt{1-r^2}\,\varepsilon|\ge c\}.
\]
Write
\[
x_\pm=\frac{c\mp rz}{\sqrt{1-r^2}}.
\]
Then
\[
R_{0,r,z}\{p(c)\}=\Phib(x_+)+\Phib(x_-).
\]
Fix $C>0$.  Uniformly for $|z|\le T$ and $C\le c\le A/r$,
\[
\begin{aligned}
x_\pm-c
&=c\left\{\frac1{\sqrt{1-r^2}}-1\right\}
\mp\frac{rz}{\sqrt{1-r^2}}\\
&=\frac{cr^2}{\sqrt{1-r^2}\{1+\sqrt{1-r^2}\}}
\mp\frac{rz}{\sqrt{1-r^2}}.
\end{aligned}
\]
Therefore,
\[
|x_\pm-c|
\le
\frac{Ar}{\sqrt{1-r^2}\{1+\sqrt{1-r^2}\}}
+\frac{Tr}{\sqrt{1-r^2}}
=O_{A,T}(r).
\]
Consequently, for all sufficiently small $r$, the shifts $x_\pm-c$ are
uniformly bounded and $x_\pm\ge C/2$.  The uniform expansion
\eqref{eq:mills-local-ratio} in Lemma~\ref{lem:mills} therefore gives
remainders $\rho_{r,C,\pm}(c,z)$ such that
\begin{equation}
\begin{aligned}
\frac{\Phib(x_\pm)}{\Phib(c)}
&=
\frac{c}{x_\pm}
\exp\left\{-\frac{x_\pm^2-c^2}{2}\right\}
\{1+\rho_{r,C,\pm}(c,z)\},\\
-\frac{x_\pm^2-c^2}{2}
&=
-\frac{(rc)^2}{2}\pm rcz+O_{A,T}(r^2).
\end{aligned}
\label{eq:null-tail-expansion}
\end{equation}
and
\begin{equation}
\lim_{C\to\infty}\limsup_{r\downarrow0}
\sup_{|z|\le T}\sup_{C\le c\le A/r}
\max_{\pm}|\rho_{r,C,\pm}(c,z)|=0.
\label{eq:null-tail-remainder}
\end{equation}
For each fixed $C>0$, $c/x_\pm\to1$ {uniformly for $|z|\le T$ and $C\le c\le A/r$} as
$r\downarrow0$.  To identify the leading term, put $t=rc$, so that
$0\le t\le A$.  Then
\[
\frac12\left[
\exp\left\{-\frac{t^2}{2}+tz\right\}
+\exp\left\{-\frac{t^2}{2}-tz\right\}
\right]
=e^{-t^2/2}\cosh(tz)
=L_t(|z|).
\]
Because $t$ and $z$ range over compact sets, these exponential factors
are uniformly bounded.  Thus, after summing the two tails in
\eqref{eq:null-tail-expansion} and using $p(c)=2\Phib(c)$, the errors from
$c/x_\pm-1$ and from the $O_{A,T}(r^2)$ term vanish uniformly for each
fixed $C$.  Consequently, there is a constant $K_{A,T}<\infty$, independent
of $C$, such that, for
\[
\eta(C)
=
\limsup_{r\downarrow0}
\sup_{|z|\le T}
\sup_{C\le c\le A/r}
\left|
\frac{R_{0,r,z}\{p(c)\}}{p(c)}
-L_{rc}(|z|)
\right|,
\]
we have
\[
\eta(C)
\le
K_{A,T}
\limsup_{r\downarrow0}
\sup_{|z|\le T}\sup_{C\le c\le A/r}
\max_{\pm}|\rho_{r,C,\pm}(c,z)|.
\]
The right side tends to zero as $C\to\infty$ by
\eqref{eq:null-tail-remainder}.  Hence $\eta(C)\to0$.

It remains to control $0\le c\le C$.  On this range, $p(c)\ge p(C)>0$.  Also, uniformly over $0\le c\le C$ and $|z|\le T$,
\[
R_{0,r,z}\{p(c)\}
=
\Phib\!\left(\frac{c-rz}{\sqrt{1-r^2}}\right)
+
\Phib\!\left(\frac{c+rz}{\sqrt{1-r^2}}\right)
=p(c)+O_{C,T}(r),
\]
because the two arguments differ from $c$ by $O_{C,T}(r)$ and $\Phib$ has bounded derivative.  Hence
\[
\sup_{|z|\le T}\sup_{0\le c\le C}
\left|
\frac{R_{0,r,z}\{p(c)\}}{p(c)}-1
\right|
\longrightarrow0.
\]
Moreover, $L_{rc}(|z|)=e^{-(rc)^2/2}\cosh(rc|z|)\to1$ {uniformly for $|z|\le T$ and $0\le c\le C$}.  Thus
\[
\limsup_{r\downarrow0}
\sup_{|z|\le T}
\sup_{0\le c\le A/r}
\left|
\frac{R_{0,r,z}\{p(c)\}}{p(c)}-L_{rc}(|z|)
\right|
\le \eta(C).
\]
Letting $C\to\infty$ proves the claim.
\end{proof}

The following lemma provides a generic criterion for deriving the limit of
$C_r(z)$.
\begin{lemma}
\label{lem:localized-crossing}
Let $K$ be compact.  For $z\in K$, let
$m_r(z)>u_q$ and $w_r(z)>0$.
Suppose that, for every fixed $H>0$,
\begin{equation}
 \inf_{z\in K}\{m_r(z)-Hw_r(z)\}>u_q
 \label{eq:localized-crossing-domain}
\end{equation}
for all sufficiently small $r$, and
\begin{equation}
 \sup_{z\in K}\sup_{|h|\le H}
 \left|
 \bar R_{r,z}\{m_r(z)+w_r(z)h\}
 -d(z)-\{1-d(z)\}e^{\xi(z)h}
 \right|\longrightarrow0,
 \label{eq:localized-crossing-full}
\end{equation}
where $d:K\to[0,1)$ and $\xi:K\to(0,\infty)$ are continuous.
Suppose also that, for every $h_0>0$,
\begin{equation}
 \limsup_{r\downarrow0}\sup_{z\in K}
 \sup_{u_q\le c\le m_r(z)-w_r(z)h_0}\bar R_{r,z}(c)<1.
 \label{eq:localized-crossing-left}
\end{equation}
Then
\begin{equation}
 \sup_{z\in K}
 \left|\frac{C_r(z)-m_r(z)}{w_r(z)}\right|
 \longrightarrow0.
 \label{eq:localized-crossing-cutoff}
\end{equation}
\end{lemma}

\begin{proof}
Fix $h_0>0$.  Compactness gives
\[
 \inf_{z\in K}
 \{1-d(z)\}\{e^{\xi(z)h_0}-1\}>0.
\]
Hence \eqref{eq:localized-crossing-full} gives
$\bar R_{r,z}\{m_r(z)+w_r(z)h_0\}>1$ uniformly on $K$, while
\eqref{eq:localized-crossing-left} excludes a crossing at or before
$m_r(z)-w_r(z)h_0$.  Thus
\[
 m_r(z)-w_r(z)h_0
 <C_r(z)
 \le m_r(z)+w_r(z)h_0
\]
uniformly on $K$.  Letting $h_0\downarrow0$ proves
\eqref{eq:localized-crossing-cutoff}.
\end{proof}

The next lemma gives regularity and the limiting null
contribution once the localized cutoff has been identified.
\begin{lemma}
\label{lem:localized-crossing-regularity}
Under the assumptions and notation of
Lemma~\ref{lem:localized-crossing}, assume in addition that, for every fixed
$H>0$,
\begin{equation}
 \sup_{z\in K}\sup_{|h|\le H}
 \left|\bar R_{0,r,z}\{m_r(z)+w_r(z)h\}-d(z)\right|
 \longrightarrow0.
 \label{eq:localized-crossing-null}
\end{equation}
If, for some $H_*>0$ and all sufficiently small $r$, the map
\[
 h\longmapsto \bar R_{r,z}\{m_r(z)+w_r(z)h\}
\]
is differentiable with positive derivative on $(-H_*,H_*)$, and
the map
$h\mapsto\bar R_{0,r,z}\{m_r(z)+w_r(z)h\}$ is continuous there for
every $z\in K$, then $C_r(z)$ is regular and
\begin{equation}
 \sup_{z\in K}
 \left|D_r(z)-d(z)\right|
 \longrightarrow0.
 \label{eq:localized-crossing-fdp}
\end{equation}
\end{lemma}

\begin{proof}
{
For all sufficiently small $r$, \eqref{eq:localized-crossing-cutoff}
gives
\[
 m_r(z)-w_r(z)H_*<C_r(z)<m_r(z)+w_r(z)H_*.
\]}
With
$c=m_r(z)+w_r(z)h$, the chain rule gives
\[
 \frac{\dd}{\dd h}
 \bar R_{r,z}\{m_r(z)+w_r(z)h\}
 =w_r(z)\bar R_{r,z}'(c).
\]
Since $w_r(z)>0$,
\[
 0<\frac{\dd}{\dd h}
 \bar R_{r,z}\{m_r(z)+w_r(z)h\}
 =w_r(z)\bar R_{r,z}'(c)
 \quad\Longrightarrow\quad
 \bar R_{r,z}'(c)>0.
\]
Thus
\begin{equation}
 \bar R_{r,z}'(c)>0,
 \qquad
 m_r(z)-w_r(z)H_*<c<m_r(z)+w_r(z)H_*.
 \label{eq:localized-positive-derivative}
\end{equation}
Equations~\eqref{eq:localized-crossing-cutoff} and
\eqref{eq:localized-crossing-domain}, together with
\eqref{eq:localized-positive-derivative}, verify the hypotheses of
Proposition~\ref{prop:local-regularity},
which gives regularity.
Finally, put
\[
 h_r(z)=\frac{C_r(z)-m_r(z)}{w_r(z)}.
\]
Equation~\eqref{eq:localized-crossing-cutoff} gives $h_r(z)\to0$
uniformly.  By \eqref{eq:Dr},
\[
 D_r(z)=\bar R_{0,r,z}\{C_r(z)\}
 =\bar R_{0,r,z}\{m_r(z)+w_r(z)h_r(z)\}.
\]
Evaluating \eqref{eq:localized-crossing-null} at $h=h_r(z)$ therefore
proves \eqref{eq:localized-crossing-fdp}.
\end{proof}

The next lemma derives the derivatives of the null and secondary
non-null contributions.
\begin{lemma}
\label{lem:two-block-derivatives}
For $c>0$, put
\[
 x_\pm=\frac{c\mp rz}{\sqrt{1-r^2}},
 \qquad
 Q_\pm(c,z)=\frac{\Phib(x_\pm)}{\Phib(c)}.
\]
The null contribution $\bar R_{0,r,z}(c)$ satisfies
\begin{align}
 \bar R_{0,r,z}'(c)
 &=\frac{q\pi_{0,r}}2
 \sum_{\sigma\in\{-,+\}}Q_\sigma(c,z)
 \left\{\lambda(c)-\frac{\lambda(x_\sigma)}{\sqrt{1-r^2}}\right\},
 \label{eq:two-null-block-derivative}\\
 \frac{\dd}{\dd c}\log\bar R_{0,r,z}(c)
 &=\lambda(c)-
 \frac{Q_+(c,z)\lambda(x_+)+Q_-(c,z)\lambda(x_-)}
 {\sqrt{1-r^2}\{Q_+(c,z)+Q_-(c,z)\}}.
 \label{eq:two-null-block-log-derivative}
\end{align}

Define
\begin{equation}
 g_r(a)=a+r y(a).
 \label{eq:gr}
\end{equation}
{
For $0<a<a_q$,
\[
 g_r'(a)=1+r y'(a)>1,
\]
so $g_r$ is strictly increasing on $[b_r,a_q]$.}
Finally, fix $y>1$ and $c>0$, and suppose that
\begin{equation}
 g_r(b_r)>r(y-c).
\label{eq:two-secondary-lower-tail}
\end{equation}
If
\[
 g_r(b_r)<r(c+y)<g_r(a_q),
\]
let $\beta_{r,y}(c)\in(b_r,a_q)$ be the unique solution of
\begin{equation}
 g_r\{\beta_{r,y}(c)\}=r(c+y).
\label{eq:two-secondary-threshold-equation}
\end{equation}
Conditional on $Z=-y$, a secondary non-null indexed by
$a\in[b_r,a_q]$ is then rejected at cutoff $c$ if and only if
\begin{equation}
 a\in[\beta_{r,y}(c),a_q].
\label{eq:two-secondary-rejection-set}
\end{equation}
Whenever
$1-qM\{y(\beta_{r,y}(c))\}>0$, the secondary non-null contribution
$\bar R_{2,r,-y}(c)$ satisfies
\begin{align}
 \frac{\partial\beta_{r,y}(c)}{\partial c}
 &=\frac{r}{1+r y'\{\beta_{r,y}(c)\}},
 \label{eq:two-secondary-threshold-derivative}\\
 \frac{\dd}{\dd c}\log\bar R_{2,r,-y}(c)
 &=-\frac{qM'\{y(\beta_{r,y}(c))\}y'\{\beta_{r,y}(c)\}}
 {1-qM\{y(\beta_{r,y}(c))\}}
 \frac{r}{1+r y'\{\beta_{r,y}(c)\}}
 \notag\\
 &\quad
 -\frac{\lambda\{\beta_{r,y}(c)/r\}}
 {1+r y'\{\beta_{r,y}(c)\}}+\lambda(c),
 \label{eq:two-secondary-block-log-derivative}\\
 \bar R_{2,r,-y}'(c)
 &=\bar R_{2,r,-y}(c)
 \frac{\dd}{\dd c}\log\bar R_{2,r,-y}(c).
 \label{eq:two-secondary-block-derivative}
\end{align}
If $r(c+y)\le g_r(b_r)$, the secondary non-null block is fully rejected.
Under the strict inequality $r(c+y)<g_r(b_r)$,
\[
 \bar R_{2,r,-y}(c)=\frac{q\tau_r}{p(c)},
 \qquad
 \bar R_{2,r,-y}'(c)
 =-\frac{q\tau_r p'(c)}{p(c)^2}
 =\lambda(c)\bar R_{2,r,-y}(c).
\]
If $r(c+y)\ge g_r(a_q)$, the secondary non-null contribution vanishes:
at equality the rejected set is $\{a_q\}$, which has $\mu_r$-measure
zero by \eqref{eq:mur-survival} and $W_r(a_q)=0$.  Under the strict
inequality $r(c+y)>g_r(a_q)$,
\[
 \bar R_{2,r,-y}(c)=\bar R_{2,r,-y}'(c)=0.
\]
As $r(c+y)\downarrow g_r(b_r)$,
$\beta_{r,y}(c)\downarrow b_r$; as
$r(c+y)\uparrow g_r(a_q)$,
$\beta_{r,y}(c)\uparrow a_q$.  Since $W_r$ is continuous,
$W_r(b_r)=\tau_r$, and $W_r(a_q)=0$, the interior expression
\[
 \bar R_{2,r,-y}(c)=\frac{qW_r\{\beta_{r,y}(c)\}}{p(c)}
\]
matches the endpoint values.  Thus the contribution is continuous at both
equalities.  Its one-sided derivatives need not agree there, so a two-sided
derivative is not asserted.
\end{lemma}

\begin{proof}
Since
\[
 \frac{\dd x_\pm}{\dd c}=\frac1{\sqrt{1-r^2}},
 \qquad
 \frac{\dd}{\dd t}\log\Phib(t)=-\lambda(t),
\]
we have
\[
 \frac{\dd}{\dd c}\log Q_\pm(c,z)
 =-\frac{\lambda(x_\pm)}{\sqrt{1-r^2}}+\lambda(c).
\]
Multiplying by $Q_\pm(c,z)$ and summing gives
\begin{align*}
 \bar R_{0,r,z}'(c)
 &=\frac{q\pi_{0,r}}2\{Q_+'(c,z)+Q_-'(c,z)\}\\
 &=\frac{q\pi_{0,r}}2
 \sum_{\sigma\in\{-,+\}}Q_\sigma(c,z)
 \left\{\lambda(c)-
 \frac{\lambda(x_\sigma)}{\sqrt{1-r^2}}\right\},
\end{align*}
which is \eqref{eq:two-null-block-derivative}, and
\begin{align*}
 \frac{\bar R_{0,r,z}'(c)}{\bar R_{0,r,z}(c)}
 &=\frac{Q_+'(c,z)+Q_-'(c,z)}{Q_+(c,z)+Q_-(c,z)}\\
 &=\lambda(c)-
 \frac{Q_+(c,z)\lambda(x_+)+Q_-(c,z)\lambda(x_-)}
 {\sqrt{1-r^2}\{Q_+(c,z)+Q_-(c,z)\}},
\end{align*}
which is \eqref{eq:two-null-block-log-derivative}.

For a secondary non-null indexed by $a$, conditional on $Z=-y$,
\[
 T(a)=\frac ar+y(a)-y,
 \qquad
 r\{T(a)+y\}=g_r(a).
\]
By \eqref{eq:gr} and the positivity of $y'$ in
Lemma~\ref{lem:envelope}, $g_r'(a)=1+ry'(a)>1$, proving the asserted
strict monotonicity.  Equation~\eqref{eq:two-secondary-lower-tail} gives
\[
 g_r(a)\ge g_r(b_r)>r(y-c)
 \quad\Longrightarrow\quad T(a)>-c,
\]
so rejection can occur only through $T(a)\ge c$.  In the interior case,
\eqref{eq:two-secondary-threshold-equation} and strict monotonicity give
\[
 T(a)\ge c
 \quad\Longleftrightarrow\quad
 g_r(a)\ge r(c+y)
 \quad\Longleftrightarrow\quad
 a\ge\beta_{r,y}(c).
\]
This proves \eqref{eq:two-secondary-rejection-set}.
Thus
\begin{align*}
 \bar R_{2,r,-y}(c)
 &=\frac{q\tau_r}{p(c)}
 \mu_r\bigl([\beta_{r,y}(c),a_q]\bigr)\\
 &=\frac{qW_r\{\beta_{r,y}(c)\}}{p(c)}\\
 &=\bigl[1-qM\{y(\beta_{r,y}(c))\}\bigr]
 \frac{p\{\beta_{r,y}(c)/r\}}{p(c)},
\end{align*}
by \eqref{eq:mur-survival} and \eqref{eq:Wr}.

Differentiating the threshold equation yields
\[
 \bigl[1+ry'\{\beta_{r,y}(c)\}\bigr]
 \frac{\partial\beta_{r,y}(c)}{\partial c}=r,
\]
which proves \eqref{eq:two-secondary-threshold-derivative}.  Since
$p'(t)/p(t)=-\lambda(t)$,
\begin{align*}
 \frac{\dd}{\dd c}\log\bar R_{2,r,-y}(c)
 &=-\frac{qM'\{y(\beta_{r,y}(c))\}y'\{\beta_{r,y}(c)\}}
 {1-qM\{y(\beta_{r,y}(c))\}}
 \frac{\partial\beta_{r,y}(c)}{\partial c}\\
 &\quad
 -\lambda\{\beta_{r,y}(c)/r\}
 \frac1r\frac{\partial\beta_{r,y}(c)}{\partial c}
 +\lambda(c).
\end{align*}
Substitution of \eqref{eq:two-secondary-threshold-derivative} gives
\eqref{eq:two-secondary-block-log-derivative}, and
\[
 \bar R_{2,r,-y}'(c)
 =\bar R_{2,r,-y}(c)
 \frac{\dd}{\dd c}\log\bar R_{2,r,-y}(c)
\]
gives \eqref{eq:two-secondary-block-derivative}.
The same equivalence
$T(a)\ge c\Longleftrightarrow g_r(a)\ge r(c+y)$ gives the endpoint cases:
\[
 \bar R_{2,r,-y}(c)
 =\begin{cases}
 q\tau_r/p(c),&r(c+y)\le g_r(b_r),\\
 0,&r(c+y)\ge g_r(a_q),
 \end{cases}
 \qquad
 \bar R_{2,r,-y}'(c)
 =\begin{cases}
 \lambda(c)\bar R_{2,r,-y}(c),&r(c+y)<g_r(b_r),\\
 0,&r(c+y)>g_r(a_q).
 \end{cases}
\]
Because $W_r$ is continuous, \eqref{eq:mur-survival} implies that
$\mu_r$ has no atoms.  Thus the displayed endpoint values agree with the
limits from the interior, so the contribution is continuous at both
thresholds.
\end{proof}

\subsubsection{\texorpdfstring{The regime $z>-1$}{The regime z > -1}}

\begin{lemma}
\label{lem:primary}
For every compact $K\subset(-1,\infty)$ and every $H>0$,
uniformly for $z\in K$ and $|h|\le H$,
\begin{equation}
\bar R_{r,z}\left(c_r+\frac h{c_r}\right)
\longrightarrow
q+(1-q)e^h.
\label{eq:primary-local}
\end{equation}
Moreover, for every $h_0>0$,
\begin{equation}
\limsup_{r\downarrow0}
\sup_{z\in K}
\sup_{u_q\le c\le c_r-h_0/c_r}
\bar R_{r,z}(c)
\le
q+(1-q)e^{-h_0}<1.
\label{eq:primary-left-bound}
\end{equation}
Consequently,
\begin{equation}
C_r(z)=c_r+o(c_r^{-1})
\label{eq:primary-result}
\end{equation}
and
\begin{equation}
D_r(z)\longrightarrow q,
\label{eq:primary-fdp-result}
\end{equation}
uniformly on $K$.  Moreover, for sufficiently small $r$, $C_r(z)$ is regular for every $z\in K$.
\end{lemma}

\begin{proof}
\textbf{Proof of \eqref{eq:primary-local}.}
Fix $H>0$, take $z\in K$, and take $|h|\le H$.  The primary non-null has $B=1$ and $\Theta=c_r+y(b_r)$, so conditional on $Z=z$ its value is $c_r+y(b_r)+z$.  Since $K\subset(-1,\infty)$ is compact,
\[
\eta_K:=\inf_{z\in K}(1+z)>0.
\]
By Lemma~\ref{lem:scale-properties}, $c_r\to\infty$ and $y(b_r)\downarrow1$.  For the fixed $H$, this implies $H/c_r\to0$.  Combining these limits, for sufficiently small $r$,
\begin{equation}
|y(b_r)-1|\le\frac{\eta_K}{4},
\quad
\frac{H}{c_r}\le\frac{\eta_K}{4}.
\label{eq:primary-eta-bounds}
\end{equation}
For $z\in K$ and $|h|\le H$, the definition of $\eta_K$ gives $z\ge -1+\eta_K$, while \eqref{eq:primary-eta-bounds} gives $y(b_r)\ge1-\eta_K/4$ and $-h/c_r\ge-H/c_r\ge-\eta_K/4$.  Therefore
\[
y(b_r)+z-\frac h{c_r}
\ge
\left(1-\frac{\eta_K}{4}\right)
+\left(-1+\eta_K\right)
-\frac{\eta_K}{4}
=\frac{\eta_K}{2},
\quad z\in K,\ |h|\le H.
\]
Equivalently, $y(b_r)+z\ge h/c_r+\eta_K/2$.  Hence the conditional value of the primary non-null satisfies
\begin{equation}
\begin{aligned}
|c_r+y(b_r)+z|
&=c_r+y(b_r)+z\\
&=c_r+\frac h{c_r}
+\left\{y(b_r)+z-\frac h{c_r}\right\}
\\
&\ge c_r+\frac h{c_r}+\frac{\eta_K}{2}
>c_r+\frac h{c_r},
\end{aligned}
\label{eq:primary-rejection-bound}
\end{equation}
so the primary non-null is rejected at cutoff $c_r+h/c_r$, uniformly for $z\in K$ and $|h|\le H$.

Next consider a secondary non-null indexed by $a\in[b_r,a_q]$.  Its conditional value at $Z=z$ is $a/r+y(a)+z$.  Since $a\ge b_r$, we have $a/r\ge b_r/r$.  Also, Lemma~\ref{lem:envelope} shows that $y(\cdot)$, the inverse of the strictly increasing map $a(\cdot)$, is increasing; hence $y(a)\ge y(b_r)$.  Together with $z\ge\inf_{u\in K}u$ and $h\le H$, this gives
\begin{equation}
\frac ar+y(a)+z-\left(c_r+\frac h{c_r}\right)
\ge
\left(\frac{b_r}{r}-c_r\right)
+y(b_r)+\inf_{u\in K}u-\frac{H}{c_r}.
\label{eq:secondary-rejection-bound}
\end{equation}
Here $\frac{b_r}{r}-c_r\to\infty$ by \eqref{eq:cr-properties}, while
\begin{equation}
y(b_r)+\inf_{u\in K}u-\frac{H}{c_r}
\longrightarrow
1+\inf_{u\in K}u
\label{eq:secondary-offset-limit}
\end{equation}
because $y(b_r)\downarrow1$ and $H/c_r\to0$.  Equations~\eqref{eq:cr-properties} and~\eqref{eq:secondary-offset-limit} show that the right side of \eqref{eq:secondary-rejection-bound} tends to $+\infty$.  Hence it is positive for sufficiently small $r$, uniformly in $z\in K$, $|h|\le H$, and $a\in[b_r,a_q]$.  Thus every secondary non-null is rejected at cutoff $c_r+h/c_r$.

Lastly, we analyze the nulls.  Since $|h|\le H$ and $rc_r\to0$ by \eqref{eq:cr-properties},
\begin{equation}
r\left(c_r+\frac h{c_r}\right)
=rc_r+\frac{rh}{c_r}
\longrightarrow0.
\label{eq:primary-rescaled-cutoff}
\end{equation}
Let $T_K=\sup_{z\in K}|z|<\infty$.  Since
$c_r\to\infty$ by \eqref{eq:cr-properties} in
Lemma~\ref{lem:scale-properties}, while
\eqref{eq:primary-rescaled-cutoff} gives a vanishing rescaled cutoff, we have
\[
u_q\le c_r+\frac h{c_r}\le\frac1r
\]
for all sufficiently small $r$, uniformly for $z\in K$ and
$|h|\le H$.  Applying \eqref{eq:null-tail} in Lemma~\ref{lem:null-tail}
with $A=1$ and $T=T_K$ gives
\[
\frac{R_{0,r,z}\{p(c_r+h/c_r)\}}{p(c_r+h/c_r)}
=
L_{r(c_r+h/c_r)}(|z|)+o(1).
\]
Moreover,
\[
L_{r(c_r+h/c_r)}(|z|)
=
\exp\left\{-\frac{r^2(c_r+h/c_r)^2}{2}\right\}
\cosh\!\left(r(c_r+h/c_r)|z|\right)
=1+o(1),
\]
uniformly for $z\in K$ and $|h|\le H$.  Since $\pi_{0,r}=1-r-\tau_r\to1$, it follows that
\[
\bar R_{0,r,z}(c_r+h/c_r)
=q+o(1).
\]
By \eqref{eq:cr},
\[
\frac{q(r+\tau_r)}{p(c_r+h/c_r)}
=
(1-q\pi_{0,r})
\frac{p(c_r)}{p(c_r+h/c_r)}
\longrightarrow
(1-q)e^h
\]
by \eqref{eq:h-over-x} in Lemma~\ref{lem:mills}.  This proves \eqref{eq:primary-local}.

\par\medskip\noindent
\textbf{Proof of \eqref{eq:primary-left-bound}.}
Fix $h_0>0$.  Equation~\eqref{eq:primary-rejection-bound}, evaluated at $h=h_0$, gives
\[
|c_r+y(b_r)+z|>c_r+\frac{h_0}{c_r},
\]
so the primary non-null is rejected at cutoff $c_r+h_0/c_r$.  Equations~\eqref{eq:secondary-rejection-bound}, \eqref{eq:cr-properties}, and~\eqref{eq:secondary-offset-limit} give
\[
\frac ar+y(a)+z>c_r+\frac{h_0}{c_r},
\quad a\in[b_r,a_q],
\]
for sufficiently small $r$, uniformly in $z\in K$.  Thus every secondary non-null is also rejected at cutoff $c_r+h_0/c_r$.  Since rejection at cutoff $c$ means $|T_i|\ge c$, all non-nulls are rejected for every $u_q\le c\le c_r+h_0/c_r$.  Therefore, on this interval,
\[
\bar R_{r,z}(c)
=
\bar R_{0,r,z}(c)
+
\frac{q(r+\tau_r)}{p(c)}.
\]
For $u_q\le c\le c_r-h_0/c_r$, Lemma~\ref{lem:null-tail} and $r c_r\to0$ from \eqref{eq:cr-properties} give
\[
\sup_{z\in K}
\sup_{u_q\le c\le c_r-h_0/c_r}
\bar R_{0,r,z}(c)
\le q+o(1).
\]
Also $p(c)\ge p(c_r-h_0/c_r)$, so \eqref{eq:cr} and \eqref{eq:h-over-x} in Lemma~\ref{lem:mills} give
\[
\sup_{u_q\le c\le c_r-h_0/c_r}
\frac{q(r+\tau_r)}{p(c)}
\le
\frac{q(r+\tau_r)}{p(c_r-h_0/c_r)}
=
(1-q\pi_{0,r})
\frac{p(c_r)}{p(c_r-h_0/c_r)}
\longrightarrow
(1-q)e^{-h_0}.
\]
Taking the supremum over $z\in K$ and then the limsup in $r$ proves \eqref{eq:primary-left-bound}.

\par\medskip\noindent
\textbf{Proof of \eqref{eq:primary-result}.}
Apply Lemma~\ref{lem:localized-crossing} with
\[
 m_r(z)=c_r,
 \qquad w_r(z)=c_r^{-1},
 \qquad d(z)=q,
 \qquad \xi(z)=1.
\]
The set $K$ is compact by hypothesis.  Since $c_r\to\infty$, for all
sufficiently small $r$, $m_r(z)=c_r>u_q$ and
$w_r(z)=c_r^{-1}>0$.  Moreover, $d\equiv q$ and $\xi\equiv1$ are
continuous on $K$, with $d(z)\in[0,1)$ and $\xi(z)>0$.  For every
fixed $H>0$,
\[
 \inf_{z\in K}\{m_r(z)-Hw_r(z)\}
 =c_r-\frac H{c_r}>u_q
\]
for all sufficiently small $r$, which verifies
\eqref{eq:localized-crossing-domain}.  Under these choices,
\eqref{eq:localized-crossing-full} becomes
\[
 \sup_{z\in K}\sup_{|h|\le H}
 \left|
 \bar R_{r,z}\left(c_r+\frac h{c_r}\right)
 -q-(1-q)e^h
 \right|\longrightarrow0,
\]
which is exactly \eqref{eq:primary-local}.  Its left-of-crossing assumption
\eqref{eq:localized-crossing-left} becomes, for every $h_0>0$,
\[
 \limsup_{r\downarrow0}\sup_{z\in K}
 \sup_{u_q\le c\le c_r-h_0/c_r}\bar R_{r,z}(c)<1.
\]
This follows from \eqref{eq:primary-left-bound}, because
$q+(1-q)e^{-h_0}<1$.  Hence all assumptions of
Lemma~\ref{lem:localized-crossing} hold, and
\eqref{eq:localized-crossing-cutoff} gives
\[
 \sup_{z\in K}
 \left|\frac{C_r(z)-c_r}{c_r^{-1}}\right|
 =\sup_{z\in K}c_r|C_r(z)-c_r|\longrightarrow0,
\]
which is \eqref{eq:primary-result} uniformly on $K$.

\par\medskip\noindent
\textbf{Proof of \eqref{eq:primary-fdp-result}.}
Fix $H>0$.
On $|c-c_r|\le H/c_r$, all non-nulls are rejected, uniformly over
$z\in K$, and hence
\begin{equation}
\bar R_{r,z}(c)
=\bar R_{0,r,z}(c)+\frac{q(r+\tau_r)}{p(c)}.
\label{eq:primary-smooth-curve}
\end{equation}
{
In the notation of Lemma~\ref{lem:two-block-derivatives}, uniformly for
$|c-c_r|\le H/c_r$ and $z\in K$, \eqref{eq:cr-properties} gives
\[
 c\longrightarrow\infty,\qquad rc\longrightarrow0.
\]
For all sufficiently small $r$, this range lies in
$[C,1/r]$, with $C\to\infty$.  Thus
\eqref{eq:null-tail-expansion}-\eqref{eq:null-tail-remainder} in
Lemma~\ref{lem:null-tail} give, for either sign,
\[
\begin{aligned}
 Q_\pm(c,z)
 &=
 \frac{c}{x_\pm}
 \exp\left\{-\frac{(rc)^2}{2}\pm rcz+O(r^2)\right\}
 \{1+o(1)\}\\
 &=1+o(1),
\end{aligned}
\]
because $c/x_\pm\to1$, $rc\to0$, and $z$ ranges over the compact set
$K$.  Also $x_\pm/c_r\to1$, $c/c_r\to1$, and
$\sqrt{1-r^2}\to1$.
Thus \eqref{eq:mills-hazard} in Lemma~\ref{lem:mills}, applied directly
to \eqref{eq:two-null-block-derivative} in
Lemma~\ref{lem:two-block-derivatives}, gives
\[
\sup_{z\in K}\sup_{|c-c_r|\le H/c_r}
|\bar R_{0,r,z}'(c)|=o(c_r).
\]}
For $|c-c_r|\le H/c_r$, write $c=c_r+h/c_r$, where
$|h|\le H$.  By
\eqref{eq:cr},
\[
\frac{q(r+\tau_r)}{p(c)}
=(1-q\pi_{0,r})\frac{p(c_r)}{p(c)},
\]
and \eqref{eq:h-over-x} in Lemma~\ref{lem:mills} gives
\[
\frac{p(c_r)}{p(c)}
=
\frac{p(c_r)}{p(c_r+h/c_r)}
\longrightarrow e^h,
\]
uniformly for $|h|\le H$.  Since $e^h\ge e^{-H}$ on this range and
$1-q\pi_{0,r}\to1-q>0$, for all sufficiently small $r$,
\[
\inf_{|c-c_r|\le H/c_r}
\frac{q(r+\tau_r)}{p(c)}
\ge \frac{1-q}{2}\cdot\frac{e^{-H}}{2}.
\]
Thus we may take $m_H=(1-q)e^{-H}/4>0$.
Since all non-nulls are fully rejected for $|c-c_r|\le H/c_r$, their combined
contribution is $q(r+\tau_r)/p(c)$, whose derivative is
$\lambda(c)q(r+\tau_r)/p(c)$.  Together with
$\lambda(c)\sim c_r$ uniformly for $|c-c_r|\le H/c_r$, this gives
\[
\inf_{|c-c_r|\le H/c_r}
\frac{\dd}{\dd c}\frac{q(r+\tau_r)}{p(c)}
\ge \frac{m_H}{2}c_r
\]
for all sufficiently small $r$.  By contrast,
$\bar R_{0,r,z}'(c)=o(c_r)$ uniformly over $z\in K$ and
$|c-c_r|\le H/c_r$.  Differentiating \eqref{eq:primary-smooth-curve}
therefore shows that
\begin{equation}
\inf_{z\in K}\inf_{|c-c_r|\le H/c_r}
\bar R_{r,z}'(c)>0
\label{eq:primary-strict-increase}
\end{equation}
for all sufficiently small $r$.  By \eqref{eq:primary-result}, uniformly
for $z\in K$,
\[
 c_r-\frac{H}{c_r}<C_r(z)<c_r+\frac{H}{c_r}
\]
for all sufficiently small $r$; moreover,
$c_r-H/c_r>u_q$.  Equation~\eqref{eq:primary-strict-increase} and the
smoothness of the null contribution on this interval therefore verify the
hypotheses of Proposition~\ref{prop:local-regularity}, so $C_r(z)$ is
regular.

Equation~\eqref{eq:Dr} gives
\[
 D_r(z)=\bar R_{0,r,z}\{C_r(z)\}.
\]
Put $h_r(z)=c_r\{C_r(z)-c_r\}$.  Equation~\eqref{eq:primary-result}
gives $h_r(z)\to0$ uniformly on $K$.  The null limit established in
the proof of \eqref{eq:primary-local}, evaluated at $h=h_r(z)$, now gives
\[
 \sup_{z\in K}
 \left|D_r(z)-q\right|
 =\sup_{z\in K}
 \left|\bar R_{0,r,z}\{C_r(z)\}-q\right|
 \longrightarrow0,
\]
which is \eqref{eq:primary-fdp-result}.
\end{proof}

\subsubsection{\texorpdfstring{The regime $z\in(-y_q,-1)$}{The regime -yq < z < -1}}

Let $y=-z$.
For $1<y<y_q$, put
\begin{equation}
\kappa(y)=a(y)y'\{a(y)\}>0.
\label{eq:kappa}
\end{equation}
The positivity follows from Lemma~\ref{lem:envelope}, since $a(y)>0$ and $y'\{a(y)\}>0$ for $1<y<y_q$.
For the remainder of the population analysis, define
\begin{equation}
 s_r(y)=c_r+y(b_r)-y.
 \label{eq:sr-def}
\end{equation}

The next lemma separates the primary non-null value from the
cutoffs on the $r^{-1}$ scale.
\begin{lemma}
\label{lem:primary-scale-separation}
For every compact $I\subset(1,\infty)$ and every $H>0$, if
$a_I=\inf_{y\in I}a(y)>0$, then
\begin{equation}
\begin{aligned}
 \sup_{y\in I}r|s_r(y)|
 &\le rc_r+r\sup_{y\in I}|y(b_r)-y|\longrightarrow0,\\
 \inf_{\substack{y\in I\\|h|\le H}}
 r\left\{\frac{a(y)}r+h\right\}
 &=a_I-rH\longrightarrow a_I>0.
\end{aligned}
\label{eq:rare-primary-scale-separation}
\end{equation}
Consequently, the primary non-null is not rejected at cutoff
$a(y)/r+h$ for all sufficiently small $r$, uniformly for $y\in I$
and $|h|\le H$.
\end{lemma}

\begin{proof}
Conditional on $Z=-y$, the primary non-null value is $s_r(y)$
by \eqref{eq:sr-def}.  The two limits in
\eqref{eq:rare-primary-scale-separation} follow from
\eqref{eq:br-properties} and \eqref{eq:cr-properties} in
Lemma~\ref{lem:scale-properties}.  Their limiting bounds are separated by
$a_I>0$, which proves the rejection claim.
\end{proof}

\begin{lemma}
\label{lem:primary-active-range}
For every compact $I\subset(1,\infty)$,
\begin{equation}
 \sup_{y\in I}\sup_{u_q\le s\le s_r(y)}
 \bar R_{r,-y}(s)\le q+o(1)<1.
 \label{eq:primary-active-uniform}
\end{equation}
\end{lemma}

\begin{proof}
Put $y_I=\inf I>1$ and
$\delta_I^{\mathrm{shift}}=(y_I-1)/2>0$.  Since $y(b_r)\downarrow1$,
\begin{equation}
 \delta_I^{\mathrm{shift}}\le y-y(b_r)
 \le \sup_{u\in I}u-1=: \Delta_I<\infty
 \label{eq:primary-shift-bounds}
 \end{equation}
for all sufficiently small $r$, uniformly for $y\in I$.  Hence
$s_r(y)\le c_r-\delta_I^{\mathrm{shift}}$.  From
\eqref{eq:population-curve} and the bound
by one on each non-null rejection probability,
\[
 \bar R_{r,-y}(s)
 \le \bar R_{0,r,-y}(s)+\frac{q(r+\tau_r)}{p(s)},
 \qquad u_q\le s\le s_r(y).
\]
Uniformly on this range, $0\le rs\le rc_r\to0$.  Therefore
\eqref{eq:null-tail} in Lemma~\ref{lem:null-tail} gives
\[
 \bar R_{0,r,-y}(s)=q+o(1).
\]
Since $p$ is decreasing, \eqref{eq:cr} yields
\[
\begin{aligned}
 \frac{q(r+\tau_r)}{p(s)}
 &\le \frac{q(r+\tau_r)}{p\{s_r(y)\}}\\
 &=(1-q\pi_{0,r})
 \frac{p(c_r)}{p\{c_r+y(b_r)-y\}}.
\end{aligned}
\]
Here $s_r(y)\to\infty$ uniformly and the shift
$y-y(b_r)$ lies in
$[\delta_I^{\mathrm{shift}},\Delta_I]$.  Thus
\eqref{eq:fixed-shift} in Lemma~\ref{lem:mills} gives

\[
 \sup_{y\in I}
 \frac{p(c_r)}{p\{c_r+y(b_r)-y\}}\longrightarrow0.
\]
Combining the bounds proves
\eqref{eq:primary-active-uniform}.
\end{proof}

We first prove a lemma that is useful for the key result in this regime.
\begin{lemma}
\label{lem:secondary-threshold}
For every compact $I\subset(1,y_q)$ and every $H>0$,
there is an interval $U_I$ whose closure is contained in $(0,a_q)$ and contains $\{a(y):y\in I\}$.
For all sufficiently small $r$, with $g_r$ as in
\eqref{eq:gr}, the equation
\begin{equation}
g_r\{\tilde{\alpha}_r(y,h)\}=g_r\{a(y)\}+rh
\label{eq:tilde-alpha-equation}
\end{equation}
has a unique solution $\tilde{\alpha}_r(y,h)\in U_I$, uniformly for $y\in I$ and $|h|\le H$, and
\begin{equation}
\tilde{\alpha}_r(y,h)=a(y)+O(r).
\label{eq:alpha-close}
\end{equation}

Conditional on $Z=-y$, a secondary non-null with $a=\tilde a$ is rejected at cutoff $a(y)/r+h$ {if and only if}
\[
\tilde a\in[\tilde{\alpha}_r(y,h),a_q].
\]
Finally,
\begin{equation}
\log\frac{p\{\tilde{\alpha}_r(y,h)/r\}}{p(a(y)/r+h)}
=
\kappa(y)h+o(1),
\label{eq:tilde-alpha-log-ratio}
\end{equation}
uniformly for $y\in I$ and $|h|\le H$.
\end{lemma}

\begin{proof}
Fix a compact $I\subset(1,y_q)$ and $H>0$ as in the statement.
Let
\[
A_I=\{a(y):y\in I\}.
\]
Because $I\subset(1,y_q)$ is compact, $A_I$ is a compact subset of $(0,a_q)$.  Choose an interval $U_I$ whose closure is contained in $(0,a_q)$ and such that $A_I\subset U_I$.
{
By \eqref{eq:br-properties} in Lemma~\ref{lem:scale-properties},
$b_r\to0$, so $U_I\subset(b_r,a_q)$ for all sufficiently small
$r$.  Lemma~\ref{lem:two-block-derivatives} then shows that $g_r$ is
strictly increasing on $U_I$.}

Put $d_I=\mathrm{dist}(A_I,U_I^c)>0$.  If $rH<d_I/2$, then $a(y)\pm rH\in U_I$ for all $y\in I$.  Since $g_r'\ge1$ on $U_I$, the intermediate value theorem gives a unique solution to \eqref{eq:tilde-alpha-equation} in $U_I$, and
\[
|\tilde{\alpha}_r(y,h)-a(y)|\le rH.
\]
Hence, \eqref{eq:alpha-close} is proved.


Put $c=a(y)/r+h$ and $\beta=\tilde{\alpha}_r(y,h)$.  If
$a_I=\inf_{u\in I}a(u)>0$, then
\[
 r(y-c)
 =ry-a(y)-rh
 \le r\sup_{u\in I}u-a_I+rH<0<g_r(b_r)
\]
for all sufficiently small $r$, uniformly for $y\in I$ and
$|h|\le H$.  Thus \eqref{eq:two-secondary-lower-tail} holds uniformly.
Moreover,
\eqref{eq:tilde-alpha-equation} and $y\{a(y)\}=y$ give
\[
 g_r(\beta)
 =g_r\{a(y)\}+rh
 =r(c+y).
\]
This is \eqref{eq:two-secondary-threshold-equation}, so
\eqref{eq:two-secondary-rejection-set} shows that a secondary non-null is
rejected exactly when its index lies in
$[\tilde{\alpha}_r(y,h),a_q]$.


Write $\beta=\tilde{\alpha}_r(y,h)$.  Differentiating
\eqref{eq:tilde-alpha-equation} with respect to $h$ gives
\[
 \frac{\partial\beta}{\partial h}
 =\frac{r}{1+r y'(\beta)}.
\]
Since $p'(x)/p(x)=-\lambda(x)$,
\begin{equation}
 \frac{\partial}{\partial h}
 \log\frac{p(\beta/r)}{p\{a(y)/r+h\}}
 =
 \lambda\!\left(\frac{a(y)}r+h\right)
 -\frac{\lambda(\beta/r)}{1+r y'(\beta)}.
 \label{eq:tilde-alpha-log-ratio-derivative}
\end{equation}
Moreover, \eqref{eq:tilde-alpha-equation} and $y\{a(y)\}=y$ imply
\begin{equation}
 \frac{\beta}{r}
 =\frac{a(y)}r+h+y-y(\beta).
 \label{eq:tilde-alpha-threshold-identity}
\end{equation}
The function $a(y)$ is bounded away from zero on $I$, and
\eqref{eq:alpha-close} gives $\beta=a(y)+O(r)$ uniformly.  Hence both
arguments of $\lambda$ in
\eqref{eq:tilde-alpha-log-ratio-derivative} are of order $r^{-1}$.
Using $\lambda(x)=x+O(x^{-1})$ from
\eqref{eq:mills-hazard} in Lemma~\ref{lem:mills} and then
\eqref{eq:tilde-alpha-threshold-identity}, we obtain
\[
\begin{aligned}
 \lambda\!\left(\frac{a(y)}r+h\right)
 -\frac{\lambda(\beta/r)}{1+r y'(\beta)}
 &=
 \frac{a(y)}r+h
 -\frac{\beta/r}{1+r y'(\beta)}+O(r)\\
 &=
 \frac{\{a(y)+rh\}y'(\beta)+y(\beta)-y}
      {1+r y'(\beta)}+O(r)\\
 &\longrightarrow a(y)y'\{a(y)\}=\kappa(y)
\end{aligned}
\]
uniformly for $y\in I$ and $|h|\le H$.  At $h=0$, uniqueness in
\eqref{eq:tilde-alpha-equation} gives $\beta=a(y)$, so the logarithm in
\eqref{eq:tilde-alpha-log-ratio-derivative} is zero.  Integrating from
$0$ to $h$ proves \eqref{eq:tilde-alpha-log-ratio}.
\end{proof}

\begin{lemma}
\label{lem:rare-local}
For every compact $I\subset(1,y_q)$ and every $H>0$,
uniformly for $y\in I$ and $|h|\le H$,
\begin{equation}
\bar R_{r,-y}\left(\frac{a(y)}r+h\right)
\longrightarrow
qM(y)+\{1-qM(y)\}e^{\kappa(y)h}.
\label{eq:rare-local}
\end{equation}
Moreover, for every $h_0>0$, there is $\gamma>0$ such that, for all sufficiently small $r$,
\begin{equation}
\sup_{y\in I}
\sup_{u_q\le c\le a(y)/r-h_0}
\bar R_{r,-y}(c)
\le1-\gamma.
\label{eq:no-earlier}
\end{equation}
Consequently, uniformly for $y\in I$,
\begin{equation}
C_r(-y)-\frac{a(y)}r\longrightarrow0
\label{eq:rare-result}
\end{equation}
and
\begin{equation}
D_r(-y)\longrightarrow qM(y).
\label{eq:rare-fdp-result}
\end{equation}
Moreover, for sufficiently small $r$, $C_r(-y)$ is regular for every
$y\in I$.
\end{lemma}

\begin{proof}
\textbf{Proof of \eqref{eq:rare-local}.}
Fix $H>0$, take $y\in I$, and take $|h|\le H$.  By Lemma~\ref{lem:secondary-threshold}, a secondary non-null with $a=\tilde a$ is rejected at cutoff $a(y)/r+h$ {if and only if}
\[
\tilde a\in[\tilde{\alpha}_r(y,h),a_q].
\]
By \eqref{eq:mur-survival}, their mass under the secondary component is
\[
\tau_r\mu_r([\tilde{\alpha}_r(y,h),a_q])
=W_r\{\tilde{\alpha}_r(y,h)\}.
\]
The definition \eqref{eq:Wr} therefore gives
\[
\frac{qW_r\{\tilde{\alpha}_r(y,h)\}}{p(a(y)/r+h)}
=
\bigl[1-qM\{y(\tilde{\alpha}_r(y,h))\}\bigr]
\frac{p\{\tilde{\alpha}_r(y,h)/r\}}{p(a(y)/r+h)}.
\]
By \eqref{eq:alpha-close}, $y(\tilde{\alpha}_r(y,h))\to y$
uniformly for $y\in I$ and $|h|\le H$.  Equation~\eqref{eq:tilde-alpha-log-ratio} gives
\[
\frac{p\{\tilde{\alpha}_r(y,h)/r\}}{p(a(y)/r+h)}
\longrightarrow e^{\kappa(y)h},
\]
uniformly for $y\in I$ and $|h|\le H$.  Hence
\begin{equation}
\frac{qW_r\{\tilde{\alpha}_r(y,h)\}}{p(a(y)/r+h)}
=
\bigl[1-qM\{y(\tilde{\alpha}_r(y,h))\}\bigr]
\frac{p\{\tilde{\alpha}_r(y,h)/r\}}{p(a(y)/r+h)}
\longrightarrow
\{1-qM(y)\}e^{\kappa(y)h}
\label{eq:signal-local}
\end{equation}

Lemma~\ref{lem:primary-scale-separation}, through
\eqref{eq:rare-primary-scale-separation}, shows that the primary non-null is
not rejected at cutoff $a(y)/r+h$, uniformly for $y\in I$ and
$|h|\le H$.

Since $a(y)$ is bounded away from zero on $I$ and
$a(y)\le a_q$, for all sufficiently small $r$,
\[
u_q\le \frac{a(y)}r+h\le \frac{a_q+1}{r}
\]
uniformly for $y\in I$ and $|h|\le H$.  Thus
\eqref{eq:null-tail} in Lemma~\ref{lem:null-tail}, applied with
$A=a_q+1$ and $T=\sup_{u\in I}u$, gives
\begin{equation}
\bar R_{0,r,-y}(a(y)/r+h)
\longrightarrow
qL_{a(y)}(y)=qM(y).
\label{eq:rare-null-local}
\end{equation}
Combining \eqref{eq:signal-local} and \eqref{eq:rare-null-local} proves \eqref{eq:rare-local}.

\par\medskip\noindent
\textbf{Proof of \eqref{eq:no-earlier}.}
Lemma~\ref{lem:primary-active-range}, through
\eqref{eq:primary-active-uniform}, excludes a crossing on
$u_q\le s\le s_r(y)$, uniformly for $y\in I$.
Fix $h_0>0$.
The complementary range $s_r(y)<s\le a(y)/r-h_0$ is nonempty uniformly
on $I$, because
\[
\inf_{y\in I}
\left\{
\frac{a(y)}r-h_0-s_r(y)
\right\}
\ge
\frac{\inf_{y\in I}a(y)}r-c_r-O_I(1)
\longrightarrow\infty,
\]
where $rc_r\to0$ by \eqref{eq:cr-properties} in
Lemma~\ref{lem:scale-properties}.
It remains to prove that there is $\gamma>0$ such that, for all sufficiently
small $r$,
\begin{equation}
\sup_{y\in I}
\sup_{s_r(y)<s\le a(y)/r-h_0}
\bar R_{r,-y}(s)
\le 1-\gamma
\label{eq:secondary-range-target}
\end{equation}

For $s>s_r(y)$, the identity $T_i=s_r(y)>0$ gives $|T_i|=T_i<s$.  For sufficiently small $r$, every secondary non-null value is positive uniformly over $y\in I$ and $\tilde a\in[b_r,a_q]$.
{For every $y>1$ and $s>s_r(y)$, define
\begin{equation}
\mathcal A_{r,y,s}:=\left\{\tilde a\in[b_r,a_q]:g_r(\tilde a)\ge r(s+y)\right\},
\qquad \beta_{r,y,s}:=\inf\bigl(\mathcal A_{r,y,s}\cup\{a_q\}\bigr).
\label{eq:beta-rys-def}
\end{equation}}
On the range $s_r(y)<s\le a(y)/r-h_0$, the set is nonempty for
sufficiently small $r$, since $\tilde a=a_q$ satisfies the inequality
uniformly over $y\in I$.  By \eqref{eq:gr} and
Lemma~\ref{lem:two-block-derivatives}, $g_r$ is strictly increasing.
Thus a secondary non-null with $a=\tilde a$ is rejected if and only if
$\tilde a\in[\beta_{r,y,s},a_q]$.  Therefore, by
\eqref{eq:population-curve},
\begin{equation}
\bar R_{r,-y}(s)
=
\bar R_{0,r,-y}(s)
+
\frac{q\tau_r}{p(s)}
\mu_r([\beta_{r,y,s},a_q]).
\label{eq:secondary-only-curve}
\end{equation}

\noindent Suppose \eqref{eq:secondary-range-target} fails for this $h_0$.  Then there are
\begin{equation}
r_n\downarrow0,
\quad y_n\in I,
\quad s_{r_n}(y_n)<s_n\le a(y_n)/r_n-h_0,
\quad \liminf_{n\to\infty}\bar R_{r_n,-y_n}(s_n)\ge1.
\label{eq:secondary-contradiction-sequence}
\end{equation}
After taking a subsequence,
\begin{equation}
y_n\to y\in I,
\quad a(y_n)\to a(y),
\quad x_n=r_ns_n\to x\in[0,a(y)].
\label{eq:secondary-contradiction-limits}
\end{equation}

Define
\[
h_n:=s_n-\frac{a(y_n)}{r_n}.
\]
Then $h_n\le -h_0$ by \eqref{eq:secondary-contradiction-sequence}.  If $h_n=O(1)$, then after passing to a further subsequence $h_n\to h\le -h_0$.  Equation~\eqref{eq:rare-local} gives
\[
\bar R_{r_n,-y_n}(s_n)
\longrightarrow
qM(y)+\{1-qM(y)\}e^{\kappa(y)h}
\le
qM(y)+\{1-qM(y)\}e^{-\kappa(y)h_0}
<1,
\]
contradicting $\liminf_{n\to\infty}\bar R_{r_n,-y_n}(s_n)\ge1$.  Hence, after passing to a further subsequence if necessary, it remains to consider
\begin{equation}
h_n\to-\infty.
\label{eq:hn-minus-infty}
\end{equation}

We next identify the rejected secondary non-nulls at cutoff $s_n$.  A secondary non-null with index $\tilde a\in[b_{r_n},a_q]$ has $(\Theta,B)=(\tilde a/r_n+y(\tilde a),1)$.  Conditional on $Z=-y_n$, its value is
\[
T_{\tilde a,n}
=
\frac{\tilde a}{r_n}+y(\tilde a)-y_n.
\]
For all large $n$, this value is positive uniformly in $\tilde a\in[b_{r_n},a_q]$, because $b_{r_n}/r_n\to\infty$ and $y(\tilde a)-y_n$ is bounded below.  Hence $|T_{\tilde a,n}|=T_{\tilde a,n}$, and the rejection rule $|T_{\tilde a,n}|\ge s_n$ is equivalent to
\[
\frac{\tilde a}{r_n}+y(\tilde a)-y_n\ge s_n.
\]
The rejected set is nonempty because the endpoint $\tilde a=a_q$ is rejected.  Indeed, compactness of $I\subset(1,y_q)$ and continuity of $a(\cdot)$ give
\[
\Delta_I:=a_q-\sup_{u\in I}a(u)>0.
\]
Since $s_n\le a(y_n)/r_n-h_0$ by \eqref{eq:secondary-contradiction-sequence},
\[
\frac{a_q}{r_n}+y_q-y_n-s_n
\ge
\frac{a_q-a(y_n)}{r_n}+y_q-y_n+h_0>0
\]
for large $n$, because $a_q-a(y_n)\ge\Delta_I$ and $y_n\le\sup I<y_q$.  Define
\[
G_n(\tilde a)
:=
g_{r_n}(\tilde a)-r_n(s_n+y_n),
\quad
\tilde a\in[b_{r_n},a_q],
\]
where $g_r$ is defined in \eqref{eq:gr}.  Multiplying the rejection inequality by $r_n$, a secondary non-null with index $\tilde a$ is rejected if and only if
\[
G_n(\tilde a)\ge0.
\]
By \eqref{eq:gr} and Lemma~\ref{lem:two-block-derivatives}, $G_n$ is
continuous and strictly increasing on $[b_{r_n},a_q]$ for all large
$n$.  Therefore a secondary non-null with $a = \tilde{a}$ is rejected
if and only if $\tilde{a}\in[\beta_n,a_q]$, where
\begin{equation}
\beta_n
:=
\inf\left\{
\tilde a\in[b_{r_n},a_q]:
G_n(\tilde a)\ge0
\right\}.
\label{eq:beta-n-def}
\end{equation}
Put $d_n:=y_n-y(\beta_n)$.
If $\beta_n>b_{r_n}$, then $G_n(\beta_n)=0$.  Thus, in this case,
\begin{equation}
\frac{\beta_n}{r_n}-s_n
=d_n.
\label{eq:rejection-threshold}
\end{equation}
If $\beta_n=b_{r_n}$, then $G_n(\beta_n)\ge0$, so \eqref{eq:rejection-threshold} is replaced by
\begin{equation}
\frac{\beta_n}{r_n}-s_n
\ge
d_n.
\label{eq:rejection-threshold-endpoint}
\end{equation}
{
Moreover, $s_n\to\infty$, because
$s_n>s_{r_n}(y_n)=c_{r_n}+y(b_{r_n})-y_n$,
$c_{r_n}\to\infty$, $y(b_{r_n})\to1$, and $I$ is compact.
Also $d_n>0$ eventually.  If $\beta_n=b_{r_n}$, this follows from
the definition of $d_n$ and
\eqref{eq:primary-shift-bounds} in
Lemma~\ref{lem:primary-active-range}, which give
\[
d_n=y_n-y(b_{r_n})\ge\delta_I^{\mathrm{shift}}>0.
\]
If $\beta_n>b_{r_n}$, then
\[
g_{r_n}(\beta_n)
=r_n(s_n+y_n)
=g_{r_n}\{a(y_n)\}+r_nh_n
\le g_{r_n}\{a(y_n)\}-r_nh_0.
\]
The strict monotonicity of $g_{r_n}$ therefore gives
$\beta_n<a(y_n)$, and hence
$d_n=y_n-y(\beta_n)>0$.
}
The null contribution term in \eqref{eq:secondary-only-curve} already has a limit along this subsequence:
\begin{equation}
q\pi_{0,r_n}
\frac{R_{0,r_n,-y_n}\{p(s_n)\}}{p(s_n)}
\longrightarrow
qL_x(y)
\le qM(y)<1.
\label{eq:null-term-secondary-contradiction}
\end{equation}
Indeed, \eqref{eq:null-tail} in Lemma~\ref{lem:null-tail} applies because $r_ns_n\to x$, $y_n\to y$, and $\pi_{0,r_n}\to1$.  The inequality follows from $M(y)=\sup_{\alpha\ge0}L_\alpha(y)$, the strict monotonicity of $M$ on $(1,\infty)$, $y\in I\subset(1,y_q)$, and $qM(y_q)=1$.  Equations~\eqref{eq:secondary-only-curve} and~\eqref{eq:null-term-secondary-contradiction}, together with the threshold characterization in \eqref{eq:beta-n-def}, imply
\begin{equation}
\bar R_{r_n,-y_n}(s_n)
=
qL_x(y)+o(1)
+
\frac{q\tau_{r_n}}{p(s_n)}
\mu_{r_n}([\beta_n,a_q]).
\label{eq:secondary-sequence-curve}
\end{equation}
Moreover, \eqref{eq:mur-survival}, \eqref{eq:Wr}, \eqref{eq:deficit-properties} in Lemma~\ref{lem:envelope}, and the bound from \eqref{eq:rejection-threshold}-\eqref{eq:rejection-threshold-endpoint} give
\begin{equation}
\frac{q\tau_{r_n}}{p(s_n)}
\mu_{r_n}([\beta_n,a_q])
=
\frac{qW_{r_n}(\beta_n)}{p(s_n)}
=
\bigl[1-qM\{y(\beta_n)\}\bigr]
\frac{p(\beta_n/r_n)}{p(s_n)}
\le
\frac{p(s_n+d_n)}{p(s_n)}.
\label{eq:secondary-tail-bound}
\end{equation}
It remains only to prove that
\begin{equation}
s_nd_n\longrightarrow\infty.
\label{eq:sn-dn-diverges}
\end{equation}
Equations~\eqref{eq:secondary-tail-bound}, \eqref{eq:sn-dn-diverges}, and
\eqref{eq:variable-shift} in Lemma~\ref{lem:mills} imply
\[
\frac{q\tau_{r_n}}{p(s_n)}
\mu_{r_n}([\beta_n,a_q])
=o(1).
\]
Substituting this into \eqref{eq:secondary-sequence-curve} gives
\[
\bar R_{r_n,-y_n}(s_n)\longrightarrow qL_x(y)<1,
\]
which yields a contradiction to \eqref{eq:secondary-contradiction-sequence}.

\par\medskip\noindent
To prove \eqref{eq:sn-dn-diverges}, we now consider three cases under \eqref{eq:secondary-contradiction-sequence}, \eqref{eq:secondary-contradiction-limits}, and \eqref{eq:hn-minus-infty}.
\par\medskip\noindent

\begin{enumerate}[label=\textbf{Case (\alph*):},wide=0pt]
\item $0<x<a(y)$.
Suppose $x>0$.  Since $b_{r_n}\to0$ by \eqref{eq:br-properties} in Lemma~\ref{lem:scale-properties} and $r_ns_n\to x$, the endpoint case $\beta_n=b_{r_n}$ cannot occur for large $n$: multiplying \eqref{eq:rejection-threshold-endpoint} by $r_n$ would give
\[
b_{r_n}-r_ns_n
\ge
r_n\{y_n-y(b_{r_n})\},
\]
whose left side tends to $-x<0$, while the right side is nonnegative for large $n$.  Hence \eqref{eq:rejection-threshold} holds eventually.  Multiplying it by $r_n$ gives
\[
\beta_n-r_ns_n
=
r_nd_n.
\]
The factor $d_n$ is bounded.  Indeed, $I$ is compact, so $|y_n|\le \sup_{u\in I}|u|$.  Also $\beta_n\in[b_{r_n},a_q]$, and $y(\cdot)$ is increasing by Lemma~\ref{lem:envelope}; hence
\begin{equation}
y(b_{r_n})\le y(\beta_n)\le y(a_q)=y_q.
\label{eq:beta-y-bounds}
\end{equation}
Since $y(b_{r_n})\downarrow1$ by \eqref{eq:br-properties} in Lemma~\ref{lem:scale-properties}, the sequence $y(\beta_n)$ is bounded.  Thus $r_nd_n\to0$, so $\beta_n-r_ns_n\to0$.  Since $r_ns_n\to x$, we have $\beta_n\to x$.  Since $x<a(y)$ and $y(\cdot)$ is strictly increasing by Lemma~\ref{lem:envelope}, $y(x)<y$.  Together, $y_n\to y$ from \eqref{eq:secondary-contradiction-limits} and $\beta_n\to x$ imply, by continuity of $y(\cdot)$, that $d_n\to d:=y-y(x)>0$.  Also, \eqref{eq:rejection-threshold} gives $\beta_n/r_n=s_n+d_n$.  Therefore, for all large $n$,
\[
\frac{\beta_n}{r_n}=s_n+d_n,
\quad
0<\frac d2\le d_n\le 2d,
\quad
s_n\to\infty.
\]
As a result, \eqref{eq:sn-dn-diverges} is proved.

\item $x=0$.
Then $r_ns_n\to0$.  Since
\[
s_n>s_{r_n}(y_n)=c_{r_n}+y(b_{r_n})-y_n,
\]
\eqref{eq:cr-properties} gives $c_{r_n}\to\infty$, while \eqref{eq:br-properties} gives $y(b_{r_n})\downarrow1$ and compactness of $I$ keeps $y_n$ bounded.  Hence $s_n\to\infty$.  If $\beta_n=b_{r_n}$, then $\beta_n\to0$ by \eqref{eq:br-properties}.  If $\beta_n>b_{r_n}$, then \eqref{eq:rejection-threshold} holds; multiplying it by $r_n$, using compactness of $I$, and applying \eqref{eq:beta-y-bounds} gives
\[
\beta_n-r_ns_n=r_nd_n\to0.
\]
Since $r_ns_n\to0$, this also gives $\beta_n\to0$.  Thus $\beta_n\to0$ in both cases.  By \eqref{eq:secondary-contradiction-limits}, $y_n\to y$, and by the inverse relation together with \eqref{eq:envelope-limits} in Lemma~\ref{lem:envelope}, $y(\beta_n)\to1$.  Hence
\[
d_n\to y-1>0.
\]
Moreover, \eqref{eq:rejection-threshold} in the interior case and \eqref{eq:rejection-threshold-endpoint} in the endpoint case give $\beta_n/r_n\ge s_n+d_n$.  Since $d_n\to d:=y-1>0$ and $s_n\to\infty$, \eqref{eq:sn-dn-diverges} is proved.

\item $x=a(y)$.  By \eqref{eq:hn-minus-infty}, this is the only remaining subcase.  Since $r_ns_n\to a(y)$ and $a(y_n)\to a(y)$, we have
\[
r_nh_n=r_ns_n-a(y_n)\to a(y)-a(y)=0.
\]
The threshold equation $G_n(\tilde a)=0$ is
\[
g_{r_n}(\tilde a)
=
r_n(s_n+y_n)
=
a(y_n)+r_ny_n+r_nh_n
=
g_{r_n}\{a(y_n)\}+r_nh_n,
\]
where $y\{a(y_n)\}=y_n$.  Since $h_n<0$ and $g_{r_n}$ is strictly
increasing by \eqref{eq:gr} and Lemma~\ref{lem:two-block-derivatives}, the
corresponding threshold lies below $a(y_n)$.
To justify the existence and location of this threshold, choose
$\eta>0$ such that
\[
[a(y_n)-\eta,a(y_n)]\subset(0,a_q)
\]
for all large $n$; this is possible because $a(y_n)\to a(y)\in(0,a_q)$.
Since $-r_nh_n\to0$ and $g_{r_n}'\ge1$, for all large $n$,
\[
g_{r_n}\{a(y_n)-\eta\}
<g_{r_n}\{a(y_n)\}+r_nh_n
<g_{r_n}\{a(y_n)\}.
\]
Continuity and strict monotonicity of $g_{r_n}$ therefore give a unique
$\tilde\beta_n\in(a(y_n)-\eta,a(y_n))$ satisfying
\[
g_{r_n}(\tilde\beta_n)
=
g_{r_n}\{a(y_n)\}+r_nh_n.
\]
Moreover, the mean-value theorem and $g_{r_n}'\ge1$ give
\[
0<a(y_n)-\tilde\beta_n\le-r_nh_n\longrightarrow0.
\]
Because $a(y_n)$ remains bounded away from $0$ and $a_q$, and
$b_{r_n}\to0$ by \eqref{eq:br-properties} in
Lemma~\ref{lem:scale-properties}, it follows that
\[
b_{r_n}<\tilde\beta_n<a_q
\]
eventually.  Thus $\tilde\beta_n$ is the threshold $\beta_n$ in
\eqref{eq:beta-n-def}, so $G_n(\beta_n)=0$.  The mean-value theorem applied
to $g_{r_n}$ now gives, for some $\xi_n$ between $\beta_n$ and
$a(y_n)$,
\[
-r_nh_n
=
g_{r_n}\{a(y_n)\}-g_{r_n}(\beta_n)
=
(a(y_n)-\beta_n)\{1+r_ny'(\xi_n)\}.
\]
Therefore $\beta_n<a(y_n)$ and
\begin{equation}
a(y_n)-\beta_n
=
\frac{-r_nh_n}{1+r_ny'(\xi_n)}.
\label{eq:case-c-beta-gap}
\end{equation}
For some $\zeta_n$ between $\beta_n$ and $a(y_n)$,
\begin{equation}
\frac{\beta_n}{r_n}-s_n
=d_n
=y'(\zeta_n)\{a(y_n)-\beta_n\}.
\label{eq:case-c-dn-gap}
\end{equation}
Combining \eqref{eq:case-c-beta-gap} and~\eqref{eq:case-c-dn-gap} gives
\begin{equation}
s_nd_n
=
(r_ns_n)
\frac{y'(\zeta_n)}{1+r_ny'(\xi_n)}
(-h_n).
\label{eq:case-c-sn-dn-product}
\end{equation}
Here $r_ns_n\to a(y)>0$.  Also $\beta_n\to a(y)$ and $a(y_n)\to a(y)$, so
$\xi_n,\zeta_n\to a(y)$; hence $y'(\zeta_n)\to y'\{a(y)\}>0$, while
$1+r_ny'(\xi_n)\to1$.  Since $h_n\to-\infty$ by \eqref{eq:hn-minus-infty}, \eqref{eq:case-c-sn-dn-product} yields
\[
s_nd_n\longrightarrow\infty.
\]
Thus \eqref{eq:sn-dn-diverges} is proved.
\end{enumerate}

This proves \eqref{eq:secondary-range-target}.  Combining \eqref{eq:primary-active-uniform} and \eqref{eq:secondary-range-target}, and reducing $\gamma$ if necessary, proves \eqref{eq:no-earlier}.

\par\medskip\noindent
\textbf{Proof of \eqref{eq:rare-result}.}
{
Apply Lemma~\ref{lem:localized-crossing} to $\bar R_{r,-y}$, with
\[
 m_r(y)=\frac{a(y)}r,
 \qquad w_r(y)=1,
 \qquad d(y)=qM(y),
 \qquad \xi(y)=\kappa(y).
\]
The set $I$ is compact, and $a_I=\inf_{y\in I}a(y)>0$; hence, for every
fixed $H>0$,
\[
 \inf_{y\in I}\left\{\frac{a(y)}r-H\right\}
 \ge\frac{a_I}{r}-H>u_q
\]
for all sufficiently small $r$.  Because $I\subset(1,y_q)$ and $M$
is continuous and strictly increasing there,
\[
 0<d(y)=qM(y)<1,\qquad \xi(y)=\kappa(y)>0,
\]
and both functions are continuous on $I$.  Equation~\eqref{eq:rare-local}
is exactly \eqref{eq:localized-crossing-full}, while
\eqref{eq:no-earlier} is \eqref{eq:localized-crossing-left}.  Thus all
hypotheses of Lemma~\ref{lem:localized-crossing} hold, and
\eqref{eq:localized-crossing-cutoff} gives \eqref{eq:rare-result} uniformly
on $I$.}

\par\medskip\noindent
\textbf{Proof of \eqref{eq:rare-fdp-result}.}
{
Fix $H=1$.}
For
$y\in I$ and $|h|\le H$, let $\tilde{\alpha}_r(y,h)$ be the threshold
defined by \eqref{eq:tilde-alpha-equation}.  Write
\[
\bar R_{2,r,-y}\left(\frac{a(y)}r+h\right)
=\frac{qW_r\{\tilde{\alpha}_r(y,h)\}}{p(a(y)/r+h)}
=\bigl[1-qM\{y(\tilde{\alpha}_r(y,h))\}\bigr]
\frac{p\{\tilde{\alpha}_r(y,h)/r\}}{p(a(y)/r+h)}.
\]
Equation~\eqref{eq:rare-primary-scale-separation} shows that the
primary non-null is not rejected for $y\in I$ and $|h|\le H$.
Consequently, \eqref{eq:population-curve} gives
\[
\bar R_{r,-y}\left(\frac{a(y)}r+h\right)
=\bar R_{0,r,-y}\left(\frac{a(y)}r+h\right)
 +\bar R_{2,r,-y}\left(\frac{a(y)}r+h\right).
\]

We first differentiate the secondary non-null contribution
$\bar R_{2,r,-y}\{a(y)/r+h\}$.  Equation
\eqref{eq:two-secondary-lower-tail} holds uniformly, since
\[
 g_r(b_r)>0>ry-a(y)-rh
 =r\left\{y-\left(\frac{a(y)}r+h\right)\right\}
\]
for all sufficiently small $r$.
{
Apply \eqref{eq:two-secondary-block-log-derivative} in
Lemma~\ref{lem:two-block-derivatives} with
$c=a(y)/r+h$ and $\beta=\tilde{\alpha}_r(y,h)$.
The term in \eqref{eq:two-secondary-block-log-derivative},
\[
 -\frac{qM'\{y(\beta)\}y'(\beta)}
 {1-qM\{y(\beta)\}}
 \frac{r}{1+r y'(\beta)},
\]
is $O(r)$ uniformly by \eqref{eq:alpha-close} and
\eqref{eq:deficit-properties} in Lemma~\ref{lem:envelope}.  Indeed,
\eqref{eq:alpha-close} places $\beta$, uniformly over
$y\in I$ and $|h|\le H$, in a fixed compact subinterval of
$(0,a_q)$.  On this subinterval,
\[
 \frac{|M'\{y(\beta)\}|y'(\beta)}
 {1-qM\{y(\beta)\}}=O(1),
 \qquad
 \frac{r}{1+r y'(\beta)}=O(r),
\]
by \eqref{eq:deficit-properties} in Lemma~\ref{lem:envelope}; hence
their product is $O(r)$
uniformly.

The last two terms in \eqref{eq:two-secondary-block-log-derivative} are
\[
 -\frac{\lambda(\beta/r)}{1+r y'(\beta)}+\lambda(c).
\]
For these terms, \eqref{eq:two-secondary-threshold-equation} implies
\[
 \frac{\beta}{r}=c+y-y(\beta).
\]
Because $a(y)$ is bounded away from zero on $I$,
\eqref{eq:alpha-close} gives $c\asymp\beta/r\asymp r^{-1}$
uniformly.  Thus \eqref{eq:mills-hazard} in Lemma~\ref{lem:mills}
gives
\[
\begin{aligned}
 \lambda(c)-\frac{\lambda(\beta/r)}{1+r y'(\beta)}
 &=
 c-\frac{\beta/r}{1+r y'(\beta)}+O(r)\\
 &=
 \frac{rcy'(\beta)+y(\beta)-y}
 {1+r y'(\beta)}+O(r).
\end{aligned}
\]
Now $rc=a(y)+rh\to a(y)$, while
\eqref{eq:alpha-close} and continuity of $y$ and $y'$ give
\[
 y(\beta)-y=o(1),
 \qquad
 y'(\beta)=y'\{a(y)\}+o(1)
\]
uniformly.  Consequently,
\[
 \lambda(c)-\frac{\lambda(\beta/r)}{1+r y'(\beta)}
 \longrightarrow a(y)y'\{a(y)\}=\kappa(y)
\]
uniformly, by \eqref{eq:kappa}.  Combining this with
\eqref{eq:signal-local} yields
\begin{equation}
\frac{\partial}{\partial h}
\bar R_{2,r,-y}\left(\frac{a(y)}r+h\right)
\longrightarrow
\kappa(y)\{1-qM(y)\}e^{\kappa(y)h}
\label{eq:rare-signal-derivative}
\end{equation}
uniformly for $y\in I$ and $|h|\le H$.}

{
It remains to differentiate the null contribution.  Use the notation of
Lemma~\ref{lem:two-block-derivatives} at $c=a(y)/r+h$.  Since $a(y)$
is bounded away from zero on $I$ and
$a(y)\le a_q$, for all sufficiently small $r$,
\[
u_q\le \frac{a(y)}r+h\le \frac{a_q+1}{r}
\]
uniformly for $y\in I$ and $|h|\le H$.  Applying
\eqref{eq:null-tail} in Lemma~\ref{lem:null-tail} with
$A=a_q+1$ and $T=\sup_{u\in I}u$ shows that
\begin{equation}
 \sup_{y\in I}\sup_{|h|\le H}
 \bar R_{0,r,-y}\left(\frac{a(y)}r+h\right)=O(1).
\label{eq:rare-null-level-bound}
\end{equation}
Equation~\eqref{eq:two-null-block-log-derivative} in
Lemma~\ref{lem:two-block-derivatives} can be written as
\[
 \frac{\partial}{\partial h}\log\bar R_{0,r,-y}(c)
 =\sum_{\sigma\in\{-,+\}}
 \frac{Q_\sigma}{Q_++Q_-}
 \left\{\lambda(c)-\frac{\lambda(x_\sigma)}{\sqrt{1-r^2}}\right\},
\]
because $\partial c/\partial h=1$.  Moreover,
\eqref{eq:mills-hazard} in Lemma~\ref{lem:mills} gives, for either sign,
\[
\lambda(c)
-\frac{\lambda(x_\pm)}{\sqrt{1-r^2}}
=c-\frac{c\pm ry}{1-r^2}
+O(r)
=O(r)
\]
uniformly for $y\in I$ and $|h|\le H$.  Since the nonnegative weights
$Q_\sigma/(Q_++Q_-)$ sum to one,
\begin{equation}
 \sup_{y\in I}\sup_{|h|\le H}
 \left|\frac{\partial}{\partial h}
 \log\bar R_{0,r,-y}\left(\frac{a(y)}r+h\right)\right|=O(r).
\label{eq:rare-null-log-derivative-bound}
\end{equation}
Multiplying \eqref{eq:rare-null-level-bound} and
\eqref{eq:rare-null-log-derivative-bound} gives
\begin{equation}
\sup_{y\in I}\sup_{|h|\le H}
\left|
\frac{\partial}{\partial h}
\bar R_{0,r,-y}\left(\frac{a(y)}r+h\right)
\right|
\longrightarrow0.
\label{eq:rare-null-derivative}
\end{equation}}
Since $I$ is compact and
$\kappa(y)\{1-qM(y)\}e^{\kappa(y)h}$ is strictly positive on
$I\times[-H,H]$, \eqref{eq:rare-signal-derivative} and~\eqref{eq:rare-null-derivative} imply
\begin{equation}
\inf_{y\in I}\inf_{|h|\le H}
\frac{\partial}{\partial h}
\bar R_{r,-y}\left(\frac{a(y)}r+h\right)>0
\label{eq:rare-strict-increase}
\end{equation}
for all sufficiently small $r$.
For every fixed $H>0$, \eqref{eq:rare-null-local} verifies
\eqref{eq:localized-crossing-null} with $d(y)=qM(y)$.  The null
contribution is smooth, and \eqref{eq:rare-strict-increase}, with $H=1$,
gives the positive derivative required by
Lemma~\ref{lem:localized-crossing-regularity}.  That lemma
therefore shows that $C_r(-y)$ is regular for every $y\in I$ when $r$
is sufficiently small, and \eqref{eq:localized-crossing-fdp} gives
\[
 \sup_{y\in I}|D_r(-y)-qM(y)|\longrightarrow0,
\]
which is \eqref{eq:rare-fdp-result}.
\end{proof}

\subsubsection{\texorpdfstring{The regime $z<-y_q$}{The regime z < -yq}}

Let $y=-z$.
For $y>y_q$, let $\alpha_q(y)\in(0,a_q)$ be the unique solution of
\begin{equation}
qL_{\alpha_q(y)}(y)=1.
\label{eq:alpha}
\end{equation}
For fixed $y$, the map $a\mapsto L_a(y)$ is continuous and
\begin{equation}
\frac{\partial}{\partial a}\log L_a(y)=-a+y\tanh(ay).
\label{eq:La-log-derivative}
\end{equation}
By Lemma~\ref{lem:envelope}, this derivative is positive on $(0,a(y))$.  Since $y>y_q$, the same lemma gives $a(y)>a_q$, so $a\mapsto L_a(y)$ is strictly increasing on $[0,a_q]$.  Moreover, by the definition of $a_q$ in \eqref{eq:aq-def},
\[
qL_0(y)=q<1,
\quad
qL_{a_q}(y)>qL_{a_q}(y_q)=qM(y_q)=1,
\]
where the strict inequality follows from $a_q>0$, $y>y_q$, and the monotonicity of $\cosh(a_q y)$ in $y>0$.  Thus continuity and strict monotonicity give exactly one solution to \eqref{eq:alpha}.

\begin{lemma}
\label{lem:null-only}
For every compact $I\subset(y_q,\infty)$, uniformly for $y\in I$,
\begin{equation}
rC_r(-y)\longrightarrow\alpha_q(y)
\label{eq:null-only-result}
\end{equation}
and
\begin{equation}
D_r(-y)\longrightarrow1.
\label{eq:null-only-fdp-result}
\end{equation}
\end{lemma}

\begin{proof}
\textbf{Proof of \eqref{eq:null-only-result}.}
Fix a compact $I\subset(y_q,\infty)$, and put
\[
\delta_I=\inf_{y\in I}(y-y_q)>0.
\]
{
Use $s_r(y)$ from \eqref{eq:sr-def} and
$(\mathcal A_{r,y,s},\beta_{r,y,s})$ from
\eqref{eq:beta-rys-def}.  By \eqref{eq:gr} and
Lemma~\ref{lem:two-block-derivatives},
$g_r'(\tilde a)=1+r y'(\tilde a)>1$.
For all sufficiently small $r$, the primary non-null is not rejected
when $s>s_r(y)$.  To verify the corresponding sign assertion for the
secondary non-nulls, note that, conditional on $Z=-y$, the value associated
with $\tilde a\in[b_r,a_q]$ is
{
\begin{equation}
\frac{\tilde a}{r}+y(\tilde a)-y
\ge
\frac{b_r}{r}+y(b_r)-\sup_{u\in I}u.
\label{eq:null-only-secondary-positive-bound}
\end{equation}}
The monotonicity of $y(\cdot)$ gives
\eqref{eq:null-only-secondary-positive-bound}.  Its right-hand side tends to
infinity as $r\downarrow0$, by \eqref{eq:br-properties} in
Lemma~\ref{lem:scale-properties}.  Hence every
secondary non-null value is positive for all sufficiently small $r$,
uniformly over $y\in I$ and $\tilde a\in[b_r,a_q]$.  Thus the rejected
secondary non-nulls are indexed by $\mathcal A_{r,y,s}$.  If this
set is nonempty, continuity and strict monotonicity of $g_r$ show that it is
the closed interval $[\beta_{r,y,s},a_q]$ and that
\[
g_r(\beta_{r,y,s})\ge r(s+y).
\]
Consequently, in the nonempty case,
\begin{equation}
\frac{\beta_{r,y,s}}r-s
\ge y-y(\beta_{r,y,s})
\ge y-y_q
\ge\delta_I.
\label{eq:null-only-threshold-gap}
\end{equation}
If $\mathcal A_{r,y,s}=\varnothing$, its $\mu_r$-mass is zero.
Since $\mu_r(\{a_q\})=0$ by \eqref{eq:mur-survival}, the convention in
\eqref{eq:beta-rys-def} gives in both cases
\[
\mu_r(\mathcal A_{r,y,s})
=\mu_r([\beta_{r,y,s},a_q]).
\]
Using \eqref{eq:mur-survival}, \eqref{eq:deficit-properties} in
Lemma~\ref{lem:envelope}, and \eqref{eq:null-only-threshold-gap} when the set
is nonempty, we obtain
\[
0\le
\frac{q\tau_r}{p(s)}\mu_r([\beta_{r,y,s},a_q])
\le
\frac{p(s+\delta_I)}{p(s)}.
\]
Moreover,
\[
\inf_{y\in I}s_r(y)
=c_r+y(b_r)-\sup_{y\in I}y
\longrightarrow\infty,
\]
because $c_r\to\infty$, $y(b_r)\to1$, and $I$ is compact.
Therefore \eqref{eq:fixed-shift} in Lemma~\ref{lem:mills} gives
\begin{equation}
\sup_{y\in I}
\sup_{s>s_r(y)}
\frac{q\tau_r}{p(s)}
\mu_r([\beta_{r,y,s},a_q])
\longrightarrow0.
\label{eq:null-only-signal-small}
\end{equation}
}


The function $(a,y)\mapsto L_a(y)$ is $C^\infty$.
Equation~\eqref{eq:La-log-derivative}, together with
$\alpha_q(y)<a_q<a(y)$ and Lemma~\ref{lem:envelope}, shows that
\[
\frac{\partial}{\partial a}\log L_a(y)
\bigg|_{a=\alpha_q(y)}>0.
\]
The implicit function theorem therefore shows that
$y\mapsto\alpha_q(y)$ is continuous on $(y_q,\infty)$.  Since $I$ is
compact,
\begin{equation}
m_I
:=
\inf_{y\in I}
\min\{\alpha_q(y),a_q-\alpha_q(y)\}>0.
\label{eq:mI-def}
\end{equation}
Fix any $0<\delta<m_I/2$.  For every $y\in I$, continuity and strict
monotonicity in $a$ give
\[
qL_{\alpha_q(y)-\delta}(y)
<qL_{\alpha_q(y)}(y)=1
<qL_{\alpha_q(y)+\delta}(y).
\]
Both strict gaps are continuous functions of $y$.  Their minima over the
compact set $I$ are positive, so there is $\gamma>0$ such that, uniformly
on $I$,
\begin{equation}
qL_{\alpha_q(y)-\delta}(y)\le1-2\gamma,
\quad
qL_{\alpha_q(y)+\delta}(y)\ge1+2\gamma
\label{eq:null-only-margins}
\end{equation}
The choice $\delta<m_I/2$ also gives
\begin{equation}
\alpha_q(y)+\delta
\le \alpha_q(y)+\frac{m_I}{2}
{\le\frac{\alpha_q(y)+a_q}{2}<a_q<a(y)},
\label{eq:alphaq-delta-left}
\end{equation}
uniformly for $y\in I$.

Write $\psi_y(x)=\log L_x(y)$.  The proof of
Lemma~\ref{lem:envelope}, through \eqref{eq:gprime}, shows that
$\psi_y'(x)>0$ for $0<x<a(y)$.  By
\eqref{eq:alphaq-delta-left}, every
$x\in(0,\alpha_q(y)+\delta)$ lies in $(0,a(y))$.  Hence
$\partial_x L_x(y)={L_x(y)\psi_y'(x)}>0$ throughout
$(0,\alpha_q(y)+\delta)$, and therefore $x\mapsto L_x(y)$ is
increasing on $[0,\alpha_q(y)+\delta]$.

On $u_q\le s\le s_r(y)$,
\eqref{eq:primary-active-uniform} in
Lemma~\ref{lem:primary-active-range} gives
\[
 \sup_{y\in I}\sup_{u_q\le s\le s_r(y)}
 \bar R_{r,-y}(s)\le q+o(1).
\]

For $s>s_r(y)$, the term in \eqref{eq:population-curve} that corresponds to the primary non-nulls is zero, and \eqref{eq:null-only-signal-small} and \eqref{eq:null-tail} in Lemma~\ref{lem:null-tail} give, uniformly for $y\in I$ and $s_r(y)<s\le(\alpha_q(y)+\delta)/r$,
\[
\bar R_{r,-y}(s)
=
\bar R_{0,r,-y}(s)
+
\frac{q\tau_r}{p(s)}
\mu_r([\beta_{r,y,s},a_q])
=
qL_{rs}(y)+o(1).
\]
Combining these two ranges gives
\begin{equation}
\sup_{u_q\le s\le(\alpha_q(y)-\delta)/r}
\bar R_{r,-y}(s)
\le
qL_{\alpha_q(y)-\delta}(y)+o(1)
\le1-\gamma.
\label{eq:null-only-left-margin}
\end{equation}
Since $rs_r(y)\to0$ uniformly on $I$ and
$\alpha_q(y)+\delta$ is bounded away from zero, we have
\[
\frac{\alpha_q(y)+\delta}{r}>s_r(y)
\]
for all sufficiently small $r$, uniformly on $I$.  At the cutoff
$(\alpha_q(y)+\delta)/r$, the term in \eqref{eq:population-curve} that
corresponds to the primary non-nulls is zero, while the secondary term is
nonnegative.  Therefore \eqref{eq:null-tail} in Lemma~\ref{lem:null-tail}
gives, uniformly for $y\in I$,
\begin{equation}
\bar R_{r,-y}\left(\frac{\alpha_q(y)+\delta}{r}\right)
\ge
\bar R_{0,r,-y}\left(\frac{\alpha_q(y)+\delta}{r}\right)
=
qL_{\alpha_q(y)+\delta}(y)+o(1).
\label{eq:null-only-right-margin}
\end{equation}
By \eqref{eq:null-only-margins}, the right side is at least $1+\gamma$
for all sufficiently small $r$.  Hence
\[
\alpha_q(y)-\delta<rC_r(-y)\le\alpha_q(y)+\delta.
\]
Letting $\delta\downarrow0$ gives
\[
rC_r(-y)\longrightarrow\alpha_q(y),
\]
uniformly for $y\in I$.

\par\medskip\noindent
\textbf{Proof of \eqref{eq:null-only-fdp-result}.}
We now verify regularity for each fixed sufficiently small $r$.  Fix one
$0<\delta<m_I/2$ as in \eqref{eq:mI-def} and consider the interval
\[
\frac{\alpha_q(y)-\delta}{r}
\le s\le
\frac{\alpha_q(y)+\delta}{r}.
\]
The primary non-null has conditional value
\[
T_i
=
c_r+y(b_r)-y
=s_r(y).
\]
It is positive for sufficiently small $r$, uniformly in $y\in I$, and it
is rejected at cutoff $s$ exactly when $s\le s_r(y)$.  Since
$\delta<m_I/2$ and $m_I\le\alpha_q(y)$, we have
$\alpha_q(y)-\delta\ge m_I/2$.  On the other hand,
\[
r s_r(y)
=
r c_r+r\{y(b_r)-y\}
\longrightarrow0
\]
uniformly for $y\in I$, by \eqref{eq:cr-properties}, $y(b_r)\to1$, and
compactness of $I$.  Therefore, for all sufficiently small $r$, for every
$y\in I$ and every cutoff $s$ satisfying
\[
\frac{\alpha_q(y)-\delta}{r}
\le s\le
\frac{\alpha_q(y)+\delta}{r},
\]
we have
\[
s_r(y)
<
\frac{\alpha_q(y)-\delta}{r}
\le s.
\]
{
Thus every cutoff in this interval lies strictly to the right of the primary
value $s_r(y)$, so the primary non-null is not rejected there.  Moreover,
uniformly for these $y$ and $s$,
\[
\begin{aligned}
r(s+y)-g_r(b_r)
&\ge
\alpha_q(y)-\delta+r\{y-y(b_r)\}-b_r
\ge\frac{m_I}{2}-o(1)>0,\\
g_r(a_q)-r(s+y)
&\ge
a_q-\alpha_q(y)-\delta+r(y_q-y)
\ge\frac{m_I}{2}-o(1)>0.
\end{aligned}
\]
Strict monotonicity of $g_r$ therefore implies that
$\mathcal A_{r,y,s}\ne\varnothing$, that
$\beta_{r,y,s}\in(b_r,a_q)$.
{
By \eqref{eq:beta-rys-def}, continuity and strict monotonicity of
$g_r$ give
\[
 g_r(\beta_{r,y,s})=r(s+y).
\]
Using $g_r(a)=a+ry(a)$ from \eqref{eq:gr}, this equality yields
\[
\beta_{r,y,s}
=rs+r\{y-y(\beta_{r,y,s})\}
=rs+O(r)
\]
uniformly.}  Hence, for all sufficiently small $r$,
\[
\frac{m_I}{4}\le\beta_{r,y,s}\le a_q-\frac{m_I}{4},
\]
so the thresholds remain in a fixed compact subinterval of
$(0,a_q)$.
}

For $y\in I$ and cutoffs $s$ in the local crossing interval
\[
\frac{\alpha_q(y)-\delta}{r}
\le s\le
\frac{\alpha_q(y)+\delta}{r},
\]
write the secondary non-null contribution as
\[
\bar R_{2,r,-y}(s)
=\bigl[1-qM\{y(\beta_{r,y,s})\}\bigr]
\frac{p(\beta_{r,y,s}/r)}{p(s)}.
\]
Then
\[
 \bar R_{r,-y}(s)=\bar R_{0,r,-y}(s)+\bar R_{2,r,-y}(s).
\]
Abbreviate $\beta=\beta_{r,y,s}$.
Equation~\eqref{eq:two-secondary-lower-tail} holds uniformly because
$g_r(b_r)>0>r(y-s)$ for all sufficiently small $r$.
{
The term in
\eqref{eq:two-secondary-block-log-derivative} of
Lemma~\ref{lem:two-block-derivatives}, evaluated at
$c=s$ and $\beta_{r,y}(s)=\beta_{r,y,s}=\beta$, is
\[
 -\frac{qM'\{y(\beta)\}y'(\beta)}
 {1-qM\{y(\beta)\}}
 \frac{r}{1+r y'(\beta)}.
\]
Because
\[
 \frac{m_I}{4}\le\beta\le a_q-\frac{m_I}{4},
\]
\eqref{eq:deficit-properties} in Lemma~\ref{lem:envelope} and continuity
give a constant $C_I<\infty$ such that
\[
 \sup_{m_I/4\le a\le a_q-m_I/4}
 \left|
 \frac{qM'\{y(a)\}y'(a)}{1-qM\{y(a)\}}
 \right|\le C_I.
\]
Since $y'(\beta)>0$,
\[
 0<\frac{r}{1+r y'(\beta)}\le r,
\]
and therefore
\[
 \left|
 \frac{qM'\{y(\beta)\}y'(\beta)}
 {1-qM\{y(\beta)\}}
 \frac{r}{1+r y'(\beta)}
 \right|\le C_Ir.
\]

The expressions in
\eqref{eq:two-secondary-block-log-derivative} are
\[
 -\frac{\lambda(\beta/r)}{1+r y'(\beta)}
 \qquad\text{and}\qquad
 \lambda(s).
\]
To bound their sum, write
\[
 \lambda(t)=t+\varepsilon(t),
 \qquad 0<\varepsilon(t)<t^{-1},
\]
by \eqref{eq:mills-hazard} in Lemma~\ref{lem:mills}.  On the cutoff range,
\[
 s\ge\frac{m_I}{2r},
 \qquad
 \frac\beta r\ge\frac{m_I}{4r},
\]
and hence $\varepsilon(s)=O(r)$ and
$\varepsilon(\beta/r)=O(r)$ uniformly.  Using
$\beta/r=s+y-y(\beta)$, we obtain
\[
\begin{aligned}
 \lambda(s)-\frac{\lambda(\beta/r)}{1+r y'(\beta)}
 &=s-\frac{\beta/r}{1+r y'(\beta)}+O(r)\\
 &=\frac{rs y'(\beta)+y(\beta)-y}
 {1+r y'(\beta)}+O(r)
 =O(1),
\end{aligned}
\]
uniformly, because $rs$, $y$, $y(\beta)$, and $y'(\beta)$ are
uniformly bounded.  Hence
\begin{equation}
\sup_{y\in I}
\sup_{|rs-\alpha_q(y)|\le\delta}
\left|
\frac{\partial}{\partial s}\log\bar R_{2,r,-y}(s)
\right|
=O(1).
\label{eq:null-only-signal-log-bound}
\end{equation}}
Moreover, $\beta_{r,y,s}/r-s\ge\delta_I$ by
\eqref{eq:null-only-threshold-gap}, so
$\beta_{r,y,s}/r\ge s+\delta_I$.  Since $p$ is decreasing on
$[0,\infty)$, and since \eqref{eq:deficit-properties} in
Lemma~\ref{lem:envelope} gives
$0\le1-qM\{y(\beta_{r,y,s})\}\le1$, we have
\[
0\le\bar R_{2,r,-y}(s)
\le
\frac{p(s+\delta_I)}{p(s)}.
\]
Applying \eqref{eq:mills-shift-upper} in Lemma~\ref{lem:mills} with
$x=s$ and $\delta=\delta_I$ gives
\begin{equation}
0\le\bar R_{2,r,-y}(s)
\le
\frac{p(s+\delta_I)}{p(s)}
\le
(1+s^{-2})
\exp\left\{-s\delta_I-\frac{\delta_I^2}{2}\right\}
=o(r),
\label{eq:null-only-signal-size}
\end{equation}
uniformly on the interval.  The last $o(r)$ follows because
\eqref{eq:mI-def} and
$0<\delta<m_I/2$ imply
\[
s
\ge
\frac{\alpha_q(y)-\delta}{r}
\ge
\frac{m_I}{2r}
\]
whenever $y\in I$ and $|rs-\alpha_q(y)|\le\delta$, and therefore
\[
r^{-1}(1+s^{-2})
\exp\left\{-s\delta_I-\frac{\delta_I^2}{2}\right\}
\le
r^{-1}(1+o(1))
\exp\left\{-\frac{m_I\delta_I}{2r}-\frac{\delta_I^2}{2}\right\}
\longrightarrow0
\]
uniformly.  Since
$\partial_s\bar R_{2,r,-y}(s)
=\bar R_{2,r,-y}(s)\partial_s\log\bar R_{2,r,-y}(s)$,
\eqref{eq:null-only-signal-log-bound} and~\eqref{eq:null-only-signal-size} imply
\begin{equation}
\sup_{y\in I}
\sup_{|rs-\alpha_q(y)|\le\delta}
\left|\frac{\partial}{\partial s}\bar R_{2,r,-y}(s)\right|
=o(r).
\label{eq:null-only-signal-derivative}
\end{equation}

{
For the null contribution term, put
\[
 x_+=\frac{s+ry}{\sqrt{1-r^2}},
 \qquad
 x_-=\frac{s-ry}{\sqrt{1-r^2}},
 \qquad
 Q_\pm=\frac{\Phib(x_\pm)}{\Phib(s)}.
\]
Because $\alpha_q(y)-\delta\ge m_I/2$, the range in
\eqref{eq:null-only-signal-log-bound} implies
\[
 s\ge\frac{m_I}{2r}\longrightarrow\infty,
\]
while $rs$ and $y$ range over compact sets.  Therefore
\eqref{eq:null-tail-expansion} in Lemma~\ref{lem:null-tail}, with
$z=-y$, gives uniformly
\[
 Q_+
 =e^{-(rs)^2/2-rsy}+o(1),
 \qquad
 Q_-
 =e^{-(rs)^2/2+rsy}+o(1).
\]
Indeed, $s/x_\pm=1+o(1)$, the $O(r^2)$ term in
\eqref{eq:null-tail-expansion} is uniform, and its remainder tends to zero
because $s\to\infty$ uniformly.

Next, \eqref{eq:mills-hazard-expansion} in Lemma~\ref{lem:mills} gives
\begin{equation}
\begin{aligned}
 \frac1r\left\{\lambda(s)
 -\frac{\lambda(x_+)}{\sqrt{1-r^2}}\right\}
 &=-rs-y+o(1),\\
 \frac1r\left\{\lambda(s)
 -\frac{\lambda(x_-)}{\sqrt{1-r^2}}\right\}
 &=-rs+y+o(1).
\end{aligned}
\label{eq:null-only-scaled-hazards}
\end{equation}
More precisely, for either sign,
\[
 \lambda(s)-\frac{\lambda(x_\pm)}{\sqrt{1-r^2}}
 =s-\frac{s\pm ry}{1-r^2}
 +\frac1s-\frac1{s\pm ry}+O(r^3),
\]
where
\[
 \frac1s-\frac1{s\pm ry}=O(r^3),
 \qquad
 \frac1r\left\{s-\frac{s\pm ry}{1-r^2}\right\}
 =\frac{-rs\mp y}{1-r^2}.
\]
This proves \eqref{eq:null-only-scaled-hazards}.

Substitution of these four expansions into
\eqref{eq:two-null-block-derivative} in
Lemma~\ref{lem:two-block-derivatives}, together with
$\pi_{0,r}\to1$, yields
\[
\begin{aligned}
 \frac1r\frac{\partial}{\partial s}\bar R_{0,r,-y}(s)
 &=\frac q2 e^{-(rs)^2/2}
 \left[e^{-rsy}(-rs-y)+e^{rsy}(-rs+y)\right]+o(1)\\
 &=q e^{-(rs)^2/2}
 \{-rs\cosh(rsy)+y\sinh(rsy)\}+o(1).
\end{aligned}
\]
Finally, differentiating
$L_a(y)=e^{-a^2/2}\cosh(ay)$ gives
\[
 \frac{\partial}{\partial a}L_a(y)
 =e^{-a^2/2}\{-a\cosh(ay)+y\sinh(ay)\}.
\]
Evaluating at $a=rs$ proves
\begin{equation}
\frac1r\frac{\partial}{\partial s}\bar R_{0,r,-y}(s)
=
q e^{-(rs)^2/2}
\{-rs\cosh(rsy)+y\sinh(rsy)\}+o(1)
=q\frac{\partial}{\partial a}L_a(y)\bigg|_{a=rs}+o(1).
\label{eq:null-only-null-derivative}
\end{equation}}
{
By \eqref{eq:mI-def} and \eqref{eq:alphaq-delta-left}, the pairs
$(rs,y)$ under consideration range
over a compact subset of
$\{(a,y):y\in I,\ 0<a<a(y)\}$.  Continuity,
\eqref{eq:La-log-derivative}, and Lemma~\ref{lem:envelope} therefore show that
$\partial_aL_a(y)|_{a=rs}$ is bounded away from zero uniformly.}
Combining
\eqref{eq:null-only-signal-derivative} and~\eqref{eq:null-only-null-derivative} yields
\begin{equation}
\inf_{y\in I}
\inf_{|rs-\alpha_q(y)|\le\delta}
\frac{\partial}{\partial s}\bar R_{r,-y}(s)>0
\label{eq:null-only-strict-increase}
\end{equation}
for all sufficiently small $r$.  Equation~\eqref{eq:null-only-result}
gives, uniformly for $y\in I$,
\[
 \frac{\alpha_q(y)-\delta}{r}
 <C_r(-y)<
 \frac{\alpha_q(y)+\delta}{r}
\]
for all sufficiently small $r$.  Equation
\eqref{eq:null-only-strict-increase} and the smoothness of the null
contribution for
$|rs-\alpha_q(y)|\le\delta$
verify the hypotheses of Proposition~\ref{prop:local-regularity}; hence
$C_r(-y)$ is regular.

Equation~\eqref{eq:Dr} gives
\[
 D_r(-y)=\bar R_{0,r,-y}\{C_r(-y)\}.
\]
Because $rC_r(-y)\to\alpha_q(y)$ uniformly and
$\alpha_q(y)$ stays in a compact subset of $(0,a_q)$,
\eqref{eq:null-tail} in Lemma~\ref{lem:null-tail} applies at
$c=C_r(-y)$ and gives
\[
D_r(-y)
=qL_{rC_r(-y)}(y)+o(1)
\longrightarrow qL_{\alpha_q(y)}(y)=1,
\]
uniformly for $y\in I$, where the equality follows from
\eqref{eq:alpha}.  This proves \eqref{eq:null-only-fdp-result}.
\end{proof}

\subsubsection{\texorpdfstring{Conditional limit of $D_r$}{Conditional limit of Dr}}

The following lemma establishes the limit of $D_r(z)$ as $r \downarrow 0$, with $D_*$ defined in Section~\ref{sec:roadmap}.
\begin{lemma}
\label{lem:continuum-limit}
For every $z\notin\{-1,-y_q\}$,
\begin{equation}
D_r(z)\longrightarrow D_*(z).
\label{eq:pointwise-D}
\end{equation}
Consequently,
\begin{equation}
\mathbb E[D_r(Z)]\longrightarrow\mathbb E[D_*(Z)]=\ell_{=}(q).
\label{eq:ED-limit}
\end{equation}
\end{lemma}

\begin{proof}
If $z>-1$, Lemma~\ref{lem:primary} gives $D_r(z)\to q$.  If $-y_q<z<-1$, put $y=-z$ and apply Lemma~\ref{lem:rare-local}.  If $z<-y_q$, apply Lemma~\ref{lem:null-only}.  This proves \eqref{eq:pointwise-D}.

At every regular crossing, $0\le D_r\le1$; the value assigned at nonregular points also lies in $[0,1]$.  Dominated convergence gives the convergence in \eqref{eq:ED-limit}.  Finally,
\begin{align*}
\mathbb E[D_*(Z)]
&=
q\mathbb P(Z>-1)
+q\int_{-y_q}^{-1}M(-z)\phi(z)\dd z
+\mathbb P(Z<-y_q)\\
&=
q\Phi(1)
+q\int_1^{y_q}M(y)\phi(y)\dd y
+\Phib(y_q)\\
&=\ell_{=}(q).
\end{align*}
\end{proof}

\subsection{Proofs of Theorem~\ref{thm:main} and
Propositions~\ref{prop:ell-expansion} and~\ref{prop:ell-strict}}

\begin{proof}[Proof of Theorem~\ref{thm:main}]
Lemma~\ref{lem:continuum-limit} gives
$\mathbb E\{D_*(Z)\}=\ell_{=}(q)$.  Fix $\delta>0$.  Choose a compact set
\[
E\subset\R\setminus\{-1,-y_q\}
\]
such that
\[
\int_E D_*(z)\phi(z)\dd z>{\ell_{=}}(q)-\frac{\delta}{4}.
\]
Because $E$ is compact and separated from $-1$ and
$-y_q$, the sets
\[
E_+=E\cap(-1,\infty),\qquad
E_0=E\cap(-y_q,-1),\qquad
E_-=E\cap(-\infty,-y_q)
\]
are compact after discarding the empty ones.  Apply the compact-uniform
regime estimates on these pieces: \eqref{eq:primary-local}-\eqref{eq:primary-left-bound}
on $E_+$, \eqref{eq:rare-local}-\eqref{eq:no-earlier} on $E_0$, and
\eqref{eq:null-only-left-margin}-\eqref{eq:null-only-right-margin} on
$E_-$, together with the corresponding null limits
\eqref{eq:null-tail} and \eqref{eq:rare-null-local}.  Taking the minimum of
the positive crossing margins over the nonempty pieces and then taking $r$
sufficiently small, we obtain brackets
\[
A_r(z)<B_r(z),\quad z\in E,
\]
and a constant $\gamma>0$, such that
\[
\sup_{z\in E}\sup_{u_q\le c\le A_r(z)}\bar R_{r,z}(c)\le1-\gamma,
\quad
\inf_{z\in E}\bar R_{r,z}\{B_r(z)\}\ge1+\gamma,
\]
\[
\sup_{z\in E}\sup_{A_r(z)\le c\le B_r(z)}
|\bar R_{0,r,z}(c)-D_*(z)|
\le\frac{\delta}{8}.
\]
Fix such an $r$ and put
\[
 C_*=\sup_{z\in E}B_r(z)<\infty.
\]
For $z\in E$, define
\[
 \mathcal E_N(z)
 =
 \max\left\{
 \|\widehat R_N-R_{r,z}\|_{\infty,[0,1]},
 \|\widehat R_{0,N}-\pi_{0,r}R_{0,r,z}\|_{\infty,[0,1]}
 \right\}
\]
and
\[
 t_*=\frac{p(C_*)}{q}
 \min\left\{\frac{\gamma}{2},\frac{\delta}{16}\right\}>0.
\]
Following the argument in the proof of
Theorem~\ref{thm:population-transfer}, on the event
$\mathcal E_N(z)<t_*$, for $u_q\le c\le C_*$,
\[
\begin{aligned}
 \left|
 \frac{q\widehat R_N\{p(c)\}}{p(c)}-\bar R_{r,z}(c)
 \right|
 &\le\frac{q\mathcal E_N(z)}{p(C_*)},\\
 \left|
 \frac{q\widehat R_{0,N}\{p(c)\}}{p(c)}
 -\bar R_{0,r,z}(c)
 \right|
 &\le\frac{q\mathcal E_N(z)}{p(C_*)}.
\end{aligned}
\]
The first bound and the two crossing margins imply
\[
 A_r(z)<\widehat C_N\le B_r(z).
\]
The second bound, \eqref{eq:exact-FDP}, and the null bracket then give
\[
 \FDP
 \ge \bar R_{0,r,z}(\widehat C_N)-\frac{\delta}{16}
 \ge D_*(z)-\frac{3\delta}{16}.
\]
Lemma~\ref{lem:DKW} gives, uniformly for $z\in E$,
\[
 \mathbb P\{\mathcal E_N(z)\ge t_*\mid Z=z\}
 \le \eta_N:=4e^{-2Nt_*^2}\longrightarrow0.
\]
Since $\FDP\ge0$ and $0\le D_*\le1$, conditional expectation and
integration over $E$ yield
\[
\begin{aligned}
 \mathbb E_{\Omega_N,Z,\varepsilon}[\FDP]
 &\ge
 (1-\eta_N)
 \int_E\left(D_*(z)-\frac{3\delta}{16}\right)_+
 \phi(z)\dd z\\
 &\ge
 \int_E D_*(z)\phi(z)\dd z-\frac{3\delta}{16}-\eta_N.
\end{aligned}
\]
Choose $N$ large enough that $\eta_N<\delta/16$.  Using the choice of
$E$ and \eqref{eq:FDRomega}, we obtain
\[
\mathbb E_{\Omega_N}\!\left[
\FDR_{\Omega_N}(\BH_q)
\right]
>
\ell_{=}(q)-\frac{\delta}{2}.
\]
For such an $N$, some realization $\omega^\star$ satisfies
\[
\FDR_{\omega^\star}(\BH_q)>{\ell_{=}}(q)-\frac{\delta}{2}.
\]
By Lemma~\ref{lem:eta}, choose $\eta>0$ so small that
\begin{equation}
{
\FDR_{\omega^\star}^{(\eta)}(\BH_q)
>
\FDR_{\omega^\star}(\BH_q)-\frac{\delta}{2}
>
\ell_{=}(q)-\delta.}
\label{eq:perturbed-fdr-lower}
\end{equation}
{
The perturbed vector $T^{(\eta)}$ has finite dimension $N$, mean vector
$(\theta_i)_{i=1}^N\in\mathbb R^N$, and covariance matrix
$\Sigma_{\omega^\star,\eta}$, which has unit diagonal and is strictly
positive definite by \eqref{eq:eta-PD} in Lemma~\ref{lem:eta}.  Thus the
bound \eqref{eq:perturbed-fdr-lower} establishes \eqref{eq:main}.  Since
$\delta>0$ was
arbitrary, taking the supremum proves \eqref{eq:sup}.}
\end{proof}

\begin{proof}[Proof of Proposition~\ref{prop:ell-expansion}]
Recall from Lemma~\ref{lem:envelope} that, for $y>1$, $a(y)$ is the
unique positive maximizer of $a\mapsto L_a(y)$, equivalently the unique
positive solution of
\[
a(y)=y\tanh\{a(y)y\}.
\]
By the monotonicity of $a(\cdot)$ established in that lemma,
$a(y)\ge a(2)>0$ for $y\ge2$, so
$a(y)y\to\infty$.
Moreover,
\[
0\le y-a(y)
=y\left[1-\tanh\{a(y)y\}\right]
\le2y e^{-2a(y)y}
\longrightarrow0.
\]
Because $a(y)$ is the maximizer defining $M(y)$, we have
$M(y)=L_{a(y)}(y)$.  Substituting the definitions of $L_{a(y)}(y)$
and $\phi(y)$, expanding
$\cosh(t)=(e^t+e^{-t})/2$, and completing the two squares gives
{
\begin{equation}
\begin{aligned}
M(y)\phi(y)
&=
e^{-a(y)^2/2}\cosh\{a(y)y\}
\frac{e^{-y^2/2}}{\sqrt{2\pi}}\\
&=
\frac{1}{2\sqrt{2\pi}}
\left[
e^{-\{a(y)^2+y^2\}/2+a(y)y}
+e^{-\{a(y)^2+y^2\}/2-a(y)y}
\right]\\
&=
\frac{1}{2\sqrt{2\pi}}
\left[
e^{-\{y-a(y)\}^2/2}
+e^{-\{y+a(y)\}^2/2}
\right].
\end{aligned}
\label{eq:Mphi-completed-squares}
\end{equation}}
Consequently, $M(y)\phi(y)\to 1/(2\sqrt{2\pi})$.  The difference
$M(y)\phi(y)-1/(2\sqrt{2\pi})$ is integrable on $[1,\infty)$.  Indeed, for all
sufficiently large $y$, $a(y)\ge y/2$, so
\[
y-a(y)\le2y e^{-y^2},
\]
while
\[
\left|e^{-\{y-a(y)\}^2/2}-1\right|
\le\frac{\{y-a(y)\}^2}{2},
\quad
e^{-\{y+a(y)\}^2/2}\le e^{-y^2/2}.
\]
It follows from the definition of $c_\ell$ that, as $Y\to\infty$,
\begin{equation}
{
\int_1^Y M(y)\phi(y)\dd y
=\frac{Y}{2\sqrt{2\pi}}+c_\ell-\Phi(1)+o(1).}
\label{eq:integral-M-asymptotic}
\end{equation}

Next, \eqref{eq:Mphi-completed-squares} gives
\[
M(y)
=
\frac12e^{y^2/2}
\left[
e^{-\{y-a(y)\}^2/2}
+e^{-\{y+a(y)\}^2/2}
\right]
=\frac12e^{y^2/2}\{1+o(1)\}.
\]
{
Since $M(y_q)=1/q\to\infty$, \eqref{eq:envelope-limits} in
Lemma~\ref{lem:envelope} implies $y_q\to\infty$.  The identity
$qM(y_q)=1$ therefore gives}
\begin{equation}
{
y_q^2
=2\log(1/q)+2\log2+o(1),
\quad
y_q=\sqrt{2\log(1/q)}+o(1).}
\label{eq:yq-small-q}
\end{equation}
Equations~\eqref{eq:mills-upper} in Lemma~\ref{lem:mills} and
\eqref{eq:yq-small-q} give
\begin{equation}
{
\Phib(y_q)
\le\frac{\phi(y_q)}{y_q}
=O\left(\frac{q}{y_q}\right)
=o(q).}
\label{eq:yq-tail-small-q}
\end{equation}
Substituting \eqref{eq:integral-M-asymptotic},
\eqref{eq:yq-small-q}, and \eqref{eq:yq-tail-small-q} into
\eqref{eq:ell} yields
\[
\begin{aligned}
\ell_{=}(q)
&=q\Phi(1)+q\left\{\frac{y_q}{2\sqrt{2\pi}}+c_\ell-\Phi(1)+o(1)\right\}+o(q)\\
&=\frac{q\sqrt{\log(1/q)}}{2\sqrt\pi}+{c_\ell}q+o(q).
\end{aligned}
\]
Numerical quadrature of the absolutely convergent integral defining
$c_\ell$ gives $c_\ell=0.6492828\ldots$.
\end{proof}

\begin{proof}[Proof of Proposition~\ref{prop:ell-strict}]
Since $q\in(0,1)$, \eqref{eq:yq} gives $M(y_q)=1/q>1$.  By Lemma~\ref{lem:envelope}, $M=1$ on $[0,1]$ and $M$ is strictly increasing on $(1,\infty)$, so $y_q>1$ and $M(y)\ge1$ for $1\le y\le y_q$.  Using \eqref{eq:ell},
\[
\begin{aligned}
\ell_{=}(q)-q
&=
q\Phi(1)+q\int_1^{y_q}M(y)\phi(y)\dd y+\Phib(y_q)\\
&\quad
-q\left\{\Phi(1)+\int_1^{y_q}\phi(y)\dd y+\Phib(y_q)\right\}\\
&=
q\int_1^{y_q}\{M(y)-1\}\phi(y)\dd y
+(1-q)\Phib(y_q).
\end{aligned}
\]
The integral is nonnegative, and $(1-q)\Phib(y_q)>0$ because $q<1$ and $y_q<\infty$.  Hence ${\ell_{=}}(q)>q$.
\end{proof}

\begingroup

\section{Lower bound for one-sided tests}
\label{sec:one-sided-lower}

\subsection{Main result}

For $0<q<1$, define
\begin{equation}
 y_q^+=\sqrt{2\log(1/q)}
 \label{eq:one-yq}
\end{equation}
and
\begin{equation}
 \ell_{\le}(q)
 =\frac{q\sqrt{\log(1/q)}}{\sqrt\pi}+\frac q2+\Phib(y_q^+).
 \label{eq:one-ell}
\end{equation}

The quantities in \eqref{eq:one-yq} and \eqref{eq:one-ell}
determine the finite-dimensional one-sided Gaussian lower bound.
\begin{theorem}
\label{thm:one-lower}
For every $q\in(0,1)$ and $\delta>0$, there are $N<\infty$,
$\theta\in\R^N$, and a positive definite correlation matrix $\Sigma$
such that BH at level $q$, applied to the one-sided $p$-values
$P_i=\Phib(T_i)$ from $T\sim N(\theta,\Sigma)$, satisfies
\[
 \FDR_{\theta,\Sigma}(\BH_q)>\ell_{\le}(q)-\delta.
\]
Every true null in the construction has $\theta_i=0$, and every
non-null
has $\theta_i>0$.
\end{theorem}

The first proposition gives the small-$q$ expansion of the one-sided lower
bound.
\begin{proposition}
\label{prop:one-expansion}
As $q\downarrow0$,
\[
 \ell_{\le}(q)
 =\frac{q\sqrt{\log(1/q)}}{\sqrt\pi}+\frac q2+o(q).
\]
In particular, $\ell_{\le}(q)/q\to\infty$.
\end{proposition}

The next proposition shows strict anticonservativeness at every nontrivial
nominal level.
\begin{proposition}
\label{prop:one-strict}
For every $q\in(0,1)$, $\ell_{\le}(q)>q$.
\end{proposition}

Figure~\ref{fig:one-ellq} in the Introduction plots $\ell_{\le}(q)-q$ and
$\ell_{\le}(q)/q$ over the grid $q=0.005k$, $k=1,\ldots,199$.
Table~\ref{tab:one-ell} gives the absolute inflation
$\ell_{\le}(q)-q$ and relative inflation $\ell_{\le}(q)/q$ for commonly
used nominal levels.

\subsection{Roadmap}

Fix $q$.  For a small $r>0$, let
$(\Theta_i,B_i)_{i=1}^N$ be i.i.d. from a law $\nu_{q,r}^+$, independently
of $Z,\varepsilon_1,\ldots,\varepsilon_N$, which are independent standard
normal variables, and set
\begin{equation}
 T_i=\Theta_i+B_iZ+\sqrt{1-B_i^2}\,\varepsilon_i.
 \label{eq:one-population-model}
\end{equation}
In the model \eqref{eq:one-population-model}, the law
$\nu_{q,r}^+$ has one null component and two non-null
components.  We
first analyze the population BH crossing conditional on $Z=z$.  For
every $z\notin\{0,y_q^+\}$, its conditional FDP converges, as
$r\downarrow0$, to
\begin{equation}
{
 D_+^*(z)=
 \begin{cases}
 q,&z\leq0,\\
 qe^{z^2/2},&0<z<y_q^+,\\
 1,&z\geq y_q^+.
 \end{cases}
}
 \label{eq:one-Dstar}
\end{equation}
The definition~\eqref{eq:one-Dstar} specifies the values at
$\{0,y_q^+\}$; these
values do not affect the expectation because the boundary points have zero
probability.  Therefore
\[
 \mathbb E\{D_+^*(Z)\}
 =\frac q2+q\int_0^{y_q^+}e^{z^2/2}\phi(z)\dd z+\Phib(y_q^+)
 =\ell_{\le}(q).
\]

We reuse the machinery and use similar notation in Subsections~\ref{sec:generic}
and~\ref{sec:finite-transfer}.  Throughout this section, put $p_+(x)=\Phib(x)$ and
$u_s^+=p_+^{-1}(s)$.  For $x\geq0$ and
$0<s\leq1/2$,
\begin{equation}
 p_+(x)=\frac{p(x)}2,
 \qquad
 p_+^{-1}(s)=p^{-1}(2s).
 \label{eq:one-two-tail-bridge}
\end{equation}
Therefore, all bounds for $p$ in Lemma~\ref{lem:mills} remain to apply
to $p_+$ up to a constant.  Use the symbols
\[
 \pi_0^+,\ R_z^+,\ R_{0,z}^+,\ \bar R_z^+,\ \bar R_{0,z}^+,
 \ C^+(z),\ D^+(z)
\]
as the one-sided analogues of the quantities in
\eqref{eq:pi0-generic} and \eqref{eq:Rz-generic}-\eqref{eq:D-generic}.
In particular, the one-sided population cutoff is
\[
 C^+(z)=\inf\{c\geq u_q^+:\bar R_z^+(c)\geq1\},
\]
and every one-sided use of Definition~\ref{def:regular} has lower endpoint
$u_q^+$ in place of $u_q$.
The only change to \eqref{eq:Ftheta-formula}-\eqref{eq:Ftheta-degenerate}
is
\begin{equation}
 F^+_{\theta,b,z}(s)
 =\Phib\!\left(\frac{u_s^+-\theta-bz}{\sqrt{1-b^2}}\right),
 \qquad |b|<1,
 \label{eq:one-conditional-cdf}
\end{equation}
while
$F^+_{\theta,b,z}(s)=\1\{\theta+bz\geq u_s^+\}$ for $|b|=1$.
We retain the empty-crossing convention $C^+(z)=\infty$, $D^+(z)=0$,
and the regularity definition in Definition~\ref{def:regular}.

The proofs of Lemmas~\ref{lem:DKW} and~\ref{lem:exact-BH} and
Theorem~\ref{thm:population-transfer} are p-value agnostic and apply after
\eqref{eq:one-conditional-cdf}; the one-sided rejection set in
Lemma~\ref{lem:exact-BH} is $\{i:T_i\geq\widehat C_N\}$.  We also use the
localized DKW bracketing in the proof of
Theorem~\ref{thm:population-transfer}.  Finally, the perturbation
\eqref{eq:eta-model}-\eqref{eq:eta-cov} and Lemma~\ref{lem:eta} apply to the
one-sided p-values as well, because their continuity argument does not use
the two-sided form of $p$.

{\subsection{Construction of
\texorpdfstring{$\nu_{q,r}^+$}{nu+(q,r)}}}

This is the one-sided, sign-reversed specialization of the three-component
construction in Subsection~\ref{sec:continuum-design}: the signal offset
$y(a)$ is replaced by $a$, the envelope term $M\{y(a)\}$ by
$e^{a^2/2}$, and the non-null loading $+1$ by $-1$.

Take $r>0$, and set
\begin{equation}
 b_r^+=r\,p_+^{-1}(r^2).
 \label{eq:one-br}
\end{equation}
We henceforth assume $r$ is sufficiently small that $r^2<1/2$ and
$b_r^+<y_q^+$.  For $b_r^+\leq a\leq y_q^+$, define
\begin{equation}
 W_r^+(a)=\frac{\{1-qe^{a^2/2}\}p_+(a/r)}{q}.
 \label{eq:one-Wr}
\end{equation}
Both factors in the numerator are nonnegative and decreasing in $a$, and the first
vanishes at $a=y_q^+$.  Hence $W_r^+$ is continuous and decreasing.  Put
\begin{equation}
 \tau_r^+=W_r^+(b_r^+),
 \qquad
 \mu_r^+([a,y_q^+])=\frac{W_r^+(a)}{\tau_r^+},
 \quad b_r^+\leq a\leq y_q^+.
 \label{eq:one-tau-mu}
\end{equation}
Thus $\mu_r^+$ is a probability measure on $[b_r^+,y_q^+]$.  Since
$p_+(b_r^+/r)=r^2$, \eqref{eq:one-two-tail-bridge} and the
quantile expansion
\eqref{eq:mills-quantile} in Lemma~\ref{lem:mills} gives $b_r^+\to0$, and hence
\begin{equation}
 \tau_r^+\sim\frac{1-q}{q}r^2.
 \label{eq:one-tau-asymptotic}
\end{equation}
Finally, set
\begin{equation}
 \pi_{0,r}^+=1-r-\tau_r^+,
 \qquad
 p_+(c_r^+)=\frac{q(r+\tau_r^+)}{1-q\pi_{0,r}^+}.
 \label{eq:one-pi-cr}
\end{equation}
For all sufficiently small $r$, these quantities are well-defined and
$\pi_{0,r}^+>0$.

The law $\nu_{q,r}^+$ is displayed in Table~\ref{tab:one-construction}.
Equivalently, for bounded measurable $f$,
\begin{equation}
 \int f\,\dd\nu_{q,r}^+
 =\pi_{0,r}^+f(0,r)
 +rf(c_r^++b_r^+,-1)
 +\tau_r^+\int_{b_r^+}^{y_q^+}f(a/r+a,-1)\,\mu_r^+(\dd a).
 \label{eq:one-nu}
\end{equation}

\begin{table}[ht]

\centering
\caption{One-sided population construction.  The opposite loading signs are essential.}
\label{tab:one-construction}
\begin{tabular}{lccc}
\toprule
Type & Mass & $\Theta$ & $B$\\
\midrule
Nulls & $\pi_{0,r}^+$ & $0$ & $r$\\
Primary non-nulls & $r$ & $c_r^++b_r^+$ & $-1$\\
Secondary non-nulls & $\tau_r^+\mu_r^+(\dd a)$ & $a/r+a$ &
$-1$, $a\in[b_r^+,y_q^+]$\\
\bottomrule
\end{tabular}
\end{table}

Under \eqref{eq:one-nu}, the nulls become more significant
when $Z$ is positive.  Every
non-null
statistic is deterministic conditional on $Z$ and decreases with $Z$.
The construction is not PRDS.  To see this directly, pair a null $i$ with
a non-null $j$, and fix $v\in(0,1)$.  Conditional on
$P_i=s$, the event
$\{P_j\geq v\}$, which is increasing in the p-values, has probability
\[
 \Phi\!\left(
 \frac{p_+^{-1}(v)-\theta_j+r p_+^{-1}(s)}{\sqrt{1-r^2}}
 \right),
\]
strictly decreasing in $s$.  This also exhibits the negative
null-to-non-null covariance, opposite to the nonnegative
covariance assumption
that guarantees Gaussian one-sided PRDS
\citep{BenjaminiYekutieli2001,chi2025multiple}.  On the other hand, all
null-null correlations equal $r^2$, so the null p-values are positively
regression dependent and the full vector is PRDN in the terminology of
\citet{Su2018}.

\vspace{1em}

\subsection{Population analysis}

\subsubsection{Preliminaries}

The next lemma gives the one-sided counterparts of
\eqref{eq:br-properties}-\eqref{eq:cr-properties}.
\begin{lemma}
\label{lem:one-scale-properties}
As $r\downarrow0$,
\begin{equation}
 b_r^+\to0,\qquad b_r^+/r\to\infty,\qquad c_r^+\to\infty,
 \qquad rc_r^+\to0,\qquad b_r^+/r-c_r^+\to\infty.
 \label{eq:one-scale-properties}
\end{equation}
\end{lemma}

\begin{proof}
By \eqref{eq:one-br} and the quantile expansion
\eqref{eq:mills-quantile} in Lemma~\ref{lem:mills},
\[
 \frac{b_r^+}{r}=p_+^{-1}(r^2)
 \sim2\sqrt{\log(1/r)}\to\infty,
 \qquad
 b_r^+\sim2r\sqrt{\log(1/r)}\to0.
\]
Moreover, \eqref{eq:one-tau-asymptotic} gives
$\tau_r^+=O(r^2)$ and hence $\pi_{0,r}^+\to1$.  Therefore
\eqref{eq:one-pi-cr} yields
\[
 p_+(c_r^+)\sim\frac{qr}{1-q}.
\]
Another application of \eqref{eq:mills-quantile} in
Lemma~\ref{lem:mills} gives
\[
 c_r^+\sim\sqrt{2\log(1/r)}.
\]
Thus $c_r^+\to\infty$ and $rc_r^+\to0$, while
\[
 \frac{b_r^+}{r}-c_r^+
 \sim(2-\sqrt2)\sqrt{\log(1/r)}
 \longrightarrow\infty.
\]
\end{proof}

Apply the reused population notation to $\nu_{q,r}^+$, and write the
resulting quantities as
$R_{r,z}^+$, $R_{0,r,z}^+$, $\bar R_{r,z}^+$,
$\bar R_{0,r,z}^+$, $\bar R_{1,r,z}^+$,
$\bar R_{2,r,z}^+$, $C_r^+(z)$, and $D_r^+(z)$.
Then
\begin{align}
 \bar R_{r,z}^+(c)
 &=\bar R_{0,r,z}^+(c)
 +\bar R_{1,r,z}^+(c)
 +\bar R_{2,r,z}^+(c),
 \label{eq:one-population-curve}\\
 \bar R_{0,r,z}^+(c)
 &=q\pi_{0,r}^+
 \frac{p_+\{(c-rz)/\sqrt{1-r^2}\}}{p_+(c)}.
 \label{eq:one-null-curve}\\
 \bar R_{1,r,z}^+(c)
 &{=\frac{qr}{p_+(c)}
 \1\{c\leq c_r^++b_r^+-z\},}
 \label{eq:one-primary-curve}\\
 \bar R_{2,r,z}^+(c)
 &=\frac{q\tau_r^+}{p_+(c)}
 \mu_r^+\!\left(\left[\frac{r(c+z)}{1+r},y_q^+\right]\right).
 \label{eq:one-secondary-curve}
\end{align}

The next lemma derives the derivatives of the null and secondary non-null
contributions.
\begin{lemma}
\label{lem:one-block-derivatives}
For $c>0$, put
\[
 u=\frac{c-rz}{\sqrt{1-r^2}}.
\]
The null contribution satisfies
\begin{align}
 \frac{\dd}{\dd c}\log\bar R_{0,r,z}^+(c)
 &=\lambda(c)-\frac{\lambda(u)}{\sqrt{1-r^2}},
 \label{eq:one-null-block-log-derivative}\\
 \frac{\dd}{\dd c}\bar R_{0,r,z}^+(c)
 &=\bar R_{0,r,z}^+(c)
 \left\{\lambda(c)-\frac{\lambda(u)}{\sqrt{1-r^2}}\right\}.
 \label{eq:one-null-block-derivative}
\end{align}
Define
\[
 \beta_{r,z}(c)=\frac{r(c+z)}{1+r}.
\]
If $\beta_{r,z}(c)\in(b_r^+,y_q^+)$, then
\begin{equation}
 \bar R_{2,r,z}^+(c)
 =\left[1-qe^{\{\beta_{r,z}(c)\}^2/2}\right]
 \frac{p_+\{\beta_{r,z}(c)/r\}}{p_+(c)}
 \label{eq:one-secondary-block-formula}
\end{equation}
and
\begin{equation}
 \frac{\dd}{\dd c}\log\bar R_{2,r,z}^+(c)
 =-\frac{qr\beta_{r,z}(c)e^{\{\beta_{r,z}(c)\}^2/2}}
 {(1+r)\left[1-qe^{\{\beta_{r,z}(c)\}^2/2}\right]}
 +\lambda(c)-\frac{\lambda\{\beta_{r,z}(c)/r\}}{1+r}.
 \label{eq:one-secondary-block-log-derivative}
\end{equation}
\end{lemma}

\begin{proof}
Since
\[
 \frac{\dd u}{\dd c}=\frac1{\sqrt{1-r^2}},
 \qquad
 \frac{\dd}{\dd t}\log p_+(t)
 =\frac{p_+'(t)}{p_+(t)}=-\lambda(t),
\]
Equation~\eqref{eq:one-null-curve} gives
\begin{align*}
 \frac{\dd}{\dd c}\log\bar R_{0,r,z}^+(c)
 &=\frac{\dd}{\dd c}
 \left[
   \log(q\pi_{0,r}^+)+\log p_+(u)-\log p_+(c)
 \right]\\
 &=-\frac{\lambda(u)}{\sqrt{1-r^2}}+\lambda(c),
\end{align*}
which is \eqref{eq:one-null-block-log-derivative}.  Therefore
\begin{align*}
 \frac{\dd}{\dd c}\bar R_{0,r,z}^+(c)
 &=\bar R_{0,r,z}^+(c)
 \frac{\dd}{\dd c}\log\bar R_{0,r,z}^+(c)\\
 &=\bar R_{0,r,z}^+(c)
 \left\{\lambda(c)-\frac{\lambda(u)}{\sqrt{1-r^2}}\right\},
\end{align*}
which proves \eqref{eq:one-null-block-derivative}.

Now suppose that
$\beta_{r,z}(c)\in(b_r^+,y_q^+)$.  By
\eqref{eq:one-secondary-curve}, \eqref{eq:one-tau-mu}, and
\eqref{eq:one-Wr},
\begin{align*}
 \bar R_{2,r,z}^+(c)
 &=\frac{q\tau_r^+}{p_+(c)}
 \mu_r^+([\beta_{r,z}(c),y_q^+])\\
 &=\frac{qW_r^+\{\beta_{r,z}(c)\}}{p_+(c)}\\
 &=\left[1-qe^{\{\beta_{r,z}(c)\}^2/2}\right]
 \frac{p_+\{\beta_{r,z}(c)/r\}}{p_+(c)}.
\end{align*}
This proves \eqref{eq:one-secondary-block-formula}.  Moreover,
\[
 \frac{\partial\beta_{r,z}(c)}{\partial c}=\frac{r}{1+r}.
\]
Since $\beta_{r,z}(c)<y_q^+$, we have
$1-qe^{\{\beta_{r,z}(c)\}^2/2}>0$, and hence
\begin{align*}
 \frac{\dd}{\dd c}\log\bar R_{2,r,z}^+(c)
 &=-\frac{q\beta_{r,z}(c)e^{\{\beta_{r,z}(c)\}^2/2}}
 {1-qe^{\{\beta_{r,z}(c)\}^2/2}}
 \frac{\partial\beta_{r,z}(c)}{\partial c}\\
 &\quad
 -\lambda\{\beta_{r,z}(c)/r\}\frac1r
 \frac{\partial\beta_{r,z}(c)}{\partial c}
 +\lambda(c)\\
 &=-\frac{qr\beta_{r,z}(c)e^{\{\beta_{r,z}(c)\}^2/2}}
 {(1+r)[1-qe^{\{\beta_{r,z}(c)\}^2/2}]}
 +\lambda(c)-\frac{\lambda\{\beta_{r,z}(c)/r\}}{1+r}.
\end{align*}
This proves \eqref{eq:one-secondary-block-log-derivative}.
\end{proof}

The next lemma gives the limit of the null contribution.
\begin{lemma}
\label{lem:one-null-sequential}
For every compact
$X\subset[0,\infty)$ and $K\subset\mathbb R$, as $r\downarrow0$
and $c\to\infty$, uniformly over $z\in K$ subject to $rc\in X$,
\begin{equation}
 \bar R_{0,r,z}^+(c)
 =q\exp\left\{(rc)z-\frac{(rc)^2}{2}\right\}+o(1).
 \label{eq:one-null-sequential}
\end{equation}
In particular, if $c=c(r)\to\infty$ and $rc\to x\geq0$, then the
left-hand side converges to
$q\exp(xz-x^2/2)$, uniformly for $z$ in compact sets.
\end{lemma}

\begin{proof}

Set
\[
 \Delta_r=\frac{c-rz}{\sqrt{1-r^2}}-c.
\]
Because $rc$ and $z$ range over compact sets while $c\to\infty$,
uniformly over the stated range,
$\Delta_r=O(r)=o(1)$ and
\begin{align*}
 c\Delta_r
 &=c^2\left\{\frac{1}{\sqrt{1-r^2}}-1\right\}
   -\frac{rzc}{\sqrt{1-r^2}}\\
 &=\frac12(rc)^2-z(rc)+o(1),
\end{align*}
where the remainder is uniform.  The hazard expansion
\eqref{eq:mills-hazard-expansion} in Lemma~\ref{lem:mills}, together with
$c\to\infty$ and $\Delta_r=o(1)$, gives
\[
 \log\frac{p_+(c+\Delta_r)}{p_+(c)}
 =-\int_c^{c+\Delta_r}\lambda(t)\,\dd t
 =-c\Delta_r+o(1)
\]
uniformly on the same range.  Exponentiating, using
$(c-rz)/\sqrt{1-r^2}=c+\Delta_r$, and then applying
\eqref{eq:one-null-curve} together with $\pi_{0,r}^+\to1$ proves
\eqref{eq:one-null-sequential}.
\end{proof}


The following lemma is the one-sided analogue of
Lemma~\ref{lem:localized-crossing}.
\begin{lemma}
\label{lem:one-localized-crossing}
Let $K$ be compact.  For $z\in K$, let
$m_r(z)>u_q^+$ and $w_r(z)>0$.
Suppose that, for every fixed $H>0$,
\begin{equation}
 \inf_{z\in K}\{m_r(z)-Hw_r(z)\}>u_q^+
 \label{eq:one-localized-crossing-domain}
\end{equation}
for all sufficiently small $r$, and
\begin{equation}
 \sup_{z\in K}\sup_{|h|\le H}
 \left|
 \bar R_{r,z}^+\{m_r(z)+w_r(z)h\}
 -d(z)-\{1-d(z)\}e^{\xi(z)h}
 \right|\longrightarrow0,
 \label{eq:one-localized-crossing-full}
\end{equation}
where $d:K\to[0,1)$ and $\xi:K\to(0,\infty)$ are continuous.
Suppose also that, for every $h_0>0$,
\begin{equation}
 \limsup_{r\downarrow0}\sup_{z\in K}
 \sup_{u_q^+\le c\le m_r(z)-w_r(z)h_0}
 \bar R_{r,z}^+(c)<1.
 \label{eq:one-localized-crossing-left}
\end{equation}
Then
\begin{equation}
 \sup_{z\in K}
 \left|\frac{C_r^+(z)-m_r(z)}{w_r(z)}\right|
 \longrightarrow0.
 \label{eq:one-localized-crossing-cutoff}
\end{equation}
\end{lemma}

\begin{proof}
The proof of Lemma~\ref{lem:localized-crossing} applies with
$u_q$, $\bar R_{r,z}$, and $C_r(z)$ replaced by
$u_q^+$, $\bar R_{r,z}^+$, and $C_r^+(z)$, respectively.
\end{proof}



The following lemma is the one-sided analogue of
Lemma~\ref{lem:localized-crossing-regularity}.
\begin{lemma}
\label{lem:one-localized-crossing-regularity}
Under the assumptions and notation of
Lemma~\ref{lem:one-localized-crossing}, assume in addition that, for every
fixed $H>0$,
\begin{equation}
 \sup_{z\in K}\sup_{|h|\le H}
 \left|
 \bar R_{0,r,z}^+\{m_r(z)+w_r(z)h\}-d(z)
 \right|\longrightarrow0.
 \label{eq:one-localized-crossing-null}
\end{equation}
If, for some $H_*>0$ and all sufficiently small $r$, the map
\[
 h\longmapsto\bar R_{r,z}^+\{m_r(z)+w_r(z)h\}
\]
is differentiable with positive derivative on $(-H_*,H_*)$, and the map
\[
 h\longmapsto\bar R_{0,r,z}^+\{m_r(z)+w_r(z)h\}
\]
is continuous there for every $z\in K$, then $C_r^+(z)$ is regular and
\begin{equation}
 \sup_{z\in K}|D_r^+(z)-d(z)|\longrightarrow0.
 \label{eq:one-localized-crossing-fdp}
\end{equation}
\end{lemma}

\begin{proof}
The proof of Lemma~\ref{lem:localized-crossing-regularity} applies with
$u_q$, $\bar R_{r,z}$, $\bar R_{0,r,z}$, $C_r(z)$, and $D_r(z)$
replaced by $u_q^+$, $\bar R_{r,z}^+$, $\bar R_{0,r,z}^+$,
$C_r^+(z)$, and $D_r^+(z)$, respectively.
\end{proof}


The next lemma shows that the primary non-null contribution is negligible uniformly
away from $z=0$.
\begin{lemma}
\label{lem:one-primary-bound}
For every compact $K\subset(0,\infty)$, uniformly for $z\in K$, the
primary non-null contribution in \eqref{eq:one-population-curve}, whenever nonzero,
is bounded by
\begin{equation}
 \frac{qr}{p_+(c_r^++b_r^+-z)}=o(1).
 \label{eq:one-primary-bound}
\end{equation}
\end{lemma}

\begin{proof}
Whenever the primary non-null contribution is nonzero, the indicator in
\eqref{eq:one-primary-curve} equals one, so
$\bar R_{1,r,z}^+(c)=qr/p_+(c)$.  Equation~\eqref{eq:one-primary-curve}
also gives
$c\leq c_r^++b_r^+-z$.  Since $p_+$ is decreasing,
\[
 \frac{qr}{p_+(c)}
 \leq \frac{qr}{p_+(c_r^++b_r^+-z)}.
\]
The right-hand side is the expression in \eqref{eq:one-primary-bound}.
By \eqref{eq:one-pi-cr}, it can be written as
\begin{equation*}
 \frac{qr}{p_+(c_r^++b_r^+-z)}
 =\frac{r(1-q\pi_{0,r}^+)}{r+\tau_r^+}
 \frac{p_+(c_r^+)}{p_+(c_r^++b_r^+-z)}.
\end{equation*}
Fix a compact $K\subset(0,\infty)$, and put
$\delta_{r,z}=z-b_r^+$.  By \eqref{eq:one-scale-properties} in
Lemma~\ref{lem:one-scale-properties}, $\delta_{r,z}$ remains in a fixed
compact subset of $(0,\infty)$, uniformly for $z\in K$, and
$c_r^+-\delta_{r,z}\to\infty$ uniformly.  Therefore
\eqref{eq:fixed-shift} in Lemma~\ref{lem:mills}, applied with
$x=c_r^+-\delta_{r,z}$, gives
\[
 \frac{p_+(c_r^+)}{p_+(c_r^++b_r^+-z)}
 =\frac{p_+(x+\delta_{r,z})}{p_+(x)}\longrightarrow0
\]
uniformly for $z\in K$.  Since
$0<r(1-q\pi_{0,r}^+)/(r+\tau_r^+)\leq1$, the expression in
\eqref{eq:one-primary-bound} is $o(1)$ uniformly.
\end{proof}

The next lemma bounds the secondary non-null contribution in the two positive-
$z$ regimes.
\begin{lemma}
\label{lem:one-secondary-bound}
For all $c,z\in\mathbb R$,
\begin{equation}
 0\leq \frac{q\tau_r^+}{p_+(c)}
 \mu_r^+\!\left(\left[\frac{r(c+z)}{1+r},y_q^+\right]\right)
 \leq\frac{p_+\{(c+z)/(1+r)\}}{p_+(c)}.
 \label{eq:one-secondary-bound}
\end{equation}
\end{lemma}

\begin{proof}
If $r(c+z)/(1+r)\leq b_r^+$, then
\[
 q\tau_r^+\leq p_+(b_r^+/r)
 \leq p_+\{(c+z)/(1+r)\}.
\]
If $b_r^+<r(c+z)/(1+r)<y_q^+$, then
\begin{align*}
 q\tau_r^+\mu_r^+\!\left(\left[\frac{r(c+z)}{1+r},y_q^+\right]\right)
 &=\left[1-q\exp\left\{\frac{r^2(c+z)^2}{2(1+r)^2}\right\}\right]
 p_+\!\left(\frac{c+z}{1+r}\right)\\
 &\leq p_+\!\left(\frac{c+z}{1+r}\right).
\end{align*}
If $r(c+z)/(1+r)\geq y_q^+$, the contribution is zero.  Dividing these
bounds by $p_+(c)$ proves \eqref{eq:one-secondary-bound}.
\end{proof}

\subsubsection{\texorpdfstring{The regime $z<0$}{The regime z < 0}}

\begin{lemma}
\label{lem:one-negative-regime}
For every compact $K\subset(-\infty,0)$, uniformly for $z\in K$,
{\begin{equation}
 C_r^+(z)=c_r^++o\{(c_r^+)^{-1}\}
 \label{eq:one-negative-cutoff}
\end{equation}
and
\begin{equation}
 D_r^+(z)\longrightarrow q.
 \label{eq:one-negative-fdp}
\end{equation}}
Moreover, for all sufficiently small $r$, $C_r^+(z)$ is regular for
every $z\in K$.
\end{lemma}

\begin{proof}
\textbf{Proof of \eqref{eq:one-negative-cutoff}.}
Fix a compact $K\subset(-\infty,0)$.  Uniformly for $z\in K$ and bounded
$h$, all primary and secondary non-nulls are rejected at
the cutoff $c_r^++h/c_r^+$.  Indeed, the primary statistic equals
$c_r^++b_r^+-z$, so its distance above the cutoff is
$b_r^+-z-h/c_r^+$.  This converges to $-z>0$ because
$b_r^+\to0$, $c_r^+\to\infty$, and $h$ is bounded.

Among the
secondary non-nulls, the smallest statistic is attained at
$a=b_r^+$.
Its distance above the cutoff is
\[
 \frac{b_r^+}{r}+b_r^+-z-c_r^+-\frac{h}{c_r^+}
 =\left(\frac{b_r^+}{r}-c_r^+\right)
  +b_r^+-z-\frac{h}{c_r^+},
\]
which tends to infinity by \eqref{eq:one-scale-properties} in
Lemma~\ref{lem:one-scale-properties}.  Thus both gaps are positive for all
sufficiently small $r$, uniformly when $z$ ranges over a compact subset
of $(-\infty,0)$ and $h$ remains bounded.

Since every non-null is rejected,
\[
 \bar R_{r,z}^+\!\left(c_r^++\frac h{c_r^+}\right)
 =\bar R_{0,r,z}^+\!\left(c_r^++\frac h{c_r^+}\right)
  +\frac{q(r+\tau_r^+)}{p_+(c_r^++h/c_r^+)}.
\]
For every fixed $H>0$,
\eqref{eq:one-scale-properties} in
Lemma~\ref{lem:one-scale-properties} gives, uniformly for $z\in K$ and
$|h|\leq H$,
\[
 c_r^++\frac h{c_r^+}\longrightarrow\infty,
 \qquad
 r\left(c_r^++\frac h{c_r^+}\right)\longrightarrow0.
\]
Therefore \eqref{eq:one-null-sequential} in
Lemma~\ref{lem:one-null-sequential} directly yields
\[
 \bar R_{0,r,z}^+\!\left(c_r^++\frac h{c_r^+}\right)\longrightarrow q
\]
uniformly for $z\in K$ and $|h|\leq H$.
For the combined non-null contribution, the
calibration \eqref{eq:one-pi-cr} gives the exact identity
\begin{equation}
 \frac{q(r+\tau_r^+)}{p_+(c_r^++h/c_r^+)}
 =(1-q\pi_{0,r}^+)
 \frac{p_+(c_r^+)}{p_+(c_r^++h/c_r^+)}.
 \label{eq:one-negative-nonnull-calibration}
\end{equation}
The tail ratio in
\eqref{eq:one-negative-nonnull-calibration} tends to $e^h$ by
\eqref{eq:h-over-x} in
Lemma~\ref{lem:mills}, whereas $1-q\pi_{0,r}^+\to1-q$.  Combining the
two contributions gives
\begin{equation}
 \bar R_{r,z}^+(c_r^++h/c_r^+)
 \longrightarrow q+(1-q)e^h,
 \qquad
 \bar R_{0,r,z}^+(c_r^++h/c_r^+)\longrightarrow q.
 \label{eq:one-negative-local}
\end{equation}
The first limit is below one for $h<0$, equals one at zero, and is above
one for $h>0$.

We next exclude earlier crossings.  By
\eqref{eq:one-scale-properties} in
Lemma~\ref{lem:one-scale-properties}, uniformly for $z\in K$, all
non-nulls are rejected when $u_q^+\leq c\leq c_r^+$, and
$(c-rz)/\sqrt{1-r^2}>c$ for small $r$.  Hence
\begin{equation}
 \bar R_{r,z}^+(c)
 <q\pi_{0,r}^++\frac{q(r+\tau_r^+)}{p_+(c)}
 \leq q\pi_{0,r}^++\frac{q(r+\tau_r^+)}{p_+(c_r^+)}=1.
 \label{eq:one-negative-left-pointwise}
\end{equation}
For every fixed $h_0>0$,
\eqref{eq:one-negative-left-pointwise} and the
calibration \eqref{eq:one-pi-cr} give, uniformly for $z\in K$,
\begin{equation}
\begin{aligned}
 \sup_{u_q^+\leq c\leq c_r^+-h_0/c_r^+}\bar R_{r,z}^+(c)
 &\leq q\pi_{0,r}^+
 +(1-q\pi_{0,r}^+)
 \frac{p_+(c_r^+)}{p_+(c_r^+-h_0/c_r^+)}\\
 &\longrightarrow q+(1-q)e^{-h_0}<1.
\end{aligned}
 \label{eq:one-negative-left}
\end{equation}
Thus Lemma~\ref{lem:one-localized-crossing} applies
with
\[
 m_r(z)=c_r^+,
 \qquad w_r(z)=\frac1{c_r^+},
 \qquad d(z)=q,
 \qquad \xi(z)=1.
\]
Equations~\eqref{eq:one-negative-local} and
\eqref{eq:one-negative-left} verify
\eqref{eq:one-localized-crossing-full} and
\eqref{eq:one-localized-crossing-left}, respectively.  Equation
\eqref{eq:one-localized-crossing-cutoff} therefore gives
\eqref{eq:one-negative-cutoff}.

\par\medskip\noindent
\textbf{Proof of \eqref{eq:one-negative-fdp}.}
To apply
Lemma~\ref{lem:one-localized-crossing-regularity}, it remains to
prove that the derivative of
$\bar R_{r,z}^+(c_r^++h/c_r^+)$ with respect to $h$ is positive
there.
{
Fix $H<\infty$.  Uniformly for $z\in K$ and $|h|\le H$,
{
put
\[
 c=c_r^++\frac{h}{c_r^+},
 \qquad
 u=\frac{c-rz}{\sqrt{1-r^2}}.
\]
Equation~\eqref{eq:one-scale-properties} in
Lemma~\ref{lem:one-scale-properties} gives
$c/c_r^+\to1$ and $u/c_r^+\to1$ uniformly.  Hence
\eqref{eq:mills-hazard} in Lemma~\ref{lem:mills} gives
\[
\begin{aligned}
 \lambda(c)-\frac{\lambda(u)}{\sqrt{1-r^2}}
 &=c-\frac{u}{\sqrt{1-r^2}}+O\{(c_r^+)^{-1}\}\\
 &=\frac{rz-r^2c}{1-r^2}+O\{(c_r^+)^{-1}\}\\
 &=O_{K,H}\!\left(r+r^2c_r^++\frac1{c_r^+}\right)
 =o(c_r^+).
\end{aligned}
\]
Thus the hazard difference in
\eqref{eq:one-null-block-derivative} is $o(c_r^+)$ uniformly.}
Applying
\eqref{eq:one-null-block-derivative} in
Lemma~\ref{lem:one-block-derivatives}, differentiating the fully rejected
non-null contribution directly using
$p_+'(c)=-\lambda(c)p_+(c)$, and then using
\eqref{eq:one-negative-local}, the calibration \eqref{eq:one-pi-cr},
and \eqref{eq:h-over-x} in Lemma~\ref{lem:mills}, gives
\[
\begin{aligned}
 \frac{\partial}{\partial h}
 \bar R_{0,r,z}^+\!\left(c_r^++\frac h{c_r^+}\right)
 &\longrightarrow0,
 &
 \frac{\partial}{\partial h}
 \frac{q(r+\tau_r^+)}{p_+(c_r^++h/c_r^+)}
 &\longrightarrow(1-q)e^h,\\
 \frac{\partial}{\partial h}
 \bar R_{r,z}^+\!\left(c_r^++\frac h{c_r^+}\right)
 &\longrightarrow(1-q)e^h.
\end{aligned}
\]}
Since $\inf_{|h|\le H}(1-q)e^h=(1-q)e^{-H}>0$, for all sufficiently
small $r$,
\begin{equation}
 \inf_{z\in K}\inf_{|h|\le H}
 \frac{\partial}{\partial h}
 \bar R_{r,z}^+\!\left(c_r^++\frac h{c_r^+}\right)>0.
 \label{eq:one-negative-positive-derivative}
\end{equation}
The second limit in \eqref{eq:one-negative-local} verifies
\eqref{eq:one-localized-crossing-null}.  The derivative
bound \eqref{eq:one-negative-positive-derivative} and
continuity of the null contribution verify the remaining hypotheses of
Lemma~\ref{lem:one-localized-crossing-regularity}.  That lemma
therefore gives regularity, and
\eqref{eq:one-localized-crossing-fdp} gives
\eqref{eq:one-negative-fdp}, uniformly on $K$.
\end{proof}

\subsubsection{\texorpdfstring{The regime $z\in(0,y_q^+)$}{The regime 0 < z < yq+}}

\begin{lemma}
\label{lem:one-middle-regime}
For every compact $K\subset(0,y_q^+)$, uniformly for $z\in K$,
{\begin{equation}
 C_r^+(z)=\frac zr+o(1)
 \label{eq:one-middle-cutoff}
\end{equation}
and
\begin{equation}
 D_r^+(z)\longrightarrow qe^{z^2/2}.
 \label{eq:one-middle-fdp}
\end{equation}}
Moreover, for all sufficiently small $r$, $C_r^+(z)$ is regular for
every $z\in K$.
\end{lemma}

\begin{proof}
\textbf{Proof of \eqref{eq:one-middle-cutoff}.}
Fix a compact $K\subset(0,y_q^+)$ and $H>0$, and put $c=z/r+h$.
On $z\in K$ and $|h|\leq H$, the primary non-null contribution in
\eqref{eq:one-population-curve} is nonzero only if
\[
 c_r^++b_r^+-z\geq\frac zr+h.
\]
Let $\delta_K=\inf_{z\in K}z>0$.  Uniformly for $z\in K$ and
$|h|\leq H$,
\[
\begin{aligned}
 r\left\{\frac zr+h-(c_r^++b_r^+-z)\right\}
 &=z+rh-rc_r^+-rb_r^++rz\\
 &\geq\delta_K-rH-rc_r^+-rb_r^++r\delta_K
 \longrightarrow\delta_K>0
\end{aligned}
\]
by \eqref{eq:one-scale-properties} in
Lemma~\ref{lem:one-scale-properties}.  Hence
\begin{equation}
 c_r^++b_r^+-z<\frac zr+h
 \label{eq:one-middle-primary-absent}
\end{equation}
{
for all sufficiently small $r$, uniformly for $z\in K$ and
$|h|\le H$, so the primary non-null contribution is absent.}

{A secondary non-null is rejected if and only if
\[
 a\geq\beta_{r,z}(c)=z+\frac{rh}{1+r}.
\]
Compactness of $K\subset(0,y_q^+)$ implies that
$\beta_{r,z}(c)\in(b_r^+,y_q^+)$ for all sufficiently small $r$,
uniformly for $z\in K$ and $|h|\le H$.  In the formula for
$\bar R_{2,r,z}^+(c)$ in Lemma~\ref{lem:one-block-derivatives},
\[
 \beta_{r,z}(c)\longrightarrow z,
 \qquad
 \frac{\beta_{r,z}(c)}r=\frac zr+\frac{h}{1+r},
\]
uniformly on $K\times[-H,H]$, so its first factor converges to
$1-qe^{z^2/2}$.  With $x=z/r$,
\eqref{eq:mills-local-ratio} in Lemma~\ref{lem:mills} and the identity
$p_+(x+u)/p_+(x+v)=p(x+u)/p(x+v)$ give
\[
\begin{aligned}
 \log
 \frac{p_+\{x+h/(1+r)\}}{p_+(x+h)}
 &=
 \log\frac{x+h}{x+h/(1+r)}
 -x\left\{\frac{h}{1+r}-h\right\}
 -\frac12\left\{\frac{h^2}{(1+r)^2}-h^2\right\}
 +o(1)\\
 &=
 \log\left\{1+\frac{hr}{(1+r)x+h}\right\}
 +\frac{zh}{1+r}
 +\frac{h^2r(2+r)}{2(1+r)^2}
 +o(1)\\
 &=zh+o(1)
 \qquad\text{uniformly on }K\times[-H,H].
\end{aligned}
\]
Consequently,
\begin{equation}
 \bar R_{2,r,z}^+(z/r+h)
 \longrightarrow
 \{1-qe^{z^2/2}\}e^{zh}.
 \label{eq:one-middle-secondary-local}
\end{equation}}
{For $c=z/r+h$, uniformly for $z\in K$ and $|h|\leq H$,
we have $c\to\infty$ and $rc=z+rh$.  By uniformity of
\eqref{eq:one-null-sequential} in Lemma~\ref{lem:one-null-sequential},
\[
 \sup_{z\in K}\sup_{|h|\leq H}
 \left|
 \bar R_{0,r,z}^+(z/r+h)-qe^{z^2/2}
 \right|\longrightarrow0.
\]}
Combining this with \eqref{eq:one-middle-secondary-local} and the absence
of the primary non-null contribution for $z\in K$ and
$|h|\le H$ gives
\begin{equation}
 \bar R_{r,z}^+(z/r+h)
 \longrightarrow
 qe^{z^2/2}+\{1-qe^{z^2/2}\}e^{zh},
 \qquad
 \bar R_{0,r,z}^+(z/r+h)\longrightarrow qe^{z^2/2}.
 \label{eq:one-middle-local}
\end{equation}
Because $qe^{z^2/2}<1$ uniformly away from one on $K$, the first limit
crosses one strictly at $h=0$.

We now verify \eqref{eq:one-localized-crossing-left} in
Lemma~\ref{lem:one-localized-crossing}.  For every fixed $\eta>0$, we show
that
\begin{equation}
 \limsup_{r\downarrow0}\sup_{z\in K}
 \sup_{u_q^+\leq c\leq z/r-\eta}\bar R_{r,z}^+(c)<1.
 \label{eq:one-middle-left}
\end{equation}
Suppose instead that this assertion failed.  Then there would be sequences
satisfying
\[
 r_n\downarrow0,
 \qquad z_n\in K,
 \qquad u_q^+\leq c_n\leq\frac {z_n}{r_n}-\eta,
 \qquad \bar R_{r_n,z_n}^+(c_n)\geq1-o(1).
\]
After passing to subsequences,
\[
 z_n\longrightarrow z_0,
 \qquad r_nc_n\longrightarrow x\in[0,z_0].
\]
We consider three cases to get a contradiction.

~\\
\noindent\textbf{Case (a). } If $c_n=O(1)$, then, since $z_n\in K$,
\[
 \Delta_n
 :=\frac{c_n-r_nz_n}{\sqrt{1-r_n^2}}-c_n
 =c_n\left\{\frac{1}{\sqrt{1-r_n^2}}-1\right\}
 -\frac{r_nz_n}{\sqrt{1-r_n^2}}
 =o(1).
\]
Moreover, $\inf_n p_+(c_n)>0$.  Hence continuity of $p_+$,
$\pi_{0,r_n}^+\to1$, and \eqref{eq:one-null-curve} give
\[
 \frac{p_+(c_n+\Delta_n)}{p_+(c_n)}=1+o(1),
 \qquad
 \bar R_{0,r_n,z_n}^+(c_n)
 =q\pi_{0,r_n}^+
 \frac{p_+(c_n+\Delta_n)}{p_+(c_n)}
 =q+o(1).
\]
By \eqref{eq:one-population-curve},
\[
\begin{aligned}
 0
 &\leq \bar R_{r_n,z_n}^+(c_n)-\bar R_{0,r_n,z_n}^+(c_n)\\
 &=\frac{qr_n}{p_+(c_n)}
 \1\{c_{r_n}^++b_{r_n}^+-z_n\geq c_n\}
 +\frac{q\tau_{r_n}^+}{p_+(c_n)}
 \mu_{r_n}^+\!\left(
 \left[\frac{r_n(c_n+z_n)}{1+r_n},y_q^+\right]
 \right)\\
 &\leq\frac{q(r_n+\tau_{r_n}^+)}{p_+(c_n)}
 =O(r_n)=o(1),
\end{aligned}
\]
The equality
$q(r_n+\tau_{r_n}^+)/p_+(c_n)=O(r_n)$ uses
\eqref{eq:one-tau-asymptotic}.  Thus
$\bar R_{r_n,z_n}^+(c_n)=q+o(1)<1$, a contradiction.

~\\
\noindent\textbf{Case (b). } $c_n\to\infty$ and $x<z_0$.  Put
$d_n=(c_n+z_n)/(1+r_n)$.  Then
\[
 d_n-c_n=\frac{z_n-r_nc_n}{1+r_n}\longrightarrow z_0-x>0,
 \qquad c_n(d_n-c_n)\longrightarrow\infty.
\]
By \eqref{eq:one-secondary-bound} in
Lemma~\ref{lem:one-secondary-bound} and \eqref{eq:mills-hazard} in
Lemma~\ref{lem:mills}, the secondary non-null contribution satisfies
\[
 0\leq
 \frac{q\tau_{r_n}^+}{p_+(c_n)}
 \mu_{r_n}^+\!\left(\left[\frac{r_n(c_n+z_n)}{1+r_n},y_q^+\right]\right)
 \leq\frac{p_+(d_n)}{p_+(c_n)}
 =\exp\!\left\{-\int_{c_n}^{d_n}\lambda(t)\,dt\right\}
 \leq e^{-c_n(d_n-c_n)}=o(1).
\]
Equations \eqref{eq:one-primary-bound} and
\eqref{eq:one-null-sequential} in Lemmas~\ref{lem:one-primary-bound}
and~\ref{lem:one-null-sequential} therefore yield
\[
 \bar R_{r_n,z_n}^+(c_n)
 =q\exp\left(xz_0-\frac{x^2}{2}\right)+o(1)
 \leq qe^{z_0^2/2}+o(1)<1,
\]
again a contradiction.

~\\
\noindent\textbf{Case (c). } $c_n\to\infty$ and $x=z_0$.  Write
$h_n=c_n-z_n/r_n\leq-\eta$.  If $h_n$ is bounded,
\eqref{eq:one-middle-local} gives a limit strictly below one.
If $h_n\to-\infty$, then
\[
 d_n-c_n=-\frac{r_nh_n}{1+r_n}>0,
 \qquad c_n(d_n-c_n)\sim-z_0h_n\longrightarrow\infty.
\]
The hazard bound \eqref{eq:mills-hazard} in Lemma~\ref{lem:mills} gives
\[
 \frac{p_+(d_n)}{p_+(c_n)}
 =\exp\!\left\{-\int_{c_n}^{d_n}\lambda(t)\,dt\right\}
 \leq\exp\{-c_n(d_n-c_n)\}
 \longrightarrow0.
\]
Hence \eqref{eq:one-secondary-bound} makes the secondary non-null contribution
$o(1)$, while \eqref{eq:one-primary-bound} makes the primary
non-null contribution $o(1)$.  Since $r_nc_n\to x=z_0$ and $z_n\to z_0$,
\eqref{eq:one-null-sequential} gives
\[
 \bar R_{0,r_n,z_n}^+(c_n)
 \longrightarrow
 q\exp\left(z_0^2-\frac{z_0^2}{2}\right)
 =qe^{z_0^2/2}<1.
\]
Therefore
\[
 \bar R_{r_n,z_n}^+(c_n)
 =\bar R_{0,r_n,z_n}^+(c_n)+o(1)
 \longrightarrow qe^{z_0^2/2}<1,
\]
again a contradiction.

Since all three cases lead to a contradiction, \eqref{eq:one-middle-left}
holds.  Apply Lemma~\ref{lem:one-localized-crossing} with
\[
 m_r(z)=\frac zr,\qquad w_r(z)=1,\qquad
 d(z)=qe^{z^2/2},\qquad \xi(z)=z.
\]
Equations~\eqref{eq:one-middle-local} and
\eqref{eq:one-middle-left} verify
\eqref{eq:one-localized-crossing-full} and
\eqref{eq:one-localized-crossing-left}, respectively.  Therefore
\eqref{eq:one-localized-crossing-cutoff} yields
\eqref{eq:one-middle-cutoff}.

\par\medskip\noindent
\textbf{Proof of \eqref{eq:one-middle-fdp}.}
We apply
Lemma~\ref{lem:one-localized-crossing-regularity}.  Fix $H>0$, put
\[
 c=\frac zr+h,
 \qquad
 \beta_{r,z}(c)=z+\frac{rh}{1+r},
 \qquad |h|\leq H.
\]
Equation~\eqref{eq:one-middle-primary-absent} shows that the primary
non-null contribution is absent uniformly on this set.  Put
$u=(c-rz)/\sqrt{1-r^2}$.  The hazard expansion
\eqref{eq:mills-hazard-expansion} in Lemma~\ref{lem:mills} gives
\[
 \lambda(c)-\frac{\lambda(u)}{\sqrt{1-r^2}}=o(1)
\]
uniformly for $z\in K$ and $|h|\leq H$.  In the secondary log
derivative \eqref{eq:one-secondary-block-log-derivative}, the first term is
$O(r)$, while the same hazard expansion gives
\[
 \lambda(c)-\frac{\lambda\{\beta_{r,z}(c)/r\}}{1+r}
 =z+o(1)
\]
uniformly.  Combining these two estimates with
\eqref{eq:one-middle-secondary-local} yields
\[
 \sup_{z\in K}\sup_{|h|\leq H}
 \left|
 \frac{\partial}{\partial h}\bar R_{r,z}^+(z/r+h)
 -z\{1-qe^{z^2/2}\}e^{zh}
 \right|\longrightarrow0.
\]
Since
\[
 \inf_{z\in K}\inf_{|h|\leq H}
 z\{1-qe^{z^2/2}\}e^{zh}>0,
\]
the derivative is positive on every fixed local window for all sufficiently
small $r$.  Equation~\eqref{eq:one-middle-cutoff} verifies
\eqref{eq:one-localized-crossing-cutoff}, and the second limit in
\eqref{eq:one-middle-local} verifies
\eqref{eq:one-localized-crossing-null}.  Continuity follows from
\eqref{eq:one-null-curve}.
Lemma~\ref{lem:one-localized-crossing-regularity} therefore gives
regularity, and \eqref{eq:one-localized-crossing-fdp} gives
\eqref{eq:one-middle-fdp}, uniformly on $K$.
\end{proof}

\subsubsection{\texorpdfstring{The regime $z>y_q^+$}{The regime z > yq+}}

For $z>y_q^+$, define
\[
\alpha_q^+(z)=z-\sqrt{z^2-(y_q^+)^2}\in(0,z).
\]
\begin{lemma}
\label{lem:one-positive-regime}
For every compact $K\subset(y_q^+,\infty)$, uniformly for $z\in K$,
{\begin{equation}
 rC_r^+(z)\longrightarrow\alpha_q^+(z)
 \label{eq:one-positive-cutoff}
\end{equation}
and
\begin{equation}
 D_r^+(z)\longrightarrow1.
 \label{eq:one-positive-fdp}
\end{equation}}
Moreover, for all sufficiently small $r$, $C_r^+(z)$ is regular for
every $z\in K$.
\end{lemma}

\begin{proof}
\textbf{Proof of \eqref{eq:one-positive-cutoff}.}
Fix a compact $K\subset(y_q^+,\infty)$.  Fix
$z\in K$ and $x\in(0,z)$.  The limits below also hold uniformly when
$(x,z)$ ranges over a compact subset of
$\{(x,z):z\in K,\ 0<x<z\}$.  Then
\eqref{eq:one-scale-properties} in
Lemma~\ref{lem:one-scale-properties} implies that the primary
non-null is not rejected at $c=x/r$.  {For the
secondary non-null contribution, put $d=(x/r+z)/(1+r)$.  Then
\[
 d-\frac xr=\frac{z-x}{1+r}>0,
\]
and \eqref{eq:one-secondary-bound} together with
\eqref{eq:mills-hazard} in Lemma~\ref{lem:mills} gives
\[
 0\leq\bar R_{2,r,z}^+(x/r)
 \leq\frac{p_+(d)}{p_+(x/r)}
 \leq\exp\{- (x/r)(d-x/r)\}\longrightarrow0.
\]}
Equation
\eqref{eq:one-null-sequential} in Lemma~\ref{lem:one-null-sequential},
applied with $c=x/r$, gives
\begin{equation}
 \bar R_{r,z}^+(x/r)\longrightarrow
 q\exp\left(xz-\frac{x^2}{2}\right),
 \label{eq:one-large-local}
\end{equation}
with the same limit for the null contribution.  The equation
\[
 q\exp\left(xz-\frac{x^2}{2}\right)=1
\]
has smaller positive solution $\alpha_q^+(z)$.  The limit in
\eqref{eq:one-large-local} is below one for $x<\alpha_q^+(z)$ and above
one for $\alpha_q^+(z)<x<z$.

We now establish the uniform gap needed to exclude earlier
crossings.  Fix $\eta>0$ uniformly small enough that
\[
 0<\alpha_q^+(z)-\eta<\alpha_q^+(z)+\eta<z,
 \qquad z\in K.
\]
We claim that
\begin{equation}
 \limsup_{r\downarrow0}\sup_{z\in K}
 \sup_{u_q^+\leq c\leq\{\alpha_q^+(z)-\eta\}/r}
 \bar R_{r,z}^+(c)<1.
 \label{eq:one-positive-left}
\end{equation}
If \eqref{eq:one-positive-left} failed, there would be sequences
\[
 r_n\downarrow0,\qquad z_n\in K,\qquad
 u_q^+\leq c_n\leq\frac{\alpha_q^+(z_n)-\eta}{r_n},
 \qquad
 \bar R_{r_n,z_n}^+(c_n)\geq1-o(1).
\]
After taking a subsequence,
\[
 z_n\longrightarrow z_0\in K,
 \qquad
 r_nc_n\longrightarrow x\in[0,\alpha_q^+(z_0)-\eta].
\]
If $(c_n)$ is bounded, then $p_+(c_n)$ is bounded away from zero,
\eqref{eq:one-null-curve} gives
$\bar R_{0,r_n,z_n}^+(c_n)=q+o(1)$, and
\eqref{eq:one-population-curve} and \eqref{eq:one-tau-asymptotic} give
\[
 0\leq
 \bar R_{r_n,z_n}^+(c_n)-\bar R_{0,r_n,z_n}^+(c_n)
 \leq\frac{q(r_n+\tau_{r_n}^+)}{p_+(c_n)}=o(1).
\]
Thus $\bar R_{r_n,z_n}^+(c_n)\to q<1$, a contradiction.

Suppose instead that $c_n\to\infty$, and define
$d_n=(c_n+z_n)/(1+r_n)$.  Since
\[
 d_n-c_n=\frac{z_n-r_nc_n}{1+r_n}
 \longrightarrow z_0-x
 \geq z_0-\alpha_q^+(z_0)+\eta>0,
\]
\eqref{eq:one-secondary-bound} in
Lemma~\ref{lem:one-secondary-bound} and \eqref{eq:mills-hazard} in
Lemma~\ref{lem:mills} give
\[
 0\leq\bar R_{2,r_n,z_n}^+(c_n)
 \leq\exp\{-c_n(d_n-c_n)\}=o(1).
\]
Equation~\eqref{eq:one-primary-bound} in
Lemma~\ref{lem:one-primary-bound} gives
$\bar R_{1,r_n,z_n}^+(c_n)=o(1)$, and
\eqref{eq:one-null-sequential} in
Lemma~\ref{lem:one-null-sequential} gives
\[
 \bar R_{r_n,z_n}^+(c_n)
 \longrightarrow q\exp\left(xz_0-\frac{x^2}{2}\right)
 \leq q\exp\left(
   \{\alpha_q^+(z_0)-\eta\}z_0
   -\frac{\{\alpha_q^+(z_0)-\eta\}^2}{2}
 \right)<1,
\]
where the inequality uses
$x\leq\alpha_q^+(z_0)-\eta<z_0$.  This is again a contradiction, so
\eqref{eq:one-positive-left} holds.  In particular, no crossing occurs at
or before $\{\alpha_q^+(z)-\eta\}/r$.  At
$c=\{\alpha_q^+(z)+\eta\}/r$, the null contribution alone is larger
than one for all sufficiently small $r$, uniformly on $K$.  Therefore
\[
 \alpha_q^+(z)-\eta<rC_r^+(z)<\alpha_q^+(z)+\eta.
\]
Letting $\eta\downarrow0$ proves
\[
 rC_r^+(z)\longrightarrow\alpha_q^+(z)
\]
uniformly on $K$.

\par\medskip\noindent
\textbf{Proof of \eqref{eq:one-positive-fdp}.}
It remains to prove regularity.  Choose $\eta>0$ such that, for every
$z\in K$,
\[
 0<\alpha_q^+(z)-2\eta<\alpha_q^+(z)+2\eta
 <\min\{z,y_q^+\}.
\]
For any
$x\in[\alpha_q^+(z)-\eta,\alpha_q^+(z)+\eta]$, uniformly over $z\in K$,
\[
 r\{x/r-(c_r^++b_r^+-z)\}
 =x-rc_r^+-rb_r^++rz>0
\]
by \eqref{eq:one-scale-properties} in
Lemma~\ref{lem:one-scale-properties}, so the primary non-null
contribution is zero.
{
Applying \eqref{eq:mills-hazard-expansion} in Lemma~\ref{lem:mills}
directly to \eqref{eq:one-null-block-log-derivative} in
Lemma~\ref{lem:one-block-derivatives} gives, uniformly for $z\in K$ and
$x\in[\alpha_q^+(z)-\eta,\alpha_q^+(z)+\eta]$,
\begin{equation}
 \left.\frac{\dd}{\dd c}\log\bar R_{0,r,z}^+(c)\right|_{c=x/r}
 =r(z-x)+o(r).
 \label{eq:one-positive-null-log-derivative}
\end{equation}
Set
\[
 c_1=\inf_{z\in K}\alpha_q^+(z)-\eta>0,
 \qquad
 \delta=\frac12\left\{\inf_{z\in K}
 [z-\alpha_q^+(z)]-\eta\right\}>0.
\]
The null limit \eqref{eq:one-null-sequential} in
Lemma~\ref{lem:one-null-sequential} and
\eqref{eq:one-positive-null-log-derivative} imply that, for
some $c_0>0$,
\begin{equation}
\begin{aligned}
 \inf_{z\in K}\inf_{x\in[\alpha_q^+(z)-\eta,\alpha_q^+(z)+\eta]}
 \bar R_{0,r,z}^+(x/r)&\geq c_0,\\
 \inf_{z\in K}\inf_{x\in[\alpha_q^+(z)-\eta,\alpha_q^+(z)+\eta]}
 \left.\frac{\dd}{\dd c}\bar R_{0,r,z}^+(c)\right|_{c=x/r}
 &\geq c_0\delta r.
\end{aligned}
 \label{eq:one-positive-null-derivative}
\end{equation}
for all sufficiently small $r$.
{
For the secondary non-null contribution, put
$d=(x/r+z)/(1+r)$.  Here $rd\in(b_r^+,y_q^+)$,
$x/r\geq c_1/r$, and $d-x/r\geq\delta$.
Thus \eqref{eq:one-secondary-block-log-derivative} in
Lemma~\ref{lem:one-block-derivatives} and \eqref{eq:mills-hazard} in
Lemma~\ref{lem:mills} yield
\[
\begin{aligned}
 0\leq\bar R_{2,r,z}^+(x/r)
 &\leq\frac{p_+(d)}{p_+(x/r)}
 \leq e^{-(x/r)(d-x/r)}\leq e^{-c_1\delta/r},\\
 \left|\left.\frac{\dd}{\dd c}\bar R_{2,r,z}^+(c)\right|_{c=x/r}\right|
 &=O(r^{-1}e^{-c_1\delta/r})=o(r).
\end{aligned}
\]}
Combining this bound with \eqref{eq:one-positive-null-derivative},
\[
 \inf_{z\in K}\inf_{x\in[\alpha_q^+(z)-\eta,\alpha_q^+(z)+\eta]}
 \left.\frac{\dd}{\dd c}\bar R_{r,z}^+(c)\right|_{c=x/r}>0.
\]
{
Equation~\eqref{eq:one-positive-cutoff} gives
\[
 \frac{\alpha_q^+(z)-\eta}{r}
 <C_r^+(z)<
 \frac{\alpha_q^+(z)+\eta}{r}
\]
for all sufficiently small $r$, uniformly for $z\in K$.}  Hence
Proposition~\ref{prop:local-regularity} proves regularity uniformly on
$K$.

At the population cutoff, regularity gives
$\bar R_{r,z}^+\{C_r^+(z)\}=1$.  By
\eqref{eq:one-positive-cutoff}, uniformly for $z\in K$,
\[
 rC_r^+(z)\longrightarrow\alpha_q^+(z),
 \qquad
 \inf_{z\in K}\alpha_q^+(z)>0.
\]
In contrast, \eqref{eq:one-scale-properties} in
Lemma~\ref{lem:one-scale-properties} gives
\[
 r(c_r^++b_r^+-z)=rc_r^++rb_r^+-rz\longrightarrow0
\]
uniformly on $K$.  Hence
$C_r^+(z)>c_r^++b_r^+-z$ for all sufficiently small $r$, and the
indicator in \eqref{eq:one-primary-curve} is zero.  Thus the primary
non-null contribution vanishes at $C_r^+(z)$.  With
$d=\{C_r^+(z)+z\}/(1+r)$,
\eqref{eq:one-positive-cutoff} gives
\[
 C_r^+(z)\longrightarrow\infty,
 \qquad
 d-C_r^+(z)=\frac{z-rC_r^+(z)}{1+r}
 \longrightarrow z-\alpha_q^+(z)>0
\]
uniformly on $K$.  Hence Lemma~\ref{lem:one-secondary-bound} and
\eqref{eq:mills-hazard} in Lemma~\ref{lem:mills} give
\[
 0\leq\bar R_{2,r,z}^+\{C_r^+(z)\}
 \leq \exp[-C_r^+(z)\{d-C_r^+(z)\}]\longrightarrow0.
\]
It follows that
$\bar R_{0,r,z}^+\{C_r^+(z)\}\to1$.  By the definition of
$D_r^+(z)$, uniformly on $K$,
\[
 D_r^+(z)=\bar R_{0,r,z}^+\{C_r^+(z)\}\longrightarrow1.
\]
}
\end{proof}

\subsection{Proofs of Theorem~\ref{thm:one-lower} and
Propositions~\ref{prop:one-expansion} and~\ref{prop:one-strict}}

\begin{proof}[Proof of Theorem~\ref{thm:one-lower}]
Choose a compact set
\[
 E\subset\mathbb R\setminus\{0,y_q^+\}
\]
such that
\[
 \mathbb E\{D_+^*(Z)\1\{Z\in E\}\}>\ell_{\le}(q)-\frac\delta4.
\]
The proofs of Lemmas~\ref{lem:one-negative-regime},
\ref{lem:one-middle-regime}, and \ref{lem:one-positive-regime} give, for all
sufficiently small $r$, brackets
\[
 A_r(z)<B_r(z),\qquad z\in E,
\]
and a constant $\gamma>0$ such that
\[
 \sup_{z\in E}\sup_{u_q^+\leq c\leq A_r(z)}
 \bar R_{r,z}^+(c)\leq1-\gamma,
 \qquad
 \inf_{z\in E}\bar R_{r,z}^+\{B_r(z)\}\geq1+\gamma,
\]
\[
 \sup_{z\in E}\sup_{A_r(z)\leq c\leq B_r(z)}
 \left|\bar R_{0,r,z}^+(c)-D_+^*(z)\right|
 \leq\frac{\delta}{8}.
\]
Fix such an $r$, and put $C_*=\sup_{z\in E}B_r(z)<\infty$.  For
$z\in E$, define
\[
 \mathcal E_N(z)=
 \max\left\{
 \|\widehat R_N-R_{r,z}^+\|_{\infty,[0,1]},\,
 \|\widehat R_{0,N}-\pi_{0,r}^+R_{0,r,z}^+
 \|_{\infty,[0,1]}
 \right\}
\]
and
\[
 t_*=\frac{p_+(C_*)}{2q}
 \min\left\{\gamma,\frac{\delta}{8}\right\}.
\]
Following the same argument in the proof of
Theorem~\ref{thm:population-transfer}, Lemma~\ref{lem:DKW} gives
\[
 \sup_{z\in E}
 \mathbb P\{\mathcal E_N(z)>t_*\mid Z=z\}
 \leq4e^{-2Nt_*^2}.
\]
On the complementary event, the empirical and population curves differ
by at most
$q\mathcal E_N(z)/p_+(C_*)\leq
\frac12\min\{\gamma,\delta/8\}$ throughout
$[u_q^+,C_*]$.  The two population brackets and
Lemma~\ref{lem:exact-BH} therefore imply
\[
 A_r(z)<\widehat C_N\leq B_r(z),
 \qquad
 \FDP\geq D_+^*(z)-\frac{\delta}{4}.
\]
Consequently,
\begin{align*}
 \mathbb E_{\Omega_N}\{\FDR_{\Omega_N}(\BH_q)\}
 &=\mathbb E_{\Omega_N,Z,\varepsilon}(\FDP)\\
 &\geq
 \int_E\left\{D_+^*(z)-\frac{\delta}{4}\right\}\phi(z)\,\dd z
 -4e^{-2Nt_*^2}\\
 &>\ell_{\le}(q)-\frac{\delta}{2}-4e^{-2Nt_*^2}.
\end{align*}
For all sufficiently large $N$, this gives
\[
 \mathbb E_{\Omega_N}\{\FDR_{\Omega_N}(\BH_q)\}
 >\ell_{\le}(q)-\frac{3\delta}{4}.
\]
Therefore some deterministic realization $\omega$ satisfies the same
inequality.  The one-sided analogue of Lemma~\ref{lem:eta} permits an
$\eta>0$ for which the perturbed model has a positive definite correlation
matrix and
\[
 \FDR_\omega^{(\eta)}(\BH_q)>\ell_{\le}(q)-\delta.
\]
All means and null labels are unchanged by the perturbation.
Table~\ref{tab:one-construction} gives the pre-perturbation sign
pattern, and \eqref{eq:eta-cov} shows that every off-diagonal covariance is
multiplied by the positive factor $1-\eta^2$.  Thus the perturbation
preserves that sign pattern.
\end{proof}

\begin{proof}[Proof of Proposition~\ref{prop:one-expansion}]
Since $e^{-(y_q^+)^2/2}=q$, the Mills expansion in
Lemma~\ref{lem:mills} gives
\[
 \Phib(y_q^+)\sim\frac{q}{\sqrt{2\pi}\,y_q^+}=o(q).
\]
Substitute $y_q^+=\sqrt{2\log(1/q)}$ into \eqref{eq:one-ell}.
\end{proof}

\begin{proof}[Proof of Proposition~\ref{prop:one-strict}]
By \eqref{eq:one-Dstar}, $D_+^*(z)=q$ for $z\leq0$ and
$D_+^*(z)>q$ for every $z>0$.  Hence
$\ell_{\le}(q)=\mathbb E\{D_+^*(Z)\}>q$.
\end{proof}
\endgroup

\section{\texorpdfstring{Upper bounds}{Upper bounds}}
\label{sec:upper-bound}

\subsection{Preliminaries}

The upper bounds concern the common-factor Gaussian model
\begin{equation}
 T_i=\theta_i+a_iZ+\sqrt{1-a_i^2}\,\varepsilon_i,
 \quad 1\leq i\leq m,
 \label{eq:common-factor-model}
\end{equation}
where $Z,\varepsilon_1,\ldots,\varepsilon_m$ are i.i.d. standard
normal random variables and $|a_i|\leq1$.  Its covariance matrix is
diagonal plus rank one.  Conditional on $Z$, the coordinates and their
corresponding $p$-values are independent.

The following conditional leave-one-out bound will be used for
both types of tests.  Let $P_1,\ldots,P_m$ be conditionally independent
given $Z$, let $\mathcal H_0$ denote the true-null indices, and apply BH
at level $q$.  For $i\in\mathcal H_0$, write
$F_{i,z}(t)=\mathbb P(P_i\leq t\mid Z=z)$.
\begin{lemma}
\label{lem:conditional-fdp-bound}
For almost every $z$,
\begin{equation}
 \mathbb E(\FDP\mid Z=z)
 \leq\frac qm\sum_{i\in\mathcal H_0}
       \sup_{0<t\leq q}\frac{F_{i,z}(t)}t
 \label{eq:conditional-fdp-bound}
\end{equation}
\end{lemma}

\begin{proof}
Let $R$ be the BH rejection count.  For
$i\in\mathcal H_0$, let $R_i$ be the rejection count after replacing
$P_i$ by zero; in particular, $R_i\geq1$.  The standard leave-one-out
argument \citep{BenjaminiYekutieli2001} starts from the pointwise identity
\[
 \frac{\1\{i\text{ is rejected}\}}{R\vee1}
 =\frac{\1\{P_i\leq qR_i/m\}}{R_i}.
\]
In fact, if $i$ is rejected, replacing $P_i$ by any value below, including
zero, does not change other rejections because of the step-up rejection rule
for BH.  Taking conditional expectations given $Z=z$
and summing gives, for almost every $z$,

\begin{equation}
 \mathbb E(\FDP\mid Z=z)
 =\sum_{i\in\mathcal H_0}
   \mathbb E\left[
   \left.
   \frac{\1\{P_i\leq qR_i/m\}}{R_i}
   \right|Z=z\right].
 \label{eq:loo-identity}
\end{equation}


Conditional independence implies that $P_i$ and $R_i$ are independent
given $Z=z$.  Since $0<qR_i/m\leq q$, conditioning gives, for every
$i\in\mathcal H_0$ and almost every $z$,
\begin{equation}
\begin{aligned}
 \mathbb E\left[
   \left.
   \frac{\1\{P_i\leq qR_i/m\}}{R_i}
   \right| Z=z\right]
 &=\frac qm\,
   \mathbb E\left[
   \left.
   \frac{F_{i,z}(qR_i/m)}{qR_i/m}
   \right| Z=z\right]\\
 &\leq\frac qm\sup_{0<t\leq q}\frac{F_{i,z}(t)}t .
\end{aligned}
 \label{eq:conditional-loo-term-bound}
\end{equation}
Summing \eqref{eq:conditional-loo-term-bound} over
$i\in\mathcal H_0$ proves
\eqref{eq:conditional-fdp-bound}.
\end{proof}

\subsection{Upper bound for two-sided tests}

The common-factor class \eqref{eq:common-factor-model} contains the
lower-bound construction in Subsection~\ref{sec:continuum-design}.  The
following theorem shows that this construction attains the sharp leading
constant as $q\downarrow0$.  All constants below are universal and all
asymptotic statements are uniform over the common-factor model.

\begin{theorem}\label{thm:common-factor-upper}
For ordinary BH applied to the two-sided $p$-values $P_i=p(|T_i|)$,
let $\mathcal H_0=\{i:\theta_i=0\}$, $m_0=|\mathcal H_0|$, and
$\pi_0=m_0/m$.
Throughout $0<q\leq2\Phib(1)$, let $u_q$ be defined by
$p(u_q)=2\Phib(u_q)=q$.  If $m_0=0$, then $\FDR(\BH_q)=0$.  If
$m_0>0$, then the following bounds hold uniformly over the common-factor
model.
\begin{enumerate}[label=(\alph*)]
\item
\[
 \FDR(\BH_q)
 \leq q\left\{1+\pi_0\left(\frac{1-q}{2}
                    +\frac{u_q}{\sqrt{2\pi}}\right)\right\}.
\]
\item There is a universal constant $C<\infty$ such that
\[
 \FDR(\BH_q)
 \leq q\left[1+\frac{\pi_0}{2\sqrt\pi}\sqrt{\log(1/q)}
       +C\pi_0\{\log(1/q)\}^{1/4}\right].
\]
\end{enumerate}
\end{theorem}

\subsubsection{Proof of Theorem~\ref{thm:common-factor-upper}~(a)}

\begin{proof}
If $m_0=0$, then $V=0$ identically and hence $\FDR=0$.  Assume
henceforth that $m_0\geq1$.
Conditional on $Z=z$, each $P_i$ is a function of $\varepsilon_i$
alone, or is deterministic when $|a_i|=1$.  Thus the $p$-values are
conditionally independent, and Lemma~\ref{lem:conditional-fdp-bound} gives
\eqref{eq:conditional-fdp-bound}.

To average \eqref{eq:conditional-fdp-bound} over $Z$, it remains to control
{\[
 \int_{-u_q}^{u_q}
 \phi(z)\sup_{0<t\leq q}\frac{F_{i,z}(t)}t\dd z
\]}
for each true null $i$.  We do this on $|z|\leq u_q$; the event
$|Z|>u_q$ is handled at the end by $\FDP\leq1$.
Fix a true null index $i$.  Put $r=|a_i|$ and
$s=\sqrt{1-r^2}$, and first suppose $s>0$.  Conditional on $Z=z$,
$T_i\sim N(a_i z,s^2)$.  The inequality
$t=p(u)=2\Phib(u)\leq q$ holds if and only if $u\geq u_q$, and in this
case
{\[
 F_{i,z}(p(u))
 =\int_u^\infty s^{-1}\phi\{(x-a_i z)/s\}\dd x
  +\int_u^\infty s^{-1}\phi\{(x+a_i z)/s\}\dd x .
\]}
Since $s^2=1-a_i^2$,
{\[
\begin{aligned}
 \frac{s^{-1}\phi\{(x-a_i z)/s\}}{\phi(x)}
 &=\frac1s
   \exp\left\{-\frac{(x-a_i z)^2}{2s^2}+\frac{x^2}{2}\right\}\\
 &=\frac1s
   \exp\left\{\frac{z^2}{2}
        -\frac{(a_i x-z)^2}{2s^2}\right\}.
\end{aligned}
\]
The second tail is the same calculation with $z$ replaced by $-z$.  Choose
$\eta_+,\eta_-\in\{-1,1\}$ with $\{\eta_+,\eta_-\}=\{-1,1\}$
so that $\eta_+a_i z\geq0$ and
$\eta_-a_i z\leq0$.  For $x\geq u$,
\[
 |a_i x-\eta_+z|\geq (ru-|z|)_+,\qquad
 |a_i x-\eta_-z|\geq ru+|z|.
\]
Both right-hand sides are nondecreasing in $u$, so for $u\geq u_q$,
\[
\begin{aligned}
 \phi(z)\frac{F_{i,z}(p(u))}{p(u)}
 &\leq
 \frac{\phi(z)}{p(u)}\frac{e^{z^2/2}}s
 \left[
 e^{-(r u_q-|z|)_+^2/(2s^2)}
 +e^{-(r u_q+|z|)^2/(2s^2)}
 \right]\int_u^\infty\phi(x)\dd x\\
 &=\frac1{2s\sqrt{2\pi}}
 \left[
 e^{-(r u_q-|z|)_+^2/(2s^2)}
 +e^{-(r u_q+|z|)^2/(2s^2)}
 \right],
\end{aligned}
\]}
because $\int_u^\infty\phi(x)\dd x=p(u)/2$.  Taking the supremum gives
\begin{equation}
 \phi(z)\sup_{0<t\leq q}\frac{F_{i,z}(t)}t
 \leq\frac1{2s\sqrt{2\pi}}
 \left[
 e^{-(r u_q-|z|)_+^2/(2s^2)}+e^{-(r u_q+|z|)^2/(2s^2)}
 \right].                                                    \label{eq:conditional-tail-ratio-bound}
\end{equation}
Integrating \eqref{eq:conditional-tail-ratio-bound} over $|z|\leq u_q$ and using symmetry gives
{
\begin{equation}
\begin{aligned}
 \int_{-u_q}^{u_q}\phi(z)
     \sup_{0<t\leq q}\frac{F_{i,z}(t)}t\dd z
 &\leq\frac1{s\sqrt{2\pi}}
 \left\{\int_0^{u_q}e^{-(r u_q-z)_+^2/(2s^2)}\dd z
       +\int_0^{u_q}e^{-(r u_q+z)^2/(2s^2)}\dd z\right\}.
\end{aligned}
\label{eq:integrated-tail-ratio-decomposition}
\end{equation}}
{The two integrals on the right-hand side of
\eqref{eq:integrated-tail-ratio-decomposition} are
\[
\begin{aligned}
 \int_0^{u_q}e^{-(r u_q-z)_+^2/(2s^2)}\dd z
 &=\int_0^{r u_q}e^{-y^2/(2s^2)}\dd y+(1-r)u_q,\\
 \int_0^{u_q}e^{-(r u_q+z)^2/(2s^2)}\dd z
 &=\int_{r u_q}^{(1+r)u_q}e^{-y^2/(2s^2)}\dd y.
\end{aligned}
\]}
Consequently, writing
$\gamma_r=\sqrt{(1-r)/(1+r)}\in(0,1]$,
{\begin{equation}
\begin{aligned}
 \int_{-u_q}^{u_q}\phi(z)
     \sup_{0<t\leq q}\frac{F_{i,z}(t)}t\dd z
 &\leq\frac1{s\sqrt{2\pi}}
 \left\{\int_0^{(1+r)u_q}e^{-y^2/(2s^2)}\dd y+(1-r)u_q\right\}\\
 &=\left\{\Phi\left(\frac{(1+r)u_q}{s}\right)-\frac12\right\}
   +\frac{(1-r)u_q}{s\sqrt{2\pi}}\\
 &=\Phi(u_q/\gamma_r)-\frac12+\frac{u_q\gamma_r}{\sqrt{2\pi}},
\end{aligned}
\label{eq:integrated-tail-ratio-bound}
\end{equation}}
where the final equality in
\eqref{eq:integrated-tail-ratio-bound} uses
$s^2=1-r^2=(1-r)(1+r)$, so
$(1+r)/s=1/\gamma_r$ and $(1-r)/s=\gamma_r$.
The right-hand side of
\eqref{eq:integrated-tail-ratio-bound} is increasing in
$\gamma_r\in(0,1]$.  Its derivative with respect to $\gamma_r$ is
\[
 \frac{u_q}{\sqrt{2\pi}}
 \left[1-\gamma_r^{-2}\exp\{-u_q^2/(2\gamma_r^2)\}\right]\geq0,
\]
because $u_q\geq1$ and, on putting $w=\gamma_r^{-2}\geq1$,
\[
 w e^{-u_q^2w/2}\leq w e^{-w/2}\leq 2/e<1.
\]
Hence \eqref{eq:integrated-tail-ratio-bound} is at most
\begin{equation}
 \Phi(u_q)-\frac12+\frac{u_q}{\sqrt{2\pi}}
 =\frac{1-q}{2}+\frac{u_q}{\sqrt{2\pi}}.                       \label{eq:integrated-tail-ratio-uniform}
\end{equation}
When $r=1$, the conditional $p$-value is deterministic.  For
$|z|<u_q$, it exceeds $q$, and the boundary $|z|=u_q$ has Lebesgue
measure zero; hence \eqref{eq:integrated-tail-ratio-uniform} remains valid.
When $r=0$, the conditional null $p$-value is uniform and independent of
$Z$; \eqref{eq:integrated-tail-ratio-uniform} remains valid, although it is
not sharp.

Let $A=\{|Z|\leq u_q\}$.  Decomposing over $A$ and $A^c$,
{\[
 \FDR=\mathbb E(\FDP\1_A)
      +\mathbb E(\FDP\1_{A^c}).
\]}
For the first term, integrate \eqref{eq:conditional-fdp-bound} over $z\in[-u_q,u_q]$ and
use \eqref{eq:integrated-tail-ratio-uniform}.  For the second term, no conditional tail bound is
needed: since $0\leq\FDP\leq1$,
{
\begin{equation}
 \mathbb E(\FDP\1_{A^c})
 \leq\mathbb P(A^c)
 =\mathbb P(|Z|>u_q)
 =2\Phib(u_q)
 =q.
\label{eq:outer-factor-fdp-bound}
\end{equation}}
Combining \eqref{eq:conditional-fdp-bound},
\eqref{eq:integrated-tail-ratio-uniform}, and
\eqref{eq:outer-factor-fdp-bound} yields
\[
 \FDR
 \leq q+\frac qm\sum_{i\in\mathcal H_0}
       \left(\frac{1-q}{2}+\frac{u_q}{\sqrt{2\pi}}\right)
 =q\left\{1+\pi_0\left(\frac{1-q}{2}
       +\frac{u_q}{\sqrt{2\pi}}\right)\right\},
\]
as claimed.
\end{proof}

\subsubsection{Proof of Theorem~\ref{thm:common-factor-upper}~(b)}

The proof of part (b) has two parts.  First we prove a deterministic statement
for the rank-weighted contribution that will arise from the finite BH threshold.
We then verify its hypotheses from the finite threshold by a uniform
concentration argument for Poisson-binomial counts, that is, sums of
independent Bernoulli random variables with possibly different success
probabilities.
Throughout the proof, $C$ and $c$ denote positive universal constants
whose values may change from line to line.

For $0\leq r<1$, define
\begin{equation}
 \rho_r(u,z)=
 \frac{\Phib\{(u-rz)/\sqrt{1-r^2}\}
       +\Phib\{(u+rz)/\sqrt{1-r^2}\}}
      {2\Phib(u)}.                                   \label{eq:upper-rho}
\end{equation}
For $r=1$, set $\rho_1(u,z)=\mathbf1\{|z|\geq u\}/p(u)$; the convention
on the measure-zero boundary $|z|=u$ is immaterial.
For every true null $i$, this is its conditional two-sided tail ratio:
\begin{equation}
 \frac{F_{i,z}\{p(u)\}}{p(u)}=\rho_{|a_i|}(u,z),       \label{eq:upper-null-tail-ratio}
\end{equation}
because the two Gaussian tails are unchanged when $a_i$ is replaced by
$|a_i|$.
Integrating \eqref{eq:upper-null-tail-ratio} over the common factor gives
the unconditional normalization: for every true null $i$ and every
$u>0$,
\begin{equation}
 \int_{\mathbb R}\rho_{|a_i|}(u,z)\phi(z)\dd z
 =\frac{1}{p(u)}
   \int_{\mathbb R}F_{i,z}\{p(u)\}\phi(z)\dd z
 =\frac{\mathbb P(P_i\leq p(u))}{p(u)}
 =1.                                                \label{eq:upper-rho-normalization}
\end{equation}
The middle equality follows because
\[
 F_{i,z}\{p(u)\}
 =\mathbb P(P_i\leq p(u)\mid Z=z),
\]
and $Z$ has density $\phi$.  Hence
\[
 \int_{\mathbb R}F_{i,z}\{p(u)\}\phi(z)\dd z
 =\mathbb E\{\mathbb P(P_i\leq p(u)\mid Z)\}
 =\mathbb P(P_i\leq p(u)),
\]
which is the tower property.  The last equality in
\eqref{eq:upper-rho-normalization} uses that $P_i$ is a two-sided null
$p$-value.

We first give a useful bound on $\rho_r(u,z)$ without restrictions on $r$.
\begin{lemma}\label{lem:upper-null-ratio}
If $u_q\geq1$ and $0\leq r<1$, then
\begin{equation*}
 \int_{-u_q}^{u_q}\phi(z)
       \sup_{u\geq u_q}\rho_r(u,z)\dd z
 \leq
 \Phi\left(\frac{(1+r)u_q}{\sqrt{1-r^2}}\right)-\frac12
       +\frac{(1-r)u_q}{\sqrt{1-r^2}\sqrt{2\pi}}.
\end{equation*}
For $r=1$, the integral on the left is zero.
\end{lemma}

\begin{proof}
Assume first that $0\leq r<1$.  For $\xi\in\{-1,1\}$, using
$\phi(t)=(2\pi)^{-1/2}\exp(-t^2/2)$,
\begin{align*}
 \frac{\phi\{(x-\xi rz)/\sqrt{1-r^2}\}}
      {\sqrt{1-r^2}\,\phi(x)}
 &=\frac1{\sqrt{1-r^2}}
   \exp\left\{-\frac{(x-\xi rz)^2}{2(1-r^2)}
              +\frac{x^2}{2}\right\}\\
 &=\frac1{\sqrt{1-r^2}}\exp\left\{\frac{z^2}{2}
            -\frac{(rx-\xi z)^2}{2(1-r^2)}\right\}.
\end{align*}
The second equality uses the identity
\[
 (1-r^2)z^2-(rx-\xi z)^2
 =(1-r^2)x^2-(x-\xi rz)^2
 =-r^2x^2+2\xi rxz-r^2z^2.
\]
If $\xi z=|z|$, then
\[
 |rx-\xi z|=|rx-|z||\geq (rx-|z|)_+
       \geq (r u_q-|z|)_+,
\]
while if $\xi z=-|z|$, then
\[
 |rx-\xi z|=rx+|z|\geq r u_q+|z|.
\]
For fixed $u\geq u_q$, each conditional tail in the numerator of
$\rho_r(u,z)$ can be written as
\[
 \Phib\{(u-\xi rz)/\sqrt{1-r^2}\}
 =\int_u^\infty
   \frac{\phi\{(x-\xi rz)/\sqrt{1-r^2}\}}{\sqrt{1-r^2}}\dd x .
\]
Multiplying the density-ratio identity above by $\phi(z)$ and using the two
lower bounds on $|rx-\xi z|$, we get, for $|z|\leq u_q$,
\begin{align*}
 \phi(z)\rho_r(u,z)
&=\frac1{p(u)}
  \sum_{\xi\in\{-1,1\}}\int_u^\infty
   \phi(x)\phi(z)
   \frac{\phi\{(x-\xi rz)/\sqrt{1-r^2}\}}
        {\sqrt{1-r^2}\,\phi(x)}\dd x\\
&\leq
 \frac{\int_u^\infty\phi(x)\dd x}{p(u)}
 \frac1{\sqrt{1-r^2}\sqrt{2\pi}}
 \left[
 e^{-(r u_q-|z|)_+^2/\{2(1-r^2)\}}
 +e^{-(r u_q+|z|)^2/\{2(1-r^2)\}}
 \right].
\end{align*}
Since $p(u)=2\int_u^\infty\phi(x)\dd x$, and the right side no longer
depends on $u$, taking the supremum over $u\geq u_q$ gives
\[
 \phi(z)\sup_{u\geq u_q}\rho_r(u,z)
 \leq\frac1{2\sqrt{1-r^2}\sqrt{2\pi}}
 \left[
 e^{-(r u_q-|z|)_+^2/\{2(1-r^2)\}}
 +e^{-(r u_q+|z|)^2/\{2(1-r^2)\}}
 \right].
\]
Integrating this bound over $z\in[-u_q,u_q]$ and using symmetry reduces the
right side to the integral over $0\leq z\leq u_q$ without the factor $1/2$.
The first exponential contributes
\begin{align*}
 \int_0^{u_q}e^{-(r u_q-z)_+^2/\{2(1-r^2)\}}\dd z
 &=\int_0^{r u_q}e^{-(r u_q-z)^2/\{2(1-r^2)\}}\dd z
   +\int_{r u_q}^{u_q}1\,\dd z\\
 &=\int_0^{r u_q}e^{-y^2/\{2(1-r^2)\}}\dd y+(1-r)u_q,
\end{align*}
where the last line uses $y=r u_q-z$ in the first integral.  The second exponential
contributes
\[
 \int_0^{u_q}e^{-(r u_q+z)^2/\{2(1-r^2)\}}\dd z
 =\int_{r u_q}^{(1+r)u_q}e^{-y^2/\{2(1-r^2)\}}\dd y,
\]
using $y=r u_q+z$.  Therefore
\begin{align*}
&\int_{-u_q}^{u_q}\phi(z)
       \sup_{u\geq u_q}\rho_r(u,z)\dd z
\\
&\leq \frac1{\sqrt{1-r^2}\sqrt{2\pi}}
 \bigg\{\int_0^{r u_q}e^{-y^2/\{2(1-r^2)\}}\dd y
       +\int_{r u_q}^{(1+r)u_q}e^{-y^2/\{2(1-r^2)\}}\dd y+(1-r)u_q\bigg\}\\
&=\Phi\{(1+r)u_q/\sqrt{1-r^2}\}-\frac12
       +\frac{(1-r)u_q}{\sqrt{1-r^2}\sqrt{2\pi}},
\end{align*}
which is the asserted bound.

When $r=1$, the conditional residual variance $1-r^2$ is zero.  Thus a
null statistic with $|a_i|=1$ is $T_i=a_iZ$, so conditional on $Z=z$
it equals $\pm z$ and has absolute value $|z|$.  For $|z|\leq u_q$,
\begin{equation}
 \{u\geq u_q:|z|\geq u\}
 =\begin{cases}
 \varnothing,&|z|<u_q,\\
 \{u_q\},&|z|=u_q.
 \end{cases}
 \label{eq:upper-degenerate-threshold-set}
\end{equation}
By \eqref{eq:upper-degenerate-threshold-set} and $p(u_q)=q$,
\begin{align}
 \sup_{u\geq u_q}\rho_1(u,z)
 &=\frac{\mathbf1\{|z|=u_q\}}q,
 \qquad |z|\leq u_q,\label{eq:upper-degenerate-ratio-sup}\\
 \int_{-u_q}^{u_q}\phi(z)\sup_{u\geq u_q}\rho_1(u,z)\dd z
 &=\frac1q\int_{\{-u_q,u_q\}}\phi(z)\dd z=0.
 \label{eq:upper-degenerate-ratio-integral}
\end{align}
Changing the convention at $|z|=u$ affects
\eqref{eq:upper-degenerate-ratio-sup} only at $z=\pm u_q$, so
\eqref{eq:upper-degenerate-ratio-integral} is unchanged.

\end{proof}

Define
\begin{equation}
 K_q=\sqrt{8\log u_q},\qquad L_q=K_q+\sqrt{u_q}.
\label{eq:upper-KLq-def}
\end{equation}
The following lemma shows a refined bound on $\rho_r(u, z)$ for small $r$.
\begin{lemma}\label{lem:upper-localization}
With $K_q$ and $L_q$ as defined in \eqref{eq:upper-KLq-def}, uniformly for
$0\leq r\leq3/5$, $u\geq u_q$, and $|z|\leq u_q$,
\begin{equation}
 \phi(z)\rho_r(u,z)
 \leq C\left[
 e^{-(z-ru)^2/\{2(1-r^2)\}}
 +e^{-(z+ru)^2/\{2(1-r^2)\}}\right].   \label{eq:upper-localization}
\end{equation}
Moreover, there are universal constants $C<\infty$ and $q_0>0$ such that,
whenever $q\leq q_0$, if
$|z|\geq L_q$ and
$\big||z|-ru\big|\leq K_q$, then
\begin{equation}
 \phi(z)\rho_r(u,z)
 \leq \frac{1+C(K_q+1)/u_q}{2\sqrt{2\pi}\sqrt{1-r^2}}
       +C\exp\{-u_q\}.                              \label{eq:upper-localization-quantitative}
\end{equation}
\end{lemma}

\begin{proof}
Since $r\leq3/5$, $u\geq u_q$, and
$|z|\leq u_q$,
\[
 u-rz\geq u-r|z|\geq u-ru_q\geq (1-r)u\geq \frac25u\geq\frac25u_q.
\]
Since $\sqrt{1-r^2}\leq1$, this gives
\[
 \frac{u-rz}{\sqrt{1-r^2}}\geq\frac25u_q.
\]
Hence the upper Mills bound
\eqref{eq:mills-upper} in Appendix~A applies to
$(u-rz)/\sqrt{1-r^2}$, while the lower Mills bound
\eqref{eq:mills-lower} applies to $u$.  These two inequalities give
\begin{align}
 \frac{\phi(z)\Phib\{(u-rz)/\sqrt{1-r^2}\}}{2\Phib(u)}
 &\leq
 \frac{\phi(z)\phi\{(u-rz)/\sqrt{1-r^2}\}}{2\phi(u)}
 \frac{\sqrt{1-r^2}(u^2+1)}{u(u-rz)} \nonumber\\
 &= \frac1{2\sqrt{2\pi}}
 \frac{\sqrt{1-r^2}(u^2+1)}{u(u-rz)}
 \exp\left\{
 -\frac{z^2}{2}
 -\frac{(u-rz)^2}{2(1-r^2)}
 +\frac{u^2}{2}
 \right\} \nonumber\\
 &= \frac1{2\sqrt{2\pi}}
 \frac{\sqrt{1-r^2}(u^2+1)}{u(u-rz)}
 \exp\left\{
 -\frac{(1-r^2)z^2+(u-rz)^2-(1-r^2)u^2}
 {2(1-r^2)}
 \right\} \nonumber\\
 &= \frac1{2\sqrt{2\pi}}
 \frac{\sqrt{1-r^2}(u^2+1)}{u(u-rz)}
 \exp\left\{-\frac{(z-ru)^2}{2(1-r^2)}\right\}.  \label{eq:upper-mills-localization}
\end{align}
Using a similar argument, we can prove
\begin{align}
 \frac{\phi(z)\Phib\{(u+rz)/\sqrt{1-r^2}\}}{2\Phib(u)}
 &\leq \frac1{2\sqrt{2\pi}}
\frac{\sqrt{1-r^2}(u^2+1)}{u(u+rz)}
 \exp\left\{-\frac{(z+ru)^2}{2(1-r^2)}\right\}.  \label{eq:upper-mills-localization-minus}
\end{align}
For both signs, $|z|\leq u_q\leq u$ implies
\[
 u\mp rz\geq u-r|z|\geq (1-r)u\geq \frac25 u.
\]
Also $\sqrt{1-r^2}\leq1$ and $u\geq u_q\geq1$.  Therefore
\[
 \max\left\{
 \frac{\sqrt{1-r^2}(u^2+1)}{u(u-rz)},
 \frac{\sqrt{1-r^2}(u^2+1)}{u(u+rz)}
 \right\}
 \leq
 \frac{u^2+1}{(2/5)u^2}
 \leq 5.
\]
This bound is uniform over $0\leq r\leq3/5$, $u\geq u_q$, and
$|z|\leq u_q$.  Substituting it into
\eqref{eq:upper-mills-localization} and
\eqref{eq:upper-mills-localization-minus}, and increasing $C$, proves
\eqref{eq:upper-localization}.  If $|z|=ru+d$ with
$|d|\leq K_q$, then the first term in
\eqref{eq:upper-mills-localization}-\eqref{eq:upper-mills-localization-minus}
has prefactor
\begin{equation}
 \frac{\sqrt{1-r^2}(u^2+1)}{u\{(1-r^2)u-rd\}}
 =\frac1{\sqrt{1-r^2}}\,
   \frac{1+u^{-2}}{1-rd/\{(1-r^2)u\}}.               \label{eq:upper-localization-prefactor}
\end{equation}
Because $r\leq3/5$, one has $1-r^2\geq16/25$.  Hence, when
$|d|\leq K_q\leq u_q/4$,
\[
 \left|\frac{rd}{(1-r^2)u}\right|
 \leq
 \frac{(3/5)K_q}{(16/25)u_q}
 \leq \frac{15}{64}.
\]
Since $(1-x)^{-1}\leq1+C|x|$ for $|x|\leq15/64$, and since
$u\geq u_q\geq1$,
\[
 \frac{1+u^{-2}}{1-rd/\{(1-r^2)u\}}
 \leq
 (1+u_q^{-1})\left(1+C\frac{K_q}{u_q}\right)
 \leq 1+C\frac{K_q+1}{u_q}.
\]
Combining this estimate with \eqref{eq:upper-localization-prefactor} gives
\[
\begin{aligned}
 \frac{\sqrt{1-r^2}(u^2+1)}{u\{(1-r^2)u-rd\}}
 &=\frac1{\sqrt{1-r^2}}\,
   \frac{1+u^{-2}}{1-rd/\{(1-r^2)u\}}\\
 &\leq
 \frac1{\sqrt{1-r^2}}
 \left\{1+C\frac{K_q+1}{u_q}\right\}\\
 &=
 \frac{1+C(K_q+1)/u_q}{\sqrt{1-r^2}}.
\end{aligned}
\]
Note that
\[
\begin{aligned}
 z\geq0:\quad
 |z+ru|
 &=|z|+ru=2|z|-d
 \geq 2L_q-K_q,\\
 z<0:\quad
 |z-ru|
 &=|z|+ru=2|z|-d
 \geq 2L_q-K_q.
\end{aligned}
\]
Therefore, with the $+$ sign when $z\geq0$ and the $-$ sign when $z<0$,
\begin{equation}
\exp\left\{-\frac{(z\pm ru)^2}{2(1-r^2)}\right\}
\leq
\exp\left\{-\frac{(2L_q-K_q)^2}{2(1-r^2)}\right\}
\leq \exp\{-u_q\},
\label{eq:upper-localization-opposite-exponential}
\end{equation}
because $1-r^2\leq1$ and $(2L_q-K_q)^2/2\geq u_q$.
The proof is then completed by
\eqref{eq:upper-mills-localization} - \eqref{eq:upper-localization-opposite-exponential}.
\end{proof}

For the next three lemmas, fix $0<r\leq3/5$ and use $K_q,L_q$ from
\eqref{eq:upper-KLq-def}.  Let $\Pi$ be a positive measure of mass at most
one on $(\theta,\alpha)\in\mathbb R\times[-1,1]$, let
$\varepsilon\sim N(0,1)$, and define
\begin{equation}
 G_z(u)=\int \mathbb P\{|\theta+\alpha z+\sqrt{1-\alpha^2}\,\varepsilon|
                    \geq u\}\,\dd\Pi(\theta,\alpha). \label{eq:upper-mixture}
\end{equation}
For $z$ and $u$, write
\[
\begin{aligned}
G_z^{\mathrm{large}}(u)
&=\int_{\{|\alpha|\ge r/u_q\}}
 \mathbb P\{|\theta+\alpha z+\sqrt{1-\alpha^2}\,\varepsilon|\ge u\}
 \,\dd\Pi(\theta,\alpha),\\
G_z^{\mathrm{small}}(u)
&=\int_{\{|\alpha|< r/u_q\}}
 \mathbb P\{|\theta+\alpha z+\sqrt{1-\alpha^2}\,\varepsilon|\ge u\}
 \,\dd\Pi(\theta,\alpha).
\end{aligned}
\]
Then
\[
G_z(u)=G_z^{\mathrm{large}}(u)+G_z^{\mathrm{small}}(u).
\]
For each $z$, let $\mathcal C_z$ be a finite set satisfying
\begin{equation}
 \mathcal C_z\subseteq\left\{u\geq u_q:\ G_z(u)\geq\frac{p(u)}{2q},\
 G_z(v)\leq3\frac{p(v)}q\ \forall\,u_q\leq v<u\right\}. \label{eq:upper-threshold-class}
\end{equation}
Define
\begin{equation}
\begin{aligned}
E_\pm^{\mathrm{large}}(r)
=\Big\{z:\;&\pm z\in[L_q,u_q],\ \exists u\text{ such that }
u\in\mathcal C_z,\ \big||z|-ru\big|\leq K_q,\\
&\text{and }G_z^{\mathrm{large}}(u)\geq p(u)/(4q)\Big\},
\end{aligned}                                      \label{eq:upper-large-radii-def}
\end{equation}
and
\begin{equation}
\begin{aligned}
E_\pm^{\mathrm{small}}(r)
=\Big\{z:\;&\pm z\in[L_q,u_q],\ \exists u\text{ such that }
u\in\mathcal C_z,\ \big||z|-ru\big|\leq K_q,\\
&\text{and }G_z^{\mathrm{small}}(u)\geq p(u)/(4q)\Big\}.
\end{aligned}                                      \label{eq:upper-small-radii-def}
\end{equation}
The next lemma bounds $|E_\pm^{\mathrm{large}}(r)|$.
\begin{lemma}\label{lem:upper-large-coefficients}
There are universal constants $C<\infty$ and $q_0>0$ such that, whenever
$q\leq q_0$, the following bound holds uniformly over all positive measures
$\Pi$ on $\mathbb R\times[-1,1]$ with
$\Pi(\mathbb R\times[-1,1])\leq1$, and over all families
$(\mathcal C_z)$ satisfying \eqref{eq:upper-threshold-class}:
\begin{equation}
 |E_+^{\mathrm{large}}(r)|+|E_-^{\mathrm{large}}(r)|
 \leq(1-r)u_q+C\sqrt{u_q}.                             \label{eq:upper-large-coefficient-range}
\end{equation}
\end{lemma}

\begin{proof}
Set
\begin{equation}
\begin{aligned}
Y_z&=Y_z(\theta,\alpha,e)=\theta+\alpha z+\sqrt{1-\alpha^2}\,e,\\
\dd\nu(\theta,\alpha,e)&=\frac13\,\dd\Pi(\theta,\alpha)\phi(e)\dd e .
\end{aligned}                                      \label{eq:upper-Yz-def}
\end{equation}
Then
\begin{align}
\nu\{|Y_z|\geq v\}&=\frac13G_z(v), \notag\\
\nu\{|\alpha|\geq r/u_q,\ |Y_z|\geq v\}
   &=\frac13G_z^{\mathrm{large}}(v).                  \label{eq:upper-large-path-identity}
\end{align}
If $u\in\mathcal C_z$ and $u_q\leq v<u$, then
\eqref{eq:upper-threshold-class} gives
\begin{equation}
\nu\{|Y_z|\geq v\}\leq\frac{p(v)}q.                 \label{eq:upper-admissible-tail-bound}
\end{equation}
If $z\in E_+^{\mathrm{large}}(r)$ and
$u\in\mathcal C_z$ is as in \eqref{eq:upper-large-radii-def}, then by
\eqref{eq:upper-large-path-identity},
\begin{equation}
 \nu\{|\alpha|\geq r/u_q,\ |Y_z|\geq u\}
 \geq \frac{p(u)}{12q}.                             \label{eq:upper-high-mass}
\end{equation}
The same result holds with $z\in E_-^{\mathrm{large}}(r)$ and
$u\in\mathcal C_z$.

Fix any $z_1\in E_+^{\mathrm{large}}(r)$.  Consider
$z_2\in E_+^{\mathrm{large}}(r)$ and
$-z_3\in E_-^{\mathrm{large}}(r)$ with $z_2>z_1$.  Choose
$v_1\in\mathcal C_{z_1}$, $v_2\in\mathcal C_{z_2}$, and
$v_3\in\mathcal C_{-z_3}$ as in \eqref{eq:upper-large-radii-def}, and put
\begin{equation}
 d_2=\frac r{u_q}(z_2-z_1),\qquad
 d_3=\frac r{u_q}(z_1+z_3).                         \label{eq:upper-three-increments}
\end{equation}
Split
$\{|\alpha|\ge r/u_q,\ |Y_{z_1}|\ge v_1\}=A_+\dot\cup A_-$, where
\[
\begin{aligned}
A_+&=\{|\alpha|\ge r/u_q,\ |Y_{z_1}|\ge v_1,\ \alpha Y_{z_1}\ge0\},\\
A_-&=\{|\alpha|\ge r/u_q,\ |Y_{z_1}|\ge v_1,\ \alpha Y_{z_1}<0\}.
\end{aligned}
\]
Then \eqref{eq:upper-high-mass} gives
\[
\nu(A_+)+\nu(A_-)
=\nu\{|\alpha|\ge r/u_q,\ |Y_{z_1}|\ge v_1\}
\geq\frac{p(v_1)}{12q}.
\]
Moreover,
\[
A_+\subseteq\{|Y_{z_2}|\geq v_1+d_2\},\qquad
A_-\subseteq\{|Y_{-z_3}|\geq v_1+d_3\}.
\]
Indeed, on $A_+$,
\[
|Y_{z_2}|=|Y_{z_1}+\alpha(z_2-z_1)|
\geq |Y_{z_1}|+|\alpha|(z_2-z_1)\geq v_1+d_2,
\]
while on $A_-$,
\[
|Y_{-z_3}|=|Y_{z_1}-\alpha(z_1+z_3)|
\geq |Y_{z_1}|+|\alpha|(z_1+z_3)\geq v_1+d_3.
\]

Let
\[
 \widetilde E_-^{\mathrm{large}}(r)
 =\{-z:\ z\in E_-^{\mathrm{large}}(r)\}.
\]
It is enough to bound
$|E_+^{\mathrm{large}}(r)|+|\widetilde E_-^{\mathrm{large}}(r)|$.
If $E_+^{\mathrm{large}}(r)\cup\widetilde E_-^{\mathrm{large}}(r)$ is empty,
there is nothing to prove.  Otherwise choose
$z_1\in E_+^{\mathrm{large}}(r)\cup\widetilde E_-^{\mathrm{large}}(r)$
arbitrarily close to
\[
\inf\{z:\ z\in E_+^{\mathrm{large}}(r)\cup
\widetilde E_-^{\mathrm{large}}(r)\}.
\]
Choose
$v_1\in\mathcal C_{z_1}$ if $z_1\in E_+^{\mathrm{large}}(r)$, and
$v_1\in\mathcal C_{-z_1}$ if
$z_1\in\widetilde E_-^{\mathrm{large}}(r)$.  In the first case,
\eqref{eq:upper-large-radii-def} gives
\[
 z_1\in[L_q,u_q],\qquad |z_1-rv_1|\leq K_q.
\]
In the second case, $-z_1\in E_-^{\mathrm{large}}(r)$, so the same
definition gives
\[
 z_1=|-z_1|\in[L_q,u_q],\qquad |z_1-rv_1|\leq K_q.
\]
Thus, in either case,
\begin{equation}
 z_1\geq L_q,\quad |z_1-rv_1|\leq K_q
 \quad\Longrightarrow\quad
 \frac{r v_1}{u_q}\geq\frac{z_1-K_q}{u_q}
 \geq\frac{L_q-K_q}{u_q}.                            \label{eq:upper-ru-lower}
\end{equation}
Set
\begin{equation}
 B_q=\frac{2K_q+2r^2}{1-r^2/u_q}
       +\frac{4u_q}{L_q-K_q}.                            \label{eq:upper-buffer}
\end{equation}
We claim that, to the right of $z_1+B_q$, the two reflected sets cannot
overlap:
\begin{equation}
\bigl(E_+^{\mathrm{large}}(r)\cap(z_1+B_q,u_q]\bigr)
\cap
\bigl(\widetilde E_-^{\mathrm{large}}(r)\cap(z_1+B_q,u_q]\bigr)=\emptyset .
                                                        \label{eq:upper-reflected-disjoint-tail}
\end{equation}
We prove \eqref{eq:upper-reflected-disjoint-tail} by contradiction.  Assume
\eqref{eq:upper-reflected-disjoint-tail} fails.  Then there exist
\begin{equation}
 z_2\in E_+^{\mathrm{large}}(r),\qquad
 z_3\in \widetilde E_-^{\mathrm{large}}(r),\qquad
 z_2,z_3>z_1+B_q .                                  \label{eq:upper-no-reflected-tail-pair}
\end{equation}
If $z_1\in E_+^{\mathrm{large}}(r)$, assume
\eqref{eq:upper-no-reflected-tail-pair} and choose
$v_2\in\mathcal C_{z_2}$ and $v_3\in\mathcal C_{-z_3}$.  By
\eqref{eq:upper-large-radii-def},
\[
 |z_1-rv_1|\leq K_q,\qquad |z_2-rv_2|\leq K_q,\qquad
 |z_3-rv_3|\leq K_q,
\]
where the last inequality uses $-z_3\in E_-^{\mathrm{large}}(r)$, so that
$|-z_3|=z_3$.  Hence
\[
\begin{aligned}
 r(v_2-v_1)
 &= (rv_2-z_2)+(z_2-z_1)+(z_1-rv_1)
    \geq z_2-z_1-2K_q,\\
 r(v_3-v_1)
 &= (rv_3-z_3)+(z_3-z_1)+(z_1-rv_1)
    \geq z_3-z_1-2K_q.
\end{aligned}
\]
Therefore
\begin{equation}
 v_2-v_1\geq\frac{z_2-z_1-2K_q}{r},\qquad
 v_3-v_1\geq\frac{z_3-z_1-2K_q}{r}.              \label{eq:upper-alignment-threshold-lower}
\end{equation}
Since $z_2,z_3>z_1+B_q$,
\[
 z_2-z_1,\ z_3-z_1>
 \frac{2K_q+2r^2}{1-r^2/u_q}.
\]
Therefore
\[
 (z_2-z_1)\left(1-\frac{r^2}{u_q}\right)>2K_q,
\]
and, using $z_1\leq u_q$,
\[
 (z_3-z_1)\left(1-\frac{r^2}{u_q}\right)>2K_q+2r^2
 \geq 2K_q+\frac{2r^2z_1}{u_q}.
\]
Equivalently,
\[
 \frac{z_2-z_1-2K_q}{r}>\frac r{u_q}(z_2-z_1),\qquad
 \frac{z_3-z_1-2K_q}{r}>\frac r{u_q}(z_1+z_3).
\]
Combining these inequalities with
\eqref{eq:upper-alignment-threshold-lower} gives
\[
 v_2-v_1>\frac r{u_q}(z_2-z_1),\qquad
 v_3-v_1>\frac r{u_q}(z_1+z_3),
\]
that is,
\begin{equation}
 v_1+d_2<v_2,\qquad v_1+d_3<v_3.
\label{eq:upper-three-ordering}
\end{equation}
Also, \eqref{eq:upper-ru-lower} gives
\[
 \frac{r v_1}{u_q}\geq\frac{L_q-K_q}{u_q}.
\]
Since $z_2,z_3>z_1+B_q$ and the second term in $B_q$ is
$4u_q/(L_q-K_q)$,
\[
 z_2-z_1>\frac{4u_q}{L_q-K_q},\qquad
 z_1+z_3>z_3-z_1>\frac{4u_q}{L_q-K_q}.
\]
Consequently
\[
 \frac{r v_1}{u_q}\min\{z_2-z_1,z_1+z_3\}
 \geq
 \frac{L_q-K_q}{u_q}\min\{z_2-z_1,z_1+z_3\}>4
\]
and hence, by \eqref{eq:upper-three-increments},
\begin{equation}
 \min\{d_2,d_3\}>\frac4{v_1}.                         \label{eq:upper-min-increment}
\end{equation}

\indent The ordering in \eqref{eq:upper-three-ordering}, together with
$v_1\geq u_q$ and $d_2,d_3\geq0$, gives
\begin{equation}
 u_q\leq v_1+d_2<v_2,\qquad u_q\leq v_1+d_3<v_3.
 \label{eq:upper-admissible-threshold-ordering}
\end{equation}
Thus $v_2\in\mathcal C_{z_2}$, $v_3\in\mathcal C_{-z_3}$, so
\eqref{eq:upper-admissible-tail-bound} applies with
$(z,u,v)=(z_2,v_2,v_1+d_2)$ and
$(z,u,v)=(-z_3,v_3,v_1+d_3)$.  Hence
\[
\begin{aligned}
\frac{p(v_1)}{12q}
&\leq \nu(A_+)+\nu(A_-)\\
&\leq \nu\{|Y_{z_2}|\geq v_1+d_2\}
     +\nu\{|Y_{-z_3}|\geq v_1+d_3\}\\
&\leq \frac{p(v_1+d_2)+p(v_1+d_3)}q,
   \qquad\text{by \eqref{eq:upper-admissible-tail-bound}.}
\end{aligned}
\]
Multiplying by $q$ and substituting the definitions of $d_2$ and $d_3$
in \eqref{eq:upper-three-increments} imply
\begin{equation}
 \frac{p(v_1)}{12}
 \leq p\{v_1+(r/u_q)(z_2-z_1)\}
     +p\{v_1+(r/u_q)(z_1+z_3)\}.                    \label{eq:upper-three-crossing}
\end{equation}
For $u>0$ and $d\geq0$, $p=2\Phib$ and the normal hazard
$\lambda(t)=\phi(t)/\Phib(t)$ give
\begin{equation}
\begin{aligned}
\frac{p(u+d)}{p(u)}
&=\frac{\Phib(u+d)}{\Phib(u)}
 =\exp\left\{-\int_u^{u+d}\lambda(t)\,\dd t\right\}  \\
&\leq \exp\left\{-\int_u^{u+d}t\,\dd t\right\}
 =\exp\{-ud-d^2/2\}\leq e^{-ud},
\end{aligned}                                      \label{eq:upper-tail-transport}
\end{equation}
where the inequality uses $\lambda(t)>t$ for $t>0$, as stated in
\eqref{eq:mills-hazard} of Appendix Lemma~\ref{lem:mills}.
Thus the right side of \eqref{eq:upper-three-crossing} is at most
\[
 \frac{p(v_1)}{48}+\frac{p(v_1)}{48}<\frac{p(v_1)}{12},
\]
which is impossible.  Equivalently, the tail calculation gives
\begin{equation}
 \frac r{u_q}\min\{z_2-z_1,z_1+z_3\}
 =\min\{d_2,d_3\}\leq \frac4{v_1}.                 \label{eq:upper-three-obstruction}
\end{equation}
This contradicts \eqref{eq:upper-min-increment}.  By the same argument with signs
reversed, if $-z_1,-z_3\in E_-^{\mathrm{large}}(r)$,
$z_2\in E_+^{\mathrm{large}}(r)$, and $z_3>z_1$, then, for
$v_1\in\mathcal C_{-z_1}$ chosen as in
\eqref{eq:upper-large-radii-def},
\begin{equation}
 \frac r{u_q}\min\{z_3-z_1,z_1+z_2\}\leq \frac4{v_1}.
 \label{eq:upper-three-obstruction-reversed}
\end{equation}
If $z_1\in\widetilde E_-^{\mathrm{large}}(r)$, the same contradiction uses
\eqref{eq:upper-three-obstruction-reversed}.
Together with the preceding case $z_1\in E_+^{\mathrm{large}}(r)$, this proves
\eqref{eq:upper-reflected-disjoint-tail}.

Put
\[
 a=\inf\{z:\ z\in E_+^{\mathrm{large}}(r)\cup
\widetilde E_-^{\mathrm{large}}(r)\}.
\]
Since $z_1$ can be chosen arbitrarily close to $a$,
\eqref{eq:upper-reflected-disjoint-tail} gives, after letting $z_1\downarrow a$,
\[
 \bigl(E_+^{\mathrm{large}}(r)\cap(a+B_q,u_q]\bigr)
 \cap
 \bigl(\widetilde E_-^{\mathrm{large}}(r)\cap(a+B_q,u_q]\bigr)=\emptyset .
\]
By \eqref{eq:upper-large-radii-def} and \eqref{eq:upper-threshold-class}, both
sets are contained in
\[
 I_q=[\max\{L_q,r u_q-K_q\},u_q].
\]
Indeed, for any signed point $s\in E_+^{\mathrm{large}}(r)\cup
E_-^{\mathrm{large}}(r)$, and for its associated $u\in\mathcal C_s$,
\[
 |s|\in[L_q,u_q],\qquad |s|\geq ru-K_q\geq r u_q-K_q.
\]
Recall the definition of $B_q$ in \eqref{eq:upper-buffer}.
Set
\[
 J_0=I_q\cap[a,a+B_q],\qquad
 J_1=I_q\cap(a+B_q,u_q].
\]
Since both reflected sets are contained in $I_q$ and have no points below
$a$, their total length decomposes as
\[
\begin{aligned}
 |E_+^{\mathrm{large}}(r)|+|\widetilde E_-^{\mathrm{large}}(r)|
&=|E_+^{\mathrm{large}}(r)\cap J_0|
  +|\widetilde E_-^{\mathrm{large}}(r)\cap J_0|\\
&\quad
  +|E_+^{\mathrm{large}}(r)\cap J_1|
  +|\widetilde E_-^{\mathrm{large}}(r)\cap J_1|.
\end{aligned}
\]
On the set $J_0$, each set contributes at most
$|J_0|$ with
\[
 |J_0|\leq\min\{B_q,|I_q|\}.
\]
On $J_1$, the disjointness above gives
\[
\bigl(E_+^{\mathrm{large}}(r)\cap J_1\bigr)
\cap
\bigl(\widetilde E_-^{\mathrm{large}}(r)\cap J_1\bigr)=\emptyset ,
\]
so
\[
\begin{aligned}
 |E_+^{\mathrm{large}}(r)\cap J_1|
 +|\widetilde E_-^{\mathrm{large}}(r)\cap J_1|
 &=
 |\bigl(E_+^{\mathrm{large}}(r)\cup\widetilde E_-^{\mathrm{large}}(r)\bigr)
 \cap J_1|\leq |J_1|.
\end{aligned}
\]
Since $I_q=[\max\{L_q,r u_q-K_q\},u_q]$, the containment of
$E_+^{\mathrm{large}}(r)$ and $\widetilde E_-^{\mathrm{large}}(r)$ in
$I_q$ gives $a\geq\max\{L_q,r u_q-K_q\}$.  Hence
\[
\begin{aligned}
 |J_1|
 &=|I_q\cap(a+B_q,u_q]|\\
 &\leq (u_q-a-B_q)_+\\
 &\leq (u_q-\max\{L_q,r u_q-K_q\}-B_q)_+
 =(|I_q|-B_q)_+ .
\end{aligned}
\]
Therefore
\[
\begin{aligned}
 |E_+^{\mathrm{large}}(r)|+|E_-^{\mathrm{large}}(r)|
 &=|E_+^{\mathrm{large}}(r)|+|\widetilde E_-^{\mathrm{large}}(r)|\\
 &\leq 2|J_0|+
 |\bigl(E_+^{\mathrm{large}}(r)\cup\widetilde E_-^{\mathrm{large}}(r)\bigr)
 \cap J_1|\\
 &\leq 2\min\{B_q,|I_q|\}+(|I_q|-B_q)_+\\
 &\leq B_q+|I_q|\\
 &= B_q+u_q-\max\{L_q,r u_q-K_q\} \\
 &\leq (1-r)u_q+K_q+B_q .
\end{aligned}
\]
After decreasing $q_0$ if necessary, $1-r^2/u_q\geq1/2$.  Thus
\eqref{eq:upper-buffer} gives
\[
 B_q
 \leq 2(2K_q+2r^2)+4\sqrt{u_q}
 \leq C\{K_q+\sqrt{u_q}+1\}.
\]
Consequently, since $K_q=\sqrt{8\log u_q}$,
\[
 K_q+B_q\leq C\{K_q+\sqrt{u_q}+1\}\leq C\sqrt{u_q},
\]
which proves \eqref{eq:upper-large-coefficient-range}.
\end{proof}

The next lemma bounds $|E_\pm^{\mathrm{small}}(r)|$.

\begin{lemma}\label{lem:upper-small-coefficients}
With $E_\pm^{\mathrm{small}}(r)$ defined in
\eqref{eq:upper-small-radii-def}, there are universal constants $C<\infty$
and $q_0>0$ such that, whenever $q\leq q_0$,
\begin{equation}
 |E_+^{\mathrm{small}}(r)|+|E_-^{\mathrm{small}}(r)|
 \leq C(K_q+1)\leq C\sqrt{u_q}                         \label{eq:upper-small-coefficient-range}
\end{equation}
uniformly over all positive measures $\Pi$ on $\mathbb R\times[-1,1]$
such that $\Pi(\mathbb R\times[-1,1])\leq1$, and over all families
$(\mathcal C_z)$ satisfying
\eqref{eq:upper-threshold-class}.
\end{lemma}

\begin{proof}
Put
\[
 b=\frac r{u_q},\qquad
 \eta=\Pi\{(\theta,\alpha):|\alpha|<b\}.
\]
For each $z$ and $u$, put
\begin{equation}
 Q_z(u)=\frac{G_z^{\mathrm{small}}(u)}{p(u)}
 =\frac1{p(u)}\int_{\{|\alpha|<b\}}
 \mathbb P\{|\theta+\alpha z+\sqrt{1-\alpha^2}\,\varepsilon|\geq u\}
 \,\dd\Pi(\theta,\alpha),
 \label{eq:upper-Qz-def}
\end{equation}
where $\varepsilon\sim N(0,1)$.  If
$z\in E_+^{\mathrm{small}}(r)\cup E_-^{\mathrm{small}}(r)$ and
$u\in\mathcal C_z$ is one of the values appearing in
\eqref{eq:upper-small-radii-def}, then
\begin{equation}
 Q_z(u)\geq\frac1{4q}.                              \label{eq:upper-small-coefficient-mass}
\end{equation}

If $E_+^{\mathrm{small}}(r)\cup E_-^{\mathrm{small}}(r)$ is empty, there is
nothing to prove.  Otherwise choose
$z_1\in E_+^{\mathrm{small}}(r)\cup E_-^{\mathrm{small}}(r)$ so that
$|z_1|$ is arbitrarily close to
\[
\inf\{|z|:\ z\in E_+^{\mathrm{small}}(r)\cup E_-^{\mathrm{small}}(r)\}.
\]
Choose $v_1\in\mathcal C_{z_1}$
as in \eqref{eq:upper-small-radii-def}.  Since
$Q_{z_1}(v_1)\geq1/(4q)>0$, necessarily $\eta>0$; if
$\eta=0$, then $Q_z\equiv0$ for every $z$.  By
\eqref{eq:upper-small-radii-def}, $|z_1|\leq u_q$ and
$\big||z_1|-rv_1\big|\leq K_q$.  Therefore
\begin{equation}
 rv_1\leq |z_1|+K_q\leq u_q+K_q,
 \qquad\text{and hence}\qquad
 bv_1\leq1+K_q/u_q.                                  \label{eq:upper-ru-upper}
\end{equation}
Define
\[
 H_1=\log\left\{\frac{Q_{z_1}(v_1)\sqrt{1-b^2}}{2\eta}\right\}.
\]
Using \eqref{eq:upper-small-coefficient-mass} and $\eta\leq1$,
\[
 H_1
 \geq\log\left\{\frac{\sqrt{1-b^2}}{8q}\right\}.
\]
For $q_0$ small enough, $u_q\geq2$.  Since $0\leq r\leq1$, this gives
\[
 b=\frac r{u_q}\leq\frac12,
 \qquad
 \sqrt{1-b^2}\geq\frac12.
\]
Therefore, using $q=p(u_q)\leq e^{-u_q^2/2}$ from
\eqref{eq:mills-two-sided-exponential-tail},
\begin{equation}
 H_1\geq\log\frac1{16q}
 \geq\frac{u_q^2}{2}-\log16
 \geq\frac{u_q^2}{3}\geq4,
 \label{eq:upper-H1-lower}
\end{equation}
after decreasing $q_0$, if necessary.  Moreover, by
\eqref{eq:upper-ru-upper},
\[
 \frac{9b^2v_1^2}{1-b^2}
 \leq
 \frac{9(1+K_q/u_q)^2}{1-u_q^{-2}}
 \leq C.
\]
Since $H_1\geq u_q^2/3$, decreasing $q_0$ once more makes this last
constant at most $H_1$.  Hence
\begin{equation}
 H_1=\log\left\{\frac{Q_{z_1}(v_1)\sqrt{1-b^2}}{2\eta}\right\}\geq4,
 \qquad
 \frac{9b^2v_1^2}{1-b^2}\leq H_1.                  \label{eq:upper-ratio-growth-conditions}
\end{equation}

We will show the following result at the end of the proof:
\begin{equation}
 \exists\,v\geq v_1:\qquad
 Q_{z_1}(v)\geq \frac{3e^{10u_q}}q,\qquad
 0\leq v-v_1\leq C\frac{v_1}{u_q}.
 \label{eq:upper-Q-large}
\end{equation}

\noindent Now we prove \eqref{eq:upper-small-coefficient-range} under
\eqref{eq:upper-Q-large}.  For any
$|z'|\leq u_q$, put
\begin{equation}
 \Delta=b|z'-z_1|\leq2r.
 \label{eq:upper-delta-def}
\end{equation}
Fix a component $(\theta,\alpha)$ with $|\alpha|<b$, and use the same
residual $\varepsilon$ to form the two conditional statistics at $z_1$ and
at $z'$:
\[
 Y_{z_1}=\theta+\alpha z_1+\sqrt{1-\alpha^2}\,\varepsilon,\qquad
 Y_{z'}=\theta+\alpha z'+\sqrt{1-\alpha^2}\,\varepsilon .
\]
Then
\[
 |Y_{z'}-Y_{z_1}|=|\alpha|\,|z'-z_1|\leq b|z'-z_1|=\Delta,
\]
and hence
\[
 \{|Y_{z_1}|\geq v\}\subseteq \{|Y_{z'}|\geq v-\Delta\}.
\]
For this fixed $(\theta,\alpha)$, the inclusion gives
\[
 \mathbb P_\varepsilon\{|Y_{z'}|\geq v-\Delta\}
 \geq
 \mathbb P_\varepsilon\{|Y_{z_1}|\geq v\}.
\]
Integrating the last inequality with respect to $\Pi$ over the
small-coefficient set $\{|\alpha|<b\}$ gives, by the definition of
$G_z^{\mathrm{small}}$,
\[
\begin{aligned}
 G_{z'}^{\mathrm{small}}(v-\Delta)
 &=
 \int_{\{|\alpha|<b\}}
 \mathbb P_\varepsilon\{|Y_{z'}|\geq v-\Delta\}\,\dd\Pi(\theta,\alpha)
 \\
 &\geq
 \int_{\{|\alpha|<b\}}
 \mathbb P_\varepsilon\{|Y_{z_1}|\geq v\}\,\dd\Pi(\theta,\alpha)
 =
 G_{z_1}^{\mathrm{small}}(v).
\end{aligned}
\]
Dividing by $p(v-\Delta)$ and using
$G_{z_1}^{\mathrm{small}}(v)=Q_{z_1}(v)p(v)$ gives
\begin{equation}
 Q_{z'}(v-\Delta)
 \geq Q_{z_1}(v)\frac{p(v)}{p(v-\Delta)}.            \label{eq:upper-factor-coupling}
\end{equation}
Since $p=2\Phib$, $p'(t)/p(t)=-\lambda(t)$, where
$\lambda(t)=\phi(t)/\Phib(t)$.  Also, by
\eqref{eq:upper-delta-def}, $r\leq3/5$, and $v\geq v_1\geq u_q$,
\[
 v-\Delta\geq v_1-\Delta\geq u_q-2r\geq u_q-\frac65>0
\]
after decreasing $q_0$, if necessary.  Thus the interval
$[v-\Delta,v]$ lies in $(0,\infty)$, and
\[
 \frac{p(v)}{p(v-\Delta)}
 =
 \exp\left\{-\int_{v-\Delta}^v \lambda(t)\,\dd t\right\}.
\]
By \eqref{eq:mills-hazard} of Lemma~\ref{lem:mills}, for
$v-\Delta\leq t\leq v$,
\[
 \lambda(t)\leq t+\frac1t\leq v+\frac1{v-\Delta}.
\]
Therefore
\begin{equation}
 \frac{p(v)}{p(v-\Delta)}
 \geq\exp\left[-\Delta\left\{v+\frac1{v-\Delta}\right\}\right]. \label{eq:upper-tail-ratio-lower}
\end{equation}
By \eqref{eq:upper-small-radii-def},
\[
 rv_1\leq |z_1|+K_q\leq u_q+K_q.
\]
Also, \eqref{eq:upper-Q-large} and \eqref{eq:upper-ru-upper} give
\[
 r(v-v_1)\leq C\frac{rv_1}{u_q}
 \leq C\left(1+\frac{K_q}{u_q}\right)=O(1).
\]
Therefore
\[
 rv=rv_1+r(v-v_1)\leq u_q+K_q+O(1).
\]
Since $\Delta\leq2r$ and $v-\Delta\geq u_q-2r$, the exponent in
\eqref{eq:upper-tail-ratio-lower} satisfies
\[
 \Delta\left\{v+\frac1{v-\Delta}\right\}
 \leq 2rv+\frac{2r}{u_q-2r}
 \leq 2u_q+2K_q+O(1)\leq3u_q,
\]
after decreasing $q_0$, if necessary, where the last step uses
$K_q=o(u_q)$ from \eqref{eq:upper-KLq-def}.  Combining
\eqref{eq:upper-factor-coupling}, \eqref{eq:upper-Q-large}, and
\eqref{eq:upper-tail-ratio-lower},
\[
\begin{aligned}
 Q_{z'}(v-\Delta)
 &\geq Q_{z_1}(v)\frac{p(v)}{p(v-\Delta)}\\
 &\geq \frac{3e^{10u_q}}q
 \exp\left[-\Delta\left\{v+\frac1{v-\Delta}\right\}\right]\\
 &\geq \frac{3e^{10u_q}}q e^{-3u_q}
 =\frac{3e^{7u_q}}q>\frac3q .
\end{aligned}
\]
Hence
\begin{equation}
 Q_{z'}(v-\Delta)>\frac3q.                          \label{eq:upper-global-obstruction}
\end{equation}
If $v-\Delta<u_q$, then
\begin{equation}
 v_1\leq v<u_q+\Delta\leq u_q+2r .
 \label{eq:upper-v-below-uq-plus-delta}
\end{equation}
Since $r\leq3/5$, \eqref{eq:mills-local-ratio} in
Lemma~\ref{lem:mills} gives, uniformly over $0\leq h\leq2r$,
\[
\begin{aligned}
\log\frac{p(u_q+h)}{p(u_q)}
&=-u_qh-\frac{h^2}{2}
  +\log\frac{u_q}{u_q+h}+o(1)\\
&\geq -2ru_q-2r^2-\log\left(1+\frac{2r}{u_q}\right)+o(1)\\
&\geq -\frac65u_q-\frac{18}{25}
      -\log\left(1+\frac{6}{5u_q}\right)+o(1)\\
&\geq -2u_q,
\end{aligned}
\]
after decreasing $q_0$, if necessary.  The last step uses $u_q\to\infty$
as $q\downarrow0$, and the $o(1)$ term is uniform over
$0\leq h\leq2r\leq6/5$.  Taking $h=2r$ and using
\eqref{eq:upper-v-below-uq-plus-delta} together with the monotonicity of $p$,
\[
 p(v)\geq p(u_q+2r)\geq p(u_q)e^{-2u_q}=q e^{-2u_q}.
\]
Because $G_{z_1}^{\mathrm{small}}(v)\leq\Pi(\mathbb R\times[-1,1])\leq1$,
\[
 Q_{z_1}(v)
 =\frac{G_{z_1}^{\mathrm{small}}(v)}{p(v)}
 \leq \frac1{p(v)}
 \leq \frac{e^{2u_q}}q.
\]
This contradicts \eqref{eq:upper-Q-large}, which gives
$Q_{z_1}(v)\geq3e^{10u_q}/q$.  Hence
\begin{equation}
 v-\Delta\geq u_q.                                  \label{eq:upper-v-minus-delta-lower}
\end{equation}

We next show
\begin{equation}
 \mathcal C_{z'}\cap(v-\Delta,\infty)=\emptyset.
 \label{eq:upper-cutoff-exclusion}
\end{equation}
Suppose, to the contrary, that $u'\in\mathcal C_{z'}$ and
$u'>v-\Delta$.  Since \eqref{eq:upper-v-minus-delta-lower} holds, the defining upper-tail
condition in \eqref{eq:upper-threshold-class}, applied with
$w=v-\Delta<u'$, gives
\[
 G_{z'}(v-\Delta)\leq 3\frac{p(v-\Delta)}q.
\]
On the other hand, \eqref{eq:upper-global-obstruction} gives
\[
 G_{z'}^{\mathrm{small}}(v-\Delta)
 =p(v-\Delta)Q_{z'}(v-\Delta)
 >3\frac{p(v-\Delta)}q,
\]
and $G_{z'}(v-\Delta)\geq G_{z'}^{\mathrm{small}}(v-\Delta)$.  This is a
contradiction.  Therefore every $u'\in\mathcal C_{z'}$ satisfies
\begin{equation}
 u'\leq v-\Delta\leq v .
\label{eq:upper-cutoff-below-v}
\end{equation}
Therefore, \eqref{eq:upper-cutoff-below-v} is proved.

Now let $z'\in E_+^{\mathrm{small}}(r)\cup E_-^{\mathrm{small}}(r)$.  By
\eqref{eq:upper-small-radii-def}, there exists $u'\in\mathcal C_{z'}$ such
that
\[
 \big||z'|-ru'\big|\leq K_q.
\]
Together with \eqref{eq:upper-cutoff-below-v}, this gives
\begin{equation}
 |z'|\leq ru'+K_q
 \leq rv+K_q
 \leq |z_1|+2K_q+C.                                \label{eq:upper-crossing-radius}
\end{equation}
Here the last inequality follows from
\[
 rv=rv_1+r(v-v_1)\leq |z_1|+K_q+C,
\]
using $\big||z_1|-rv_1\big|\leq K_q$ from
\eqref{eq:upper-small-radii-def} and the bound
$r(v-v_1)\leq C$ proved above.

Let
\[
 a=\inf\{|z|:\ z\in E_+^{\mathrm{small}}(r)\cup E_-^{\mathrm{small}}(r)\}.
\]
The point $z_1$ was chosen with $|z_1|$ arbitrarily close to $a$.
Thus \eqref{eq:upper-crossing-radius} shows that
\[
 \{|z|:\ z\in E_+^{\mathrm{small}}(r)\cup E_-^{\mathrm{small}}(r)\}
 \subseteq [a,a+2K_q+C].
\]
By \eqref{eq:upper-small-radii-def},
\[
 E_+^{\mathrm{small}}(r)\subseteq [L_q,u_q],
 \qquad
 E_-^{\mathrm{small}}(r)\subseteq [-u_q,-L_q].
\]
On $E_+^{\mathrm{small}}(r)$, the map $z\mapsto |z|$ is the identity.
On $E_-^{\mathrm{small}}(r)$, it is the reflection $z\mapsto -z$.  Thus,
\[
 |E_\pm^{\mathrm{small}}(r)|
 =
 \big|\{|z|:\ z\in E_\pm^{\mathrm{small}}(r)\}\big|.
\]
As a result,
\[
 |E_+^{\mathrm{small}}(r)|+|E_-^{\mathrm{small}}(r)|
 \leq 2(2K_q+C)\leq C(K_q+1).
\]
This proves \eqref{eq:upper-small-coefficient-range}.

~\\
\noindent \textbf{Proof of \eqref{eq:upper-Q-large}.}
Put
\[
 R=12e^{10u_q},\qquad
 H_1=\log\left\{\frac{Q_{z_1}(v_1)\sqrt{1-b^2}}{2\eta}\right\}.
\]
The choice of $v_1$ in \eqref{eq:upper-small-radii-def}, together with
\eqref{eq:upper-small-coefficient-mass}, gives
\[
 Q_{z_1}(v_1)\geq\frac1{4q}.
\]
Also, \eqref{eq:upper-H1-lower} gives $H_1\geq u_q^2/3$.  Thus it is
enough to find $v\geq v_1$ such that
\[
 Q_{z_1}(v)\geq RQ_{z_1}(v_1),\qquad
 v-v_1\leq C\frac{v_1}{u_q}.
\]

For $z\in\mathbb R$ and $x\geq0$, define
\[
 \kappa_z(x)=
 \int_{\{|\alpha|<b\}}
 \frac{\phi\left(\frac{x-(\theta+\alpha z)}{\sqrt{1-\alpha^2}}\right)+
 \phi\left(\frac{x+(\theta+\alpha z)}{\sqrt{1-\alpha^2}}\right)}
 {2\phi(x)\sqrt{1-\alpha^2}}\,\dd\Pi(\theta,\alpha).
\]
By definition of $Q_z$ in \eqref{eq:upper-Qz-def},
\[
 Q_{z_1}(u)
 =
 \frac{\int_u^\infty 2\phi(x)\kappa_{z_1}(x)\,\dd x}
      {\int_u^\infty 2\phi(x)\,\dd x}.
\]
Using straightforward algebra,
\[
 Q_{z_1}'(x)=\lambda(x)\{Q_{z_1}(x)-\kappa_{z_1}(x)\},
 \qquad \lambda(x)=\phi(x)/\Phib(x).
\]
Define
\begin{equation}
 \tilde v=
 \inf\left\{x\geq v_1:\ 
 Q_{z_1}(x)\geq RQ_{z_1}(v_1)
 \ \text{or}\ 
 \kappa_{z_1}(x)\geq \frac12 Q_{z_1}(x)\right\}.
 \label{eq:upper-tilde-v-def}
\end{equation}
Before $\tilde v$, we have $\kappa_{z_1}(x)<Q_{z_1}(x)/2$, and therefore
\[
 Q_{z_1}'(x)
 \geq \frac12\lambda(x)Q_{z_1}(x)
 \geq \frac{x}{2}Q_{z_1}(x)
 \geq \frac{v_1}{2}Q_{z_1}(x).
\]
Thus
\[
 \bigl(\log Q_{z_1}\bigr)'(x)
 =\frac{Q_{z_1}'(x)}{Q_{z_1}(x)}
 \geq \frac{v_1}{2}.
\]
Let $T=v_1+2\log R/v_1$. If $\tilde v>T$, then
$(\log Q_{z_1})'(x)\geq v_1/2$ on $[v_1,T]$, so
\[
 \log\frac{Q_{z_1}(T)}{Q_{z_1}(v_1)}
 =\int_{v_1}^{T}(\log Q_{z_1})'(x)\,\dd x
 \geq\frac{v_1}{2}(T-v_1)=\log R.
\]
Thus $Q_{z_1}(T)\geq RQ_{z_1}(v_1)$, contradicting $T<\tilde v$
in \eqref{eq:upper-tilde-v-def}. Hence
\begin{equation}
 \tilde v\leq v_1+\frac{2\log R}{v_1}.              \label{eq:upper-tilde-v-upper}
\end{equation}
Continuity of $Q_{z_1}$ and $\kappa_{z_1}$ ensures that at least one
condition in \eqref{eq:upper-tilde-v-def} holds at $\tilde v$.

\indent Now we consider two cases depending on which inequality is binding in
\eqref{eq:upper-tilde-v-def}.
If
$Q_{z_1}(\tilde v)\geq RQ_{z_1}(v_1)$, take $v=\tilde v$.  Since
$v_1\geq u_q$ by \eqref{eq:upper-threshold-class},
\[
 \frac{\log R}{v_1}
 \leq C\frac{u_q}{v_1}
 \leq C\frac{v_1}{u_q},
\]
Together with \eqref{eq:upper-tilde-v-upper}, this gives
\begin{equation}
 \tilde v\leq v_1+C\frac{u_q}{v_1}
 \leq v_1\left(1+\frac{C}{u_q}\right).
 \label{eq:upper-tilde-v-relative}
\end{equation}
Then \eqref{eq:upper-Q-large} holds due to
\eqref{eq:upper-tilde-v-relative}.

It remains to consider the case
$\kappa_{z_1}(\tilde v)\geq Q_{z_1}(\tilde v)/2$.  Since $Q_{z_1}$ is
increasing on $[v_1,\tilde v]$, this gives
$\kappa_{z_1}(\tilde v)\geq Q_{z_1}(v_1)/2$.  We will show that
\eqref{eq:upper-Q-large} is satisfied with
\begin{equation}
 v=\tilde v+72\frac{\tilde v}{u_q}.
 \label{eq:upper-v-explicit-choice}
\end{equation}

For $z\in\mathbb R$ and $x\geq0$, define
\begin{equation}
 \widetilde\kappa_z(x)
 =\exp\left\{\frac{b^2x^2}{2(1-b^2)}\right\}\kappa_z(x).
 \label{eq:upper-tilde-kappa-def}
\end{equation}
For a fixed pair $(\theta,\alpha)$ with $|\alpha|<b$, the corresponding
integrand in $\kappa_{z_1}(x)$ is
\[
\begin{aligned}
&\frac{1}{2\phi(x)\sqrt{1-\alpha^2}}
\left\{\phi\left(\frac{x-(\theta+\alpha z_1)}{\sqrt{1-\alpha^2}}\right)
      +\phi\left(\frac{x+(\theta+\alpha z_1)}{\sqrt{1-\alpha^2}}\right)\right\}\\
&\quad
=\frac1{2\sqrt{1-\alpha^2}}\left[
\exp\left\{-\frac{\{x-(\theta+\alpha z_1)\}^2}{2(1-\alpha^2)}
             +\frac{x^2}{2}\right\}\right.\\
&\hspace{31mm}\left.
+\exp\left\{-\frac{\{x+(\theta+\alpha z_1)\}^2}{2(1-\alpha^2)}
             +\frac{x^2}{2}\right\}
\right]                                             \\
&\quad
=\frac1{\sqrt{1-\alpha^2}}
\exp\left\{-\frac{\alpha^2x^2}{2(1-\alpha^2)}
            -\frac{(\theta+\alpha z_1)^2}{2(1-\alpha^2)}\right\}
\cosh\left(\frac{(\theta+\alpha z_1)x}{1-\alpha^2}\right).
\end{aligned}
\]
Multiplying by the factor in \eqref{eq:upper-tilde-kappa-def}, the
corresponding integrand in $\widetilde\kappa_{z_1}(x)$ is denoted by
$f_{\theta,\alpha}(x)$, where
\begin{equation}
\begin{aligned}
f_{\theta,\alpha}(x)
&=
\frac1{\sqrt{1-\alpha^2}}
 \exp\left\{-\frac{(\theta+\alpha z_1)^2}{2(1-\alpha^2)}\right\}
 \exp\left\{
 \left(\frac{b^2}{2(1-b^2)}
       -\frac{\alpha^2}{2(1-\alpha^2)}\right)x^2
 \right\} \\
&\quad\times
 \cosh\left(\frac{(\theta+\alpha z_1)x}{1-\alpha^2}\right).
\end{aligned}
\label{eq:upper-tilde-kappa-integrand}
\end{equation}
The first two factors are positive and independent of $x$.  The coefficient of
$x^2$ in the second term is
\[
 a=\frac{b^2}{2(1-b^2)}-\frac{\alpha^2}{2(1-\alpha^2)}
 =\frac{b^2-\alpha^2}{2(1-b^2)(1-\alpha^2)}\geq0,
\]
because $|\alpha|<b$.  Thus, taking logarithms in
\eqref{eq:upper-tilde-kappa-integrand} and dropping the additive constant
independent of $x$, the logarithm of the integrand has the form
\[
 a x^2+\log\cosh(cx),
 \qquad c=\frac{\theta+\alpha z_1}{1-\alpha^2}.
\]
On
$[0,\infty)$,
\[
\begin{aligned}
 \frac{d}{dx}\{a x^2+\log\cosh(cx)\}
 &=2ax+c\tanh(cx)\\
 &=2ax+|c|\tanh(|c|x)\geq0,\\
\frac{d^2}{dx^2}\{a x^2+\log\cosh(cx)\}
&=2a+c^2\sech^2(cx)\geq0.
\end{aligned}
\]
Thus $f_{\theta,\alpha}$ is log-convex.

To pass from each integrand to the mixture, fix $0\leq t\leq1$ and
$x,y\geq0$.  Log-convexity gives
\[
 f_{\theta,\alpha}\{t x+(1-t)y\}
 \leq f_{\theta,\alpha}(x)^t f_{\theta,\alpha}(y)^{1-t}.
\]
After integrating over $\{|\alpha|<b\}$, H\"older's inequality gives
\[
\begin{aligned}
 \widetilde\kappa_{z_1}\{t x+(1-t)y\}
 &\leq
 \int_{\{|\alpha|<b\}}
 f_{\theta,\alpha}(x)^t f_{\theta,\alpha}(y)^{1-t}
 \,\dd\Pi(\theta,\alpha)\\
 &\leq
 \left\{\int_{\{|\alpha|<b\}} f_{\theta,\alpha}(x)
 \,\dd\Pi(\theta,\alpha)\right\}^t
 \left\{\int_{\{|\alpha|<b\}} f_{\theta,\alpha}(y)
 \,\dd\Pi(\theta,\alpha)\right\}^{1-t}\\
 &=
 \widetilde\kappa_{z_1}(x)^t
 \widetilde\kappa_{z_1}(y)^{1-t}.
\end{aligned}
\]
Hence $\widetilde\kappa_{z_1}$ is log-convex.  Equivalently,
\begin{equation}
 x\mapsto \log\kappa_{z_1}(x)+\frac{b^2x^2}{2(1-b^2)}\quad\text{is convex on }[0,\infty).              \label{eq:upper-kappa-adjusted-convex}
\end{equation}
Fix $M<\infty$ and restrict $0\leq x\leq M$.  From
\eqref{eq:upper-tilde-kappa-integrand}, for a constant $C_M<\infty$,
\begin{equation}
0\leq f_{\theta,\alpha}(x)\leq C_M\exp\left\{-\frac{(\theta+\alpha z_1)^2}{2(1-\alpha^2)}+\frac{M|\theta+\alpha z_1|}{1-\alpha^2}\right\}\leq C_M.
\label{eq:upper-f-compact-bound}
\end{equation}
The last inequality follows from
\[
 -\frac{(\theta+\alpha z_1)^2}{2(1-\alpha^2)}
 +\frac{M|\theta+\alpha z_1|}{1-\alpha^2}
 =
 -\frac{\{|\theta+\alpha z_1|-M\}^2}{2(1-\alpha^2)}
 +\frac{M^2}{2(1-\alpha^2)}
 \leq \frac{M^2}{2(1-b^2)}.
\]
Differentiating the integrand gives
\[
\frac{\dd}{\dd x}f_{\theta,\alpha}(x)=f_{\theta,\alpha}(x)\left[2\left\{\frac{b^2}{2(1-b^2)}-\frac{\alpha^2}{2(1-\alpha^2)}\right\}x+\frac{\theta+\alpha z_1}{1-\alpha^2}\tanh\left\{\frac{(\theta+\alpha z_1)x}{1-\alpha^2}\right\}\right].
\]
The bracketed factor is controlled by $1+|\theta+\alpha z_1|$.  Indeed,
on $0\leq x\leq M$,
\[
\left|2\left\{\frac{b^2}{2(1-b^2)}-\frac{\alpha^2}{2(1-\alpha^2)}\right\}x+\frac{\theta+\alpha z_1}{1-\alpha^2}\tanh\left\{\frac{(\theta+\alpha z_1)x}{1-\alpha^2}\right\}\right|
\leq C_M\{1+|\theta+\alpha z_1|\},
\]
because $|\tanh|\leq1$, $1-\alpha^2\geq1-b^2$, and $|\alpha|<b$.
Combining this with \eqref{eq:upper-f-compact-bound} gives
\[
\left|\frac{\dd}{\dd x}f_{\theta,\alpha}(x)\right|
\leq C_M\{1+|\theta+\alpha z_1|\}
\exp\left\{-\frac{(\theta+\alpha z_1)^2}{2(1-\alpha^2)}
          +\frac{M|\theta+\alpha z_1|}{1-\alpha^2}\right\}.
\]
Moreover,
\[
\begin{aligned}
&\{1+|\theta+\alpha z_1|\}
\exp\left\{-\frac{(\theta+\alpha z_1)^2}{2(1-\alpha^2)}
          +\frac{M|\theta+\alpha z_1|}{1-\alpha^2}\right\}\\
&\qquad =
\{1+|\theta+\alpha z_1|\}
\exp\left\{-\frac{\{|\theta+\alpha z_1|-M\}^2}{2(1-\alpha^2)}
          +\frac{M^2}{2(1-\alpha^2)}\right\}
\leq C_M,
\end{aligned}
\]
uniformly in $(\theta,\alpha)$ with $|\alpha|<b$, because
$1-\alpha^2\in[1-b^2,1]$.  Therefore
\[
 \sup_{0\leq x\leq M}
 \left|\frac{\dd}{\dd x}f_{\theta,\alpha}(x)\right|
 \leq C_M.
\]
Thus, on each compact interval, both $f_{\theta,\alpha}$ and
$\dd f_{\theta,\alpha}/\dd x$ are dominated by an integrable bound with
respect to the finite measure $\Pi$.  Hence $\widetilde\kappa_{z_1}$, and
therefore $\kappa_{z_1}$, is differentiable on $[0,\infty)$.

When $x=0$,
\[
\begin{aligned}
 \kappa_{z_1}(0)
 &=
 \int_{\{|\alpha|<b\}}
 \frac{\phi\left(\frac{\theta+\alpha z_1}{\sqrt{1-\alpha^2}}\right)}
      {\phi(0)\sqrt{1-\alpha^2}}\,\dd\Pi(\theta,\alpha)\\
 &\leq
 \int_{\{|\alpha|<b\}}\frac1{\sqrt{1-\alpha^2}}\,\dd\Pi(\theta,\alpha)
 \leq \frac{\eta}{\sqrt{1-b^2}}.
\end{aligned}
\]
Together with $\kappa_{z_1}(\tilde v)\geq Q_{z_1}(v_1)/2$, this gives
\[
 \frac{\kappa_{z_1}(\tilde v)}{\kappa_{z_1}(0)}
 \geq
 \frac{Q_{z_1}(v_1)\sqrt{1-b^2}}{2\eta}
 =e^{H_1},
\]
by the definition of $H_1$.  By
\eqref{eq:upper-kappa-adjusted-convex}, the derivative at $\tilde v$ is at
least the secant slope from $0$ to $\tilde v$:
\[
\begin{aligned}
 \frac{d}{dx}\left\{
 \log\kappa_{z_1}(x)+\frac{b^2x^2}{2(1-b^2)}
 \right\}\bigg|_{x=\tilde v}
 &\geq
 \frac{\log\kappa_{z_1}(\tilde v)-\log\kappa_{z_1}(0)
       +b^2\tilde v^2/\{2(1-b^2)\}}{\tilde v}\\
 &\geq \frac{H_1}{\tilde v}.
\end{aligned}
\]
The derivative of the convex function in
\eqref{eq:upper-kappa-adjusted-convex} is nondecreasing.

By \eqref{eq:upper-tilde-v-relative}, \eqref{eq:upper-ru-upper}, and
\eqref{eq:upper-H1-lower}, we have
$\tilde v\leq v_1+C u_q/v_1$, $bv_1\leq1+K_q/u_q$, and
$H_1\geq u_q^2/3$.  Since $v_1\geq u_q$, the first two bounds imply
\[
 b\tilde v
 \leq bv_1\left(1+\frac{C}{u_q}\right)
 \leq\left(1+\frac{K_q}{u_q}\right)\left(1+\frac{C}{u_q}\right)
 \leq 2
\]
after decreasing $q_0$, if necessary.  Also, if
$\tilde v\leq x\leq \tilde v+72\tilde v/u_q+1$, then $x\leq2\tilde v$.
Therefore, using $b\tilde v\leq2$ and $b\leq u_q^{-1}$,
\[
 \frac{b^2x\tilde v}{1-b^2}
 \leq \frac{2b^2\tilde v^2}{1-b^2}
 \leq C.
\]
Because $H_1\geq u_q^2/3$, decreasing $q_0$ once more makes this constant
at most $H_1/2$.  Thus,
\[
 \frac{b^2x\tilde v}{1-b^2}\leq\frac{H_1}{2}
 \qquad
 \left(\tilde v\leq x\leq \tilde v+72\frac{\tilde v}{u_q}+1\right).
\]
Hence, on this interval,
\begin{equation}
(\log\kappa_{z_1})'(x)\geq \frac{H_1}{\tilde v}-\frac{b^2x}{1-b^2}
\geq\frac{H_1}{2\tilde v}.
\label{eq:upper-kappa-log-derivative-lower}
\end{equation}
For $v$ defined in \eqref{eq:upper-v-explicit-choice},
\[
\begin{aligned}
 \log\frac{\kappa_{z_1}(v)}{\kappa_{z_1}(\tilde v)}
 &=
 \int_{\tilde v}^v(\log\kappa_{z_1})'(x)\,\dd x
 \geq \int_{\tilde v}^v\frac{H_1}{2\tilde v}\,\dd x\\
 &=\frac{H_1}{2\tilde v}(v-\tilde v)
 =\frac{H_1}{2\tilde v}\,72\frac{\tilde v}{u_q}
 =\frac{36H_1}{u_q}.
\end{aligned}
\]
Thus,
\begin{equation}
 \kappa_{z_1}(v)
 \geq \kappa_{z_1}(\tilde v)
 \exp\left\{\frac{36H_1}{u_q}\right\}
 \geq \frac{Q_{z_1}(v_1)}{2}
 \exp\left\{\frac{36H_1}{u_q}\right\}.
\label{eq:upper-kappa-v-growth}
\end{equation}
Since $H_1\geq u_q^2/3$, after decreasing $q_0$, if necessary,
\begin{equation}
 \frac{1-e^{-1}}2
 \exp\left\{\frac{36H_1}{u_q}\right\}
 \geq
 \frac{1-e^{-1}}2 e^{12u_q}
 \geq 12e^{10u_q}
 =R.
\label{eq:upper-kappa-growth-constant}
\end{equation}
Also, $v\geq\tilde v\geq v_1\geq u_q$, so $v^{-1}\leq1$ after
decreasing $q_0$, if necessary.  By \eqref{eq:upper-v-explicit-choice},
\[
 [v,v+v^{-1}]
 \subseteq
 \left[\tilde v,\tilde v+72\frac{\tilde v}{u_q}+1\right].
\]
The lower bound \eqref{eq:upper-kappa-log-derivative-lower} therefore gives
\[
 (\log\kappa_{z_1})'(x)\geq0,\qquad v\leq x\leq v+v^{-1},
\]
and hence $\kappa_{z_1}$ is nondecreasing on $[v,v+v^{-1}]$.  By the
definition of $Q_{z_1}$,
\[
\begin{aligned}
 Q_{z_1}(v)
 &\geq
 \frac{\int_v^{v+v^{-1}}2\phi(x)\kappa_{z_1}(x)\,\dd x}
      {2\Phib(v)}\\
 &\geq
 \kappa_{z_1}(v)
 \frac{\Phib(v)-\Phib(v+v^{-1})}{\Phib(v)}\\
\end{aligned}
\]
Moreover, by \eqref{eq:mills-hazard} of Lemma~\ref{lem:mills},
\begin{equation}
 \frac{\Phib(v+v^{-1})}{\Phib(v)}
 =
 \exp\left\{-\int_v^{v+v^{-1}}\lambda(t)\,\dd t\right\}
 \leq
 \exp\left\{-\int_v^{v+v^{-1}}t\,\dd t\right\}
 \leq e^{-1}.
\label{eq:upper-short-tail-ratio}
\end{equation}
Therefore
\[
 Q_{z_1}(v)
 \geq
 (1-e^{-1})\kappa_{z_1}(v)
 \geq RQ_{z_1}(v_1),
\]
where the first inequality uses \eqref{eq:upper-short-tail-ratio}, and the
second uses \eqref{eq:upper-kappa-v-growth} and
\eqref{eq:upper-kappa-growth-constant}.
Finally, by \eqref{eq:upper-v-explicit-choice} and
\eqref{eq:upper-tilde-v-relative},
\[
\begin{aligned}
 v-v_1
 &=(\tilde v-v_1)+72\frac{\tilde v}{u_q}\\
 &\leq C\frac{u_q}{v_1}
   +72\frac{v_1}{u_q}\left(1+\frac{C}{u_q}\right).
\end{aligned}
\]
Since $v_1\geq u_q$ from $v_1\in\mathcal C_{z_1}$ and
\eqref{eq:upper-threshold-class},
\[
 \frac{u_q}{v_1}\leq\frac{v_1}{u_q},
 \qquad
 72\frac{v_1}{u_q}\left(1+\frac{C}{u_q}\right)
 \leq C\frac{v_1}{u_q},
\]
after increasing $C$ and decreasing $q_0$, if necessary.  Therefore
\[
 v-v_1\leq C\frac{v_1}{u_q}.
\]
Thus $v$ defined in \eqref{eq:upper-v-explicit-choice} satisfies
\eqref{eq:upper-Q-large}.
\end{proof}

The following lemma is the deterministic input needed for the good-event
part of the finite BH proof.
\begin{lemma}\label{lem:upper-crossing}
There are universal constants $C<\infty$ and $q_0>0$ with the following property.
Let $\Pi$, $\varepsilon$, and $G_z$ be as in
\eqref{eq:upper-mixture}.  Let $m\geq1$ and $J\geq2$.  Define
\begin{equation}
 t_k=\frac{qk}{m},\qquad u_k=p^{-1}(t_k).            \label{eq:upper-rank-grid}
\end{equation}
For each $z$, let $w_k(z)$, $J<k\leq m$, be nonnegative measurable weights satisfying
\[
 \sum_{k>J}w_k(z)\leq1.
\]
and
\begin{equation}
 G_z(u_k)\geq\frac{k}{2m},\qquad
 G_z(u_j)\leq\frac{2j}{m}\quad(j > k)\,\, \text{if }w_k(z) > 0.              \label{eq:upper-rank-weight-conditions}
\end{equation}
Then, whenever $q\leq q_0$, uniformly over $m,J,\Pi$, the weights
$(w_k(z))$, and $0\leq r\leq1$,
\[
\int_{-u_q}^{u_q}\phi(z)
\sum_{k>J}w_k(z)\rho_r(u_k,z)\dd z
\leq \frac{u_q}{2\sqrt{2\pi}}+C\sqrt{u_q}.
\]
\end{lemma}

\begin{proof}[Proof of Lemma~\ref{lem:upper-crossing}]
For each $z$, put
\[
 \mathcal C_z=\{u_k:\ J<k\leq m,\ w_k(z)>0\}.
\]
If $u_k\in\mathcal C_z$, then the first condition in
\eqref{eq:upper-rank-weight-conditions} gives
\begin{equation}
 G_z(u_k)\geq \frac{k}{2m}=\frac{p(u_k)}{2q}.
 \label{eq:upper-rank-self-bound}
\end{equation}
For $u_q\leq v<u_k$, let $j=\lceil mp(v)/q\rceil$.  Then
$j>k$, $u_j\leq v$, and by monotonicity of $G_z$,
\[
 G_z(v)\leq G_z(u_j)\leq\frac{2j}{m}
 \leq2\left(1+\frac1J\right)\frac{p(v)}q
 \leq3\frac{p(v)}q,
\]
where $J\geq2$.  Thus $\mathcal C_z$ satisfies \eqref{eq:upper-threshold-class}.  Also,
since the weights are nonnegative and sum to at most one,
\[
 \sum_{k>J}w_k(z)\rho_r(u_k,z)
 \leq \sup_{u\in\mathcal C_z}\rho_r(u,z),
\]
with the right side interpreted as zero when $\mathcal C_z$ is empty.
It remains to prove
\begin{equation}
 \int_{-u_q}^{u_q}\phi(z)\sup_{u\in\mathcal C_z}\rho_r(u,z)\dd z
 \leq \frac{u_q}{2\sqrt{2\pi}}+C\sqrt{u_q}.     \label{eq:upper-crossing-target}
\end{equation}

If $r=1$, then Lemma~\ref{lem:upper-null-ratio} gives
\[
 \int_{-u_q}^{u_q}\phi(z)\sup_{u\in\mathcal C_z}\rho_1(u,z)\dd z
 \leq
 \int_{-u_q}^{u_q}\phi(z)\sup_{u\geq u_q}\rho_1(u,z)\dd z
 =0.
\]
This proves the desired bound in this case.

Next suppose $3/5\leq r<1$.  Since
$(1-r)/\sqrt{1-r^2}\leq1/2$, Lemma~\ref{lem:upper-null-ratio} gives
\begin{equation}
 \int_{-u_q}^{u_q}\phi(z)\sup_{u\geq u_q}\rho_r(u,z)\dd z
 \leq\frac12+\frac{u_q}{2\sqrt{2\pi}}
 \leq\frac{u_q}{2\sqrt{2\pi}}+C\sqrt{u_q}.       \label{eq:upper-crossing-large-r}
\end{equation}
This upper-bounds the smaller supremum over $\mathcal C_z$
and proves the desired bound in this range.

It remains to consider $0\leq r<3/5$.  For $r=0$, the integral is at
most $1-q$, which is bounded by the displayed right side after increasing
$C$.  Hence assume $0<r<3/5$.  Use $L_q,K_q$ defined in
\eqref{eq:upper-KLq-def}.
When $q$ is sufficiently small, \eqref{eq:upper-KLq-def} implies $L_q<u_q$.
We will consider the following decomposition of \eqref{eq:upper-crossing-target}:
\begin{equation}
\begin{aligned}
&\int_{-u_q}^{u_q}\phi(z)\sup_{u\in\mathcal C_z}\rho_r(u,z)\dd z\\
&\leq
\int_{|z|<L_q}\phi(z)
     \sup_{u\in\mathcal C_z}\rho_r(u,z)\dd z\\
&\quad+
\int_{L_q\leq |z|\leq u_q}\phi(z)
 \sup_{\substack{u\in\mathcal C_z:\\ \big||z|-ru\big|>K_q}}
 \rho_r(u,z)\dd z\\
&\quad+
\int_{L_q\leq |z|\leq u_q}\phi(z)
 \sup_{\substack{u\in\mathcal C_z:\\ \big||z|-ru\big|\leq K_q}}
 \rho_r(u,z)\dd z .
\end{aligned}
\label{eq:upper-crossing-decomposition}
\end{equation}
All empty suprema in \eqref{eq:upper-crossing-decomposition} are interpreted as zero.

\indent By construction, every $u\in\mathcal C_z$ satisfies $u\geq u_q$.  When
$|z|< L_q$, Lemma~\ref{lem:upper-localization}
gives
\[
 \phi(z)\rho_r(u,z)
 \leq C\left[
 e^{-(z-ru)^2/\{2(1-r^2)\}}
 +e^{-(z+ru)^2/\{2(1-r^2)\}}\right]
 \leq C
\]
uniformly over $u\in\mathcal C_z$.  Taking the supremum over
$\mathcal C_z$, with value zero when $\mathcal C_z$ is empty, and then
integrating over a set of length at most $2L_q$ gives
\begin{equation}
 \int_{|z|<L_q}\phi(z)
     \sup_{u\in\mathcal C_z}\rho_r(u,z)\dd z
 \leq CL_q.                                      \label{eq:upper-small-z-integral}
\end{equation}
On $L_q\leq|z|\leq u_q$, if $u\in\mathcal C_z$ and
$\big||z|-ru\big|>K_q$, then
\[
 \min\{|z-ru|,|z+ru|\}=\big||z|-ru\big|>K_q.
\]
Therefore \eqref{eq:upper-localization} in Lemma~\ref{lem:upper-localization}
gives
\[
 \phi(z)\rho_r(u,z)
 \leq
 C\exp\left\{-\frac{K_q^2}{2(1-r^2)}\right\}
 \leq C e^{-K_q^2/2}.
\]
Taking the supremum over such $u$, with value zero if there is no such
$u$, and integrating over a set of length at most $2u_q$, gives
\begin{equation}
 \int_{L_q\leq |z|\leq u_q}\phi(z)
 \sup_{\substack{u\in\mathcal C_z:\\ \big||z|-ru\big|>K_q}}
 \rho_r(u,z)\dd z
 \leq C u_qe^{-K_q^2/2}
 =O(u_q^{-3}).                                    \label{eq:upper-away-from-localization}
\end{equation}
where we use the definition $K_q=\sqrt{8\log u_q}$ in
\eqref{eq:upper-KLq-def}.

\indent Now consider the remaining term in \eqref{eq:upper-crossing-decomposition}.  For any contributing
pair, $|z|\in[L_q,u_q]$ and $\big||z|-ru\big|\leq K_q$.  Since
$u\in\mathcal C_z$,
\[
 G_z^{\mathrm{large}}(u)+G_z^{\mathrm{small}}(u)
 =G_z(u)\geq\frac{p(u)}{2q}.
\]
Thus
\[
 G_z^{\mathrm{large}}(u)\geq\frac{p(u)}{4q}
 \quad\text{or}\quad
 G_z^{\mathrm{small}}(u)\geq\frac{p(u)}{4q}.
\]
Thus,
\[
 z\in E_{\operatorname{sgn}(z)}^{\mathrm{large}}(r)
       \cup E_{\operatorname{sgn}(z)}^{\mathrm{small}}(r),
\]
and the last integral in \eqref{eq:upper-crossing-decomposition} satisfies
\[
\begin{aligned}
&\int_{L_q\leq |z|\leq u_q}\phi(z)
 \sup_{\substack{u\in\mathcal C_z:\\ \big||z|-ru\big|\leq K_q}}
 \rho_r(u,z)\dd z\\
&\leq
\int_{z\in E_+^{\mathrm{large}}(r)\cup E_-^{\mathrm{large}}(r)}
\phi(z)
 \sup_{\substack{u\in\mathcal C_z:\\ \big||z|-ru\big|\leq K_q}}
 \rho_r(u,z)\dd z\\
&\quad+
\int_{z\in E_+^{\mathrm{small}}(r)\cup E_-^{\mathrm{small}}(r)}
\phi(z)
 \sup_{\substack{u\in\mathcal C_z:\\ \big||z|-ru\big|\leq K_q}}
 \rho_r(u,z)\dd z .
\end{aligned}
\]
Lemma~\ref{lem:upper-large-coefficients} gives
\[
 |E_+^{\mathrm{large}}(r)|+|E_-^{\mathrm{large}}(r)|
 \leq(1-r)u_q+C\sqrt{u_q}.
\]
Lemma~\ref{lem:upper-small-coefficients}
gives
\[
 |E_+^{\mathrm{small}}(r)|+|E_-^{\mathrm{small}}(r)|
 \leq C(K_q+1)\leq C\sqrt{u_q}.
\]
Combining the two bounds, the total combined length of the corresponding
aligned factor values is at most
\begin{equation}
 (1-r)u_q+C\sqrt{u_q}.                                \label{eq:upper-combined-length}
\end{equation}
Combining \eqref{eq:upper-localization-quantitative} in
Lemma~\ref{lem:upper-localization} and \eqref{eq:upper-combined-length}, and
using $0<r<3/5$, hence $(1-r^2)^{-1/2}\leq5/4$, we obtain
\begin{align*}
&\int_{L_q\leq |z|\leq u_q}\phi(z)
 \sup_{\substack{u\in\mathcal C_z:\\ \big||z|-ru\big|\leq K_q}}
 \rho_r(u,z)\dd z\\
&\leq
 \left\{\frac{1+C(K_q+1)/u_q}{2\sqrt{2\pi}\sqrt{1-r^2}}
       +Ce^{-u_q}\right\}
       \left\{(1-r)u_q+C\sqrt{u_q}\right\}\\
&\leq
 \frac{1-r}{2\sqrt{1-r^2}\sqrt{2\pi}}u_q
 +C\frac{K_q+1+\sqrt{u_q}}{\sqrt{1-r^2}}
 +C u_qe^{-u_q}\\
&\leq
 \frac{1-r}{2\sqrt{1-r^2}\sqrt{2\pi}}u_q
 +C\{K_q+1+\sqrt{u_q}+u_qe^{-u_q}\}.
\end{align*}
Here the middle line expands the product and absorbs the term
$(K_q+1)/\sqrt{u_q}$ into $K_q+1$.  Since $L_q=K_q+\sqrt{u_q}$,
$K_q=O(\sqrt{\log u_q})$, and $u_q e^{-u_q}$ is negligible, combining this with
\eqref{eq:upper-crossing-decomposition}, \eqref{eq:upper-small-z-integral}, and
\eqref{eq:upper-away-from-localization} yields
\begin{equation}
 \int_{-u_q}^{u_q}\phi(z)\sup_{u\in\mathcal C_z}\rho_r(u,z)\dd z
 \leq\frac{1-r}{2\sqrt{1-r^2}\sqrt{2\pi}}u_q+C\sqrt{u_q}
 \leq\frac{u_q}{2\sqrt{2\pi}}+C\sqrt{u_q},       \label{eq:upper-crossing-small-r}
\end{equation}
where the last inequality uses
$(1-r)/\sqrt{1-r^2}=\sqrt{(1-r)/(1+r)}\leq1$.
This proves Lemma~\ref{lem:upper-crossing}.
\end{proof}

The next lemma converts observed rejection counts into bounds for their
conditional means.
\begin{lemma}\label{lem:upper-rank}
There are universal constants $C,c>0$ with the following property.
Let $J\geq1$, and let $N_j$ be Poisson-binomial with mean
$\mu_j$; the counts may be nested in $j$.  For $j\geq J$, define the
bad events
\begin{align}
\mathcal B_j^+&=\{N_j\geq j-1,\ \mu_j<j/2\},\label{eq:upper-rank-upper}\\
\mathcal B_j^-&=\{N_j\leq j-2,\ \mu_j>2j\}. \label{eq:upper-rank-lower}
\end{align}
Then
\[
 \mathbb P\left(\bigcup_{j\geq J}(\mathcal B_j^+\cup\mathcal B_j^-)\right)
 \leq Ce^{-cJ}.
\]
The constants are universal and the bound is uniform in the number and
success probabilities of the Bernoulli variables.
\end{lemma}

\begin{proof}
If $\mu_j<j/2$, the Chernoff upper-tail inequality bounds
$\mathbb P(\mathcal B_j^+)=\mathbb P(N_j\geq j-1)$ by
$C_0e^{-c_0 j}$; if $\mu_j\geq j/2$, then $\mathcal B_j^+$ is empty.
Similarly, if $\mu_j>2j$, the Chernoff lower-tail inequality bounds
$\mathbb P(\mathcal B_j^-)=\mathbb P(N_j\leq j-2)$ by $C_0e^{-c_0 j}$,
while if $\mu_j\leq2j$, then $\mathcal B_j^-$ is empty.  Enlarging
$C_0$, if necessary, absorbs the finitely many small values of $j$.
Sum these bounds over $j\geq J$.
\end{proof}

\begin{proof}[Proof of Theorem~\ref{thm:common-factor-upper}~(b)]
If $m_0=0$, then $\FDR(\BH_q)=0$.  Hence assume $m_0>0$.
Let $R_i$ be the BH rejection count after replacing the true-null $p$-value $P_i$ by zero, as in the proof of Lemma~\ref{lem:conditional-fdp-bound}.  For every hypothesis $\ell$, define
\[
 F_{\ell,z}(t)=\mathbb P(P_\ell\leq t\mid Z=z),\qquad
 t_k=\frac{qk}{m},\qquad u_k=p^{-1}(t_k).
\]
The leave-one-out identity \eqref{eq:loo-identity} and the same conditional-independence argument give, for almost every $z$,
\begin{align}
 \FDR(z)
 &=\frac qm\sum_{i\in\mathcal H_0}\sum_{k=1}^m
   \frac{F_{i,z}(t_k)}{t_k}
   \mathbb P(R_i=k\mid Z=z) \notag\\
 &=\frac qm\sum_{i\in\mathcal H_0}\sum_{k=1}^m
   \rho_{|a_i|}(u_k,z)
   \mathbb P(R_i=k\mid Z=z).           \label{eq:upper-fdr-rank}
\end{align}
Thus $\FDR=\int_{\mathbb R}\FDR(z)\phi(z)\dd z$.
The second equality follows from \eqref{eq:upper-null-tail-ratio}.
Let
\[
 A_q=\{|Z|>u_q\}.
\]
Decompose
\[
 \FDR
 =\mathbb E\{\FDR(Z)\,\mathbf1_{A_q}\}
  +\mathbb E\{\FDR(Z)\,\mathbf1_{A_q^c}\}.
\]
The first term is at most $q$:
\[
 \mathbb E\{\FDR(Z)\,\mathbf1_{A_q}\}
 \leq \mathbb P(A_q)
 =2\Phib(u_q)
 =p(u_q)
 =q,
\]
because $0\leq\FDR(Z)\leq1$ and $u_q=p^{-1}(q)$.
It remains to prove
\begin{equation}
 \mathbb E\{\FDR(Z)\,\mathbf1_{A_q^c}\}
 \leq
 \pi_0q\left\{\frac{u_q}{2\sqrt{2\pi}}+C\sqrt{u_q}\right\}.
 \label{eq:upper-central-target}
\end{equation}
Define
\[
 J=\lceil\sqrt{u_q}\rceil.
\]
Then $J\geq2$ when $q$ is sufficiently small.  We split the summands in
\eqref{eq:upper-central-target} into two parts.  It suffices to prove
\begin{equation}
 \begin{aligned}
 &\int_{A_q^c}\frac qm\sum_{i\in\mathcal H_0}\sum_{1\leq k\leq J}
 \rho_{|a_i|}(u_k,z)\mathbb P(R_i=k\mid Z=z)\phi(z)\dd z \\
 &\qquad\leq \pi_0qJ
 \leq\pi_0q(\sqrt{u_q}+1),
 \end{aligned}                                      \label{eq:upper-small-rank-target}
\end{equation}
and
\begin{equation}
 \begin{aligned}
 &\int_{A_q^c}\frac qm\sum_{i\in\mathcal H_0}\sum_{k>J}
 \rho_{|a_i|}(u_k,z)\mathbb P(R_i=k\mid Z=z)\phi(z)\dd z \\
 &\qquad\leq
 \pi_0q\left\{\frac{u_q}{2\sqrt{2\pi}}+C\sqrt{u_q}\right\}.
 \end{aligned}                                      \label{eq:upper-large-rank-target}
\end{equation}

We first prove \eqref{eq:upper-small-rank-target}.  Its left-hand side is
bounded directly from \eqref{eq:upper-fdr-rank}.  Using
\eqref{eq:upper-rho-normalization} with $u=u_k$,
$\mathbf1_{A_q^c}\leq1$, and
$\mathbb P(R_i=k\mid Z=z)\leq1$, it is at most
\[
 \frac qm\sum_{i\in\mathcal H_0}\sum_{1\leq k\leq J}1
 =\pi_0qJ
 \leq\pi_0q(\sqrt{u_q}+1).
\]

We next prove \eqref{eq:upper-large-rank-target}.  For each $i$ and
$z$, and for $1\leq j\leq m$, let
\begin{equation}
 N_{i,j}=\sum_{\ell\ne i}\mathbf1\{P_\ell\leq qj/m\},
 \qquad
 \mu_{i,j}(z)=\mathbb E(N_{i,j}\mid Z=z).        \label{eq:upper-counts}
\end{equation}
Define the good event corresponding to
\eqref{eq:upper-rank-upper}-\eqref{eq:upper-rank-lower} as follows.  Let
\[
 \mathcal B_{i,j}^+(z)=\{N_{i,j}\geq j-1,\ \mu_{i,j}(z)<j/2\},\qquad
 \mathcal B_{i,j}^-(z)=\{N_{i,j}\leq j-2,\ \mu_{i,j}(z)>2j\},
\]
and set
\begin{equation}
 \mathcal A_{i,z}
 :=
 \bigcap_{j=J}^m
 \left((\mathcal B_{i,j}^+(z))^c\cap(\mathcal B_{i,j}^-(z))^c\right).
 \label{eq:upper-good-event}
\end{equation}
We split the conditional probability in the left-hand side of
\eqref{eq:upper-large-rank-target} according to this event:
\[
 \mathbb P(R_i=k\mid Z=z)
 =\mathbb P\{R_i=k,\mathcal A_{i,z}\mid Z=z\}
  +\mathbb P\{R_i=k,\mathcal A_{i,z}^c\mid Z=z\}.
\]
It is enough to prove the bad-event bound
\begin{equation}
 \begin{aligned}
 &\int_{A_q^c}\frac qm\sum_{i\in\mathcal H_0}\sum_{k>J}
 \rho_{|a_i|}(u_k,z)\mathbb P\{R_i=k,\mathcal A_{i,z}^c\mid Z=z\}
 \phi(z)\dd z \\
 &\qquad\leq C\pi_0q,
 \end{aligned}
 \label{eq:upper-large-rank-bad-target}
\end{equation}
and the good-event bound
\begin{equation}
 \begin{aligned}
 &\int_{A_q^c}\frac qm\sum_{i\in\mathcal H_0}\sum_{k>J}
 \rho_{|a_i|}(u_k,z)\mathbb P\{R_i=k,\mathcal A_{i,z}\mid Z=z\}
 \phi(z)\dd z \\
 &\qquad\leq
 \pi_0q\left\{\frac{u_q}{2\sqrt{2\pi}}+C\sqrt{u_q}\right\}.
 \end{aligned}
 \label{eq:upper-large-rank-good-target}
\end{equation}

We first prove the bad-event bound \eqref{eq:upper-large-rank-bad-target}.
Set $\delta_J=Ce^{-cJ}$.  Fix $i$ and $z$, and condition on
$Z=z$.  The residuals of the hypotheses $\ell\ne i$ are then
independent, so the indicators in \eqref{eq:upper-counts} are independent
Bernoulli random variables, with success probabilities depending on
$\ell$, $j$, and $z$.  Hence each $N_{i,j}$ is Poisson-binomial
with mean $\mu_{i,j}(z)$, and the family may be nested in $j$, exactly as
allowed in Lemma~\ref{lem:upper-rank}.  Moreover,
$\mathcal A_{i,z}^c$ is the union over $J\leq j\leq m$ of the two events
\[
 \{N_{i,j}\geq j-1,\ \mu_{i,j}(z)<j/2\}
 \quad\text{and}\quad
 \{N_{i,j}\leq j-2,\ \mu_{i,j}(z)>2j\},
\]
which are exactly the bad events in Lemma~\ref{lem:upper-rank} with
$N_j=N_{i,j}$ and $\mu_j=\mu_{i,j}(z)$.  Thus the lemma gives, uniformly
in $z$,
\begin{equation}
 \mathbb P(\mathcal A_{i,z}^c\mid Z=z)\leq\delta_J.
 \label{eq:upper-good-event-prob}
\end{equation}
Using \eqref{eq:upper-good-event-prob}, and since $u_k\geq u_q$ for
$k>J$, for each $i$ and $z$,
\[
 \begin{aligned}
 &\sum_{k>J}\rho_{|a_i|}(u_k,z)
 \mathbb P\{R_i=k,\mathcal A_{i,z}^c\mid Z=z\} \\
 &\qquad\leq
 \sup_{u\geq u_q}\rho_{|a_i|}(u,z)
 \sum_{k>J}\mathbb P\{R_i=k,\mathcal A_{i,z}^c\mid Z=z\} \\
 &\qquad\leq
 \sup_{u\geq u_q}\rho_{|a_i|}(u,z)
 \mathbb P(\mathcal A_{i,z}^c\mid Z=z)
 \leq
 \delta_J\sup_{u\geq u_q}\rho_{|a_i|}(u,z).
 \end{aligned}
\]
Since $A_q^c=\{|z|\leq u_q\}$, inserting this pointwise bound into the
left-hand side of \eqref{eq:upper-large-rank-bad-target} gives
\begin{equation}
 \begin{aligned}
 &\int_{A_q^c}\frac qm\sum_{i\in\mathcal H_0}\sum_{k>J}
 \rho_{|a_i|}(u_k,z)\mathbb P\{R_i=k,\mathcal A_{i,z}^c\mid Z=z\}
 \phi(z)\dd z \\
 &\qquad\leq
 \frac qm\sum_{i\in\mathcal H_0}\delta_J
 \int_{-u_q}^{u_q}\phi(z)
 \sup_{u\geq u_q}\rho_{|a_i|}(u,z)\dd z \\
 &\qquad\leq
 \frac qm|\mathcal H_0|\delta_J C_q
 =\pi_0q\delta_J C_q
 \leq C\pi_0q(1+u_q)e^{-c\sqrt{u_q}}
 \leq C\pi_0q .
 \end{aligned}                                      \label{eq:upper-bad-rank}
\end{equation}
Here Lemma~\ref{lem:upper-null-ratio} gives
\[
 C_q:=\sup_{0\leq r\leq1}
 \int_{-u_q}^{u_q}\phi(z)\sup_{u\geq u_q}\rho_r(u,z)\dd z
 \leq\frac{1-q}{2}+\frac{u_q}{\sqrt{2\pi}}.
\]

Lastly, we prove the good-event bound
\eqref{eq:upper-large-rank-good-target}.
Here $\mathcal A_{i,z}$ is defined in \eqref{eq:upper-good-event}.
On $\{R_i=k\}$,
\begin{equation}
 N_{i,k}=k-1,\qquad N_{i,j}\leq j-2\quad(j>k).        \label{eq:upper-threshold-counts}
\end{equation}
Consequently, on $\{R_i=k\}\cap\mathcal A_{i,z}$, the exclusions in
\eqref{eq:upper-good-event} applied with $j=k$ and then with each $j>k$
give
\begin{equation}
 \mu_{i,k}(z)\geq k/2,\qquad
 \mu_{i,j}(z)\leq2j\quad(j>k).                 \label{eq:upper-count-means}
\end{equation}

Define the averaged conditional sub-CDF of the other hypotheses and its
scale version by
\begin{equation}
 F_{-i,z}(t)=\frac1m\sum_{\ell\ne i}F_{\ell,z}(t),
 \qquad G_{i,z}(u)=F_{-i,z}\{p(u)\}.                \label{eq:upper-mixture-other}
\end{equation}
For each $\ell\ne i$, the common-factor representation
\eqref{eq:common-factor-model} gives, conditionally on $Z=z$,
\[
 F_{\ell,z}\{p(u)\}
 =\mathbb P\{|T_\ell|\geq u\mid Z=z\}
 =\mathbb P\{|\theta_\ell+a_\ell z+\sqrt{1-a_\ell^2}\,\varepsilon_\ell|
             \geq u\}.
\]
Therefore
\[
 G_{i,z}(u)
 =\int \mathbb P\{|\theta+\alpha z+\sqrt{1-\alpha^2}\,\varepsilon|
                    \geq u\}\,\dd\Pi_i(\theta,\alpha),
 \qquad
 \Pi_i=\frac1m\sum_{\ell\ne i}\delta_{(\theta_\ell,a_\ell)}.
\]
This is exactly the form \eqref{eq:upper-mixture}.

We now verify the hypotheses of Lemma~\ref{lem:upper-crossing}, one
true null $i$ at a time.  For this fixed $i$, define
\[
 w_{i,k}(z)=\mathbb P\{R_i=k,\mathcal A_{i,z}\mid Z=z\},\qquad J<k\leq m,
\]
and take $G_z=G_{i,z}$.  First, the weights are nonnegative and, because the events
$\{R_i=k\}$, $1\leq k\leq m$, are disjoint,
\[
 \sum_{k>J}w_{i,k}(z)\leq1.
\]
Second, whenever $w_{i,k}(z)>0$, the event
$\{R_i=k,\mathcal A_{i,z}\}$ has positive conditional probability.  Since
the quantities $\mu_{i,j}(z)$ are fixed after conditioning on $Z=z$, the
implication above gives \eqref{eq:upper-count-means} for this $i,z,k$.
Using $\mu_{i,j}(z)=mG_{i,z}(u_j)$, these inequalities become
\[
 G_{i,z}(u_k)\geq\frac{k}{2m},\qquad
 G_{i,z}(u_j)\leq\frac{2j}{m}\quad(j>k).
\]
Thus \eqref{eq:upper-rank-weight-conditions} holds for every $k$ with
$w_{i,k}(z)>0$, with $G_z=G_{i,z}$ and $w_k(z)=w_{i,k}(z)$.
Applying Lemma~\ref{lem:upper-crossing} with $r=|a_i|$ gives
\[
 \int_{-u_q}^{u_q}\sum_{k>J}w_{i,k}(z)
 \rho_{|a_i|}(u_k,z)\phi(z)\dd z
 \leq
 \frac{u_q}{2\sqrt{2\pi}}+C\sqrt{u_q},
\]
where $A_q^c=\{|z|\leq u_q\}$.
Summing the preceding bound over $i\in\mathcal H_0$ and using
$|\mathcal H_0|/m=\pi_0$ gives
\eqref{eq:upper-large-rank-good-target}.

We have proved part (b) for $q\le q_0$.  If
$q_0<q\le2\bar\Phi(1)$, part (a)
gives
\[
\FDR(\BH_q)
\le q\left\{1+\pi_0\left(\frac{1-q}{2}
+\frac{u_q}{\sqrt{2\pi}}\right)\right\}.
\]
When $q\in[q_0,2\bar\Phi(1)]$, the quantities
$u_q$ and $\log(1/q)$ are bounded above and $\log(1/q)$ is bounded away
from zero.  Hence, after enlarging the universal constant $C$,
\[
\frac{1-q}{2}+\frac{u_q}{\sqrt{2\pi}}
\le
\frac1{2\sqrt\pi}\sqrt{\log(1/q)}
+C\{\log(1/q)\}^{1/4},
\]
which closes part (b) on the remaining $q$-range.
\end{proof}

\begin{remark}[PRDN for the two-sided null $p$-values]\label{rem:prdn-pvalues}
The theorem imposes no sign restriction on the loadings $a_i$, so the null
correlations $a_ia_j$ may be negative.  Nevertheless, the two-sided null
$p$-values satisfy PRDN.  Let
\[
 T_0=(T_i:i\in\mathcal H_0),\qquad
 a_0=(a_i:i\in\mathcal H_0),\qquad
 \varepsilon_0=(\varepsilon_i:i\in\mathcal H_0).
\]
Put
\[
 D_0=\operatorname{diag}(1-a_i^2:i\in\mathcal H_0).
\]
Since $\theta_i=0$ for $i\in\mathcal H_0$,
\[
 T_0=a_0Z+\sqrt{D_0}\,\varepsilon_0.
\]
Hence $T_0$ is centered Gaussian with covariance matrix
\[
 \Sigma_0=D_0+a_0a_0^\top.
\]
Assume first that $|a_i|<1$ for every null coordinate.  Let
\[
 B=\operatorname{diag}\{\operatorname{sign}(a_i):i\in\mathcal H_0\},
 \qquad
 r_0=(|a_i|:i\in\mathcal H_0)^\top,
\]
with $\operatorname{sign}(0)=1$.  Then
\[
 B\Sigma_0B=D_0+r_0r_0^\top.
\]
By the Sherman-Morrison formula,
\[
 (D_0+r_0r_0^\top)^{-1}
 =D_0^{-1}
  -\frac{D_0^{-1}r_0r_0^\top D_0^{-1}}
  {1+r_0^\top D_0^{-1}r_0}.
\]
Thus every off-diagonal entry of $(D_0+r_0r_0^\top)^{-1}$ is nonpositive.  The
Karlin-Rinott absolute-value multinormal criterion for
multivariate total positivity of order two (MTP$_2$)
\citep{KarlinRinott1981} therefore applies to $BT_0$, and
$(|(BT_0)_i|:i\in\mathcal H_0)$ is MTP$_2$.  Since
$|(BT_0)_i|=|T_i|$, coordinatewise sign changes do not alter the
absolute null statistics.  Applying the same decreasing map
$g(x)=p(x)=2\Phib(x)$ to every coordinate preserves MTP$_2$.
Indeed, for $u,v\in(0,1)^{m_0}$, coordinatewise monotonicity of $g^{-1}$
gives
\[
 g^{-1}(u\wedge v)=g^{-1}(u)\vee g^{-1}(v),
 \qquad
 g^{-1}(u\vee v)=g^{-1}(u)\wedge g^{-1}(v).
\]
If $f$ is the density of $(|(BT_0)_i|:i\in\mathcal H_0)$, the density
after the transformation is
\[
 \widetilde f(u)
 =f\{g^{-1}(u)\}\prod_{i\in\mathcal H_0}|(g^{-1})'(u_i)|.
\]
For each coordinate,
$\{u_i\wedge v_i,u_i\vee v_i\}=\{u_i,v_i\}$; hence the two products of
Jacobian factors are equal.  Therefore the MTP$_2$ inequality for $f$
implies
\[
\begin{aligned}
 \widetilde f(u\wedge v)\widetilde f(u\vee v)
 &=f\{g^{-1}(u)\vee g^{-1}(v)\}
   f\{g^{-1}(u)\wedge g^{-1}(v)\}
   \prod_{i\in\mathcal H_0}|(g^{-1})'(u_i)(g^{-1})'(v_i)|\\
 &\geq f\{g^{-1}(u)\}f\{g^{-1}(v)\}
   \prod_{i\in\mathcal H_0}|(g^{-1})'(u_i)(g^{-1})'(v_i)|\\
 &=\widetilde f(u)\widetilde f(v).
\end{aligned}
\]
Thus the vector of two-sided null $p$-values is MTP$_2$, which implies
PRDN.

If some $|a_i|=1$, define $a_i^{(\eta)}=(1-\eta)a_i$ for all
$i\in\mathcal H_0$, and let $\eta\downarrow0$.  The corresponding
absolute null vectors converge weakly to
$(|T_i|:i\in\mathcal H_0)$.  Under the measure-theoretic definition
of MTP$_2$, the class of MTP$_2$ probability measures is closed under
weak convergence \citep{ColangeloMullerScarsini2006}.  Hence the
limiting absolute-value law remains MTP$_2$.  Appendix A.1 of
\citet{Su2018} then implies that the induced vector of two-sided null
$p$-values satisfies PRDN.
\end{remark}

\begingroup

\subsection{Upper bounds for one-sided tests}

We derive an FDR upper bound for one-sided tests under the
common-factor model and show that its leading constant cannot be improved within
this class.

\begin{theorem}
\label{thm:one-upper}
Consider the common-factor model
\eqref{eq:common-factor-model}.  Test
$H_i:\theta_i\leq0$ with $P_i=\Phib(T_i)$.  Let
$\mathcal H_0=\{i:\theta_i\leq0\}$, $m_0=|\mathcal H_0|$, and
$\pi_0=m_0/m$.  For $0<q<1/2$, put
$u_q^+={\Phib}^{-1}(q)>0$.  The FDR is zero when $m_0=0$, and otherwise
\begin{equation}
 \FDR(\BH_q)
 \leq q\left\{2+\pi_0\left(\frac12+\frac{u_q^+}{\sqrt{2\pi}}\right)\right\}.
 \label{eq:one-upper-bound}
\end{equation}
Consequently, the worst-case FDR in this common-factor class is
$O\{q\sqrt{\log(1/q)}\}$, uniformly in $m$, the means
$(\theta_1,\ldots,\theta_m)$, and the loadings
$(a_1,\ldots,a_m)$, as $q\downarrow0$.
\end{theorem}

The following corollary identifies the exact leading constant for
the common-factor class.
\begin{corollary}
\label{cor:one-sharp}
For the common-factor model
\eqref{eq:common-factor-model}, where $\FDR_{\theta,a}$ denotes the FDR
under that model, as $q\downarrow0$,

\[
 \sup_{\substack{m\in\N,\ \theta\in\R^m,\\
                    a\in[-1,1]^m}}
 \FDR_{\theta,a}(\BH_q)
 =\frac{q\sqrt{\log(1/q)}}{\sqrt\pi}+O(q).
\]

Thus the constant $1/\sqrt\pi$ in
Proposition~\ref{prop:one-expansion} is optimal in the common-factor class.
\end{corollary}

\begin{proof}[Proof of Theorem~\ref{thm:one-upper}]
If there are no true nulls, the FDR is zero.  Partition the true nulls into
the two sign groups
\[
 \mathcal H_{0,1}=\{i\in\mathcal H_0:a_i\geq0\},\qquad
 \mathcal H_{0,-1}=\{i\in\mathcal H_0:a_i<0\}.
\]
{Let $\mathcal S\subseteq\{-1,1\}$ index the nonempty groups.
The leave-one-out identity \eqref{eq:loo-identity} and conditional reduction
\eqref{eq:conditional-loo-term-bound} are independent of the particular
form of the $p$-values.

Suppose $i\in\mathcal H_{0,\sigma}$, where
$\sigma\in\mathcal S$, and write
$r=|a_i|$ and
$Y_\sigma=\sigma Z\sim N(0,1)$.  Define the actual conditional CDF by
\[
 F^{\theta_i}_{i,y}(t)
 =\mathbb P_{\theta_i}(P_i\leq t\mid Y_\sigma=y)
\]
and let $F^0_{r,y}$ denote the corresponding conditional CDF at the
boundary mean $\theta_i=0$.  Conditional on $Y_\sigma=y$,
$T_i\sim N(\theta_i+ry,1-r^2)$.  Since $\theta_i\leq0$ and rejection is
increasing in $T_i$,
\[
 F^{\theta_i}_{i,y}(t)\leq F^0_{r,y}(t),\qquad 0<t<1.
\]
Thus it suffices in the conditional leave-one-out bound to control the
boundary CDF $F^0_{r,y}$.

For $r<1$, the one-tail Gaussian density-ratio calculation gives
\begin{equation}
 \phi(y)\sup_{0<t\leq q}\frac{F^0_{r,y}(t)}t
 \leq\frac1{\sqrt{1-r^2}\sqrt{2\pi}}
 \exp\left\{-\frac{(ru_q^+-y)_+^2}{2(1-r^2)}\right\}.
 \label{eq:one-conditional-ratio-bound}
\end{equation}
Indeed, write $t=p_+(u)$, where $u\geq u_q^+$.  The bivariate normal
density identity
\[
 \phi(y)\frac1{\sqrt{1-r^2}}\phi\!\left(\frac{x-ry}{\sqrt{1-r^2}}\right)
 =\phi(x)\frac1{\sqrt{1-r^2}}\phi\!\left(\frac{y-rx}{\sqrt{1-r^2}}\right)
\]
and $p_+(u)=\int_u^\infty\phi(x)\dd x$ give

\begin{align}
 \phi(y)\frac{F^0_{r,y}\{p_+(u)\}}{p_+(u)}
 &=\frac{\displaystyle\int_u^\infty
 \phi(x)\frac1{\sqrt{1-r^2}}\phi\!\left(\frac{y-rx}{\sqrt{1-r^2}}\right)\dd x}
 {\displaystyle\int_u^\infty\phi(x)\dd x}\notag\\
 &\leq\sup_{x\geq u}\frac1{\sqrt{1-r^2}}
 \phi\!\left(\frac{y-rx}{\sqrt{1-r^2}}\right)\notag\\
 &\leq\frac1{\sqrt{1-r^2}\sqrt{2\pi}}
 \exp\left\{-\frac{(ru-y)_+^2}{2(1-r^2)}\right\}.
 \label{eq:one-ratio-at-u}
\end{align}

The final inequality in \eqref{eq:one-ratio-at-u} follows
because, for every $x\geq u$,
\[
 (rx-y)^2\geq(ru-y)_+^2.
\]
Since $r\geq0$, the map $u\mapsto(ru-y)_+$ is nondecreasing.  Thus
the right-hand side of \eqref{eq:one-ratio-at-u} is
nonincreasing in $u$ and is maximized over
$u\geq u_q^+$ at $u=u_q^+$, proving
\eqref{eq:one-conditional-ratio-bound}.  Integrating over $y\leq u_q^+$
yields

\begin{align}
 I(r)
 &:=\int_{-\infty}^{u_q^+}\phi(y)
 \sup_{0<t\leq q}\frac{F^0_{r,y}(t)}t\dd y\notag\\
 &\leq\frac1{\sqrt{1-r^2}\sqrt{2\pi}}
 \left\{
 \int_{-\infty}^{ru_q^+}
 e^{-(ru_q^+-y)^2/\{2(1-r^2)\}}\dd y
 +\int_{ru_q^+}^{u_q^+}1\dd y
 \right\}\notag\\
 &=\frac1{\sqrt{1-r^2}\sqrt{2\pi}}
 \left\{
 \int_0^\infty e^{-v^2/\{2(1-r^2)\}}\dd v
 +(1-r)u_q^+
 \right\}\notag\\
 &=\frac12+\frac{(1-r)u_q^+}{\sqrt{1-r^2}\sqrt{2\pi}}\notag\\
 &\leq\frac12+\frac{u_q^+}{\sqrt{2\pi}}.
 \label{eq:one-integrated-ratio}
\end{align}

The inequality
$(1-r)u_q^+/\{\sqrt{1-r^2}\sqrt{2\pi}\}\leq u_q^+/\sqrt{2\pi}$ in
\eqref{eq:one-integrated-ratio} follows from
$(1-r)/\sqrt{1-r^2}=\sqrt{(1-r)/(1+r)}\leq1$.  If $r=1$, then on
$Y_\sigma<u_q^+$ the boundary-null p-value is larger than $q$, so
\eqref{eq:one-integrated-ratio} remains valid.

Let $V_\sigma$ be the false rejections in sign group $\sigma$ and
$\FDP_\sigma=V_\sigma/(R\vee1)$.  On
$A_\sigma=\{Y_\sigma\leq u_q^+\}$, sum the per-null conditional bound over
$\mathcal H_{0,\sigma}$ and apply \eqref{eq:one-integrated-ratio}.  This gives
\[
 \mathbb E(\FDP_\sigma\1_{A_\sigma})
 \leq q\frac{|\mathcal H_{0,\sigma}|}{m}
 \left(\frac12+\frac{u_q^+}{\sqrt{2\pi}}\right).
\]
On $A_\sigma^c$, use $0\leq\FDP_\sigma\leq1$ and
$\mathbb P(A_\sigma^c)=q$.  Summing over $\sigma\in\mathcal S$, using
$|\mathcal S|\leq2$ and
$\FDP=\sum_{\sigma\in\mathcal S}\FDP_\sigma$, proves
\eqref{eq:one-upper-bound}.
}
\end{proof}

\begin{proof}[Proof of Corollary~\ref{cor:one-sharp}]
Theorem~\ref{thm:one-lower} gives the lower bound within the
common-factor class.  Indeed, for the perturbed model \eqref{eq:eta-model}, set
\[
 a_i^{(\eta)}=\sqrt{1-\eta^2}\,b_i,
 \qquad
 \widetilde\varepsilon_i^{(\eta)}
 =\frac{\sqrt{(1-\eta^2)(1-b_i^2)}\,\varepsilon_i+\eta\xi_i}
 {\sqrt{1-\{a_i^{(\eta)}\}^2}}.
\]
The variables $\widetilde\varepsilon_i^{(\eta)}$ are independent standard
normal variables and are independent of $Z$, and
\[
 T_i^{(\eta)}
 =\theta_i+a_i^{(\eta)}Z
  +\sqrt{1-\{a_i^{(\eta)}\}^2}\,
   \widetilde\varepsilon_i^{(\eta)}.
\]
Thus the perturbation is of the form \eqref{eq:common-factor-model}.
Together with Proposition~\ref{prop:one-expansion}, this gives

\[
 \sup_{\substack{m\in\N,\ \theta\in\R^m,\\
                    a\in[-1,1]^m}}
 \FDR_{\theta,a}(\BH_q)
 \geq \ell_{\le}(q)
 =\frac{q\sqrt{\log(1/q)}}{\sqrt\pi}+\frac q2+o(q).
\]


For the matching upper bound, note first that
$u_q^+=p^{-1}(2q)$, so \eqref{eq:mills-quantile} in
Lemma~\ref{lem:mills} gives
$u_q^+\sim\sqrt{2\log(1/q)}$.  More precisely,
\eqref{eq:mills-asymp} in Lemma~\ref{lem:mills} and
$q=\Phib(u_q^+)$ imply
\[
 (u_q^+)^2
 =2\log(1/q)-2\log u_q^+-\log(2\pi)+o(1)
 =2\log(1/q)+O\{\log\log(1/q)\}.
\]
Consequently,
\[
 u_q^+=\sqrt{2\log(1/q)}
 +O\left\{\frac{\log\log(1/q)}{\sqrt{\log(1/q)}}\right\}
 =\sqrt{2\log(1/q)}+o(1).
\]
Theorem~\ref{thm:one-upper}, with $\pi_0\leq1$, now gives the reverse
inequality up to an $O(q)$ term, proving the claim.
\end{proof}
\endgroup

\section{Discussion}


For two-sided problems, Theorem~\ref{thm:main} and
Proposition~\ref{prop:ell-expansion} show that no
bound of the form $Cq$, with $C$ independent of $q$, can hold uniformly
over all Gaussian correlation matrices.  Because the example that achieves
the lower bound belongs to the one-common-factor class studied in
Section~\ref{sec:upper-bound}, Theorem~\ref{thm:common-factor-upper} shows
that the worst-case FDR within this class has the sharp leading constant
$1/(2\sqrt\pi)$. Similarly, For one-sided tests,
Theorem~\ref{thm:one-lower} and Corollary~\ref{cor:one-sharp} give the
optimal leading constant $1/\sqrt\pi$ within the same class.

In the literature, there are procedures with finite-sample FDR guarantees
for arbitrary dependent two-sided Gaussian tests. The conditional-calibration
framework of \citet{FithianLei2022} decomposes FDR into hypothesis-specific
contributions and, for each null $i$, conditions on a null sufficient statistic
under which the $i$th $p$-value remains conditionally valid, often eliminating
nuisance parameters. The resulting guarantees depend on the procedure and
the dependence assumptions: under PRDS, the procedure controls FDR and its
rejection set contains that of BH. Under arbitrary dependence, the procedure
controls FDR and its rejection set contains that of the Benjamini-Yekutieli
procedure \citep{BenjaminiYekutieli2001}. Conditional calibration can therefore
exploit known dependence without automatically paying the full $O(\log N)$
correction of \citet{BenjaminiYekutieli2001}. Another route is the fixed-$X$
knockoff filter of \citet{BarberCandes2015}. In a Gaussian linear model,
knockoffs augment the covariate matrix with synthetic variables that mimic
the correlation structure of the original variables, and achieve the FDR
control through the symmetry between the original test statistic and its knockoff.
\citet{LiFithian2021} recast fixed-$X$ knockoffs as adding user-generated
Gaussian noise to a Gaussian estimator to obtain a whitened estimator,
followed by conditional inference.  This whitening can substantially reduce
power when the covariance has large leading eigenvalues associated with dense
leading eigenvectors, because it then requires enough added noise to erase much
of the signal.  Knockoffs also face a threshold phenomenon when the rejection
set is small.  The calibrated knockoff method of \citet{LuoFithianLei2025}
uses conditional calibration to uniformly improve knockoff procedures, with
especially large gains in small-rejection regimes.



This discussion points to two complementary directions: identifying restrictions of
dependence structures  under which the standard BH remains reliable, and developing other procedures
that leverage the dependence structures to control FDR without further restrictions.


\section*{Acknowledgments and disclosure}

The author thanks Will Fithian for encouraging him to work on the two-sided
problems, Ruodu Wang for encouraging him to work on the one-sided problems,
and Edgar Dobriban for the surprising initial counterexample that reignited
interest in this project.  The author used OpenAI GPT-5.6 Sol for assistance
with proof exploration, exposition, and editing.  The author has been working
on this problem for over five years and the results in this paper could not
have been developed without the significant input of GPT 5.6 Sol.  Nevertheless,
the human input is equally important for the research paper: the author spent
about 180 hours on idea generation, verification, correction, simplification,
and writing.  From the author's perspective, it is a remarkably rewarding
experience of Human-AI collaboration.

\bibliographystyle{plainnat}
\bibliography{FDR_BH}

\appendix

\section{\texorpdfstring{Auxiliary lemmas}{Auxiliary lemmas}}
\label{app:envelope}

This appendix collects the properties of the envelope and Gaussian tails used to define and analyze $\nu_{q,r}$.

The following lemma characterizes the likelihood-ratio envelope.
\begin{lemma}
\label{lem:envelope}
For $0\le y\le1$, $M(y)=1$.  For $y>1$, $a\mapsto L_a(y)$ has a unique maximizer $a(y)>0$, characterized by
\[
a(y)=y\tanh\{a(y)y\}.
\]
The maps $a:(1,\infty)\to(0,\infty)$ and $M:(1,\infty)\to(1,\infty)$ are continuous and strictly increasing, with
\begin{equation}
\lim_{y\downarrow1}a(y)=0,
\quad
\lim_{y\to\infty}M(y)=\infty.
\label{eq:envelope-limits}
\end{equation}
The inverse $y=y(a)$ is continuously differentiable on $(0,\infty)$, and
\begin{equation}
y'(a)
=
\frac{1-y(a)^2\sech^2\{ay(a)\}}
{\tanh\{ay(a)\}+ay(a)\sech^2\{ay(a)\}}
>0.
\label{eq:yprime}
\end{equation}
Moreover, with $a_q=a(y_q)$, the deficit in the secondary survival mass satisfies
\begin{equation}
1-qM\{y(a)\}>0\quad(0<a<a_q),
\quad
1-qM\{y(a_q)\}=0,
\quad
\frac{\mathrm d}{\mathrm da}\bigl[1-qM\{y(a)\}\bigr]<0.
\label{eq:deficit-properties}
\end{equation}
\end{lemma}

\begin{proof}
Let
\[
g_y(a)=\log L_a(y)
=-\frac{a^2}{2}+\log\cosh(ay).
\]
Then
\begin{equation}
g_y'(a)=-a+y\tanh(ay).
\label{eq:gprime}
\end{equation}
If $y\le1$, then $y\tanh(ay)\le ay^2\le a$, so $M(y)=L_0(y)=1$.

For $y>1$, put $t=ay$.  Equation $g_y'(a)=0$ is equivalent to
\begin{equation}
y^2=\frac{t}{\tanh t}.
\label{eq:t-param}
\end{equation}
{
To prove that the map $t\mapsto t/\tanh t$ in
\eqref{eq:t-param} is strictly increasing, let
$H(t)=\tanh t-t\sech^2t$.  Then $H(0)=0$ and
$H'(t)=2t\sech^2t\tanh t>0$ for $t>0$.  Hence
\[
\frac{\dd}{\dd t}
\left(\frac{t}{\tanh t}\right)
=
\frac{\tanh t-t\sech^2t}{\tanh^2t}>0.
\]
Moreover,
$t/\tanh t\to1$ as $t\downarrow0$ and
$t/\tanh t\to\infty$ as $t\to\infty$.  Because $y^2>1$,
\eqref{eq:t-param} in Lemma~\ref{lem:envelope} therefore has a unique
positive solution.  The sign of
$g_y'$ changes from positive to negative there, so the solution is the
unique maximizer.  Moreover,}
\begin{equation}
a(y)=\sqrt{t\tanh t},
\quad
y=\sqrt{\frac{t}{\tanh t}},
\label{eq:a-param}
\end{equation}
{
Both parameter functions in \eqref{eq:a-param} in
Lemma~\ref{lem:envelope} are smooth and strictly
increasing in $t>0$.  They tend respectively to zero and one as
$t\downarrow0$, and both tend to infinity as $t\to\infty$.  Thus
$a(y)$ is continuous and strictly increasing on $(1,\infty)$, with
$a(y)\to0$ as $y\downarrow1$; the inverse function theorem applied to
the second parameter function also shows that $a(y)$ is continuously
differentiable.}
Since $M(y)=L_{a(y)}(y)$, the chain rule and $\partial_aL_{a(y)}(y)=0$ give
\[
M'(y)
=
M(y)a(y)\tanh\{a(y)y\}>0.
\]
Thus $M$ is continuous and strictly increasing.  Also
\[
M(y)\ge L_y(y)\ge\frac12e^{y^2/2}\to\infty.
\]
{
Finally, apply the implicit function theorem to
\[
F(a,y)=a-y\tanh(ay)=0.
\]
At the maximizer, with $t=ay>0$, equation~\eqref{eq:t-param} in
Lemma~\ref{lem:envelope} gives
\[
 y^2\sech^2(ay)
 =\frac{t\sech^2t}{\tanh t}
 =\frac{2t}{\sinh(2t)}<1.
\]
Consequently,
\[
F_a=1-y^2\sech^2(ay)>0,
\qquad
F_y=-\tanh(ay)-ay\sech^2(ay)<0.
\]
Thus \eqref{eq:yprime} in Lemma~\ref{lem:envelope} follows from
$y'=-F_a/F_y$.}

It remains to prove \eqref{eq:deficit-properties} in
Lemma~\ref{lem:envelope}.  Since $a_q=a(y_q)$, we have
$y(a_q)=y_q$, and therefore $1-qM\{y(a_q)\}=0$ by \eqref{eq:yq}.  If
$0<a<a_q$, then $y(a)<y_q$; since $M$ is strictly increasing on
$(1,\infty)$, $qM\{y(a)\}<qM(y_q)=1$.  Finally,
\[
\frac{\mathrm d}{\mathrm da}\bigl[1-qM\{y(a)\}\bigr]
=-qM'\{y(a)\}y'(a)<0,
\]
because $M'>0$ on $(1,\infty)$ and $y'>0$ on $(0,\infty)$.
\end{proof}

The final lemma collects the Mills bounds and quantile asymptotics used to control Gaussian tails.
\begin{lemma}
\label{lem:mills}
{
The normal hazard $\lambda$ is increasing on $\R$ and satisfies
\begin{equation}
x<\lambda(x)<x+x^{-1}\quad(x>0).
\label{eq:mills-hazard}
\end{equation}
Moreover, as $x\to\infty$,
\begin{equation}
\lambda(x)=x+x^{-1}+O(x^{-3}).
\label{eq:mills-hazard-expansion}
\end{equation}
}
As $x\to\infty$,
\begin{equation}
\Phib(x)=\frac{\phi(x)}x\{1+o(1)\}.
\label{eq:mills-asymp}
\end{equation}
For every fixed $0<\sigma<1$, as $x\to\infty$,
\begin{equation}
\frac{\Phib(\sigma x)}{\Phib(x)}
\sim\frac1\sigma
\exp\left\{\frac{(1-\sigma^2)x^2}{2}\right\}.
\label{eq:mills-tail-ratio-asymp}
\end{equation}
For every $0<H<\infty$, uniformly over
$|u|\vee|v|\le H$, as $x\to\infty$,
\begin{equation}
\frac{p(x+u)}{p(x+v)}
=
\frac{x+v}{x+u}
\exp\left\{-x(u-v)-\frac{u^2-v^2}{2}\right\}
\{1+o(1)\}.
\label{eq:mills-local-ratio}
\end{equation}
If $c>0$ is fixed, then, as $q\downarrow0$,
\begin{equation}
p^{-1}(cq)\sim\sqrt{2\log(1/q)}.
\label{eq:mills-quantile}
\end{equation}
In particular, for every fixed $c_1,c_2>0$,
\[
\frac{p^{-1}(c_1q)}{p^{-1}(c_2q)}\longrightarrow1
\quad(q\downarrow0).
\]
Finally, for $x\ge0$,
\begin{equation}
2\Phib(x)\le e^{-x^2/2}.
\label{eq:mills-two-sided-exponential-tail}
\end{equation}
For $x>0$ and $\delta\ge0$,
\begin{equation}
\frac{p(x+\delta)}{p(x)}
\le
\left(1+x^{-2}\right)
\exp\left\{-x\delta-\frac{\delta^2}{2}\right\}.
\label{eq:mills-shift-upper}
\end{equation}
Consequently, if $x\to\infty$, then the following tail-ratio limits hold.
\begin{enumerate}[label=\textup{(\roman*)},leftmargin=2.2em]
\item For every $0<H<\infty$, uniformly over
$|u|\vee|v|\le H$,
\begin{equation}
\log\frac{p(x+u)}{p(x+v)}
=-x(u-v)-\frac{u^2-v^2}{2}+o(1).
\label{eq:general-ratio}
\end{equation}
\item For every $0<H<\infty$, uniformly over $|h|\le H$,
\begin{equation}
\frac{p(x)}{p(x+h/x)}\longrightarrow e^h.
\label{eq:h-over-x}
\end{equation}
\item If $0<\delta_0\le\delta\le\delta_1<\infty$, then
\begin{equation}
\frac{p(x+\delta)}{p(x)}\longrightarrow0
\label{eq:fixed-shift}
\end{equation}
uniformly in $\delta$.
\item If $\delta_x\ge0$ and $x\delta_x\to\infty$, then
\begin{equation}
\frac{p(x+\delta_x)}{p(x)}\longrightarrow0.
\label{eq:variable-shift}
\end{equation}
\end{enumerate}
\end{lemma}

\begin{proof}
For $x>0$, the upper Mills bound follows from
\begin{equation}
\Phib(x)<\frac1x\int_x^\infty t\phi(t)\,\dd t
=\frac{\phi(x)}x.
\label{eq:mills-upper}
\end{equation}
Integration by parts gives
\[
\Phib(x)=\frac{\phi(x)}x-
\int_x^\infty\frac{\phi(t)}{t^2}\,\dd t
>\frac{\phi(x)}x-\frac{\Phib(x)}{x^2},
\]
which proves the lower Mills bound
\begin{equation}
\frac{x}{1+x^2}\phi(x)<\Phib(x).
\label{eq:mills-lower}
\end{equation}
{
A further integration by parts gives
\[
\Phib(x)
=\frac{\phi(x)}x-\frac{\phi(x)}{x^3}
+3\int_x^\infty\frac{\phi(t)}{t^4}\dd t,
\]
where
\[
0<\int_x^\infty\frac{\phi(t)}{t^4}\dd t
<\frac{\phi(x)}{x^5}.
\]
Hence
\[
\Phib(x)
=\frac{\phi(x)}x\{1-x^{-2}+O(x^{-4})\},
\]
and inversion proves \eqref{eq:mills-hazard-expansion} in
Lemma~\ref{lem:mills}.}
Equations~\eqref{eq:mills-upper} and~\eqref{eq:mills-lower} imply
\eqref{eq:mills-hazard} in Lemma~\ref{lem:mills} for $x>0$.
{
Since $\lambda(x)-x>0$ also holds trivially for $x\le0$, the identity
\[
\lambda'(x)=\lambda(x)\{\lambda(x)-x\}
\]
shows that $\lambda$ is increasing on $\R$.}

Equations~\eqref{eq:mills-upper} and~\eqref{eq:mills-lower} give \eqref{eq:mills-asymp} in Lemma~\ref{lem:mills}.  Applying this at $x$ and $\sigma x$ proves \eqref{eq:mills-tail-ratio-asymp} in Lemma~\ref{lem:mills}.  Applying \eqref{eq:mills-asymp} in Lemma~\ref{lem:mills} at $x+u$ and $x+v$ gives \eqref{eq:mills-local-ratio} in Lemma~\ref{lem:mills}, for every $0<H<\infty$, uniformly over $|u|\vee|v|\le H$.  Moreover, as $x\to\infty$,
\[
-\log p(x)=\frac{x^2}{2}+O(\log x),
\]
which yields \eqref{eq:mills-quantile} in Lemma~\ref{lem:mills} by inversion.  To prove $2\Phib(x)\le e^{-x^2/2}$, set
\[
d(x)=e^{-x^2/2}-2\Phib(x).
\]
Then $d(0)=0$, $\lim_{x\to\infty}d(x)=0$, and
\[
d'(x)=e^{-x^2/2}\left(\sqrt{\frac2\pi}-x\right).
\]
Thus $d$ first increases and then decreases to zero, so $d(x)\ge0$ for all $x\ge0$.
Finally, \eqref{eq:mills-upper} and~\eqref{eq:mills-lower} imply
\[
\frac{p(x+\delta)}{p(x)}
\le
\frac{1+x^2}{x(x+\delta)}
\exp\left\{-x\delta-\frac{\delta^2}{2}\right\}
\le
\left(1+x^{-2}\right)
\exp\left\{-x\delta-\frac{\delta^2}{2}\right\},
\]
which proves \eqref{eq:mills-shift-upper} in Lemma~\ref{lem:mills}.

It remains to prove the four stated tail-ratio consequences.  Taking logarithms in \eqref{eq:mills-local-ratio} in Lemma~\ref{lem:mills} gives \eqref{eq:general-ratio} in Lemma~\ref{lem:mills}, because
\[
\log\frac{x+v}{x+u}=o(1)
\]
for every $0<H<\infty$, uniformly over
$|u|\vee|v|\le H$.  For \eqref{eq:h-over-x} in
Lemma~\ref{lem:mills}, apply \eqref{eq:mills-local-ratio} in
Lemma~\ref{lem:mills} with $u=0$ and $v=h/x$.
For every $0<H<\infty$, uniformly over $|h|\le H$,
\[
\frac{p(x)}{p(x+h/x)}
=
\frac{x+h/x}{x}
\exp\left\{h+\frac{h^2}{2x^2}\right\}
\{1+o(1)\}
\longrightarrow e^h.
\]
For \eqref{eq:fixed-shift} in Lemma~\ref{lem:mills}, apply \eqref{eq:general-ratio} in Lemma~\ref{lem:mills} with $u=\delta$ and $v=0$.  If $0<\delta_0\le\delta\le\delta_1<\infty$, then
\[
\log\frac{p(x+\delta)}{p(x)}
\le
-x\delta_0+O(1)
\longrightarrow-\infty
\]
uniformly in $\delta$.  Finally, \eqref{eq:variable-shift} in Lemma~\ref{lem:mills} follows from \eqref{eq:mills-shift-upper} in Lemma~\ref{lem:mills} with $\delta=\delta_x$, because $x\delta_x\to\infty$.
\end{proof}





\end{document}

%%% Local Variables:
%%% mode: latex
%%% TeX-master: t
%%% End:

```
