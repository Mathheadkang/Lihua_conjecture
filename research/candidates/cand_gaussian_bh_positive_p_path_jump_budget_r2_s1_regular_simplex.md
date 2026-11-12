---
type: candidate
title: Regular-simplex all-null family has a bounded positive jump budget
status: failed
target_asset: gaussian_bh_positive_p_path_jump_budget
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: fail
mode: refute
round: 2
slot: 1
direction: known_counterexamples
statement_digest: 301a9fdf2ecda11e42541631b84ac56c2ad1d8a75b5cf72d593e5cd71674b0e2
performed_by: unknown
created_at: '2026-11-09T21:30:07.309Z'
extension_version: 0.0.4
---

## Object

For every integer $N\geq2$ and $0<q\leq q_0:=S(1)$, take $\theta=0$ and
$$
\Sigma_N=\frac{N}{N-1}I_N-\frac{1}{N-1}{\bf1}{\bf1}^{\mathsf T}.
$$
Equivalently, for independent standard normals $X_1,\ldots,X_N$, set
$$
Z_j=\sqrt{\frac{N}{N-1}}(X_j-\overline X).
$$
The intended mechanism is an increasing number of weak negative correlations in a rank-$N-1$ singular Gaussian model, rather than a rank-one antipodal clone model. Dimension may depend arbitrarily on $q$.

## Checks

### H1

Pass. Each member has finite integer dimension $N\geq2$.

### H2

Pass. The mean vector is real and all its entries are zero, so $I_0=[N]$ and every original weight is $g_i(t)=1$.

### H3

Pass. The displayed representation is jointly Gaussian. The covariance has unit diagonal, eigenvalue zero on ${\bf1}$, and eigenvalue $N/(N-1)$ on its orthogonal complement. It is therefore positive semidefinite, including the permitted singularity.

### H4

Pass. The family uses precisely $0<q\leq S(1)$.

### H5

Pass. Use the full original conditional paths and the actual largest non-strict BH ranks from the stated finite identity. For a selected null $i$, its own score is $u(t)$ and every other score is
$$
T_j^i(t)=\xi_j-\frac{u(t)}{N-1},\qquad j\ne i.
$$
Thus all scores except the selected score increase as $t$ increases. In particular, their threshold counts cannot decrease.

At a simultaneous event $t_0$, suppose the actual BH rank decreases from $r$ on the left to $s<r$ on the right. The rank-$r$ qualification can be lost only through the selected coordinate crossing the rank-$r$ threshold: every other threshold indicator is nondecreasing. Consequently $t_0=qr/N$. Both one-sided values of $A_i$ are then one, since the left rank is $r$ and the right rank is smaller. Such an event contributes no jump. If the rank increases, $A_i$ can only decrease; if it stays fixed, $A_i$ is continuous. This argument uses the net ranks on the two sides and therefore already merges simultaneous crossings. All actual jumps of $A_i$ are downward.

It follows that the positive sum equals the signed sum pathwise. The supplied exact finite identity, with $g_i=1$, therefore gives
$$
\frac1N\sum_{i=1}^N\mathbb E B_i=\frac{F}{q}-1,
\qquad F=\Pr(R_q>0).
$$

### NOT

Fail. The entire family has a uniform finite normalized budget, as follows.

For any subset $K$ and real thresholds $a_j$, its nonpositive pairwise correlations imply
$$
\Pr(Z_j\geq a_j\text{ for every }j\in K)
\leq\prod_{j\in K}S(a_j).
$$
Here is a direct justification sufficient for this family. Interpolate its principal covariance from the identity by $C(s)=I+s(C-I)$, initially with $s<1$. For smooth increasing functions $f_j$ taking values in $[0,1]$, Gaussian differentiation gives
$$
\frac{d}{ds}\mathbb E\prod_{j\in K}f_j(Y_j(s))
=\sum_{j<\ell}C_{j\ell}\,
\mathbb E\left[f_j'(Y_j(s))f_\ell'(Y_\ell(s))
\prod_{h\ne j,\ell}f_h(Y_h(s))\right]\leq0.
$$
Approximate upper-tail indicators and then let $s$ increase to one. Each marginal is continuous, so singularity at the endpoint does not affect the limit. This proves the displayed orthant inequality without an independence assumption on the original scores.

If BH has a positive rank, for some $k\in[N]$ at least $k$ original p-values are at most $qk/N$. Union-bounding over ranks and subsets, and applying the orthant inequality, gives
$$
F\leq q+\sum_{k=2}^N\binom Nk\left(\frac{qk}{N}\right)^k
\leq q+\sum_{k=2}^{\infty}(eq)^k
=q+\frac{e^2q^2}{1-eq}.
$$
The denominator is positive throughout the allowed range: Mills' upper bound yields $S(1)<\phi(1)<1/e$. Consequently
$$
0\leq
\frac{N^{-1}\sum_i\mathbb E B_i}{\sqrt{\log(1/q)}}
\leq
\frac{e^2q_0}{(1-eq_0)\sqrt{\log(1/q_0)}}<\infty.
$$
This bound is uniform in dimension, including sequences $N=N(q)$, and rules out this family as an unbounded counterexample. It establishes no bound for general mixed-sign covariances or heterogeneous means.

## Failure

NOT is the first failing check: the regular-simplex family's normalized positive budget is uniformly bounded by the explicit finite constant above.
