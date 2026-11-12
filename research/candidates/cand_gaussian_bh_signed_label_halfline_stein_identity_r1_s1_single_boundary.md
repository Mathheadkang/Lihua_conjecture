---
type: candidate
title: Single null at the largest allowed testing level
status: failed
target_asset: gaussian_bh_signed_label_halfline_stein_identity
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
statement_digest: d3fb61916137dfc085bea1f638521abd2a8ea4841b661d5f9f84d49785283ab4
performed_by: unknown
created_at: '2026-11-07T05:27:14.931Z'
extension_version: 0.0.4
---

## Object

Take $N=1$, $\theta_1=0$, $\Sigma=(1)$, and $q=S(1)$. Thus $U=u_1=1$, $Z_1\sim N(0,1)$, and the fixed original true-null set is $I_0=\{1\}$. In addition to the sampling law, inspect its deterministic threshold score $z_1=1$.

## Checks

### H1

Pass: $N=1$ is a finite positive integer.

### H2

Pass: $\theta_1=0$ is real and the original null label is retained along the auxiliary translation path.

### H3

Pass: $\Sigma=(1)$ is positive definite with unit diagonal, and the stated Gaussian law has that covariance.

### H4

Pass: $0<q=S(1)$ is the endpoint of the permitted interval, so $U=u_1=1$.

### H5

Pass: use $p_1=S(Z_1)$ and ordinary BH at level $q$, hence rejection is exactly $\{Z_1\ge1\}$.

### NOT

Fail: the full record chain has the sole edge $0\to1$, coefficient $c_{1e}=1$, $\tau_e=z_1-1$, $a_{1e}=1$, and $d_{11}=0$. Its deterministic telescoping identity is $\mathbf1\{z_1\ge1\}=\mathbf1\{\tau_e\ge0\}$, including equality at $z_1=1$. The signed baseline is exactly $B_1=S(1)=q$, so every inequality in (B) is equality. In (SF) the derivative correction vanishes because $d_{11}=0$, and both sides equal $\operatorname{FDR}=\mathbb P(Z_1\ge1)=q$. The above-threshold correction and $D_<$ are both zero, and the final inequality is $q\le5q$. The field is the ordinary continuous half-line potential $H_1(z_1,1)$; there are no record or score-order interfaces. Its two formulas match at $z_1=1$, its weak derivative has no surface mass, and its derivative away from that point follows directly by differentiating the displayed scalar formulas. Thus this boundary model does not violate the conclusion.

## Failure

NOT fails: at $N=1$ and $q=S(1)$ the path identity and Stein identity are exact and the baseline budget is saturated.
