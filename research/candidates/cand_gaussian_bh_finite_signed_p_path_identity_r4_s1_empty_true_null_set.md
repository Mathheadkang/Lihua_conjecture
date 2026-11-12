---
type: candidate
title: Empty true-null set at the zero-FDR boundary
status: failed
target_asset: gaussian_bh_finite_signed_p_path_identity
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  NOT: fail
mode: refute
round: 4
slot: 1
direction: boundary_degenerate
statement_digest: d7a8a4f0b24ea902729e5f1f7788367f78c722f470f62ba2b0bf55c676594eec
performed_by: unknown
created_at: '2026-11-09T20:58:25.271Z'
extension_version: 0.0.4
---

## Object

Take $N=1$, $\theta=(1)$, $\Sigma=(1)$, and $q=1/4$. Let $Z\sim\mathcal N(0,1)$, $T=1+Z$, and $p_1=\overline\Phi(T)$. Use the original one-sided true-null convention and ordinary non-strict BH. This tests the empty-index-set boundary, rather than a negative-null singleton: $I_0=\varnothing$.

## Checks

### H1

Pass. $N=1$ is finite and positive.

### H2

Pass. $\theta=(1)\in\mathbb R^1$.

### H3

Pass. $\Sigma=(1)$ is symmetric positive semidefinite with unit diagonal.

### H4

Pass. $q=1/4$ satisfies $0<q<1/2$.

### H5

Pass. $T=\theta+Z$ has exactly the prescribed Gaussian law.

### H6

Pass. The original one-sided convention gives $I_0=\{i:\theta_i\leq0\}=\varnothing$. Ordinary BH rejects exactly when $p_1\leq1/4$. No coordinate or original label is dropped from that procedure.

### NOT

Fail. Every statement indexed by $i\in I_0$ is vacuous. There is no residual path, event set, jump sum, or Stieltjes integral to construct for a true-null label. For every realization, $V=|\mathcal R_q\cap I_0|=0$, so $F=0$, while $\pi_0=0$ and $\sum_{i\in I_0}\mathbb E B_i=0$. The asserted final bound is the equality $0\leq0$. Thus the empty true-null set produces no violation of any conclusion.

## Failure

NOT is the first failing check: all per-null assertions are vacuous and the original FDR and both terms of its upper bound are exactly zero.
