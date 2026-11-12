---
type: candidate
title: Rank-one Gaussian construction using an antithetic alternative
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
slot: 4
direction: products_limits
statement_digest: 9f2cf4094f405ea7ab6e91647d7c2eae547e583022c0a0ab42e0071b8242fa50
performed_by: unknown
created_at: '2026-11-04T12:37:56.077Z'
extension_version: 0.0.4
---

## Object

Fix any $q\in(0,1/2)$. Let $\Phi$ denote the standard normal distribution function and set
$$
a=\Phi^{-1}(1-q),\qquad d=\Phi^{-1}(1-2q/3),\qquad e=\Phi^{-1}(1-q/3),\qquad \delta=(d-a)/2.
$$
Thus $0<a<d<e$ and $\delta>0$. Define
$$
b=a-e,\qquad b'=a-e-2\delta,\qquad c=e+a+\delta,
$$
$$
\Sigma=\begin{pmatrix}1&1&-1\\1&1&-1\\-1&-1&1\end{pmatrix}.
$$
For a standard normal variable $Z$, the two models have the realizations
$$
T^A=(Z,Z+b,c-Z),\qquad T^B=(Z,Z+b',c-Z).
$$
Use the specified one-sided p-values and ordinary BH procedure with three tests and level $q$ in each model. These are distributions of two models with the same covariance, and a common $Z$ is just a convenient coupling.

For the exact formulas, define
$$
K(q)=\max\{\Phi(e-\delta)-\Phi(d),0\},\qquad M(q)=\Phi(e+\delta)-\Phi(e).
$$
All symbols in these Gaussian arguments are the explicit quantiles given above. The resulting full FDRs and their difference are
$$
F_A(q)=\frac{K(q)}2+\frac23M(q)+1-\Phi(e+\delta),
$$
$$
F_B(q)=\frac{K(q)}2+1-\Phi(e)=\frac{K(q)}2+\frac q3,
$$
$$
F_B(q)-F_A(q)=\frac13M(q)>0.
$$

## Checks

### P1

Put $v=(1,1,-1)^{\mathsf T}$. Then $\Sigma=vv^{\mathsf T}$ has diagonal entries one and is positive semidefinite because $x^{\mathsf T}\Sigma x=(v^{\mathsf T}x)^2\geq0$. Each displayed model is an affine image of $Z$, so is exactly jointly Gaussian with the displayed mean and covariance; for every vector $x$, $x^{\mathsf T}(T^J-\theta^J)=(x_1+x_2-x_3)Z$. In particular each marginal variance is one. The rank-one singularity is allowed.

### P2

Since $a<e$ and $\delta>0$, $b'<b<0$. Also $c=e+a+\delta>0$. The mean vectors are exactly $(0,b,c)$ and $(0,b',c)$; their common one-sided true-null set is therefore $\{1,2\}$. Only the second mean changes.

### P3

Set $p_i^J=1-\Phi(T_i^J)$. For three tests, the BH critical values in statistic coordinates at ranks one, two, and three are $e,d,a$, respectively. Thus BH has rank three precisely when all three statistics are at least $a$; otherwise it has rank two precisely when at least two statistics are at least $d$; otherwise it has rank one precisely when at least one statistic is at least $e$; otherwise it has rank zero. This implements the largest qualifying rank, including its non-strict boundary convention. The exact partition below counts both true-null rejections and the alternative rejection, and uses $V/(R\vee1)$.

### P4

The partition and exact evaluation in P6 show
$$
F_B-F_A=\frac13\{\Phi(e+\delta)-\Phi(e)\}.
$$
For every $q$ in the whole specified interval, $\delta>0$ and both endpoints are finite; the normal density is strictly positive between them. Hence this difference is strictly positive. The affected interval is $e<Z<e+\delta$: model A rejects all three tests with FDP $2/3$, whereas model B rejects only the first true null with FDP one. Outside this interval the two FDPs agree almost surely.

### P5

Because $e-\delta<e$,
$$
0\leq K(q)\leq\Phi(e)-\Phi(d)
=(1-q/3)-(1-2q/3)=q/3.
$$
Consequently the exact formula in P6 gives
$$
F_B\leq q/6+q/3=q/2<q.
$$
As P4 gives $F_A<F_B$, both FDRs are at most the nominal level for every $q\in(0,1/2)$.

### P6

Here is a full enumeration, including every possible rejection count. Write
$$
h=a+\delta=(a+d)/2,\qquad \ell=e-\delta=c-d,\qquad u=e+\delta=c-a,
$$
$$
D_A=d-b=e+2\delta,\qquad D_B=d-b'=e+4\delta.
$$
The relations needed below are $h<d<e<u<D_A<D_B$ and $\ell<e$; no comparison between $\ell$ and $d$ is assumed. Let $I=[d,\ell]$ if $\ell\geq d$, and let $I$ be empty otherwise. Normal interval endpoints have probability zero, so the open or closed endpoints in the following table do not affect its probabilities.

| Model | Region of $Z$ | $R$ | $V$ | FDP |
| --- | --- | --- | --- | --- |
| A or B | $Z\leq h$ | 1 | 0 | 0 |
| A or B | $Z\in I$ | 2 | 1 | $1/2$ |
| A or B | $h<Z<e$ and $Z\notin I$ | 0 | 0 | 0 |
| A | $e\leq Z\leq u$ | 3 | 2 | $2/3$ |
| A | $u<Z<D_A$ | 1 | 1 | 1 |
| A | $Z\geq D_A$ | 2 | 2 | 1 |
| B | $e\leq Z<D_B$ | 1 | 1 | 1 |
| B | $Z\geq D_B$ | 2 | 2 | 1 |

To verify exhaustiveness directly, the second statistic is always strictly below the first. In model A all three statistics reach the rank-three threshold $a$ exactly when $Z\geq a-b=e$ and $Z\leq c-a=u$, giving the stated rank-three interval. In model B they would require simultaneously $Z\geq a-b'=e+2\delta$ and $Z\leq u=e+\delta$, which is impossible.

For the rank-two threshold $d$, tests 1 and 3 both qualify exactly on $I$. Tests 1 and 2 both qualify exactly on $Z\geq D_J$. Tests 2 and 3 cannot both qualify: they would require $Z\geq D_J\geq e+2\delta$ and $Z\leq c-d=e-\delta$. The two possible rank-two regions are disjoint from the rank-three interval in A. On $I$ the rejected tests are 1 and 3, and on $Z\geq D_J$ the rejected tests are 1 and 2.

Outside those regions, the rank-one criterion is supplied by test 3 exactly when $Z\leq c-e=h$, and by test 1 exactly when $Z\geq e$; test 2 cannot supply it without test 1. Since $h<d$, the first region does not meet $I$. All remaining points have no rejection. This proves the table, including the zero-rejection regions and both types of two-rejection outcome.

Now $\Pr(Z\in I)=K(q)$ and $\Pr(e\leq Z\leq u)=M(q)$. Summing the table gives the full expectations
$$
\begin{aligned}
F_A
&=\frac12K(q)+\frac23M(q)
  +\Pr(u<Z<D_A)+\Pr(Z\geq D_A)\\
&=\frac12K(q)+\frac23M(q)+1-\Phi(e+\delta),\\
F_B
&=\frac12K(q)+\Pr(e\leq Z<D_B)+\Pr(Z\geq D_B)\\
&=\frac12K(q)+1-\Phi(e).
\end{aligned}
$$
Their difference is exactly $M(q)/3$. Every parameter, endpoint, and Gaussian argument is explicit in the quantiles of $q$, and P4 and P5 give analytic verification over the whole interval, without any asymptotic or simulation approximation.
