---
type: search_round
title: 'One-sided Gaussian BH upper-bound search: round 3 obstructions'
target_asset: gaussian_bh_one_sided_sharp_upper
mode: refute
round: 3
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
  - known_counterexamples
candidates:
  - cand_gaussian_bh_one_sided_sharp_upper_r3_s1_slow_rank_fourier_boundary
  - cand_gaussian_bh_one_sided_sharp_upper_r3_s3_regular_simplex_composite_nulls
statement_digest: 03b9629ae9bd4a6f3de6d1b9c08dfb86fb31a1aa0b7c62a1844a84111ad32086
performed_by: unknown
created_at: '2026-11-04T10:26:33.877Z'
extension_version: 0.0.4
---

## Obstructions

- **The prescribed Fourier arrays have too little radial cost to violate the target.** In [the Fourier candidate](../candidates/cand_gaussian_bh_one_sided_sharp_upper_r3_s1_slow_rank_fourier_boundary.md), with $L=\log(1/q)$, the exact unit-row Gaussian Gram representation has covariance rank $d=O(L^{1/4})$, zero independent residual variance, and testing dimension $N=6\lceil e^{L^2}\rceil$. Its null means include both zero and heterogeneous values diverging negatively, and it also has positive alternative means. All null loading coefficients in the approved [radial bound](../assets/multifactor_radial_fdr_bounds.md) vanish at unit row norm. The candidate's growing-dimension quantile calculation bounds the radial strip cost by $O(d\log L)$, giving $\operatorname{FDR}=O(qL^{1/4}\log L)=o(q\sqrt L)$. Thus NOT fails for the exact arrays; neither their enormous dimension nor their negative null means produces a counterexample.

- **The prescribed regular-simplex boundary is close enough to independent nulls.** In [the simplex candidate](../candidates/cand_gaussian_bh_one_sided_sharp_upper_r3_s3_regular_simplex_composite_nulls.md), $N=\lceil q^{-6}\rceil$, every coordinate is a true null with mean $0$ or $-q$, and the covariance has rank $N-1$ and off-diagonal entries $-1/(N-1)$. On the event $\overline Z\geq-q^2$, every qualifying BH rank transfers to the independent p-values $\overline\Phi(Z_i)$ at level $2q$, simultaneously over all rank thresholds. The complementary event has probability at most $e^{-1/(2q^2)}$. Hence $\operatorname{FDR}\leq2q+e^{-1/(2q^2)}=o(q\sqrt L)$ and NOT fails. This is an exclusion of the displayed growing-simplex all-null family, not arbitrary negative dependence or mixed alternative configurations.

- **Attaining the proposed constant does not refute the upper-bound target.** The round's search report records that the source construction attains $1/\sqrt\pi$ on the $q\sqrt{\log(1/q)}$ scale. Equality with the proposed upper constant is compatible with the target; a refutation requires a strict asymptotic excess. This report therefore supplies a boundary comparison, not a surviving counterexample or a proof of the unrestricted upper bound.

## Limitations

- Covariance rank, common-factor dimension, and the number of distinct null directions are different quantities. In the residual-free Fourier representation the displayed factor dimension equals covariance rank; a model with one common factor plus independent residuals can instead have large covariance rank. The Fourier obstruction does not justify identifying those model classes or excluding arbitrary covariance-rank growth.
- A union bound based on a small number $K$ of distinct null directions is scoped to that representation and its required small-$K$ regime. It does not describe the full known low-complexity coverage. The approved [oriented-null entropy bound](../assets/directional_entropy_one_sided_fdr_bound.md) already proves the proposed upper constant whenever $\mathcal E_0=o(\sqrt{\log(1/q)})$, with arbitrary varying ambient factor dimension and testing dimension, all nonpositive true-null means, and arbitrary alternative means and loadings. The approved radial bound also supplies a uniform finite-level estimate beyond the concrete arrays searched here. Growing $K$ alone therefore does not identify an uncovered family.
- The simplex coupling uses the specified equicorrelation boundary, dimension schedule, and all-null setting. It supplies neither a comparison for general covariance matrices with alternatives nor a general mean-monotonicity theorem. Negative true-null means remain included throughout the actual checks.
- The round establishes no control of unrestricted higher-complexity covariance configurations outside the applicable approved entropy and radial bounds and the scoped family exclusions. No admissible asymptotic counterexample survived; the unrestricted sharp upper target remains open.
