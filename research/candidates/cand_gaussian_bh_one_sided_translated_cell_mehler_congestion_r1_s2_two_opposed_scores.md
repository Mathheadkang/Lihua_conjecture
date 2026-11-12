---
type: candidate
title: Two opposed scores with both forced-rank cells overlapping
status: failed
target_asset: gaussian_bh_one_sided_translated_cell_mehler_congestion
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  NOT: fail
mode: refute
round: 1
slot: 2
direction: small_cases
statement_digest: d49b6ceedd94063add2326953562443ef9d47a5aaa10af748c68abcc336945a7
performed_by: unknown
created_at: '2026-11-10T22:52:57.718Z'
extension_version: 0.0.4
---

## Object

For every $0<q\leq S(1)$, set $N=2$, $d=1$, $a_1=1$, $a_2=-1$, $\theta_1=0$, and $\theta_2=b=u_1+u_2$, where $u_1=S^{-1}(q/2)$ and $u_2=S^{-1}(q)$. Thus $T_1(z)=z$ and $T_2(z)=b-z$. Use the exact physical two-test BH procedure in the target. This family attempts to exploit two simultaneously active translated forced-rank terms for its only null.

## Checks

### H1

$N=2$ and $d=1$ are finite positive integers; both directions have unit norm. With $Z\sim N(0,1)$ the covariance is the admissible singular Gram matrix with diagonal entries one and off-diagonal entries minus one.

### H2

The means are real, $b>0$, and the original null set is exactly $I_0=\{1\}$; no null labels are changed.

### H3

The family is defined for every $0<q\leq S(1)$, so $u_1>u_2\geq1$. In particular it covers every proposed sufficiently small level in the statement.

### H4

Forcing only $p_1$ to zero gives rank two precisely when the retained original $p_2(z)$ is at most $q$. Hence
$$
R_1(z)=2\quad\Longleftrightarrow\quad z\leq b-u_2=u_1,
$$
and otherwise $R_1(z)=1$. This uses both physical tests and the non-strict BH convention.

### H5

Since $c_{1r}=u_r$, substitution into the exact displayed density yields
$$
H_q(y)=\mathbf1\{y>0\}\exp(-u_1y-u_1^2/2)
+\frac12\mathbf1\{0\leq y\leq u_1-u_2\}\exp(-u_2y-u_2^2/2).
$$
At $y=0$ the first term is absent because its forced rank is two; this single-point distinction has no effect on either integral or smoothing. No cells have been optimized separately.

### H6

Use $L=\log(1/q)$, $\tau=1/L$, and independent scalar $G\sim N(0,1)$, exactly as specified. The spatial point $x$ remains arbitrary.

### NOT

Fails: this entire family satisfies both conclusions with a uniform constant.

For part (a), completing the square in each term gives
$$
\int H_q\,d\gamma_1=S(u_1)+\frac12\{S(u_2)-S(u_1)\}=\frac{3q}{4}.
$$
In the original BH procedure the null is rejected alone on $Z>u_1$, and both tests are rejected on $u_2\leq Z\leq u_1$. These events give the same FDR, $3q/4$.

For part (b), uniformly in $y$,
$$
H_q(y)\leq e^{-u_1^2/2}+\frac12e^{-u_2^2/2}.
$$
The elementary Mills bound $\phi(u)\leq(u+1/u)S(u)$ for $u>0$ implies
$$
H_q(y)\leq\frac{\sqrt{2\pi}}{2}q
\left(u_1+\frac1{u_1}+u_2+\frac1{u_2}\right).
$$
Here $L>1$, $u_2\leq\sqrt{2L}$ and $u_1\leq\sqrt{2(L+\log2)}<1.85\sqrt L$, by the Gaussian Chernoff bound. As $u_1,u_2\geq1$, the last display is less than $7q\sqrt L$. Averaging at the prescribed Mehler input and taking the supremum over every $x\in\mathbb R$ preserves this bound. Thus $C=7$ and $q_0=S(1)$ work uniformly for this family; there is no divergence capable of refuting the universal assertion.

## Failure

NOT fails: exact FDR and translated mass equal $3q/4$, and the full smoothed density is at most $7q\sqrt{\log(1/q)}$ for every admissible $q$ and every spatial point.
