---
type: candidate
title: >-
  One boundary null with antithetic rank-one alternatives (overshoot-zero BH
  crossing)
status: failed
target_asset: gaussian_bh_near_boundary_frozen_ray_transfer
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
statement_digest: be073e791d4239baa7b5f7c3e9a5802f0f6c644848af48ae7b3362b87b76b57d
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-12T08:00:46.953Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Object

A family indexed by $q\to0$. For each $q$ take an integer $n=n(q)\geq2$ and a constant $c=c(q)>0$. Put $N=n$, $\theta_1=0$, $\theta_j=c$ for $2\leq j\leq n$, and the rank-one singular covariance $\Sigma=ss^{\mathsf T}$ with $s=(1,-1,\ldots,-1)$. Thus $Z_1=g$, $Z_j=-g$ for $j\geq2$, $g\sim\mathcal N(0,1)$; $T_1=g$ and $T_j=c-g$. Here $B_q=\{1\}$ (a single null at the boundary mean $0$), and the alternatives fall as the null rises, so the BH cutoff tracks the null value: this is the degenerate configuration in which the null is rejected with small overshoot over the cutoff $x^*$, the case where the pointwise relaxation loses the hazard factor.

## Checks

### H1
$N=n\geq2$ is an integer. Pass.

### H2
$\theta\in\mathbb R^N$. Pass.

### H3
$\Sigma=ss^{\mathsf T}$ is symmetric, positive semidefinite, of rank one, with $\Sigma_{ii}=s_i^2=1$. Pass.

### H4
$q\in(0,q_{\mathrm T}]$ for any proposed $q_{\mathrm T}$; the family lets $q\to0$. Pass.

### NOT
Fails. For any single null $i$ with super-uniform $p_i$ (here $\mathbb P(p_1\leq t)=t$), write $F(j)=\mathbb P(p_i\leq qj/N)\leq qj/N$. Since $R=\widehat k_q$ and $i\in\mathcal R_q$ forces $p_i\leq qR/N$,
$$
\mathbb E\!\left[\frac{\mathbf 1\{i\in\mathcal R_q\}}{R\vee1}\right]\leq\sum_{j=1}^N\frac{F(j)-F(j-1)}{j}=\frac{F(N)}{N}+\sum_{j=1}^{N-1}F(j)\Bigl(\frac1j-\frac1{j+1}\Bigr)\leq\frac qN H_N,
$$
with $H_N=\sum_{j\leq N}1/j$ (the first inequality uses that on $\{R=k\}$ the indicator $\mathbf 1\{p_i\leq qk/N\}/k$ is at most $\sum_{j\leq k}\mathbf 1\{p_i\in(q(j-1)/N,qj/N]\}/j$). Hence the left side is at most $qH_n/n\leq q$, whatever $c$ is. The right side is at least $A_{\mathrm T}q$. The ratio is at most $H_n/(nA_{\mathrm T})\leq1/A_{\mathrm T}$, and tends to $0$ if $n\to\infty$. The zero-overshoot geometry cannot help: with $|B_q|=1$ the $A_{\mathrm T}q$ floor already dominates.

## Failure

NOT fails: a single near-boundary null contributes at most $(q/N)H_N\leq q$ by the Benjamini-Yekutieli summation, below the $A_{\mathrm T}q$ floor.
