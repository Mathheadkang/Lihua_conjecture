---
type: candidate
title: Singleton Gaussian null test of the exogenous pivotal identity
status: failed
target_asset: gaussian_bh_two_sided_exact_pivotal_identity
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  NOT: fail
mode: refute
round: 1
slot: 2
direction: small_cases
statement_digest: 10fd42aac96d6f560ddc31272941b5f90f8a40eb9cbddd044801e18b7016e6b1
performed_by: unknown
created_at: '2026-11-06T20:02:43.032Z'
extension_version: 0.0.4
---

## Object

Take $N=1$, $\theta_1=0$, $\Sigma=(1)$, $q=0.05$, and $T_1=X\sim N(0,1)$. Put $p_1=2\overline\Phi(|X|)$ and apply ordinary BH at level $q$. The proposed contradiction would come from an empty residual vector or the $R=0$ event.

## Checks

### H1

Pass: $N=1$ is a positive finite integer, $0<q<1$, and $q<2\overline\Phi(1)$, so the displayed small-level notation is also admissible.

### H2

Pass: $\Sigma$ is positive semidefinite with unit diagonal, $\theta_1=0$, and the observation is exactly Gaussian.

### H3

Pass: $i=1$ is a two-sided true null and $p_1$ is exactly uniform on $(0,1)$.

### H4

Pass: ordinary BH uses its maximum qualifying rank. Its rank is $R=\mathbf1\{p_1\le q\}$, whereas the forced-zero rank is always $\rho_1=1$, with threshold $\tau_1=q$. The residual $Y_1$ is the sole vector in $\mathbb R^0$; it is deterministic and independent of $X$. Its covariance is the empty PSD matrix. Every permitted Borel threshold map is the constant $q$.

### NOT

Fail: $a(X;q)=\mathbf1\{p_1\le q\}/q$ has expectation $1$, so $\Delta_1=0$ and both sides of the FDR identity equal $q$. The pointwise identity holds also on $R=0$. Both branches are constant, have zero jumps, and $\Psi=1$. Repeating the single coordinate $M$ times makes the largest qualifying rank either $0$ or $M$, with rejection threshold $q$; every copy again has $\Delta=0$. Thus none of the asserted conclusions fails.

## Failure

NOT fails: the empty residual and zero-rejection cases satisfy the exact identity without an exceptional term.
