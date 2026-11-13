---
type: search_round
title: >-
  Refute search round 1 for the angular-cluster entropy bound (boundary and
  degenerate cases)
target_asset: gaussian_bh_angular_cluster_entropy_bound
mode: refute
round: 1
directions:
  - boundary_degenerate
candidates:
  - >-
    cand_gaussian_bh_angular_cluster_entropy_bound_r1_s1_equality_level_max_spread
  - cand_gaussian_bh_angular_cluster_entropy_bound_r1_s1_sign_cube_tiny_clusters
  - cand_gaussian_bh_angular_cluster_entropy_bound_r1_s1_wide_angle_q_near_half
statement_digest: c0f4a35d70bb8c3321136accd04202b71bb70ae9a12fd0aaa5c3d48abe6e1b98
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T05:47:01.490Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Obstructions

- Every object fails NOT, because the statement reduces to a per-null estimate that holds with an explicit $A_1$. For cluster $j$: on $\{Z_{v_j}>\beta_j\}$ the cluster's FDP share is at most $1$, giving $\overline\Phi(\beta_j)$; on $\{Z_{v_j}\le\beta_j\}$ the per-null Lei identity ([lei2026_conditional_fdp_bound]) gives $\frac qm\mathbb E[G_i;Z_{v_j}\le\beta_j]$ with $G_i=\sup_{0<t\le q}F_{i,Z}(t)/t$. With $Y=a_i^{\mathsf T}Z/r_i$: (i) $\mathbb E[G_i;Y\le u]\le\frac12+\gamma_iu/\sqrt{2\pi}$ by [lei2026_integrated_conditional_tail_ratios] (mean $0$ dominates $\theta_i\le0$); (ii) for $Y>u$, $G_i\le1/\overline\Phi(Y)$, since $\overline\Phi(x)\ge\overline\Phi(Y)\,\overline\Phi((x-r_iY)/s_i)$; (iii) $Z_{v_j}\mid Y=y\sim\mathcal N(\rho_iy,1-\rho_i^2)$ and $\phi/\overline\Phi(y)\le y+1$ give $\int_u^{\beta_j}\phi/\overline\Phi=\log(q/\overline\Phi(\beta_j))$ plus an off-strip integral at most $A^*(\kappa)=2(\kappa+1)(\kappa\Phi(\kappa)+\phi(\kappa))+2((\kappa^2+1)\Phi(\kappa)+\kappa\phi(\kappa))$, using $\beta_j(1-\rho_i)/\sigma_i\le\beta_j\sigma_i\le\kappa$ and $\rho_i\ge1/2$. Zero-loading members have $G_i\le1$. Hence the statement holds with $A_1=A^*$ (nondecreasing, $A^*(1)\approx8.18$).
- A_1 is existential in kappa only, so a single object can never refute; a counterfamily must make $(\mathrm{LHS}-\text{explicit part})/(q\pi_*)$ unbounded at fixed $\kappa$, and the obstruction above caps it by $A^*(\kappa)$.
- Equality cases $\beta_j=u$ and $\beta_j\sigma_i=\kappa$ (unit loadings, $q\to0$): the off-strip integral converges to $\int_0^\infty\Phi(\kappa/2-t/\kappa)\,dt$ (about $0.698$ at $\kappa=1$), bounded uniformly in $q$.
- Cosine exactly $1/2$ forces $u\le\beta_j\le2\kappa/\sqrt3$, so $q$ is bounded below and all terms are $O_\kappa(q\pi_j)$.
- Many tiny clusters (sign-cube, simplex frames) and negative null-alternative correlations cannot couple clusters: the bound is a sum of per-null Lei bounds plus per-cluster off-strip probabilities, so alternatives only change $R_i$, which the supremum $G_i$ already dominates.

## Limitations

- Not covered: verification that Lei's integrated one-sided bound applies verbatim with $Y$ in place of a one-dimensional factor when $d>1$ (it does by conditional independence given $Z$, but no worker rechecked the source constants), and the inequality $\phi/\overline\Phi(y)\le y+1$ for small $y>0$ was used without written proof.
- Simplex frames were treated only through the general decomposition, not computed numerically; two-sided p-values are outside the statement and were not examined.
