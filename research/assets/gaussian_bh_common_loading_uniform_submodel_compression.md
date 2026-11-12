---
type: lemma
title: >-
  Uniform random-submodel compression of full Gaussian BH FDP and rank at fixed
  common loading
status: approved
source:
  kind: original
depends_on:
  - gaussian_bh_common_loading_wasserstein_fdr_continuity
uses_definitions:
  - gaussian_bh_common_loading_tagged_population
  - gaussian_multiple_testing_model
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
  - false_discovery_rate
tags:
  - gaussian_bh
  - uniform_compression
  - random_submodel
  - actual_rank
---

## Statement

Fix $q\in(0,1/2)$ and $\sigma\in(0,1)$, and let $S=\overline\Phi$ and $\phi$ be the standard Gaussian density. For arbitrary $N,d\ge1$, deterministic unit vectors $v_1,\ldots,v_N\in\mathbb R^d$, means $\theta_i\in\mathbb R$, and tags $\ell_i\in\{0,1\}$ satisfying $\ell_i=1\Rightarrow\theta_i\le0$ and $\ell_i=0\Rightarrow\theta_i\ge0$, generate
$$
T_i=\theta_i+\sqrt{1-\sigma^2}\langle v_i,G\rangle+\sigma Z,
\qquad G\sim N_d(0,I_d),\quad Z\sim N(0,1),\quad G\perp Z.
$$
Singular residual Gram matrices and repeated directions are allowed. False-tagged zero is admitted only in this analytic completion. Sample $I_1,\ldots,I_m$ iid uniformly on $[N]$, independently of $(G,Z)$. Apply ordinary $m$-test BH at level $q$ to the exact original scores $T_{I_j}$ with means $\theta_{I_j}$ and tags $\ell_{I_j}$; repeated indices are exact copies, with no fresh Gaussian noise. Write $D_N,D_m$ for the full tagged FDPs and $\rho_N=R_N/N$, $\rho_m=R_m/m$ for their normalized actual largest non-strict BH ranks. This includes all ties, zero rejection, and terminal rank one.

There exist deterministic $e_m(q,\sigma)\ge0$, independent of $N,d$, means, tags, residual rank and directions, such that
$$
\mathbb E_{I,G,Z}\bigl[|D_m-D_N|+|\rho_m-\rho_N|\bigr]\le e_m(q,\sigma),\qquad
\lim_{m\to\infty}e_m(q,\sigma)=0.
$$
For every compact $K\subset(0,1/2)$ and fixed $\sigma$, the errors can be chosen with $\sup_{q\in K}e_m(q,\sigma)\to0$.

The bound must follow from the following constituent conclusions. Conditional on $G$, let $A_i=\theta_i+\sqrt{1-\sigma^2}\langle v_i,G\rangle$, and let $H(t),V(t)$ and $H_m(t),V_m(t)$ be total/true-tagged empirical upper score tails of $A_i$ and $A_{I_j}$. Prove an expected supremum empirical-tail error $O(m^{-1/2})$ independent of their distribution, using symmetrization and a Rademacher maximal inequality (or a verified known estimate). This gives a bad-event bound $O(1/(\gamma\sqrt m))$ for simultaneous tail errors at most $\gamma$, independent of $Z$ and uniformly over thresholds, including atoms. On its complement, prove common-$Z$ trimmed-rank transfer in both directions for ranks at least $a>0$ using $u_q(r)=S^{-1}(qr)$ and
$$
L_{q,a}=\sup_{a/2\le r\le1}|u_q'(r)|<\infty,
\qquad h=L_{q,a}\gamma/\sigma,\quad0<\gamma<a/2.
$$
A qualifying rank $r\ge a$ of either empirical law at $z$ must give a qualifying rank $r-\gamma$ of the other at $z+h$, interpreted through the continuous-rank crossing formulation and then its exact finite-grid identification. At every positive actual rank prove exact self-consistency of the total count with that rank. Use the rank comparison, this identity and domination of the true tail by the total tail to compare the original full mixed FDPs; their monotonicity is not assumed.

Microscopic ranks are controlled by the approved [fixed-common-loading continuity theorem](gaussian_bh_common_loading_wasserstein_fdr_continuity.md): with $\tau=\sqrt{1-\sigma^2}$ and
$$
F_z(t)=S\!\left(\frac{S^{-1}(t)-\sigma z}{\tau}\right),\quad
B_{q,\sigma}(a)=\mathbb E_Z\min\left\{1,q\int_{(0,qa]}t^{-1}\,dF_Z(t)\right\},
$$
use $\mathbb E[D\mathbf1_{\{0<\rho\le a\}}]\le B_{q,\sigma}(a)$ and prove the local-in-$q$ uniform vanishing needed above. No sharp DKW constant is assumed.

Consequently, if $W_\sigma(q)$ is the supremum over all finite canonical common-loading models and $W_{m,\sigma}(q)$ the supremum restricted to exactly $m$ tests, then
$$
0\le W_\sigma(q)-W_{m,\sigma}(q)\le e_m(q,\sigma).
$$
The canonical tags of an original model are preserved by index sampling.

## Scope and provenance

Extracted as a new proof target from the seventh resumed reassessment in project.md and the compression proposals, with no candidate proof imported as an established argument. This is absolute FDR/rank approximation; it asserts no relative-$q$ error, rate uniform as $\sigma\downarrow0$, derivative recovery, optimizer existence, or main universal-order bound.

## Proof

Put $\tau=\sqrt{1-\sigma^2}$ and $u_q(r)=S^{-1}(qr)$ for $0<r\le1$. Throughout the proof the sampled occurrences retain their original scores and tags. We use the five approved definitions in `uses_definitions` and clause 2 of the approved [fixed-common-loading continuity theorem](gaussian_bh_common_loading_wasserstein_fdr_continuity.md). No draft definition is assumed.

**1. Conditional empirical-tail bound.** Fix $G$ and write $x_i=(A_i,\ell_i)$, $P=N^{-1}\sum_i\delta_{x_i}$, and $P_m=m^{-1}\sum_j\delta_{x_{I_j}}$. The two classes of functions needed are
$$
\mathcal F_H=\{(A,\ell)\mapsto\mathbf1_{\{A\ge t\}}:t\in\mathbb R\},\qquad
\mathcal F_V=\{(A,\ell)\mapsto\ell\mathbf1_{\{A\ge t\}}:t\in\mathbb R\}.
$$
For either class $\mathcal F$, let $P_m'$ be an independent ghost sample conditional on $G$. Jensen's inequality and then independent swapping of each original/ghost pair by a Rademacher sign $\varepsilon_j$ give
$$
\begin{aligned}
\mathbb E_I\sup_{f\in\mathcal F}|(P_m-P)f|
&\le \mathbb E_{I,I'}\sup_{f\in\mathcal F}|(P_m-P_m')f|\\
&=\mathbb E_{I,I',\varepsilon}\sup_{f\in\mathcal F}
\left|\frac1m\sum_{j=1}^m\varepsilon_j(f(x_{I_j})-f(x_{I_j'}))\right|\\
&\le2\mathbb E_{I,\varepsilon}\sup_{f\in\mathcal F}
\left|\frac1m\sum_{j=1}^m\varepsilon_jf(x_{I_j})\right|.
\end{aligned}
$$
Here the Rademacher signs are independent uniform signs, also independent of the indices. Conditional on the sampled pairs, decreasing-score ordering shows that the signed sums for $\mathcal F_H$ form a subset of the prefix partial sums of $m$ such signs. For $\mathcal F_V$, retain the $k\le m$ true-tagged sampled occurrences and order them by decreasing score; its signed sums form a subset of the prefix sums of these $k$ independent signs. Include the empty prefix, and use zero when $k=0$. Ties can only remove available prefixes.

For completeness, let $S_j=\sum_{i=1}^j\varepsilon_i$, $S_0=0$, and $M_k=\max_{0\le j\le k}|S_j|$. For $\lambda>0$, partition $\{M_k\ge\lambda\}$ according to its first crossing index $j$. Since $\mathbb E[S_k\mid\varepsilon_1,\ldots,\varepsilon_j]=S_j$, conditional Jensen gives
$$
\lambda\mathbb P(M_k\ge\lambda)
\le\mathbb E\bigl[|S_k|\mathbf1_{\{M_k\ge\lambda\}}\bigr].
$$
Integrating twice this inequality in $\lambda$ and applying Cauchy--Schwarz yields
$$
\mathbb EM_k^2\le2\mathbb E(|S_k|M_k)
\le2\sqrt{k}\sqrt{\mathbb EM_k^2},
\qquad \mathbb EM_k\le2\sqrt{k}.
$$
All variables are bounded here, so the integrations are legitimate; the assertion is immediate for $k=0$. Thus each symmetrized empirical supremum has expectation at most $4/\sqrt m$. With
$$
H(t)=\frac1N\sum_i\mathbf1_{\{A_i\ge t\}},\quad
V(t)=\frac1N\sum_i\ell_i\mathbf1_{\{A_i\ge t\}},\quad
H_m(t)=\frac1m\sum_j\mathbf1_{\{A_{I_j}\ge t\}},\quad
V_m(t)=\frac1m\sum_j\ell_{I_j}\mathbf1_{\{A_{I_j}\ge t\}},
$$
define
$$
\Delta=\max\left\{\sup_t|H_m(t)-H(t)|,\ \sup_t|V_m(t)-V(t)|\right\}.
$$
We have $\mathbb E[\Delta\mid G]\le8/\sqrt m$. Measurability of the suprema follows directly by checking the finitely many full-array scores and the two extreme intervals: the tails change only at those scores. This argument includes every atom and every sampled multiplicity. For $E_\gamma=\{\Delta\le\gamma\}$, conditional and unconditional Markov inequalities give
$$
\mathbb P(E_\gamma^c\mid G)\le p_m(\gamma),\qquad
\mathbb P(E_\gamma^c)\le p_m(\gamma),\qquad
p_m(\gamma)=\min\left\{1,\frac8{\gamma\sqrt m}\right\}.
$$
The event is measurable in $(G,I)$ and independent of $Z$.

**2. Exact finite-grid crossings.** Fix $(G,I)$ and a common-shift value $z$. For either the full or sampled empirical law, use $H_n$ for its score tail and $n$ for its size ($H_N=H$). A continuous rank $r\in(0,1]$ qualifies if
$$
H_n(u_q(r)-\sigma z)\ge r.
$$
If it qualifies, put $k=nH_n(u_q(r)-\sigma z)$. This is an integer with $k/n\ge r>0$. Because $u_q$ is decreasing,
$$
H_n(u_q(k/n)-\sigma z)\ge H_n(u_q(r)-\sigma z)=k/n,
$$
so $k/n$ is a qualifying grid rank at least $r$. A grid rank $k/n$ qualifies exactly when $p_{(k)}\le qk/n$, with multiplicities included. Hence the largest continuous crossing equals the largest qualifying grid rank, and equals the normalized [ordinary BH rank](../definitions/benjamini_hochberg_step_up.md). There are no continuous crossings if and only if there are no grid crossings; in that case set the rank and FDP to zero.

At a positive largest grid rank $r=k/n$, if the count $j=nH_n(u_q(r)-\sigma z)$ exceeded $k$, the same monotonicity would make $j/n$ a larger qualifying grid rank. Therefore
$$
H_n(u_q(r)-\sigma z)=r.
$$
This also applies at $r=1$, since the count is at most $n$. It proves that the BH rejection count is exactly $k$, including all threshold ties. The true-tail fraction divided by $r$ is consequently the original tagged FDP. The ranks, cutoffs on positive ranks, and FDPs are measurable: the largest grid rank is selected from finitely many measurable threshold comparisons.

**3. Two-way common-shift transfer.** Choose $0<c<1$ and $0<\gamma<c/2$, and put
$$
L_{q,c}=\sup_{c/2\le r\le1}\frac q{\phi(S^{-1}(qr))}<\infty,\qquad
h=\frac{L_{q,c}\gamma}{\sigma}.
$$
Indeed $u_q'(r)=-q/\phi(S^{-1}(qr))$ is continuous on this compact interval. Suppose $E_\gamma$ holds. If $r\ge c$ qualifies for either empirical law at $z$, then $r-\gamma\ge c/2$ and
$$
u_q(r-\gamma)-\sigma(z+h)\le u_q(r)-\sigma z.
$$
The other empirical law has tail at least $r-\gamma$ at the old threshold, by the definition of $\Delta$, and hence also at the displayed new threshold. Thus $r-\gamma$ is a continuous qualifying rank of the other law at $z+h$. Step 2 turns this into an actual normalized-rank lower bound. The argument applies in both directions and simultaneously for all $z$. In particular, a source rank one transfers to $1-\gamma$, with no request for a rank above one.

Write $r_N(z)$ and $r_m(z)$ for the two actual normalized ranks at common value $z$. Apply the transfer to $r_m(z)$ if it is at least $c$, and otherwise use $r_m(z)<c$. Apply the reverse transfer to $r_N(z-h)$ when that rank is at least $c$, and otherwise use its trivial bound. This gives, on $E_\gamma$, for every $z$,
$$
r_N(z-h)-c-\gamma\le r_m(z)\le r_N(z+h)+c+\gamma.
$$
The comparison uses actual largest crossings, without selecting a branch. Replacing $c$ by any specified $a\in(0,1)$ proves the trimmed-transfer constituent in the statement.

**4. Integrated rank gate.** Each rank is a nondecreasing $[0,1]$-valued function of $z$, since every score increases with $z$. For any measurable such function $f$, the layer-cake representation gives
$$
f(t)=\int_0^1\mathbf1_{\{f(t)>y\}}\,dy.
$$
Each level set is an upper interval, possibly empty or the whole line, with either endpoint convention. Its indicator evaluated at $z+h$ minus that at $z-h$ is nonnegative and supported on an interval of Lebesgue length at most $2h$. Its integral against the standard normal density is at most $2h/\sqrt{2\pi}$. Tonelli therefore proves
$$
\mathbb E_Z[f(Z+h)-f(Z-h)]\le\frac{2h}{\sqrt{2\pi}}.
$$
On $E_\gamma$, step 3 implies
$$
|r_m(z)-r_N(z)|\le c+\gamma+r_N(z+h)-r_N(z-h).
$$
Conditional integration over $Z$ is legitimate since $E_\gamma$ depends only on $(G,I)$. On its complement the rank difference is at most one. Consequently
$$
\mathbb E|\rho_m-\rho_N|\le Q_m(q,\sigma;c,\gamma)
:=c+\gamma+\frac{2L_{q,c}\gamma}{\sigma\sqrt{2\pi}}+p_m(\gamma).
$$
This estimate is independent of the number of jumps or competing crossings. Monotonicity has been used only for ranks.

**5. Comparison of the original mixed FDPs.** Fix $0<a<1/2$. On $E_\gamma\cap\{\rho_N,\rho_m\ge a\}$, put $r=\rho_N$, $s=\rho_m$, $b_r=u_q(r)-\sigma Z$, and $b_s=u_q(s)-\sigma Z$. For any two thresholds, their upper sets are nested, so the tagged count on their difference is at most the total count there. Thus
$$
|V(b_r)-V(b_s)|\le|H(b_r)-H(b_s)|.
$$
By exact self-consistency, $H(b_r)=r$ and $H_m(b_s)=s$. The uniform tail errors yield
$$
|V(b_r)-V_m(b_s)|
\le|H(b_r)-H(b_s)|+\gamma
\le|r-s|+2\gamma.
$$
Write $U=V(b_r)$ and $W=V_m(b_s)$. Here $D_N=U/r$, $D_m=W/s$, and $0\le W\le s$. Direct subtraction, using $r,s\ge a$, gives
$$
\left|\frac Ur-\frac Ws\right|
\le\frac{|U-W|}{r}+\frac{W|r-s|}{rs}
\le\frac{2|r-s|+2\gamma}{a}.
$$
On $E_\gamma^c$ the FDP difference is at most one. Integration proves
$$
\mathbb E\left[|D_m-D_N|\mathbf1_{\{\rho_N,\rho_m\ge a\}}\right]
\le\frac{2Q_m(q,\sigma;c,\gamma)+2\gamma}{a}+p_m(\gamma).
$$
Both numerators and denominators here are those of the original mixed tagged procedures on their own actual BH cutoffs.

**6. Microscopic FDPs.** The full array defines the deterministic uniform parameter law $N^{-1}\sum_i\delta_{(\theta_i,v_i,\ell_i)}$ in the [closed tagged parameter space](../definitions/gaussian_bh_common_loading_tagged_population.md) with $\mathcal H=\mathbb R^d$. It has finite first moment, unit directions, and the required signed-mean tags. Clause 2 of the approved [continuity theorem](gaussian_bh_common_loading_wasserstein_fdr_continuity.md), together with step 2's finite identification, applies even for singular Gram matrices, repeated directions, and alternative-tagged zero means. For the sampled array, first condition on the complete index list $I$. Its uniform parameter law is then another deterministic finite law of exactly this type; $I$ is independent of $(G,Z)$, so the same theorem applies for each list, and we may average over $I$. No conditioning on $G$ is made in this application. For $j=N,m$ and $0<b<1$ we obtain
$$
\mathbb E\bigl[D_j\mathbf1_{\{0<\rho_j\le b\}}\bigr]\le B_{q,\sigma}(b).
$$
At rank zero the FDP is zero. In particular the theorem supplies, for every real $z$,
$$
I_z(b):=\int_{(0,b]}t^{-1}\,dF_z(t)<\infty\quad(0<b<1),\qquad
I_z(b)\longrightarrow0\quad(b\downarrow0).
$$
Only this approved microscopic bound and its integral properties are imported; the finite crossing, shift, and rank-integration arguments above have been reproved.

**7. Full coupled bound and a deterministic error.** Every pair of ranks is covered by: both ranks at most $2a$; both ranks at least $a$; or their minimum smaller than $a$ and maximum greater than $2a$. On the first set, $|D_m-D_N|\le D_m+D_N$ costs at most $2B_{q,\sigma}(2a)$ in expectation, by step 6 including rank zero. On the third set the rank difference exceeds $a$, so Markov's inequality and step 4 bound its expected FDP cost by $Q_m/a$. Step 5 bounds the second set. The sets may overlap, which only enlarges this nonnegative bound. Adding the rank error itself yields
$$
\mathbb E\bigl[|D_m-D_N|+|\rho_m-\rho_N|\bigr]
\le\mathcal E_m(q,\sigma;a,c,\gamma)
:=2B_{q,\sigma}(2a)+(1+3/a)Q_m(q,\sigma;c,\gamma)
+2\gamma/a+p_m(\gamma).
$$
Define, for every $m\ge1$,
$$
e_m(q,\sigma)=\min\left\{2,
\inf_{\substack{0<a<1/2,\ 0<c<1\\0<\gamma<c/2}}
\mathcal E_m(q,\sigma;a,c,\gamma)\right\}.
$$
All the quantities in this definition depend only on the displayed deterministic parameters. Every member of the infimum bounds the same coupled expectation uniformly over all input arrays; the expectation is also at most two. Thus the stated expectation is bounded by $e_m$.

To prove convergence explicitly, fix $\varepsilon>0$. Choose $a\in(0,1/2)$ so that $2B_{q,\sigma}(2a)<\varepsilon/4$. Set $C_a=1+3/a$ and choose $c\in(0,1)$ with $C_ac<\varepsilon/4$. For these fixed choices, choose $0<\gamma<c/2$ so that
$$
\left[C_a\left(1+\frac{2L_{q,c}}{\sigma\sqrt{2\pi}}\right)+\frac2a\right]\gamma<\varepsilon/4.
$$
Finally choose $m$ sufficiently large that $(C_a+1)p_m(\gamma)<\varepsilon/4$. The full gate is then less than $\varepsilon$. These choices are independent of $N,d$, all means and tags, and all directions. The separate parameters $c$ and $a$ ensure that the rank-trimming cost $c/a$ can be made small. This proves $e_m(q,\sigma)\to0$.

**8. Uniformity on compact level sets.** If $K\subset(0,1/2)$ is nonempty and compact, let $q_- =\min K>0$ and $q_+=\max K<1/2$. For fixed $c$ the continuous derivative expression is bounded on $[q_-,q_+]\times[c/2,1]$, so
$$
L_{K,c}:=\sup_{q\in K}L_{q,c}<\infty.
$$
The scalar $F_z$ and $I_z$ depend on $\sigma$, not on $q$. Since $I_z$ increases in its argument, for $0<a<1/2$,
$$
\sup_{q\in K}B_{q,\sigma}(2a)
\le\overline B_{K,\sigma}(a)
:=\mathbb E_Z\min\{1,q_+I_Z(2q_+a)\}\longrightarrow0.
$$
Indeed $2q_+a<1$, and step 6 supplies pointwise convergence of the integrals to zero for every $z$; the integrands are bounded by one, so bounded convergence proves the limit. In the choices of step 7 replace $B_{q,\sigma}(2a)$ by $\overline B_{K,\sigma}(a)$ and $L_{q,c}$ by $L_{K,c}$. The same deterministic $a,c,\gamma$ and lower bound on $m$ then work for every $q\in K$ and every model. Therefore $\sup_{q\in K}e_m(q,\sigma)\to0$. The empty compact set is vacuous. This makes no limiting assertion as $\sigma$ tends to zero.

**9. Exactly-$m$ canonical supremum.** Start with any finite canonical common-loading model, so $\ell_i=\mathbf1_{\{\theta_i\le0\}}$. For each fixed index list its sampled vector has means $\theta_{I_j}$ and covariance
$$
\Sigma^{(I)}_{jk}=\tau^2\langle v_{I_j},v_{I_k}\rangle+\sigma^2.
$$
This is positive semidefinite as a sum of a Gram matrix with nonnegative coefficient and $\sigma^2$ times the all-ones matrix; its diagonal is $\tau^2+\sigma^2=1$. The vector is jointly Gaussian, being an affine function of the original $(G,Z)$. Repeated indices are identical coordinates and cause no difficulty for the admissible singular covariance convention. Sampling preserves the canonical tags exactly, including true-tagged zero means. Each fixed list therefore produces an admissible exactly-$m$ common-loading model, and
$$
\mathbb E_{G,Z}[D_m\mid I]\le W_{m,\sigma}(q).
$$
Averaging and using the already proved coupled error bound gives
$$
\mathbb E D_N\le\mathbb E D_m+e_m(q,\sigma)
\le W_{m,\sigma}(q)+e_m(q,\sigma).
$$
Taking the supremum over all finite canonical input arrays yields $W_\sigma(q)\le W_{m,\sigma}(q)+e_m(q,\sigma)$. Class inclusion gives the reverse inequality $W_{m,\sigma}(q)\le W_\sigma(q)$. This proves the claimed supremum gap with the same deterministic error, without requiring an optimizer.
