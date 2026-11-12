---
title: Radial truncation and monotone Gaussian tail strips
type: plan
status: succeeded
target_asset: multifactor_radial_fdr_bounds
inspired_by: []
adapts: []
proof_digest: 96ef71ae1ec61c66e5844510691fc97510259a22ea1b441ffb4a1673465ccb59
statement_digest: c1bc65d229f2e3db424011091017ad2c03cd4b99cd43b5a9fc22c50df1a8d8a7
dependency_digests:
  lei2026_conditional_fdp_bound: 44ffaa8350cce69886ffb1907cd5a32495616e8ae1bfffc50faacce9e404d689
  lei2026_integrated_conditional_tail_ratios: eaba74a3d26ad4ac1b23dbf9994b6056da3e28d3e763ef838fb82f70c8fc5867
  gaussian_multifactor_representation: e3a61244f476941be96780294a5d26af63dd415aa7462c2662601bf6aeb086fe
  gaussian_null_loading_coefficients: 09a1a87d4a0bdf55ae76e1e04ecb437e172fbf9a8038b92d07f9b37d8a7002c5
  gaussian_test_pvalues: 77bd992c815e7093fd72c2543d655df56c15eef2bf6240d46d729bce9f86ca50
  benjamini_hochberg_step_up: 2654feec463fe339f6bebe029e9f1cbff9e970db6ad51faa3b66f632a90eb875
  false_discovery_rate: ce88ab68fe7c28f8baff59d3beb8b2c38cbb031634b8dc2f3cb3cad67a3309d1
  gaussian_worst_case_bh_fdr: 5c3438b5ed0ad228d4c497cb1bba3bc00df045464de3732cd69e217ebf9b28a1
verified_proof_digest: 96ef71ae1ec61c66e5844510691fc97510259a22ea1b441ffb4a1673465ccb59
---

## Goal

Target: [Finite-level radial bounds for Gaussian multifactor BH](../assets/multifactor_radial_fdr_bounds.md).

Prove the frozen statement for both p-value tracks and all deterministic Gaussian multifactor representations, retaining its exact $q$ ranges, radial quantile, $\Delta_s(d,q)$, composite one-sided true nulls, and degenerate loading endpoints. The approved dependencies are used through their statements; the radial tail-strip argument below is derived directly.

## Plan

1. [x] **Fix the track and verify the radial quantile comparisons.** Fix $s\in\{1,2\}$, an admissible $m,d,\theta,A$, and the statement's range of $q$. Put $u=u_s(q)$ and let $b>0$ satisfy $\mathbb P(\|Z\|>b)=q$. The $\chi_d$ law is continuous with a strictly decreasing survival function on $(0,\infty)$, so this positive quantile exists uniquely. Since $\|Z\|\geq |Z_1|$, for the one-sided track $q\geq\overline\Phi(b)$, and for the two-sided track $q\geq2\overline\Phi(b)$. Deduce $b\geq u$, $\Delta_s(d,q)\geq0$, and $\mathbb P(\|Z\|>b)=q$ with no strict/non-strict boundary discrepancy.

2. [x] **Set up each null's scalar projection without losing full-factor independence.** For $i\in I_0$ with $r_i>0$, put $v_i=a_i/r_i$ and $W_i=v_i^{\mathsf T}Z\sim\mathcal N(0,1)$. When $r_i=0$, choose any deterministic unit vector $v_i$ (possible because $d\geq1$) and use the same notation. For a generic $r\in[0,1]$, let $F^{(s)}_{r,z}(t)$ be the boundary-null conditional p-value CDF in the approved integrated-tail-ratio lemma, and put $G^{(s)}_r(z)=\sup_{0<t\leq q}F^{(s)}_{r,z}(t)/t$. Conditional on the full $Z$, the actual null CDF equals this boundary CDF at $W_i$ for $s=2$ and is bounded above by it for $s=1$ because $\theta_i\leq0$. State this domination also for $r_i=1$ using the deterministic threshold event. All coordinates, including deterministic ones, remain conditionally independent given the full $Z$; do not replace this conditioning by conditioning on a single $W_i$. Take the supremum over a countable dense set together with $q$, using right continuity, to justify measurability if needed.

3. [x] **Truncate the FDP radially before bounding its conditional expectation.** Let $B=\{\|Z\|\leq b\}$. Since $0\leq\operatorname{FDP}\leq1$, the contribution from $B^c$ is at most $q$. Apply the approved [Lei conditional leave-one-out FDP bound](../assets/lei2026_conditional_fdp_bound.md) given the full $Z$, then the CDF domination from step 2, to obtain
   $$
   \operatorname{FDR}^{(s)}_{\mathrm{BH}}
   \leq q+\frac qm\sum_{i\in I_0}\mathbb E\!\left[\mathbf1_B G^{(s)}_{r_i}(W_i)\right].
   $$
   If $I_0=\varnothing$, instead record directly that $V=0$ almost surely and the FDR is exactly zero; the displayed upper bound is still valid but does not assert that exact value.

4. [x] **Derive the new per-projection tail envelopes from monotonicity and exact marginal calibration.** For every $0<t\leq q$, use $x=\overline\Phi^{-1}(t)$ for $s=1$ and $x=\overline\Phi^{-1}(t/2)$ for $s=2$. For $r<1$, with $\sigma=\sqrt{1-r^2}$, the one-sided CDF is $\overline\Phi((x-rz)/\sigma)$ and is nondecreasing in $z$. The two-sided CDF is
   $$
   \overline\Phi((x-rz)/\sigma)+\overline\Phi((x+rz)/\sigma),
   $$
   which is even and nondecreasing in $|z|$: for $z\geq0$ its derivative is $(r/\sigma)[\phi((x-rz)/\sigma)-\phi((x+rz)/\sigma)]\geq0$ because $x\geq0$. At $r=1$ the corresponding CDFs are $\mathbf1\{z\geq x\}$ and $\mathbf1\{|z|\geq x\}$ and have the same monotonicity. At $r=0$ they are constant in $z$. Exact standard-normal marginal calibration gives $\int\phi(w)F^{(s)}_{r,w}(t)\,dw=t$, also at both endpoints. Hence
   $$
   t\geq\int_z^\infty\phi(w)F^{(1)}_{r,w}(t)\,dw
   \geq\overline\Phi(z)F^{(1)}_{r,z}(t),
   $$
   and
   $$
   t\geq\int_{|w|\geq|z|}\phi(w)F^{(2)}_{r,w}(t)\,dw
   \geq2\overline\Phi(|z|)F^{(2)}_{r,z}(t).
   $$
   Taking the supremum in $t$ proves, for every finite $z$ and every $r\in[0,1]$,
   $$
   G^{(1)}_r(z)\leq\frac1{\overline\Phi(z)},\qquad
   G^{(2)}_r(z)\leq\frac1{2\overline\Phi(|z|)}.
   $$
   This is a direct derivation, not an additional unproved dependency. In particular it retains a strip cost when $r=1$.

5. [x] **Bound the truncated projection integral by the approved central estimate plus the exact strip cost.** Since $B\subseteq\{|W_i|\leq b\}$ and $G\geq0$,
   $$
   \mathbb E[\mathbf1_B G^{(s)}_{r_i}(W_i)]
   \leq\int_{-b}^{b}\phi(z)G^{(s)}_{r_i}(z)\,dz.
   $$
   For $s=1$, enlarge the portion $[-b,u]$ to $(-\infty,u]$ and invoke the approved [Lei integrated conditional Gaussian tail-ratio bounds](../assets/lei2026_integrated_conditional_tail_ratios.md). For $s=2$, invoke that dependency on $[-u,u]$. Its hypotheses hold because the boundary-null scalar representation is exactly $r_iW_i+\sqrt{1-r_i^2}\varepsilon_i$, the track's $q$ range is unchanged, and $r_i\in[0,1]$. The central contribution in either case is at most $1/2+\gamma_i u/\sqrt{2\pi}$. For $r_i=1$, use the dependency's separate endpoint assertion (central integral zero) rather than an expression dividing by $\gamma_i$. Step 4 gives the one-sided strip integral
   $$
   \int_u^b\frac{\phi(z)}{\overline\Phi(z)}\,dz
   =\log\frac{\overline\Phi(u)}{\overline\Phi(b)}
   =\Delta_1(d,q),
   $$
   and the combined two-sided strips give
   $$
   \int_{u<|z|\leq b}\frac{\phi(z)}{2\overline\Phi(|z|)}\,dz
   =\int_u^b\frac{\phi(z)}{\overline\Phi(z)}\,dz
   =\log\frac{q}{2\overline\Phi(b)}
   =\Delta_2(d,q).
   $$
   Zero-width strips have integral zero; projection endpoints have Gaussian measure zero. Conclude for every null, including $r_i=0,1$,
   $$
   \mathbb E[\mathbf1_B G^{(s)}_{r_i}(W_i)]
   \leq\frac12+\frac{\gamma_i u}{\sqrt{2\pi}}+\Delta_s(d,q).
   $$

6. [x] **Sum and match the frozen conclusion.** Insert step 5 into step 3, use $|I_0|/m=\pi_0$, and obtain exactly
   $$
   q+q\pi_0\left(\frac12+\Delta_s(d,q)\right)
   +\frac{q\,u_s(q)}{\sqrt{2\pi}}\frac1m\sum_{i\in I_0}\gamma_i.
   $$
   Intersect this bound with the universal FDR bound $1$. Retain the separately established exact-zero conclusion when there are no true nulls. Explain that the argument imposed no condition on alternative means or deterministic loading directions, preserved the exact conditional independence supplied by the model, and introduced no constant depending on the displayed model parameters; it therefore gives the claimed uniform assertion.

## Verification

Check the algebra separately for $s=1$ and $s=2$: $\overline\Phi(u_1)=q$, $2\overline\Phi(u_2)=q$, and the two symmetric strips cancel the factor $2$ in their envelope, producing precisely the target's $\Delta_2$. The only use of the source's two-sided restriction $u\geq1$ is the approved central-region estimate; the new monotonicity envelope requires only $x\geq0$. Check full-factor conditional independence before invoking the FDP bound, scalar Gaussian marginal calibration before invoking monotonicity, and the deterministic inclusion $B\subseteq\{|W_i|\leq b\}$ before integrating; no independence between $B$ and $W_i$ is asserted. Check non-strict threshold events at $r=1$, composite one-sided means by pointwise domination, $r=0$ by the constant conditional CDF, empty-null sums and exact zero FDR, $b=u$, both $q$ endpoints permitted by the statement, the cap at $1$, and the common conservative range. No numerical computation is required.

## Assumed definitions

No draft definitions or unproved dependencies are assumed. The six definitions listed in the target's `uses_definitions`, together with their displayed dependencies in the context pack, specify the model, null sets, loadings, ordinary BH, and FDR. The only theorem/lemma black boxes are the target's two approved dependencies: [Lei conditional leave-one-out FDP bound](../assets/lei2026_conditional_fdp_bound.md) and [Lei integrated conditional Gaussian tail-ratio bounds](../assets/lei2026_integrated_conditional_tail_ratios.md).

Library searches for `Gaussian conditional tail ratio radial truncation` and for the missing-step terms `monotone conditional survival hazard tail strip` returned no matches. The new strip estimate is therefore rederived in step 4 with its precise hypotheses instead of relying on an unrecorded result.

## Outcome

The complete proof is under `## Proof` in [Finite-level radial bounds for Gaussian multifactor BH](../assets/multifactor_radial_fdr_bounds.md). It establishes all six checklist items for both tracks, with the frozen statement unchanged and the target still `status: draft`. The proof keeps conditioning on the full factor vector, treats all composite one-sided null means, derives the calibrated monotonicity envelopes, integrates both exact tail-strip costs, and includes supremum measurability using rational thresholds together with $q$, the endpoints $r_i=0,1$, empty strips, and the exact-zero FDR when there are no true nulls.

The only result assumptions are the approved [Lei conditional leave-one-out FDP bound](../assets/lei2026_conditional_fdp_bound.md) and [Lei integrated conditional Gaussian tail-ratio bounds](../assets/lei2026_integrated_conditional_tail_ratios.md), used through their statements with their hypotheses checked. All model and procedure definitions are approved; no draft definitions or additional unproved dependencies are assumed. The new radial and tail-strip steps are proved directly.

The notation check against the target's six approved definitions and their displayed dependencies found no undefined or conflicting symbols or missing direct definition links; the configured `macros.tex` and `notations.tex` contain comments only. Asset validation found zero problems. Targeted links preview and apply each reported zero changes and zero review items. The target's statement SHA-256 remains `30d6d009b8a845f66d0bc3d39ae7b9d8f9f46032327fc6c756e519ca2ec70810`.


## Verdict

confirmed

The proof establishes the frozen statement, taking the two displayed Lei estimates as mathematical inputs. Full-factor conditioning gives conditional independence, including point masses; boundary-null domination covers every one-sided mean $\theta_i\leq0$. Each scalar experiment satisfies the integrated estimate's hypotheses and stated level range. The radial complement costs exactly $q$; the projection-event inclusion needs no independence. Calibration and monotonicity give the tail envelopes, and the hazard integrals yield exactly $\Delta_1$ and $\Delta_2$, including the symmetric factor cancellation.

I checked the countable-supremum measurability argument, finite envelopes, arbitrary deterministic loading directions and alternative means, $r_i=0,1$, the two-sided endpoint $u=1$, empty strips, absence of division by $\gamma_i=0$, uniform constants, and the exact zero FDR when there are no nulls. One harmless definitional extension is needed: the conditional-CDF definition names a real conditioning variable, but the cited leave-one-out proof applies unchanged to $\sigma(Z)$ for a vector $Z$, since conditional independence of $P_i$ and $R_i$ is its only conditioning hypothesis.

This verdict does not independently verify the source estimates or approve their background definitions: `conditional_pvalue_distributions` and `gaussian_one_common_factor_model` remain draft. The live statement and proof matched the frozen context pack immediately before this append.
