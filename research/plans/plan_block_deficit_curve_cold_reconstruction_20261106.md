---
type: plan
title: Cold reconstruction of the block deficit-curve reduction
status: succeeded
target_asset: gaussian_bh_block_deficit_curve_reduction
inspired_by: []
adapts: []
proof_digest: 44ba6a8b4883e551ef1752800759d1985e605be78d234eb1869204f9d38e1cab
statement_digest: f1dda2f50a23bcb44d5591faa42a4ed7c15018980386fbefca5819ed441dbef8
dependency_digests:
  gaussian_multiple_testing_model: 535694725c29c2ede682edeaeef6e40dce424d3a88330832f592e18853f99db7
  gaussian_test_pvalues: 77bd992c815e7093fd72c2543d655df56c15eef2bf6240d46d729bce9f86ca50
  benjamini_hochberg_step_up: 2654feec463fe339f6bebe029e9f1cbff9e970db6ad51faa3b66f632a90eb875
  gaussian_multifactor_representation: e3a61244f476941be96780294a5d26af63dd415aa7462c2662601bf6aeb086fe
verified_proof_digest: 44ba6a8b4883e551ef1752800759d1985e605be78d234eb1869204f9d38e1cab
---

# Cold reconstruction of the block deficit-curve reduction

## Goal

Target: [Block deficit-curve reduction for Gaussian BH](../assets/gaussian_bh_block_deficit_curve_reduction.md).

Prove exactly clauses (i)–(iii), for each finite N >= 1, q in (0,1), every finite independent one-factor block partition, arbitrary deterministic means and loadings in [-1,1], including zero and unit loadings and singular Gaussian laws. The extracted candidate proof is unchecked source material, not a black box; execution must reconstruct all arguments below independently. Keep the original N in every threshold when mates are removed from the count. All comparisons are closed and all ranks are maximal qualifying ranks; retain ties pointwise.

## Plan

1. [x] Reconstruct the deterministic BH count characterization from the approved step-up definition. For any fixed p-vector and k, establish p_(k) <= t_k iff its closed threshold count is at least k. Show that the number rejected at the maximal qualifying rank equals that rank (including ties), and separately treat the zero-rank case. With coordinate i replaced by zero, prove that the count is exactly 1 + beta(k) + M_z(k); its maximal qualifying rank is R_i >= 1. Removing the mates from this count gives R_i^flat = max{k: 1 + beta(k) >= k} >= 1, with denominator N unchanged. Rearrange these two inequalities into clause (i). If the source's rejection-equivalence argument is retained, reconstruct it from the monotonicity of t_k rather than cite its BH0 label; no further assertion from that argument is needed for the stated target.

2. [x] For the arbitrary integer nondecreasing background count beta, prove D(k+1)-D(k) <= 1, D(k) <= k-1, and the suffix-minimum recursion D*(N)=D(N), D*(k)=min(D(k),D*(k+1)). Derive integer values, monotonicity, D* <= D, and the increment bound D*(k+1)-D*(k) in {0,1}. Explicitly split equal suffix minima from a strict increase; in the strict case identify D*(k)=D(k), then use D*(k+1) <= D(k+1) <= D(k)+1. Do not assume monotonicity of D itself or a bound on jumps of beta other than its monotonicity.

3. [x] Set k_f=max{k:D(k)<=0}; establish nonemptiness from D(1)=-beta(1). Prove both directions of D*(k)<=0 iff k<=k_f using a suffix witness and maximality of k_f; use integrality for D*(k)>=1 beyond k_f. Identify k_f=R_i^flat and verify membership of D* in the precise class D_N in Local notation. Check N=1, an empty background, a singleton selected block, and k_f=N without introducing undefined k_f+1 expressions.

4. [x] Prove equality of the two maximal ranks in clause (ii) pointwise. One inclusion follows from D*<=D. For the reverse, take any k with M_z(k)>=D*(k), choose a finite suffix minimizer j>=k with D(j)=D*(k), and use M_z(j)>=M_z(k) to show j qualifies for the original D criterion. Therefore the maximum for D is at least every qualifying k for D*. Show the sets are nonempty so these maxima are well defined. As a check needed by subsequent use of this reduction, prove the plateau right-endpoint property: if R_i<N and D*(R_i+1)=D*(R_i), monotonicity of M_z would make R_i+1 qualify, a contradiction. If a baseline endpoint is used, derive the corresponding plateau endpoint statement for k_f from its defining sign interval. No strict-threshold or almost-sure shortcut may replace these arguments.

5. [x] Establish full exogeneity from the factor representation, not from pairwise uncorrelatedness. Show beta is measurable with respect to the primitive variables (Z_h, eps_l) for h!=g and l outside B_g. These primitives are independent of (Z_g,(eps_j)_{j in B_g}); hence beta and its deterministic transform D* are independent of that full selected-block tuple. Explain why conditioning on beta leaves the selected-block Gaussian factor and residual law unchanged. This must include arbitrary means, opposite loading signs, zero and unit loadings, conditionally deterministic coordinates, singular covariance laws, any finite number of blocks, and the deterministic empty-background case. Treat these as consequences of primitive independence and measurable maps; do not impose nonsingularity or positive residual variances.

6. [x] Supply the measurability and absolute-integrability justification for the signed conditioning/Fubini step. For fixed beta and z, define R(z) as the finite maximal rank from step 4, retaining the random mate residuals in the inner expectation. Threshold indicators, finite minima, and finite maxima make this Borel measurable even at ties and unit loadings. For every possible rank k>=1, show directly from the numerator being a conditional probability that 0<=rho_r(u_k,z)<=1/p(u_k)=1/t_k<=N/q; handle r=1 by its displayed indicator definition, and r=0 directly if needed. Thus the absolute signed central integrand is bounded, for example by 2N/q, against probability measures. Apply Fubini/conditioning to obtain exactly Delta_i^c = E_beta[Delta^c(D*(beta))], with k_f(beta)=R_i^flat(beta), inner expectation only over mate residuals, and integration in z over [-U,U]. A common deterministic upper bound on every admissible curve transfers by expectation; make no pointwise conditional bound or uniform-in-N integrability claim beyond what this finite-N argument proves.

7. [x] Assemble (i), every listed property in (ii), and precisely the consequence in (iii). Record that D* nondecreasing in k is nonincreasing as a function on the discrete decreasing levels u_k. The only background information used by both ranks is D*, including its baseline endpoint k_f. Retain the exact finite-N, arbitrary-block and closed-threshold scope; do not import a tail-ratio estimate, a small-q restriction, a central-deficit bound, or assumptions from the unresolved main conjecture. If reconstruction exposes a gap in the stated target, report the obstruction rather than modify its statement.

## Verification

Independently check the two directions of each maximum identity and of the sign-interval equivalence. Trace the strict suffix-minimum case, the suffix witness used to transfer rank qualification, and the endpoint R_i=N separately. Audit dependence on each primitive variable before conditioning. Verify the signed expectation identity using the explicit finite N/q bound, including the degenerate loading cases. The plateau property is a deterministic check of the reduction, not an extra hypothesis. The extracted proof and the cold-audit observation do not supply a native verification verdict.

Library searches for `BH deficit curve suffix minimum`, `suffix minimum`, and `Fubini integrability finite rank` returned no matches. The finite combinatorial and bounded-integrand arguments above will be reconstructed directly; no undeclared library theorem is assumed.

## Assumed definitions

Use exactly the four declared approved definitions: gaussian_multiple_testing_model, gaussian_test_pvalues, benjamini_hochberg_step_up, and gaussian_multifactor_representation, with their declared dependencies. Use the target's Local notation for the independent one-factor block class, p, t_k, u_k, rho_r, R_i, R_i^flat and the central quantity, and the extracted source only to identify the intended forced-zero and mate-removal meanings when reconstructing step 1. No draft definition, unproved asset dependency, failed source plan conclusion, library result, or provisional cold-audit verdict is assumed.

## Outcome

The complete independently reconstructed proof is in `research/assets/gaussian_bh_block_deficit_curve_reduction.md`, under `## Proof`; its frozen Statement and draft status are unchanged. The historical extracted source candidate is preserved under an explicit historical heading, without treating it as native verification. All seven checklist items were established in writing before their progress record was consolidated into the final proof.

The proof covers exactly (i)–(iii), finite N>=1, q in (0,1), arbitrary finite independent one-factor blocks and deterministic means/loadings, including zero/unit loadings and singular Gaussian laws. It preserves thresholds qk/N, closed comparisons and ties; establishes equality of maximal ranks without equating all qualifying ranks; records plateau endpoints; and justifies signed Fubini by the finite absolute bound 2N/q. It assumes only the four declared approved definitions and the target's local setup. No draft definition or unproved dependency is assumed. This is an executed proof candidate for independent native verification, not an approval or verification verdict.


## Verdict
confirmed
The canonical Statement and every Proof step are valid for all finite N >= 1 and q in (0,1): closed-threshold BH counts, suffix minima with increments 0 or 1, equality of maximal ranks, and baseline and plateau endpoints include ties, N = 1, empty backgrounds and singleton blocks.
The disjoint primitive sigma-fields establish independence of the background from the entire selected-block tuple, including arbitrary means, either loading orientation, zero or unit loadings and singular laws.
The Borel rank maps and absolute bound 2N/q justify signed conditioning and Fubini for each fixed model; the deterministic-curve bound transfers by averaging without requiring this integrability bound to be uniform in N. No repair or additional hypothesis is needed.
