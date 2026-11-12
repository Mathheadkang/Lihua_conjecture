---
type: candidate
title: Signed six-type rank-three Gaussian arrays with growing multiplicities
status: failed
target_asset: gaussian_bh_two_sided_sharp_upper
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
statement_digest: 2aaf3b157d839619c9429607bf182d896b1dacb3bc592c3dc8041bc442b8ed40
performed_by: unknown
created_at: '2026-11-04T08:34:06.454Z'
extension_version: 0.0.4
---

## Object

For every $q\in(0,e^{-2})$, put $L=\log(1/q)$,
$M=\lceil\exp(L^2)\rceil$, $N=6M$, and
$u=\overline\Phi^{-1}(q/2)>0$.
Let $Z=(Z_1,Z_2,Z_3)$ be standard Gaussian. There are six groups of $M$ coordinates each. Their deterministic pairs (mean, loading) are
$$
(0,e_1),\quad(0,e_2),\quad(0,e_3),\quad
\left(u,\frac{e_1-e_2}{\sqrt2}\right),\quad
\left(-u,\frac{e_2-e_3}{\sqrt2}\right),\quad
\left(2u,\frac{-e_1-e_3}{\sqrt2}\right).
$$
Every coordinate in a group equals its mean plus the group's loading dotted with $Z$. Use the stated two-sided p-values and ordinary BH at level $q$.

This family includes signed null/alternative loadings, nonzero deterministic means, singular covariance, and a testing dimension growing faster than every power of $1/q$. Its failure is therefore not the fixed-$N$ harmonic-bound obstruction.

## Checks

### H1

The testing dimension $N=6M$ is a finite positive integer for every $q$ in the given range.

### H2

All means are deterministic real numbers. Exactly the first three groups are true nulls, because $u>0$.

### H3

Let $A$ have the indicated unit loading vector in each row. Then $\Sigma=AA^{\mathsf T}$ is symmetric positive semidefinite and has unit diagonal. Its rank is three. Identical coordinates within a group are allowed by the target.

### H4

The observation is exactly $T=\theta+AZ$, so every linear combination is Gaussian with the required covariance; this is not a mixture or a conditional-law substitution.

### H5

Use $p_i=2\overline\Phi(|T_i|)$, $I_0=\{i:\theta_i=0\}$, the largest qualifying BH rank, and the stated $V/(R\vee1)$ expectation. No local or block BH procedure is used.

### NOT

Fail. Every BH rejection has $p_i\leq q$, because its threshold is $qR/N\leq q$. Thus a false rejection requires $|Z_j|\geq u$ for at least one of $j=1,2,3$. Each such event has probability exactly $q$, and hence
$$
0\leq\operatorname{FDR}^{(2)}_{\rm BH}
\leq\mathbb P(V>0)\leq3q.
$$
Consequently
$$
\lim_{q\downarrow0}
\frac{\operatorname{FDR}^{(2)}_{\rm BH}}
{q\sqrt{\log(1/q)}}=0.
$$
More generally the same argument gives $K_0q$ whenever all true-null p-values have at most $K_0$ distinct random values, independently of the number of hypotheses, alternative means, and dependence. For two-sided tests opposite unit loadings give the same random null p-value. This obstruction does not cover a finite parameter-type model with independent residual noise within its null groups.

## Failure

NOT fails: only three distinct random null p-values occur, forcing the normalized FDR to zero even with arbitrarily large repeated-group multiplicities.
