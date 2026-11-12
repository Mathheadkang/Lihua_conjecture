---
type: candidate
title: Singular duplicate Gaussian scores at the covariance boundary
status: failed
target_asset: gaussian_bh_signed_label_halfline_stein_identity
checks:
  H1: pass
  H2: pass
  H3: fail
  H4: unknown
  H5: unknown
  H6: unknown
  NOT: unknown
mode: refute
round: 1
slot: 3
direction: drop_hypothesis
statement_digest: d3fb61916137dfc085bea1f638521abd2a8ea4841b661d5f9f84d49785283ab4
performed_by: unknown
created_at: '2026-11-07T05:27:14.931Z'
extension_version: 0.0.4
---

## Object

Take $N=2$, $\theta=(0,0)$, $q=S(1)$, and
$$
\Sigma=\begin{pmatrix}1&1\\1&1\end{pmatrix},\qquad Z=(G,G),\quad G\sim N(0,1).
$$
This is the exact duplicate-score limit of $\Sigma_\varepsilon=\left(\begin{smallmatrix}1&1-\varepsilon\\1-\varepsilon&1\end{smallmatrix}\right)$ for $0<\varepsilon<1$, whose eigenvalues are $\varepsilon$ and $2-\varepsilon$. The proposed boundary object tests whether a permanent score-tie Gaussian law lies in the extracted lemma's scope.

## Checks

### H1

Pass: $N=2$ is a finite positive integer.

### H2

Pass: $\theta=(0,0)\in\mathbb R^2$.

### H3

Fail: although $\Sigma$ is symmetric and has unit diagonal, for $v=(1,-1)$ one has $v^{\mathsf T}\Sigma v=0$. Its eigenvalues are $0$ and $2$, so it is not positive definite.

### H4

Unknown: not checked after the first failing hypothesis.

### H5

Unknown: not checked after the first failing hypothesis.

### H6

Unknown: not checked after the first failing hypothesis.

### NOT

Unknown: the conclusion is not tested after the failed positive-definiteness hypothesis. This object gives neither a counterexample nor a singular-covariance extension of the statement.

## Failure

H3 fails: exact duplicated Gaussian scores have singular covariance, outside the lemma's positive-definite scope.
