---
type: falsification_check
title: 'Falsification check: gaussian_bh_angular_cluster_partial_entropy_bound'
target_asset: gaussian_bh_angular_cluster_partial_entropy_bound
outcome: no_counterexample_found
statement_digest: 736750aaadb60109c2ce46215b308676bc7a0cd9e89173948fa97978fa8123b1
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T06:16:01.464Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Cases checked

- Round 1, boundary_degenerate: cand_gaussian_bh_angular_cluster_partial_entropy_bound_r1_s1_chord_equality_orthogonal_spread failed — NOT fails: per null, the BH weight is at most $\min(1,q/(m\overline\Phi(X)))$, and $\mathbb P(Y_G\le u\mid X)$ decays like $\Phi(\kappa-\log(q/p)/(2\kappa))$, so the scale-$\kappa/u$ spread gives only $O(q/m)$ per null on $\{Y_G\le u\}$.
- Round 1, boundary_degenerate: cand_gaussian_bh_angular_cluster_partial_entropy_bound_r1_s1_full_exact_cluster failed — NOT fails: with zero spread and $\pi_G=1$ the strip is empty and the off-strip part is at most $\mathbb P(Y_G>u)=q\pi_G$.
- Round 1, boundary_degenerate: cand_gaussian_bh_angular_cluster_partial_entropy_bound_r1_s1_singleton_minimal_mass failed — NOT fails: for a singleton the BY bound $(q/m)(1+\log m)$ equals $q\pi_G(1+\log(1/\pi_G))$, which is exactly the allowed order in (b).
- Obstruction: The second term of (a) cannot fail: $V_G\le R$ gives $V_G/(R\vee1)\le1$, so it is at most $\mathbb P(Y_G>b_G)=\overline\Phi(b_G)=q\pi_G$, under any dependence.
- Obstruction: Part (b) cannot fail: it follows from the approved [angular-cluster entropy bound](../assets/gaussian_bh_angular_cluster_entropy_bound.md) with $J=1$, $I_*=G$, $\beta_1=b_G$. Unit loadings give $\gamma_i=0$; $\rho_i=w_i^{\mathsf T}v\ge1-\kappa^2/(2u^2)\ge1/2$ for small $q$; and $b_G\sqrt{1-\rho_i^2}\le b_G\|w_i-v\|\le\kappa b_G/u\le\kappa'$ with $\kappa'=2\kappa\sqrt{C+1}$, because $\pi_G\ge q^C$ forces $b_G\le\overline\Phi^{-1}(q^{C+1})$, so $b_G/u$ stays bounded as $q\to0$. The total $\mathbb E[V_G/(R\vee1)]$ is then $\le q\pi_G(5/2+A_1(\kappa')+\log(1/\pi_G))$. This is where $\pi_G\ge q^C$ and small $q$ enter.
- Obstruction: The first term of (a) cannot fail, for any configuration of the coordinates outside $G$. Per null $i\in G$ one has the deterministic BY-type bound $\mathbf 1\{p_i\le qR/m\}/(R\vee1)\le\min(1,q/(m\overline\Phi(X_i)))\mathbf 1\{X_i\ge u\}$ with $X_i=w_i^{\mathsf T}Z$ (here $\theta_i\le0$ helps). The scale condition gives $\mathbb P(Y_G\le u\mid X_i=x)\le\Phi(\kappa-(x-u)u/(2\kappa))$, and $u(x-u)\ge\log(q/\overline\Phi(x))$. Integrating gives at most $(q/m)(1+\int_0^\infty\Phi(\kappa-s/(2\kappa))\,ds)$ per null. So the BY logarithm is cut off at $O(\kappa^2)$ on $\{Y_G\le u\}$. This needs neither small $q$ nor $\pi_G\ge q^C$. It covers equality $\|w_i-v\|=\kappa/u$, unbounded $|G|$ with orthogonal spread, shifted effective centres, and sub-clusters.
- Obstruction: Zero-spread and full-mass degeneracies ($w_i=v$, $\pi_G=1$, so $b_G=u$ and the strip is empty) and singletons at minimal mass $\pi_G=q^C$ meet the bound with $A_1=1$. For a singleton, $\log m=\log(1/\pi_G)$, so the BY staircase reaches the allowed order of (b) but does not exceed it.
- Obstruction: Net effect: the three obstructions together give a complete proof sketch of the statement. On this evidence it is true, and refute search in other directions is unlikely to succeed.

## Limitations

- Only boundary and degenerate cases were examined explicitly. The proof sketch above was not written out with explicit constants. The claim $b_G/u\le2\sqrt{C+1}$ for $q\le q_1(C)$ and the $\rho_i\ge1/2$ step need $q_1$ small, and were checked only asymptotically.
- Not covered: small cases worked out exactly, extremal multi-cluster configurations, and known pathological dependence structures (other slots or later rounds).

Object search: 3 candidate(s) in 1 round(s).
