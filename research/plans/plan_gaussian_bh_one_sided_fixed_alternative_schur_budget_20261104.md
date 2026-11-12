---
id: plan_gaussian_bh_one_sided_fixed_alternative_schur_budget_20261104
title: "Fixed-alternative covariance interpolation with an explicit Schur budget"
type: plan
status: failed
target_asset: gaussian_bh_one_sided_sharp_upper
inspired_by:
  - idea_07d633ccf6b2
  - idea_b8a514004c9b
  - idea_07179cf4b146
  - idea_45ea077b792d
adapts: []
---

## Goal

Target: [Sharp uniform upper-bound target for one-sided Gaussian BH](../assets/gaussian_bh_one_sided_sharp_upper.md).

Implement [Repair covariance interpolation by fixing the alternative block and its SDP completion geometry](../ideas/idea_07d633ccf6b2.md). Retain the actual true-null set and every actual mean. Freeze the original alternative covariance throughout interpolation. This plan supplies an explicit Schur-complement certificate and tests the concrete sufficient inequality (R) below. Neither (R) nor the more general constrained-completion certificate is established; either can fail while the target remains true. A rigorous failure of (R) ends this plan and must not be reported as a refutation of the target or of all constrained certificates.

Library searches for `Gaussian`, `fixed alternative block covariance interpolation constrained completion`, `semidefinite duality covariance block completion`, and `Gaussian BH corner trace budget` returned no matches. There are no library analogues or pending plans in the fresh context pack. No library result is invoked as a black box. The earlier failed plan's exact corner calculation is rechecked below for the new path, rather than treated as an approved dependency.

## Plan

1. [x] Fix arbitrary finite admissible $(N,\theta,\Sigma)$ and $0<q<1/2$. Write $J=\{i:\theta_i\leq0\}$, $A=[N]\setminus J$, $m_0=|J|$, $\delta_i=\mathbf1_{\{i\in J\}}$, $a=q/N$, $z_k=\overline\Phi^{-1}(ak)$, $u=\overline\Phi^{-1}(q)$, and $b_{ik}=z_k-\theta_i$. Treat $J=\varnothing$ directly, since the FDP is identically zero. First work with positive-definite $\Sigma$; step 9 supplies a uniform singular limit. After ordering indices as $(J,A)$, put
   $$
   S=\Sigma_{AA},\qquad B=\begin{pmatrix}I_{m_0}&0\\0&S\end{pmatrix},\qquad S_t=(1-t)B+t\Sigma,\quad 0\leq t\leq1.
   $$
   Check positive definiteness and unit diagonal. Thus $(\Sigma-B)_{ij}=\Sigma_{ij}$ for off-diagonal pairs with at least one null, and $(\Sigma-B)_{AA}=0$ exactly. Let $f(x)$ be the actual ordinary-BH FDP of $p_i=\overline\Phi(\theta_i+x_i)$ with labels $\delta_i$. Prove $\mathbb E_B f\leq qm_0/N$: for each $i\in J$, the forced-zero BH rank $R_i\geq1$ depends only on other coordinates, is independent of $p_i$ under $B$, and the deterministic identity is
   $$
   \frac{\mathbf1_{\{i\in\mathcal R_q\}}}{R\vee1}=\frac{\mathbf1_{\{p_i\leq aR_i\}}}{R_i}.
   $$
   Use $\Pr(p_i\leq s)=\overline\Phi(\overline\Phi^{-1}(s)-\theta_i)\leq s$. Alternatives may be arbitrarily dependent under this baseline. Do not shift a null mean to zero inside the FDP or assume monotonicity of total FDR in any mean.

2. [x] Recheck the mixed-corner coefficients from [Global Gaussian BH corner matrix and a diagonal budget certificate](plan_gaussian_bh_one_sided_global_corner_budget_20261104.md) by their finite-bin combinatorics. For $i\ne j$, encode each other coordinate by $h_v=\min(\{s:p_v\leq as\}\cup\{N+1\})$, and put
   $$
   C_s=\sum_{v\ne i,j}\mathbf1_{\{h_v\leq s\}},\qquad W_s=\sum_{v\ne i,j}\delta_v\mathbf1_{\{h_v\leq s\}},\qquad C_0=W_0=0.
   $$
   At thresholds $(k,l)$ define $f_{ef}$ by $h_i=k+1-e$, $h_j=l+1-f$ and $\Delta_{ij;k,l}=f_{11}-f_{10}-f_{01}+f_{00}$. These are one-sided limits of cells. For $k<l$ set $r=\max(\{0\}\cup\{s<k:C_s\geq s\})$. The gate $G_{ij}^{k,l}$ is
   $$
   C_k=k-1,\quad C_l=l-2,\quad C_s+1<s\ (k<s\leq l),\quad C_s+2<s\ (l<s\leq N).
   $$
   Prove that on this gate the four ranks are $(r,k,l,l)$ and
   $$
   \Delta_{ij;k,l}=\mathbf1_{G_{ij}^{k,l}}\left\{\frac{W_r}{r\vee1}-\frac{W_k+\delta_i}{k}\right\},
   $$
   and that the mixed difference is zero off the gate. Obtain $l<k$ by exchanging coordinates. For $k=l$, use the same $r$ and gate $C_k=k-2$, $C_s+2<s$ for $s>k$; the ranks are $(r,r,r,k)$ and
   $$
   \Delta_{ij;k,k}=\mathbf1_{G_{ij}^{k,k}}\left\{\frac{W_k+\delta_i+\delta_j}{k}-\frac{W_r}{r\vee1}\right\}.
   $$
   The equal-threshold gate is impossible at $k=1$. Check arbitrary rank jumps and all labels. Alternative/alternative corners can be nonzero as derivatives of $f$; their coefficient in the new covariance derivative is zero because the alternative block is frozen, not because these FDP differences vanish.

3. [x] Derive the exact new-path matrix. For the positive-definite Gaussian density $g_t$ with covariance $S_t$, set $b_{v0}=+\infty$, $b_{v,N+1}=-\infty$,
   $$
   D_{ij}(h)=\prod_{v\ne i,j}(b_{v,h_v},b_{v,h_v-1}),\quad
   P_t^{ij}(k,l,h)=\int_{D_{ij}(h)}g_t(b_{ik},b_{jl},x_{-ij})\,dx_{-ij}.
   $$
   Define a symmetric matrix $K$ with zero diagonal and zero $AA$ block, and for off-diagonal pairs with at least one null set
   $$
   K_{ij}=\frac12\int_0^1\sum_{k,l,h}\Delta_{ij;k,l}(h)P_t^{ij}(k,l,h)\,dt.
   $$
   Equivalently the inner sum over $h$ is
   $$
   \varphi_2(b_{ik},b_{jl};t\Sigma_{ij})\,
   \mathbb E_t[\Delta_{ij;k,l}\mid X_i=b_{ik},X_j=b_{jl}].
   $$
   Differentiate $g_t$ and integrate over its grid cells to prove
   $$
   \mathbb E_\Sigma f-\mathbb E_B f=\operatorname{tr}(\Sigma K).
   \tag{I}
   $$
   Check the factor $1/2$ and the absence of $AA$ derivatives. Retain the original $S$ inside every full-cell density and every conditional gate. Integrability for a fixed finite model follows from $|\Delta|\leq4$ and the pair-density bound proportional to $(1-t^2\Sigma_{ij}^2)^{-1/2}$; do not assert gate independence or interpolation monotonicity.

4. [x] Establish the constrained completion geometry directly. Write
   $$
   K=\begin{pmatrix}U&V\\V^{\mathsf T}&0\end{pmatrix},\qquad C=VSV^{\mathsf T}\succeq0.
   $$
   For any real $d$ such that $E=\operatorname{Diag}(d)-U\succ0$, set $H=V^{\mathsf T}E^{-1}V$ and
   $$
   M=\begin{pmatrix}\operatorname{Diag}(d)&0\\0&H\end{pmatrix}.
   $$
   Exhibit the exact factorization
   $$
   M-K=
   \begin{pmatrix}E^{1/2}\\-V^{\mathsf T}E^{-1/2}\end{pmatrix}
   \begin{pmatrix}E^{1/2}&-E^{-1/2}V\end{pmatrix}\succeq0.
   $$
   Consequently every $\Gamma\succeq0$ satisfying $\Gamma_{ii}=1$ for $i\in J$ and $\Gamma_{AA}=S$ has
   $$
   \operatorname{tr}(\Gamma K)\leq
   \sum_{i\in J}d_i+\operatorname{tr}(HS)
   =\sum_{i\in J}d_i+\operatorname{tr}(E^{-1}C).
   \tag{D}
   $$
   Prove PSD trace pairing by a Gram/eigenvector decomposition, without importing SDP duality. The generating $\Sigma$ is feasible. This is the explicit dual cost; replacing $S$ by an arbitrary alternative correlation matrix is forbidden. No strong-duality theorem is needed.

5. [x] Construct one completely explicit coefficient family for (D), so the remaining analytic claim is a testable inequality. Put
   $$
   r_i=\sum_{j\in J\setminus\{i\}}|U_{ij}|,\qquad
   c_i=\sqrt{C_{ii}}=\left\|\sum_{a\in A}V_{ia}v_a\right\|,
   $$
   where $S_{ab}=\langle v_a,v_b\rangle$ is a Gram representation of the actual alternative block. Empty alternative sums give $c_i=0$. For $\epsilon>0$, prescribe
   $$
   d_i^{(\epsilon)}=r_i+c_i+\epsilon,\quad
   E_\epsilon=\operatorname{Diag}(r)-U+\operatorname{Diag}(c+\epsilon),\quad
   H_\epsilon=V^{\mathsf T}E_\epsilon^{-1}V.
   $$
   Verify
   $$
   \operatorname{Diag}(r)-U=
   \sum_{i<j,\ i,j\in J}|U_{ij}|(e_i-\operatorname{sgn}(U_{ij})e_j)
   (e_i-\operatorname{sgn}(U_{ij})e_j)^{\mathsf T}\succeq0.
   $$
   Thus $E_\epsilon\succ0$, and inversion order gives the explicit cost bound
   $$
   \sum_i d_i^{(\epsilon)}+\operatorname{tr}(E_\epsilon^{-1}C)
   \leq\sum_i r_i+\sum_i c_i+m_0\epsilon+
   \sum_i\frac{c_i^2}{c_i+\epsilon}
   \leq\mathcal Q(K,S)+m_0\epsilon,
   $$
   where
   $$
   \mathcal Q(K,S)=\sum_{i\ne j,\ i,j\in J}|K_{ij}|+
   2\sum_{i\in J}\sqrt{\sum_{a,b\in A}K_{ia}S_{ab}K_{ib}}.
   $$
   The concrete sufficient claim to prove or refute is the existence of a numerical $C_*$, independent of $q,N,\theta,\Sigma$, such that
   $$
   \boxed{\quad \mathcal Q(K,S)\leq
   \frac{\varphi(u)}{\sqrt{2\pi}}+
   C_*q\{1+\log(1+u)\}\quad}
   \tag{R}
   $$
   for every finite model above. This is a stronger claim than the scalar target: it bounds an explicit null-row and alternative-Gram certificate, including directions other than the generating covariance. Its truth is unknown. Keep absolute values outside the integrated signed $K_{ij}$, and keep the alternative quadratic form intact.

6. [ ] Test (R) analytically before attempting its uniform proof. For $N=2$ with at least one null, compute
   $$
   K_{12}=\frac12\int_0^1\left\{
   -\delta_1\varphi_2(b_{11},b_{22};t\Sigma_{12})
   -\delta_2\varphi_2(b_{12},b_{21};t\Sigma_{12})
   +\frac{\delta_1+\delta_2}{2}\varphi_2(b_{12},b_{22};t\Sigma_{12})
   \right\}\,dt;
   $$
   here $\mathcal Q=2|K_{12}|$ for one or two nulls. Check this against the Schur cost and the two-dimensional PSD completion bound. Then test the failed plan's weak-equicorrelation alternative-only family, heterogeneous negative nulls, the actual-boundary-null contribution obstruction, all-null and mixed singular rank-one limits, and the singular simplex. For the alternative-only family the new path is constant and the actual gain in (I) is zero; this does not imply that the transverse corner matrix $K$ or its stronger cost $\mathcal Q$ is zero. Check that distinction explicitly. A disproof of uniform (R) must provide an admissible analytic family for which
   $$
   \frac{\mathcal Q(K,S)-\varphi(u)/\sqrt{2\pi}}
   {q\{1+\log(1+u)\}}
   $$
   is unbounded, or an equivalent sharp-leading-order violation. A finite numerical excess with an unspecified $C_*$ is insufficient. If such a family is proved, record the failed subclaim (R) and stop this plan; leave the general optimized cost $\inf_d\{\sum d_i+\operatorname{tr}((\operatorname{Diag}(d)-U)^{-1}C)\}$ and the original scalar target unresolved.

7. [ ] Attempt the actual analytic proof of (R) using a precise signed-kernel formulation. For fixed $\sigma_{ij}\in[-1,1]$ on null/null pairs and vectors $w_i$ with $\|w_i\|\leq1$, define coefficients
   $$
   \lambda_{ij}=\sigma_{ij}\quad(i<j,\ i,j\in J),\qquad
   \lambda_{ia}=\langle w_i,v_a\rangle\quad(i\in J,a\in A).
   $$
   The exact support identity is
   $$
   \mathcal Q(K,S)=\sup_{\sigma,w}\left\{
   2\sum_{i<j,\ i,j\in J}\lambda_{ij}K_{ij}
   +2\sum_{i\in J,a\in A}\lambda_{ia}K_{ia}\right\}.
   \tag{G}
   $$
   Insert the full-cell formula from step 3, so the expression in braces is the integral of $\sum_{\{i,j\}\cap J\ne\varnothing}\lambda_{ij}\sum_{k,l,h}\Delta_{ij;k,l}(h)P_t^{ij}(k,l,h)$, taking each unordered pair once. All coefficients and gates are explicit. The needed kernel inequality is that this signed integral is bounded by the right side of (R) uniformly over these fixed $\sigma,w$. Derive it by grouping equal and unequal corners over the same actual rank gates before any absolute values. On each unequal-corner interval retain the exact identity, for $r>0$,
   $$
   \frac{W_k+\delta_i}{k}-\frac{W_r}{r}
   =\frac{W_k-W_r+\delta_i}{k}-\frac{W_r(k-r)}{rk},
   $$
   and use $(W_k+\delta_i)/k$ for $r=0$; equal corners use $\delta_i+\delta_j$. Track the negative old-null dilution term with the new admissions, rather than charging them separately. Write an explicit rank-interval allocation showing that the leading mass is charged to
   $$
   \frac1{\sqrt{2\pi}}\int_0^\infty\min\{q,\overline\Phi(v)\}\,dv
   =\frac{\varphi(u)}{\sqrt{2\pi}}.
   $$
   Every remaining endpoint, rank and integration term must have total at most $C_*q\{1+\log(1+u)\}$ with a single constant. The elementary capacity identity alone proves no such allocation. If this signed weighted inequality cannot be derived, identify its exact unresolved subclaim; do not substitute unweighted Schur positivity, per-null budgets, a $q\log N$ remainder, or a statement equivalent only to the desired FDR bound.

8. [ ] Conditional on a proof of (R), apply (D) to the generating $\Gamma=\Sigma$, send $\epsilon\downarrow0$ for each fixed finite model, and combine with (I) and step 1 to obtain
   $$
   \operatorname{FDR}_{\mathrm{BH}}^{(1)}(q;N,\theta,\Sigma)
   \leq q+\frac{\varphi(u)}{\sqrt{2\pi}}+
   C_*q\{1+\log(1+u)\}.
   $$
   Check $A=\varnothing$ with the empty alternative block, $J=\varnothing$ separately, and every negative composite-null mean at its original boundary. None of the coefficient construction requires a covariance rank, entropy, mean-size, null-proportion or dimension restriction.

9. [ ] Extend the finite-model inequality to singular $\Sigma$ by $\Sigma^{(\eta)}=(1-\eta)\Sigma+\eta I$, using its own frozen alternative block $S^{(\eta)}$. The same $C_*$ must work for all $\eta>0$. Couple $X^{(\eta)}=\sqrt{1-\eta}X+\sqrt\eta Z$ with independent standard $Z$. Each coordinate of $X$ has a continuous variance-one marginal; hence the finite grid boundaries have zero probability, $f(X^{(\eta)})\to f(X)$ almost surely, and bounded convergence passes the inequality to $\eta=0$. No uniform boundary-avoidance rate is needed. Finally derive Mills asymptotics $\varphi(u)=q\{u+O(1/u)\}$, $u/\sqrt{2\log(1/q)}\to1$, and $\log(1+u)=o(u)$. Take the model supremum only after establishing the same finite-level bound for every model. This yields precisely the target upper constant $1/\sqrt\pi$ with arbitrary $q$-dependent dimensions, means and covariance matrices.

## Verification

The nonconditional algebraic obligations are the baseline forced-zero identity, the finite-bin corner formulas, new-path interpolation (I), the Schur factorization and explicit coefficients in (D), and the support identity (G). The essential unproved analytic obligation is (R), with the exact integrated matrix and original alternative Gram geometry. A proof must give the capacity allocation in step 7 and one dimension- and mean-uniform remainder constant; finite diagnostics or a certificate definition do not establish it. Only after this obligation succeeds do steps 8--9 prove the unchanged target. A rigorous refutation of (R) fails this sufficient plan alone. A failure to find a proof must remain an obstruction, without declaring either the corrected general certificate or the theorem false.

## Assumed definitions

All five model definitions in the current context pack are approved: [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md), [Gaussian test p-values and true nulls](../definitions/gaussian_test_pvalues.md), [ordinary Benjamini-Hochberg step-up procedure](../definitions/benjamini_hochberg_step_up.md), [false discovery rate](../definitions/false_discovery_rate.md), and [uniform worst-case Gaussian BH false discovery rate](../definitions/gaussian_worst_case_bh_fdr.md). No draft definition, unproved dependency, undeclared library conclusion, mean-reduction principle or unrestricted matrix certificate is assumed. The inspired ideas propose methods and stress cases; their claims are not black-box premises.

## Difference from failed plans

- `plan_gaussian_bh_one_sided_global_corner_budget_20261104`: Its unrestricted diagonal certificate (C) has an alternative-only weak-correlation counterfamily with unbounded dual trace. The new path fixes $\Sigma_{AA}$, removes all $AA$ covariance derivatives, and restricts test completions to that same original alternative block. The alternative part of the explicit dual cost is $\operatorname{tr}(H\Sigma_{AA})$, and its prescribed Schur coefficients depend on the Gram quantity $K_{JA}\Sigma_{AA}K_{AJ}$. The new sufficient inequality is (R), which is independently testable and unproved; the failed (C) is not reused. The earlier corner combinatorics are rechecked, and a constant interpolation path is distinguished from a zero transverse certificate cost.

## Failure

Execution on 2026-11-04 establishes the algebra in steps 1--5 and the support identity (G), but refutes the sufficient inequality (R) in step 6. Two analytic families below isolate both terms of the proposed cost. The second is positive definite, has a constant fixed-alternative interpolation path, and violates (R) along explicit levels tending to zero. Thus step 7's proposed signed-kernel bound for the support set in (G) is false. Steps 8--9 cannot follow from this plan. The target asset and its statement are unchanged. Neither the general optimized constrained-completion cost nor the scalar FDR target is refuted.

### Established algebra and exact corner coefficients

For positive-definite $\Sigma$, the principal block $S$ and the block diagonal $B$ are positive definite, and so is every convex combination $S_t$. Diagonals remain one and the $AA$ block is exactly $S$ throughout. When $J$ is empty the FDP vanishes. For $i\in J$, force $p_i$ to zero and let $R_i$ be the resulting BH rank. If $p_i\leq aR_i$, restoring $p_i$ leaves rank $R_i$ unchanged; conversely, if $i$ is rejected at rank $R$, forcing its p-value to zero cannot change any qualifying rank above $R$, because $i$ was already counted at every such threshold. Hence $R_i=R$ on rejection and the forced-zero identity in step 1 holds, including tied p-values. Under $B$, $p_i$ is independent of $R_i$, and
$$
\mathbb E_B\frac{\mathbf1_{\{i\in\mathcal R_q\}}}{R\vee1}
=\mathbb E_B\frac{\overline\Phi(z_{R_i}-\theta_i)}{R_i}
\leq a.
$$
Summing proves $\mathbb E_B f\leq am_0$. Equality holds when every true-null mean is zero, regardless of dependence among alternatives. No null mean has been changed inside any FDP comparison.

For $k<l$, the counts of p-values at most $as$ in the four adjacent cells are $C_s$ for $s<k$, $C_k+e$ at $s=k$, $C_s+1$ for $k<s<l$, $C_l+1+f$ at $s=l$, and $C_s+2$ for $s>l$. A qualifying common rank above $l$ makes all four FDPs identical. A qualifying common rank strictly between $k$ and $l$ makes the FDP independent of $e$; hence the mixed difference again vanishes. At $l$, dependence on $f$ requires precisely $C_l=l-2$; at $k$, dependence on $e$ requires precisely $C_k=k-1$. In the absence of the excluded common ranks, these conditions give the gate in step 2 and the ranks $(r,k,l,l)$ for $(00,10,01,11)$. At rank $l$ both crossing coordinates are rejected in either case, and therefore
$$
\Delta_{ij;k,l}=\mathbf1_G
\left\{\frac{W_r}{r\vee1}-\frac{W_k+\delta_i}{k}\right\}.
$$
The same count argument shows zero mixed difference whenever any gate condition fails; interchange coordinates for $l<k$. For $k=l$, first exclude common qualifying ranks above $k$. Then necessarily $C_k\leq k-2$: otherwise at least $k+1$ coordinates would already be counted at threshold $k$, forcing a common qualifying rank above $k$. If $C_k<k-2$, no state qualifies at $k$ and all four FDPs agree. If $C_k=k-2$, only $(11)$ qualifies, giving ranks $(r,r,r,k)$ and the stated equal-corner formula. In particular $k=1$ is impossible. This argument permits every old rank $r$, every jump, and arbitrary labels.

Writing $D=\Sigma-B$, Gaussian density differentiation gives
$$
\partial_tg_t=\frac12\sum_{i,j}D_{ij}\partial_{ij}g_t
=\sum_{i<j:\{i,j\}\cap J\ne\varnothing}
\Sigma_{ij}\partial_{ij}g_t.
$$
Integrating by parts twice over the finite grid gives the coefficient $\Delta_{ij;k,l}$ multiplying the full-cell integral $P_t^{ij}(k,l,h)$. Thus each unordered pair contributes $2\Sigma_{ij}K_{ij}$, proving (I) with exactly the factor $1/2$ in the definition of $K$. The $AA$ coefficients vanish because $D_{AA}=0$, not because alternative/alternative FDP corners vanish. The original block $S$ remains in every joint density and conditional gate. The finite sum is integrable in $t$ by the bivariate density bound in step 3. No sign or independence of a conditional gate is asserted. At $N=2$ the only nonzero corners are $(1,2)$ with coefficient $-\delta_1$, $(2,1)$ with coefficient $-\delta_2$, and $(2,2)$ with coefficient $(\delta_1+\delta_2)/2$; this gives precisely the displayed formula in step 6, including composite-null boundaries.

For $E=\operatorname{Diag}(d)-U\succ0$, multiplication of the two factors in step 4 gives block matrix $(E,-V;-V^{\mathsf T},V^{\mathsf T}E^{-1}V)=M-K$. If $L\succeq0$ and $\Gamma=\sum_b\gamma_bx_bx_b^{\mathsf T}\succeq0$ with $\gamma_b\geq0$, then $\operatorname{tr}(\Gamma L)=\sum_b\gamma_bx_b^{\mathsf T}Lx_b\geq0$. Applying this to $M-K$ yields (D) with the actual block $S$. The signed-edge expansion in step 5 proves $\operatorname{Diag}(r)-U\succeq0$, so $E_\epsilon\succeq\operatorname{Diag}(c+\epsilon)\succ0$. Inversion reverses this order (conjugate by the positive square root and invert the eigenvalues), and PSD trace pairing with $C$ gives
$$
\operatorname{tr}(E_\epsilon^{-1}C)
\leq\sum_i\frac{C_{ii}}{c_i+\epsilon}
=\sum_i\frac{c_i^2}{c_i+\epsilon}\leq\sum_i c_i.
$$
This proves the prescribed cost estimate, but does not prove (R). In the $N=2$ check, writing $k=K_{12}$ gives $\mathcal Q=2|k|$ with either one or two nulls. With one null the Schur objective is $d+k^2/d$, minimized at $d=|k|$; with two nulls the signed diagonal completion has cost $2|k|$. Both agree with the two-dimensional PSD completion bound $\max_{|\gamma|\leq1}2\gamma k=2|k|$. Finally independent choices of $\sigma_{ij}$ maximize each signed null/null entry to its absolute value, while each $w_i$ maximizes its inner product with $\sum_aK_{ia}v_a$ to that vector's norm. This proves (G) exactly. The counterfamilies below show that this particular support set is too large for step 7's proposed kernel bound.

### All-null obstruction and a signed completion that avoids it

Fix $q_0=1/4$, let all means be zero, and take the positive-definite equicorrelation model
$$
\Sigma_{N,\rho}=(1-\rho)I_N+\rho\mathbf1\mathbf1^{\mathsf T},
\qquad 0<\rho<1.
$$
Here $B=I_N$, and exchangeability makes every off-diagonal entry of $K$ equal to a scalar $\kappa_{N,\rho}$. If $F_{N,\rho}=\mathbb E_{\Sigma_{N,\rho}}f$, baseline equality and (I) give the exact identities
$$
F_{N,\rho}-q_0=\rho N(N-1)\kappa_{N,\rho},\qquad
\mathcal Q(K,\varnothing)=\frac{|F_{N,\rho}-q_0|}{\rho}.
$$
We next prove that, for every sufficiently small fixed $\rho>0$, $F_{N,\rho}<q_0/2$ for all sufficiently large $N$.

Represent $X_i=\sqrt\rho Z+\sqrt{1-\rho}Z_i$ with independent standard normals. Conditional on $Z=z$, the p-values are iid with cdf
$$
F_{z,\rho}(t)=\overline\Phi\left(
\frac{\overline\Phi^{-1}(t)-\sqrt\rho z}{\sqrt{1-\rho}}
\right).
$$
For every finite $z$ and fixed $\rho>0$, $F_{z,\rho}(t)/t\to0$ as $t\downarrow0$, by the Gaussian tail exponents. The conditional density of $X_i$ relative to a standard normal density is
$$
L_{z,\rho}(x)=\frac1{\sqrt{1-\rho}}
\exp\left\{-\frac{(x-\sqrt\rho z)^2}{2(1-\rho)}+\frac{x^2}{2}\right\},
\qquad
\sup_xL_{z,\rho}(x)=\frac{e^{z^2/2}}{\sqrt{1-\rho}}.
$$
For $z\leq0$ and $t\leq q_0$, the normal threshold is positive and $F_{z,\rho}(t)\leq t$. For $0<z<c_\rho$, where
$$
c_\rho=\sqrt{2\log\{\sqrt{1-\rho}/q_0\}},
$$
the density-ratio bound gives $\sup_{0<t\leq q_0}F_{z,\rho}(t)/t<1/q_0$.

For completeness, if a fixed cdf $F$ satisfies $F(t)/t\to0$ and $r=q_0\sup_{0<t\leq q_0}F(t)/t<1$, its iid BH rejection probability tends to zero. Indeed the count at threshold $q_0k/N$ is binomial with mean at most $rk$, so for any integer $K$,
$$
\Pr\{\exists k>K:\operatorname{Bin}(N,F(q_0k/N))\geq k\}
\leq\sum_{k>K}\exp\{-k(\log(1/r)-1+r)\}.
$$
For each $k\leq K$, its mean $NF(q_0k/N)=q_0k\,F(q_0k/N)/(q_0k/N)$ tends to zero, and Markov's inequality finishes the finite set of small ranks. First let $N\to\infty$, then $K\to\infty$. Apply this lemma conditionally for every $z<c_\rho$, and use bounded convergence there and the bound one on the remaining event, to obtain
$$
\limsup_{N\to\infty}F_{N,\rho}\leq\overline\Phi(c_\rho).
$$
As $\rho\downarrow0$, $c_\rho\to\sqrt{2\log4}$, and Mills' bound gives
$$
\overline\Phi(\sqrt{2\log4})
<\frac{q_0}{\sqrt{2\pi}\sqrt{2\log4}}<\frac{q_0}{2}.
$$
Choose $\rho_j\downarrow0$ small enough for this strict inequality to persist, and finite integers $N_j\geq\rho_j^{-3}$ large enough that $F_{N_j,\rho_j}\leq q_0/2$. The model sequence is admissible and positive definite, and
$$
\mathcal Q(K_j,\varnothing)\geq\frac{q_0}{2\rho_j}\longrightarrow\infty.
$$
The right side of (R) is a fixed finite number at $q_0$ for every finite $C_*$. This alone refutes (R).

This family also shows exactly why the row-absolute-value recipe need not reflect the optimized signed completion. Here $\kappa<0$; write $h=-\kappa>0$, so $U=hI-h\mathbf1\mathbf1^{\mathsf T}$. The signed choice $d_i=h+\epsilon$ gives
$$
\operatorname{Diag}(d)-U=\epsilon I+h\mathbf1\mathbf1^{\mathsf T}\succ0,
\qquad \sum_i d_i\downarrow Nh=\frac{\mathcal Q}{N-1}.
$$
This limiting cost is optimal: take the PSD unit-diagonal simplex correlation matrix with off-diagonals $-1/(N-1)$ in (D), whose pairing with $U$ is $Nh$. Since $\mathcal Q\leq q_0/\rho$ and $N_j\geq\rho_j^{-3}$, the optimized cost in this counterfamily tends to zero. Thus the refutation of (R) cannot be promoted to a refutation of the corrected signed dual.

### Explicit small-level obstruction in the alternative Gram term

The second family isolates the alternative Gram term even when the generating nulls are independent. For integers $r\to\infty$, set
$$
q_r=e^{-r},\quad N_r=2\lceil e^{r^2}\rceil=2n_r,\quad
a_r=q_r/N_r,\quad \mu_r=\overline\Phi^{-1}(q_r/2),\quad
\eta_r=N_r^{-12}.
$$
There are $n_r$ true nulls with mean zero and $n_r$ alternatives with mean $\mu_r>0$. Let the null coordinates be independent standard normals, independent of the alternatives, and give the latter the positive-definite covariance
$$
S_\eta=(1-\eta)\mathbf1\mathbf1^{\mathsf T}+\eta I_{n_r},\qquad
\Sigma_\eta=\operatorname{diag}(I_{n_r},S_\eta)=B.
$$
Thus every interpolation path in this family is constant and positive definite. Its actual FDR is exactly $q_r/2$ by the forced-zero calculation; the gain in (I) is zero. The transverse matrix $K$ still need not vanish.

Suppress $r$ temporarily. Represent alternative coordinates by $X_a=\sqrt{1-\eta}Z_0+\sqrt\eta Z_a$, and let $f_\eta$ be the actual FDP on these observations. The original alternative block has the Gram vectors $v_a=\sqrt{1-\eta}e_0+\sqrt\eta e_a$. At the constant path, the exact corner formula is $2K_{ia}=\mathbb E[\partial_{ia}f_\eta]$, interpreted distributionally. Gaussian integration by parts in the independent variables $X_i,Z_0$ gives
$$
\mathbb E[X_iZ_0f_\eta]
=2\sqrt{1-\eta}\sum_{a\in A}K_{ia}
=2\left\langle e_0,\sum_{a\in A}K_{ia}v_a\right\rangle.
$$
All expectations are finite since the FDP is bounded; the distributional identity also follows directly by integrating the finite grid. Therefore the actual, unmodified Gram cost satisfies
$$
\mathcal Q(K,S_\eta)\geq
2\sum_{i\in J}\left\|\sum_aK_{ia}v_a\right\|
\geq\sum_{i\in J}|\mathbb E[X_iZ_0f_\eta]|.
\tag{F1}
$$
We bound these scores using the auxiliary singular coupling $\eta=0$, and then give an explicit error for the positive-definite family. Define $z(s)=\overline\Phi^{-1}(s)$ and the Mills ratio $m(x)=\varphi(x)/\overline\Phi(x)$. Conditional on $Z_0=z$, the alternatives have deterministic common p-value $\overline\Phi(\mu+z)$ and the nulls remain independent. The forced-zero rank $R_i$ is independent of $X_i$. The exact identity is
$$
G(z):=\mathbb E[X_if_0\mid Z_0=z]
=\mathbb E\left[\frac{\varphi(z(aR_i))}{R_i}\,\middle|\,Z_0=z\right]
=a\,\mathbb E[m(z(aR_i))\mid Z_0=z]\geq0.
\tag{F2}
$$
To verify that the other null terms contribute zero in (F2), vary only the mean of coordinate $i$ near zero while keeping the true-null labels fixed in the function. For each other null $j$, its uniform independent p-value gives expected contribution exactly $a$ for every value of the varied mean, since its own forced-zero rank excludes $p_j$. Its Gaussian score derivative is therefore zero. Coordinate $i$ contributes $\mathbb E[\overline\Phi(z(aR_i)-t)/R_i]$ under mean $t$, whose derivative at zero is the displayed expression. This is a differentiation identity for a fixed labelled function, not a replacement of the target's composite nulls.

Put $c=z(q)-\mu<0$. When $z<c$, all alternative p-values exceed $q$, so $R_i$ is the forced-zero rank $R_0$ among $n$ nulls at BH level $q/2$. For integers $L\geq2$,
$$
\Pr(R_0\geq L)
\leq\sum_{s=L}^{n}\Pr\{\operatorname{Bin}(n-1,as)\geq s-1\}
\leq\frac{(eq)^{L-1}}{1-eq}.
$$
Indeed the binomial mean is at most $(q/2)s$ and $s/(s-1)\leq2$. For every $q\leq1/4$, choosing $L=10$ makes this upper bound less than $1/2$. Since $m(x)\geq x$ for $x>0$, (F2) implies, for all sufficiently large $n$,
$$
G(z)\geq \frac a2 z(aL),\qquad z<c.
$$
When $z>0$, the common alternative p-value is less than $q/2$, so the forced-zero configuration has a qualifying rank at least $n+1$. Consequently $aR_i>q/2$, and monotonicity of $m$ gives $G(z)\leq am(\mu)$. Here monotonicity follows from $m'(x)=m(x)(m(x)-x)>0$; the Mills bound proves $m(x)>x$ for $x\geq0$, and it is immediate for $x<0$. On $c\leq z\leq0$, the product $zG(z)$ is nonpositive. Integrating the three ranges proves
$$
\mathbb E[X_iZ_0f_0]
\leq-\frac a2\varphi(c)z(aL)+am(\mu)\varphi(0).
\tag{F3}
$$

To pass to the explicitly prescribed $\eta=N^{-12}$, couple the same nulls, $Z_0$, and $Z_a$, and take $h=N^{-4}$. Each alternative displacement from $Z_0$ has variance at most $2\eta$. If all these displacements are at most $h$ in absolute value, and $Z_0$ is more than $h$ from each of the $N$ thresholds $z(ak)-\mu$, no alternative changes its bin and $f_\eta=f_0$. Gaussian tails and a union bound give the uniform estimate
$$
\Pr(f_\eta\ne f_0)
\leq2\varphi(0)Nh+2n\exp\{-h^2/(4\eta)\}
=2\varphi(0)N^{-3}+N e^{-N^4/4}.
$$
Since $\mathbb E[X_i^2Z_0^2]=1$, Cauchy--Schwarz yields
$$
\sum_{i\in J}|\mathbb E[X_iZ_0(f_\eta-f_0)]|
\leq n\sqrt{\Pr(f_\eta\ne f_0)}=O(N^{-1/2}).
\tag{F4}
$$
Combining (F1)--(F4) with $na=q/2$ therefore gives
$$
\mathcal Q(K,S_\eta)
\geq\frac q2\left\{\frac{\varphi(c)}2z(aL)-m(\mu)\varphi(0)\right\}
-O(N^{-1/2}).
\tag{F5}
$$
In the explicit family, $z(a_rL)\sim\sqrt2\,r$, $m(\mu_r)=O(\sqrt r)$, $c_r\to0$, and $N_r^{-1/2}=o(q_r)$. These statements follow from the elementary Mills estimates: $z(s)\sim\sqrt{2\log(1/s)}$, $m(x)=x+O(1/x)$, and $z(q)-z(q/2)\to0$ (the latter follows also by integrating $1/\varphi(z(s))$ from $q/2$ to $q$ and bounding the difference by $1/z(q)$). Thus
$$
\mathcal Q(K_r,S_r)\geq
\left\{\frac{\varphi(0)}{2\sqrt2}+o(1)\right\}q_r r.
\tag{F6}
$$
On the other hand, $u_r=z(q_r)\sim\sqrt{2r}$, so the proposed leading term in (R) is $O(q_r\sqrt r)$ and its remainder is $O(C_*q_r\log r)$. In particular
$$
\frac{\mathcal Q(K_r,S_r)-\varphi(u_r)/\sqrt{2\pi}}
{q_r\{1+\log(1+u_r)\}}\longrightarrow+\infty.
$$
This is an explicit positive-definite small-level refutation of (R), with the original fixed alternative Gram form retained exactly. No alternative/alternative derivative was used.

### Exact failure level and verification record

Steps 1--5 and (G) are valid. Step 6 decisively refutes (R), so its instruction to stop the plan applies; a capacity allocation proving step 7 over the support set (G) cannot exist. The all-null example gives an explicit signed completion that avoids its row-absolute divergence. The mixed example refutes even the alternative Gram part of the prescribed additive recipe, while its actual FDR remains $q_r/2$. Its optimized joint cost is not evaluated here: a null-block choice in $\operatorname{Diag}(d)-U$ can interact with the alternative term, so (F6) does not refute the general constrained cost. A replacement plan must bound that joint signed cost or use a different scalar argument; neither a per-null surrogate nor an unrestricted completion is justified by this execution.

The exact rational unit diagnostic `/private/tmp/bh_fixed_alt_corner_unit_20261104.py` checked all 4,204 mixed-corner cases with $2\leq N\leq4$, every label pattern and every bin configuration for the remaining coordinates. It passed; the analytic count argument above supplies the proof for arbitrary $N$. Read-only `research-maintenance validate` returned zero problems. No large computation, source-asset edit, approval record, loop state or setting was changed.
