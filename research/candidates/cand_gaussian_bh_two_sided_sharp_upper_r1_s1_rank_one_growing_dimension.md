---
type: candidate
title: Growing-dimension exactly rank-one Gaussian null family
status: failed
target_asset: gaussian_bh_two_sided_sharp_upper
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  NOT: fail
mode: refute
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: 2aaf3b157d839619c9429607bf182d896b1dacb3bc592c3dc8041bc442b8ed40
performed_by: unknown
created_at: '2026-11-04T08:34:06.454Z'
extension_version: 0.0.4
---

## Object

For each $q\in(0,1/2)$ set $N(q)=\lceil\exp(1/q)\rceil$, $\theta(q)=0$, and $\Sigma(q)=\mathbf1\mathbf1^{\mathsf T}$. Let $Z\sim\mathcal N(0,1)$ and $T_i=Z$ for every $i\leq N(q)$. Use the specified two-sided p-values and ordinary BH procedure at level $q$.

## Checks

### H1

Pass: $N(q)$ is a finite positive integer at every $q$, and the unrestricted quantifiers allow this growth.

### H2

Pass: $\theta(q)=0\in\mathbb R^{N(q)}$, so every hypothesis is a true null.

### H3

Pass: $\Sigma(q)$ is symmetric, has diagonal entries one, and $x^{\mathsf T}\Sigma(q)x=(\sum_i x_i)^2\geq0$. The displayed representation gives the required exact joint Gaussian law, including singularity.

### H4

Pass: every two-sided p-value equals $U=2\overline\Phi(|Z|)$, which is uniform on $(0,1)$. Ordinary BH rejects all hypotheses exactly when $U\leq q$: that condition makes rank $N$ qualify, and if $U>q$ no rank can qualify. Thus its FDR is exactly $q$.

### NOT

Fail: the candidate's FDR divided by $q\sqrt{\log(1/q)}$ equals $1/\sqrt{\log(1/q)}\to0$, so it does not violate the proposed upper bound. This is a uniform obstruction for all rank-one Gaussian covariance matrices, even with arbitrary means and dimension: every true-null two-sided p-value is the same uniform $U$, and a false rejection implies $U\leq qR/N\leq q$, hence FDR $\leq q$.

## Failure

NOT fails: exact rank-one dependence gives FDR at most $q$, uniformly over growing dimension and arbitrary nonnull means.
