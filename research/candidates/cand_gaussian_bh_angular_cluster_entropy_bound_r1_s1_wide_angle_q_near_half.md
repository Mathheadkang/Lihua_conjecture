---
type: candidate
title: >-
  Cosine exactly 1/2 with q near 1/2 (u near 0), partial loadings and zero
  loadings in the cluster
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

Fix $\kappa=1$ and $q=0.49$, so $u=\overline\Phi^{-1}(0.49)\approx0.02507$. Take $d=2$, one cluster $C_1$ with $v_1=e_1$, $\beta_1=2/\sqrt3\approx1.1547$. Members: nulls with $\theta_i=0$ and $a_i=r_i(\tfrac12e_1\pm\tfrac{\sqrt3}2e_2)$ for any $r_i\in(0,1]$ (cosine exactly $1/2$), plus nulls with $a_i=0$ (no condition imposed). Other nulls outside $I_*$ and alternatives arbitrary (e.g. alternatives loaded on $-e_1$ or on $\mp e_2$, chosen to maximize false rejections of $C_1$). $\pi_1=|C_1|/m$ arbitrary in $(0,1]$.

## Checks

### H1
Valid multifactor representation, endpoint $r_i\in\{0,1\}$ allowed. pass.

### H2
$q=0.49<1/2$. pass.

### H3
$\beta_1=1.1547\ge u=0.0251$; $v_1$ unit; $C_1\subseteq I_0$ nonempty. pass.

### H4
$\rho_i=1/2$ exactly for $r_i>0$. pass (equality case).

### H5
$\beta_1\sqrt{1-\rho_i^2}=\tfrac2{\sqrt3}\cdot\tfrac{\sqrt3}2=1=\kappa$. pass (equality case).

### NOT
fail. By the reduction recorded in the round record (Lei identity on $\{Z_{e_1}\le\beta_1\}$, trivial bound off it, $G_i\le1/\overline\Phi(Y)$ for $Y>u$, Lei's integrated bound for $Y\le u$), each member with $r_i>0$ contributes at most $\frac qm\big(\frac12+\frac{\gamma_iu}{\sqrt{2\pi}}+\log\frac q{\overline\Phi(\beta_1)}+J\big)$ with
$$
J=\int_{\beta_1}^\infty\frac{\phi(y)}{\overline\Phi(y)}\Phi\!\Big(\frac{\beta_1-y/2}{\sqrt3/2}\Big)dy\approx4.06\le A^*(1)\approx8.18,
$$
and $\log(q/\overline\Phi(\beta_1))\approx\log(0.49/0.1241)\approx1.373$. Each zero-loading member has $G_i\le1$, contribution at most $q/m$. Together with $\overline\Phi(\beta_1)\approx0.124$ the left side is below the right side once $A_1(1)\ge A^*(1)$. The wide angle $60^\circ$ is only admitted when $\beta_j\le2\kappa/\sqrt3$, so $q$ is bounded below and everything is $O_\kappa(1)\cdot q\pi_1$.

## Failure

NOT fails: the cosine-$1/2$ boundary forces $u\le\beta_j\le2\kappa/\sqrt3$, and the off-strip integral there is at most $A^*(\kappa)$; zero-loading members are bounded by $q/m$ each.
