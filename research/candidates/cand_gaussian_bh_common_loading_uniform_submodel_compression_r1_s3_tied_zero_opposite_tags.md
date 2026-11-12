---
type: candidate
title: Exact tied zero scores with opposite tags at the analytic boundary
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
slot: 3
direction: drop_hypothesis
statement_digest: 559f931c8cf870c13d2afe6f41bae6c492b9b6e20edb09e35b2275ac15e3ed5d
performed_by: unknown
created_at: '2026-11-09T05:14:18.431Z'
extension_version: 0.0.4
---

## Object

Set $q=1/4$, $\sigma=1/2$, $N=2$, $d=1$, $v_1=v_2=1$, $\theta_1=\theta_2=0$, $\ell_1=1$, and $\ell_2=0$. For every $m\ge1$ sample indices independently and uniformly from $\{1,2\}$, independently of independent standard normal variables $G,Z$. Both original scores and every sampled score equal
$$
T=\frac{\sqrt3}{2}G+\frac12 Z.
$$
This probes the alternative-tagged-zero boundary, a singular residual Gram matrix, exact repetitions, and terminal normalized rank one simultaneously.

## Checks

### H1

Pass: $q=1/4\in(0,1/2)$ and $\sigma=1/2\in(0,1)$ are fixed independently of $m$.

### H2

Pass: $N=2,d=1$ are positive integers and both deterministic directions have norm one.

### H3

Pass: the means are deterministic real numbers and the tags lie in $\{0,1\}$; $\ell_1=1$ has $\theta_1=0\le0$, while $\ell_2=0$ has $\theta_2=0\ge0$. The second point is explicitly permitted in the analytic completion.

### H4

Pass: independent standard Gaussian $G,Z$ give exactly the required common-loading scores. Their residual Gram matrix has all entries one and is singular, as permitted.

### H5

Pass: the indices are iid uniform and independent of $(G,Z)$. Every sampled score is the exact original score, with no added noise.

### H6

Pass: use ordinary BH at the stated level with the largest non-strict crossing and inherited tags. Since all p-values equal $p=S(T)$, all tests are rejected exactly on $\{p\le q\}$; otherwise none are rejected. This follows because $p\le qk/n$ for any $k\le n$ implies $p\le q$, and conversely $p\le q$ qualifies $k=n$.

### H7

Pass: define $D_N,D_m$ by the inherited-tag FDP and $\rho_N=R_N/2$, $\rho_m=R_m/m$, including zero rejections and all ties, exactly as prescribed.

### NOT

Fail: put $K=\sum_{j=1}^m\mathbf1_{\{I_j=1\}}\sim\operatorname{Bin}(m,1/2)$. The common score is standard normal, so $p$ is uniform and independent of $K$. Consequently
$$
\rho_N=\rho_m=\mathbf1_{\{p\le q\}},\qquad
D_N=\tfrac12\mathbf1_{\{p\le q\}},\qquad
D_m=\frac Km\mathbf1_{\{p\le q\}}.
$$
Thus the proposed approximation error for this family is exactly
$$
\mathbb E[|D_m-D_N|+|\rho_m-\rho_N|]
=\frac14\,2^{-m}\sum_{k=0}^m\binom mk\left|\frac km-\frac12\right|
\le\frac14\sqrt{\frac1{4m}}=\frac1{8\sqrt m}\longrightarrow0.
$$
The inequality is Cauchy--Schwarz and $\operatorname{Var}(K/m)=1/(4m)$. Every positive rank is one, so this object has no positive microscopic ranks. The rank transfer also holds directly: if the identical-score law qualifies at rank $r$, it has count one there, and a positive common shift only increases that count. The same calculation with arbitrary $q$ gives error at most $q/(2\sqrt m)$, uniformly for $q$ in any compact subset of $(0,1/2)$. This family therefore supplies no violation.

## Failure

NOT fails: exact copies preserve the rejection event and normalized rank, while the sampled tag proportion has error at most $1/(8\sqrt m)$.
