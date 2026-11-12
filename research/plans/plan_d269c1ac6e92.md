---
id: plan_d269c1ac6e92
title: >-
  Prove fixed-common-loading full FDR continuity by coupling trimming and
  monotone rank shifts
type: plan
status: succeeded
target_asset: gaussian_bh_common_loading_wasserstein_fdr_continuity
inspired_by:
  - idea_014983d6daea
  - idea_f5243b60c394
  - idea_0b5c5ee44247
  - idea_b5b7cac88cc7
adapts: []
tags:
  - gaussian-bh
  - common-loading
  - wasserstein-continuity
proof_digest: 301015f1ff6e3bc510ed60d2ba98d3840ea2752e0dc13d7a1ee96fb5d88fb0b5
statement_digest: c7c3378df201906f905a39cc98232cebf031e1b6084f86c0a75c836910b8f564
dependency_digests:
  gaussian_bh_common_loading_tagged_population: 231a8f229542b6b2293185c00d427dab12fe7b375e48f8d675f3b6828db09437
  gaussian_multiple_testing_model: 535694725c29c2ede682edeaeef6e40dce424d3a88330832f592e18853f99db7
  gaussian_test_pvalues: 77bd992c815e7093fd72c2543d655df56c15eef2bf6240d46d729bce9f86ca50
  benjamini_hochberg_step_up: 2654feec463fe339f6bebe029e9f1cbff9e970db6ad51faa3b66f632a90eb875
  false_discovery_rate: ce88ab68fe7c28f8baff59d3beb8b2c38cbb031634b8dc2f3cb3cad67a3309d1
verified_proof_digest: 301015f1ff6e3bc510ed60d2ba98d3840ea2752e0dc13d7a1ee96fb5d88fb0b5
---

## Goal

Target: [Wasserstein continuity of full population Gaussian BH FDR with a fixed common loading](../assets/gaussian_bh_common_loading_wasserstein_fdr_continuity.md).

Prove all four clauses, at fixed q and sigma, for the exact largest non-strict crossing and its original common-cutoff true-tag numerator. The central deterministic argument trims a small mass from a coupling of scalar scores and pays the lost rank with an additional common shift. It never assumes a unique, strict, interior or transverse crossing.

## Plan

1. [x] **Construct the measurable evaluation on precisely the stated probability space.** Write the convergence set of the partial Gaussian series as a countable Cauchy criterion, hence a measurable subset of sphere times Gaussian sample space. The limit there, with zero elsewhere, is jointly measurable. Prove convergence for each fixed direction from independent centered summands with summable variances (give the maximal-inequality/Cauchy argument, or a complete elementary Gaussian-series argument), and identify all finite-dimensional covariances by L2 limits. Fubini gives, for each deterministic law, a probability-one event of parameter-almost-everywhere valid evaluations; intersect these events for a countable family. Include marginals of every coupling later used in this event. No samplewise bounded linear Gaussian functional on the whole infinite-dimensional Hilbert space is required.

2. [x] **Prove the deterministic largest-crossing facts and their measurability.** For an arbitrary probability law of finite scalar scores, H(r) is increasing and right-continuous on (0,1], so H(r)-r is upper semicontinuous there. A sequence of positive qualifying ranks tending to a positive supremum shows H(rho)>=rho. If H(rho)>rho and rho<1, any slightly larger rank below H(rho) qualifies, a contradiction; at rho=1 the bound H<=1 gives equality. Thus every positive largest root is attained and H(rho)=rho, and V(rho)<=rho. For each deterministic a>0, prove
   
   $$
   \{\rho\ge a\}=\left\{\max_{r\in[a,1]}(H(r)-r)\ge0\right\}.
   $$
   
   Compute the maximum value as the supremum over rational ranks in (a,1), together with the endpoints a and 1, using right-continuity. This proves measurability without incorrectly replacing an isolated qualifying irrational rank by a qualifying rational one. Apply the same argument jointly in the common shift z. Establish joint measurability of H,V in rank and all random inputs, hence of V(rho), D and F. A product-null change of the evaluation representative leaves the entire score law, all H,V values and D identical outside one Gaussian-null set by Fubini; therefore it leaves F unchanged.

3. [x] **Establish the conditional reciprocal-tail bound without residual independence.** For every true tag, compute its conditional p-value CDF given Z=z and use theta<=0 to obtain the displayed comparison with F_z. Derive
   
   $$
   I_z(b):=\int_{(0,b]}\frac{dF_z(t)}t
   =\int_{S^{-1}(b)}^\infty
   \frac{\phi((u-\sigma z)/\tau)}{\tau S(u)}\,du<\infty.
   $$
   
   For u>=1, prove/use the elementary normal-tail lower bound S(u)>=c exp(-u^2/2)/(u+1). The integrand is at most a constant depending on z,sigma times (u+1)exp(-sigma^2 u^2/(2 tau^2)+sigma z u/tau^2); the remaining bounded interval is harmless for every b<1. Explain why stochastic CDF domination bounds the expectation of the nonnegative decreasing function t^{-1}1_{t<=b}; truncation or integration by parts makes this rigorous even at t=0. On the event 0<rho<=a, prove pathwise
   
   $$
   D\mathbf1_{\{0<\rho\le a\}}
   \le q\int\ell\,p(x)^{-1}\mathbf1_{\{p(x)\le qa\}}\,\pi(dx).
   $$
   
   Conditional Tonelli and the marginal bound give a conditional expectation at most q I_z(qa), while D<=1 gives the cap by one. Integrate Z. Show I_z(b)->0 as b down to zero by its already proved integrability, then use bounded convergence in Z. This proves the exact law- and dimension-uniform inequality in clause 2 using no joint independence of residual scores.

4. [x] **Push W1 couplings to jointly realized scalar-score couplings.** For deterministic couplings lambda_n of pi and pi_n with parameter costs delta_n->0, put A(x)=theta+tau X(v), A'(x')=theta'+tau X(v'). Check by Fubini and the variance of X(v)-X(v') that
   
   $$
   \mathbb E_X\int|A-A'|\,d\lambda_n
   \le\int\bigl(|\theta-\theta'|+\tau\sqrt{2/\pi}\|v-v'\|\bigr)\,d\lambda_n
   \le C\delta_n,
   \qquad \lambda_n\{\ell\ne\ell'\}\le\delta_n.
   $$
   
   This is an integrated estimate, not a supremum over directions. Condition on the residual series and retain the independent common Z for the next two steps.

5. [x] **Prove the deterministic trimmed-coupling rank sandwich, including endpoints and competing crossings.** Write u(r)=S^{-1}(qr), fix a in (0,1), 0<gamma<a/2 and e>0, and set
   
   $$
   L_a=\sup_{a/2\le r\le1}|u'(r)|<\infty,\qquad
   h=(e+L_a\gamma)/\sigma,\qquad
   \beta(X)=\lambda_n\{|A-A'|>e\}.
   $$
   
   On beta<=gamma, if r>=a qualifies for the primed law at z, show that s=r-gamma>0 qualifies for the unprimed law at z+h: remove at most gamma coupling mass, and use sigma h-e>=u(s)-u(r). Thus its selected mass is at least r-gamma=s. Exchange laws for the reverse implication. Because step 2 proves attainment, these statements apply to actual largest roots, not just selected local branches. Deduce simultaneously for every real z
   
   $$
   R(z-h)-a-\gamma\le R_n(z)\le R(z+h)+a+\gamma.
   $$
   
   Verify r=1 explicitly: only s=r-gamma is transferred and no rank above one is introduced. Roots below a, including zero, are paid by the additive a; retain every competing qualifying rank.

6. [x] **Integrate only rank monotonicity to obtain L1 rank convergence.** Prove z->R(z) is increasing and takes values in [0,1]. By its Stieltjes measure or a layer-cake calculation, for every residual realization,
   
   $$
   \mathbb E_Z[R(Z+h)-R(Z-h)]\le\frac{2h}{\sqrt{2\pi}}.
   $$
   
   Step 4 and Markov give P_X(beta>gamma)<=C delta_n/(e gamma). Combine with step 5 to obtain the executable bound
   
   $$
   \mathbb E|\rho_n-\rho|
   \le a+\gamma+\frac{2(e+L_a\gamma)}{\sigma\sqrt{2\pi}}
      +\frac{C\delta_n}{e\gamma}.
   $$
   
   First send n to infinity at fixed a,e,gamma, then send e and gamma to zero at fixed a, and finally a to zero. This proves L1 rank convergence for the full largest-root functional. Apply monotonicity to R only; mixed-label D is not asserted monotone.

7. [x] **Prove common-shift anti-concentration at the dependent random cutoff itself.** Fix a residual realization and a parameter x where its evaluation is valid. On the increasing set of shifts with R(z)>0 define g_x(z)=A(x)+sigma z-u(R(z)). For z2>z1 with both ranks positive, prove
   
   $$
   g_x(z_2)-g_x(z_1)\ge\sigma(z_2-z_1).
   $$
   
   Thus the measurable set {z:R(z)>0, |g_x(z)|<=b} has Lebesgue measure at most 2b/sigma, even when g has jumps or the score law has atoms. Integrate the standard normal density and then the parameter law to obtain
   
   $$
   \mathbb E\,\pi\{|T(x)-u(\rho)|\le b,\ \rho>0\}
   \le\frac{2b}{\sigma\sqrt{2\pi}}.
   $$
   
   The cutoff and the score use the same Z throughout. Do not replace this argument by unconditional Gaussian anti-concentration at a supposedly independent random cutoff.

8. [x] **Control the original mixed-label numerator on macroscopic ranks.** Fix a>0, d>0 and e>0. On {rho,rho_n>=a, |rho_n-rho|<=d}, a coupled pair with equal tags and |A-A'|<=e can change selection only if |T(x)-u(rho)|<=e+L_a d (enlarging L_a, if needed, to the same finite bound from step 5). Hence prove
   
   $$
   \mathbb E\left[|V_n(\rho_n)-V(\rho)|\mathbf1_{\{\rho_n,\rho\ge a\}}\right]
   \le \delta_n+\frac{C\delta_n}{e}
   +\frac{2(e+L_a d)}{\sigma\sqrt{2\pi}}
   +\frac{\mathbb E|\rho_n-\rho|}{d}.
   $$
   
   Send n to infinity, then e,d to zero. Use V<=rho and V_n<=rho_n to bound the FDP difference on this event by a^{-1} times the numerator difference plus a^{-1}|rho_n-rho|. This proves macroscopic full-FDP convergence without discarding mixed tags or optimizing the numerator separately.

9. [x] **Remove the microscopic cutoff and complete clause 3.** Cover the remaining rank pairs by: both ranks<=2a; both ranks>=a; and min(rho,rho_n)<a with max(rho,rho_n)>2a. The first part costs at most two copies of the uniform clause-2 microscopic bound at 2a, with zero ranks assigned D=0. The last event forces |rho_n-rho|>a and costs at most E|rho_n-rho|/a. The middle part is step 8. Let n tend to infinity and then a down to zero (take 2a<1). This proves E|D_n-D|->0 and therefore the requested FDR continuity, including vanishing roots and endpoint one.

10. [x] **Construct canonical finite rational laws and identify ordinary BH exactly.** First move every alternative-tagged mean theta to theta+epsilon, leaving its tag and unit direction unchanged; leave true tags unchanged. Its cost is at most epsilon and all resulting tags are canonical. Use separability and the finite first moment to approximate this law in W1 by a finitely supported law whose atoms lie in this canonical domain: truncate the integrable distance to a fixed canonical anchor, cover a compact set carrying all but a small distance-weighted mass by finitely many small balls, and select a canonical support point in each occupied ball. Give the tightness/uniform-integrability calculation, rather than assuming a bounded parameter domain. Approximate its finitely many positive weights by positive rationals k_j/N, tuning the weight error against the finite distances of those atoms to the anchor. Preserve unit directions. Diagonalize the choices to get the stated W1 convergence; alternative-tagged zero points approach positive means with the tag fixed.

11. [x] **Check the finite array, replication, and supremum statement.** Realize weight k_j/N by exactly k_j identical copies of its specified score. The covariance is tau^2 times the directions' Gram matrix plus sigma^2 times the all-ones matrix, so it is PSD with diagonal one; no nonsingularity is needed. For its empirical law H, step 2 gives rho=H(rho)=k/N whenever rho>0, and H(k/N)>=k/N is exactly p_(k)<=qk/N. Therefore rho is the actual largest ordinary BH rank fraction, V(rho) is the rejected true fraction, and D equals ordinary finite FDP pathwise, including ties and no rejections. Uniform replication leaves the empirical law exactly unchanged and hence preserves FDR. Step 9 gives F_pi_n->F_pi. Since canonical finite empirical laws are themselves completed tagged laws, the approximation implies equality of completed and canonical finite suprema at this fixed common loading. Phrase comparison with the original unrestricted finite model class as non-enlargement, not equality with that larger class.

## Verification

Steps 1-2 prove every assertion in clause 1; step 3 proves the exact inequality, conditional comparison and limit of clause 2. Steps 4-9 prove clause 3 using the same realization and common cutoff for both labels; steps 10-11 prove every finite-approximation and replication assertion of clause 4. Check all ratios only on positive ranks. Every estimate permits arbitrary deterministic parameter laws, arbitrary Gaussian residual dependence, atoms, multiple roots, singular finite covariance and endpoint rank one.

Run adversarial deterministic checks during execution: a moving single score atom; two competing qualifying crossings; an isolated tangent qualifying root; a mixed-tag atom exactly at the cutoff; disappearance to zero; and transfer from terminal rank one. These checks validate the stated inequalities, not a numerical replacement for their proofs. In particular, a shifted single atom disproves a naive claim that small score-coupling cost yields small expected supremum CDF discrepancy. No step here requires that claim: step 5 uses trimmed couplings directly.

The proof obligations with the greatest risk are the simultaneous-in-z deterministic sandwich and the random-cutoff band inclusion; write them in full before using their integrated estimates. If either fails, exhibit the precise deterministic configuration and fail the plan rather than modifying the target. No main Gaussian BH bound, uniform sigma-down-to-zero estimate, attained optimizer, Ekeland argument or rare-clone derivative transfer is used or concluded.

## Assumed definitions

Use the five definitions in the context pack: gaussian_bh_common_loading_tagged_population, gaussian_multiple_testing_model, gaussian_test_pvalues, benjamini_hochberg_step_up and false_discovery_rate. All are approved. No unproved asset dependency or draft definition is assumed; the target has no asset dependencies. The elementary Gaussian-series, measure-theoretic and normal-tail ingredients are to be justified within execution, not promoted to new black-box research claims.

## Library search and source applicability

Native library searches for Wasserstein common loading BH continuity, largest crossing common shift measurable rank, conditional marginal microscopic rank integral, jointly measurable isonormal process, and the separate terms Wasserstein, crossing, isonormal, Stieltjes, BH and quantization returned no matches. There is consequently no complete library proof to adapt and no library statement used as a dependency.

The regular-root and conditional-independence applicability gaps recorded in idea_0b5c5ee44247 are respected. The plan follows the original deterministic trimming proposal of idea_014983d6daea and directly checks the random-cutoff band mechanism of idea_f5243b60c394. As recorded in idea_b5b7cac88cc7, it replaces the latter idea's uniform-CDF grid step, which fails for moving atoms, by the all-shifts trimmed-coupling sandwich. These are draft ideas to verify, not cited theorem conclusions. No adaptation of a library result is claimed.


## Outcome

All eleven checklist steps are established in the target asset's `## Proof`, in its correspondingly numbered paragraphs. All four frozen clauses are proved using the five approved definitions, with no draft-definition or unproved-asset assumptions. The target remains draft and awaits fresh independent verification. Its statement, scope and approval history were preserved. The executor wrote no proof digest.

Post-execution checks: research-maintenance validate reported zero problems; links preview and apply reported zero proposed/updated files and zero review items. The notation check compared the five approved definition texts, their definition dependencies in the context pack, all locally introduced symbols, and the configured macros.tex and notations.tex (both contain comments only); no undefined or conflicting notation or missing definition relationship was found. Validation also emitted an informational older-schema migration note; no out-of-scope migration was performed. A byte comparison by SHA-256 confirms that the entire target prefix preceding the new Proof section is unchanged.

The proof gives the exact rational-value maximum measurability argument, the conditional reciprocal-tail integral, the simultaneous all-shifts trimmed rank comparison, integrated rank convergence, a band bound at the same dependent random cutoff, convergence of the original mixed-label numerator, removal of microscopic ranks, and canonical rational finite approximation. It covers endpoint one, zero roots, atoms, non-atomic directions and competing crossings, without expected supremum CDF convergence, residual independence, strict/unique roots or FDP monotonicity.

Adversarial deterministic checks were performed analytically:

- A single p-value atom at t in (0,q) has H(r)=1_{r>=t/q} and largest rank one. Arbitrarily small movement of t changes the supremum CDF discrepancy by one. This invalid estimate is not used. The trimmed transfer still holds by u(r-gamma)-u(r)<=L_a gamma; when t passes q, the rank-one jump to zero is handled by common-shift integration.
- Masses 1/5, 3/10, 1/2 at p-values q/5, q/2, (1+q)/2 have exactly two positive qualifying ranks, 1/5 and 1/2. A small upward shift of the second p-value destroys its crossing. Paragraph 5 transfers the actual largest rank after the common shift, without choosing a branch.
- With r0=sqrt(2)/2, the CDF segment H(r)=r exp(-(r-r0)^2), 0<=r<=1, is increasing: its derivative is exp(-(r-r0)^2)(1-2r(r-r0))>0. Put the remaining mass above q. Its only positive qualifying rank is the irrational tangent r0, so no positive rational rank qualifies, but the supremum of H(r)-r over rational ranks is zero. This checks paragraph 2's use of a supremum of values instead of a supremum of qualifying rational ranks.
- Put mass 1/2 at p=q/2, divided equally between true and alternative tags, and the rest above q. Then rho=1/2 and D=1/2, with a mixed-tag atom exactly at the cutoff. Paragraph 8 includes the closed band. Paragraph 7 still gives slope at least sigma for g and band length at most 2b/sigma; its zero set has at most one point for each fixed residual parameter.
- A mass epsilon at p=q epsilon, with the rest above q, has rho=epsilon, which disappears if its only crossing is lost. A true-tagged atom can have FDP one, so paragraph 9 correctly invokes the probabilistic microscopic bound rather than a deterministic small-FDP assertion; paragraph 5 pays roots below a by the additive a term.
- A terminal qualifying r=1 transfers to s=1-gamma, with the derivative controlled on [a/2,1]. No step introduces a rank above one.

This proves continuity and finite approximation only: no rare-clone derivative transfer, completed-space optimizer, Ekeland conclusion or main Gaussian BH order bound follows here.

## Verdict

confirmed

Independently checked all four clauses against the stated deterministic laws, unit directions and fixed common loading with 0 < sigma < 1. Joint evaluation measurability and countable-law validity, representative invariance, attained largest non-strict crossings and rank-one/zero endpoints are justified. Conditional microscopic-rank control uses only scalar marginals and remains uniform over laws and residual dependence.

The trimmed coupling comparison controls the actual largest rank without selecting a root branch. Common-shift integration gives rank convergence, and the dependent-cutoff band bound uses that same Gaussian shift; together with label-cost control and microscopic-rank truncation, this proves convergence of the original full mixed-label FDP in L1. Canonical rational approximation handles unbounded means, non-atomic directions and alternative-tagged zero means; finite BH identification, threshold ties, singular covariance and uniform replication all check out. No substantive gap or additional hypothesis was found. This verdict establishes continuity and finite approximation only, with no derivative-transfer, optimizer or main-order conclusion.
