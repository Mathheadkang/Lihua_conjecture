---
type: search_round
title: >-
  Refute search round 1 (boundary and degenerate cases) for the sign-split
  cluster steering bound
target_asset: gaussian_bh_sign_split_cluster_steering_bound
mode: refute
round: 1
directions:
  - boundary_degenerate
candidates:
  - >-
    cand_gaussian_bh_sign_split_cluster_steering_bound_r1_s1_comonotone_single_cluster
  - >-
    cand_gaussian_bh_sign_split_cluster_steering_bound_r1_s1_full_information_carrier
  - >-
    cand_gaussian_bh_sign_split_cluster_steering_bound_r1_s1_zero_cross_nonneg_loadings
statement_digest: 4f504776ef9d05ca6e613df26ad574964aa50a24ff5098db3d1c7b8692792457
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T21:45:47.957Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Obstructions

- Every carrier with $Q=0$ (in particular $Y=T$, or any $Y$ that determines $T_{I_0}$) fails NOT: the conditional law is a point mass, and at $t\downarrow qR/N$ one gets $qK(Y)\ge V/R$, so $\operatorname{FDP}\le\min\{1,qK(Y)\}$ pointwise and the conclusion holds with $C_2=1$. More generally, a counterexample needs $Y$ to leave substantial conditional null variance.
- Few nulls fail NOT: the per-null band (Benjamini-Yekutieli) bound gives $\mathbb E[\operatorname{FDP}]\le q(n_0/N)H_N$ for every Gaussian model, so a counterexample needs $n_0\gg N/\log N$; in particular $|I_0|=1$ gives LHS $\le q$.
- A perfectly tied null block with equal means placed in one cluster fails NOT: its FDR contribution is at most $q\,x(1+\ln(1/x))\le q$ with $x=n_0/N$, for any alternatives, while $K\equiv1$. Coarsening the partition only raises $K$ (since $|c|\,\mathbb P(\min_c p\le t\mid Y)\ge\sum_{i\in c}\mathbb P(p_i\le t\mid Y)$), so the hardest instances use the finest admissible partition.
- Every entrywise nonnegative $\Sigma$ fails NOT: Gaussian with nonnegative covariances is PRDS on $I_0$, so $\operatorname{FDR}\le qn_0/N$. Hence a counterexample needs negative correlation between some nulls and alternatives (steering against the null), and the equality case $Q_{ij}=0$ helps only through such negative loadings.

## Limitations

- Not covered: the equality case $Y$ constant, mutually independent (or conditionally independent) nulls, singleton clusters, with alternatives loading negatively on many nulls; this is the open class-E case and was not attacked.
- Not covered: comonotone null blocks with staggered null means $\theta_i<0$ (the tied-block band bound above uses equal means), and cross-cluster $Q_{ij}<0$ strictly.
- Not covered: intermediate carriers $Y$ with partial conditional variance, the role of the rational-$t$ supremum in $K$ for irrational $q$ (it does not matter for the $Q=0$ case), and small-$q$ asymptotics of the constants.
