---
type: falsification_check
title: 'Falsification check: gaussian_bh_negative_null_boundary_strip'
target_asset: gaussian_bh_negative_null_boundary_strip
outcome: no_counterexample_found
statement_digest: 8cb3729d0db20bedb0d623cce2676cfa7d01e08b10180884af70e5a810e0b568
performed_by: unknown
created_at: '2026-11-11T19:48:31.186Z'
extension_version: 0.0.4
---

## Cases checked

- Round 1, small_cases: cand_gaussian_bh_negative_null_boundary_strip_r1_s2_single_negative_null failed — NOT fails: this actual one-coordinate BH contribution is strictly less than the claimed general strip bound.
- Round 1, drop_hypothesis: cand_gaussian_bh_negative_null_boundary_strip_r1_s3_antipodal_endpoint failed — NOT fails: the exact original BH contribution is 2 barPhi(2+barPhi^{-1}(barPhi(1)/2)), strictly below (5/4)barPhi(1)e^{-4}.
- Round 2, boundary_degenerate: cand_gaussian_bh_negative_null_boundary_strip_r2_s3_mixed_tied_cutoffs failed — NOT fails: the exact far-null contribution is barPhi(e+2/e)/2, which obeys both asserted bounds, and the exact same-procedure FDR decomposition also holds.
- Round 4, small_cases: cand_gaussian_bh_negative_null_boundary_strip_r4_s2_independent_mixed_means failed — NOT fails: the exact original two-coordinate BH contribution is strictly below the claimed bound even though both rejection ranks occur with positive probability.
- Round 1, boundary_degenerate: no plausible candidate.
- Round 2, known_counterexamples: no plausible candidate.
- Round 2, extremal: no plausible candidate.
- Round 3, boundary_degenerate: no plausible candidate.
- Round 3, small_cases: no plausible candidate.
- Round 3, drop_hypothesis: no plausible candidate.
- Round 4, boundary_degenerate: no plausible candidate.
- Round 4, drop_hypothesis: no plausible candidate.
- Round 5, boundary_degenerate: no plausible candidate.
- Round 5, small_cases: no plausible candidate.
- Round 5, drop_hypothesis: no plausible candidate.
- Obstruction: Empty strip sets cannot violate the contribution estimate: both the actual contribution and its stated bound are zero. This is a degeneracy check, not a refutation.
- Obstruction: The tested scalar shifted-null family at N=1, q=barPhi(1), a=1, theta=-1 satisfies every hypothesis but fails NOT. Its actual contribution is barPhi(2)<exp(-3/2)barPhi(1), whereas the stated bound is 3exp(-3/2)barPhi(1). A one-coordinate endpoint example therefore does not exploit rank multiplicity or dependence to defeat the estimate.
- Obstruction: The tested singular antipodal pair, N=2, theta=(-2,-2), Sigma=[[1,-1],[-1,1]], q=barPhi(1), a=2, also satisfies every hypothesis but fails NOT. Rank 2 is impossible, and the actual contribution is 2barPhi(2+barPhi^{-1}(barPhi(1)/2))<(5/4)barPhi(1)exp(-4). Singular covariance and equality at the negative-mean cutoff alone therefore do not produce a violation in this tested family.
- Obstruction: The known-counterexample worker found no candidate: the original BH rejection inequality gives the pathwise inverse-p-value envelope 1{i rejected}/(R vee 1)<=q 1{p_i<=q}/(Np_i). The reported Gaussian marginal integral controls this envelope for arbitrary joint laws with the required marginals, obstructing dependence-based attacks without changing the actual procedure.
- Obstruction: The extremal worker found no candidate in a(q) or threshold limits. Its reported Gaussian-integral calculation retains a>0 explicitly; at a_q=2log(U)/U and U>=e, the coefficient is bounded by (1+1/U)/(2log(U))+1/(4log(U)^2)<=3/4+1/(2e).
- Obstruction: The mixed-mean singular common-noise candidate at q=barPhi(e) passes H1-H6 and fails only NOT. Its exact far-null contribution barPhi(e+2/e)/2 obeys both contribution bounds, and its same-procedure FDR decomposition also holds. Mixed deep and boundary means, tied cutoffs, and endpoint inclusion therefore do not yield a violation in this tested family.
- Obstruction: Ties and non-strict comparisons do not separate the largest qualifying BH rank from the actual rejection count: if a later tied coordinate also lay below the selected cutoff, its own larger rank would qualify. Thus the reported identity R=khat and the full-procedure inverse-p-value envelope survive multiplicities. Singular covariance does not create atoms at fixed thresholds, because each unit-variance Gaussian marginal remains continuous; this does not exclude cross-coordinate ties.
- Obstruction: The small-case worker found no new candidate beyond the recorded board. The full actual rejection count still gives 1{i rejected}/(R vee 1)<=q 1{p_i<=q}/(Np_i), so the previously reported marginal-envelope obstruction persists without deleting rank-affecting coordinates.
- Obstruction: Setting a=0, changing unit marginal variances, or removing the stated Gaussian law leaves the hypothesis class. Such changes cannot refute this target; no admissible candidate from that direction was recorded.
- Obstruction: The original full-procedure BH inequality bounds each rejected coordinate's contribution by its inverse-p-value envelope, with the actual rejection count and every rank-affecting coordinate retained. The board's reported Gaussian marginal integral therefore obstructs dependence-based attacks that preserve the stated marginals; the reported tie/rank argument also preserves this envelope under multiplicities and singular covariance.
- Obstruction: Allowing both rejection ranks to occur does not itself defeat the bound: the round's independent two-coordinate mixed-mean candidate satisfies H1–H6 but fails NOT because its exact original BH contribution is strictly below the claimed bound. Together with the earlier mixed tied-cutoff example, this rules out the proposed mechanisms in these checked examples, without excluding every mixed-mean model.
- Obstruction: The reported shrinking-strip endpoint and positive mean-gap limit checks retain slack in the stated coefficient. Setting the gap to zero or changing the unit-variance Gaussian marginals instead leaves the hypothesis class and supplies no counterexample.
- Obstruction: Deterministic dependence of the gap, finite dimension, means, or singular unit-diagonal covariance on q does not evade the reported full-procedure inverse-p-value envelope: for each fixed q the same original BH rejection inequality and Gaussian marginal calculation apply. Merely varying these parameters with q therefore supplies no distinct failure mechanism beyond the already recorded families.
- Obstruction: Dependence, singular covariance, multiplicities, and mixed mean labels retain the original rejection count in that envelope. The existing marginal-envelope obstruction consequently continues to cover these proposed attacks when every stated hypothesis is preserved and the reported integral estimate is valid.
- Obstruction: Choosing the strip or model parameters after observing the Gaussian sample changes the deterministic statement being tested; such data-dependent selections cannot refute the frozen target.

## Limitations

All three workers recorded no new candidate, and the current pack lists no round 5 candidates. No new plausible family beyond the board's existing obstruction was identified. This search summary does not independently verify the marginal integral, its uniform constants, or the complete lemma; those remain proof and verification obligations, and the target remains draft. Absence of a candidate is not exhaustive search or approval. The round establishes no bound on the remaining near-boundary contribution and neither universal-order target. Every reported check retains the unmodified full BH procedure.

Object search: 4 candidate(s) in 5 round(s).
