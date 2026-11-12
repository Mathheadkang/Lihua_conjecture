---
type: candidate
title: Orthogonal atom dust does not break marked-array FDR continuity
status: failed
target_asset: gaussian_bh_exchangeable_array_variational_compactification
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  NOT: fail
mode: refute
round: 2
slot: 1
direction: known_counterexamples
statement_digest: ad34243f88082429829568f6c42e01df9341469c502adef723e491225d546918
performed_by: unknown
created_at: '2026-11-09T05:53:03.140Z'
extension_version: 0.0.4
---

## Object

Fix $\sigma=1/2$ and $q=1/20$. For each integer $m\ge1$, let $J_1,J_2,\ldots$ be iid uniform on $\{1,\ldots,m\}$, set every mark to $(\theta_i,\ell_i)=(0,1)$, and set
$$
C^{(m)}_{ij}=\mathbf1_{\{J_i=J_j\}}.
$$
Write $P_m$ for the resulting parameter-array law. Let $P_\infty$ have the same marks and $C^{(\infty)}_{ij}=\mathbf1_{\{i=j\}}$. This is an orthogonal-atom dust limit: the finite directing law supported uniformly on $e_1,\ldots,e_m$ loses every positive-mass off-diagonal atom as $m\to\infty$. The attempted failure is discontinuity at this limit, rather than at an all-copy covariance.

## Checks

### H1

Pass. The specified $\sigma$ lies in $(0,1)$ and $q$ lies in $(0,1/2)$ (also $q<S(1)$).

### H2

Pass. Every mark is lawful and canonical. For finite coefficients $a_1,\ldots,a_n$,
$$
\sum_{i,j\le n}a_i C^{(m)}_{ij}a_j
=\sum_{j=1}^m\left(\sum_{i:J_i=j}a_i\right)^2\ge0.
$$
The diagonal is one and entries lie in $[-1,1]$. The limiting matrix is the identity and is likewise lawful.

### H3

Pass. The iid labels give joint exchangeability, while the limiting deterministic identity array is invariant under every index permutation. Draw all labels independently of the Gaussian innovations. Conditional observations may be generated as
$$
T_i=\sqrt{1-\sigma^2}\,G_{J_i}+\sigma Z
$$
for $P_m$, and with independent $G_i$ in place of $G_{J_i}$ for $P_\infty$. Here all $G_j,Z$ are independent standard normals.

### H4

Pass. All laws have $M_2=0$, so the entire family belongs to $\mathfrak P_2$. For every fixed $n$, the first $n$ coordinates of $P_m$ agree with the identity-array parameters whenever their labels are distinct. The probability of a collision is at most $n(n-1)/(2m)$; consequently $P_m\to P_\infty$ in finite-subarray weak convergence.

### NOT

Fail. There is no FDR discontinuity. Here is an explicit comparison using the approved uniform submodel compression statement, with no directing-representation assertion assumed. Let $f_m$ be the ordinary $m$-test FDR of the deterministic zero-mean, all-true residual identity matrix. Sampling $n$ indices iid from those $m$ tests produces exactly the conditional model defining $\mathcal F_n(P_m)$. Thus compression gives
$$
|\mathcal F_n(P_m)-f_m|\le e_n(q,\sigma).
$$
On the no-collision event the sampled model is the $n$-test residual identity model, whose FDR is $f_n$. Boundedness of the FDP therefore gives
$$
|\mathcal F_n(P_m)-f_n|\le\frac{n(n-1)}{2m},\qquad
|f_m-f_n|\le e_n(q,\sigma)+\frac{n(n-1)}{2m}.
$$
For fixed $n$, comparing two sufficiently large indices $m,m'$ bounds $|f_m-f_{m'}|$ by $2e_n$ plus terms tending to zero. Since $e_n\to0$, the sequence $f_m$ has a limit $L$. Letting $m\to\infty$ in the last display gives $|L-f_n|\le e_n$.

For fixed $m$, the first compression display and $n\to\infty$ show $\mathcal F(P_m)=f_m$. Also $\mathcal F_n(P_\infty)=f_n$, hence $\mathcal F(P_\infty)=L$. In particular
$$
|\mathcal F(P_m)-\mathcal F(P_\infty)|
\le2e_n(q,\sigma)+\frac{n(n-1)}{2m}\longrightarrow0
$$
by first taking $m\to\infty$ and then $n\to\infty$. The dust component is represented lawfully by $v=0$ with fresh coordinate noise; no unit-sphere representation of the dust is required by the target. This family supplies no violation of the other conclusions.

## Failure

NOT fails: orthogonal-atom dust converges in finite subarrays and in completed FDR, with an explicit collision-plus-compression bound.
