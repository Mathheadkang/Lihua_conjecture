---
type: candidate
title: Two dependent Gaussian carriers with growing signed multiplicities
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
round: 3
slot: 2
direction: small_cases
statement_digest: 15d52b3eb80faa8138461b0390ec347f4eb6a5465aae5494d0e050fea1bae614
performed_by: unknown
created_at: '2026-11-09T04:24:10.657Z'
extension_version: 0.0.4
---

## Object

Let $Z,W$ be independent standard Gaussian variables. For $-1<\rho<0$, put
$$
X=Z,\qquad Y=\rho Z+\sqrt{1-\rho^2}\,W.
$$
Choose positive integer multiplicities $m_1,m_2,m_3,m_4$ and form $T$ from $m_1$ copies of $X$, $m_2$ copies of $-X$, $m_3$ copies of $Y$, and $m_4$ copies of $-Y$. Put $N=m_1+m_2+m_3+m_4$ and let $0<q<1/2$. All parameters may depend on $q$.

A concrete sequence is $n\ge2$, $q_n=e^{-n}$, $\rho_n=-1+1/n$, and $(m_1,m_2,m_3,m_4)=(1,2,3,2^n)$, so $N_n=2^n+6\to\infty$ and $\rho_n\to-1$.

This tests the smallest correlated-carrier case beyond one carrier. The earlier bounded-$N$ obstruction does not directly cover it because $N$ diverges; the independent-antipodal obstruction does not apply because the carriers have nonzero covariance. The finite number of distinct coordinate values gives a separate obstruction below.

## Checks

### H1

Pass: $N=m_1+m_2+m_3+m_4$ is a positive integer and can grow without bound.

### H2

Pass: represent the four coordinate types by the unit vectors
$$
v_1=(1,0),\quad v_2=(-1,0),\quad
v_3=(\rho,\sqrt{1-\rho^2}),\quad v_4=-v_3.
$$
Repeating their rows according to the multiplicities gives a matrix $A\in\mathbb R^{N\times2}$. Its Gram matrix $\Sigma=AA^{\mathsf T}$ has diagonal one and is symmetric positive semidefinite, because $a^{\mathsf T}\Sigma a=\|A^{\mathsf T}a\|^2\ge0$. Thus $\Sigma\in\mathcal C_N$, including its allowed singularity when $N>2$.

### H3

Pass: $T=A(Z,W)^{\mathsf T}$ is exactly jointly Gaussian with mean zero and covariance $\Sigma$. Every coordinate is a true null.

### H4

Pass: the level is positive and below $1/2$; the concrete sequence has $q_n\downarrow0$. The calculation below applies uniformly over this whole interval, and hence over any proposed sufficiently small level interval.

### H5

Pass: use the specified one-sided p-values $p_i=\overline\Phi(T_i)$ and ordinary Simes event, with multiplicities and non-strict inequalities,
$$
E_q=\{\exists k\in\{1,\ldots,N\}:p_{(k)}\le qk/N\}.
$$
Writing $U=\overline\Phi(X)$ and $V=\overline\Phi(Y)$, the only four possible p-values are $U,1-U,V,1-V$. Each of $U,V$ is marginally uniform on $(0,1)$, despite their dependence.

### NOT

Fail: if $E_q$ occurs, its witnessing rank satisfies $p_{(1)}\le p_{(k)}\le qk/N\le q$. Consequently
$$
E_q\subseteq\{U\le q\}\cup\{1-U\le q\}\cup\{V\le q\}\cup\{1-V\le q\}.
$$
The four events each have probability $q$. A union bound, requiring no independence, therefore gives
$$
\mathbb P(E_q)\le4q
$$
uniformly in $N$, all multiplicities, and $\rho$, including parameters varying with $q$. Thus this family admits the finite constant $C=4$ and cannot violate the conjecture's existence of some finite universal constant. No sharper calibration or claim about other growing-rank models follows.

## Failure

NOT fails: two arbitrarily dependent Gaussian carriers with arbitrary signed multiplicities have at most four distinct p-values, so their Simes rejection probability is at most $4q$ even as the dimension diverges.
