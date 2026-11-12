---
type: lemma
title: >-
  Cross-dimension marked-array compactification and penalized Gaussian BH
  extrema
status: approved
source:
  kind: original
depends_on:
  - gaussian_bh_common_loading_uniform_submodel_compression
  - gaussian_bh_common_loading_wasserstein_fdr_continuity
  - lib_panchenko2009_dovbysh_sudakov_mixture
uses_definitions:
  - gaussian_bh_marked_exchangeable_parameter_array
  - gaussian_bh_common_loading_tagged_population
  - gaussian_multiple_testing_model
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
  - false_discovery_rate
  - gaussian_worst_case_bh_fdr
tags:
  - gaussian_bh
  - exchangeable_array
  - quadratic_mean_penalty
  - normalized_variational_maximum
  - directing_representation
---

## Statement

Fix $0<\sigma<1$. Use the lawful jointly exchangeable [marked parameter arrays](../definitions/gaussian_bh_marked_exchangeable_parameter_array.md), their law space $\mathfrak P$, moment $M_2$, finite conditional Gaussian FDRs $\mathcal F_n$, canonical finite suprema $W_\sigma,A_{\eta,\sigma}^{\rm fin}$ and normalized objective $\mathcal L_{\eta,\delta}$. Put $S=\overline\Phi$, $\phi(t)=(2\pi)^{-1/2}e^{-t^2/2}$ and $q_{\max}=S(1)$. Every outer parameter mixture remains an expectation of conditional Gaussian FDRs, rather than one Gaussian model.

1. **Uniform completion and topology.** For $q\in(0,1/2)$, $\mathcal F_n(P;q,\sigma)$ converges uniformly in all $P\in\mathfrak P$ to $\mathcal F(P;q,\sigma)$. Convergence is locally uniform in $q$, and $\mathcal F$ is jointly continuous in $P$ for finite-subarray weak convergence and $q$ in this interval. Prove this with [uniform submodel compression](gaussian_bh_common_loading_uniform_submodel_compression.md), exchangeability, and the probability of repeated iid indices when comparing an $m$-sample of an $n$-array with $m$ distinct indices. Prove finite conditional Gaussian FDR continuity even at singular covariance matrices, using the marginal Gaussian threshold-null sets. For every finite $C\ge0$, the set $\{P\in\mathfrak P:M_2(P)\le C\}$ is compact, and $M_2$ is lower semicontinuous in this topology.

2. **Faithful suprema and fixed-level extrema.** For $\eta>0$ and fixed $q$,
$$
\sup_{P\in\mathfrak P}\mathcal F(P;q,\sigma)=W_\sigma(q),\qquad
\max_{P\in\mathfrak P_2}\{\mathcal F(P;q,\sigma)-\eta M_2(P)\}
=A_{\eta,\sigma}^{\rm fin}(q)=:A_{\eta,\sigma}(q).
$$
The unpenalized supremum is unchanged by restricting to $\mathfrak P_2$. The maximum exists, $q\le A_{\eta,\sigma}(q)\le W_\sigma(q)\le1$, and every chosen maximizer $P_\eta$ satisfies $\eta M_2(P_\eta)\le1$. As $\eta\downarrow0$,
$$
A_{\eta,\sigma}(q)\longrightarrow W_\sigma(q),\qquad
\mathcal F(P_\eta;q,\sigma)\longrightarrow W_\sigma(q),\qquad
\eta M_2(P_\eta)\longrightarrow0.
$$
Show that a maximizer with canonical zero-mean tags can be chosen: retagging every $(\theta_i,\ell_i)=(0,0)$ as $(0,1)$ preserves all BH ranks and moments and increases the true numerator. This does not characterize every maximizer. Prove the supremum comparisons by conditional finite models and canonical approximation of false-zero marks, with moment control; no simultaneous deterministic finite FDR/moment approximation of an arbitrary outer mixture follows merely from these equalities.

3. **Preliminary logarithmic bound and normalized extrema.** There is a finite $C_\sigma$ depending only on $\sigma$ such that
$$
\mathcal F(P;q,\sigma)\le C_\sigma q[1+\log(1/q)]
\quad(P\in\mathfrak P,\ 0<q\le q_{\max}).
$$
Derive this directly, including terminal rank one, from the conditional true marginal comparison and Mills bounds, rather than from a microscopic estimate with rank one omitted. With $\tau=\sqrt{1-\sigma^2}$ and $U=S^{-1}(q)$, one permitted route is to prove
$$
\mathbb E[D_n\mid Z=z,\omega]\le
\min\left\{1,\ q\int_U^\infty\frac{\phi((u-\sigma z)/\tau)}{\tau S(u)}\,du\right\},
$$
and integrate a justified Mills/completed-square bound after splitting the Gaussian $Z$ tails. For every $\eta,\delta>0$, the value
$$
L_{\eta,\delta,\sigma}=\max_{P\in\mathfrak P_2,\ 0<q\le q_{\max}}\mathcal L_{\eta,\delta}(P,q;\sigma)
$$
is finite and attained. Prove uniform $q$-coercivity towards $-\infty$ as $q\downarrow0$, using $S^{-1}(q)\asymp\sqrt{\log(1/q)}$ there, and moment compactness on the remaining level interval. Write
$$
L_{0,\delta,\sigma}=\sup_{P\in\mathfrak P,\ 0<q\le q_{\max}}
\left\{\frac{\mathcal F(P;q,\sigma)}{qS^{-1}(q)}-\delta\log(1/q)\right\}.
$$
For fixed $\delta>0$, $L_{\eta,\delta,\sigma}\to L_{0,\delta,\sigma}$ as $\eta\downarrow0$, and $\eta M_2(P_{\eta,\delta})\to0$ for any choices of maximizers. Do not assume $L_{0,\delta,\sigma}$ stays bounded as $\delta\downarrow0$.

4. **Exact lawful comparisons.** At a fixed-level maximizer $P_\eta$, every $P'\in\mathfrak P_2$ obeys
$$
\mathcal F(P';q,\sigma)-\mathcal F(P_\eta;q,\sigma)
\le\eta\{M_2(P')-M_2(P_\eta)\}.
$$
At a normalized maximizer $(P_*,q_*)$, every lawful $(P',q')$ obeys
$$
\frac{\mathcal F(P';q',\sigma)}{q'S^{-1}(q')}
-\frac{\mathcal F(P_*;q_*,\sigma)}{q_*S^{-1}(q_*)}
\le\eta\{M_2(P')-M_2(P_*)\}
+\delta\{\log(1/q')-\log(1/q_*)\}.
$$
For a deterministic lawful coordinate mean velocity $b_i$, chosen before Gaussian observations, with $|b_i|\le K$ and an exchangeability-preserving parameter transformation $\theta_i\mapsto\theta_i+\epsilon b_i$, retain the exact signed expansion
$$
M_2(P_\epsilon)-M_2(P)=2\epsilon\mathbb E[\theta_1b_1]+\epsilon^2\mathbb E b_1^2.
$$
No upward motion of a retained zero-mean true tag is lawful. Pure covariance/direction changes preserving marks have zero moment cost. These are exact value comparisons, without an assumed FDR derivative.

5. **Removal of the common loading in value.** If $F_1(q)$ is the [original unrestricted one-sided Gaussian BH FDR supremum](../definitions/gaussian_worst_case_bh_fdr.md), then
$$
\lim_{\sigma\downarrow0}W_\sigma(q)=F_1(q)\qquad(0<q<1/2).
$$
Prove this by finite-model covariance continuity under $(1-\sigma^2)\Sigma+\sigma^2\mathbf1\mathbf1^{\mathsf T}$ and both supremum comparisons. No rate, monotonicity, or fixed-$\sigma$ independent-block closure is asserted.

6. **Marked directing representation and maximum component selection.** After the known unmarked Dovbysh--Sudakov representation theorem has been independently sourced and verified, adapt it to prove the following original marked extension. Every $P\in\mathfrak P$ is a mixture of arrays generated by a random directing probability $\mu$ on $\mathbb R\times B_{\mathcal H}\times\{0,1\}$, for a separable real Hilbert space $\mathcal H$ and its closed unit ball $B_{\mathcal H}$. Conditional on $\mu$, draw $(\theta_i,v_i,\ell_i)$ iid from $\mu$, retain their lawful marks, and set
$$
C_{ij}=\langle v_i,v_j\rangle\ (i\ne j),\qquad C_{ii}=1.
$$
Conditional on these parameters, a faithful observation representation is
$$
T_i=\theta_i+\sqrt{1-\sigma^2}\,X(v_i)
+\sqrt{1-\sigma^2}\sqrt{1-\|v_i\|^2}\,\zeta_i+\sigma Z,
$$
where $X$ is a jointly measurable isonormal-series representative, and $Z,\zeta_1,\zeta_2,\ldots$ are mutually independent standard normals independent of $X$ and all parameters. Prove representative validity, conditional Gaussian equivalence, and $M_2(P)=\mathbb E\int\theta^2d\mu$.

One candidate reduction is to encode the Borel mark $(\theta,\ell)$ injectively in $[0,1]$, add the code to $C_{ii}$, use the known general diagonal-correction representation, and recover marks from the represented diagonal minus one. Check measurable mark recovery and prove $\|v\|\le1$ almost surely from the original off-diagonal bound, rather than assuming a unit-sphere representation. Verify the necessary affinity and integrability so a deterministic directing component can be selected at each attained fixed-level or normalized maximum (with its maximizing level fixed). Canonical retagging can then select a canonical maximum. No finite support or positive definiteness of the optimizer is asserted.

## Source gate and scope

This is a new draft target extracted from the seventh resumed reassessment and the uniform-compression/array-compactness proposal. The known Dovbysh--Sudakov theorem is an external prerequisite for clause 6, not an original theorem to reprove here. Its primary-source theorem node must be verified and approved in the sources stage before clause 6 or a later deterministic-directing argument uses it; no source-node ID is invented in this scaffold. Clauses 1--5 do not require that representation theorem. Complete signed transport, paired inverse-Mills recovery, and a $q$-scaled extremal zero-null flux remain outside this target. No main upper bound follows from mere existence of these extrema.

## Proof

We use the approved [uniform compression theorem](gaussian_bh_common_loading_uniform_submodel_compression.md) and, for the unmarked representation only, the approved [general diagonal-correction theorem](../library/panchenko2009_dovbysh_sudakov/assets/lib_panchenko2009_dovbysh_sudakov_mixture.md). The measurable marked extension below is proved here; no proof of the latter external theorem is asserted. Throughout, fix $\sigma\in(0,1)$ and write $\tau=\sqrt{1-\sigma^2}$ and $\Phi=1-S$ for the standard normal distribution function. All parameter sampling is independent of the Gaussian innovations.

**1. Finite kernels, topology and collision completion.** Denote the lawful array space by $\Omega_{\rm arr}$. It is a closed subspace of the countable product of real mean coordinates, discrete two-point tag coordinates and compact covariance coordinates: the mark restrictions, symmetry, unit diagonal and each finite PSD condition are closed. Thus it is Polish. Every finite permutation acts continuously, so its invariant probability laws form a closed subset $\mathfrak P$ of $\operatorname{Prob}(\Omega_{\rm arr})$.

Here and below weak convergence of laws means convergence against bounded continuous functions. Finite-subarray convergence implies tightness in the full product. Indeed, each individual coordinate law in a convergent sequence is uniformly tight. For any $\varepsilon>0$, enumerate the coordinates and choose a compact set for coordinate $j$ whose complement has probability at most $\varepsilon2^{-j}$, uniformly along that sequence. The product of these sets is compact, and its intersection with $\Omega_{\rm arr}$ is compact there; the union bound gives probability at least $1-\varepsilon$. Probability compactness on Polish spaces and uniqueness from cylinder events now imply full weak convergence. The converse follows from the continuous finite projections. This also proves the asserted equivalence of topologies.

Let $f_n(\omega,q)$ be the conditional tagged FDR of the first $n$ coordinates. It is bounded by one and jointly continuous in its finite parameters and $q\in(0,1/2)$. To see this, for convergent parameters couple the observations using the same standard $n$-normal vector and the continuous PSD square root of their covariance matrices. The observations converge almost surely, and the discrete tags are eventually constant. At a limiting observation the BH decision can change under an arbitrarily small perturbation only if
$$
T_i=S^{-1}(qk/n)\qquad\text{for some }1\le i,k\le n.
$$
Every such event has probability zero because each marginal has variance one. Away from this finite union all threshold comparisons, hence the largest qualifying rank and the full tagged FDP, are locally constant. Bounded convergence proves continuity, including singular covariances and varying levels. Consequently $\mathcal F_n(P;q,\sigma)=\int f_n(\omega,q)P(d\omega)$ is jointly continuous in $P,q$: apply weak convergence to the product laws $P_j\otimes\delta_{q_j}$ and the bounded continuous finite kernel.

For $n\ge m$, condition on the first $n$ parameters and realize their residual PSD matrix by unit vectors. Sample $m$ indices iid uniformly from $[n]$ and use the exact original observations at these indices. Compression bounds the difference between the original $n$-FDR and this sampled FDR by $e_m(q,\sigma)$. The probability of any repeated index is at most $m(m-1)/(2n)$. Conditional on no repetition, the ordered parameter subarray has, after integrating over $P$, the same law as the first $m$ coordinates by joint exchangeability. Its Gaussian observations have precisely the corresponding conditional covariance. Since FDP lies in $[0,1]$, it follows that
$$
|\mathcal F_n(P;q,\sigma)-\mathcal F_m(P;q,\sigma)|
\le e_m(q,\sigma)+\frac{m(m-1)}{2n}. \tag{P1}
$$
On collisions the observations used here are exact copies; no new private noise is introduced.

For any two large indices $n,n'\ge m$, comparison through $m$ bounds their FDR difference by $2e_m+m(m-1)(n^{-1}+{n'}^{-1})/2$. First choose $m$ large, then $n,n'$ large. This proves uniform Cauchy convergence in $P$. Letting $n\to\infty$ in (P1) gives
$$
\sup_{P\in\mathfrak P}|\mathcal F(P;q,\sigma)-\mathcal F_m(P;q,\sigma)|\le e_m(q,\sigma). \tag{P2}
$$
The compression errors vanish uniformly on each compact level interval, so the convergence is also locally uniform in $q$. Joint continuity of $\mathcal F$ follows from that of the finite kernels.

**2. Moment compactness and faithful suprema.** If $M_2(P)\le C$, exchangeability and Markov's inequality give $P(|\theta_i|>R_i)\le C/R_i^2$. Choose the $R_i$ so that the sum of these bounds is smaller than any prescribed positive number. Together with the compact tag and covariance coordinates, the resulting product gives tightness uniformly on the moment sublevel. When $C=0$ all means are zero almost surely, and the same assertion holds directly. Moreover
$$
M_2(P)=\sup_{a>0}\int\min\{\theta_1^2,a\}\,dP
$$
is lower semicontinuous, being a supremum of continuous functions. Thus the moment sublevel is closed, and probability compactness makes it compact.

For a deterministic finite lawful tagged model, replace every alternative-tagged zero mean by a positive number tending to zero, keeping its tag and covariance. All other coordinates stay fixed. The approximants are canonical. Finite-kernel continuity and convergence of empirical second moments show that the original finite tagged FDR is at most $W_\sigma(q)$ and that its FDR minus $\eta$ times its empirical second moment is at most $A_{\eta,\sigma}^{\rm fin}(q)$. Apply these inequalities conditionally to each finite prefix of an arbitrary $P$. For $P\in\mathfrak P_2$, exchangeability gives
$$
\mathbb E_P\frac1n\sum_{i=1}^n\theta_i^2=M_2(P).
$$
Integrating and passing to the limit by (P2) proves
$$
\mathcal F(P;q,\sigma)\le W_\sigma(q),\qquad
\mathcal F(P;q,\sigma)-\eta M_2(P)\le A_{\eta,\sigma}^{\rm fin}(q). \tag{P3}
$$
The first inequality holds also for infinite moment.

Conversely, fix a finite canonical model of size $N$ with parameters $(\theta_i,\ell_i,C_{ij})$. Sample indices $I_1,I_2,\ldots$ iid uniformly on $[N]$, put the sampled marks at the infinite coordinates, and put $C'_{jk}=C_{I_jI_k}$. This is a lawful jointly exchangeable array, including $C'_{jk}=1$ when distinct sampled coordinates repeat the same index. Its moment is $N^{-1}\sum_i\theta_i^2$. Its first $m$ conditional Gaussian observations have exactly the law of the sampled original scores, with repetitions copied. Compression therefore gives $|\mathcal F_m(P;q,\sigma)-f_N(q)|\le e_m(q,\sigma)$, where $f_N(q)$ is the finite model's FDR. Thus its completed FDR equals $f_N(q)$. Taking finite-model suprema proves the reverse directions in (P3), as well as equality of the unpenalized supremum restricted to $\mathfrak P_2$. This argument makes no deterministic simultaneous FDR/moment selection from a general outer mixture.

The all-true zero-mean model with residual correlations all equal to one has FDR $q$ and moment zero. Hence $q\le A_{\eta,\sigma}\le W_\sigma\le1$. A maximizing sequence for the penalized objective can be chosen with objective at least $q/2$; since $\mathcal F\le1$, its moments are bounded by $1/\eta$. On this compact sublevel the objective is upper semicontinuous, so its supremum is attained. Every maximizer has $\eta M_2\le1$. For any fixed finite canonical model, its penalized value tends to its FDR as $\eta\downarrow0$. Taking their supremum gives $A_{\eta,\sigma}\uparrow W_\sigma$, and for any maximizers
$$
0\le\eta M_2(P_\eta)=\mathcal F(P_\eta;q,\sigma)-A_{\eta,\sigma}(q)
\le W_\sigma(q)-A_{\eta,\sigma}(q)\longrightarrow0.
$$
It follows that $\mathcal F(P_\eta;q,\sigma)\to W_\sigma(q)$. Finally, the Borel coordinatewise operation $(0,0)\mapsto(0,1)$ preserves exchangeability, lawfulness, observations, ranks and moments, while increasing each finite tagged numerator. Passing to the limit shows that this operation sends a maximizer to a canonical maximizer. No assertion about all maximizers is required.

**3. Direct logarithmic bound and normalized maxima.** We supply the bound at every finite rank, including one. Write $U=S^{-1}(q)\ge1$ for $q\le q_{\max}$. Conditional on $Z=z$ and the parameters, every true coordinate has score mean $\theta_i+\sigma z$ with $\theta_i\le0$ and residual variance $\tau^2$. Its p-value is stochastically no smaller than the zero-mean conditional p-value with distribution function
$$
F_z(t)=S\bigl((S^{-1}(t)-\sigma z)/\tau\bigr).
$$
If it is rejected at positive rank $R_n$, then $p_i\le qR_n/n\le q$ and $1/R_n\le q/(np_i)$. Thus, using the nonnegative decreasing function $t\mapsto t^{-1}\mathbf1_{\{t\le q\}}$ and then $D_n\le1$, we get
$$
\mathbb E[D_n\mid Z=z,\omega]\le\min\{1,qJ(z)\},\qquad
J(z)=\int_U^\infty\frac{\phi((u-\sigma z)/\tau)}{\tau S(u)}\,du. \tag{P4}
$$
For an unbounded decreasing integrand the stochastic comparison follows by bounded truncation and monotone convergence. No independence between true coordinates was used.

Integration by parts gives, for $u>0$,
$$
S(u)=\frac{\phi(u)}u-\int_u^\infty\frac{\phi(t)}{t^2}\,dt,
\qquad \frac{u\phi(u)}{u^2+1}\le S(u)\le\frac{\phi(u)}u. \tag{P5}
$$
The lower bound follows by bounding the integral by $S(u)/u^2$. Consequently $\phi(u)/S(u)\le u+u^{-1}$. For fixed $z$, the integrand of $J(z)$ is at most a constant times $(u+u^{-1})$ times the exponential with exponent
$$
-\frac{\sigma^2u^2}{2\tau^2}+\frac{\sigma zu}{\tau^2}-\frac{\sigma^2z^2}{2\tau^2}.
$$
Completing the square shows that it is integrable on $[U,\infty)$; in particular $J(z)<\infty$.

Split the expectation in (P4) at $Z>U$, whose probability is $q$. If $G,Z$ are independent standard normals and $Y=\tau G+\sigma Z$, the conditional law of $Z$ given $Y=u$ is $N(\sigma u,\tau^2)$. Integrating the joint normal density, and using Tonelli, therefore gives the exact identity
$$
\mathbb E[J(Z)\mathbf1_{\{Z\le U\}}]
=\int_U^\infty\frac{\phi(u)}{S(u)}
\Phi\bigl((U-\sigma u)/\tau\bigr)\,du. \tag{P6}
$$
On $[U,2U/\sigma]$, discard the factor $\Phi\le1$ and integrate $u+u^{-1}$; the result is bounded by $C_\sigma(1+U^2)$. On the remaining interval, $U-\sigma u\le-\sigma u/2$, so the integral is at most
$$
\int_1^\infty(u+u^{-1})\Phi(-\sigma u/(2\tau))\,du<\infty.
$$
Its finiteness follows, for example, from the upper bound in (P5) applied to $\sigma u/(2\tau)$ for large $u$, with the bounded initial interval treated separately. The constant depends only on $\sigma$. Combining (P4)--(P6),
$$
\mathbb E D_n\le q+C_\sigma q(1+U^2).
$$
The Mills bounds (P5) imply $U^2\asymp\log(1/q)$ on $U\ge1$. More explicitly, the upper tail bound gives $\log(1/q)\ge U^2/2$ there, and the lower tail bound gives $\log(1/q)\le U^2/2+\log(2U)+\tfrac12\log(2\pi)\le C U^2$. Enlarge the constant and use (P2) to obtain the claimed uniform bound $\mathcal F\le C_\sigma q[1+\log(1/q)]$.

Put $t=\log(1/q)$. Since $U\asymp\sqrt t$ and $U\ge1$, the preceding estimate implies, uniformly over $P\in\mathfrak P_2$,
$$
\mathcal L_{\eta,\delta}(P,q;\sigma)\le C_\sigma\sqrt t-\delta t-\eta M_2(P). \tag{P7}
$$
The first two terms tend to $-\infty$ as $q\downarrow0$. The zero-moment perfectly correlated model at $q_{\max}$ gives the fixed lower value $B_\delta=1-\delta\log(1/q_{\max})$. Thus all maximizing sequences, for every fixed $\eta,\delta>0$, may be restricted to $q\in[a,q_{\max}]$ for some $a>0$, independent of the sequence and its moments. On this compact interval $1/(qS^{-1}(q))$ is bounded. A sequence with objective at least $B_\delta-1$ consequently has a uniform finite moment bound because $\eta>0$. Moment compactness and joint continuity of $\mathcal F$ give upper semicontinuity of the objective and attainment. Estimate (P7), also without its moment term, proves finiteness of $L_{0,\delta,\sigma}$.

At every fixed level the unpenalized supremum is unchanged on finite-moment laws, as proved in part 2. For any $P$ and level, approximate its FDR from below by such laws, keeping that level fixed. For each resulting law the penalty tends to zero as $\eta\downarrow0$. Taking suprema proves $L_{\eta,\delta,\sigma}\uparrow L_{0,\delta,\sigma}$. If $(P_{\eta,\delta},q_{\eta,\delta})$ is any maximizing pair, use the same pair as competitor at penalty $\eta/2$ to get
$$
\eta M_2(P_{\eta,\delta})\le
2\{L_{\eta/2,\delta,\sigma}-L_{\eta,\delta,\sigma}\}\longrightarrow0.
$$
All these conclusions hold for fixed $\delta>0$; they give no uniform bound as $\delta\downarrow0$.

**4. Exact comparisons and removal of the loading.** Maximality gives
$$
\mathcal F(P';q,\sigma)-\eta M_2(P')
\le\mathcal F(P_\eta;q,\sigma)-\eta M_2(P_\eta),
$$
and
$$
\frac{\mathcal F(P';q',\sigma)}{q'S^{-1}(q')}-\eta M_2(P')-\delta\log(1/q')
\le\frac{\mathcal F(P_*;q_*,\sigma)}{q_*S^{-1}(q_*)}-\eta M_2(P_*)-\delta\log(1/q_*).
$$
Rearranging gives exactly both asserted inequalities. For bounded lawful pre-observation velocities, $\mathbb E|\theta_1b_1|\le K\sqrt{M_2(P)}<\infty$, so expanding the square and integrating yields
$$
M_2(P_\epsilon)-M_2(P)=2\epsilon\mathbb E[\theta_1b_1]+\epsilon^2\mathbb E b_1^2.
$$
Lawfulness at a retained true zero requires $\epsilon b_i\le0$; in particular an upward displacement is excluded. If means and tags are preserved, changing only lawful directions or covariances has zero moment cost. None of these comparisons assumes an FDR derivative.

Every finite common-loading covariance is an admissible unrestricted covariance, so $W_\sigma(q)\le F_1(q)$. Conversely fix any unrestricted finite canonical model $(N,\theta,\Sigma)$. Its covariance $(1-\sigma^2)\Sigma+\sigma^2\mathbf1\mathbf1^{\mathsf T}$ is a common-loading covariance and tends to $\Sigma$. The finite square-root coupling in part 1, which only needs unit marginal variances, proves convergence of its FDR even if $\Sigma$ is singular. Therefore $\liminf_{\sigma\downarrow0}W_\sigma(q)$ is at least the FDR of each such finite model. Taking their supremum and using the opposite inequality proves the stated limit.

**5. Component laws with marks.** Define the Borel injective code on the lawful marked domain by
$$
c(\theta,1)=\frac{-\theta}{3(1-\theta)},\qquad
c(\theta,0)=\frac{2+\theta/(1+\theta)}3.
$$
The images are respectively $[0,1/3)$ and $[2/3,1)$; each branch is continuous and strictly monotone with a continuous inverse on its image. Thus the image is Borel and the inverse is Borel. Replace the diagonal of $C$ by $D_{ii}=1+c(\theta_i,\ell_i)$, keeping $D_{ij}=C_{ij}$ for $i\ne j$. This adds a nonnegative diagonal matrix to every finite principal submatrix, so $D$ is PSD and jointly exchangeable. Apply the approved unmarked theorem: its law is a measurable probability-kernel mixture of array laws generated by iid $(h_i,a_i)\in\ell^2\times[0,\infty)$ with entries $\langle h_i,h_j\rangle+a_i\mathbf1_{\{i=j\}}$.

The set of encoded lawful arrays is Borel. Indeed, the diagonal codes must lie in the indicated Borel image, and after decoding them the residual unit-diagonal array must satisfy the countably many closed lawful conditions. The original law gives this Borel set probability one, so almost every component law does as well, by integration of its complement. Decode each good component array to its marks and unit-diagonal residual array. On the complement use any fixed lawful array; this extends decoding to a Borel map. The pushed-forward component laws form a measurable kernel and their mixture is $P$. Each good component is exchangeable, because it was generated from iid pairs and decoding commutes with permutations.

For any one good component, let $\nu$ be one of its iid pair laws furnished by the source theorem; no measurable choice of $\nu$ across components has yet been made. Its Hilbert marginal satisfies $|\langle h,h'\rangle|\le1$ for $\nu\otimes\nu$-almost every independent pair. This forces $\|h\|\le1$ almost surely. To prove it, every $h_0$ outside the unit ball has a radius $r>0$ such that
$$
\|h_0\|^2-2r\|h_0\|-r^2>1.
$$
Every pair in the open ball $B(h_0,r)$ then has inner product greater than one. By separability these balls have a countable subcover of the complement of the unit ball. Positive mass outside would give one such ball positive mass, contradicting the product bound.

For $\nu$-almost every pair $(h,a)$ the diagonal code $\|h\|^2+a-1$ belongs to the code image. Push $\nu$ forward by
$$
(h,a)\longmapsto(\theta,h,\ell),\qquad
(\theta,\ell)=c^{-1}(\|h\|^2+a-1).
$$
It gives a probability $\mu$ on the closed strong-Polish space
$$
E=\{(\theta,v,\ell)\in\mathbb R\times B_{\ell^2}\times\{0,1\}:
\ell=1\Rightarrow\theta\le0,\ \ell=0\Rightarrow\theta\ge0\}.
$$
The decoded component is exactly the iid marked Gram law generated by $\mu$, with off-diagonal inner products and diagonal one. The original correction $a$ was used in decoding the marks; the residual diagonal correction now is $1-\|v\|^2\ge0$. It has not been discarded in the observation model.

**6. Measurable lifting, proved on completed probability spaces.** Let $\Psi:\operatorname{Prob}(E)\to\operatorname{Prob}(\Omega_{\rm arr})$ map a probability to this iid marked Gram law. It is continuous. In fact, weak convergence of the probabilities gives weak convergence of every finite iid product; the finite marked Gram maps are continuous in the strong topology. The finite array laws therefore converge, and the product tightness argument from part 1 gives convergence of the full laws. In particular the relation
$$
R=\{(Q,\mu):\Psi(\mu)=Q\}
$$
is closed between the two Polish probability spaces. The measurable kernel of component laws in part 5 gives a Borel probability $\lambda$ on $\operatorname{Prob}(\Omega_{\rm arr})$: evaluation of a kernel on a countable generating class makes the map into this probability space measurable. Almost every original mixture component belongs to the projection of $R$. We next justify completed measurability of that projection and the required section rather than assuming a Borel section.

Here is the needed projection argument. For a finite Borel probability $\lambda$ on any Polish space $X$, and any subset $A\subset X$, set
$$
c_\lambda(A)=\inf\{\lambda(H):A\subset H,\ H\text{ Borel}\}.
$$
A countable intersection of Borel supersets approaching the infimum gives a Borel envelope $H$ with $\lambda(H)=c_\lambda(A)$. Every Borel subset of $H$ disjoint from $A$ is null, since removing a positive-measure such subset would improve the envelope. If $A_n$ increases and $H_n$ are these envelopes, then $H_n\setminus H_k$ is null for $k\ge n$, because it is disjoint from $A_n$. The sets $G_n=\bigcap_{k\ge n}H_k$ increase, contain $A_n$, and satisfy $\lambda(G_n)=c_\lambda(A_n)$. Thus
$$
c_\lambda\Bigl(\bigcup_n A_n\Bigr)
\le\lambda\Bigl(\bigcup_n G_n\Bigr)=\lim_n c_\lambda(A_n).
$$
Monotonicity gives the reverse inequality. Hence $c_\lambda$ is continuous from below, including for sets not yet known measurable.

Consider a nonempty closed relation $F_0\subset X\times Y$ with $X,Y$ Polish, using complete compatible metrics and their product metric. Recursively cover each nonempty closed cell of $F_0$ by countably many nonempty closed subcells of diameter at most $2^{-n}$ at depth $n$. Such covers come from countably many sufficiently small closed balls intersected with the parent. Repeat children when a list is finite. Every branch in $\mathbb N^{\mathbb N}$ gives nested nonempty closed cells of vanishing diameter in a complete space, hence a unique point. Conversely, every point belongs to a branch. The branch map is a continuous surjection onto $F_0$, and after projection gives a continuous map $F:\mathbb N^{\mathbb N}\to X$ whose depth-$n$ cylinder images have diameter at most $2^{-n}$. Its image is the projection $A$ of $F_0$.

Fix $\varepsilon>0$. Starting with all branches, prune to finitely many children at each retained node as follows. At each stage there are finitely many retained parents. If each keeps its first $k$ children, the union of the corresponding cylinder images increases to the current retained union as $k\to\infty$. Continuity from below of $c_\lambda$ permits a finite $k$ so that the content decreases by at most $\varepsilon2^{-n-1}$ at stage $n$. Let $A_n$ be the resulting finite union of cylinder images at depth $n$, and $B_n$ the union of their closures in $X$. These are decreasing closed sets with $\lambda(B_n)\ge c_\lambda(A)-\varepsilon$. Their intersection $K$ is closed in a complete metric, and is totally bounded because for every $n$ it is covered by the finitely many depth-$n$ closures, each of diameter at most $2^{-n}$. Hence $K$ is compact. Finite measure continuity from above gives $\lambda(K)\ge c_\lambda(A)-\varepsilon$.

Moreover $K\subset A$. For $x\in K$, retain those nodes whose cylinder-image closures contain $x$. At every depth some such node exists, and its ancestors have the same property. This infinite finitely branching tree has a branch $\alpha$. The image $F(\alpha)$ and $x$ both belong to the closure of the corresponding cylinder image of diameter at most $2^{-n}$ for every $n$; they must coincide. This proves the inclusion. Taking a sequence $\varepsilon\downarrow0$ gives a countable union $B\subset A$ of compact sets with $\lambda(B)=c_\lambda(A)$. If $H$ is a minimal Borel envelope of $A$, then $B\subset A\subset H$ and $\lambda(H\setminus B)=0$. Thus $A$ is measurable in the completion of $\lambda$. The empty relation gives the empty, measurable projection. This proves the projection fact needed for any closed Polish relation.

Apply it to $R$. Its projection is completion measurable. Pulling its complement back through the component-law kernel and using the good components constructed in part 5 shows that it has completed $\lambda$-measure zero. More explicitly, the preceding compact-inner/Borel-outer construction sandwiches the projection between Borel sets differing by a $\lambda$-null Borel set; any original good component lies in the projection, so its Borel outer envelope has full measure, and therefore so does the completed projection.

On $Y=\operatorname{Prob}(E)$ choose a complete compatible metric and countably many dense centers. For $Q$ in the projection of $R$, recursively select the first closed ball of radius $2^{-n}$ from these centers for which its intersection with the fiber $R_Q$ and all previously selected balls is nonempty. These balls cover $Y$, so the selection is possible at every step. For every fixed finite history, the hit set of a proposed ball is the projection of the closed relation obtained by intersecting $R$ with those finitely many closed balls. The projection fact just proved makes every hit set measurable in the completion of $\lambda$. Taking first indices and inducting on the countably many histories shows that the selected centers are completion measurable.

The nested nonempty closed fiber cells have diameter at most $2^{1-n}$. Completeness gives a unique point in their intersection, and the selected centers converge to it, since each is within $2^{-n}$ of its cell. Their limit $\mu(Q)$ is completion measurable and satisfies $\Psi(\mu(Q))=Q$. Define it arbitrarily on the completed null complement of the projection. On the completed probability space with law $\lambda$, this is an actual random element of $\operatorname{Prob}(E)$. Integrating $\Psi(\mu(Q))=Q$ gives precisely the original law $P$. This establishes a random directing probability without imposing an unproved measurable-generator choice on the external source theorem.

**7. Observations, moment identity and extremizing components.** Take $\mathcal H=\ell^2$. With independent standard normals $\xi_k$, define $X(v)=\sum_k v_k\xi_k$ on the convergence set, and zero elsewhere. The partial sums are jointly measurable, their Cauchy convergence set is measurable, and the resulting representative is jointly measurable. For each deterministic $v\in\ell^2$, square summability gives almost sure and mean-square convergence. Fubini applied to the random directing probability, and then to a countable iid sample from it, makes these evaluations valid simultaneously at every sampled $v_i$ almost surely. This is a statement about parameter-almost-everywhere evaluations; no simultaneous pointwise convergence at every vector is needed.

Choose the directing probability, its iid parameters, the sequence $\xi_k$, and the additional standard normals $Z,\zeta_i$ with the independence in the statement. Conditional on a deterministic finite parameter list, the series evaluations are jointly Gaussian: every finite linear combination is the mean-square limit of the corresponding Gaussian partial sums. Their covariance is $\langle v_i,v_j\rangle$. Consequently
$$
T_i=\theta_i+\tau X(v_i)+\tau\sqrt{1-\|v_i\|^2}\,\zeta_i+\sigma Z
$$
has conditional marginal variance $\tau^2\|v_i\|^2+\tau^2(1-\|v_i\|^2)+\sigma^2=1$ and off-diagonal covariance $\tau^2\langle v_i,v_j\rangle+\sigma^2$. Its conditional Gaussian law is exactly the specified finite model, including singular cases. Conditioning further only on the marked covariance array gives the same kernel, since this mean and covariance depend only on that array. Tonelli and iid parameter sampling give
$$
M_2(P)=\mathbb E\theta_1^2=\mathbb E\int_E\theta^2\,d\mu,
$$
also when the value is infinite.

Write $P_\mu=\Psi(\mu)$. Every finite FDR is affine under mixtures of parameter laws, so $\mathcal F_n(P;q,\sigma)=\mathbb E\mathcal F_n(P_\mu;q,\sigma)$. The uniform convergence (P2), or bounded convergence, gives
$$
\mathcal F(P;q,\sigma)=\mathbb E\mathcal F(P_\mu;q,\sigma). \tag{P8}
$$
These integrands are measurable, since $\Psi$ and $\mathcal F$ are continuous. The component moments are measurable as integrals of the nonnegative Borel function $\theta^2$. At an attained fixed-level maximum, the finite total moment implies $M_2(P_\mu)<\infty$ almost surely and integrability of the component objective. Each such component is a lawful competitor, so
$$
A_{\eta,\sigma}(q)-\{\mathcal F(P_\mu;q,\sigma)-\eta M_2(P_\mu)\}\ge0
$$
almost surely, and its expectation is zero by (P8) and the moment identity. It vanishes almost surely. Select one zero-gap component; its directing probability is deterministic and is itself a maximizer. At a normalized maximum, hold its maximizing level $q_*$ fixed. The identical argument applies to the normalized component objective, whose coefficient $1/(q_*S^{-1}(q_*))$ is finite, and again selects a deterministic maximizing directing probability. Finally push this probability forward by canonical zero-mean retagging. Part 2 shows its value cannot decrease, its moment is unchanged, and its iid Gram construction remains valid, so it is a canonical deterministic directing maximizer. The argument asserts neither finite support nor positive definiteness, and completes all six clauses. $\square$
