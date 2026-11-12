---
type: search_round
title: 'One-sided Gaussian BH upper-bound search: round 2 obstructions'
target_asset: gaussian_bh_one_sided_sharp_upper
mode: refute
round: 2
directions:
  - idea_1425d6ce283f
  - known_counterexamples
  - extremal
  - boundary_degenerate
candidates:
  - cand_gaussian_bh_one_sided_sharp_upper_r2_s2_harmonic_gaussian_marginals
  - cand_gaussian_bh_one_sided_sharp_upper_r2_s3_dense_planar_directions
  - cand_gaussian_bh_one_sided_sharp_upper_r2_s4_near_singular_residual_boundary
statement_digest: 03b9629ae9bd4a6f3de6d1b9c08dfb86fb31a1aa0b7c62a1844a84111ad32086
performed_by: unknown
created_at: '2026-11-04T10:15:59.733Z'
extension_version: 0.0.4
---

## Obstructions

- **The balanced planar angular grid has only order-$q$ FDR.** In [the dense planar candidate](../candidates/cand_gaussian_bh_one_sided_sharp_upper_r2_s3_dense_planar_directions.md), all means are zero and $N=\lceil q^{-3}\rceil$ equally spaced unit directions project a two-dimensional standard Gaussian vector. The continuous-circle crossing event at level $\alpha$ has probability at most $\alpha$. The exact finite grid differs from its angular mass by at most $2/N$: a qualifying BH rank at least four therefore implies a continuous-circle crossing at level $2q$, while ranks at most three cost at most $3q$ by marginal uniformity and a union bound. Consequently $\operatorname{FDR}\leq5q$ for these exact finite arrays, so NOT fails and their ratio to $q\sqrt{\log(1/q)}$ tends to zero. This excludes the balanced zero-mean grid, rather than every rank-two covariance model.

- **The displayed vanishing-residual family is negligible on the target scale despite growing covariance rank.** In [the near-singular residual candidate](../candidates/cand_gaussian_bh_one_sided_sharp_upper_r2_s4_near_singular_residual_boundary.md), put $L=\log(1/q)$, $\sigma=L^{-1/4}$, $r=\sqrt{1-\sigma^2}$, and $M=2\lceil e^{L^2}\rceil$. Its $M$ nulls have means alternating between $0$ and $-q$ and observations $\theta_j+rZ+\sigma\varepsilon_j$; its $M$ alternatives have the prescribed positive means and loading $-1$ on $Z$. The approved one-factor radial bound specializes to $\operatorname{FDR}=O(q[1+L^{1/4}])=o(q\sqrt L)$, uniformly in this family's finite dimension. Hence NOT fails. The factor dimension is one, whereas the covariance rank is $M+1$; the conclusion comes from the radial estimate with this loading schedule, not from the earlier rank-one obstruction.

- **The harmonic example fails joint Gaussianity before NOT can be checked.** In [the harmonic normal-marginal candidate](../candidates/cand_gaussian_bh_one_sided_sharp_upper_r2_s2_harmonic_gaussian_marginals.md), the difference of two coordinates is nonconstant and has an atom at zero. Every linear combination of a jointly Gaussian vector is either a continuous normal variable or a constant, so this difference violates H5. Gaussian marginals cannot repair this joint-law failure. The later checks and NOT remain unknown; this candidate is inadmissible rather than an admissible Gaussian family with a proved small FDR.

## Limitations

- The planar argument does not cover arbitrary angular weights, heterogeneous nonpositive means, mixtures with alternatives, or general higher-rank geometry. Its finite-grid estimate supplies no reduction of those configurations to a balanced circle.
- The residual argument covers the displayed null loadings, residual scale, null means, and alternative configuration. It establishes no universal exclusion of common-factor models with independent residuals, no reduction of covariance rank to factor dimension, and no unrestricted sharp constant.
- **Auxiliary finite-$q$ evidence only:** the round's paired mean screen reported no FDR increase in its tested configurations. This finite numerical screen is separate from the analytic NOT failures and from the inadmissible harmonic example. It proves neither a general monotonicity theorem in true-null means nor a valid replacement of arbitrary negative true-null means by zero, and it does not control the uniform $q\downarrow0$ supremum.
- Arbitrary $q$-dependent dimension, higher-rank dependence, and composite-null mean configurations remain unresolved outside the scoped families already excluded. No admissible asymptotic counterexample survived this round; the unrestricted target and its proposed constant $1/\sqrt\pi$ remain open.
