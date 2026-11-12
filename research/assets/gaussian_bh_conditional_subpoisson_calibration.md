---
type: lemma
title: Actual-rank conditional calibration from sub-Poisson null counts
status: approved
source:
  kind: original
depends_on: []
uses_definitions:
  - benjamini_hochberg_step_up
  - false_discovery_rate
tags: []
---

## Statement

Fix an integer $N\ge1$, a deterministic original true-null set $I_0\subseteq\{1,\ldots,N\}$, a level $q\in(0,1)$, and arbitrary p-values $P_1,\ldots,P_N\in[0,1]$. Let $\mathcal H$ be a conditioning sigma-field containing the complete alternative p-value vector $(P_j)_{j\notin I_0}$. Run ordinary BH at its largest qualifying rank, with non-strict comparisons, multiplicities and the original null labels; let $R,V$ be its actual rejection and false-rejection counts and $\operatorname{FDP}=V/(R\vee1)$.

Suppose an $\mathcal H$-measurable $K\in[1,\infty]$ satisfies, almost surely on $\{K<\infty\}$, for every deterministic $s\in(0,q]$ and $\lambda\ge0$,
$$
\mathbb E\!\left[\exp\{\lambda C(s)\}\mid\mathcal H\right]
\le \exp\{NKs(e^\lambda-1)\},\qquad
C(s)=\sum_{i\in I_0}\mathbf1_{\{P_i\le s\}}.
$$
The conditional law and inequalities are taken on one common full-measure set. Then
$$
\mathbb E[\operatorname{FDP}\mid\mathcal H]
\le\min\{1,4e qK\},\qquad
\operatorname{FDR}\le\mathbb E\min\{1,4e qK\}.
$$
Here $e$ is the base of the natural logarithm and the cap is interpreted as $1$ when $K=\infty$. No conditional independence or association of the null coordinates is assumed.

A Gaussian sufficient condition is the following. Suppose, under the final conditioning $\mathcal H$, the null score vector $T_{I_0}$ has a Gaussian law with an $\mathcal H$-measurable finite mean vector and PSD covariance matrix $Q$, with $Q_{ij}\le0$ for distinct original null labels. Singular covariance and zero conditional variances are permitted. Put $P_i=\overline\Phi(T_i)$ for $i\in I_0$, $F_{i,\mathcal H}(s)=\mathbb P(P_i\le s\mid\mathcal H)$, and
$$
K=\max\left\{1,\sup_{0<s\le q}
\frac{\sum_{i\in I_0}F_{i,\mathcal H}(s)}{Ns}\right\}.
$$
The supremum can be taken over rational $s\in(0,q)$ and the endpoint $q$, hence defines a measurable extended-real variable. This $K$ satisfies the displayed conditional count inequality wherever it is finite, and therefore the same conditional FDR bound holds. Nonpositive residual covariance must hold after the entire alternative vector has been included in $\mathcal H$; no preservation of its signs under further conditioning is asserted. All coordinates and alternative gates remain in the same original BH procedure. The lemma supplies a conditional calibration mechanism only; it asserts no unrestricted Gaussian order bound.

## Proof

Write $\mathbb E$ and $\mathbb P$ for expectation and probability under the given law, and put $m=|I_0|$. If $m=0$, the FDP is identically zero and the empty Gaussian count has exponential moment $1$, so every conclusion follows. Assume $m\ge1$. Let
$$
\mathcal E=\{K<\infty\}\in\mathcal H.
$$
On $\mathcal E^c$ the asserted conditional cap is $1$. We first prove the general result on $\mathcal E$.

### Conditional versions and admissible random parameters

For $k=1,\ldots,N$ put $s_k=qk/N$ and choose versions
$$
p_{k,c}=\mathbb E[\mathbf1_{\{C(s_k)=c\}}\mid\mathcal H],
\qquad c=0,\ldots,m.
$$
On one common full-measure set these are nonnegative and sum to $1$. Define the finite exponential polynomial
$$
M_k(\lambda)=\sum_{c=0}^m e^{\lambda c}p_{k,c}.
$$
For deterministic $\lambda\ge0$, this is a version of
$\mathbb E[e^{\lambda C(s_k)}\mid\mathcal H]$. Intersecting the finitely many grid-index sets and the countably many sets for rational nonnegative $\lambda$, and then using continuity in $\lambda$, gives on $\mathcal E$
$$
M_k(\lambda)\le
\exp\{NKs_k(e^\lambda-1)\}
\quad\text{for every }k\in\{1,\ldots,N\},\ \lambda\ge0.
\tag{1}
$$
All subsequent uses of (1) take place on this same set.

If $L$ is any finite, nonnegative $\mathcal H$-measurable random variable, then the finite partition by $C(s_k)$ and the nonnegative conditional multiplication rule give
$$
\mathbb E[e^{L C(s_k)}\mid\mathcal H]
=\sum_{c=0}^m e^{Lc}p_{k,c}=M_k(L).
\tag{2}
$$
The multiplication rule applies to nonnegative variables even if an unconditional integral is infinite. Thus (1) can be evaluated at $L$ without selecting a new exceptional set. If $J$ is $\mathcal H$-measurable and takes values in $\{1,\ldots,N\}$, finite pasting over $\{J=k\}$ also gives the corresponding inequality at $s_J$ with any such $L$. These are conditional finite-grid substitutions; they do not substitute a selected threshold into an unconditional bound.

Null zeros can be excluded on $\mathcal E$. Take $s_n=q2^{-n}$, $n\ge1$. The bounded variables $e^{C(s_n)}$ decrease to $e^{C(0)}$, where $C(0)$ counts null p-values equal to zero. Conditional bounded convergence and the hypothesis at $\lambda=1$ imply on $\mathcal E$
$$
\mathbb E[e^{C(0)}\mid\mathcal H]
\le\lim_{n\to\infty}\exp\{NKs_n(e-1)\}=1.
$$
Since $e^{C(0)}\ge1$, it follows that
$\mathbb E[\mathbf1_{\mathcal E}(e^{C(0)}-1)]=0$.
Consequently $C(0)=0$ almost surely on $\mathcal E$, and its conditional probability of being positive is zero there. The versions for this countable limit and the preceding finite-grid versions may all be fixed on one full-measure set.

### The exact original BH rank

Let $r$ be the largest qualifying BH rank. If $r>0$, at least $r$ p-values are at most $qr/N$. If their number were $\ell>r$, then
$P_{(\ell)}\le qr/N\le q\ell/N$, contradicting maximality. Hence the rejection count is $R=r$. When $r=0$, the rejection set is empty by definition, so again $R=r$. This reasoning includes every tied member of a non-strict threshold.

For $k=0,\ldots,N$ define
$$
A(k)=\sum_{j\notin I_0}\mathbf1_{\{P_j\le qk/N\}},
\qquad
k_i=\max\{k\in\{0,\ldots,N\}:i+A(k)\ge k\},
\quad0\le i\le m.
\tag{3}
$$
Every $A(k)$ and $k_i$ is $\mathcal H$-measurable because the entire alternative vector is contained in $\mathcal H$. The defining set for $k_i$ contains $k=i$, so $k_i\ge i$.

On $R>0$, the original rejection set gives
$$
V=C(qR/N),\qquad R=V+A(R).
$$
On $R=0$, $C(0)=0$ almost surely on $\mathcal E$, while $A(0)=0$: an alternative p-value equal to zero would make rank $1$ qualify. Thus both equalities hold there as well. In particular $R$ is feasible in the definition of $k_V$. If $k_V>R$, count monotonicity and (3) give
$$
C(qk_V/N)\ge V,\qquad V+A(k_V)\ge k_V.
$$
At least $k_V$ original p-values would then be at most $qk_V/N$, making $k_V$ a larger qualifying rank. This contradiction proves
$$
R=k_V,\qquad C(qk_V/N)=V
\quad\text{almost surely on }\mathcal E.
\tag{4}
$$
No coordinate, null label or alternative gate has changed. Conditional versions of the finitely many consequences of (4) hold on one common full-measure set on $\mathcal E$.

### Conditional Chernoff allocation

On $\mathcal E$ put $\alpha=qK$ and, for $i=1,\ldots,m$, put $t_i=\alpha k_i>0$. Equation (4) gives
$$
\mathbb E[\operatorname{FDP}\mid\mathcal H]
=\sum_{i=1}^m\frac{i}{k_i}
 \mathbb P(V=i\mid\mathcal H).
\tag{5}
$$
Choose a deterministic $a>e$. Let $B_i=\{i/k_i>a\alpha\}$ on $\mathcal E$. On $B_i$,
$t_i/i<1/a$ and $\lambda_i=\log(i/t_i)>0$.
Define $\lambda_i=0$ elsewhere, including $\mathcal E^c$; it is finite, nonnegative and $\mathcal H$-measurable.

On $\mathcal E$, $\{V=i\}$ implies $C(qk_i/N)\ge i$ almost surely by (4). Conditional Markov's inequality follows by conditioning the pointwise exponential inequality. Applying (1)--(2), with finite pasting for $k_i$, yields on $\mathcal E\cap B_i$
$$
\begin{aligned}
\mathbb P(V=i\mid\mathcal H)
&\le\mathbb E[
  e^{\lambda_i(C(qk_i/N)-i)}\mid\mathcal H]\\
&\le\exp\{-i\log(i/t_i)+t_i(i/t_i-1)\}\\
&=e^{i-t_i}(t_i/i)^i
\le(e t_i/i)^i.
\end{aligned}
\tag{6}
$$
Only the conditional count hypothesis has been used. In particular, no independence or association is needed.

The total contribution in (5) from $B_i^c$ is at most $a\alpha$, because each associated FDP coefficient is at most that value and the conditional probabilities sum to at most $1$. For the remaining contribution, use $i/k_i=\alpha i/t_i$ and (6):
$$
\begin{aligned}
\mathbb E[\operatorname{FDP}\mid\mathcal H]
&\le a\alpha+
 \alpha\sum_{i=1}^m
 \mathbf1_{B_i}e^i(t_i/i)^{i-1}\\
&\le\alpha\left[
 a+\sum_{i=1}^{\infty}e^i a^{-(i-1)}\right]
=\alpha\left[a+\frac e{1-e/a}\right].
\end{aligned}
\tag{7}
$$
For $i=1$ the exponent $i-1$ is zero and its contribution is $e$, exactly the first term of the convergent series. Setting $a=2e$ makes the bracket $4e$. Combining this bound with $0\le\operatorname{FDP}\le1$ and the trivial $\mathcal E^c$ branch proves
$$
\mathbb E[\operatorname{FDP}\mid\mathcal H]
\le\min\{1,4e qK\}.
\tag{8}
$$
The cap is interpreted as $1$ at $K=\infty$. Taking expectation proves the stated FDR inequality. The states $V=0$, including $R=0$, contribute zero in (5).

### Gaussian count inequality

We prove the required Gaussian fact directly. Let $X$ be a finite Gaussian vector with finite mean $\mu$, PSD covariance $Q$ and $Q_{ij}\le0$ for $i\ne j$. Fix finite thresholds $b_i$ and $\lambda\ge0$, and put $p_i=\mathbb P(X_i\ge b_i)$. We claim
$$
\mathbb E\exp\left\{\lambda\sum_i
 \mathbf1_{\{X_i\ge b_i\}}\right\}
\le\prod_i[1+p_i(e^\lambda-1)]
\le\exp\left\{\sum_i p_i(e^\lambda-1)\right\}.
\tag{9}
$$

Positivity of the two-coordinate quadratic forms gives
$Q_{ij}^2\le Q_{ii}Q_{jj}$. If $Q_{ii}=0$, this forces every entry in that row to vanish, and $X_i=\mu_i$ almost surely. Remove these deterministic coordinates temporarily and retain their exact comparisons $\mathbf1_{\{\mu_i\ge b_i\}}$. If none remain, the first inequality of (9) is equality and the second follows from $1+x\le e^x$ for $x\ge0$. Otherwise keep the notation $\mu,Q$ for the retained vector, now of dimension $d\ge1$, whose marginal variances are positive.

Put $D=\operatorname{diag}(Q)$ and $B=Q-D$. For $0\le\tau\le1$ and $\eta>0$ let
$$
H_{\tau,\eta}=D+\tau B+\eta I_d.
$$
This matrix is positive definite: $D+\tau B$ is a convex combination of $D$ and $Q$. Let $\rho_{\tau,\eta}$ be its Gaussian density with mean $\mu$. Write $z=x-\mu$ and $A=H_{\tau,\eta}^{-1}$. Differentiating $H_{\tau,\eta}A=I$ gives
$\partial_\tau A=-ABA$. Furthermore,
$$
\det(H_{\tau,\eta}+hB)
=\det(H_{\tau,\eta})\det(I+hAB),
\qquad
\det(I+hAB)=1+h\operatorname{tr}(AB)+O(h^2),
$$
where the second identity follows from the finite permutation expansion of the determinant. Direct differentiation of the Gaussian density therefore gives
$$
\begin{aligned}
\partial_\tau\rho_{\tau,\eta}
&=\tfrac12[
 z^{\mathsf T}ABA z-\operatorname{tr}(AB)]
 \rho_{\tau,\eta},\\
\partial_{ij}\rho_{\tau,\eta}
&=[(Az)_i(Az)_j-A_{ij}]\rho_{\tau,\eta}.
\end{aligned}
$$
Summing the second identity against $B_{ij}$ proves
$$
\partial_\tau\rho_{\tau,\eta}
=\frac12\sum_{i,j}B_{ij}
 \partial_{ij}\rho_{\tau,\eta}.
\tag{10}
$$

Let $f_i$ be bounded, positive, smooth increasing functions with bounded first and second derivatives. At fixed $\eta>0$, the eigenvalues of $H_{\tau,\eta}$ are uniformly bounded below by $\eta$ and above by a finite constant for $\tau\in[0,1]$. The density and its derivatives in (10) are consequently bounded by an integrable Gaussian times a polynomial of degree at most two in $\|x-\mu\|$, uniformly in $\tau$. This justifies differentiating the integral of $\prod_i f_i(x_i)$.

Integrate (10) twice by parts. For completeness, insert first a smooth cutoff equal to $1$ in the radius-$L$ ball, supported in the radius-$2L$ ball, with first and second derivatives bounded by constants times $L^{-1}$ and $L^{-2}$. Every resulting cutoff error is bounded by an integrable Gaussian polynomial times bounded factors or their first two derivatives outside the radius-$L$ ball, and tends to zero as $L\to\infty$. Since $B_{ii}=0$ and $B$ is symmetric, the two off-diagonal terms cancel the factor $1/2$, giving
$$
\begin{aligned}
\frac d{d\tau}\mathbb E\prod_i f_i(X_{\tau,\eta,i})
=\sum_{i<j}Q_{ij}\,
 \mathbb E\left[
 f_i'(X_{\tau,\eta,i})f_j'(X_{\tau,\eta,j})
 \prod_{\ell\ne i,j}f_\ell(X_{\tau,\eta,\ell})
 \right]\le0.
\end{aligned}
\tag{11}
$$
Here $X_{\tau,\eta}$ denotes a Gaussian vector of the displayed mean and covariance. The sign follows because all the factors in the expectation are nonnegative. Integrating in $\tau$ and using the diagonal covariance at $\tau=0$ gives
$$
\mathbb E\prod_i f_i(X_{1,\eta,i})
\le\prod_i\mathbb E f_i(X_{0,\eta,i}).
\tag{12}
$$

The singular limit requires only endpoint couplings. Couple $X_{1,\eta}$ as $X+\sqrt\eta\,Z$, where $Z$ is an independent standard Gaussian vector. Couple $X_{0,\eta}$ as $Y+\sqrt\eta\,Z'$, where $Y$ has independent coordinates of means $\mu_i$ and variances $Q_{ii}$, and $Z'$ is independent standard Gaussian. These have precisely the required endpoint laws and converge almost surely to $X$ and $Y$. Bounded convergence in (12) yields
$$
\mathbb E\prod_i f_i(X_i)
\le\prod_i\mathbb E f_i(X_i),
\tag{13}
$$
the right side using the same marginal laws. This argument allows singular $Q$ and needs no continuity assertion about matrix square roots.

Choose a smooth nondecreasing function $\psi$ with values in $[0,1]$, equal to $0$ on $(-\infty,-1]$ and to $1$ on $[1,\infty)$; it can be obtained by integrating a nonnegative smooth probability density supported in $(-1,1)$. For $\delta>0$ apply (13) to
$$
f_{i,\delta}(x)
=1+(e^\lambda-1)\psi((x-b_i)/\delta).
$$
Every retained Gaussian marginal has positive variance, so it has no atom at $b_i$. Bounded convergence as $\delta\downarrow0$ proves the first inequality in (9) for the retained coordinates, including the desired non-strict comparisons. Restoring the removed deterministic exponential factors proves that inequality for the original vector. Finally multiply
$1+p_i(e^\lambda-1)\le\exp\{p_i(e^\lambda-1)\}$ over all coordinates, including $p_i=0$ or $1$, to obtain the second inequality. When $\lambda=0$ or the vector is empty, all these expressions equal $1$. Thus (9) holds for every finite Gaussian law described above.

### Final conditional Gaussian law and envelope

Under the Gaussian sufficient condition, use the conditional Gaussian probability kernel $\nu_\omega$ for the original null score vector. On one full-measure set its mean is finite, its covariance is PSD and all its off-diagonal entries are nonpositive. This is already the conditional law under the final $\mathcal H$, containing the entire alternative vector. No further conditioning is performed.

Write $S=\overline\Phi$. Choose versions of the conditional CDFs and count exponential moments by integration against this same kernel:
$$
\begin{aligned}
F_{i,\mathcal H}(s)
&=\int\mathbf1_{\{S(x_i)\le s\}}\,\nu_\omega(dx),\\
L_\omega(s,\lambda)
&=\int\exp\left\{\lambda
 \sum_{i\in I_0}\mathbf1_{\{S(x_i)\le s\}}\right\}
 \,\nu_\omega(dx).
\end{aligned}
$$
These are $\mathcal H$-measurable for fixed parameters and are versions of the stated conditional expectations. For $0<s\le q<1$, the original comparison $P_i\le s$ is precisely $T_i\ge S^{-1}(s)$. The fixed-law assertion (9) therefore gives on that same full set
$$
L_\omega(s,\lambda)
\le\exp\left\{
 \sum_{i\in I_0}F_{i,\mathcal H}(s)
 (e^\lambda-1)\right\}
\quad(0<s\le q,\ \lambda\ge0).
\tag{14}
$$
The fixed-law proof applies to every finite mean, every permitted covariance, every threshold and every finite exponential parameter. Thus, using the kernel-integral versions, (14) selects no new exceptional set depending on $s$ or $\lambda$. Alternatively its versions can be fixed on rational parameters and extended by right continuity in $s$ and continuity in $\lambda$ of the finite count exponential polynomial.

For each fixed conditional law, every coordinate CDF is right-continuous, including CDFs with atoms arising from deterministic scores. For $0<s<q$, choose rationals $r_n\in(s,q)$ decreasing to $s$. Then
$$
\frac{\sum_{i\in I_0}F_{i,\mathcal H}(r_n)}{Nr_n}
\longrightarrow
\frac{\sum_{i\in I_0}F_{i,\mathcal H}(s)}{Ns}.
$$
The supremum over all $0<s\le q$ consequently equals the supremum over rational $s\in(0,q)$ and the endpoint $q$. These entries are $\mathcal H$-measurable, so their countable supremum and its maximum with $1$ define the asserted measurable $K\in[1,\infty]$.

Where $K<\infty$, its definition gives
$\sum_iF_{i,\mathcal H}(s)\le NKs$ for every $0<s\le q$. Combining with (14) proves exactly the general conditional count hypothesis. Conditional null scores are finite almost surely, so their survival p-values are positive, consistently with the null-zero argument above. Applying (8) and then taking expectation proves the Gaussian conclusions as well, with cap $1$ at $K=\infty$.

All calculations retain the original labels, alternative gates, multiplicities and largest BH rank. They include empty or full null sets, alternative p-values equal to zero, ties, no rejections, singular covariance and completely deterministic conditional Gaussian vectors. The nonpositive covariance condition was used only for the final stated conditional law. No unrestricted Gaussian order estimate follows from the lemma alone. $\square$

