---
type: plan
title: Full-BH inverse-p envelope and negative-mean marginal integral
status: succeeded
target_asset: gaussian_bh_negative_null_boundary_strip
inspired_by: []
adapts: []
proof_digest: 68a0df7b3fd7695036652e2e09f469ed326f4e2fb2d48b21aa0992855c75256b
statement_digest: 8cb3729d0db20bedb0d623cce2676cfa7d01e08b10180884af70e5a810e0b568
dependency_digests:
  gaussian_multiple_testing_model: 535694725c29c2ede682edeaeef6e40dce424d3a88330832f592e18853f99db7
  gaussian_test_pvalues: 77bd992c815e7093fd72c2543d655df56c15eef2bf6240d46d729bce9f86ca50
  benjamini_hochberg_step_up: 2654feec463fe339f6bebe029e9f1cbff9e970db6ad51faa3b66f632a90eb875
  false_discovery_rate: ce88ab68fe7c28f8baff59d3beb8b2c38cbb031634b8dc2f3cb3cad67a3309d1
verified_proof_digest: 68a0df7b3fd7695036652e2e09f469ed326f4e2fb2d48b21aa0992855c75256b
---

## Goal

Target: [Shrinking null-mean boundary strip for the actual Gaussian BH FDR](../assets/gaussian_bh_negative_null_boundary_strip.md).
Prove its exact finite-model bounds directly, without changing its Statement or the original BH procedure.

## Plan

1. [x] Establish the full-procedure pathwise envelope. Write k for the largest qualifying rank and R for the actual count. If k=0 there are no rejections. If k>0, at least k p-values are at most qk/N; if their count m exceeded k, then p_(m)<=qk/N<=qm/N would contradict maximality. Thus R=k, including all multiplicities and ties. Since every T_i is finite almost surely, p_i>0; on rejection p_i<=qR/N<=q and 1/R<=q/(Np_i). Consequently

   $$
   \frac{\mathbf 1\{i\in\mathcal R_q\}}{R\vee1}
   \le \frac qN\frac{\mathbf 1\{p_i\le q\}}{p_i}.
   $$

2. [x] For each i in D_a put b=-theta_i>=a>0, and use its exact N(-b,1) marginal to obtain

   $$
   J_b(U):=\mathbb E\!\left[\frac{\mathbf 1\{p_i\le q\}}{p_i}\right]
   =\int_U^\infty\frac{\phi(t+b)}{\overline\Phi(t)}\,dt
   =e^{-b^2/2}\int_U^\infty e^{-bt}\frac{\phi(t)}{\overline\Phi(t)}\,dt.
   $$

   Here phi(t)=(2 pi)^(-1/2)exp(-t^2/2). No joint density, invertible covariance, independence, or conditioning is used; singular covariance still gives the same unit-variance marginals.

3. [x] Prove the needed Mills bound from integration by parts: for t>0,

   $$
   \overline\Phi(t)=\frac{\phi(t)}t-\int_t^\infty\frac{\phi(s)}{s^2}\,ds
   \ge\frac{\phi(t)}t-\frac{\overline\Phi(t)}{t^2},
   \qquad \frac{\phi(t)}{\overline\Phi(t)}\le t+\frac1t\le t+1\quad(t\ge1).
   $$

   Justify the vanishing boundary term and integrate the resulting bound exactly:

   $$
   J_b(U)\le e^{-b^2/2}\int_U^\infty(t+1)e^{-bt}\,dt
   =e^{-b^2/2-bU}\left[\frac{U+1}{b}+\frac1{b^2}\right].
   $$

   For fixed U>=1 both positive factors on the right are decreasing in b>0, so replace b>=a by a. Sum the envelope from step 1 over the deterministic set D_a. This gives precisely the first bound; if D_a is empty both sides are zero.

4. [x] For q<=barPhi(e), set L=log U>=1 and a=a_q=2L/U>0. Drop only exp(-a^2/2)<=1 and compute

   $$
   e^{-a^2/2-aU}\left[\frac{U+1}{a}+\frac1{a^2}\right]
   \le\frac{1+1/U}{2L}+\frac1{4L^2}
   \le\frac34+\frac1{2e}<1.
   $$

   Use |D_q|<=N to obtain the displayed contribution bound and its <=q consequence, also at U=e.

5. [x] Partition the original true-null set exactly as I_0=D_q disjoint-union B_q, retaining equality theta_i=-a_q in D_q and theta_i=0 in B_q. Thus V=V_(D_q)+V_(B_q) with the same original R, even when R=0. Take expectations and apply step 4 to get the stated FDR decomposition. Explain that each step holds at each fixed q with constants independent of N, theta, Sigma, and a, so arbitrary deterministic dependence of these parameters on q is allowed; assert no estimate for the B_q contribution.

## Verification

Execution must supply the deterministic tie argument, exact one-dimensional density identity, integration-by-parts boundary term, elementary exponential integral, monotonic replacement b>=a, and explicit strip constant in this order. Their sum proves every displayed inequality of the unchanged Statement for the unmodified full BH count. Check the empty D_a and no-rejection cases as above; arbitrary positive-semidefinite unit-diagonal covariance needs no limiting argument.

## Assumed definitions

Only the approved definitions gaussian_multiple_testing_model, gaussian_test_pvalues, benjamini_hochberg_step_up, and false_discovery_rate listed by the target are used. No draft definitions, unproved dependencies, or library black boxes are assumed. Library searches for the Gaussian BH envelope and Mills bound yielded no usable proof analogue; lib_chi2024_positive_gaussian_simes has no Proof section and is not adapted or cited as a step.

## Outcome

The complete proof is in the target asset's `## Proof` section. It establishes the full-procedure inverse-$p$ envelope with ties, the one-dimensional negative-mean Gaussian integral and elementary Mills bound, the explicit shrinking-strip constant, and the original-null contribution decomposition. The target Statement is unchanged and its status remains `draft`. Only the four approved definitions listed above are assumed; no draft definitions or unproved dependencies are used. The remaining $B_q$ contribution is not bounded here. Independent proof verification remains a separate stage.

## Verdict

confirmed

The largest-qualifying-rank argument proves R=k even with ties and non-strict comparisons; the pathwise inverse-p bound has the correct direction and covers R=0.
The integration-by-parts identity gives phi(t)/barPhi(t) <= t+1/t <= t+1 for t>=1. The exact exponential integral is finite for b>0, and both factors decrease with b, giving the stated bound at b>=a.
For U>=e, L=log U>=1 and a=2L/U give the coefficient at most (1+1/e)/2+1/4=3/4+1/(2e)<1. These are pointwise bounds with parameter-independent constants, so arbitrary deterministic q-dependent models and a are covered.
The null partition includes theta=-a in D and theta=0 in B, preserves the full BH denominator, and covers empty sets and zero rejections. Unit-diagonal Gaussian marginals suffice even for singular covariance; no unproved dependence assumption is used.
