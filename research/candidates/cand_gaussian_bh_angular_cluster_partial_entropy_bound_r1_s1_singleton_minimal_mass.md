---
type: candidate
title: Singleton cluster at the minimal mass pi_G = q^C with a BY-type staircase
status: failed
target_asset: gaussian_bh_angular_cluster_partial_entropy_bound
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  NOT: fail
mode: refute
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: 736750aaadb60109c2ce46215b308676bc7a0cd9e89173948fa97978fa8123b1
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T06:16:00.960Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Object

$C\ge1$, $q$ small with $m=q^{-C}$ an integer, $G=\{1\}$, $\theta_1=0$, $v=w_1$ (exact, any $\kappa$), so $\pi_G=q^C$ is the equality case of H4 and $b_G=\overline\Phi^{-1}(q/m)$. The other $m-1$ coordinates form an arbitrary staircase (alternatives and nulls on further factors) chosen so that $R=j$ exactly when $p_1\in(q(j-1)/m,qj/m]$, the Benjamini-Yekutieli worst-case pattern, to push the strip part (b) to the $\log m$ scale or beyond.

## Checks

### H1, H2, H3, H4
Unit loading; $\|w_1-v\|=0$; $G\subseteq I_0$ nonempty; $\pi_G=q^C$ exactly.

### NOT
Fails. For any configuration of the other coordinates,
$$
\frac{\mathbf 1\{1\in\mathcal R_q\}}{R\vee1}\le\sum_{j=1}^m\frac1j\mathbf 1\Bigl\{\tfrac{q(j-1)}m<p_1\le\tfrac{qj}m\Bigr\},
$$
and $p_1$ is uniform, so the total contribution is at most $\frac qm\sum_{j\le m}\frac1j\le q\pi_G(1+\log m)=q\pi_G(1+\log(1/\pi_G))$. This is (b) with $A_1=1$, and the BY staircase attains this order, so the logarithm in (b) is sharp but not exceeded. For a singleton, $\log m=\log(1/\pi_G)$, so minimal mass gives no extra room. Part (a): on $Y_G=T_1\le u$ we have $p_1\ge q\ge qR/m$, so a rejection needs $R=m$ and $p_1=q$, a null event; the second term is $\le\mathbb P(Y_G>b_G)=q\pi_G$.

## Failure

NOT fails: for a singleton the BY bound $(q/m)(1+\log m)$ equals $q\pi_G(1+\log(1/\pi_G))$, which is exactly the allowed order in (b).
