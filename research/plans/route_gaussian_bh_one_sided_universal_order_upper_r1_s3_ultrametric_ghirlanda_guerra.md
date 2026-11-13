---
type: plan
title: >-
  Universal one-sided order via Ghirlanda-Guerra ultrametricity of worst-case
  arrays and a tree bound
status: abandoned
target_asset: gaussian_bh_one_sided_universal_order_upper
route_lemmas:
  - gaussian_bh_worst_case_approximate_ghirlanda_guerra
  - gaussian_bh_ghirlanda_guerra_ultrametric_value_transfer
  - gaussian_bh_ultrametric_covariance_order_bound
route_title: via ultrametric worst cases and trees
origin: researcher
inspired_by:
  - idea_b808cca5bf7f
  - idea_ae102c56085d
  - idea_94863105930a
tags:
  - parallel-round-20261112
  - route-3
route_round: 1
reduction_digest: d6dc69a81bbc82553ad4c8c0603dd761b0fca10a8a745c634da8b90374a94084
reduction_inputs:
  gaussian_bh_one_sided_universal_order_upper: 4fe10575d36df3f3f1d7a5d3b02045f11cc1642e336a0a94fe50ce0a9f321484
  gaussian_bh_fractional_frame_surface_kernel: 73320a924701f1ff16a1f07678da1f8aec14bcaa701710f663f9a9f5b0d67369
  gaussian_bh_conditional_compound_calibration: 72c9382ceb1913470689b87acb600c14e6c36c033da80c5f6d7559dceeaafc01
  gaussian_bh_negative_null_boundary_strip: 8cb3729d0db20bedb0d623cce2676cfa7d01e08b10180884af70e5a810e0b568
  gaussian_bh_conditional_subpoisson_calibration: 690ddb01c6ce756d2366c4901fffdbdfa396da6353901f8ea0cfffa828f89b29
  gaussian_bh_worst_case_approximate_ghirlanda_guerra: 0fa059894da56d1c7aa170ddad938948acb823f2dc7eea7e4574aa98d3831230
  gaussian_bh_ghirlanda_guerra_ultrametric_value_transfer: 04ca83314db51cc918266749a1a6d9a0b88e4f742e15668be25d2ab61e886b23
  gaussian_bh_ultrametric_covariance_order_bound: 52eec1c5485d9f0b6127ce178a5d7e660c6443b578270b06f4a59370a0435c1b
reduction_verified_digest: d6dc69a81bbc82553ad4c8c0603dd761b0fca10a8a745c634da8b90374a94084
reduction_checked: true
---

## Goal

Target: [Universal order upper bound for one-sided Gaussian BH](../assets/gaussian_bh_one_sided_universal_order_upper.md).

Prove the unchanged statement: universal $C_1,q_{0,1}$ with $F_1(q)\le C_1q\sqrt{\log(1/q)}$ for $0<q\le q_{0,1}$, over every finite $N$, every mean vector, every unit-diagonal PSD covariance (singular included), original labels $I_0=\{i:\theta_i\le0\}$ and ordinary BH with the largest qualifying rank. This is the researcher-selected route of [the ultrametric selection](../ideas/idea_b808cca5bf7f.md), whose content is [Route 3](../ideas/idea_ae102c56085d.md): show that worst-case marked arrays can be taken ultrametric (Ghirlanda-Guerra identities plus Panchenko's ultrametricity theorem), then bound BH on trees. Slot 3 of the round follows the order of the researcher's route request (decision of 12 November 2026); the generic direction line of the pack names Route 1, which belongs to slot 1.

External Gaussian inequalities brought in (as the direction requires):
- Panchenko, *The Parisi ultrametricity conjecture*, Ann. of Math. 177 (2013) 383-393: a Gram-de Finetti array satisfying the Ghirlanda-Guerra identities has ultrametric off-diagonal support almost surely; with Talagrand's positivity principle (Ghirlanda-Guerra implies nonnegative overlaps). Neither is in the library yet; both must be imported with `import-math-paper` and verified before Lemma 2 is proved. Exact theorem locations are to be read from the sources, not assumed here.
- The approved Dovbysh-Sudakov representation (lib_panchenko2009_dovbysh_sudakov_mixture), already used by the approved compactification.
- For Lemma 3: chaining over the levels of the tree, with the approved [directional-entropy bound](../assets/directional_entropy_one_sided_fdr_bound.md) as the per-level estimate and the draft [two-level tree frozen-ray result](../assets/gaussian_frozen_ray_two_level_tree.md) as the base case; these are suggestions for the lemma's own plan, not route lemmas.

Stated remainders (saturation check, before execution). Lemma 1 leaves the Ghirlanda-Guerra defect $\Delta_{P_k}(n,f,\psi)$, a statistic of the residual-correlation array alone, not the FDR. Lemma 2 leaves the distance of the limiting overlap law from ultrametric support, which Panchenko's theorem makes zero. Lemma 3 leaves an explicit tree-chaining charge; in the zero-mean independent case ($\Sigma=I$, a star tree) the BH FDR is exactly $q\pi_0$, so the charge there must be $O(q)$ and cannot equal the FDR up to $O(q)$ in a circular way.

Risks to test first (by the loop's counterexample searches on the lemmas). Lemma 1 is the high-risk step: in spin glasses the identities come from convexity of the free energy in perturbation parameters, and here the candidate substitute is that the value function $\lambda\mapsto\sup_P\{\mathcal F(P)+\lambda\Phi(P)\}$ of overlap-moment perturbations $\Phi$ is convex (a supremum of affine functions), combined with tilting the directing measure by an independent Gaussian process and the approved first-variation and [global particle-potential](../assets/gaussian_bh_global_particle_potential_certificate.md) stationarity. If no such structure produces identities of Ghirlanda-Guerra shape, Lemma 1 fails and the route is obstructed for that reason. A legal falsifier of Lemma 1 combined with Lemma 2 is any $\sigma,q$ with $W_\sigma(q)>U_\sigma(q)$, i.e. a non-ultrametric (for example negatively correlated or non-hierarchical) finite model that beats every tree model; the families of [the computer-assisted triage](../ideas/idea_213cbf984362.md) are priority test cases. Lemma 3 is the target restricted to trees; equicorrelated and one-factor lower-bound families are trees, so it carries the full $q\sqrt{\log(1/q)}$ order.

## Route

- gaussian_bh_worst_case_approximate_ghirlanda_guerra: supplies, at fixed $\sigma,q$, near-maximizing marked arrays $P_k$ with $\mathcal F(P_k;q,\sigma)\to W_\sigma(q)$ whose Ghirlanda-Guerra defects vanish (Step 1).
- gaussian_bh_ghirlanda_guerra_ultrametric_value_transfer: turns vanishing Ghirlanda-Guerra defects into the value bound $\limsup_k\mathcal F(P_k;q,\sigma)\le U_\sigma(q)$, the supremum over finite models with nonnegative ultrametric residual correlations (Step 2).
- gaussian_bh_ultrametric_covariance_order_bound: bounds the FDR of every finite model with nonnegative ultrametric covariance by $Aq[1+\sqrt{\log(1/q)}]$, uniformly (Step 3).
- Approved dependency [the marked-array compactification](../assets/gaussian_bh_exchangeable_array_variational_compactification.md), item 5: $\lim_{\sigma\downarrow0}W_\sigma(q)=F_1(q)$ for $0<q<1/2$ (Step 4).

## Plan

1. [x] Fix $0<q\le q_*:=\min\{\widetilde q,\overline\Phi(1),e^{-1}\}$, with $\widetilde q$ from gaussian_bh_ultrametric_covariance_order_bound, and fix $0<\sigma<1$. By gaussian_bh_worst_case_approximate_ghirlanda_guerra there are $P_k\in\mathfrak P$ with $\mathcal F(P_k;q,\sigma)\to W_\sigma(q)$ and $\Delta_{P_k}(n,f,\psi)\to0$ for every $n\ge2$ and all continuous $f,\psi$ (the defect is defined identically in both lemmas).
2. [x] By gaussian_bh_ghirlanda_guerra_ultrametric_value_transfer applied to this sequence, $W_\sigma(q)=\lim_k\mathcal F(P_k;q,\sigma)\le U_\sigma(q)$.
3. [x] Every model counted in $U_\sigma(q)$ has covariance $\Sigma=(1-\sigma^2)C+\sigma^2\mathbf 1\mathbf 1^{\mathsf T}$ with $C$ a nonnegative ultrametric correlation matrix. Then $\Sigma$ is a nonnegative ultrametric correlation matrix: it is PSD as a sum of PSD matrices, $\Sigma_{ii}=1$, $\Sigma_{ij}=(1-\sigma^2)C_{ij}+\sigma^2\ge0$ for $i\ne j$, and the map $x\mapsto(1-\sigma^2)x+\sigma^2$ is increasing, so it preserves $C_{ij}\ge\min\{C_{ik},C_{jk}\}$. Its FDR is the original one-sided $\operatorname{FDR}^{(1)}_{\mathrm{BH}}(q;n,\theta,\Sigma)$ with $I_0=\{i:\theta_i\le0\}$, so gaussian_bh_ultrametric_covariance_order_bound gives $\operatorname{FDR}\le Aq[1+\sqrt{\log(1/q)}]$. Taking the supremum, $U_\sigma(q)\le Aq[1+\sqrt{\log(1/q)}]$, hence $W_\sigma(q)\le Aq[1+\sqrt{\log(1/q)}]$ for every $\sigma\in(0,1)$.
4. [x] Since $q\le\overline\Phi(1)<1/2$, item 5 of the compactification gives $F_1(q)=\lim_{\sigma\downarrow0}W_\sigma(q)\le Aq[1+\sqrt{\log(1/q)}]$.
5. [x] By the target's acceptance criterion with $A_1=A$ and $\widetilde q_{0,1}=q_*$: since $q\le e^{-1}$ gives $1+\sqrt{\log(1/q)}\le2\sqrt{\log(1/q)}$, the target holds with $C_1=2A$ and $q_{0,1}=q_*$.

## Reduction

Black boxes, each used by its statement only: Lemma 1 = [the approximate Ghirlanda-Guerra lemma](../assets/gaussian_bh_worst_case_approximate_ghirlanda_guerra.md), Lemma 2 = [the ultrametric value transfer](../assets/gaussian_bh_ghirlanda_guerra_ultrametric_value_transfer.md), Lemma 3 = [the ultrametric covariance order bound](../assets/gaussian_bh_ultrametric_covariance_order_bound.md), and items 1 and 5 of the approved [marked-array compactification](../assets/gaussian_bh_exchangeable_array_variational_compactification.md). The objects $\mathfrak P$, $\mathcal F_n$, $\mathcal F$ and $W_\sigma(q)$ are those of the approved [marked parameter array definition](../definitions/gaussian_bh_marked_exchangeable_parameter_array.md); all three lemmas and the compactification refer to this one definition, and $F_1$ in item 5 is the $F_1$ of the approved [worst-case definition](../definitions/gaussian_worst_case_bh_fdr.md), which is exactly the supremum in the target statement (every $N\ge1$, every $\theta\in\mathbb R^N$, every symmetric PSD unit-diagonal $\Sigma$, singular included, $p_i=\overline\Phi(T_i)$, $I_0=\{i:\theta_i\le0\}$, ordinary BH with the largest qualifying rank).

**Constants.** Let $A>0$ and $\widetilde q\in(0,1)$ be the universal constants of Lemma 3. Put
$$
q_*=\min\{\widetilde q,\ \overline\Phi(1),\ e^{-1}\}.
$$
Then $0<q_*<1$, and $q_*$ depends on nothing but $\widetilde q$ and absolute numbers, so it is universal. Note $\overline\Phi(1)=q_{\max}<1/2$ (since $\overline\Phi(0)=1/2$ and $\overline\Phi$ is strictly decreasing). Put $B(q)=Aq[1+\sqrt{\log(1/q)}]$.

Fix $0<q\le q_*$ for the rest of the argument. Then $0<q\le q_{\max}$, $0<q<1/2$, $q\le\widetilde q$ and $q\le e^{-1}$.

**Step 1 (Lemma 1).** Fix $0<\sigma<1$. The hypotheses of Lemma 1 are $0<\sigma<1$ and $0<q\le q_{\max}$, both satisfied. (The functional $\mathcal F(\cdot;q,\sigma)$ it uses exists on all of $\mathfrak P$ because $0<q<1/2$, by item 1 of the compactification.) Lemma 1 gives a sequence $(P_k)_{k\ge1}$ in $\mathfrak P$ with
$$
\lim_{k\to\infty}\mathcal F(P_k;q,\sigma)=W_\sigma(q)
$$
and $\lim_k\Delta_{P_k}(n,f,\psi)=0$ for every integer $n\ge2$ and all continuous $f:[-1,1]^{n(n-1)/2}\to[-1,1]$, $\psi:[-1,1]\to[-1,1]$. The defect $\Delta_P(n,f,\psi)$ in Lemma 1 is, symbol for symbol, the defect in Lemma 2 (same three expectations, same coefficients $1/n$, same index sets $C^{(n)}=(C_{ll'})_{1\le l<l'\le n}$, $C_{1,n+1}$, $C_{12}$, $C_{1l}$ for $2\le l\le n$, same function classes). No moment bound on $P_k$ is produced or needed.

**Step 2 (Lemma 2).** Lemma 2's hypotheses are $0<\sigma<1$, $0<q\le q_{\max}$, and a sequence in $\mathfrak P$ whose defects all tend to $0$, with no assumption on $M_2(P_k)$. The sequence of Step 1 qualifies. Hence $\limsup_k\mathcal F(P_k;q,\sigma)\le U_\sigma(q)$. Since the limit exists and equals $W_\sigma(q)$ by Step 1,
$$
W_\sigma(q)=\lim_{k\to\infty}\mathcal F(P_k;q,\sigma)=\limsup_{k\to\infty}\mathcal F(P_k;q,\sigma)\le U_\sigma(q).
$$

**Step 3 (Lemma 3 on the ultrametric class).** Let $n\ge1$, $\theta\in\mathbb R^n$, and let $C$ be an $n\times n$ nonnegative ultrametric correlation matrix in the sense of Lemma 2. Put $\Sigma=(1-\sigma^2)C+\sigma^2\mathbf 1\mathbf 1^{\mathsf T}$ and $g(x)=(1-\sigma^2)x+\sigma^2$. Then:

- $\Sigma$ is symmetric and PSD: $C$ is PSD, $1-\sigma^2>0$, and $x^{\mathsf T}\mathbf 1\mathbf 1^{\mathsf T}x=(\mathbf 1^{\mathsf T}x)^2\ge0$, so $x^{\mathsf T}\Sigma x\ge0$ for all $x$. Singular $\Sigma$ is allowed in Lemma 3.
- $\Sigma_{ii}=(1-\sigma^2)\cdot1+\sigma^2=1$.
- For $i\ne j$, $\Sigma_{ij}=g(C_{ij})\ge g(0)=\sigma^2>0$, because $C_{ij}\ge0$ and $g$ is increasing.
- For pairwise distinct $i,j,k$: $g$ is strictly increasing, so $g(\min\{a,b\})=\min\{g(a),g(b)\}$; from $C_{ij}\ge\min\{C_{ik},C_{jk}\}$ we get $\Sigma_{ij}=g(C_{ij})\ge g(\min\{C_{ik},C_{jk}\})=\min\{\Sigma_{ik},\Sigma_{jk}\}$. For $n\le2$ this condition is vacuous in both definitions.

So $\Sigma$ is an $n\times n$ nonnegative ultrametric correlation matrix in the sense of Lemma 3 (the two lemmas use the same four defining conditions). The quantity $\operatorname{FDR}^{(1)}_{\mathrm{BH}}(q;n,\theta,\Sigma)$ inside $U_\sigma(q)$ is by Lemma 2's definition the original one-sided FDR of ordinary BH with $p_i=\overline\Phi(T_i)$, $T\sim\mathcal N_n(\theta,\Sigma)$, $I_0=\{i:\theta_i\le0\}$, largest qualifying rank, non-strict comparisons and multiplicities, which is exactly the quantity bounded in Lemma 3. Since $0<q\le\widetilde q$, Lemma 3 gives
$$
\operatorname{FDR}^{(1)}_{\mathrm{BH}}\bigl(q;n,\theta,(1-\sigma^2)C+\sigma^2\mathbf 1\mathbf 1^{\mathsf T}\bigr)\le B(q).
$$
This holds for every $n$, $\theta$ and $C$ in the supremum defining $U_\sigma(q)$, with a right side free of $n,\theta,C,\sigma$. Taking the supremum, $U_\sigma(q)\le B(q)$, and by Step 2,
$$
W_\sigma(q)\le B(q)\qquad\text{for every }\sigma\in(0,1).
$$

**Step 4 (item 5 of the compactification).** Since $0<q\le\overline\Phi(1)<1/2$, item 5 gives that $\lim_{\sigma\downarrow0}W_\sigma(q)$ exists and equals $F_1(q)$. Every term of this limit is at most $B(q)$ by Step 3 (which holds for every $\sigma\in(0,1)$, in particular along any sequence $\sigma\downarrow0$), and $B(q)$ does not depend on $\sigma$. A limit of numbers bounded by $B(q)$ is bounded by $B(q)$, so
$$
F_1(q)\le Aq\left[1+\sqrt{\log(1/q)}\right].
$$

**Step 5 (acceptance criterion).** Step 4 holds for every $0<q\le q_*$, with $A$ finite universal and $q_*\in(0,1)$ universal; this is the target's sufficient finite-level conclusion with $A_1=A$, $\widetilde q_{0,1}=q_*$. Explicitly, for $0<q\le q_*\le e^{-1}$ we have $\log(1/q)\ge1$, hence $1\le\sqrt{\log(1/q)}$ and $1+\sqrt{\log(1/q)}\le2\sqrt{\log(1/q)}$. Therefore, with
$$
C_1=2A,\qquad q_{0,1}=q_*,
$$
$F_1(q)\le C_1q\sqrt{\log(1/q)}$ for every $0<q\le q_{0,1}$. Since $F_1(q)$ is the supremum over all finite models in the target, this is the target's displayed inequality for every $N$, $\theta$ and unit-diagonal PSD $\Sigma$, singular included, with constants depending on nothing but Lemma 3's universal $A,\widetilde q$.

**Uniformity and what is used.** No step depends on $N$, $\theta$, $\Sigma$, rank, null proportion or tree structure: the only quantitative input is Lemma 3, uniform by hypothesis; Lemmas 1 and 2 and item 5 are value statements without rates, used at fixed $(\sigma,q)$ and then in the limit $\sigma\downarrow0$ after a $\sigma$-free bound. The target's listed dependencies (the fractional-frame surface kernel, the compound and sub-Poisson calibrations, the negative-null boundary strip) are not needed in this reduction. Remainder: none beyond the three route lemmas.

## Verification

Steps 1-2 use only the two lemma statements at the same fixed $(\sigma,q)$, with the identical defect $\Delta_P(n,f,\psi)$ and the same completed functional $\mathcal F$ whose existence is item 1 of the approved compactification; $W_\sigma(q)$ is the finite common-loading supremum of the approved definition. Step 3 is an elementary matrix check plus Lemma 3, whose hypotheses (any $N$, any $\theta$, any nonnegative ultrametric unit-diagonal PSD $\Sigma$, singular included, original labels, largest rank) cover every model in $U_\sigma(q)$; the bound does not depend on $\sigma$. Step 4 is item 5 of the approved compactification, valid for $0<q<1/2$. Step 5 is the acceptance criterion verbatim. The constants $A,\widetilde q$ are universal by Lemma 3, $\overline\Phi(1)$ and $e^{-1}$ are absolute, and no step introduces dependence on $N$, rank, means, $\sigma$ or any regularization: $\sigma$ is removed in Step 4 after a $\sigma$-free bound. Lemmas 1 and 2 are pure value statements about the supremum; they carry no rate and need none.

## Difference from failed plans

- plan_252211621cea: no signed occupation or switch-sum accounting of the actual BH path; the worst case is restricted structurally (ultrametric) before any FDR estimate.
- plan_503f8fddcbb5: no global-shift record partition or entrant Stein allocation; no residual flux budget is ever formed.
- plan_ee2f7b97740a: no rank-chain transport or Hall-cut maximum; the only quantitative estimate is on trees.
- plan_one_sided_order_actual_mean_global_flux_20261106: no aggregate rank-flux estimate; the cascade problem is not attacked pointwise but bypassed by the extremal-structure reduction.
- plan_one_sided_order_common_anchor_rotation_20261107: no rotation path or integrated facet flux, so no terminal cancellation back to the FDR.
- plan_one_sided_order_convex_proxy_label_curvature_20261107: no convex proxy or curvature allocation; convexity enters only through the value function of overlap perturbations.
- plan_one_sided_order_fdp_entropy_mills_coherence_20261107: no trace-versus-coherence certificate; the refuted certificate TC is not used, and its low-coherence lower family is a test case for Lemmas 1-3 (does it lie in, or is it beaten by, the ultrametric class?), not a falsifier of a stronger certificate.
- plan_one_sided_order_gaussian_interpolation_sdp_20261106: no covariance interpolation or SDP completion; no dimension-dependent completion charge appears.
- plan_one_sided_order_mixed_trace_replica_cells_20261108: no replica cells or cross-face comparison; replicas appear only as iid samples of a directing measure in Ghirlanda-Guerra identities.
- plan_one_sided_order_negative_contact_transport_20261106: negative covariances are not transported but excluded from the extremal class via positivity of Ghirlanda-Guerra arrays.
- plan_one_sided_order_peeling_history_kernel_20261107: no peeling or history kernels, hence no P4-saturation remainder; the remainders are overlap statistics and a tree-chaining charge.
- plan_one_sided_order_three_face_noise_packing_20261106: no face/noise packing budget; its log N divergent charge in equicorrelated models concerns that budget only, and equicorrelated models are a test family for Lemma 3.

## Reduction verdict

confirmed

Independent check of ## Reduction as written. The three route lemmas and items 1 and 5 of the approved compactification are used only through their statements.

1. **Objects and target.** $\mathfrak P$, $\mathcal F_n$, $\mathcal F$ and $W_\sigma(q)$ all come from the approved marked parameter array definition, which every lemma and the compactification cite. $W_\sigma(q)$ is the finite canonical common-loading supremum, with residual matrix $(1-\sigma^2)C+\sigma^2\mathbf 1\mathbf 1^{\mathsf T}$. $F_1$ in item 5 is the $F_1$ of the approved worst-case definition, which is word for word the supremum in the target (every $N$, every $\theta$, unit-diagonal PSD $\Sigma$ including singular ones, $p_i=\overline\Phi(T_i)$, $I_0=\{\theta_i\le0\}$, largest qualifying rank).
2. **Level ranges.** $q_*=\min\{\widetilde q,\overline\Phi(1),e^{-1}\}\in(0,1)$ is universal. For $0<q\le q_*$:
   - $q\le q_{\max}=\overline\Phi(1)<1/2$, which is what Lemmas 1 and 2 require. It also places $q$ in item 1's range $(0,1/2)$, where $\mathcal F$ exists, and in item 5's range $(0,1/2)$.
   - $q\le\widetilde q$, which is what Lemma 3 requires.
   - $q\le e^{-1}$, which is what the acceptance step needs. (This entry of the minimum is redundant because $\overline\Phi(1)\approx0.159<e^{-1}$, but it does no harm.)
3. **Defect identity.** I compared the two statements term by term. $\Delta_P(n,f,\psi)$ in Lemma 1 and in Lemma 2 has the same three expectations, the same coefficients $1/n$, the same entries $C^{(n)}=(C_{ll'})_{l<l'\le n}$, $C_{1,n+1}$, $C_{12}$ and $C_{1l}$ for $2\le l\le n$, and the same classes (integer $n\ge2$, continuous $f:[-1,1]^{n(n-1)/2}\to[-1,1]$, continuous $\psi:[-1,1]\to[-1,1]$). Lemma 1 concludes that the defects vanish for all such $(n,f,\psi)$, which is exactly Lemma 2's hypothesis. Lemma 2 assumes nothing about $M_2(P_k)$ and allows marks to escape, so the unbounded moments that Lemma 1 permits do no harm.
4. **Quantifiers, Steps 1 and 2.** At fixed $(\sigma,q)$, Lemma 1 gives $\lim_k\mathcal F(P_k;q,\sigma)=W_\sigma(q)$. Lemma 2 gives $\limsup_k\mathcal F(P_k;q,\sigma)\le U_\sigma(q)$. Since the limit exists, $W_\sigma(q)\le U_\sigma(q)$. Lemma 1 supplies the near-maximizing sequence directly, so the reduction never uses the penalized maximizers $P_\eta$ or a limit in $\eta$ (item 2 is not invoked). No interchange of $\eta$ and $\sigma$ limits arises. The sequence may depend on $(\sigma,q)$, and this is harmless because only the value inequality survives.
5. **Private-noise map, Step 3.** For $C$ a nonnegative ultrametric correlation matrix and $0<\sigma<1$, put $\Sigma=(1-\sigma^2)C+\sigma^2\mathbf 1\mathbf 1^{\mathsf T}$. Then:
   - $\Sigma$ is symmetric PSD as a sum of PSD matrices.
   - $\Sigma_{ii}=1$.
   - $\Sigma_{ij}=g(C_{ij})\ge\sigma^2>0$ for $i\ne j$.
   - Ultrametricity is preserved because the increasing affine $g$ commutes with $\min$.
   - The case $n\le2$ is vacuous in both definitions.

   Lemma 2's class and Lemma 3's class have the same four defining conditions. The FDR inside $U_\sigma(q)$ is the original one-sided ordinary-BH FDR of the Gaussian model with covariance $\Sigma$, which is exactly the quantity Lemma 3 bounds. The case $n=1$ is covered by Lemma 3 ($N\ge1$). So $U_\sigma(q)\le B(q)=Aq[1+\sqrt{\log(1/q)}]$.
6. **Uniformity in $\sigma$, Step 4.** Lemma 3's constants $A,\widetilde q$ are universal and in particular free of $\sigma$, because Lemma 3 never mentions $\sigma$. Hence $W_\sigma(q)\le B(q)$ for every $\sigma\in(0,1)$ with the same $B(q)$. Item 5 says $\lim_{\sigma\downarrow0}W_\sigma(q)$ exists and equals $F_1(q)$. A limit of terms each bounded by $B(q)$ is bounded by $B(q)$, so $F_1(q)\le B(q)$. Item 5 is listed under the compactification's header "Fix $0<\sigma<1$", but its content is the $\sigma\downarrow0$ limit at fixed $q$, and it is used only that way.
7. **Acceptance criterion, Step 5.** $F_1(q)\le Aq[1+\sqrt{\log(1/q)}]$ on $0<q\le q_*$ is the target's stated sufficient finite-level conclusion, with $A_1=A$ and $\widetilde q_{0,1}=q_*$. The explicit conversion is correct: $\log(1/q)\ge1$ on $q\le e^{-1}$, so we may take $C_1=2A$ and $q_{0,1}=q_*$. The constants depend only on Lemma 3's universal $A,\widetilde q$, so the bound covers the whole supremum, independently of $N$, rank, null proportion, tree structure and $\sigma$.

No gap was found. Remainder: none beyond the three route lemmas. The reduction carries the full weight of the target into Lemma 3 (a universal order bound on the nonnegative ultrametric class) and into Lemma 2 (the transfer of value with marks escaping to $\pm\infty$ and no moment control). Both are unproved draft statements and need fresh proofs and independent verification.

## Dropped

Researcher-approved drop (12 Nov 2026): its Ghirlanda-Guerra lemma is refuted by a verified counterexample; exact identities force nonnegative overlaps, where BH's FDR is at most q, contradicting Lei's lower bound. The null-only tree variant remains open.
