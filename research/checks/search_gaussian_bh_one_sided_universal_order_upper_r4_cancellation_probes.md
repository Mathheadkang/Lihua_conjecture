---
type: search_round
title: One-sided Gaussian BH round 4 cancellation probes
target_asset: gaussian_bh_one_sided_universal_order_upper
mode: refute
round: 4
directions:
  - idea_b5466535b0cc
  - idea_b87c754c46ad
  - idea_d31f99b82bbb
candidates: []
statement_digest: cd12dcc669b996361216cbba6573ecfdf68a5a7c79acc1bbf89869a2e1233389
performed_by: unknown
created_at: '2026-11-11T16:42:56.869Z'
extension_version: 0.0.4
---

## Obstructions

- The mixed-label rank-one family of idea_b5466535b0cc has actual FDR below q, uniformly over its size parameter m>=2 and 0<q<=S(1), where S=barPhi. Specifically, set N=2m, c_k=S^{-1}(qk/(2m)), mu=c_m, b=c_{m+1}, and M=c_1+2mu+2; its scores are m null copies of G, m-1 alternative copies of mu-G, and one alternative M-G. The rechecked largest-rank calculation gives FDR=q/2+S(M-b)/(m+1)<q/2+q/[2m(m+1)]<=q. The first Hermite contribution can grow with m only because other orders compensate it; losing that cancellation refutes an intermediate bound rather than the main theorem.
- With a single independent uniform null p-value and any fixed realization U of the alternative environment, the force-zero largest rank L(U) gives conditional FDP expectation (1/L(U))(qL(U)/N)=q/N. Thus the model in idea_b87c754c46ad has FDR=q/N even when its selected-null energy entropy grows. That entropy growth cannot by itself be interpreted as FDR inflation. The identity requires the stated independence and uniformity; it is not a bound for arbitrarily dependent nulls.
- The rank-one single-null Gaussian ladder in idea_d31f99b82bbb is controlled for all N>=2 and 0<q<=S(1): with u_j=S^{-1}(qj/N), scores T_0=X and T_j=2u_j-X, and b_j=2u_j-u_{j+1}, its full BH FDR is q/N+sum_{j=1}^{N-1}S(b_j)/[j(j+1)]<=q H_N/N<=q. Its positive harmonic remainder rules out a uniform per-null bound Cq/N, but its total FDR remains below q; that auxiliary failure does not refute the main universal-order statement.

## Limitations

All three workers wrote no candidate files. Each assigned family has actual FDR at most q; none yields an unbounded ratio FDR/[q sqrt(log(1/q))]. These exact family calculations are search obstructions and diagnostic checks, not a proof of the main upper bound, a formal approval of the draft ideas, or a resolution of the conjecture.

This round does not control the aggregate contributions of many dependent nulls under unrestricted signed covariance, heterogeneous means, growing dimension, or growing directional complexity. The Hermite calculation does not rule out every signed resummation, the independent-environment identity does not extend by assertion to dependent nulls, and the single-null ladder does not bound the full null aggregate. The finite conditional compound-p calibration, its independent source check, the Gaussian averaged-envelope estimate, and the uniform singular-limit gate remain separate proof obligations not established here.
