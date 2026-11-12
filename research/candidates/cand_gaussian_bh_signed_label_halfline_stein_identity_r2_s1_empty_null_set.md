---
type: candidate
title: Empty original null set at the largest admissible level
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
round: 2
slot: 1
direction: boundary_degenerate
statement_digest: d3fb61916137dfc085bea1f638521abd2a8ea4841b661d5f9f84d49785283ab4
performed_by: unknown
created_at: '2026-11-07T05:29:57.144Z'
extension_version: 0.0.4
---

## Object

Take $N=2$, $\theta=(1,1)$, $\Sigma=I_2$, and $q=S(1)$. Thus $Z_1,Z_2$ are independent $N(1,1)$ scores. Use the specified one-sided p-values and ordinary BH, retaining the original null labels throughout translation.

This tests the empty-null boundary, rather than the already checked one-test true-null family.

## Checks

### H1

$N=2$ is a finite positive integer.

### H2

$\theta=(1,1)$ is an allowed vector of real means.

### H3

$\Sigma=I_2$ has unit diagonal and eigenvalues $1,1$, so it is positive definite.

### H4

$q=S(1)>0$ attains the upper endpoint of the stated interval. Here $U=u_2=1$ and $u_1=S^{-1}(q/2)>1$.

### H5

The p-values are $p_j=S(Z_j)$ and $I_0=\{j:\theta_j\le0\}=\varnothing$, as required. The auxiliary path retains this empty original set. Ordinary BH with ordered scores $z_{\pi(1)}\ge z_{\pi(2)}$ has translated rank $2$ precisely when $z_{\pi(2)}-u_2\ge t$, rank $1$ when this fails but $z_{\pi(1)}-u_1\ge t$, and rank $0$ otherwise. This is the stated maximum-of-qualifying-ranks rule. Its only possible complete chains are $0\to1\to2$ or $0\to2$, with equality of the two contact times coalescing to the latter. Score ties have $\tau_1<\tau_2$ and hence the latter chain as well.

### NOT

The conclusion does not fail. For every outcome the rejection set contains zero original nulls, so $\operatorname{FDP}=\operatorname{FDR}=0$. Every sum over $j\in I_0$ is empty, including both terms of (SF) and $D_<$, and the final inequality is $0\le0$. Every assertion about a fixed null label, its coefficients, its field, or its baseline is vacuous. The scalar formulas for $H_j$ are not instantiated because there is no $j\in I_0$. The preceding direct two-rank calculation checks the remaining deterministic path assertion, including contact and score ties. Thus this model produces no violation.

## Failure

NOT fails: an empty original null set makes the exact signed identities and all null-label budgets zero or vacuous, including the final inequality.
