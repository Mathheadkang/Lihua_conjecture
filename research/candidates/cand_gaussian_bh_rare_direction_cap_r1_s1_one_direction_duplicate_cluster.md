---
type: candidate
title: >-
  One-direction duplicate rare cluster with arbitrary alternatives, including
  the harmonic one-null staircase
status: failed
target_asset: gaussian_bh_rare_direction_cap
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
statement_digest: 9afb59906629533a14999f6caaf3ad9532b3838891de891a2f9d6b5299480a12
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T06:03:41.507Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Object

Degenerate dimension $d=1$. Fix $0<q\le q_2$, integers $n\ge1$ and $L\ge1$, $m=n+L$. True nulls: $n$ exact duplicates $T_i=Z$ ($\theta_i=0$, $a_i=1$, $r_i=1$, no residual), $i\in S$. Alternatives: $L$ coordinates with arbitrary means $\theta_j>0$ and arbitrary loadings $a_j\in[-1,1]$ (with independent residuals). The special case $n=1$, $L=N-1$, $a_j=-1$, $\theta_j=z_j+z_{j+1}$, $z_j=\overline\Phi^{-1}(qj/N)$ is the one-null harmonic staircase of idea_75d71c7756b4, whose exact FDR is $(q/N)H_N$. Put $\mu=n/m$ and take $\mu<q^{C_2}$.

## Checks

### H1

Valid Gaussian multifactor representation: every loading has norm at most one; nulls have $r_i=1$ and zero residual.

### H2

One-sided p-values $p_i=\overline\Phi(T_i)$; $I_0=S$ because all alternatives have $\theta_j>0$.

### H3

BH at level $q\le q_2$, largest qualifying rank, non-strict comparisons. Nothing to check.

### H4

Every $i\in S$ has $w_i=1$; its neighbourhood is $S$ for every value of $\kappa_2$ (there are no other nulls), so $\mu_i=n/m=\mu<q^{C_2}$ and $I_{\mathrm{rare}}=S$. Boundary: at $\mu=q^{C_2}$ exactly the strict inequality fails and $I_{\mathrm{rare}}=\varnothing$; for $m\le q^{-C_2}$ every null has $\mu_i\ge1/m\ge q^{C_2}$, so no rare null exists in any model with $m\le q^{-C_2}$.

### NOT

All members of $S$ share the p-value $p=\overline\Phi(Z)$, uniform on $(0,1)$. BH has $R=\widehat k_q$ exactly (if more than $\widehat k_q$ p-values were below $q\widehat k_q/m$, a larger rank would qualify). On rejection of $S$, $R\ge n$ and $p\le qR/m$, so $R\ge\max(n,\lceil mp/q\rceil)$. Hence
$$
\frac{|\mathcal R_q\cap S|}{R\vee1}\le n\Bigl[\frac{\mathbf 1\{p\le qn/m\}}{n}+\sum_{k=n+1}^{m}\frac{\mathbf 1\{q(k-1)/m<p\le qk/m\}}{k}\Bigr],
$$
and taking expectations,
$$
\mathbb E\frac{|\mathcal R_q\cap I_{\mathrm{rare}}|}{R\vee1}\le q\mu\Bigl(1+\sum_{k=n+1}^m\frac1k\Bigr)\le q\mu\bigl(1+\log(1/\mu)\bigr)\le q,
$$
since $x(1+\log(1/x))\le1$ on $(0,1]$. With $\mu<q^{C_2}$ the bound is in fact at most $q^{1+C_2}(1+C_2\log(1/q))$. The same value also follows from the approved [angular-cluster entropy bound](../assets/gaussian_bh_angular_cluster_entropy_bound.md) with $J=1$, $\kappa=0$, $\beta_1=\overline\Phi^{-1}(q\mu)$. For the harmonic staircase ($n=1$): $(q/N)H_N\le q$. The conclusion holds with any $A_2\ge1$.

## Failure

NOT fails: a single exact-duplicate rare direction contributes at most $q\mu(1+\log(1/\mu))\le q$, and rarity makes the harmonic gain negligible.
