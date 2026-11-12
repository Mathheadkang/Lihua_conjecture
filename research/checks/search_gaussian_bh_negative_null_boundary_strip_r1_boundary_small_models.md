---
type: search_round
title: Boundary and smallest-model obstructions for the negative-null strip
target_asset: gaussian_bh_negative_null_boundary_strip
mode: refute
round: 1
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - cand_gaussian_bh_negative_null_boundary_strip_r1_s2_single_negative_null
  - cand_gaussian_bh_negative_null_boundary_strip_r1_s3_antipodal_endpoint
statement_digest: 8cb3729d0db20bedb0d623cce2676cfa7d01e08b10180884af70e5a810e0b568
performed_by: unknown
created_at: '2026-11-11T19:35:06.188Z'
extension_version: 0.0.4
---

## Obstructions

- Empty strip sets cannot violate the contribution estimate: both the actual contribution and its stated bound are zero. This is a degeneracy check, not a refutation.
- The tested scalar shifted-null family at N=1, q=barPhi(1), a=1, theta=-1 satisfies every hypothesis but fails NOT. Its actual contribution is barPhi(2)<exp(-3/2)barPhi(1), whereas the stated bound is 3exp(-3/2)barPhi(1). A one-coordinate endpoint example therefore does not exploit rank multiplicity or dependence to defeat the estimate.
- The tested singular antipodal pair, N=2, theta=(-2,-2), Sigma=[[1,-1],[-1,1]], q=barPhi(1), a=2, also satisfies every hypothesis but fails NOT. Rank 2 is impossible, and the actual contribution is 2barPhi(2+barPhi^{-1}(barPhi(1)/2))<(5/4)barPhi(1)exp(-4). Singular covariance and equality at the negative-mean cutoff alone therefore do not produce a violation in this tested family.

## Limitations

No worker found a counterexample. The two recorded candidates pass all hypothesis checks H1-H6 and fail only NOT; their failures neither falsify the target nor establish it. The scalar and antipodal computations concern their displayed parameter choices, not every scalar or antipodal model. The reported empty-set, N=1, singular complete-correlation, and q-endpoint checks do not exhaust mixed means, higher-dimensional covariance structures, simultaneous rejection ranks, or parameter sequences depending on q. In particular, the two recorded candidates use q=barPhi(1), outside the special q<=barPhi(e) range; they do not directly test the specialized coefficient or the shrinking-strip decomposition. No bound for the remaining near-boundary contribution or either universal-order target follows from this round.
