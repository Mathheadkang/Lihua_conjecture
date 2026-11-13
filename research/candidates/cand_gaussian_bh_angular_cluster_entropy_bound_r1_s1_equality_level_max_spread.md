---
type: candidate
title: >-
  Unit-loading nulls at the maximal admitted angle kappa/u with the equality
  level beta=u, q to 0
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

Fix $\kappa=1$. For each $q\in(0,\overline\Phi(2/\sqrt3)]$ put $u=\overline\Phi^{-1}(q)\ge 2/\sqrt3$, $\sigma=1/u$, $\rho=\sqrt{1-1/u^2}$. Take $d=2$, $m=2n$, nulls $i=1,\ldots,n$ with $\theta_i=0$ and
$$
a_i=\rho e_1+(-1)^i\sigma e_2,\qquad r_i=1,\ \gamma_i=0,
$$
and alternatives $i=n+1,\ldots,2n$ with arbitrary $\theta_i>0$ and arbitrary loadings (any choice, including loadings $-e_1$, i.e. negative null-alternative correlation). Take $I_*=I_0$, $J=1$, $C_1=I_0$, $v_1=e_1$, $\beta_1=u$ (equality in $\beta_j\ge u$), so $\pi_1=1/2$.

## Checks

### H1
Multifactor representation with $\|a_i\|=1$ for nulls (endpoint loading, conditionally deterministic coordinate), $\|a_i\|\le1$ for alternatives. pass.

### H2
$0<q\le\overline\Phi(2/\sqrt3)<1/2$. pass.

### H3
$\kappa=1\ge0$; $C_1=I_0\ne\varnothing$; $v_1$ unit; $\beta_1=u$. pass (equality case).

### H4
$\rho_i=a_i^{\mathsf T}e_1=\rho=\sqrt{1-1/u^2}\ge1/2$ since $u\ge2/\sqrt3$. pass.

### H5
$\beta_1\sqrt{1-\rho^2}=u\cdot(1/u)=1=\kappa$. pass (equality case).

### NOT
fail. Reduction valid for every object satisfying H1-H5: on $\{Z_{v_j}>\beta_j\}$ the cluster fraction $|\mathcal R_q\cap C_j|/(R\vee1)\le1$ contributes at most $\overline\Phi(\beta_j)$; on $\{Z_{v_j}\le\beta_j\}$ the Lei leave-one-out identity ([lei2026_conditional_fdp_bound]) gives per null $i\in C_j$ at most $\frac qm\mathbb E[G_i;Z_{v_j}\le\beta_j]$, $G_i=\sup_{0<t\le q}F_{i,Z}(t)/t$. With $Y=a_i^{\mathsf T}Z/r_i$, $G_i\le G^{0}_{r_i}(r_iY)$ (mean $0$ dominates $\theta_i\le0$), Lei's integrated bound gives $\mathbb E[G_i;Y\le u]\le\frac12+\gamma_iu/\sqrt{2\pi}$, and for $Y>u$ one has $G_i\le1/\overline\Phi(Y)$ because $\overline\Phi(x)=\mathbb P(rY'+s\varepsilon\ge x)\ge\overline\Phi(Y)\overline\Phi((x-rY)/s)$. Since $Z_{v_j}\mid Y=y\sim\mathcal N(\rho y,1-\rho^2)$ and $\phi/\overline\Phi\le y+1$,
$$
\mathbb E[G_i;Y>u,Z_{v_j}\le\beta_j]\le\log\frac q{\overline\Phi(\beta_j)}+\int_{\beta_j}^\infty\frac{\phi(y)}{\overline\Phi(y)}\Phi\!\Big(\frac{\beta_j-\rho y}{\sigma}\Big)dy,
$$
and with $\beta_j(1-\rho)/\sigma\le\beta_j\sigma\le\kappa$, $\rho\ge1/2$ the last integral is at most $A^*(\kappa)=2(\kappa+1)(\kappa\Phi(\kappa)+\phi(\kappa))+2((\kappa^2+1)\Phi(\kappa)+\kappa\phi(\kappa))$, finite and nondecreasing ($A^*(1)\approx8.18$). So the statement holds with $A_1=A^*$ and no object refutes it.

For this family explicitly: $\mathrm{LHS}\le q+\frac q2\big(\frac12+J(u)\big)$ with $J(u)=\int_u^\infty\frac{\phi}{\overline\Phi}(y)\Phi((u-\rho y)u)\,dy$. Numerically $J=1.020,\,0.817,\,0.750,\,0.722,\,0.710$ at $q=10^{-2},10^{-4},10^{-8},10^{-16},10^{-30}$, converging (substitute $y=u+t/u$) to $\int_0^\infty\Phi(\tfrac12-t)\,dt=\tfrac12\Phi(\tfrac12)+\phi(\tfrac12)\approx0.698$. The excess over $q+\frac34 q$ stays $O(q)$ uniformly in $q$, so no fixed $A_1(1)$ is beaten.

## Failure

NOT fails: the off-strip integral for spread exactly $\kappa/\beta_j$ at the level $\beta_j=u$ stays bounded (limit $\approx0.698$ for $\kappa=1$), so the gap is absorbed by $A_1(\kappa)$.
