---
type: candidate
title: Coincident zero-mean scores with different analytic tags
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

For every positive integer $m$, take $q=1/4$, $\sigma=1/2$, $N=2$, $d=1$, $v_1=v_2=1$, $\theta_1=\theta_2=0$, and $(\ell_1,\ell_2)=(1,0)$. The second coordinate uses the expressly admitted alternative-tagged zero. Let $G,Z$ be independent standard normals and put $T_1=T_2=(\sqrt3/2)G+Z/2$. Sample the indices iid uniform on $\{1,2\}$ independently of $G,Z$.

## Checks

### H1

Pass: $q=1/4\in(0,1/2)$.

### H2

Pass: $\sigma=1/2\in(0,1)$.

### H3

Pass: $N=2$ and $d=1$ are positive integers.

### H4

Pass: both deterministic residual directions have norm one. Their residual Gram matrix is singular, which the statement allows.

### H5

Pass: the true-tagged mean is $0\le0$, and the alternative-tagged mean is $0\ge0$. Both tags are within the analytic completion of the target statement.

### H6

Pass: the shared displayed score is the required Gaussian representation with independent $G,Z$, giving marginal variance one.

### H7

Pass: index sampling is iid uniform and independent of the Gaussian variables. Repeated scores are exact copies, with original tags retained; ordinary largest-rank BH includes all ties.

### NOT

Fail. Let $p=S(T_1)$, $J=\mathbf1_{\{p\le q\}}$, and $K=\sum_{j=1}^m\mathbf1_{\{I_j=1\}}$. All p-values coincide, so $\rho_N=\rho_m=J$ pointwise, including equality and the zero/one rank endpoints. The tagged FDPs are $D_N=J/2$ and $D_m=JK/m$. Here $K\sim\operatorname{Binomial}(m,1/2)$ independently of $J$, while $T_1$ is standard normal and $\mathbb EJ=q$. Hence
$$
\mathbb E\bigl[|D_m-D_N|+|\rho_m-\rho_N|\bigr]
=q\,\mathbb E|K/m-1/2|
\le q\sqrt{\operatorname{Var}(K/m)}
=\frac{q}{2\sqrt m}\longrightarrow0.
$$
The same calculation applies for every $q\in(0,1/2)$, and the bound is uniform on compact subsets. Thus the most singular coincident-score atom with mixed admissible tags does not produce a failure.

## Failure

NOT fails: normalized ranks agree pointwise and the only FDP discrepancy is a binomial tag-frequency error of order $m^{-1/2}$.
