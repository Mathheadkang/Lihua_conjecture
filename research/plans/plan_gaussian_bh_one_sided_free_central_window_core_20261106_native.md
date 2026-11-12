---
title: >-
  Native reconstruction of the one-sided free central-window kernel and BH
  central bound
type: plan
status: succeeded
target_asset: gaussian_bh_one_sided_free_central_window_core
inspired_by:
  - idea_41e71c79a5f9
adapts: []
proof_digest: aeb60a5dea1c1275370d85bae627b30168270a65794f50e99743492f4a70ff1a
statement_digest: 779c4649ca5118819e8dfa6dbce8e2a5f940384b9968185d078f02aeffa659b9
dependency_digests:
  gaussian_multifactor_representation: e3a61244f476941be96780294a5d26af63dd415aa7462c2662601bf6aeb086fe
  gaussian_null_loading_coefficients: 09a1a87d4a0bdf55ae76e1e04ecb437e172fbf9a8038b92d07f9b37d8a7002c5
  gaussian_test_pvalues: 77bd992c815e7093fd72c2543d655df56c15eef2bf6240d46d729bce9f86ca50
  benjamini_hochberg_step_up: 2654feec463fe339f6bebe029e9f1cbff9e970db6ad51faa3b66f632a90eb875
  false_discovery_rate: ce88ab68fe7c28f8baff59d3beb8b2c38cbb031634b8dc2f3cb3cad67a3309d1
verified_proof_digest: aeb60a5dea1c1275370d85bae627b30168270a65794f50e99743492f4a70ff1a
---

## Goal

Target: [One-sided free central window kernel and BH central-contribution bound](../assets/gaussian_bh_one_sided_free_central_window_core.md).

Prove the frozen Statement exactly: the scalar pointwise and central-integral kernel inequalities for every $0<q<1/2$, including the stated $r=0$ and $r=1$ interpretations, and the BH central contribution bound for every $0<q\le1/10$ and every finite admissible multifactor model. Negative null means, arbitrary loading orientations, zero/unit loadings and singular covariance remain allowed. The extracted candidate argument is an unchecked guide; every substantive step below is reconstructed. No DCL consequence, block hypothesis, unproved asset or source-plan assumption is used.

## Plan

1. [x] **Fix scope and measurable conventions.** Set $U=\overline\Phi^{-1}(q)>0$, $t_k=qk/N\in(0,1)$ and $u_k=\overline\Phi^{-1}(t_k)\ge U$, $1\le k\le N$. For $0\le r<1$, let $s=\sqrt{1-r^2}>0$ and use the target's finite real-variable kernel. Show that $(v,y)\mapsto\rho_r(v,y)$ is continuous and nonnegative. For each real $y$, its supremum over $v\ge U$ equals its supremum over the countable dense set $(\mathbb Q\cap[U,\infty))\cup\{U\}$; therefore the supremum is Borel measurable, allowing an extended nonnegative integral before finiteness is proved. At $r=1$ use the indicator kernel, whose supremum over $v\ge U$ is $\mathbf1\{y\ge U\}/\overline\Phi(y)$: for $y\ge U$ the maximum over $U\le v\le y$ occurs at $v=y$, and for $y<U$ it vanishes. This also establishes Borel measurability at the singular endpoint.

2. [x] **Reconstruct the bivariate density identity.** For all real $x,y$, expand the exponents to verify

   $$
   \phi(x)s^{-1}\phi((y-rx)/s)=\phi(y)s^{-1}\phi((x-ry)/s).
   $$

   Integrate in $x$ from the finite real $v$ to infinity, using the substitution $(x-ry)/s$ on the right. This gives exactly

   $$
   \phi(y)\overline\Phi((v-ry)/s)=\int_v^\infty\phi(x)s^{-1}\phi((y-rx)/s)\,dx.
   $$

   This is direct algebra and integration, rather than a black-box conditional-normal theorem.

3. [x] **Prove the pointwise bound on its full domain.** For $x\ge v$, $r\ge0$ gives $|y-rx|\ge(rx-y)_+\ge(rv-y)_+$. Since $\phi$ is even and decreases on $[0,\infty)$, bound the integrand in step 2 by $\phi(x)s^{-1}\phi((rv-y)_+/s)$. Divide by the strictly positive $\overline\Phi(v)$. Obtain both inequalities

   $$
   \phi(y)\rho_r(v,y)\le s^{-1}\phi((rv-y)_+/s)\le(s\sqrt{2\pi})^{-1}
   $$

   for every real $y$ and every $v\ge U$, with no sign restriction on $y$ and including $r=0$.

4. [x] **Integrate the envelope and handle both scalar endpoints.** As $v\ge U$ and $r\ge0$, replace $(rv-y)_+$ by $(rU-y)_+$ in the envelope from step 3. Because $\phi(y)>0$, taking the supremum commutes with multiplying by $\phi(y)$. Split the integral at $y=rU\le U$ and compute

   $$
   \int_{-\infty}^{rU}s^{-1}\phi((rU-y)/s)\,dy=\tfrac12,
   \qquad
   \int_{rU}^{U}\frac{dy}{s\sqrt{2\pi}}=\frac{(1-r)U}{s\sqrt{2\pi}}.
   $$

   Verify $(1-r)/s=\gamma_r$ to obtain the exact claimed constant. At $r=0$, check directly $s=1$, $\gamma_0=1$, $\rho_0\equiv1$: the scalar integral is $\Phi(U)$, still bounded by the displayed envelope integral. At $r=1$, the kernel vanishes for every $y<U\le v$; at $y=U$ its supremum is $1/q$, a finite value on a Lebesgue-null singleton, so the central integral is exactly zero. No limit $s\downarrow0$ or density argument for a degenerate conditional law is used.

5. [x] **Reprove the deterministic BH forced-zero identity, including ties.** For any $p\in[0,1]^N$, write $K=\widehat k_q(p)$ and prove $R_q(p)=K$: when $K>0$, at least $K$ coordinates satisfy $p_j\le t_K$, while more than $K$ would make their larger count a qualifying rank; when $K=0$ the rejection set is empty by definition. Set $p_i$ to zero to form $p^{(i)}$ and $R_i=\widehat k_q(p^{(i)})$. Show $1\le R_i\le N$, $R_i\ge K$, and $R_i$ depends only on the other coordinates. If $p_i\le t_{R_i}$, restoring $p_i$ preserves a qualifying rank $R_i$, giving $K=R_i$ and rejection of $i$. Conversely, rejection of $i$ means $p_i\le t_K\le t_{R_i}$, so the same equality holds. Conclude for all deterministic configurations

   $$
   \frac{\mathbf1\{i\in\mathcal R_q(p)\}}{R_q(p)\vee1}=\frac{\mathbf1\{p_i\le t_{R_i}\}}{R_i}.
   $$

   Include $K=0$, equal p-values and threshold equalities explicitly. The finite rank/count maps are Borel measurable because their defining comparisons are Borel.

6. [x] **Derive the conditional formula with composite-null domination.** For each $i$, condition on $\mathcal G_i=\sigma(Z,(\varepsilon_j)_{j\ne i})$. The integer $R_i$ is $\mathcal G_i$-measurable and $\varepsilon_i$ is independent of $\mathcal G_i$. For $0<r_i<1$, let $Y_i=a_i^{\mathsf T}Z/r_i$; compute

   $$
   \Pr(p_i\le t_{R_i}\mid\mathcal G_i)=\overline\Phi((u_{R_i}-\theta_i-r_iY_i)/s_i).
   $$

   This follows from the strictly decreasing p-value transform and independence of the remaining residual. At $r_i=1$, replace this expression by $\mathbf1\{\theta_i+Y_i\ge u_{R_i}\}$, using the deterministic conditional coordinate; negative null means give an event contained in $\{Y_i\ge u_{R_i}\}$. For $r_i=0$, compute directly $\overline\Phi(u_{R_i}-\theta_i)\le\overline\Phi(u_{R_i})$ for $\theta_i\le0$, without evaluating $0\cdot(-\infty)$ or a composite kernel at an infinite argument. For $s_i>0$, monotonicity similarly proves $\rho^{\theta_i}_{r_i}\le\rho_{r_i}$. Use $\overline\Phi(u_k)/k=q/N$ and step 5. After multiplication by any $Z$-measurable central/shell indicator and taking expectations, obtain the exact conditional equality with the mean-dependent kernels wherever defined and its null-mean domination by the target kernels. No unconditional independence of $R_i$ and $Y_i$ is needed.

7. [x] **Prove the central decomposition and bound each loading class.** Use $Y_i=a_i^{\mathsf T}Z/r_i\sim N(0,1)$ for $r_i>0$, and use $Y_i=-\infty$ only as the event-label convention for $r_i=0$. The events $\{Y_i\le U\}$ and $\{Y_i>U\}$ partition the space, so summing the FDP identity over the fixed null set gives $\mathrm{FDR}=\mathrm{Ce}+\mathrm{Sh}$. Step 6 gives the target's central and shell dominations, interpreting the zero-loading boundary kernel as the constant $1$. For $0<r_i<1$, use $u_{R_i}\ge U$, dominate by the measurable supremum from step 1, and integrate using the marginal standard normal law of $Y_i$ and step 4. For $r_i=1$, its dominated central contribution is zero almost surely: the only possible intersection $Y_i\ge u_{R_i}\ge U$ with $Y_i\le U$ lies in $\{Y_i=U\}$, which has probability zero regardless of its dependence on $R_i$. Thus its central contribution is at most the claimed $\frac qN(1/2+\gamma_iU/\sqrt{2\pi})=q/(2N)$. At $r_i=0$, step 6 gives a contribution at most $q/N$; the scalar real-$y$ integral is not substituted for this all-central event convention.

8. [x] **Establish the small-level constant without numerical assumptions.** Put $a=\sqrt{\pi/2}$. Integrate $e^{-z}\le1-z+z^2/2$ for $z=x^2/2\ge0$ on $0\le x\le a$ to prove

   $$
   \int_0^a\phi(x)\,dx\le\tfrac12(1-\pi/12+\pi^2/160)<\tfrac25.
   $$

   Check the strict final inequality by the equivalent polynomial $3\pi^2-40\pi+96<0$; for example, $157/50<\pi<22/7$ and the fact that this polynomial decreases throughout that interval give an entirely rational check. Therefore $\overline\Phi(a)>1/10$. For $q\le1/10$, the inverse survival function gives $U>a$, hence $1\le1/2+U/\sqrt{2\pi}$ (indeed strictly). Apply this only to the zero-loading contribution in step 7. Sum all loading classes and obtain precisely

   $$
   \mathrm{Ce}\le\frac qN\sum_{i\in I_0}\left(\tfrac12+\frac{\gamma_iU}{\sqrt{2\pi}}\right).
   $$

   Treat an empty null set by the zero-sum convention. Keep the scalar domain $0<q<1/2$ separate from the consequence's domain $0<q\le1/10$.

## Verification

Steps 1--4 prove all scalar claims with Borel measurability, exact constants and both loading endpoints. Steps 5--8 prove the stated consequence from the approved model/BH/FDR definitions alone; they reconstruct rather than assume the extracted candidate's conditional formula. Independently check the exponent identity, both Gaussian integrations, forced-zero rank restoration, the conditioning sigma-field and all endpoint events. Check that each use of $Y_i\sim N(0,1)$ has $r_i>0$, and each use of $q\le1/10$ is confined to the BH consequence. The proof must not assume nonsingularity, positivity of loadings, zero null means, a fixed dimension, or independence between $R_i$ and a factor projection. No DCL or unrestricted-FDR conclusion is part of the deliverable. All checklist items are established in the completed proof; fresh independent verification remains pending.

## Assumed definitions

Only the approved definitions in the context pack are used: Gaussian multifactor representation and its Gaussian multiple-testing model, Gaussian null loading coefficients, Gaussian test p-values and true nulls, ordinary Benjamini--Hochberg step-up procedure, and false discovery rate. There are no draft definitions or unproved dependencies assumed. Elementary Gaussian density algebra, nonnegative integration, independent residual conditioning and standard-normal continuity are explicitly justified in the checklist. Native library searches for the central kernel, normal conditional-density kernel and BH forced-zero/leave-one-out identity returned no analogue. The extracted proof section is unchecked source material, not a black-box lemma.

## Outcome

All eight checklist items are established. The complete proof is under `## Proof` in [One-sided free central window kernel and BH central-contribution bound](../assets/gaussian_bh_one_sided_free_central_window_core.md). The scalar result retains $0<q<1/2$, while the BH central consequence retains $0<q\le1/10$, for all finite admissible multifactor models including negative null means, zero/unit loadings and singular covariance. No draft definition or unproved result is assumed; the elementary tail certificate is derived in the proof. No extra DCL consequence is asserted.

Every established step was first saved in Progress and has now been transferred to the asset proof. The pre-existing asset content, including the frozen Statement, draft status, extracted candidate and provenance, is byte-for-byte preserved: removing only the inserted proof recovers the original asset SHA-256 `9cb3d6238974fcdd1e4c1b2ea4db38fdcae6d4905f31c8ccbff8aa0bd581d50e`.

Maintenance validation returned 0 problems; scoped links preview/apply returned 0 changes and 0 review items. The notation audit read the approved definitions and their dependencies, configuration, macros and notation file. The latter two contain only placeholder comments; all symbols are covered by approved definitions or explicitly local definitions, with no new notation conflict found. The zero-loading label is explicitly separated from finite-variable kernel evaluation. This is a completed native proof execution, pending independent proof verification and researcher approval; no approval record or loop state was edited.


## Verdict
confirmed

Independently checked the Statement against the canonical eight-step Proof and declared definitions. The scalar inequalities hold for every finite real y, v >= U and 0 <= r < 1 throughout 0 < q < 1/2. The countable dense supremum is Borel measurable; the density identity, positive-part envelope, integration split and exact coefficient gamma_r are valid. At r = 0 the scalar integral uses the standard normal variable, while the BH event convention uses the constant central label; these are correctly distinguished. At r = 1 the central kernel vanishes except at the single null-measure boundary point.

The deterministic forced-zero identity includes ties, threshold equality, N = 1 and zero original rejection count. Conditioning on Z and all other residuals fixes the random rank and leaves the selected residual independent, so the conditional formula is justified without assuming independence between the rank and its factor projection. Nonpositive null means give the claimed domination, including zero and unit loadings. Arbitrary alternative means, finite N and factor dimension, loading orientations and admissible singular covariances introduce no additional restriction. The exact Ce + Sh decomposition and both contribution dominations follow under their stated event convention.

The BH central bound uses 0 < q <= 1/10 only for zero loadings. Independently recomputed f(157/50) = 240053/2400000 > 1/10; the preceding Taylor envelope, integration and monotonicity certificate imply the required U > sqrt(pi/2). All constants, the empty-null case and the distinction between the scalar and BH q ranges are retained. No substantive gap, added hypothesis or repair was needed.
