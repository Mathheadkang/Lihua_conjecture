---
type: candidate
title: >-
  Equicorrelated nulls at the boundary mean, rho in [0,1] (identity and rank-one
  endpoints)
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

A family indexed by the level $q\to0$. For each $q$ take any integer $N=N(q)\geq1$, any $\rho=\rho(q)\in[0,1]$, $\theta=0\in\mathbb R^N$ (every coordinate a true null sitting at the boundary mean $\theta_i=0$, so $B_q=\{1,\ldots,N\}$), and the equicorrelated matrix $\Sigma=(1-\rho)I_N+\rho\mathbf 1\mathbf 1^{\mathsf T}$. The endpoints $\rho=0$ (independence) and $\rho=1$ (rank one, $Z_i=g$ for all $i$) are the degenerate cases this candidate is meant to test.

## Checks

### H1
$N\geq1$ is an integer. Pass.

### H2
$\theta=0\in\mathbb R^N$. Pass.

### H3
$\Sigma$ is symmetric, has unit diagonal, and is positive semidefinite (eigenvalues $1-\rho\geq0$ and $1-\rho+N\rho\geq0$); for $\rho=1$ it is singular, which is admitted. Pass.

### H4
$q$ ranges over $(0,q_{\mathrm T}]$ for any proposed $q_{\mathrm T}$ (the family lets $q\to0$). Pass.

### NOT
Fails. All covariances are $\geq0$, so $T$ is associated (Pitt's theorem for Gaussian vectors with nonnegative covariances) and the one-sided p-values $p_i=\overline\Phi(T_i)$ are decreasing in $T$, hence PRDS on $B_q$; each null p-value satisfies $\mathbb P(p_i\leq t)=t$. The Benjamini-Yekutieli PRDS bound gives $\mathbb E[V_{B_q}/(R\vee1)]\leq q|B_q|/N=q$. Explicitly at $\rho=1$: all p-values equal $\overline\Phi(g)$, so $\widehat k_q\in\{0,N\}$ and BH rejects everything iff $g\geq U$, giving the left side exactly $\mathbb P(g\geq U)=q$. At $\rho=0$ the left side is exactly $q$ (independent uniform nulls, all nulls). The right side is at least $A_{\mathrm T}q$, and $\Lambda_{B_q}\geq|B_q|/N=1$ (take $w=0$), so the right side is at least $A_{\mathrm T}q(1+\min\{1/q,1\})=2A_{\mathrm T}q$. The ratio left/right is at most $1/(2A_{\mathrm T})$ along the whole family.

## Failure

NOT fails: nonnegative covariances make the p-values PRDS, so the left side is at most $q|B_q|/N\leq q$, below the $A_{\mathrm T}q$ floor of the right side.
