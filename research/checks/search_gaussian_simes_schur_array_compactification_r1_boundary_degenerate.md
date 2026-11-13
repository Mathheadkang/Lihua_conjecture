---
type: search_round
title: >-
  Refute search round 1 for the Schur-array compactification of the loaded Simes
  supremum (boundary and degenerate cases)
target_asset: gaussian_simes_schur_array_compactification
mode: refute
round: 1
directions:
  - boundary_degenerate
candidates:
  - >-
    cand_gaussian_simes_schur_array_compactification_r1_s1_antipodal_singular_clones
  - >-
    cand_gaussian_simes_schur_array_compactification_r1_s1_identity_array_sigma_to_zero
  - >-
    cand_gaussian_simes_schur_array_compactification_r1_s1_loading_cancelling_negative_equicorrelation
statement_digest: 3ff8e143d2d88073822e605c70956af7082d952917d813001866b18b04299581
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-13T05:51:19.466Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Obstructions

- **Part 6 cannot be broken by any degenerate family.** It concerns only the finite-model suprema. $B^\sigma(q)\le B(q)$ because $(1-\sigma^2)\Sigma+\sigma^2\mathbf1\mathbf1^{\mathsf T}\in\mathcal C_N$. For the reverse, fix $N$ and $\Sigma$: then $F_q((1-\sigma^2)\Sigma+\sigma^2J)\to F_q(\Sigma)$, since the Simes event's boundary lies in the marginal hyperplanes $\{T_i=\overline\Phi^{-1}(qk/N)\}$, which are null even for singular covariances. So $\liminf_{\sigma\downarrow0}B^\sigma\ge B$. The equicorrelated/identity-array discontinuity at $\sigma=0$ (idea_ed169268dd35) comes from taking $N\to\infty$ before $\sigma\to0$ for a fixed infinite array. The supremum over $N$ lets one use fixed $N$, and the lemma never asserts $\Phi_\sigma(P)\to\Phi_0(P)$ or convergence of maximizers.
- **At fixed $\sigma>0$ the loading keeps every infinite array away from the $\sigma=0$ discontinuity.** Conditionally on the directing measure, the mean loaded correlation is $\sigma^2+(1-\sigma^2)\|\mathbb E v\|^2\ge\sigma^2$. Loaded near-independence (negative residual correlation cancelling the loading) exists only at a fixed finite $N$, where finite-dimensional continuity applies.
- **Clone ties, singular $\Sigma$, the edge entries $C_{ij}=\pm1$, $N=1$, the endpoints $t\in\{0,1\}$ and $q=1/4$ all satisfy parts 1, 3 and 4.**
  - $g_t$ maps $[-1,1]$ into $[-1,1]$ with $g_t(1)=1$, so clones stay tied, and $(1-t)C+tC\circ C$ is PSD.
  - The clone-weighted Simes event $\max_j[\sum_iw_i\mathbf1\{p_i\le p_j\}-p_j/q]\ge0$ is continuous in the weights off the null set $\{p_j=qk/N\}$, so $\Phi_\sigma(P_\Sigma)=F_q(\text{loaded }\Sigma)$.
  - $S_1$ makes every loaded off-diagonal entry nonnegative, so the positive-Gaussian Simes theorem gives $\le q$, with equality at rank-one $J$.
- **Part 5 reduces to two inclusions.** Each $\Phi_{n,\sigma}(P)$ averages loaded finite models, which gives $\le B^\sigma$. The array $P_\Sigma$ gives $\ge$. Compactness of $\mathfrak P_0$ holds because the all-null condition fixes the marks, so only the compact $[-1,1]$-valued Gram entries remain.

## Limitations

- The search did not re-examine the uniform-in-$P$ convergence of the approved array compactification (its part 1) for small fixed $\sigma$. Part 2 inherits it as an approved dependency, and a slow, $\sigma$-dependent rate there was not probed.
- The Dey (2024) population limit used for the identity-array discontinuity is only cited in idea_ed169268dd35, not imported. The obstruction above does not depend on it.
- Monte Carlo checks covered only dimensions 2 to 4 and the identity array up to $n=2000$, which is too small to see the Dey limit. Large-$N$ structured families (block, spiked or ultrametric arrays) were left to other directions.
