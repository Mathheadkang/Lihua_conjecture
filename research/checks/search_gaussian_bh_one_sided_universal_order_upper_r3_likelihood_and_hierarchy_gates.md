---
type: search_round
title: One-sided Gaussian BH round 3 likelihood and hierarchy gates
target_asset: gaussian_bh_one_sided_universal_order_upper
mode: refute
round: 3
directions:
  - idea_57338934f2f7
  - idea_8a445ee0b200
  - idea_aca5b09e9a0c
candidates: []
statement_digest: cd12dcc669b996361216cbba6573ecfdf68a5a7c79acc1bbf89869a2e1233389
performed_by: unknown
created_at: '2026-11-11T16:40:50.286Z'
extension_version: 0.0.4
---

## Obstructions

- The collinear all-null finite mean grids in idea_8a445ee0b200 cannot refute the main bound. With a>0, theta_j=-aj/N, a common standard Gaussian Y, and S=barPhi, their exact largest-crossing threshold is b_N=min_{1<=j<=N}{aj/N+S^{-1}(qj/N)}. Every summand is at least S^{-1}(q), so FDR=S(b_N)<=q for every finite N. The separate question of transferring finite-model rare-clone derivatives through atomization does not furnish a counterexample to the main FDR bound.
- In the proposed two-level Gaussian hierarchy of idea_aca5b09e9a0c, a group's conditional null density depends on one combined latent projection. Multiplying two separate tilt gains therefore does not establish the claimed enhancement: the actual conditional density must be computed for the combined projection. This obstructs that product calculation, not every hierarchical or degenerate Gaussian family.

## Limitations

All three workers wrote no candidate files and supplied no verified finite Gaussian BH family with asymptotically unbounded FDR/[q sqrt(log(1/q))]. No conjecture is resolved by these search results, and the obstructions above are not a proof of the universal upper bound.

The frozen-ray likelihood probes in idea_57338934f2f7 remain diagnostics rather than finite-model BH constructions or super-order lower bounds. The reported Mehler rows at q=1e-4 are unreliable and are not used as evidence; the cascade probe remains open.

The hierarchical probe still lacks specified type-B means, finite weights, and a calculation for the actual largest BH rank. The single combined-projection observation does not exclude singular degenerations, growing hierarchical models, or other admissible choices. The derivative-transfer issue remains a distinct limit and perturbation obligation, despite the exact FDR control of the collinear mean grid itself.

Unrestricted growing dimension, signed covariance, heterogeneous null and alternative means, and the full q-dependent supremum remain unbounded by this round. The finite conditional compound-p calibration, its independent source check, the Gaussian averaged-envelope estimate, and the uniform singular-limit gate were not established here.
