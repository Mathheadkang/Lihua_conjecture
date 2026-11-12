---
type: candidate
title: Iid simplex colours and fluctuating cluster ranks
status: failed
target_asset: gaussian_bh_exchangeable_array_variational_compactification
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  NOT: fail
mode: refute
round: 4
slot: 2
direction: small_cases
statement_digest: ad34243f88082429829568f6c42e01df9341469c502adef723e491225d546918
performed_by: unknown
created_at: '2026-11-09T05:59:53.935Z'
extension_version: 0.0.4
---

## Object

Fix $\sigma=1/2$ and $q=1/10$. In $\mathbb R^2$ put
$$
v_1=(1,0),\qquad v_2=(-1/2,\sqrt3/2),\qquad
v_3=(-1/2,-\sqrt3/2).
$$
Let $A_i$ be iid uniform on $\{1,2,3\}$, set $\theta_i=0$, $\ell_i=1$, and set $C_{ij}=\langle v_{A_i},v_{A_j}\rangle$. Thus distinct coordinates have residual correlation $1$ when their colours agree and $-1/2$ otherwise. Generate
$$
T_i=\frac{\sqrt3}{2}\langle v_{A_i},G\rangle+\frac12Z,
$$
where $G\sim N_2(0,I_2)$ and $Z\sim N(0,1)$ are independent of each other and of all colours.

The proposed failure mechanism is that multinomial colour counts, and hence the finite BH rank grid, might prevent completion at the exactly equal limiting colour weights. Unlike a constant negative off-diagonal prescription, this construction includes repeated colours and is positive semidefinite in every dimension. It therefore escapes the board's finite-simplex extendibility obstruction rather than changing its negative correlation constant.

## Checks

### H1

Pass. The fixed parameters satisfy $0<\sigma<1$ and $0<q<1/2$; indeed $q<\overline\Phi(1)$.

### H2

Pass. The infinite marked array is jointly exchangeable because every simultaneous permutation merely permutes its iid colours. It is symmetric with diagonal one, and every finite principal matrix is a Gram matrix. Explicitly, for real coefficients $a_i$,
$$
\sum_{i,j}a_ia_jC_{ij}
=\left\|\sum_i a_i v_{A_i}\right\|^2\ge0.
$$
The within-colour entries $1$ are essential for this verification.

### H3

Pass. All means are zero and all tags are true, so the marks are lawful and canonical. The moment is $M_2=0$, in particular finite.

### H4

Pass. Conditional on the parameter array, the displayed observations are jointly Gaussian, have the prescribed mean and covariance
$$
\operatorname{Cov}(T_i,T_j\mid(A_k)_k)
=\tfrac34C_{ij}+\tfrac14,
$$
and have marginal variance one. The Gaussian innovations are independent of the parameters. The outer expectation over colours is retained and is not identified with one unconditional Gaussian distribution.

### NOT

Fail for the proposed noncompletion mechanism. Write $p_a=\overline\Phi(\tfrac{\sqrt3}{2}\langle v_a,G\rangle+\tfrac12Z)$, and order these three values increasingly as $p_{(1)},p_{(2)},p_{(3)}$. With probability one they are distinct: each score difference is a nondegenerate one-dimensional Gaussian. Let $w_{n,(a)}$ be the empirical frequency of the corresponding colour among the first $n$ coordinates. Almost surely all colours eventually occur and $w_{n,(a)}\to1/3$.

Because all hypotheses are true, the finite FDP equals the indicator of a positive BH rank. A group of equal p-values can qualify only if its final rank qualifies, so this event is exactly
$$
\bigcup_{k=1}^3
\left\{p_{(k)}\le q\sum_{a=1}^k w_{n,(a)}\right\}
$$
once all colours occur. Each $p_a$ is uniform on $(0,1)$, so the probability that any $p_a$ equals one of $q/3,2q/3,q$ is zero. Consequently these finite rejection indicators converge almost surely to
$$
\mathbf1\!\left\{p_{(1)}\le q/3\ \text{or}\
p_{(2)}\le2q/3\ \text{or}\ p_{(3)}\le q\right\}.
$$
Bounded convergence gives an explicit completed FDR and rules out the proposed finite-size oscillation. The same threshold-null argument gives continuity of this expression in $q$.

The model also has the deterministic directing measure
$$
\mu=\tfrac13\sum_{a=1}^3\delta_{(0,v_a,1)},
$$
with unit vectors and no diagonal correction. Furthermore any rejection requires at least one $p_a\le q$, so its completed FDR is at most $3q$. Its zero-moment normalized objective is therefore at most $3/\overline\Phi^{-1}(q)-\delta\log(1/q)$, which tends to $-\infty$ as $q\downarrow0$. These calculations do not prove the general completion, representation, or extremum assertions.

## Failure

NOT fails: iid simplex colours give a lawful infinite extension, but their empirical BH rejection indicators converge almost surely because no limiting Gaussian score hits a deterministic BH threshold.
