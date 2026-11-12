---
type: candidate
title: Arbitrarily many rank-one Gaussian sign duplicates
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

For each $0<q<1/2$, choose any positive integer $N$ and signs $s_1,\ldots,s_N\in\{-1,1\}$. Set $\Sigma=ss^{\mathsf T}$, take $Z\sim\mathcal N(0,1)$, and set $T_i=s_iZ$, $p_i=\overline\Phi(s_iZ)$. Write $m=\#\{i:s_i=1\}$ and $n=N-m$. Both block sizes and $N$ may vary arbitrarily with $q$. This covers every unit-diagonal rank-one covariance, up to the choice of the common Gaussian sign.

## Checks

### H1

Pass: $N$ is any positive integer.

### H2

Pass: $ss^{\mathsf T}$ is symmetric positive semidefinite with diagonal entries one; its rank is one.

### H3

Pass: the family is defined at every $0<q<1/2$, hence at arbitrarily small testing levels.

### H4

Pass: $T=sZ$ is centered jointly Gaussian with covariance $ss^{\mathsf T}$.

### H5

Pass: the stated one-sided p-values are used with the ordinary non-strict Simes event and all duplicate multiplicities. With $U=\overline\Phi(Z)$, the $m$ positive-sign entries equal $U$ and the $n$ negative-sign entries equal $1-U$; $U$ is uniform on $(0,1)$.

### NOT

Fail: the rejection probability equals $q$ for every member of the family. Since $q<1/2$, a qualifying rank cannot include both nonempty sign blocks: its largest p-value would be at least $1/2$, while its threshold is at most $q$. For a block with common p-value $U$, the largest rank inside that block has the easiest threshold, so its crossing condition is precisely $U\le qm/N$. The other block's condition is $1-U\le qn/N$. A block of size zero contributes no event. These events are disjoint because $qm/N+qn/N=q<1$, and therefore
$$
\mathbb P(E_q)=\mathbb P(U\le qm/N)+\mathbb P(U\ge1-qn/N)=q\frac{m+n}{N}=q.
$$
The endpoint equalities have zero probability under the uniform law. In particular unbounded dimension, extreme positive/negative correlations, and singularity together do not increase this family's ratio above one.

## Failure

NOT fails: every rank-one sign-duplicate model has $\mathbb P(E_q)/q=1$ for $0<q<1/2$.
