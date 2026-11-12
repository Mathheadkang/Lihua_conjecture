---
type: candidate
title: >-
  Signed rank-one Gaussian construction with an explicit shrinking
  three-rejection interval
status: survived
target_asset: gaussian_bh_negative_null_mean_nonmonotonicity
checks:
  P1: pass
  P2: pass
  P3: pass
  P4: pass
  P5: pass
  P6: pass
mode: construct
round: 1
slot: 3
direction: symmetric_algebraic
statement_digest: 9f2cf4094f405ea7ab6e91647d7c2eae547e583022c0a0ab42e0071b8242fa50
performed_by: unknown
created_at: '2026-11-04T12:37:56.077Z'
extension_version: 0.0.4
---

## Object

For any fixed $q\in(0,1/2)$, let $\Phi$ be the standard normal distribution function and define
$$
a=\Phi^{-1}(1-q/3),\qquad e=\Phi^{-1}(1-2q/3),\qquad d=\Phi^{-1}(1-q),\qquad \delta=e-d.
$$
Thus $a>e>d>0$ and $\delta>0$. Put
$$
K=a+\delta/2,\qquad L_A=a+\delta,\qquad L_B=a+5\delta/4,\qquad U=a+3\delta/2,
$$
$$
c=a+e+\delta/2,\qquad b=d-L_A,\qquad b'=d-L_B.
$$
Write $b_A=b$, $b_B=b'$, and $D_J=e-b_J=L_J+\delta$ for $J\in\{A,B\}$. With $Z\sim\mathcal N(0,1)$, define each model by
$$
T^J=(Z,\ Z+b_J,\ c-Z).
$$
Both models have the covariance matrix
$$
\Sigma=\begin{pmatrix}1&1&-1\\1&1&-1\\-1&-1&1\end{pmatrix}.
$$
Use $p_i^J=\overline\Phi(T_i^J)$ and ordinary three-test BH at level $q$, with true-null set $\{1,2\}$.

The exact proposed formulas are
$$
F_A(q)=\frac q3+\frac12\overline\Phi(a+\delta/2)-\frac13\left[\Phi(a+3\delta/2)-\Phi(a+\delta)\right],
$$
$$
F_B(q)=\frac q3+\frac12\overline\Phi(a+\delta/2)-\frac13\left[\Phi(a+3\delta/2)-\Phi(a+5\delta/4)\right],
$$
$$
F_B(q)-F_A(q)=\frac13\left[\Phi(a+5\delta/4)-\Phi(a+\delta)\right].
$$
All arguments are explicit functions of $q$ through the displayed definitions of $a,e,d,\delta$.

## Checks

### P1

Let $v=(1,1,-1)^{\mathsf T}$. Then $\Sigma=vv^{\mathsf T}$ is symmetric positive semidefinite, since $x^{\mathsf T}\Sigma x=(v^{\mathsf T}x)^2\geq0$, and has diagonal entries one. Each centered observation is $vZ$, so for every $x\in\mathbb R^3$, $x^{\mathsf T}(T^J-\theta^J)=(x^{\mathsf T}v)Z$ is centered Gaussian with variance $x^{\mathsf T}\Sigma x$, including the zero-variance case. Both observations are therefore exactly jointly Gaussian with unit marginal variances and the same admissible singular covariance.

### P2

The means are $\theta^A=(0,b,c)$ and $\theta^B=(0,b',c)$. Their ordering follows from
$$
b'=b-\delta/4<b=d-a-\delta<0,\qquad c=a+e+\delta/2>0.
$$
Consequently both true-null sets are exactly $\{1,2\}$, and only the strictly negative second mean changes.

### P3

The proposed p-values are precisely $\overline\Phi(T_i^J)$. For $r=1,2,3$, their BH rank-$r$ threshold is equivalent to having at least $r$ observations at or above, respectively, $a,e,d$. The largest qualifying rank must be used; in particular, three rejections occur whenever all three observations are at least $d$, without requiring the smaller-rank inequalities. Check P6 below derives the complete rejection set directly from these largest-rank criteria. Its FDP weights are $0$ for the alternative alone, $1/2$ for one null and the alternative, $1$ for one or two nulls alone, and $2/3$ for all three. Their expectation is the total FDR specified in P3.

### P4

The full BH calculation in P6 yields
$$
F_B(q)-F_A(q)=\frac13[\Phi(L_B)-\Phi(L_A)]>0,
$$
because $L_B-L_A=\delta/4>0$ and $\Phi$ is strictly increasing. This holds for every $q\in(0,1/2)$. Under the common-$Z$ coupling, the only FDP change is on $[L_A,L_B)$, where model A rejects all three and model B rejects only null 1, changing the FDP from $2/3$ to $1$.

### P5

The exact expression in P6 gives, for either $J$,
$$
F_J(q)=\frac q3+\frac12\overline\Phi(K)-\frac13[\Phi(U)-\Phi(L_J)].
$$
Here $U>L_J$ and $K>a$, so
$$
F_J(q)<\frac q3+\frac12\overline\Phi(K)<\frac q3+\frac12\overline\Phi(a)=\frac q2<q.
$$
The bound holds analytically over the entire stipulated interval.

### P6

First note the identities
$$
c-e=K,\qquad c-d=U,\qquad d-b_J=L_J,\qquad e-b_J=D_J=L_J+\delta
$$
and the strict order, for both models,
$$
e<a<K<L_J<U<D_J.
$$
Indeed $L_A=a+\delta$, $L_B=a+5\delta/4$, $U=a+3\delta/2$, and $D_A=a+2\delta$, $D_B=a+9\delta/4$.

Since $b_J<0$, $T_2^J<T_1^J$ for all $Z$. Rank 3 qualifies exactly when
$$
Z\geq d,\qquad Z\geq d-b_J=L_J,\qquad Z\leq c-d=U.
$$
As $L_J>d$, this is exactly $Z\in[L_J,U]$; on this interval BH rejects all three.

For rank 2, at least two observations must be at least $e$. The pair $\{1,3\}$ meets this threshold exactly when $e\leq Z\leq c-e=K$. The pair $\{1,2\}$ meets it exactly when $Z\geq e-b_J=D_J$, since $D_J>e$. The pair $\{2,3\}$ cannot yield an additional rank-2 region: if both are at least $e$, then $T_1^J>T_2^J\geq e$ and rank 3 qualifies. Alternatively, the necessary inequalities for that pair would give $Z\geq D_J>K\geq Z$, which is impossible here. Neither $[e,K]$ nor $[D_J,\infty)$ intersects $[L_J,U]$. Thus these are exactly the rank-2 rejection regions, and the rejected sets are respectively $\{1,3\}$ and $\{1,2\}$.

On $Z<e$, $T_1^J<e<a$ and $T_2^J<T_1^J$, whereas $T_3^J>c-e=K>a$, so precisely the alternative is rejected at rank 1. On the remaining intervals $(K,L_J)$ and $(U,D_J)$, the first observation exceeds $K>a$, ranks 3 and 2 fail, and only null 1 is rejected at rank 1. This exhausts the real line and also shows that $R_J=0$ never occurs. The exact finite-level partition, including its endpoints according to non-strict BH thresholds, is therefore:

| $Z$ region | BH rejection set | $R_J$ | $V_J$ | FDP |
| --- | --- | --- | --- | --- |
| $(-\infty,e)$ | $\{3\}$ | 1 | 0 | 0 |
| $[e,K]$ | $\{1,3\}$ | 2 | 1 | $1/2$ |
| $(K,L_J)$ | $\{1\}$ | 1 | 1 | 1 |
| $[L_J,U]$ | $\{1,2,3\}$ | 3 | 2 | $2/3$ |
| $(U,D_J)$ | $\{1\}$ | 1 | 1 | 1 |
| $[D_J,\infty)$ | $\{1,2\}$ | 2 | 2 | 1 |

Consequently the full FDR, including every possible rejection-count case, is
$$
\begin{aligned}
F_J(q)={}&0\cdot\Phi(e)+\frac12[\Phi(K)-\Phi(e)]
+[\Phi(L_J)-\Phi(K)]\\
&+\frac23[\Phi(U)-\Phi(L_J)]
+[\Phi(D_J)-\Phi(U)]+\overline\Phi(D_J)\\
={}&1-\frac12\Phi(K)-\frac12\Phi(e)-\frac13[\Phi(U)-\Phi(L_J)]\\
={}&\frac q3+\frac12\overline\Phi(K)-\frac13[\Phi(U)-\Phi(L_J)],
\end{aligned}
$$
where $\Phi(e)=1-2q/3$. Substituting the explicit $K,L_A,L_B,U$ gives both formulas in the Object section and subtracting gives the stated exact positive difference. This partition proof and the bound in P5 require only $a>e>d>0$, so establish the entire interval $q\in(0,1/2)$ without asymptotic or finite-grid assumptions.

As a supplementary algebra and implementation check, a deterministic unit check evaluated the six interval interiors in both models at $q\in\{0.499,0.1,0.001,10^{-8}\}$ with the original largest-rank BH definition, and compared the summed formula with its simplification. All checks passed. These checks are not used to establish any of P1--P6.
