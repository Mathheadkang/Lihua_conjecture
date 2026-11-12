---
type: candidate
title: Antithetic Gaussian pair is excluded by positive definiteness
status: failed
target_asset: gaussian_bh_signed_label_halfline_stein_identity
checks:
  H1: pass
  H2: pass
  H3: fail
  H4: unknown
  H5: unknown
  H6: unknown
  H7: unknown
  NOT: unknown
mode: refute
round: 1
slot: 4
direction: known_counterexamples
statement_digest: d3fb61916137dfc085bea1f638521abd2a8ea4841b661d5f9f84d49785283ab4
performed_by: unknown
created_at: '2026-11-07T05:27:14.931Z'
extension_version: 0.0.4
---

## Object

Take $N=2$, $\theta=(0,0)$, and a standard normal scalar $W$. Set $Z=(W,-W)$ and
$$
\Sigma=\begin{pmatrix}1&-1\\-1&1\end{pmatrix},\qquad q=1/10.
$$
This is the exact antithetic Gaussian construction, a natural pathological dependence family to test against an unrestricted Gaussian statement.

## Checks

### H1

Pass: $N=2$ is finite and at least one.

### H2

Pass: $\theta=(0,0)$ belongs to $\mathbb R^2$.

### H3

Fail: the statement requires $\Sigma$ positive definite. The nonzero vector $v=(1,1)$ satisfies $v^{\mathsf T}\Sigma v=0$, so this covariance is singular and is not positive definite. Stop here.

### H4

Unknown: unit diagonal is not checked after the first failing hypothesis.

### H5

Unknown: the sampling-law hypothesis is not checked after the first failing hypothesis.

### H6

Unknown: the required level interval is not checked after the first failing hypothesis.

### H7

Unknown: the specified original labels and auxiliary record conventions are not checked after the first failing hypothesis.

### NOT

Unknown: no conclusion is evaluated after positive definiteness fails. In particular, this object gives no evidence against the finite positive-definite Stein identity or any bound on its remainder.

## Failure

H3 fails: exact antithetic dependence has a zero covariance eigenvalue and lies outside the stated positive-definite scope.
