---
title: Uniform radial quantile plan for slowly growing factor dimension
type: plan
status: succeeded
target_asset: slow_factor_dimension_one_sided_sharpness
inspired_by: []
adapts: []
proof_digest: fd30543ba68c44487beb3d597606b1e5f3407cd4bd352273a1a1ba128ebd5c6e
statement_digest: 41c776b5ba7a93e0fc85e9c920013f0df855975e6702b5c0f76f09e9b822fd15
dependency_digests:
  multifactor_radial_fdr_bounds: c1bc65d229f2e3db424011091017ad2c03cd4b99cd43b5a9fc22c50df1a8d8a7
  lei2026_one_sided_fdr_lower: 09b4a5724c3aab9d4c07183f31173a7b5506fe32d4574e0a52dd9263d4afc94a
  gaussian_factor_dimension_budget: 677f40026fc29f6d446c1fae7754ab94d15a1e3fcf266a733e09aa268ea6da36
  gaussian_multifactor_representation: e3a61244f476941be96780294a5d26af63dd415aa7462c2662601bf6aeb086fe
  gaussian_null_loading_coefficients: 09a1a87d4a0bdf55ae76e1e04ecb437e172fbf9a8038b92d07f9b37d8a7002c5
  gaussian_test_pvalues: 77bd992c815e7093fd72c2543d655df56c15eef2bf6240d46d729bce9f86ca50
  benjamini_hochberg_step_up: 2654feec463fe339f6bebe029e9f1cbff9e970db6ad51faa3b66f632a90eb875
  false_discovery_rate: ce88ab68fe7c28f8baff59d3beb8b2c38cbb031634b8dc2f3cb3cad67a3309d1
  gaussian_worst_case_bh_fdr: 5c3438b5ed0ad228d4c497cb1bba3bc00df045464de3732cd69e217ebf9b28a1
verified_proof_digest: fd30543ba68c44487beb3d597606b1e5f3407cd4bd352273a1a1ba128ebd5c6e
---

## Goal

Target: [Sharp one-sided BH constant with slowly growing factor dimension](../assets/slow_factor_dimension_one_sided_sharpness.md).

Prove the stated limit using the approved finite-level radial inequality and the approved finite one-common-factor lower construction. All bounds used before taking the supremum must hold simultaneously for every integer $1\leq d\leq\lfloor D(q)\rfloor$, with numerical constants independent of $d,m,\theta,A$. Do not impose a bound on the finite construction size as $q$ varies.

## Library search

The native library searches `Gaussian factor dimension chi-square quantile BH` and `Gaussian square moment generating function Mills ratio` returned no matching results. Prove the elementary Gaussian-square moment identity and Mills inequalities directly below; no additional black-box result or dependency is needed. No library proof is adapted.

## Plan

1. [x] Set $\ell=\log(1/q)$ and $n(q)=\lfloor D(q)\rfloor$. Restrict to sufficiently small $q$ that $\ell>2$, $u=\overline\Phi^{-1}(q)\geq1$, and the common range of [Finite-level radial bounds for Gaussian multifactor BH](../assets/multifactor_radial_fdr_bounds.md) applies. Record $1\leq n(q)\leq D(q)$ and $n(q)\log\ell=o(\sqrt\ell)$, without assuming that $D$ is monotone or integer valued.

2. [x] For independent standard normal coordinates, evaluate the one-dimensional Gaussian integral and multiply to obtain $\mathbb E\exp(t\|Z\|^2)=(1-2t)^{-d/2}$ for $0<t<1/2$. Choose $t=(1-1/\ell)/2$ and apply Markov's inequality to the continuous $\chi_d$ tail. Show explicitly that its upper-$q$ quantile satisfies
   $$
   b_d(q)^2\leq B_d(q):=\frac{2\ell+d\log\ell}{1-1/\ell}\leq B(q):=\frac{2\ell+n(q)\log\ell}{1-1/\ell}.
   $$
   Indeed, at $B_d(q)$ the Markov bound is exactly $\exp(-\ell)=q$. This avoids any asymptotic expansion with constants depending on a fixed $d$.

3. [x] Derive by integration by parts the elementary Mills inequalities
   $$
   \frac{x}{1+x^2}\,\phi(x)\leq\overline\Phi(x)\leq\frac{\phi(x)}{x},\qquad x>0,\qquad \phi(x)=\frac{e^{-x^2/2}}{\sqrt{2\pi}}.
   $$
   Use the approved inequality $b_d(q)\geq u\geq1$ and Step 2 to obtain, simultaneously for every admissible $d$,
   $$
   0\leq\Delta_1(d,q)\leq C(q):=\frac{B(q)}2-\ell+\log\bigl(2\sqrt{B(q)}\bigr)+\frac12\log(2\pi).
   $$
   Check this from $\Delta_1=-\ell-\log\overline\Phi(b_d)$ and $b_d+1/b_d\leq2b_d\leq2\sqrt B$. Establish $B/\ell\to2$ and $C/\sqrt\ell\to0$ using the exact identity
   $$
   \frac B2-\ell=\frac{\tfrac12 n(q)\log\ell+1}{1-1/\ell}.
   $$
   Every constant in this bound is displayed and independent of dimension.

4. [x] Use the same Mills inequalities at $u$ to establish $u/\sqrt{2\ell}\to1$. One explicit check is
   $$
   0\leq\ell-\frac{u^2}{2}\leq\log\bigl(2\sqrt{2\ell}\bigr)+\frac12\log(2\pi)
   $$
   for sufficiently small $q$: first show $u^2\leq2\ell$, then apply the lower Mills bound. This introduces no dimension-dependent remainder.

5. [x] Apply [Finite-level radial bounds for Gaussian multifactor BH](../assets/multifactor_radial_fdr_bounds.md) with $s=1$ and use $0\leq\overline\gamma_0\leq\pi_0\leq1$ to get, for every model in the budget class,
   $$
   \operatorname{FDR}_{\mathrm{BH}}^{(1)}\leq q\bigl(\tfrac32+C(q)\bigr)+\frac{qu}{\sqrt{2\pi}}.
   $$
   The right side has no remaining model parameters, so take the supremum over all finite $m$, all means, all loadings and all $1\leq d\leq n(q)$ before taking a limit. Steps 3-4 give $\limsup F_{1,D}(q)/(q\sqrt\ell)\leq1/\sqrt\pi$. Explicitly retain the finite-level theorem's coverage of negative null means, zero loadings, unit-norm loadings and singular covariance matrices.

6. [x] Invoke [Lei finite Gaussian lower bound for one-sided BH](../assets/lei2026_one_sided_fdr_lower.md), including its recorded common-factor preservation under the finite transfer and independent perturbation. For each fixed $q$, choose its arbitrary accuracy parameter $\delta(q)=q^2$ and a corresponding finite example with size $N(q)$. Check from the approved [one-common-factor Gaussian testing model](../definitions/gaussian_one_common_factor_model.md) that its scalar loadings are precisely a $d=1$ multifactor representation. Since $D(q)\geq1$, this example belongs to the budget class. Thus
   $$
   F_{1,D}(q)\geq\ell_{\leq}(q)-q^2.
   $$
   Use the approved expansion $\ell_{\leq}(q)=q\sqrt\ell/\sqrt\pi+q/2+o(q)$ and $q^2/(q\sqrt\ell)\to0$ to obtain the matching liminf. No attainment of a supremum, common construction across levels, bound on $N(q)$, or interchange of a finite-size limit with $q\downarrow0$ is required.

7. [x] Combine the limsup and liminf for the exact target. Note that every fixed positive $d$ obeys the budget condition when the budget is chosen constant, and that the positive-dimension convention includes the all-zero-loading representation with $d=1$.

## Verification

The sole new quantitative obligation is Step 3's uniform bound $\sup_{1\leq d\leq\lfloor D(q)\rfloor}\Delta_1(d,q)=o(\sqrt\ell)$. Check the exact Markov threshold and the signs of $-\ell-\log\overline\Phi(b_d)$ before using it. The upper inequality is taken over the entire budget class at each $q$ before passage to the limit. For the lower inequality, check that the common-factor claim is part of the approved lower dependency's source proof route, rather than inferring factor structure from positive definiteness alone. Its finite size is unrestricted and may vary arbitrarily with $q$. Both sides use the composite one-sided null convention and the same scale $q\sqrt{\log(1/q)}$.

## Assumed definitions

No draft definition or unproved dependency is assumed. The target's definitions and the additionally inspected definition [one-common-factor Gaussian testing model](../definitions/gaussian_one_common_factor_model.md) are approved. The two black-box dependencies are the approved [Finite-level radial bounds for Gaussian multifactor BH](../assets/multifactor_radial_fdr_bounds.md) and [Lei finite Gaussian lower bound for one-sided BH](../assets/lei2026_one_sided_fdr_lower.md). Gaussian-square moments and Mills inequalities are to be established directly in Steps 2-3, not assumed as missing lemmas.

## Outcome

The complete proof is under `## Proof` in [Sharp one-sided BH constant with slowly growing factor dimension](../assets/slow_factor_dimension_one_sided_sharpness.md); its statement is unchanged and its status remains `draft`. All seven steps are established. The explicit Gaussian-square moment bound gives $b_d(q)^2\leq B(q)$ uniformly over the entire dimension budget, and the proved Mills inequalities give $\sup_{1\leq d\leq\lfloor D(q)\rfloor}\Delta_1(d,q)\leq C(q)=o(\sqrt{\log(1/q)})$. The upper supremum is taken at each fixed level before the limit; the lower example is finite at that level with accuracy $q^2$, using the approved source's common-factor preservation. No limit interchange or construction-size restriction is assumed.

The only result assumptions are the two approved dependencies named above, including the lower dependency's recorded source proof route. No draft definitions or additional unproved lemmas are assumed. The target remains subject to independent proof verification and researcher approval.

## Verdict

confirmed
Checked the Gaussian-square MGF and threshold algebra, both Mills inequalities and their remainders, u/sqrt(2 ell) -> 1, and 0 <= gamma_bar_0 <= pi_0 <= 1; C(q) = o(sqrt(ell)) holds simultaneously for every integer 1 <= d <= floor(D(q)), without a fixed-dimension remainder.
The approved lower dependency supplies finite one-factor examples with delta(q) = q^2 at each level, so the supremum precedes the level limit and yields the matching constant 1/sqrt(pi). Confirmation is relative to the two approved dependencies, including the source common-factor preservation assertion; the source paper itself was not independently re-proved.
