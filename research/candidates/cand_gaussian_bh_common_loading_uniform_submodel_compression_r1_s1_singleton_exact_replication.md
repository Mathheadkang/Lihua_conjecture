---
type: candidate
title: Singleton null with exact replication
status: failed
target_asset: gaussian_bh_common_loading_uniform_submodel_compression
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  H7: pass
  NOT: fail
mode: refute
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: 559f931c8cf870c13d2afe6f41bae6c492b9b6e20edb09e35b2275ac15e3ed5d
performed_by: unknown
created_at: '2026-11-09T05:14:18.431Z'
extension_version: 0.0.4
---

## Object

For every positive integer $m$, take $q=1/4$, $\sigma=1/2$, $N=d=1$, $v_1=1$, $\theta_1=0$, and $\ell_1=1$. Let $G,Z$ be independent standard normals and set $T_1=(\sqrt3/2)G+Z/2$. All sampled indices equal $1$.

## Checks

### H1

Pass: $q=1/4\in(0,1/2)$.

### H2

Pass: $\sigma=1/2\in(0,1)$.

### H3

Pass: $N=d=1$ are positive integers.

### H4

Pass: $v_1=1$ is deterministic and has norm one in $\mathbb R$.

### H5

Pass: the mean and tag are deterministic, and $\ell_1=1$ has $\theta_1=0\le0$.

### H6

Pass: the displayed score uses precisely the prescribed Gaussian representation with independent $G,Z$.

### H7

Pass: the constant indices $I_j=1$ are iid uniform on $[1]$ and independent of the Gaussian variables; the $m$ scores are exact copies and ordinary BH uses its largest non-strict rank.

### NOT

Fail. Write $p=S(T_1)$ and $J=\mathbf1_{\{p\le q\}}$. The single-test procedure has $D_N=\rho_N=J$. With $m$ identical p-values, rank $m$ qualifies exactly when $p\le q$; when $p>q$, no rank qualifies because $qk/m\le q$. Therefore $D_m=\rho_m=J$ for every realization and every $m$. This includes the equality $p=q$ and terminal normalized rank one. The approximation error is identically zero, so this family cannot violate the asserted uniform approximation.

## Failure

NOT fails: exact replication of a singleton preserves both FDP and normalized rank pointwise.
