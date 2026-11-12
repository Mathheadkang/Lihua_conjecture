---
type: plan
title: Weighted group cutoffs and partial-FDP proof
status: succeeded
target_asset: directional_entropy_one_sided_fdr_bound
inspired_by:
  - idea_676ddf6ca5aa
adapts: []
proof_digest: 750c888e71528f1bacb4aa12d094a07185fb6336c87c187d1191373934da6b12
statement_digest: d2f5f592be074963400a03298424a3e5e1df4050144f3e4fb2d8d8b6c4249a95
dependency_digests:
  lei2026_conditional_fdp_bound: 44ffaa8350cce69886ffb1907cd5a32495616e8ae1bfffc50faacce9e404d689
  lei2026_integrated_conditional_tail_ratios: eaba74a3d26ad4ac1b23dbf9994b6056da3e28d3e763ef838fb82f70c8fc5867
  gaussian_multifactor_representation: e3a61244f476941be96780294a5d26af63dd415aa7462c2662601bf6aeb086fe
  gaussian_null_loading_coefficients: 09a1a87d4a0bdf55ae76e1e04ecb437e172fbf9a8038b92d07f9b37d8a7002c5
  gaussian_oriented_null_directional_entropy: 5648101dba078aedadbbb13ea352082bf65c686780a3fe555ce6be586841cc68
  gaussian_test_pvalues: 77bd992c815e7093fd72c2543d655df56c15eef2bf6240d46d729bce9f86ca50
  benjamini_hochberg_step_up: 2654feec463fe339f6bebe029e9f1cbff9e970db6ad51faa3b66f632a90eb875
  false_discovery_rate: ce88ab68fe7c28f8baff59d3beb8b2c38cbb031634b8dc2f3cb3cad67a3309d1
  gaussian_worst_case_bh_fdr: 5c3438b5ed0ad228d4c497cb1bba3bc00df045464de3732cd69e217ebf9b28a1
verified_proof_digest: 750c888e71528f1bacb4aa12d094a07185fb6336c87c187d1191373934da6b12
---

# Weighted group cutoffs and partial-FDP proof

## Goal

Target: [One-sided Gaussian BH bound from oriented null directional entropy](../assets/directional_entropy_one_sided_fdr_bound.md).

Prove its frozen finite-q inequality and its uniform asymptotic consequence without changing the target. Use the all-test masses pi_h=m_{0,h}/m, all one-sided true-null means theta_i<=0, arbitrary alternatives, possibly correlated group projections, and both loading endpoints. The approach is [Directional-entropy finite-q bound with individually weighted tail cutoffs](../ideas/idea_676ddf6ca5aa.md). Native library searches for oriented directional entropy/BH, conditional tail ratios/logarithmic strips, partial false discoveries/leave-one-out, and Gaussian quantiles/Chernoff bounds found no matching library result; no additional black-box lemma or adapted library proof is needed.

## Plan

1. [x] **Separate the empty-null case and fix the actual group masses.** If m_0=0, V=0 identically, the entropy and loading sums vanish, and both conclusions follow directly. Otherwise retain exactly the approved grouping G_1,...,G_H, with pi_h=m_{0,h}/m>0 and sum_h pi_h=pi_0<=1. Write Y_h=v_h^T Z, u=overline(Phi)^(-1)(q), and b_h=overline(Phi)^(-1)(q pi_h)>=u. Each Y_h is standard normal. Do not require independence between any two Y_h. In the proof use the conventional LaTeX notation below for these survival functions and inverses.

2. [x] **Prove the conditional bound for each partial FDP, conditioning on the full factor vector.** Put
   $$
   \operatorname{FDP}_h=\frac{\sum_{i\in G_h}\mathbf 1\{i\in\mathcal R_q\}}{R\vee1},\qquad \operatorname{FDP}=\sum_{h=1}^H\operatorname{FDP}_h.
   $$
   Let R_i be the BH rejection count with p_i replaced by zero. Repeat the displayed leave-one-out argument in the approved dependency [Lei conditional leave-one-out FDP bound](../assets/lei2026_conditional_fdp_bound.md), summing only over i in G_h: R_i>=1 and
   $$
   \frac{\mathbf1\{i\in\mathcal R_q\}}{R\vee1}=\frac{\mathbf1\{p_i\le qR_i/m\}}{R_i}.
   $$
   Given the full Z, p_i is independent of R_i, including when p_i is conditionally deterministic. For i in G_h its conditional null CDF depends on Z only through Y_h, so the same argument gives
   $$
   \mathbb E(\operatorname{FDP}_h\mid Z)\le\frac qm\sum_{i\in G_h}M_i(Y_h),\qquad M_i(y)=\sup_{0<t\le q}\frac{F^{\theta_i}_{r_i,y}(t)}t.
   $$
   Here F^{theta}_{r,y}(t) is the conditional rejection probability for theta+ry+sqrt(1-r^2) epsilon. Establish F^{theta}_{r,y}(t)<=F^0_{r,y}(t) for theta<=0 directly by translating the Gaussian variable; write M^0_r(y)=sup_{0<t<=q}F^0_{r,y}(t)/t. This is a groupwise restriction of the approved proof, not an assertion of independence after conditioning only on Y_h. Check the deterministic BH identity with non-strict threshold inequalities and R=0 as well.

3. [x] **Prove the scalar outer-strip envelope and evaluate its exact cost.** For each fixed r in [0,1] and t in (0,q], F^0_{r,y}(t) is nondecreasing in y. Its integral against the standard-normal density is t because rY+sqrt(1-r^2) epsilon is standard normal. Therefore, for every finite y,
   $$
   \overline\Phi(y)F^0_{r,y}(t)\le\int_y^\infty\phi(z)F^0_{r,z}(t)\,dz\le t,
   \qquad M^0_r(y)\le\frac1{\overline\Phi(y)}.
   $$
   The argument includes r=0 and r=1 directly and uses no conditional-density division by sqrt(1-r^2). Consequently the outer strip for each group satisfies
   $$
   \int_u^{b_h}\phi(y)M_i(y)\,dy\le\int_u^{b_h}\frac{\phi(y)}{\overline\Phi(y)}\,dy
   =\log\frac{\overline\Phi(u)}{\overline\Phi(b_h)}=\log\frac1{\pi_h}.
   $$
   Derive the equality by differentiating -log(overline(Phi)(y)); it is zero when pi_h=1. The formula for r=1 has a conditional indicator at the threshold, which changes no integral at a Gaussian-measure-zero endpoint.

4. [x] **Combine the central integral with each group's own complement.** The other approved dependency, [Lei integrated conditional Gaussian tail-ratio bounds](../assets/lei2026_integrated_conditional_tail_ratios.md), and the theta_i<=0 domination give
   $$
   \int_{-\infty}^u\phi(y)M_i(y)\,dy\le\frac12+\frac{\gamma_i u}{\sqrt{2\pi}}.
   $$
   At r_i=0 use gamma_i=1; at r_i=1 use the dependency's stated deterministic endpoint, avoiding any division by gamma_i. Multiply the conditional partial-FDP bound by the full-Z-measurable event {Y_h<=b_h}, integrate over Z, and use the standard-normal marginal of Y_h. This and step 3 give
   $$
   \mathbb E[\operatorname{FDP}_h\mathbf1\{Y_h\le b_h\}]
   \le\frac qm\sum_{i\in G_h}\left(\frac12+\frac{\gamma_i u}{\sqrt{2\pi}}+\log\frac1{\pi_h}\right).
   $$
   Separately, 0<=FDP_h<=1 yields
   $$
   \mathbb E[\operatorname{FDP}_h\mathbf1\{Y_h>b_h\}]\le\mathbb P(Y_h>b_h)=q\pi_h.
   $$
   Keep these separate partial-FDP decompositions. Do not replace them by one event truncating every projection or by a tail cost Hq.

5. [x] **Sum to obtain exactly the finite-q target.** Sum step 4 over h, using sum_h pi_h=pi_0, the partition of I_0, and the approved entropy definition. The central constants sum to (q/2)pi_0; the complement costs sum to q pi_0; the strip costs sum to q sum_h pi_h log(1/pi_h). Thus
   $$
   \operatorname{FDR}_{\mathrm{BH}}^{(1)}\le\frac32q\pi_0+\frac{qu}{\sqrt{2\pi}}\frac1m\sum_{i\in I_0}\gamma_i+q\mathcal E_0.
   $$
   Combine with FDP<=1 for the displayed minimum with 1. Check explicitly that no normalization by m_0 was substituted and no step restricted the means or loadings of alternatives, the covariance among projections, the factor dimension, or the number of groups.

6. [x] **Deduce the stated uniform asymptotic constant from this same bound.** Put L=log(1/q). For a standard normal G and u>0, the Gaussian exponential moment, computed by completing the square, and Markov's inequality give q=P(G>=u)<=exp(-u^2/2), hence u<=sqrt(2L). Using 0<=m^(-1)sum_{i in I_0}gamma_i<=pi_0<=1, divide step 5 by q sqrt(L) to obtain
   $$
   \frac{\operatorname{FDR}_{\mathrm{BH}}^{(1)}}{q\sqrt L}\le\frac{3}{2\sqrt L}+\frac1{\sqrt\pi}+\frac{\mathcal E_0}{\sqrt L}.
   $$
   Under precisely E_0=o(sqrt(L)), take limsup to obtain 1/sqrt(pi). This deterministic upper bound holds separately at every q, so m, d, all means and loadings, the grouping, H, and pi_0 may vary with q; no fixed-model limiting interchange is needed. Include sequences that have m_0=0 at some or all levels.

## Verification

Verify first the groupwise conditional leave-one-out identity under the full Z, then the elementary monotone-tail inequality in step 3 for every r in [0,1]. The exact strip integral, rather than an estimate depending on b_h-u, must be log(1/pi_h). Audit the coefficients after summation: q pi_0 from complements, q pi_0/2 from central constants, qu/(sqrt(2 pi) m) times the sum of gamma_i, and q E_0 from strips. Check no-null, all-zero-loading, full-loading, pi_h=1, negative-null-mean, R=0, and correlated or identical projection cases without adding a hypothesis. The asymptotic step must use the all-test entropy E_0=o(sqrt(log(1/q))) and a q-wise bound uniform in every allowed model parameter. No numerical computation is needed to verify this proof route.

## Assumed definitions

No draft definition or unproved dependency is assumed. The only theorem-level black boxes are the target's two approved dependencies, lei2026_conditional_fdp_bound and lei2026_integrated_conditional_tail_ratios; the restricted leave-one-out sum and the scalar strip inequality are explicitly rederived above.

Use the approved definitions gaussian_multifactor_representation, gaussian_multiple_testing_model, gaussian_null_loading_coefficients, gaussian_oriented_null_directional_entropy, gaussian_test_pvalues, benjamini_hochberg_step_up, false_discovery_rate, and gaussian_worst_case_bh_fdr exactly as supplied in the context pack. The conditional-CDF and standard-normal notation required for the two black boxes is supplied in their displayed statements in the same pack. The quantities FDP_h, M_i, M^0_r, b_h, and L above are local proof notation, not new research definitions. No unverified observation in an idea node is used as a mathematical premise.

## Outcome

All six steps are proved in the `## Proof` section of [One-sided Gaussian BH bound from oriented null directional entropy](../assets/directional_entropy_one_sided_fdr_bound.md). The target statement is unchanged and the asset remains draft, pending independent proof verification and researcher approval. The proof explicitly establishes the partial-FDP leave-one-out identity under the full factor vector, measurability of the suprema, the exact logarithmic strip cost, the summed complement cost $q\pi_0$, and the uniform asymptotic bound, including all endpoint and empty-null cases in the plan.

Only the approved definitions listed above and the two approved dependencies are used; no draft definitions or additional unproved observations are assumed. The leave-one-out argument is written out for the restricted group sum and the scalar outer-strip inequality is proved directly. Notation was checked against the supplied approved definitions and the configured `macros.tex` and `notations.tex`, which contain no additional conventions; no missing or conflicting symbols or relationship links were found.

## Verdict

confirmed
The approved scalar integral bound applies: full-$Z$ conditional independence justifies groupwise partial-FDP leave-one-out with all other true nulls unchanged; $\pi_h=m_{0,h}/m$ and $b_h=\overline\Phi^{-1}(q\pi_h)$ give exactly $q\pi_0$ complement cost and $q\sum_h\pi_h\log(1/\pi_h)$ strips without independent group projections.
No gaps found: checked composite $\theta_i\leq0$, $r_i=0,1$, $\gamma_i$, rational-plus-$q$ measurability, $m_0=0$, and levelwise uniformity over all model sequences with $\mathcal E_0=o(\sqrt{\log(1/q)})$. Live Statement and Proof hashes match the frozen pack.
