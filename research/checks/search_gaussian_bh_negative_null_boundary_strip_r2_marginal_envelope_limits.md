---
type: search_round
title: Marginal-envelope and parameter-limit obstructions for the negative-null strip
target_asset: gaussian_bh_negative_null_boundary_strip
mode: refute
round: 2
directions:
  - known_counterexamples
  - extremal
  - boundary_degenerate
candidates:
  - cand_gaussian_bh_negative_null_boundary_strip_r2_s3_mixed_tied_cutoffs
statement_digest: 8cb3729d0db20bedb0d623cce2676cfa7d01e08b10180884af70e5a810e0b568
performed_by: unknown
created_at: '2026-11-11T19:38:23.224Z'
extension_version: 0.0.4
---

## Obstructions

- The known-counterexample worker found no candidate: the original BH rejection inequality gives the pathwise inverse-p-value envelope 1{i rejected}/(R vee 1)<=q 1{p_i<=q}/(Np_i). The reported Gaussian marginal integral controls this envelope for arbitrary joint laws with the required marginals, obstructing dependence-based attacks without changing the actual procedure.
- The extremal worker found no candidate in a(q) or threshold limits. Its reported Gaussian-integral calculation retains a>0 explicitly; at a_q=2log(U)/U and U>=e, the coefficient is bounded by (1+1/U)/(2log(U))+1/(4log(U)^2)<=3/4+1/(2e).
- The mixed-mean singular common-noise candidate at q=barPhi(e) passes H1-H6 and fails only NOT. Its exact far-null contribution barPhi(e+2/e)/2 obeys both contribution bounds, and its same-procedure FDR decomposition also holds. Mixed deep and boundary means, tied cutoffs, and endpoint inclusion therefore do not yield a violation in this tested family.

## Limitations

This round recorded one failed candidate and no survivor. The first two workers supplied search obstructions, not an independently audited or approved proof; the target remains draft. The mixed example does not exhaust dimensions, covariance structures, or mean configurations. All counts refer to the same full ordinary BH procedure. No bound on the remaining near-boundary contribution or either universal-order target follows from this record.
