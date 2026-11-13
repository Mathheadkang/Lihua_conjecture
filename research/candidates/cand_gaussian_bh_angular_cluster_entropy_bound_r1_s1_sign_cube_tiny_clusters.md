---
type: candidate
title: >-
  Sign-cube frame of many tiny clusters at angle kappa/beta_j with negative
  null-alternative correlations
status: failed
target_asset: gaussian_bh_angular_cluster_entropy_bound
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: fail
mode: refute
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: c0f4a35d70bb8c3321136accd04202b71bb70ae9a12fd0aaa5c3d48abe6e1b98
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T05:47:01.490Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Object

Priority family of idea_213cbf984362. Fix $\kappa=1$, $n\ge2$, $k\ge1$, $q\in(0,1/2)$. Take $d=n+1$; for each sign vector $\epsilon\in\{\pm1\}^n$ let $v_\epsilon=(\epsilon/\sqrt n,0)$, $J=2^n$. Cluster $C_\epsilon$ consists of $k$ nulls with $\theta_i=0$, $r_i=1$, $a_i=\rho_\epsilon v_\epsilon+\sigma_\epsilon w_i$ where $w_i\perp v_\epsilon$ is a unit vector (alternately $\pm e_{n+1}$), $\sigma_\epsilon=1/\beta_\epsilon$, $\rho_\epsilon=\sqrt{1-\sigma_\epsilon^2}$, $\beta_\epsilon=\overline\Phi^{-1}(q\pi_\epsilon)$, $\pi_\epsilon=k/m$. Alternatives: for each $\epsilon$, $k'$ alternatives with loading $-v_\epsilon$ (negative correlation with $C_\epsilon$, positive with $C_{-\epsilon}$) and large means. $m=2^n(k+k')$.

## Checks

### H1
Valid multifactor representation; nulls at $r_i=1$. pass.

### H2
$0<q<1/2$. pass.

### H3
Clusters disjoint and nonempty, $v_\epsilon$ unit, $\beta_\epsilon=\overline\Phi^{-1}(q\pi_\epsilon)\ge\overline\Phi^{-1}(q)=u$. pass.

### H4
$\rho_\epsilon=\sqrt{1-1/\beta_\epsilon^2}\ge1/2$ whenever $\beta_\epsilon\ge2/\sqrt3$, true for $q\le\overline\Phi(2/\sqrt3)$; take such $q$. pass.

### H5
$\beta_\epsilon\sigma_\epsilon=1=\kappa$. pass.

### NOT
fail. The right side for this partition is $\sum_\epsilon[q\pi_\epsilon(\tfrac32+A_1(1)+\log(1/\pi_\epsilon))+q\pi_\epsilon]=q\pi_*(\tfrac52+A_1(1)+\log(m/k))$, $\pi_*=2^nk/m$, with no $\gamma$ term. The per-cluster reduction (round record) applies to each cluster separately, whatever the alternatives do, because the Lei identity is per null and the off-strip event is per cluster: cluster $C_\epsilon$ contributes at most $\overline\Phi(\beta_\epsilon)+q\pi_\epsilon(\tfrac12+\log\frac{q}{\overline\Phi(\beta_\epsilon)}+A^*(1))$. Summing gives the right side with $A_1(1)=A^*(1)$. Negative null-alternative correlations change $R_i$ but not the bound $\mathbb E[F_{i,Z}(qR_i/m)/(qR_i/m)\mid Z]\le G_i$. Many tiny clusters only enlarge the $\log(1/\pi_\epsilon)$ terms; they cannot shrink the right side below the sum of per-cluster bounds.

## Failure

NOT fails: the bound decomposes cluster by cluster through per-null Lei bounds, so the sign-cube arrangement and the alternatives' signs never couple clusters; each cluster's off-strip excess is at most $A^*(\kappa)q\pi_\epsilon$.
