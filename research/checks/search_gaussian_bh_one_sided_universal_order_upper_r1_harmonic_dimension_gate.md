---
type: search_round
title: >-
  One-sided Gaussian BH round 1: harmonic dimension obstruction and remaining
  uniformity gap
target_asset: gaussian_bh_one_sided_universal_order_upper
mode: refute
round: 1
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates: []
statement_digest: 00cfb3c66a8136044b1cb19c4e657b92bca75995aa6b9711598a30aa2009eff2
performed_by: unknown
created_at: '2026-11-10T20:35:48.508Z'
extension_version: 0.0.4
---

## Obstructions

- Every admissible finite Gaussian model has super-uniform true-null p-values, including singular covariance and arbitrary true-null means at most zero. The arbitrary-dependence BH harmonic bound therefore gives
  $$
  \operatorname{FDR}_{\mathrm{BH}}^{(1)}(q;N,\theta,\Sigma)
  \le q\frac{|I_0^{(1)}(\theta)|}{N}H_N
  \le qH_N\le q(1+\log N),
  \qquad H_N=\sum_{k=1}^N\frac1k.
  $$
  Consequently, for any sequence of admissible models with $q_m\downarrow0$, writing $L_m=\log(1/q_m)$, if $\log N_m/\sqrt{L_m}\le B$ eventually for one finite sequence-specific $B$, then
  $$
  \limsup_{m\to\infty}
  \frac{\operatorname{FDR}_{\mathrm{BH}}^{(1)}(q_m;N_m,\theta_m,\Sigma_m)}
       {q_m\sqrt{L_m}}\le B.
  $$
  Thus fixed dimension, and more generally any one sequence with bounded $\log N_m/\sqrt{L_m}$, cannot yield an unbounded normalized ratio. This conclusion permits arbitrary means, null proportions, singular covariance, rank, and factor structure within each sequence. Its constant depends on the sequence's growth bound $B$: it supplies no single universal constant across arbitrarily varying growth coefficients. Any proposed sequence whose normalized ratio tends to infinity must have $\log N_m/\sqrt{L_m}\to\infty$; this is a necessary condition, not a sufficient construction or a proof of the target.

## Limitations

The round produced zero candidate files. No concrete admissible sequence with an unbounded normalized ratio was established. The available search report supplies no tested numerical parameter list, so none is asserted here. Singular covariance and negative true-null means yielded no candidate in this round; these classes have not been excluded in arbitrary dimension.

The unrestricted regime in which dimension grows faster than every fixed coefficient of $\sqrt{\log(1/q)}$ on the logarithmic scale remains open. The harmonic estimate also does not yield a uniform constant over the union of sequences with arbitrarily large finite growth coefficients. The target still requires one finite $C_1$ and one $q_{0,1}>0$, independent of $N$, all means and covariances, null proportion, rank, factor dimension, and every other complexity parameter, for every finite admissible model at every $0<q\le q_{0,1}$; models may change arbitrarily with $q$. No counterexample found in this round is not evidence of a completed proof, and no proof or target-status change is inferred.
