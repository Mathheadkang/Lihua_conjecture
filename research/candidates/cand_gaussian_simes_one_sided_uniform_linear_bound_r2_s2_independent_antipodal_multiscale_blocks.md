---
type: candidate
title: >-
  Independent antipodal Gaussian blocks with exponentially unequal
  multiplicities
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
round: 2
slot: 2
direction: extremal
statement_digest: 15d52b3eb80faa8138461b0390ec347f4eb6a5465aae5494d0e050fea1bae614
performed_by: unknown
created_at: '2026-11-09T04:20:28.439Z'
extension_version: 0.0.4
---

## Object

For each integer $B\ge2$, take independent standard normals $Z_1,\ldots,Z_B$. Block $b$ consists of $a_b=2^{b-1}$ copies of $Z_b$ and one copy of $-Z_b$. Thus
$$
N_+=2^B-1,\qquad N_-=B,\qquad N=2^B-1+B.
$$
Set $q_B=e^{-B}$. All means are zero. The covariance has independent blocks; within block $b$ it is $s_bs_b^{\mathsf T}$, where $s_b$ has $a_b$ positive entries and one negative entry. Use exactly the one-sided Gaussian p-values and ordinary BH rule in the target.

This family has rank $B\to\infty$, independent Gaussian factors, both signs in every factor, and exponentially unequal cluster masses. It is outside the search board's single-factor signed rank-one obstruction.

## Checks

### H1

The dimension $N=2^B-1+B$ is a finite positive integer for every $B\ge2$ and tends to infinity.

### H2

The displayed covariance is symmetric with unit diagonal. For every real vector $x$, its quadratic form is the sum over blocks of $(s_b^{\mathsf T}x_b)^2\ge0$. Hence $\Sigma\in\mathcal C_N$, including its permitted singularity.

### H3

The observation is a deterministic linear map of independent centered standard normals, so it is jointly Gaussian with mean zero and precisely that covariance. Every coordinate is a true null.

### H4

The levels satisfy $0<q_B\le e^{-2}<1/2$ and $q_B\downarrow0$. They eventually lie below every fixed admissible $q_0>0$.

### H5

Writing $U_b=\overline\Phi(Z_b)$, the p-values in block $b$ are $a_b$ copies of $U_b$ and one copy of $1-U_b$. Both are exactly the required one-sided p-values, and the $U_b$ are independent uniform random variables. All ranks below count copies, and all inequalities are non-strict.

### NOT

This check fails: the whole family obeys $\mathbb P(E_q)\le2q$ for every $0<q<1/2$, uniformly in $B$. Here is a direct calculation, also allowing arbitrary positive integer multiplicities $a_b,c_b$ for the positive and negative signs.

First consider independent uniform variables $W_b$ repeated $m_b$ times, with total size $M=\sum_bm_b$, and ordinary BH at level $q$. Denote its rejection count by $R$. For block $b$, replace all its p-values by zero and denote the resulting rejection count by $R^{[b]}$. It depends only on the other uniforms and satisfies $R^{[b]}\ge m_b$. The step-up definition gives the identity
$$
\{\text{block }b\text{ rejected}\}
=\{W_b\le qR^{[b]}/M\},
\qquad R=R^{[b]}\text{ on this event}.
$$
To see stability, decreasing an already rejected block does not change order statistics above the original largest crossing. Conversely, when $W_b\le qR^{[b]}/M$, restoring that block preserves the crossing at $R^{[b]}$, and monotonicity precludes a larger count. Since $R^{[b]}$ is independent of $W_b$ and $qR^{[b]}/M<1$, conditioning yields
$$
\mathbb E\left[\frac{m_b\mathbf1\{\text{block }b\text{ rejected}\}}{R\vee1}\right]
=\mathbb E\left[\frac{m_b}{R^{[b]}}\frac{qR^{[b]}}M\right]
=\frac{qm_b}{M}.
$$
Summing over $b$ proves that the duplicated independent-uniform family has rejection probability exactly $q$.

Now split the antipodal model into its positive-sign group of size $N_+$ and negative-sign group of size $N_-$. Each group separately has independent uniform block values with fixed multiplicities, so the preceding calculation gives rejection probability $q$ for each group's BH procedure at level $q$.

If the full procedure has a crossing at rank $k$, put $t=qk/N$ and let $j_+$ and $j_-$ be the numbers of p-values at most $t$ in the two groups. Then $j_++j_-\ge k$. For at least one sign $s$,
$$
j_s\ge kN_s/N,
$$
since otherwise their sum is less than $k$. In that group $j_s\ge1$ and
$$
p^{(s)}_{(j_s)}\le t=\frac{qk}N\le\frac{qj_s}{N_s}.
$$
Thus a full crossing implies a crossing in at least one of the two separate group procedures. The union bound gives $\mathbb P(E_q)\le2q$; independence between the two groups is not assumed. Consequently $\mathbb P(E_{q_B})/q_B\le2$ throughout the growing-rank, unequal-mass sequence, and no divergent ratio occurs.

## Failure

NOT fails: independent antipodal blocks with arbitrary sign multiplicities obey the uniform bound $\mathbb P(E_q)\le2q$, including exponentially unequal masses and rank tending to infinity.
