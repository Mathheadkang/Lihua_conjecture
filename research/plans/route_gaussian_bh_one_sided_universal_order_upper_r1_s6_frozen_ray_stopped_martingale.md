---
type: plan
title: >-
  Universal one-sided order via the frozen-ray maximal inequality and a BH
  transfer
status: pending
target_asset: gaussian_bh_one_sided_universal_order_upper
route_lemmas:
  - gaussian_frozen_ray_order_bound
  - gaussian_bh_near_boundary_frozen_ray_transfer
route_title: via frozen-ray maximal inequality and BH transfer
origin: researcher
inspired_by:
  - idea_bc183ea2b6fa
  - idea_2bb31516b09b
  - idea_9f8ffb204424
tags:
  - frozen-ray
route_round: 1
reduction_digest: a3b1ce972c9d56c533cef3447eb9618f49d5ef5fa19517b0900caebc38f28bc0
reduction_inputs:
  gaussian_bh_one_sided_universal_order_upper: 4fe10575d36df3f3f1d7a5d3b02045f11cc1642e336a0a94fe50ce0a9f321484
  gaussian_bh_fractional_frame_surface_kernel: 73320a924701f1ff16a1f07678da1f8aec14bcaa701710f663f9a9f5b0d67369
  gaussian_bh_conditional_compound_calibration: 72c9382ceb1913470689b87acb600c14e6c36c033da80c5f6d7559dceeaafc01
  gaussian_bh_negative_null_boundary_strip: 8cb3729d0db20bedb0d623cce2676cfa7d01e08b10180884af70e5a810e0b568
  gaussian_bh_conditional_subpoisson_calibration: 690ddb01c6ce756d2366c4901fffdbdfa396da6353901f8ea0cfffa828f89b29
  gaussian_frozen_ray_order_bound: 282dae85ea4644795f6594864fde635d6b47cfbb089d6aaaa5923db5d8b578ac
  gaussian_bh_near_boundary_frozen_ray_transfer: be073e791d4239baa7b5f7c3e9a5802f0f6c644848af48ae7b3362b87b76b57d
reduction_verified_digest: a3b1ce972c9d56c533cef3447eb9618f49d5ef5fa19517b0900caebc38f28bc0
reduction_checked: true
---

## Goal

Target: [Universal order upper bound for one-sided Gaussian BH](../assets/gaussian_bh_one_sided_universal_order_upper.md).

Prove the unchanged statement $F_1(q)\leq C_1q\sqrt{\log(1/q)}$ for $0<q\leq q_{0,1}$, with universal constants, over every finite $N$, every $\theta\in\mathbb R^N$ and every unit-diagonal PSD $\Sigma$ (singular included), with the original nulls $I_0=\{i:\theta_i\leq0\}$, the largest qualifying rank and non-strict comparisons. This is the researcher's selected route ([selection](../ideas/idea_bc183ea2b6fa.md), [full write-up](../ideas/idea_2bb31516b09b.md)): prove the order assertion of the frozen-ray maximal inequality by a stopped density-martingale argument, then transfer it to BH.

External Gaussian inequality: the dimension-free $L^1$-regularization tail for the Ornstein-Uhlenbeck semigroup (Gaussian Talagrand convolution conjecture; Eldan-Lee, Lehec; self-contained martingale versions in Shaposhnikov, arXiv:2609.11290, Section 2, as recorded in idea_2bb31516b09b and checked there at abstract level only). It enters the proof of the first lemma only. It is already in the project as two approved paper-extracted results: [Lehec's fixed-time OU tail](../assets/lehec2015_ou_fixed_time_tail.md) and [Lehec's semilogconvex density tail](../assets/lehec2015_semilogconvex_density_tail.md). The second applies to each $L_w$, since $\nabla^2\log L_w\succeq0$ in the latent Gaussian variable. Both control one fixed density only. The supremum over $w$ is the part the stopped martingale must supply.

Stated remainder before execution: the reduction below has no remainder. Once both lemmas hold it closes with the approved boundary-strip lemma and elementary arithmetic. The whole difficulty sits in the two lemma statements: the supremum over late $w$ in the first, and in the second the removal of the hazard factor $h(x^*)\geq U$ that pointwise exponential domination of indicators always costs. Neither lemma has the unknown FDR on its right-hand side.

## Route

- gaussian_bh_negative_null_boundary_strip (approved dependency): reduces the FDR to $q$ plus the contribution of the near-boundary nulls $B_q=\{-a_q<\theta_i\leq0\}$ in step 1.
- gaussian_bh_near_boundary_frozen_ray_transfer: bounds that near-boundary contribution by $A_{\mathrm T}q(1+\mathbb E\min\{1/q,\Lambda_{B_q}\})$, the BH transfer, in step 2.
- gaussian_frozen_ray_order_bound: bounds $\mathbb E\min\{1/q,\Lambda_{B_q}\}$ by $C_{\mathrm{FR}}\sqrt{\log(1/q)}$ uniformly in the null geometry, in step 3; proved by the stopped density martingale with the external regularization tail.

## Plan

1. [x] Fix $0<q\leq q_{\mathrm T}$, with $q_{\mathrm T}\leq\overline\Phi(e)<1/2$ from the transfer lemma, and any finite model $(N,\theta,\Sigma)$. With $U=\overline\Phi^{-1}(q)$, $a_q=2\log(U)/U$ and $B_q$ as in the boundary-strip lemma, its final display gives $\operatorname{FDR}^{(1)}_{\mathrm{BH}}(q;N,\theta,\Sigma)\leq q+\mathbb E[V_{B_q}/(R\vee1)]$ for the same unmodified BH procedure.
2. [x] Apply gaussian_bh_near_boundary_frozen_ray_transfer to the same model and level: $\mathbb E[V_{B_q}/(R\vee1)]\leq A_{\mathrm T}q(1+\mathbb E\min\{1/q,\Lambda_{B_q}(Z)\})$, where $Z=T-\theta$ and the definitions of $B_q$, $a_q$, $V_{B_q}$, $R$ agree with step 1.
3. [x] If $B_q=\varnothing$ then $\Lambda_{B_q}=0$. Otherwise put $n=|B_q|$, $Z_{B_q}=(Z_i)_{i\in B_q}\sim\mathcal N_n(0,\Sigma_{B_qB_q})$ with $\Sigma_{B_qB_q}\in\mathcal C_n$, and weights $\omega_i=1/N$ ($i\in B_q$), so that $\sum_i\omega_i=n/N\leq1$. Then $\Lambda_{B_q}(Z)$ is exactly the field $\Lambda$ of gaussian_frozen_ray_order_bound, and with $c=1/q\geq2$ that lemma gives $\mathbb E\min\{1/q,\Lambda_{B_q}(Z)\}\leq C_{\mathrm{FR}}\sqrt{\log(1/q)}$.
4. [x] Combine: $\operatorname{FDR}^{(1)}_{\mathrm{BH}}\leq q+A_{\mathrm T}q+A_{\mathrm T}C_{\mathrm{FR}}q\sqrt{\log(1/q)}\leq A_1q[1+\sqrt{\log(1/q)}]$ with $A_1=1+A_{\mathrm T}+A_{\mathrm T}C_{\mathrm{FR}}$, for every finite model and every $0<q\leq q_{\mathrm T}$. Take the supremum over models to get $F_1(q)\leq A_1q[1+\sqrt{\log(1/q)}]$.
5. [x] Apply the target's acceptance criterion with $\widetilde q_{0,1}=q_{\mathrm T}$: $q_{0,1}=\min\{q_{\mathrm T},e^{-1}\}$ and $C_1=2A_1$.

## Verification

Steps 1 to 4 hold for each finite model separately, and every constant ($1$, $A_{\mathrm T}$, $C_{\mathrm{FR}}$, $q_{\mathrm T}$) is universal by the statements of the two lemmas and of the boundary-strip lemma. So the bound passes to the supremum $F_1(q)$ at each fixed $q$, with $N$, $\theta$, $\Sigma$ and the null proportion free to depend on $q$. Singular $\Sigma$ is covered because every lemma allows singular covariance, and $\Sigma_{B_qB_q}$ is again a unit-diagonal PSD matrix. Negative null means are covered by the strip lemma for $\theta_i\leq-a_q$ and by the transfer lemma for $-a_q<\theta_i\leq0$. Throughout, BH is the original procedure on all $N$ coordinates with the original labels, so step 5 gives exactly the target statement through its acceptance criterion.

Failure criteria for the loop, in order of test priority: (a) a finite $(n,\Sigma,\omega)$ family with $\mathbb E\min\{c,\Lambda\}/\sqrt{\log c}$ unbounded refutes the first lemma (check the stress tests of idea_57338934f2f7 first); (b) a finite model family with $\mathbb E[V_{B_q}/(R\vee1)]/(q(1+\mathbb E\min\{1/q,\Lambda_{B_q}\}))$ unbounded refutes the transfer lemma. A natural first test is null directions that are exactly orthogonal while alternatives are correlated with the nulls so that they steer the BH level, since there $\Lambda_{B_q}$ is small. Neither refutation would refute the target.

## Difference from failed plans

- plan_252211621cea: no signed-label Stein occupation or switch-sum cancellation. The Gaussian input is an external maximal inequality for the null likelihood-ratio field, so no masked switch sum identified with the FDR is left over.
- plan_503f8fddcbb5: no global shift or entrant allocation. The near-boundary contribution is compared with a frozen-ray field, not paid by a signed facet budget.
- plan_ee2f7b97740a: no rank-chain transport or Hall-cut allocation, hence no cut mass to pay.
- plan_one_sided_order_actual_mean_global_flux_20261106: no positive-flux counting of critical crossings. The level enters only through the frozen-ray supremum over $w$, which is controlled with an exponential (not indicator) kernel.
- plan_one_sided_order_common_anchor_rotation_20261107: no rotation or integrated signed facet flux, whose interface terms cancelled back to the FDR.
- plan_one_sided_order_convex_proxy_label_curvature_20261107: no convex proxy or activation flux.
- plan_one_sided_order_fdp_entropy_mills_coherence_20261107: no trace-versus-coherence certificate. The small-null-loading family that refuted it has FDR of order $qU$, which this route allows, since the frozen-ray field of a common weak factor reaches the one-direction value $\sqrt{\log(1/q)/\pi}$.
- plan_one_sided_order_gaussian_interpolation_sdp_20261106: no covariance interpolation or SDP completion, so there is no face or label multiplicity to remove.
- plan_one_sided_order_mixed_trace_replica_cells_20261108: no replica cells or cross-face pairing.
- plan_one_sided_order_negative_contact_transport_20261106: no negative-covariance contact allocation and no inverse-noise diagonal charges.
- plan_one_sided_order_peeling_history_kernel_20261107: no peeling summation by parts, whose terminal term was the FDR itself.
- plan_one_sided_order_three_face_noise_packing_20261106: no budget maximised over an auxiliary covariance. The field $\Lambda_{B_q}$ is computed from the original null correlations.

## Reduction

Each of the following is used as a black box by its statement: the approved dependency gaussian_bh_negative_null_boundary_strip (the boundary-strip lemma), and the route lemmas gaussian_bh_near_boundary_frozen_ray_transfer (the transfer lemma, constants $A_{\mathrm T}$, $q_{\mathrm T}$) and gaussian_frozen_ray_order_bound (the frozen-ray lemma, constant $C_{\mathrm{FR}}$). All three constants are universal by those statements.

**Step 1 (boundary strip).** Fix $q$ with $0<q\leq q_{\mathrm T}$ and an arbitrary admissible finite model $(N,\theta,\Sigma)$: $N\geq1$, $\theta\in\mathbb R^N$, $\Sigma\in\mathcal C_N$ (singular allowed), $T\sim\mathcal N_N(\theta,\Sigma)$, one-sided p-values $p_i=\overline\Phi(T_i)$, original nulls $I_0=\{i:\theta_i\leq0\}$, ordinary BH at level $q$ with the largest qualifying rank, non-strict comparisons and multiplicities. By the transfer lemma $q_{\mathrm T}\leq\overline\Phi(e)$, and since $e>1$ and $\overline\Phi$ is decreasing, $q\leq\overline\Phi(e)<\overline\Phi(1)$. Hence both hypotheses of the boundary-strip lemma hold ($0<q\leq\overline\Phi(1)$ for the general part, $0<q\leq\overline\Phi(e)$ for its "in particular" part). With $U=\overline\Phi^{-1}(q)$, $a_q=2\log(U)/U$, $B_q=\{i:-a_q<\theta_i\leq0\}$ and $V_{B_q}=|B_q\cap\mathcal R_q|$, its final display gives
$$
\operatorname{FDR}^{(1)}_{\mathrm{BH}}(q;N,\theta,\Sigma)\leq q+\mathbb E\!\left[\frac{V_{B_q}}{R\vee1}\right],
$$
where $\mathcal R_q$, $R=|\mathcal R_q|$ belong to the same unmodified BH procedure on all $N$ coordinates. The left side is exactly the target's $\operatorname{FDR}^{(1)}_{\mathrm{BH}}(q;N,\theta,\Sigma)=\mathbb E[V^{(1)}_q/(R^{(1)}_q\vee1)]$: same p-values, same null set $I_0^{(1)}(\theta)$, same procedure.

**Step 2 (transfer).** The transfer lemma applies to the same model, since its hypotheses are $N\geq1$, $\theta\in\mathbb R^N$, $\Sigma\in\mathcal C_N$ and $0<q\leq q_{\mathrm T}$. Its $U$, $a_q$, $B_q$, BH procedure, $\mathcal R_q$, $R$ and $V_{B_q}$ are defined by the same formulas as in step 1, so they are the same random objects. With $Z=T-\theta\sim\mathcal N_N(0,\Sigma)$ and
$$
\Lambda_{B_q}(Z)=\sup_{w\geq0}\frac1N\sum_{i\in B_q}\exp\!\left(wZ_i-\frac{w^2}{2}\right)\quad(\Lambda_{B_q}=0\text{ if }B_q=\varnothing),
$$
it gives
$$
\mathbb E\!\left[\frac{V_{B_q}}{R\vee1}\right]\leq A_{\mathrm T}\,q\Bigl(1+\mathbb E\min\{1/q,\Lambda_{B_q}(Z)\}\Bigr).
$$

**Step 3 (frozen-ray bound).** We show
$$
\mathbb E\min\{1/q,\Lambda_{B_q}(Z)\}\leq C_{\mathrm{FR}}\sqrt{\log(1/q)}.
$$
If $B_q=\varnothing$, the left side is $0$ and the right side is nonnegative (indeed $q<1$). Otherwise let $n=|B_q|\geq1$, list $B_q=\{i_1<\cdots<i_n\}$, and put $Z'=(Z_{i_1},\ldots,Z_{i_n})$, $\Sigma'=(\Sigma_{i_ki_l})_{k,l\leq n}$. Then $\Sigma'$ is symmetric, has unit diagonal, and is positive semidefinite, because for $x\in\mathbb R^n$ the vector $\tilde x\in\mathbb R^N$ with $\tilde x_{i_k}=x_k$ and zeros elsewhere satisfies $x^{\mathsf T}\Sigma'x=\tilde x^{\mathsf T}\Sigma\tilde x\geq0$; so $\Sigma'\in\mathcal C_n$ (possibly singular). For $a\in\mathbb R^n$, $a^{\mathsf T}Z'=\tilde a^{\mathsf T}Z$ is centered normal with variance $\tilde a^{\mathsf T}\Sigma\tilde a=a^{\mathsf T}\Sigma'a$, so $Z'\sim\mathcal N_n(0,\Sigma')$. Take the deterministic weights $\omega_k=1/N\geq0$, with $\sum_k\omega_k=n/N\leq1$. Then for every $w\geq0$, on the same realization,
$$
L_w(Z')=\sum_{k=1}^n\frac1N\exp\!\left(wZ_{i_k}-\frac{w^2}{2}\right)=\frac1N\sum_{i\in B_q}\exp\!\left(wZ_i-\frac{w^2}{2}\right),
$$
so the frozen-ray field $\Lambda(Z')=\sup_{w\geq0}L_w(Z')$ equals $\Lambda_{B_q}(Z)$ pointwise. Put $c=1/q$. Since $q\leq\overline\Phi(e)<\overline\Phi(0)=1/2$, we have $c\geq2$. The frozen-ray lemma, applied with $(n,\Sigma',Z',\omega,c)$, gives $\mathbb E\min\{c,\Lambda(Z')\}\leq C_{\mathrm{FR}}\sqrt{\log c}$, which is the claim because $\log c=\log(1/q)$. The constant $C_{\mathrm{FR}}$ does not depend on $n$, $\Sigma'$, the weights or $c$, hence not on the model or on $q$.

**Step 4 (combination).** Steps 1 to 3 give, for every admissible finite model and every $0<q\leq q_{\mathrm T}$,
$$
\operatorname{FDR}^{(1)}_{\mathrm{BH}}(q;N,\theta,\Sigma)\leq q+A_{\mathrm T}q+A_{\mathrm T}C_{\mathrm{FR}}\,q\sqrt{\log(1/q)}\leq A_1q\bigl[1+\sqrt{\log(1/q)}\bigr],
$$
with $A_1=1+A_{\mathrm T}+A_{\mathrm T}C_{\mathrm{FR}}$. The last inequality holds because $q(1+A_{\mathrm T})\leq A_1q$ and $A_{\mathrm T}C_{\mathrm{FR}}q\sqrt{\log(1/q)}\leq A_1q\sqrt{\log(1/q)}$, all quantities being nonnegative ($q<1$, $A_{\mathrm T},C_{\mathrm{FR}}>0$). The right side does not depend on $(N,\theta,\Sigma)$, so taking the supremum over $N\geq1$, $\theta\in\mathbb R^N$ and $\Sigma\in\mathcal C_N$ at this fixed $q$ gives
$$
F_1(q)\leq A_1q\bigl[1+\sqrt{\log(1/q)}\bigr],\qquad 0<q\leq q_{\mathrm T}.
$$
Since the supremum is taken separately at each $q$, the model, the null proportion and $|B_q|$ may vary with $q$; nothing in steps 1 to 3 restricts this.

**Step 5 (acceptance criterion).** This is the target's sufficient finite-level conclusion with the universal constant $A_1$ and the universal interval $0<q\leq\widetilde q_{0,1}:=q_{\mathrm T}$, where $0<q_{\mathrm T}\leq\overline\Phi(e)<1$. Explicitly, set $q_{0,1}=\min\{q_{\mathrm T},e^{-1}\}\in(0,1)$ and $C_1=2A_1$. For $0<q\leq q_{0,1}$ we have $\log(1/q)\geq1$, hence $1\leq\sqrt{\log(1/q)}$ and $1+\sqrt{\log(1/q)}\leq2\sqrt{\log(1/q)}$, so by step 4
$$
F_1(q)\leq2A_1q\sqrt{\log(1/q)}=C_1q\sqrt{\log(1/q)}.
$$
Both $C_1$ and $q_{0,1}$ are built only from $A_{\mathrm T}$, $C_{\mathrm{FR}}$, $q_{\mathrm T}$ and absolute numbers, so they are independent of the number of tests, means, covariance, null proportion, rank and every other model parameter. This is the target statement. No remainder term is left: the only inputs are the three statements above.

## Reduction verdict

confirmed

Checked against the statements alone (lemmas as black boxes):

1. Level ranges. The transfer lemma gives $0<q_{\mathrm T}\leq\overline\Phi(e)$, so every $0<q\leq q_{\mathrm T}$ satisfies both hypotheses of the boundary-strip lemma ($q\leq\overline\Phi(1)$ and $q\leq\overline\Phi(e)$), hence $U\geq e$ and $a_q=2\log(U)/U>0$. Also $q<1/2$, so $c=1/q\geq2$ as the frozen-ray lemma requires, and $\log(1/q)>0$.
2. Step 1. The boundary-strip lemma's "Consequently" display is exactly $\operatorname{FDR}^{(1)}_{\mathrm{BH}}(q;N,\theta,\Sigma)\leq q+\mathbb E[V_{B_q}/(R\vee1)]$ for the target's one-sided p-values, composite null set $I_0=\{\theta_i\leq0\}$ (negative means included) and unmodified BH (largest rank, non-strict, multiplicities). Its quantifiers (every finite $N$, $\theta$, PSD unit-diagonal $\Sigma$, singular allowed) match $\mathcal C_N$.
3. Step 2. The transfer lemma's hypotheses are only $N\geq1$, $\theta\in\mathbb R^N$, $\Sigma\in\mathcal C_N$, $0<q\leq q_{\mathrm T}$; its $U$, $a_q$, $B_q$, $\mathcal R_q$, $R$, $V_{B_q}$ are given by the same formulas as in the strip lemma, so the left side of its conclusion is the remainder of step 1.
4. Step 3. $B_q$ depends only on $(\theta,q)$, so the weights $\omega_k=1/N$ are deterministic, nonnegative, with total $n/N\leq1$. The submatrix $\Sigma'$ is in $\mathcal C_n$ (the zero-padding argument is correct) and $Z'\sim\mathcal N_n(0,\Sigma')$ by the definition of joint Gaussianity via linear forms. $L_w(Z')$ coincides with the summand of $\Lambda_{B_q}(Z)$ for every $w\geq0$ on the same realization, so $\Lambda(Z')=\Lambda_{B_q}(Z)$ pointwise and the expectations agree (the integrand is a function of $Z'$, bounded by $c$). The empty case $B_q=\varnothing$ is handled by the convention $\Lambda_{B_q}=0$. $C_{\mathrm{FR}}$ is independent of $n$, $\Sigma'$, the weights and $c$ by statement.
5. Steps 4 and 5. Arithmetic: $q+A_{\mathrm T}q(1+C_{\mathrm{FR}}\sqrt{\log(1/q)})\leq A_1q[1+\sqrt{\log(1/q)}]$ with $A_1=1+A_{\mathrm T}+A_{\mathrm T}C_{\mathrm{FR}}$ is correct. The bound is model-free, so the supremum defining $F_1(q)$ (taken separately at each $q$ over $N$, $\theta$, $\Sigma\in\mathcal C_N$) obeys it. With $q_{0,1}=\min\{q_{\mathrm T},e^{-1}\}\in(0,1)$ and $C_1=2A_1\in(0,\infty)$, $\log(1/q)\geq1$ gives $F_1(q)\leq C_1q\sqrt{\log(1/q)}$ for $0<q\leq q_{0,1}$, the exact target with universal constants.

No step uses more than a statement says; no remainder term is left. The target's other listed dependencies are not needed. The whole difficulty sits in the two draft lemmas (gaussian_bh_near_boundary_frozen_ray_transfer, gaussian_frozen_ray_order_bound), which still require proofs and verification.
