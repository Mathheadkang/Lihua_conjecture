---
type: search_round
title: >-
  Refute search round 1 for few-block compression of the Schur-square downward
  variation (boundary and degenerate cases)
target_asset: gaussian_simes_schur_variation_few_block_compression
mode: refute
round: 1
directions:
  - boundary_degenerate
candidates:
  - >-
    cand_gaussian_simes_schur_variation_few_block_compression_r1_s1_antipodal_sign_blocks
  - >-
    cand_gaussian_simes_schur_variation_few_block_compression_r1_s1_simplex_frame
  - >-
    cand_gaussian_simes_schur_variation_few_block_compression_r1_s1_small_common_loading
statement_digest: ae49babfdb545830e8ad7375a17d918e1fb1ba20e49b625bd07dbdd7738fee3a
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-13T05:45:35.188Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Obstructions

- Every candidate must reach $\mathcal V_-(f_{q,\Sigma})>1/8$ at arbitrarily small $q$. The reason: $\mathcal M(q)\ge0$, and $q_2$ is existential. A counterexample at one fixed $q$ refutes nothing. In particular $K_\flat(q)=1$ for $q>4^{-8}$, and there $\mathcal M(q)=0$: one block gives $\Sigma'=J$ and $J\circ J=J$, so the path is constant. The lemma then reads $\mathcal V_-\le1/8$, but $q_2$ can be taken below $4^{-8}$.
- Hommel's bound applies to every Gaussian path, since its p-values are uniform: $f(t)\le qH_N$. Proof: on the Simes event with largest crossing index $k^*$, $1\le\sum_i\sum_{k\le k^*}\mathbf 1\{q(k-1)/N<p_i\le qk/N\}/k$; take expectations. So $\mathcal V_->1/8$ needs one of two things: about $1/(8qH_N)$ separate downward oscillations, or a Gaussian Simes size of order $1$, which needs $\log N\gtrsim1/(8q)$ and would itself break the Gaussian Simes bound being pursued.
- Every $\Sigma$ with nonnegative entries keeps $f\le q$ on the whole path. The entries of $R(t)$ are $\rho_{ij}(1-t+t\rho_{ij})\ge0$, so the positive Gaussian Simes inequality (lib_chi2024_positive_gaussian_simes) applies. A single dip in such a profile costs at most $q$.
- No endpoint jump is possible, singular $\Sigma$ included: $f$ is continuous on $[0,1]$. The rejection region is closed, and its boundary lies in $\bigcup_{i,k}\{z_i=\overline\Phi^{-1}(qk/N)\}$. That set is null under every $R\in\mathcal C_N$ because each $Z_i\sim\mathcal N(0,1)$. The Gaussian law is weakly continuous in the covariance. So degenerate or rank-dropping endpoints give no free variation.
- Entries in $\{0,1\}$: then $\Sigma\circ\Sigma=\Sigma$ and the path is constant. Entries in $\{0,\pm1\}$ (independent sign blocks): $f(0)=f(1)=q$ exactly, and the profile has one shallow dip near $t=1$. Exact for one block, $\mathcal V_-/q\to\approx0.19$ as $q\to0$; numerically $\mathcal V_-\approx0.25q$ for up to $6000$ coordinates, with no growth in the number of directions.
- Negative equicorrelation or simplex frames: the path moves the equicorrelation by only $O(1/N)$ around $0$, and numerically $f$ stays within a few percent of $q$. Mixed-sign small common loadings and random rank-3 frames give $\mathcal V_-\approx0.05q$ numerically. Equicorrelated $\rho_0\ge0$: the path lowers $\rho$ toward $\rho_0^2$, so $f$ climbs out of the large-$N$ dip of idea_ed169268dd35, numerically monotone increasing for $\rho_0=0.5$. That dip feeds upward, not downward, variation.

## Limitations

- For the many-direction families, the $\mathcal V_-$ values beyond one block are Monte Carlo grid estimates, not proofs. They use a 26-point $t$-grid, $2\times10^4$ to $10^6$ reps, and levels $q\ge10^{-3}$. Narrow oscillations between grid points, or at levels $q<10^{-3}$, are not excluded.
- No bound on the number of monotone pieces of $f$ was proved. A family whose many directions produce $\Omega(1/q)$ oscillations of size $\asymp q$ remains the open route to a counterexample.
- Not covered: possible accumulation of oscillations as $t\to0$ or $t\to1$ for singular $\Sigma$ (only continuity was shown). Also not covered: mixed-sign configurations with large $N$ at $\log N\sim1/q$ that approach Hommel's extreme; general unbalanced sign classes beyond one block; and the value of $\mathcal M(q)$ itself.
