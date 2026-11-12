---
type: plan
title: >-
  Conditional sub-Poisson BH calibration through exact null-count ranks and
  Chernoff allocation
status: succeeded
target_asset: gaussian_bh_conditional_subpoisson_calibration
inspired_by:
  - idea_e34ba60a4ca5
  - idea_24a557d20b6f
proof_digest: 08f99d830790bd47ff1258e01007dfe39ffdcac3576a87f5ae2ddaa3ab71c035
statement_digest: 690ddb01c6ce756d2366c4901fffdbdfa396da6353901f8ea0cfffa828f89b29
dependency_digests:
  benjamini_hochberg_step_up: 2654feec463fe339f6bebe029e9f1cbff9e970db6ad51faa3b66f632a90eb875
  false_discovery_rate: ce88ab68fe7c28f8baff59d3beb8b2c38cbb031634b8dc2f3cb3cad67a3309d1
verified_proof_digest: 08f99d830790bd47ff1258e01007dfe39ffdcac3576a87f5ae2ddaa3ab71c035
---

# Conditional sub-Poisson BH calibration through exact null-count ranks and Chernoff allocation

## Goal

Target: [Actual-rank conditional calibration from sub-Poisson null counts](../assets/gaussian_bh_conditional_subpoisson_calibration.md).

Prove its exact frozen statement: for arbitrary original p-values, arbitrary deterministic original null labels and a final conditioning sigma-field containing every alternative p-value, the stated conditional count exponential bound with an extended-real measurable factor K implies conditional FDP at most min{1,4e qK}. Also prove the stated Gaussian sufficient condition, including singular conditional covariance, zero conditional variances, non-strict comparisons and the measurable common null-CDF envelope. Every coordinate and alternative gate stays in the same largest-rank ordinary BH procedure. This supporting lemma is not an unrestricted Gaussian order bound.

The source [count-calibration observation](../ideas/idea_e34ba60a4ca5.md) is guidance to reconstruct, not an assumed theorem. The [null-count rank observation](../ideas/idea_24a557d20b6f.md) motivates the exact conditional rank indexing; its bound depending on the number of random nulls is not used as a dimension-uniform result. The new proof must verify every conditional-version and degeneracy obligation below.

The pack's closest library analogue, lib_chi2024_positive_gaussian_simes, has no Proof section to adapt and concerns positive Gaussian dependence rather than the present final-conditional nonpositive null covariance. Native searches for sub-Poisson BH conditional Chernoff calibration and Gaussian covariance interpolation of negative counts found no applicable proof analogue. The Danskin and OU items do not supply any step here. No library statement or external theorem is used as an additional black box, and no result is listed under adapts.

The workspace root is not a Git repository. Before exclusive plan creation, the target's SHA256 was 5ff2683fffd8e979de36dbab4a2bdd5820b835f35a1d7be5bd3e43d4a8ea0ee1. Its Statement was re-read immediately before this write. Only this new plan file is authorized.

Execution saves the first completed derivation under Progress immediately, then saves later checkpoints after fresh reads and hashes, in patches of at most 6000 tokens. Stop and preserve the exact unresolved obligation if any step fails. Do not change the target Statement, original ideas, approvals, loop state or completion roots.

## Plan

1. [x] **Set up conditional versions on one full-measure set.** Put m=|I0| and treat m=0 immediately. The cases K=infinity and 4e qK>=1 have the trivial conditional upper bound 1; the proof can work on the remaining H-measurable event. For each deterministic grid point s_k=qk/N, k=1,...,N, define the conditional count probabilities p_{k,c}=E[1{C(s_k)=c}|H], c=0,...,m. Their nonnegativity and sum 1 hold on one common set. The finite sum
   $$
   M_k(\lambda)=\sum_{c=0}^m e^{\lambda c}p_{k,c}
   $$
   is continuous in finite lambda. Intersect the countably many full sets for rational lambda>=0, extend the hypothesis by continuity, and prove that the same inequality can then be used for finite H-measurable lambda and for H-measurable grid indices by finite pasting. Explicitly identify M_k(lambda(H)) with the corresponding conditional expectation by its finite sum, using the nonnegative conditional multiplication rule. No unconditional estimate is substituted at an adaptive selected threshold.

2. [x] **Exclude null zeros and establish the deterministic largest-rank identity.** Apply the hypothesis at lambda=1 and a deterministic sequence s decreasing to zero. Conditional bounded convergence gives E[exp C(0)|H]<=1 on {K<infinity}; hence null p-values are nonzero almost surely there. Prove, directly from ordinary BH maximality and including tied p-values, that its rejection count R equals its largest qualifying rank. Define the H-measurable alternative counts
   $$
   A(k)=\sum_{j\notin I_0}1\{P_j\le qk/N\},\quad
   k_i=\max\{k\in\{0,\ldots,N\}:i+A(k)\ge k\},
   \quad0\le i\le m.
   $$
   Each k_i>=i and is H-measurable. For R>0, show R=V+A(R), so R is feasible for k_V. If k_V>R, null-count monotonicity gives C(qk_V/N)>=V, forcing k_V to be a larger qualifying rank. Therefore R=k_V and C(qk_V/N)=V. At R=0, no alternative p-value can be zero because that would make rank 1 qualify; with C(0)=0, the same identities hold. State exactly which probability-one event is needed for this zero case. This argument must keep every original alternative gate.

3. [x] **Apply the count mgf at H-measurable indexed ranks without changing the procedure.** Put alpha=qK and t_i=alpha k_i>0 for i>=1 on the finite-K event. On {V=i}, the original FDP is i/k_i and C(qk_i/N)=i. Fix a deterministic a>e and define the H-measurable bad index condition B_i={i/k_i>a alpha}, equivalent to t_i/i<1/a. On B_i let lambda_i=log(i/t_i)>0; elsewhere set lambda_i=0. Use Step 1's finite-pasting and exponential-polynomial argument to justify conditional Markov at lambda_i:
   $$
   1_{B_i}P(V=i\mid H)
   \le1_{B_i}\exp(i-t_i)(t_i/i)^i
   \le1_{B_i}(e t_i/i)^i.
   $$
   Prove this formula as a conditional probability inequality, not by conditioning on null-dependent quantities. The k_i and t_i depend only on H; V remains the original random null rejection count.

4. [x] **Sum the actual-count contributions and certify 4e.** The combined contribution of all complementary good states is at most a alpha because their FDP is at most that number. On B_i, multiply the last inequality by i/k_i=alpha i/t_i and sum:
   $$
   \begin{aligned}
   E[\mathrm{FDP}\mid H]
   &\le a\alpha+
   \alpha\sum_{i=1}^{m}1_{B_i}e^i(t_i/i)^{i-1}\\
   &\le\alpha\left[a+\frac{e}{1-e/a}\right].
   \end{aligned}
   $$
   Verify the i=1 term, the geometric-series ratio e/a<1 and that no independence or association is used. Take a=2e to obtain 4e alpha, restore the trivial capped branches from Step 1, and integrate with the tower property to prove both general conclusions. Zero rejections contribute zero throughout.

5. [x] **Derive the needed Gaussian covariance interpolation formula directly.** For a fixed finite mean mu and PSD matrix Q with off-diagonal entries <=0, remove all coordinates with Q_ii=0; prove their covariance rows vanish using Q_ij^2<=Q_ii Q_jj. Such coordinates are deterministic and are restored in Step 6. Let D=diag Q and
   $$
   H_{t,\eta}=D+t(Q-D)+\eta I,\qquad0\le t\le1,\quad\eta>0.
   $$
   Convexity and eta I make this positive definite. For its Gaussian density rho_{t,eta} with mean mu, set B=Q-D and differentiate its determinant and quadratic form explicitly:
   $$
   \partial_t\rho_{t,\eta}
   =\frac12\left[
   (x-\mu)^TH_{t,\eta}^{-1}B H_{t,\eta}^{-1}(x-\mu)
   -\operatorname{tr}(H_{t,\eta}^{-1}B)\right]\rho_{t,\eta}
   =\frac12\sum_{i,j}B_{ij}\partial_{ij}\rho_{t,\eta}.
   $$
   For bounded positive smooth increasing factors f_i with bounded first two derivatives, justify differentiating the integral uniformly on t in [0,1] at fixed eta and integrate twice with cutoffs sent to infinity. The Gaussian tails and at-most-quadratic density derivatives pay the cutoff errors. As B has zero diagonal,
   $$
   \frac d{dt}E\prod_i f_i(X_{t,\eta,i})
   =\sum_{i<j}Q_{ij}E\left[
     f_i'(X_{t,\eta,i})f_j'(X_{t,\eta,j})
     \prod_{\ell\ne i,j}f_\ell(X_{t,\eta,\ell})\right]\le0.
   $$
   Integrate in t to compare the correlated expectation with the product expectation at t=0. No unproved Gaussian negative-association theorem is invoked.

6. [x] **Pass to singular Gaussian counts and non-strict thresholds.** At fixed smooth factors, let eta decrease to zero by a common Gaussian square-root coupling and bounded convergence; justify the finite-dimensional positive-semidefinite square-root continuity used in that coupling, or give an elementary equivalent Gaussian weak-convergence argument with its proof. Then approximate f_i(x)=exp(lambda 1{x>=b_i}) by bounded positive smooth increasing factors and use the absence of threshold atoms for each retained positive-variance Gaussian marginal. Restore deterministic zero-variance coordinates with their actual non-strict comparison values. With p_i=P(X_i>=b_i), prove
   $$
   E e^{\lambda\sum_i1\{X_i\ge b_i\}}
   \le\prod_i[1+p_i(e^\lambda-1)]
   \le\exp\left\{\sum_i p_i(e^\lambda-1)\right\}.
   $$
   Check lambda=0, the empty vector and completely deterministic Gaussian laws explicitly. Deterministic indicators satisfy 1+p_i(e^\lambda-1)<=exp(p_i(e^\lambda-1)) for p_i=0 or 1 as well. Singularity is handled at this step and no inverse covariance survives in the conclusion.

7. [x] **Apply the Gaussian count inequality under the final conditioning.** For a realization of H on the common set where its conditional null law is Gaussian, its finite mean and covariance Q have the stated signs. Apply Step 6 to the fixed original null labels and thresholds b_i=barPhi^{-1}(s), with the p-value definition and non-strict comparisons exactly as in the target. The Gaussian conditional law already includes the entire alternative vector; do not add further conditioning or assert sign preservation. Obtain
   $$
   E[e^{\lambda C(s)}\mid H]
   \le\exp\left\{\sum_{i\in I_0}F_{i,H}(s)(e^\lambda-1)\right\}.
   $$
   Use the given conditional Gaussian kernel, including measurable mean and covariance parameters, to choose these integral versions simultaneously; for countably many parameters one common set suffices, and right continuity/continuity extends them as in Steps 1 and 8. The deterministic fixed-law result holds for every finite Gaussian parameter pair, so exceptional sets are not selected separately by uncountably many parameters.

8. [x] **Prove envelope measurability and finish exact statement coverage.** Conditional coordinate CDFs from the Gaussian kernel are right-continuous, even with atoms from zero variances. For each 0<s<q, choose rationals r_n in (s,q) decreasing to s to prove
   $$
   \frac{\sum_iF_{i,H}(r_n)}{N r_n}
   \longrightarrow\frac{\sum_iF_{i,H}(s)}{Ns}.
   $$
   Hence the supremum equals the rational supremum plus the endpoint q and K is H-measurable with values in [1,infinity]. Whenever K is finite its definition and Step 7 imply precisely the general conditional count hypothesis; null scores are finite so their p-values are nonzero, consistent with Step 2. Apply Steps 1--4 and state explicitly the infinite-K convention. Audit arbitrary N, original null labels, arbitrary alternative vector, atoms, ties, R=0, K near the cap, degenerate/singular Q, all deterministic coordinates and both claimed conditional/unconditional inequalities. Leave the two unrestricted completion targets unchanged.

## Verification

Steps 1--4 prove the general statement using only its conditional count-mgf assumption and the two approved definitions. The crucial separation is that k_i is H-measurable whereas V is still random; all probability estimates concern the deterministic finite grid after conditioning. The formula R=k_V is proved from the actual largest-rank BH rule and therefore covers the same original rejection set, labels and denominator.

Steps 5--6 prove an independent finite-dimensional Gaussian inequality inline, with the density derivative, sign, cutoff and singular-limit arguments exposed for review. Steps 7--8 convert the exact final-conditional Gaussian hypothesis and its common CDF envelope into the general assumption. No private-noise floor, product-coordinate hypothesis, association theorem, new source theorem or geometry-dependent constant is needed.

The proof should explicitly check that its output is min{1,4e qK}, rather than a bound with the constant 4, a selected-rank estimate at a random unconditioned threshold, or the unrelated product-law constant 2. Any failure of an auxiliary step is recorded before an unrestricted conclusion is claimed.

## Assumed definitions

Only [ordinary Benjamini-Hochberg step-up](../definitions/benjamini_hochberg_step_up.md) and [false discovery rate](../definitions/false_discovery_rate.md), both approved and attached to the target, are assumed. There are no draft definitions, unproved asset dependencies, adapted results or extra library black boxes. The source ideas are fully rederived in the checklist. Gaussian density calculus, conditional finite-sum identities and limiting arguments are proved or justified inline as specified.

## Outcome

All eight checklist items are established. The complete proof is under \`## Proof\` in [Actual-rank conditional calibration from sub-Poisson null counts](../assets/gaussian_bh_conditional_subpoisson_calibration.md). It proves the exact frozen conditional min{1,4e qK} bound using the actual R=k_V identity and a conditional Chernoff allocation, followed by a self-contained Gaussian density interpolation proof, singular endpoint couplings, deterministic-coordinate restoration and measurable final-conditional envelope.

The asset remains status draft. Its entire pre-execution byte prefix, including frontmatter and Statement, is preserved exactly; original prefix SHA256: 5ff2683fffd8e979de36dbab4a2bdd5820b835f35a1d7be5bd3e43d4a8ea0ee1. Complete asset SHA256 after proof insertion and the no-op scoped links application: 25320327129237e827500120f99fa835305274cbde005e965d08b78528232404. The general count-mgf and final-conditional Gaussian/sign hypotheses remain exactly those in the Statement; no draft definitions or unproved dependencies are assumed. No unrestricted main bound or approval is claimed.

Scoped notation review read the two attached approved definitions and the configured macros.tex and notations.tex, both comment-only. Every proof symbol is defined locally or in the Statement; the BH rank, original labels and FDP agree with the approved definitions. No notation inconsistency or missing prerequisite relation was found. Scoped links preview and apply each reported zero changes and zero review items. Maintenance validation reported only the pre-existing malformed idea_c23fac250465 and its older-schema advisory; neither was modified.

The temporary Progress checkpoints have been transferred into the complete asset proof. The parent owns native reporting and fresh independent verification.


## Verdict
confirmed

Independently checked the frozen statement and proof without using this plan's reasoning or the source ideas. The largest-rank identity R=k_V follows from maximality in the unchanged original BH procedure; null zero p-values are excluded on {K<infinity}, while alternative zeros, ties, V=0 and R=0 are handled correctly. A separate finite boundary enumeration checked the identity in 7,736 configurations (N=1 through 5).

The finite-grid conditional exponential polynomials justify the H-measurable k_i and Chernoff parameters on one common full-measure set. The split at i/k_i>a qK gives a+e/(1-e/a), hence 4e at a=2e, including i=1 and random finite K; the K=infinity branch is the trivial FDP cap.

Reconstructed the Gaussian density derivative, both integrations by parts and their sign, endpoint couplings for singular covariance, removal and exact restoration of zero-variance coordinates, and smoothing at non-strict thresholds. The conditional kernel makes the inequalities simultaneous; right continuity proves the rational-supremum envelope is measurable even with atoms. No substantive gap was found. This confirms the stated conditional calibration lemma and its stated Gaussian sufficient condition only.
