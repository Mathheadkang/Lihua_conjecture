---
type: falsification_check
title: 'Falsification check: gaussian_simes_sparse_crossing_fixed_level_cap'
target_asset: gaussian_simes_sparse_crossing_fixed_level_cap
outcome: no_counterexample_found
statement_digest: e02ea4068f860cd39643c688ca2deec7a6b3a9f5aedc920fd92281c915d2d7f4
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T19:21:30.349Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Cases checked

- Round 1, boundary_degenerate: cand_gaussian_simes_sparse_crossing_fixed_level_cap_r1_s1_rank_one_antipodal failed — NOT fails: on a rank-one covariance only one sign class can cross, at a single threshold, so $\mathbb P(S_q)<2\overline\Phi(u_q+1)<0.095$.
- Round 1, boundary_degenerate: cand_gaussian_simes_sparse_crossing_fixed_level_cap_r1_s1_rank_two_circle failed — NOT fails: in rank two a sparse crossing forces $|G|>u_q+1$, so $\mathbb P(S_q)\le e^{-(u_q+1)^2/2}<0.247$ for every $N$ and every rank-two $\Sigma$.
- Round 1, boundary_degenerate: cand_gaussian_simes_sparse_crossing_fixed_level_cap_r1_s1_sum_zero_equicorrelated failed — NOT fails: the minimal equicorrelation $-1/(N-1)$ is an $O(N^{-1/2})$ common shift of i.i.d. coordinates, so $\mathbb P(S_q)\approx q\le1/4$.
- Obstruction: Small $N$ is empty: the sparse window $qk/N<\overline\Phi(u_q+1)$ contains a rank $k\ge1$ only when $N>q/\overline\Phi(u_q+1)$ (for $q\le1/4$ this needs $N\ge6$), and then only ranks $k\le K<N\overline\Phi(u_q+1)/q$; a counterexample needs $N\to\infty$ as $q\to0$.
- Obstruction: Low rank fails: if $\operatorname{rank}\Sigma=d$, write $T_i=\langle v_i,G\rangle$ with $|v_i|=1$, $G\sim\mathcal N_d(0,I)$; a sparse crossing forces some $T_i>u_q+1$, hence $|G|>u_q+1$, so $\mathbb P(S_q)\le\mathbb P(\chi^2_d>(u_q+1)^2)$. Any counterexample family needs $d\ge(1-o(1))(u_q+1)^2\approx2\log(1/q)$ as $q\to0$. Rank one gives the sharper exact bound $\mathbb P(S_q)<2\overline\Phi(u_q+1)$; rank two gives $e^{-(u_q+1)^2/2}$.
- Obstruction: Nonnegative correlations fail: $S_q$ is contained in the Simes rejection event, so by [lib_chi2024_positive_gaussian_simes](../library/chi2024_negative_dependence/assets/lib_chi2024_positive_gaussian_simes.md) $\mathbb P(S_q)\le q$ whenever $\Sigma_{ij}\ge0$ (including all clone/clump block structures). A counterexample must use negative correlations.
- Obstruction: Uniformly weak negative correlation fails: the extreme equicorrelated matrix $\rho=-1/(N-1)$ is an $O(N^{-1/2})$ common shift of i.i.d. coordinates and gives $\mathbb P(S_q)\approx q$. Negative correlation must be strong (of order one) on many pairs, which the PSD constraint allows only through structured low-dimensional loadings, which the low-rank obstruction in turn forces to have dimension at least about $(u_q+1)^2$.

## Limitations

- Only one worker (direction boundary_degenerate). Not covered: intermediate rank $d\asymp(u_q+1)^2$ or larger with strongly signed loadings (for example sign-cube or spherical-code frames in dimension about $2\log(1/q)$), Hommel-type multi-scale constructions in which clumps at different sparse dyadic scales share coordinates, and mixtures of antipodal clumps with independent fog.
- The sum-zero bound is asymptotic plus Monte Carlo, not a finite-$N$ inequality.
- The low-rank and positive-correlation obstructions bound the full Simes or radius event and do not use the sparse restriction beyond $T_i>u_q+1$.

Object search: 3 candidate(s) in 1 round(s).
