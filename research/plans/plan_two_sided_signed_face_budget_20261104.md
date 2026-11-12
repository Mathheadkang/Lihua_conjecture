---
title: Signed Gaussian face budget for the unrestricted two-sided BH upper bound
type: plan
status: failed
target_asset: gaussian_bh_two_sided_sharp_upper
inspired_by:
  - idea_aaa81d69e1fc
  - idea_c781d2dc45a5
adapts: []
tags:
  - gaussian-bh
  - two-sided
  - signed-boundary
  - unrestricted-upper-bound
---

# Signed Gaussian face budget for the unrestricted two-sided BH upper bound

## Goal

Target: [Sharp uniform upper-bound target for two-sided Gaussian BH](../assets/gaussian_bh_two_sided_sharp_upper.md).

Prove the unchanged upper bound with leading constant $1/(2\sqrt\pi)$, uniformly over every finite $N$, arbitrary $q$-dependent means, and every positive-semidefinite covariance matrix with diagonal entries one. The route keeps the actual ordinary-BH ranks and both signs of every null-coordinate path. Its central analytic estimate below is an unproved obligation, not an assumed dependency. Four searches without a surviving counterexample do not establish this estimate.

The current pack contains no earlier plan for this target. Library searches for `Gaussian BH two-sided upper bound`, `BH`, `Gaussian`, `rank jump`, and `signed boundary Gaussian face pairing` returned no results. Thus no library statement is used and no proof is claimed to be adapted. The two motivating ideas supply calculations to rederive in steps 1--4, rather than black-box theorems.

## Plan

1. [x] **Set up exact two-sided regression paths.** Fix $q\in(0,1/2)$, $N$, $\theta$, and initially positive-definite $\Sigma$ with diagonal one. Set $a=q/N$, $p(x)=2\overline\Phi(x)$ for $x\geq0$, $z(u)=\overline\Phi^{-1}(u/2)$ for $0<u<1$, $U=z(q)$, and $I_0=\{i:\theta_i=0\}$, with $N_0=|I_0|$. Write $T=\theta+G$. For every $i\in I_0$ prove the regression decomposition

   $$
   G_{-i}=\rho_iG_i+W_i,\qquad
   \rho_i=\Sigma_{-i,i},\qquad
   W_i\perp G_i,\qquad
   K_i:=\operatorname{Cov}(W_i)=\Sigma_{-i,-i}-\rho_i\rho_i^{\mathsf T}.
   $$

   Under a true two-sided null, $u=p(|G_i|)$ is uniform on $(0,1)$, and $s=\operatorname{sign}(G_i)$ is an independent equiprobable sign, also independent of $W_i$. On branch $s\in\{-1,1\}$ retain every actual other mean and statistic:

   $$
   T_j^{i,s}(u,w)=\theta_j+s\rho_{ji}z(u)+w_j,\qquad j\ne i.
   $$

   The components of $W_i$ remain jointly dependent; no conditional-independence or one-factor assumption is introduced.

2. [x] **Compute the forced-zero rank and all its crossings.** Let $r_i^s(u,w)\in\{1,\ldots,N\}$ be the ordinary-BH rejection count at level $q$ after setting $p_i=0$ and using $p_j=2\overline\Phi(|T_j^{i,s}(u,w)|)$ for $j\ne i$. Prove the deterministic forced-zero identity, including the largest qualifying rank, non-strict inequalities, and ties, to obtain the exact null contribution

   $$
   C_i=\frac12\sum_{s\in\{-1,1\}}\mathbb E_{W_i}
   \int_0^1\frac{\mathbf1\{u\leq a r_i^s(u,W_i)\}}{r_i^s(u,W_i)}\,du.
   $$

   Define the BH normal thresholds $t_k=z(qk/N)$ for $1\leq k\leq N$. For each $j\ne i$ with $\rho_{ji}\ne0$, the complete list of possible branch crossings is

   $$
   x_{i,s,j,k,\epsilon}(w)=
   \frac{\epsilon t_k-\theta_j-w_j}{s\rho_{ji}}>0,\qquad
   u_{i,s,j,k,\epsilon}(w)=p(x_{i,s,j,k,\epsilon}(w)),
   \qquad \epsilon\in\{-1,1\}.
   $$

   Check both one-sided rank traces at every crossing by the original step-up rule. A listed crossing that does not change the rank has weight zero. When $\rho_{ji}=0$, that coordinate is constant on the path, even if it is tied to a grid level throughout. Coincident crossings must be processed as one simultaneous change of the full rank, not as an arbitrary sequence of single-coordinate changes. There are only finitely many possible crossing locations for each fixed model and residual realization.

3. [x] **Derive the exact signed jump identity.** On each branch define $H_i^s(u,w)=\min\{u/r_i^s(u,w),a\}$. Prove that its ordinary derivative away from crossings is the integrand in step 2, its limit at zero is zero, and its limit at one is $a$. For a distinct crossing $v$, put $r^-=r_i^s(v-,w)$, $r^+=r_i^s(v+,w)$ and

   $$
   B_i^s(v,w)=\min\{v/r^-,a\}-\min\{v/r^+,a\}.
   $$

   Integrating separately between crossings yields

   $$
   \operatorname{FDR}_{\mathrm{BH}}^{(2)}
   =\frac{N_0q}{N}+\mathcal S(q;N,\theta,\Sigma),\qquad
   \mathcal S=\frac12\sum_{i\in I_0}\sum_{s\in\{-1,1\}}
   \mathbb E_{W_i}\sum_v B_i^s(v,W_i).
   $$

   Retain negative and positive terms throughout. Every weight at $v\geq q$ is zero since both clipped values equal $a$; hence only crossings with $x>U$ contribute. Weak inequalities and isolated equalities do not change the integral because the actual null $u$ has a continuous distribution. For $N=1$ or $I_0=\varnothing$, check the identity directly.

4. [x] **Replace the random roots by explicit Gaussian face integrals.** For positive-definite $\Sigma$, simultaneous distinct crossings have residual probability zero, and $|\rho_{ji}|<1$. Write $v_{ij}=\sqrt{1-\rho_{ji}^2}$ and $b_{i,s,j,k,\epsilon}(x)=\epsilon t_k-\theta_j-s\rho_{ji}x$. On the face $W_{ij}=b_{i,s,j,k,\epsilon}(x)$, define $\mathcal B_{i,s,j,k,\epsilon}(x)$ to be the clipped difference in step 3, using the two ordinary-BH traces as $u$ increases through $p(x)$. Average this difference over the conditional joint Gaussian distribution of the other components of $W_i$, and denote that conditional expectation by $\beta_{i,s,j,k,\epsilon}(x)$. Its conditional mean and covariance must be written explicitly from $K_i$; for $\ell,h\ne i,j$ they are

   $$
   \mathbb E[W_{i\ell}\mid W_{ij}=b]=\frac{(K_i)_{\ell j}}{v_{ij}^2}b,\qquad
   \operatorname{Cov}(W_{i\ell},W_{ih}\mid W_{ij})
   =(K_i)_{\ell h}-\frac{(K_i)_{\ell j}(K_i)_{jh}}{v_{ij}^2}.
   $$

   Here subscripts on $K_i$ and $W_i$ use the original coordinate labels with $i$ omitted. Let $\phi(x)=(2\pi)^{-1/2}e^{-x^2/2}$. Prove by the change of variables $w_j=b_{i,s,j,k,\epsilon}(x)$ that

   $$
   \mathcal S
   =\frac12\sum_{i\in I_0}\sum_{s\in\{-1,1\}}
   \sum_{\substack{j\ne i:\rho_{ji}\ne0}}\sum_{k=1}^N\sum_{\epsilon\in\{-1,1\}}
   \int_U^\infty
   \frac{|\rho_{ji}|}{v_{ij}}
   \phi\!\left(\frac{\epsilon t_k-\theta_j-s\rho_{ji}x}{v_{ij}}\right)
   \beta_{i,s,j,k,\epsilon}(x)\,dx.
   $$

   There is no extra $\phi(x)$ in this root-counting integral; the null marginal enters through $p(x)$ inside the clipped weights. Check the orientation: the sign of $dp_j/du$ on this face is the sign of $\epsilon s\rho_{ji}$, so $\beta\leq0$ for $\epsilon s\rho_{ji}>0$ and $\beta\geq0$ for $\epsilon s\rho_{ji}<0$. These sign assertions follow from monotonicity of the BH rejection count in a single p-value. They do not bound the sum.

5. [ ] **Prove the signed Mills-weighted Gaussian face-budget lemma.** This is the difficult analytic obligation. For the explicit integrals and genuine BH trace weights of step 4, establish a bound uniform in $N$, all means, and all positive-definite unit-diagonal $\Sigma$:

   $$
   \mathcal S(q;N,\theta,\Sigma)
   \leq q\left\{\frac{U}{2\sqrt{2\pi}}+h(U)\right\},
   \qquad q=2\overline\Phi(U),\qquad
   \frac{h(U)}{U}\longrightarrow0,
   $$

   where the same deterministic function $h$ works for every model. Try the concrete sufficient remainder $h(U)=C\{1+\log(2+U)\}$ with universal $C$; a failure of that stronger remainder does not disprove the target, but a proved uniform $o(U)$ remainder is indispensable. The analytic task is to construct and prove a face-pairing or summation identity over the conditional Gaussian BH cells before estimating its signed value: telescope the reciprocal-rank differences over adjacent rank cells and all levels $k$, group both null signs and the entering and leaving faces, and apply

   $$
   \frac{2x}{1+x^2}\phi(x)\leq p(x)\leq\frac{2}{x}\phi(x),\qquad x>0,
   $$

   to the remaining Gaussian kernels. The pairing formula, the surviving term $qU/(2\sqrt{2\pi})$, and a dimension- and mean-independent bound on the discarded remainder must all be exhibited. Use the common Gram-matrix constraints on the regression coefficients and conditional laws, rather than treating the different $i$-slices as arbitrary unrelated arrays. In particular, averaging the two signs does not by itself produce the required factor $1/2$. Replacing $\beta$ by its positive part, summing absolute values, or maximizing each null over unrelated ranks would require a separate estimate and is not a permitted justification of this lemma. If no such signed estimate can be established, record the obstruction and fail this plan at this step; do not install it as a known result or conclude the target.

6. [ ] **Audit the proposed analytic inequality before claiming it.** Recompute its two sides in the independent case, where all $\rho_{ji}=0$ and $\mathcal S=0$, and in a nonsingular two-coordinate Gaussian model with arbitrary nonnull mean, using the explicit integrals rather than an assumed monotonicity of FDR. Check sequences with $\rho_{ji}\to0$ and $|\rho_{ji}|\to1$, growing $N$, and means on either side of the BH thresholds. Track the constants in the proposed $h$ through these limits. These checks can reject a proposed pairing estimate; passing them is not a proof of the uniform estimate in step 5. The proof must retain favorable boundary contributions and must not use covariance convexity, a fixed-mean rank-one maximum, or a one-factor slicing reduction.

7. [ ] **Pass the proved finite-model upper bound to singular covariance and all ties.** For an arbitrary admissible $\Sigma$, set $\Sigma_\delta=(1-\delta)\Sigma+\delta I_N$. With the same $N$ and means, couple $T_\delta=\theta+\sqrt{1-\delta}\,G+\sqrt\delta\,Z$, where $Z$ is independent standard Gaussian. For fixed $q,N,\theta,\Sigma$, show that the ordinary-BH FDP converges almost surely as $\delta\downarrow0$: its only possible discontinuities lie on the finitely many surfaces $p_i=qk/N$, each of probability zero because every marginal has variance one. Use bounded convergence and the model-independent bound from step 5. This treats singular residuals, duplicated or antipodal coordinates, and persistent inter-coordinate ties without assuming continuity of the individual face integrals. Take this fixed-model limit before any supremum; no uniform-in-$N$ regularization rate is needed.

8. [ ] **Recover exactly the target quantifiers and constant.** Prove from the displayed Mills bounds that $U/\sqrt{\log(1/q)}\to\sqrt2$. Steps 3, 5 and 7 then give, for every admissible model at the same $q$,

   $$
   \operatorname{FDR}_{\mathrm{BH}}^{(2)}
   \leq q+\frac{qU}{2\sqrt{2\pi}}+q h(U).
   $$

   Divide by $q\sqrt{\log(1/q)}$, take the supremum over $N,\theta,\Sigma$ at each $q$, and obtain $1/(2\sqrt\pi)$ as the upper limiting coefficient. Spell out that $q_\varepsilon$ depends only on the universal remainder and $\varepsilon$, allowing arbitrary $q$-dependent dimensions, means, covariance ranks, and null proportions.

## Verification

The certificate required from execution consists of the exact forced-zero identity, the finite root list and signed jump identity, the Gaussian face-integral formula with its trace orientation, and a complete proof of the uniform analytic estimate in step 5. The covariance approximation then supplies all singular models, and the elementary normal-quantile limit supplies the stated two-sided coefficient. The normal threshold is always $\overline\Phi^{-1}(q/2)$; a one-sided threshold or coefficient is not interchangeable with it.

Steps 1--4 expose an explicit finite-dimensional Gaussian integral problem and preserve the common BH rank. They do not solve its extremal estimate. Step 5 has no proof in the current materials and may fail. An estimate with a fixed-factor-dimension condition, a null-loading lower bound, a bounded number of loading directions, restricted means, or constants depending on $N$ cannot complete this plan. The four unsuccessful counterexample searches are motivation to attempt the proof, not a verification certificate.

## Assumed definitions

Use only the approved definitions [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md), [Gaussian test p-values and true nulls](../definitions/gaussian_test_pvalues.md), [ordinary Benjamini-Hochberg step-up procedure](../definitions/benjamini_hochberg_step_up.md), [false discovery rate](../definitions/false_discovery_rate.md), and [uniform worst-case Gaussian BH false discovery rate](../definitions/gaussian_worst_case_bh_fdr.md).

No draft definition or unproved dependency is assumed. The regression calculation, forced-zero identity, signed calculus, root integration, Mills inequalities, and singular-covariance passage are to be proved within execution. The proposed face-budget lemma is an internal proof obligation, not a new approved result. The target asset remains unchanged and draft.

## Progress

Execution on 2026-11-04 established checklist items 1--4. The following derivations are retained as a certificate of those items, although item 5 failed. No part of this section supplies the claimed uniform face budget. The workspace root was not a Git repository at execution, so freshness was checked using file hashes. The target asset's SHA-256 was 773dc107d2f357547c8bab56f58daf4bd2556615279452f046bc134277a8fdd8 and it was not edited.

### Regression and the deterministic forced-zero identity

Throughout this certificate fix $q,N,\theta,\Sigma$ as in item 1 with $\Sigma$ positive definite. For a null coordinate $i$, define $W_i=G_{-i}-\rho_iG_i$. Then
$$
\operatorname{Cov}(W_i,G_i)=\Sigma_{-i,i}-\rho_i=0,
\qquad
\operatorname{Cov}(W_i)=\Sigma_{-i,-i}-\rho_i\rho_i^{\mathsf T}=K_i.
$$
The pair $(W_i,G_i)$ is jointly Gaussian, since both are linear transformations of $G$. Its joint characteristic function factors when the cross covariance is zero, proving independence, including for any degenerate linear transformations. In the present positive-definite case $K_i$ is positive definite by the Schur complement. Symmetry of $G_i\sim N(0,1)$ shows that its sign is equiprobable and independent of $|G_i|$; independence from $W_i$ follows from the preceding factorization. For $0<u<1$,
$$
\Pr\{p(|G_i|)\leq u\}=\Pr\{|G_i|\geq z(u)\}
=2\overline\Phi(z(u))=u.
$$
Thus the joint law of $(u,s,W_i)$ is the product of uniform measure, the fair sign, and the full Gaussian law with covariance $K_i$. Substitution of $G_i=sz(u)$ gives exactly the paths in item 1.

For an arbitrary deterministic p-value vector, let $R$ be its BH rejection count and $r$ the count after replacing $p_i$ by zero. The largest qualifying rank equals the number of p-values below its rejection threshold: if rank $k$ is maximal and there were $h>k$ p-values at most $ak$, then rank $h$ would qualify because $ak\leq ah$. Also $r\geq1$.

If $i$ is rejected originally, then $p_i\leq aR$. At every threshold $ah$ with $h\geq R$, $p_i$ was already counted. Replacing it by zero changes none of these counts, so no new rank above $R$ qualifies, and $r=R$. Conversely, if $p_i\leq ar$, the original and forced vectors have the same count at threshold $ar$, so rank $r$ qualifies originally. Coordinatewise monotonicity of the largest qualifying rank gives $R\leq r$, hence $R=r$ and $i$ is rejected. This proves, with all non-strict ties retained,
$$
\frac{\mathbf1\{i\in\mathcal R_q(p)\}}{R\vee1}
=\frac{\mathbf1\{p_i\leq ar\}}r.
$$
Applying this equality to the product law just proved gives the displayed formula for $C_i$ in item 2. No independence between different components of $W_i$ was used.

### Finite crossings and the signed jump formula

On a fixed branch, the count at a grid threshold $ak$ changes only when
$$
|\theta_j+s\rho_{ji}x+w_j|=t_k,\qquad x=z(u)>0.
$$
For $\rho_{ji}\ne0$ these equations give exactly the two signed roots listed in item 2. For $\rho_{ji}=0$ the coordinate is constant and its contribution at every grid threshold is constant, including persistent equality. There are at most $2N(N-1)$ possible roots on a branch. The rank is constant between the distinct roots, and at each root its two traces are computed by the full step-up maximum. Coincident roots use one simultaneous rank change. Crossing $T_j=0$ alone cannot change the rank, since its p-value is then one and all grid thresholds are at most $q<1$.

On a rank-constant interval $H_i^s(u,w)=\min\{u/r,a\}$ is continuous and piecewise linear, with almost-everywhere derivative $\mathbf1\{u<ar\}/r$. The additional clipping kink $u=ar$ does not affect integration. Its endpoint limits are zero and $a$, because $H\leq u$ at zero, whereas $u>q$ implies $u/r>a$ for every $r\leq N$. Summing the fundamental theorem of calculus over all intervals gives
$$
\int_0^1\frac{\mathbf1\{u\leq ar_i^s(u,w)\}}{r_i^s(u,w)}\,du
=a+\sum_v\left[
\min\{v/r_i^s(v-,w),a\}
-\min\{v/r_i^s(v+,w),a\}\right].
$$
At $v\geq q$ both clipped terms are $a$. The finitely many isolated equality values are null for the uniform integral. Each jump has absolute value at most $a$ and the number of possible jumps is bounded for the fixed finite model, so expectations and sums can be interchanged. Summing over null coordinates and averaging the signs proves exactly
$$
\operatorname{FDR}_{\mathrm{BH}}^{(2)}
=N_0a+\frac12\sum_{i\in I_0}\sum_{s=\pm1}
\mathbb E_{W_i}\sum_{v<q} B_i^s(v,W_i).
$$
For $N=1$ the null rank is one and this reduces to $\operatorname{FDR}=q$ if the single mean is zero; if there are no nulls both sides are zero. This also checks the cases excluded from the nonempty crossing calculations.

### Face formula and the precise pivotal weight

Positive definiteness implies $|\rho_{ji}|<1$ and $K_i$ positive definite. Two different coordinates having coincident positive roots imposes a nontrivial affine equation on their residual coordinates, which has probability zero under their nonsingular joint Gaussian law. Different signed levels for the same coordinate have different roots. The finite union of these exceptional events has probability zero.

Write $v_{ij}^2=1-\rho_{ji}^2$. Gaussian regression within $W_i$ gives the conditional vector indexed by $\ell\ne i,j$ mean
$$
\left(\frac{(K_i)_{\ell j}}{v_{ij}^2}b\right)_{\ell\ne i,j}
$$
and covariance
$$
\left((K_i)_{\ell h}
-\frac{(K_i)_{\ell j}(K_i)_{jh}}{v_{ij}^2}\right)_{\ell,h\ne i,j}.
$$
These formulas follow by subtracting the indicated linear multiple of $W_{ij}$ and checking its cross covariance with $W_{ij}$ is zero, followed by Gaussian independence as above.

At the face $T_j=\epsilon t_k$, differentiation along $u$ gives
$$
\frac{dp_j}{du}
=\epsilon s\rho_{ji}\frac{\phi(t_k)}{\phi(x)},
\qquad x=z(u).
$$
If the rank changes, its two values must be $\ell<k$ and $k$. Indeed the classification of $p_j$ at every grid threshold other than $ak$ is unchanged on the two sides, while all other coordinates have unchanged classifications; thus only qualification of rank $k$ changes. A qualifying rank above $k$ would make both largest ranks identical. Put
$$
D_{\ell k}(u)=\min\{u/\ell,a\}-\min\{u/k,a\}\geq0.
$$
With the orientation of increasing $u$, the face weight is therefore
$$
\mathcal B_{i,s,j,k,\epsilon}(x)
=-\operatorname{sgn}(\epsilon s\rho_{ji})D_{\ell k}(p(x))
$$
on a pivotal face, and is zero otherwise. This proves the required signs without discarding either sign. The integer $\ell$ and pivotal event depend on the other residual coordinates and use their actual joint conditional Gaussian distribution.

Integrate a root weight first over $W_{ij}=w_j$, whose density is $v_{ij}^{-1}\phi(w_j/v_{ij})$. For the root labelled $(j,k,\epsilon)$ use
$$
w_j=\epsilon t_k-\theta_j-s\rho_{ji}x,\qquad |dw_j|=|\rho_{ji}|\,dx.
$$
Conditional expectation of the trace weight is the $\beta$ in item 4. Roots with $p(x)\geq q$ have zero weight; all other positive roots have $x>U$. Consequently
$$
\mathcal S
=\frac12\sum_{i\in I_0}\sum_{s=\pm1}
\sum_{\substack{j\ne i:\rho_{ji}\ne0}}\sum_{k=1}^N\sum_{\epsilon=\pm1}
\int_U^\infty\frac{|\rho_{ji}|}{v_{ij}}
\phi\!\left(\frac{\epsilon t_k-\theta_j-s\rho_{ji}x}{v_{ij}}\right)
\beta_{i,s,j,k,\epsilon}(x)\,dx.
$$
This is a root-location change of variables, so there is no additional null density $\phi(x)$. The null marginal is already present through $p(x)$ in $D_{\ell k}$. Finite root count and the bound $|\mathcal B|\leq a$ justify this calculation even though no model-independent bound follows from it.

### Attempted pairing: an exact reciprocal-rank telescoping

For $m=1,\ldots,N-1$ define the continuous nonnegative function
$$
d_m(u)=\min\{u/m,a\}-\min\{u/(m+1),a\}
=\begin{cases}
u/[m(m+1)],&0\leq u\leq am,\\
a-u/(m+1),&am\leq u\leq a(m+1),\\
0,&u\geq a(m+1).
\end{cases}
$$
Then $D_{\ell k}=\sum_{m=\ell}^{k-1}d_m$ exactly. More generally, for any simultaneous rank change, its weight equals
$$
B_i^s(v,w)=\sum_{m=1}^{N-1}d_m(v)
\left[\mathbf1\{r_i^s(v+,w)>m\}
-\mathbf1\{r_i^s(v-,w)>m\}\right].
$$
Define the actual sign-averaged rank-tail probability
$$
A_{im}(u)=\frac12\sum_{s=\pm1}
\Pr_{W_i}\{r_i^s(u,W_i)>m\}.
$$
Every residual path has finitely many jumps with a uniform finite bound for this fixed $N$, so $A_{im}$ has bounded variation (using one-sided versions at isolated values). The preceding identity and expectation give a signed Stieltjes integral. Since $d_m$ vanishes at both endpoints of $(0,1)$, integration by parts yields the exact formula
$$
\begin{aligned}
\mathcal S&=\sum_{i\in I_0}\mathcal S_i,\\
\mathcal S_i
&=\sum_{m=1}^{N-1}\int_0^1d_m(u)\,dA_{im}(u)\\
&=\sum_{m=1}^{N-1}\left[
\frac1{m+1}\int_{am}^{a(m+1)}A_{im}(u)\,du
-\frac1{m(m+1)}\int_0^{am}A_{im}(u)\,du\right].
\end{aligned}
$$
This performs the reciprocal-rank telescoping while preserving both signs and the entering and leaving faces. It is an identity, not the desired estimate. Using only $0\leq A_{im}\leq1$ gives
$$
\mathcal S_i\leq a\sum_{m=1}^{N-1}\frac1{m+1}
=a(H_N-1),\qquad H_N=\sum_{k=1}^N\frac1k,
$$
and hence only $\operatorname{FDR}\leq q(N_0/N)H_N$. This depends on $N$ and cannot yield the proposed theorem when $N$ may grow arbitrarily with $q$. No estimate relating these rank-tail probabilities across $i,m$ with the required common Gram-matrix constraints was established.

For $\Sigma=I_N$ every forced rank is independent of $u$; thus each $A_{im}$ is constant and each bracket in the exact formula vanishes. Equivalently there are no nonzero-$\rho$ faces. This checks $\mathcal S=0$ and $\operatorname{FDR}=qN_0/N$ directly.

### Two-coordinate audit and a failed local domination

The following genuine nonsingular model disproves a tempting intermediate assertion that opposite Gaussian face kernels are always dominated by the favorable kernels. It does not disprove the proposed global upper bound.

Take $N=2$, $\theta=(0,\mu)$ with $\mu\ne0$, and correlation $0<\rho<1$. Set $v=\sqrt{1-\rho^2}$, $q=p(U)$, and
$$
D_q(x)=\min\{p(x),q/2\}-p(x)/2,\qquad x>U.
$$
The forced rank for the null is two exactly when the other p-value is at most $q$. Thus only its level-$k=2$ faces are pivotal and their two ranks are one and two. Substituting the four signed faces into the established formula gives exactly
$$
\begin{aligned}
\mathcal S
=\frac{\rho}{2v}\int_U^\infty D_q(x)\bigg[
&\phi\!\left(\frac{U-\mu+\rho x}{v}\right)
+\phi\!\left(\frac{U+\mu+\rho x}{v}\right)\\
-&\phi\!\left(\frac{U-\mu-\rho x}{v}\right)
-\phi\!\left(\frac{U+\mu-\rho x}{v}\right)
\bigg]\,dx.
\end{aligned}
$$
For example choose $\rho=1/2$, $\mu=2U$, $x=2U$, and $U\geq1$. The bracket becomes
$$
\phi(0)+\phi(4U/v)-2\phi(2U/v)>0,
$$
since $2\exp(-2U^2/v^2)\leq2\exp(-8/3)<1$. Also $D_q(2U)>0$. By continuity the paired integrand is positive on an interval of positive length. A pointwise assertion that the sum of the two unfavorable kernels is bounded by the sum of the favorable ones is therefore false, already for this positive-definite two-coordinate covariance. Means cannot be omitted from a proposed sign pairing.

There is also an integrated positive example at arbitrarily small $q$. Fix $\rho\in(0,1)$ and take the allowed $q$-dependent mean $\mu=(1+\rho)U$. Then the preceding exact integral satisfies
$$
\lim_{U\to\infty}\frac{U\mathcal S}{q}
=\frac{\rho\log2}{4v\sqrt{2\pi}}>0.
$$
Here is a direct justification, including the tail estimate used. Integration by parts gives
$$
\overline\Phi(x)=\frac{\phi(x)}x-\int_x^\infty\frac{\phi(t)}{t^2}\,dt,
$$
so
$$
\frac{x}{1+x^2}\phi(x)\leq\overline\Phi(x)\leq\frac{\phi(x)}x.
$$
These bounds imply $p(U+y/U)/p(U)\to e^{-y}$ for fixed $y\geq0$. A translated tail integral also gives $p(U+y/U)/p(U)\leq e^{-y}$. With $x=U+y/U$,
$$
\frac{D_q(U+y/U)}q\longrightarrow
d(y)=\begin{cases}
(1-e^{-y})/2,&0\leq y\leq\log2,\\
e^{-y}/2,&y\geq\log2,
\end{cases}
\qquad
0\leq D_q(U+y/U)/q\leq e^{-y}/2.
$$
For this choice of $\mu$, the first kernel in the bracket tends to $\phi(0)$ and the other three tend to zero for each fixed $y$. The absolute bracket is at most $4\phi(0)$, so the displayed exponential bound gives dominated convergence on $y\geq0$. Finally $\int_0^\infty d(y)\,dy=(\log2)/2$, proving the limit. Thus even after integration and averaging both signs the correction need not be nonpositive. This positive correction is only of order $q/U$ and is consistent with the target scale $qU$.

The independent check and these two-coordinate checks settle limited audit cases only. They do not establish a uniform remainder as $\rho\to0$, $|\rho|\to1$, or $N\to\infty$, so checklist item 6 remains unchecked.

## Failure

Execution stopped at item 5. The exact signed face formula and its reciprocal-rank telescoping are established above, but the resulting rank-tail differences have no proved dimension- and mean-independent bound with leading term $qU/(2\sqrt{2\pi})$. Bounding them using only their ranges gives the harmonic factor $H_N$; the two-coordinate calculation rejects the attempted pointwise ordering of the opposite signed Gaussian face kernels. No cancellation or domination using the shared Gram matrix was obtained that improves this to a deterministic uniform $o(qU)$ remainder.

Consequently neither the optional $O(q\log U)$ remainder nor any uniform $o(qU)$ remainder has been proved. Merely naming the remaining face sum as a lemma would assume the central obligation. To make this route successful one would need a new, proved global relation among the actual $A_{im}$ (or an equivalent signed-cell relation) that uses their common Gaussian covariance structure and yields the displayed constant uniformly over all $N$ and means. Such a relation is not supplied by the identities here.

Items 5--8 remain unchecked. No finite-model upper bound from item 5 is available to extend in item 7 or optimize in item 8. This is failure of the proposed proof plan, not a counterexample or a falsification of the target theorem. The target statement, status, and proof content were left unchanged.
