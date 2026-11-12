---
type: candidate
title: At most three centered Gaussian coordinates with arbitrary Gram vectors
status: failed
target_asset: gaussian_simes_one_sided_uniform_linear_bound
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: fail
mode: refute
round: 1
slot: 2
direction: small_cases
statement_digest: 15d52b3eb80faa8138461b0390ec347f4eb6a5465aae5494d0e050fea1bae614
performed_by: unknown
created_at: '2026-11-09T04:15:08.641Z'
extension_version: 0.0.4
---

## Object

For each $0<q<1/2$, choose any $N\in\{1,2,3\}$ and any $N\times3$ real matrix $A$ whose rows have Euclidean norm one. Put $\Sigma=AA^{\mathsf T}$, take $Z\sim\mathcal N_3(0,I_3)$, and set $T=AZ$ and $p_i=\overline\Phi(T_i)$. All these parameters may depend on $q$. This includes every correlation matrix of size at most three, by Gram factorization and zero-padding.

## Checks

### H1

Pass: $N$ is a positive integer, here at most three.

### H2

Pass: $\Sigma=AA^{\mathsf T}$ is symmetric positive semidefinite and $\Sigma_{ii}=\|A_{i\cdot}\|_2^2=1$.

### H3

Pass: $0<q<1/2$; the family therefore permits levels arbitrarily close to zero and restriction to any proposed sufficiently small $q_0$.

### H4

Pass: $T=AZ$ is exactly jointly Gaussian with mean zero and covariance $\Sigma$, including singular cases.

### H5

Pass: use $p_i=\overline\Phi(T_i)$ and the non-strict Simes event $E_q=\{\exists k:p_{(k)}\le qk/N\}$, including multiplicities. Each $p_i$ is marginally uniform on $(0,1)$.

### NOT

Fail: there is a constant uniform over this entire family. Define $f_q(t)=1/k$ on $((k-1)q/N,kq/N]$ for $k=1,\ldots,N$, and zero on $(q,1]$; its value at zero is immaterial. If rank $r$ crosses, at least $r$ p-values are at most $qr/N$, and each has $f_q(p_i)\ge1/r$. Hence $\mathbf1_{E_q}\le\sum_i f_q(p_i)$ almost surely. Marginal uniformity, with no dependence restriction, gives
$$
\mathbb P(E_q)\le N\sum_{k=1}^N\frac{q/N}{k}=qH_N\le\frac{11}{6}q.
$$
Thus no choice or variation of Gram vectors, correlations, or singularities at these sizes can make the ratio unbounded. A finite excess above $q$ would not refute the existential universal constant.

## Failure

NOT fails: all sizes $N\le3$ obey the uniform bound $\mathbb P(E_q)/q\le11/6$.
