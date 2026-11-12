---
id: plan_e6ef3e4c8fd8
type: plan
title: Prove correlated-clone variation by conditional normal threshold transport
status: succeeded
target_asset: gaussian_bh_correlated_clone_first_variation
inspired_by:
  - idea_4b3c11e8663b
  - idea_f55224f01b3b
  - idea_6d6ab09e7d4e
  - idea_0b76f3484fd5
adapts: []
proof_digest: 37614b8a41c235b57e530a76d9d6387c8d62fd7886a29f1a841ce64dc2f5fafc
statement_digest: 680547805d2575723444c5de508a946ed17ed1f6ae88a68bfd490ee4a27dda26
dependency_digests:
  gaussian_multiple_testing_model: 535694725c29c2ede682edeaeef6e40dce424d3a88330832f592e18853f99db7
  gaussian_test_pvalues: 77bd992c815e7093fd72c2543d655df56c15eef2bf6240d46d729bce9f86ca50
  benjamini_hochberg_step_up: 2654feec463fe339f6bebe029e9f1cbff9e970db6ad51faa3b66f632a90eb875
  false_discovery_rate: ce88ab68fe7c28f8baff59d3beb8b2c38cbb031634b8dc2f3cb3cad67a3309d1
verified_proof_digest: 37614b8a41c235b57e530a76d9d6387c8d62fd7886a29f1a841ce64dc2f5fafc
---

## Goal

Target: [Correlated-clone right variation of finite positive-definite Gaussian BH](../assets/gaussian_bh_correlated_clone_first_variation.md).

Prove all four assertions of this exact fixed-model statement, including deterministic ties, the exponentially small all-or-none error, and the signed derivative with the stated Gaussian face density. Keep the original null labels and actual largest BH ranks throughout. Five initial falsification rounds found no counterexample; this supplies no proof step.

## Plan

1. [x] Establish deterministic BH facts and label preservation. For any finite p-value vector, prove that the number of p-values at most the largest qualifying threshold equals that largest rank: any extra such p-value would qualify at its own larger rank. For exact K-fold copies, the expanded order statistic at rank l equals the original one at rank ceil(l/K). A qualifying l therefore makes ceil(l/K) qualify in the original problem, while an original qualifying r makes Kr qualify in the expanded problem. Deduce the exact largest-rank identity and rejection-set identity, including ties and rank zero, and hence assertion 1. Check separately that theta_i=0 with every c_b<=0 keeps all i-clones null, and that for theta_i nonzero sufficiently small epsilon preserves its sign. Orthogonality w_b dot v_i=0 gives variance one after normalization. Thus every FDP below has exactly the preserved labels I_0 times [K].

2. [x] Prove the finite signed-measure assertion from the finite grid, without a positivity replacement. At fixed other scores, BH depends on coordinate i only through its comparisons with the finitely many u_r. Its FDP is a right-continuous step function with these possible jump locations, and each signed jump has absolute value at most one. Express the jumps by finite Borel comparisons, proving Borel measurability of Delta_{i,r}. The measure mu_{i,r} has density phi(a_r) Delta_{i,r} relative to gamma_{E_i}, so its total variation has density phi(a_r)|Delta_{i,r}|. Integrate 1+||y|| to obtain exactly the inequality in assertion 2. Use |g(y)|<=max_b|c_b|+(max_b||w_b||)||y|| to establish the required absolute integrability. Include the point mass convention if E_i has dimension zero.

3. [x] Prove a deterministic fixed-grid gap criterion for partial rejection when K>1. Put M=NK and b_l=barPhi^{-1}(q l/M). Every unchanged group is whole at every rejection threshold. If the perturbed group is partial, with m in {1,...,K-1} rejected clones and h rejected unchanged groups, the actual largest expanded rank is l=Kh+m. Put L=K(h+1)<=M. At least one i-clone is at least b_l. If its score spread were smaller than b_l-b_L, every i-clone would be strictly above b_L; together with the h unchanged groups this would make L qualify, contradicting maximality of l. Thus partial rejection forces spread at least
   $$
   \delta=\min_{1\le l\le M,\ K\nmid l}
       (b_l-b_{K\lceil l/K\rceil})>0.
   $$
   This argument uses the actual maximal rank and remains valid at threshold equalities. If all groups are whole and the expanded rank is Kh, show that h qualifies for BH on H^epsilon (unless h=0), and that every qualifying reduced rank r makes Kr qualify in the expanded problem. Deduce exact equality of rejection sets on this event, including rank zero. For K=1 this equality is pointwise without a gap argument.

4. [x] Bound the partial-group event by a fixed-model Gaussian tail, including normalization. With D_b(epsilon)=sqrt(1+epsilon^2||w_b||^2), use |D_b^{-1}-1|<=C epsilon^2 to prove, for all sufficiently small epsilon,
   $$
   |T_{ib}^\epsilon-T_i|
   \le \epsilon(|c_b|+|w_b\cdot Y|)
       +C\epsilon^2|Z|.
   $$
   Hence the clone spread is at most C epsilon(1+||G||), with a finite constant depending on the fixed marks and representation. Combine the positive delta from step 3 with an elementary finite-dimensional standard Gaussian norm tail (derive it, for example by a fixed Gaussian exponential moment) to get A exp(-a/epsilon^2). If the perturbation gives zero spread identically, the event is empty. The rejection-set discrepancy is contained in the partial-group event. Since both FDPs lie in [0,1] and labels agree, this proves all estimates in assertion 3. No constant is asserted uniform in d,N,K,q,Sigma,means,or marks.

5. [x] Construct a residual normal coordinate that freezes every unchanged statistic. Positive definiteness makes the rows v_j linearly independent. Let ell be the unit residual of v_i orthogonal to span{v_j:j!=i}, oriented so sigma=v_i dot ell>0. Write G=ell S+B with S standard normal and B standard Gaussian on L=ell-perp, independently. Every unchanged T_j=theta_j+v_j dot B is now independent of S. At fixed B define f_B(x) by substituting these unchanged scores and x for coordinate i. Prove its finite step expansion, with its actual signed largest-rank jumps D_r(B),
   $$
   f_B(x)=f_B(-\infty)+\sum_{r=1}^N D_r(B)\,1_{\{x\ge u_r\}}.
   $$
   The notation f_B(-infty) means the constant value below the smallest grid point. The identity holds with the non-strict convention; in any case its threshold values have conditional probability zero. Keep |D_r(B)|<=1. Do not freeze a BH rank, optimize ranks separately, discard negative jumps, or regard a finite mean as a deterministic rejection.

6. [x] Compute exact normalized clone crossing roots and their first variation. Set alpha_b=w_b dot ell and s_r(B)=(a_r-v_i dot B)/sigma. After decreasing epsilon_0 if needed, every clone slope in S is positive, since sigma+epsilon alpha_b>=sigma/2. Its exact crossing root at u_r is
   $$
   s_{b,r}^\epsilon(B)=
   \frac{D_b(\epsilon)(a_r-\epsilon c_b)-v_i\cdot B-\epsilon w_b\cdot B}
        {\sigma+\epsilon\alpha_b}.
   $$
   The minimum clone score is at least u_r exactly when S>=s_r^epsilon(B):=max_b s_{b,r}^epsilon(B). On the unperturbed face let
   $$
   G_r(B)=B+\ell s_r(B),\qquad
   y_r(B)=G_r(B)-v_i a_r\in E_i.
   $$
   Expand the finite family of explicit roots, checking a bound uniform in b and r,
   $$
   s_{b,r}^\epsilon(B)
   =s_r(B)-\frac{\epsilon}{\sigma}
       (c_b+w_b\cdot y_r(B))
       +O(\epsilon^2(1+\|B\|)).
   $$
   Taking a finite maximum gives the right derivative -g(y_r(B))/sigma and the global domination |s_r^epsilon(B)-s_r(B)|/epsilon<=C(1+||B||). This calculates the normalization terms rather than dropping epsilon^2 Z. To verify explicitly the optional replacement by theta_i+Z+epsilon g(Y), compute its analogous roots by setting D_b=1 in the numerator; their maximum differs from s_r^epsilon by at most C epsilon^2(1+||B||). The step expansion and the bounded normal density then give an O(epsilon^2) difference of the two FDP expectations. Thus this replacement, if used, costs o(epsilon).

7. [x] Integrate the exact conditional threshold transport before taking a derivative. Independence and the step expansion give
   $$
   \mathbb E[f(H^\epsilon)-f(T)\mid B]
    =\sum_{r=1}^N D_r(B)
       [\Phi(s_r(B))-\Phi(s_r^\epsilon(B))].
   $$
   The mean-value bound and step 6 dominate the difference quotient by C(1+||B||), integrable under gamma_L. Apply dominated convergence to obtain
   $$
   \lim_{\epsilon\downarrow0}
   \frac{\mathbb E f(H^\epsilon)-F}{\epsilon}
    =\sum_{r=1}^N\int_L
       D_r(B)\phi(s_r(B))\frac{g(y_r(B))}{\sigma}
       \,\gamma_L(dB).
   $$
   Explain explicitly why there is no unproved face-intersection removal here: all unchanged scores and all D_r(B) are held fixed under the conditional integration. Their possible discontinuities as functions of B are never differentiated or moved. The exact identity holds for every fixed background up to irrelevant threshold atoms, and its Gaussian-integrable bound controls all backgrounds at once. No assertion that a probability-zero intersection has negligible first variation is needed.

8. [x] Prove the exact Gaussian face change of variables and match the stated jumps. For each r the affine bijection from E_i to L is
   $$
   B=P_L(v_i a_r+y),
   \qquad G_r(B)=v_i a_r+y.
   $$
   Verify its inverse directly and prove that the absolute (d-1)-dimensional Jacobian of P_L restricted to E_i is sigma (identity on the common (d-2)-dimensional subspace, factor sigma on its orthogonal complement). Also verify ||B||^2+s_r(B)^2=||y||^2+a_r^2. Consequently, as Gaussian measures on the face,
   $$
   \frac{\phi(s_r(B))}{\sigma}\gamma_L(dB)
       =\phi(a_r)\gamma_{E_i}(dy).
   $$
   On this face every unchanged score equals theta_j+rho_{ji}a_r+v_j^perp dot y, so D_r(B)=Delta_{i,r}(y) with exactly the original labels and both actual ranks, including cascades. Substitute this into step 7 to obtain precisely the two displayed signed integrals in assertion 4. For d=1, positive definiteness forces N=1, ell=v_i, sigma=1, and both background spaces have dimension zero; verify the same equations using point masses and the zero-dimensional Jacobian 1 rather than the (d-2)-space argument.

9. [x] Assemble the four assertions without strengthening scope. Assertion 1 identifies F_K(0)=F. Assertion 3 gives |F_K(epsilon)-E f(H^epsilon)|/epsilon<=A epsilon^{-1}exp(-a/epsilon^2)->0, so the finite derivative from steps 7-8 is exactly F_K'(0+). Assertion 2 makes every claimed signed integral legitimate. State the local sign restrictions, K=1 case, zero-dimensional case, and fixed-model dependence of all constants in the final proof. Do not conclude any singular-original-covariance extension, uniform error estimate, universal FDR bound, or extremizer result.

## Verification

Step 1 proves assertion 1 pointwise even at deterministic ties. Step 2 proves assertion 2 with its exact first-moment estimate. Steps 3-4 prove assertion 3 as a rejection-set statement and then as an FDP/FDR estimate. Steps 5-8 prove the derivative for the reduced minimum-score model by an exact conditional identity, an integrable normal-root envelope, and the explicitly checked face Jacobian; step 9 transfers it to the expanded BH model. Every jump is a signed difference computed using the actual largest qualifying original BH ranks. Execution must verify each elementary calculation, especially the strict positive gap, normalized root expansion, conditional step representation, and Jacobian, before marking this plan succeeded.

## Assumed definitions

Only the target's approved definitions are used: [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md), [Gaussian test p-values and true nulls](../definitions/gaussian_test_pvalues.md), [ordinary BH](../definitions/benjamini_hochberg_step_up.md), and [false discovery rate](../definitions/false_discovery_rate.md). There are no unproved asset dependencies or draft definitions assumed as black boxes. The listed draft ideas motivate steps to be proved here; they are not prerequisite results.

## Library search

The stage pack lists no library analogues or dependency results. Native library searches for clone, Gaussian variation, threshold transport, Gaussian, differentiation, Stein, Jacobian, Benjamini, and normal returned no matches. This plan therefore adapts no library proof and invokes no unlisted Stein or surface-variation theorem. Its finite-grid, Gaussian-tail, root-transport, and Jacobian arguments are proved within the target.

## Freshness

Immediately before creation the target statement was reread through the native show command; its SHA-256 was 8d0ce2e933075581081670842c9fad603e81fd3cd044ba97442ef8fa59ca592d and the stage pack SHA-256 was 83db4d5428b11fb5c6365779d58f50314bbb2329eae646b10994f9e229d6424e. The unique new plan path was checked absent. The workspace root is not a Git repository, so no root HEAD exists. This new pending plan changes no target, definition, idea, previous plan, dependency, setting, approval, or loop state.

## Outcome

All nine checklist items are established in order in the complete `## Proof` of [Correlated-clone right variation of finite positive-definite Gaussian BH](../assets/gaussian_bh_correlated_clone_first_variation.md). The proof establishes all four assertions of the frozen statement, including deterministic ties, the fixed-grid exponential all-or-none estimate, the exact normalized-root transport with a Gaussian-integrable envelope, the signed face formula, and the explicit projection Jacobian. It covers $K=1$, $d=1$, zero-dimensional backgrounds, and the local mean-sign restrictions. It also proves an $O(\varepsilon^2)$ expectation error for replacing the normalized minimum by its first-order score.

Only the four approved definitions listed above and elementary finite-dimensional linear algebra, Gaussian integration, and dominated convergence are used. No draft definition or unproved asset is assumed. The original positive definiteness and every fixed-model scope restriction remain in force; no uniform FDR bound or extremizer conclusion follows here. The asset remains draft for native independent verification.

The original asset content before `## Proof` is preserved byte-for-byte (SHA-256 `8d0ce2e933075581081670842c9fad603e81fd3cd044ba97442ef8fa59ca592d`). The original plan text is preserved apart from its status and the nine completed checkboxes; this outcome is appended. No approval, proof digest, loop state, or settings were written.

## Verdict

confirmed

1. Step 1 correctly proves that the largest qualifying rank equals the rejection count even with deterministic ties, and the ceiling-rank comparison proves exact-copy invariance, including rank zero. Orthogonality gives the claimed marginal normalization; the local sign restrictions, including all c_b <= 0 when theta_i = 0, preserve precisely the original null labels.
2. Step 2 uses the finite original score grid and non-strict BH comparisons to obtain Borel, right-continuous coordinate steps with signed jumps bounded by one. Their displayed density gives the total-variation bound, Gaussian first moments, and absolute integrability of every stated mark integral.
3. Step 3 correctly shows that a partial i-group at rank Kh+m would complete K(h+1) scores at the next group endpoint unless its spread exceeds the specified positive fixed-grid gap. When no group is partial, both qualifying-rank implications and final threshold membership prove equality of the full rejection sets, also at rank zero and threshold ties.
4. Step 4 bounds the normalized clone spread by C epsilon (1+||G||); the Gaussian exponential moment gives the asserted exp(-a/epsilon^2) exceptional probability. The [0,1] FDP bound transfers this to expectations, and K=1 is an exact identity.
5. Step 5 validly uses positive definiteness to obtain a strictly positive residual sigma and an independent normal coordinate along which every unchanged score is fixed. The finite signed-step expansion therefore retains all original largest-rank cascades.
6. Step 6's exact crossing roots and subtraction identity are algebraically correct. Their denominators stay positive for all marks at sufficiently small positive epsilon, the maximum root selects the minimum first-order mark with the stated sign, and the global remainder is O(epsilon^2(1+||B||)). Replacing normalized roots by unnormalized roots costs O(epsilon^2), uniformly in B.
7. Step 7 integrates those exact roots conditionally against the independent standard normal. The difference quotients are dominated by C(1+||B||), so dominated convergence is valid without shifting or differentiating the discontinuous background jumps; intersections of threshold faces introduce no omitted contribution.
8. Step 8's affine face map is bijective, its Euclidean Jacobian is sigma, and the orthogonal norm identity gives precisely phi(s_r(B)) gamma_L(dB)/sigma = phi(a_r) gamma_E_i(dy). The background scores and signed jumps match the statement exactly. The sigma=1 and d=1 cases are valid separately, with point-mass background measures in dimension zero.
9. Step 9 correctly removes the exponentially small reduction error after division by epsilon and yields the exact finite right derivative in assertion 4. All constants and epsilon restrictions are permitted to depend on the fixed finite data; no uniform bound or singular-original-covariance extension is used. No substantive or minor gap required closure.
