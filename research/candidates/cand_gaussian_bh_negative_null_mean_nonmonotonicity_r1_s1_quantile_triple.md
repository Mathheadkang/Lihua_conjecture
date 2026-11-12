---
type: candidate
title: >-
  Quantile-separated Gaussian triple with increasing FDR under a negative null
  shift
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
slot: 1
direction: idea_8757076e592d
statement_digest: 9f2cf4094f405ea7ab6e91647d7c2eae547e583022c0a0ab42e0071b8242fa50
performed_by: unknown
created_at: '2026-11-04T12:37:56.077Z'
extension_version: 0.0.4
---

## Object

Fix an arbitrary $q\in(0,1/2)$. Write $Q=\overline\Phi$ and define the inverse by $Q(Q^{-1}(p))=p$, for $p\in(0,1)$. Set
$$
u=Q^{-1}(q),\qquad v=Q^{-1}(2q/3),\qquad w=Q^{-1}(q/3),
$$
$$
B=w+\frac14,\qquad \delta=\frac{v-u}{2},\qquad C=B+2\delta=B+v-u,\qquad \mu=B+v,
$$
$$
t_A=B+\frac{\delta}{2}-u,\qquad t_B=B+\frac{3\delta}{2}-u.
$$
For a single $Z\sim\mathcal N(0,1)$ define
$$
T^A=(Z,Z-t_A,\mu-Z),\qquad T^B=(Z,Z-t_B,\mu-Z).
$$
Thus the requested parameters are
$$
\Sigma(q)=\begin{pmatrix}1&1&-1\\1&1&-1\\-1&-1&1\end{pmatrix},\qquad
b=-t_A,\quad b'=-t_B,\quad c=\mu.
$$
The common-$Z$ representation is a coupling for the calculation; its two marginals are the requested models.

## Checks

### P1

Put $s=(1,1,-1)^{\mathsf T}$. The displayed matrix equals $ss^{\mathsf T}$, has unit diagonal, and satisfies
$$
x^{\mathsf T}\Sigma(q)x=(x_1+x_2-x_3)^2\geq0.
$$
Each centered observation is $sZ$, so every linear combination is centered normal with variance $(a_1+a_2-a_3)^2$, including variance zero. Both observations are exactly jointly Gaussian with covariance $\Sigma(q)\in\mathcal C_3$ and unit marginal variances.

### P2

Since $0<q/3<2q/3<q<1/2$ and $Q$ is strictly decreasing,
$$
0<u<v<w<B,\qquad \delta>0.
$$
In particular, $t_A>B-u>0$ and $t_B=t_A+\delta>t_A$. Also $\mu=B+v>0$. Hence
$$
b'=-t_B<b=-t_A<0<c=\mu.
$$
The mean vectors are exactly $(0,b,c)$ and $(0,b',c)$. Only the second mean changes. The common one-sided true-null set is $\{1,2\}$.

### P3

For either $t\in\{t_A,t_B\}$, use
$$
T(t)=(Z,Z-t,\mu-Z),\qquad p(t)=(Q(Z),Q(Z-t),Q(\mu-Z)).
$$
Apply ordinary largest-qualifying-rank BH at level $q$. Its statistic thresholds at ranks $1,2,3$ are respectively $w,v,u$. Let
$$
a=t+u,\qquad h=t+v.
$$
For these two choices of $t$,
$$
a_A=B+\frac\delta2,\qquad a_B=B+\frac{3\delta}2,
$$
and both satisfy
$$
v<w<B<a<C<h.
$$
Indeed $B<a<C$ follows from $\delta>0$, and $h=a+v-u=a+2\delta>C$ follows from $a>B$. These strict inequalities hold for every $q\in(0,1/2)$.

For $k=1,2,3$, let $E_k$ be the event that rank $k$ qualifies. Directly counting statistics at or above their rank threshold gives
$$
E_3=\{a\leq Z\leq C\},
$$
$$
E_2=\{v\leq Z\leq B\}\ \cup\ \{Z\geq h\},
$$
$$
E_1=\{Z\leq\mu-w\}\ \cup\ \{Z\geq w\}.
$$
For $E_2$, the pair $(1,3)$ qualifies exactly on $[v,B]$, the pair $(1,2)$ exactly on $[h,\infty)$, and the pair $(2,3)$ would require $h\leq Z\leq B$, which is empty. For $E_1$, coordinate 2 is redundant because $t>0$. Moreover $\mu-w=v+1/4>v$ and $B>w$.

Taking the largest qualifying rank, rather than stopping at the first qualifying rank, therefore gives the following exhaustive table. The rejection sets are obtained at the chosen BH threshold. Brackets specify exact endpoints, including threshold equalities.

| Value of $Z$ | $R$ | Rejection set | $V$ | FDP |
| --- | --- | --- | --- | --- |
| $Z<v$ | $1$ | $\{3\}$ | $0$ | $0$ |
| $v\leq Z\leq B$ | $2$ | $\{1,3\}$ | $1$ | $1/2$ |
| $B<Z<a$ | $1$ | $\{1\}$ | $1$ | $1$ |
| $a\leq Z\leq C$ | $3$ | $\{1,2,3\}$ | $2$ | $2/3$ |
| $C<Z<h$ | $1$ | $\{1\}$ | $1$ | $1$ |
| $Z\geq h$ | $2$ | $\{1,2\}$ | $2$ | $1$ |

There is no $R=0$ region: below $v$ coordinate 3 already qualifies at rank 1; $[v,B]$ qualifies at rank 2; and above $B$ coordinate 1 already qualifies at rank 1. Thus all rejection-count cases are included, with the empty-rejection case having probability zero.

Since the Gaussian law has no atoms, integrating this table gives the full FDR
$$
\begin{aligned}
F(t)
&=\frac12[Q(v)-Q(B)]+[Q(B)-Q(a)]
  +\frac23[Q(a)-Q(C)]\\
&\quad+[Q(C)-Q(h)]+Q(h)\\
&=\frac q3+\frac12Q(B)-\frac13Q(a)+\frac13Q(C).
\end{aligned}
$$
Here the last two summands in the first expression are respectively the entire $R=1$ region above $C$ and the upper $R=2$ region. Their sum is $Q(C)$, so neither rejection-count case has been omitted.

### P4

Substituting $a_A=B+\delta/2$ and $a_B=B+3\delta/2$ into the full FDR formula yields
$$
F_B(q)-F_A(q)
=\frac13\left[Q\left(B+\frac\delta2\right)-Q\left(B+\frac{3\delta}2\right)\right]>0.
$$
The inequality is strict because $\delta>0$ and $Q$ is strictly decreasing at every finite real argument. All arguments are finite for each $q\in(0,1/2)$, so this proves the strict inequality throughout the required interval.

Equivalently, the FDP changes only on the nonempty interval $(a_A,a_B)$: the first model has FDP $2/3$ there, while the lowered-mean model has FDP $1$. Integrating the increase $1/3$ over that interval gives the same expression. Endpoint differences have probability zero.

### P5

The exhaustive table shows that the FDP is zero for $Z<v$ and never exceeds one. Consequently, for either model,
$$
F_J(q)\leq\Pr\{Z\geq v\}=Q(v)=\frac{2q}{3}<q,\qquad J\in\{A,B\}.
$$
This analytic bound holds for every $q\in(0,1/2)$ and uses the full FDP, including rejection of either or both true nulls.

### P6

For explicit Gaussian distribution-function arguments define the following three functions of $q$:
$$
u=Q^{-1}(q),\qquad v=Q^{-1}(2q/3),\qquad w=Q^{-1}(q/3).
$$
Then every parameter in the construction is explicitly
$$
\begin{aligned}
b&=u-w-\frac14-\frac{v-u}{4},\\
b'&=u-w-\frac14-\frac{3(v-u)}{4},\\
c&=w+\frac14+v,\\
\Sigma(q)&=\begin{pmatrix}1&1&-1\\1&1&-1\\-1&-1&1\end{pmatrix}.
\end{aligned}
$$
The exact finite-level full FDRs are
$$
\begin{aligned}
F_A(q)&=\frac q3+\frac12Q\left(w+\frac14\right)
-\frac13Q\left(w+\frac14+\frac{v-u}{4}\right)
+\frac13Q\left(w+\frac14+v-u\right),\\
F_B(q)&=\frac q3+\frac12Q\left(w+\frac14\right)
-\frac13Q\left(w+\frac14+\frac{3(v-u)}{4}\right)
+\frac13Q\left(w+\frac14+v-u\right),\\
F_B(q)-F_A(q)&=\frac13\left[
Q\left(w+\frac14+\frac{v-u}{4}\right)
-Q\left(w+\frac14+\frac{3(v-u)}{4}\right)\right].
\end{aligned}
$$
These are one-dimensional Gaussian survival-function formulas with every argument given by explicit normal quantiles and constants. The largest-rank table and integration in P3 prove that they evaluate the total BH FDR. P4 and P5 prove respectively strict increase and nominal control on the entire open interval; neither proof uses limits or simulation.

As a diagnostic independent of the algebra, a short standard-library Python check evaluated the actual largest BH rank and rejection set at an interior point of each of the six regions, for both models, at $q\in\{10^{-12},10^{-6},0.001,0.01,0.1,0.3,0.49,0.499999999\}$. All 96 region checks matched the table. Integrating all six region probabilities agreed with the displayed formula to maximum absolute floating error $5.6\times10^{-17}$. These finite checks are supplementary diagnostics; the interval-wide verification is the analytic argument above.

## Verdict

confirmed

### P1

Fix an arbitrary $q\in(0,1/2)$. Throughout this verification,
$Q=\overline\Phi$, $\Phi=1-Q$, and
$\varphi(z)=(2\pi)^{-1/2}\exp(-z^2/2)$. Since $Q$ is continuous and
strictly decreasing from $1$ to $0$, the three quantiles in the object
are finite and satisfy
$$
0<u<v<w,\qquad Q(u)=q,\qquad Q(v)=2q/3,\qquad Q(w)=q/3.
$$
Write $s=(1,1,-1)^{\mathsf T}$. The proposed covariance is
$\Sigma=ss^{\mathsf T}$. Hence it is symmetric, its diagonal entries
are one, and
$$
x^{\mathsf T}\Sigma x=(x_1+x_2-x_3)^2\geq0
$$
for every $x\in\mathbb R^3$. Thus $\Sigma\in\mathcal C_3$.
For either $J$, the centered proposed vector is exactly $sZ$:
its every linear combination is centered Gaussian with variance
$x^{\mathsf T}\Sigma x$, including the constant zero when this
variance vanishes. Consequently these are exactly jointly Gaussian
models with unit marginal variances and the same admissible,
rank-one covariance.

### P2

Put $d=v-u=2\delta>0$. The parameters in the object are equivalently
$$
B=w+\frac14,\qquad C=B+d,\qquad
t_A=B+\frac d4-u,\qquad
t_B=B+\frac{3d}4-u,\qquad
\mu=B+v.
$$
In particular,
$$
t_A>B-u>w-u>0,\qquad t_B-t_A=\frac d2>0,\qquad \mu>0.
$$
Taking expectations in the two proposed affine representations gives
$\theta^A=(0,-t_A,\mu)$ and $\theta^B=(0,-t_B,\mu)$.
Thus $b'=-t_B<b=-t_A<0$, $c=\mu>0$, and only the second
mean changes. The first two means are nonpositive and the third is
strictly positive, so the one-sided true-null set is exactly
$\{1,2\}$ in both models.

### P3

The following verifies the largest qualifying BH rank directly,
including the case where a larger rank qualifies although a smaller
one need not. Let $t$ be either $t_A$ or $t_B$, and set
$$
a=t+u,\qquad
a_A=B+\frac d4,\qquad a_B=B+\frac{3d}4.
$$
Both choices obey
$$
v<w<B<a<C<a+d.
$$
The rank-$1$, rank-$2$, and rank-$3$ BH p-value thresholds are
$q/3$, $2q/3$, and $q$, respectively, and their corresponding
test-statistic thresholds are $w$, $v$, and $u$.

Rank $3$ qualifies exactly when all three statistics are at least
$u$. Since $t>0$, the first statistic is then automatically above
$u$ if the second is. Therefore the exact event is
$$
t+u\leq Z\leq \mu-u,\quad\hbox{that is,}\quad a\leq Z\leq C.
$$
Rank $2$ qualifies exactly when at least two statistics are at least
$v$. For the pair $\{1,3\}$ this event is
$v\leq Z\leq\mu-v=B$, and for the pair $\{1,2\}$ it is
$Z\geq t+v=a+d$. The pair $\{2,3\}$ would require both
$Z\geq a+d$ and $Z\leq B$, which is impossible. Thus the
rank-$2$ qualification event is exactly
$$
[v,B]\ \cup\ [a+d,\infty).
$$
These intervals are disjoint from $[a,C]$, so rank $2$ is the largest
qualifying rank on both of them.

Finally, because the second statistic is below the first, rank $1$
qualifies exactly when
$$
Z\geq w\quad\hbox{or}\quad Z\leq\mu-w=v+\frac14.
$$
Here $v<v+1/4<B$ and $B>w$. These facts prove the following complete
partition. The displayed rejection sets follow by applying the
threshold at the largest qualifying rank, not by using the smallest
p-value alone.

| Value of $Z$ | Largest rank and $R$ | Rejection set | $V$ | FDP |
| --- | --- | --- | --- | --- |
| $Z<v$ | $1$ | $\{3\}$ | $0$ | $0$ |
| $v\leq Z\leq B$ | $2$ | $\{1,3\}$ | $1$ | $1/2$ |
| $B<Z<a$ | $1$ | $\{1\}$ | $1$ | $1$ |
| $a\leq Z\leq C$ | $3$ | $\{1,2,3\}$ | $2$ | $2/3$ |
| $C<Z<a+d$ | $1$ | $\{1\}$ | $1$ | $1$ |
| $a+d\leq Z$ | $2$ | $\{1,2\}$ | $2$ | $1$ |

For example, on each rank-$1$ interval above $B$, the third
statistic is below $w$ because $\mu-w<B$, and the second is below
$w$ because $t+w=a+(w-u)>a+d$. On $Z<v$, the first and second
statistics are below $w$, whereas the third exceeds $w$.
Thus the rejection sets in all rank-$1$ cases are exact as well.
There is no $R=0$ region. The table includes the threshold endpoints;
their probability is zero under the continuous standard normal law.

It follows from the entire partition, using the fixed true-null set
$\{1,2\}$, that the requested total FDR at parameter $a$ is
$$
F(a)
=\frac12\{\Phi(B)-\Phi(v)\}
 +\{\Phi(a)-\Phi(B)\}
 +\frac23\{\Phi(C)-\Phi(a)\}
 +\{\Phi(a+d)-\Phi(C)\}
 +Q(a+d).
$$
This includes every rejection-count case and both true nulls.
In particular, $F_A(q)=F(a_A)$ and $F_B(q)=F(a_B)$ with the
p-values and ordinary BH rule specified in P3.

### P4

The full-FDR expression in P3 simplifies exactly to
$$
F(a)
=1-\frac12\Phi(B)-\frac12\Phi(v)
  +\frac13\Phi(a)-\frac13\Phi(C)
=\frac q3+\frac12Q(B)+\frac13\{Q(C)-Q(a)\},
$$
where $Q(v)=2q/3$ was used in the last equality.
Everything except $a$ is fixed between the two models. Hence
$$
F_B(q)-F_A(q)
=\frac{Q(a_A)-Q(a_B)}3
=\frac13\int_{a_A}^{a_B}\varphi(z)\,dz>0.
$$
The integration interval has length $a_B-a_A=d/2>0$ and the
integrand is strictly positive everywhere. This proves the strict
increase for every $q\in(0,1/2)$, without any limiting or numerical
argument. By P2 the mean shift producing it is between two strictly
negative second-null means.

### P5

For either $J$, the strict inequalities $a_J<C$ and $B>w$ give
$Q(C)-Q(a_J)<0$ and $Q(B)<Q(w)=q/3$. Consequently
$$
F_J(q)
<\frac q3+\frac12Q(B)
<\frac q3+\frac q6
=\frac q2<q.
$$
The FDR is nonnegative by its expectation definition (and is in fact
positive because the interval $[v,B]$ in P3 has positive Gaussian
probability). Thus both requested nominal upper bounds hold
analytically on the whole specified interval.

### P6

All quantities below are explicit functions of the given level:
$$
u=Q^{-1}(q),\qquad
v=Q^{-1}(2q/3),\qquad
w=Q^{-1}(q/3),\qquad d=v-u>0.
$$
The means are
$$
b=u-w-\frac14-\frac d4,\qquad
b'=u-w-\frac14-\frac{3d}4,\qquad
c=w+\frac14+v,
$$
and the common covariance is the matrix verified in P1. Substituting
$B=w+1/4$, $C=w+1/4+d$, $a_A=w+1/4+d/4$, and
$a_B=w+1/4+3d/4$ into the independently evaluated total FDR gives
the exact finite-level formulas
$$
F_A(q)
=\frac q3+\frac12Q\!\left(w+\frac14\right)
 +\frac13\left[
 Q\!\left(w+\frac14+d\right)
 -Q\!\left(w+\frac14+\frac d4\right)
 \right],
$$
$$
F_B(q)
=\frac q3+\frac12Q\!\left(w+\frac14\right)
 +\frac13\left[
 Q\!\left(w+\frac14+d\right)
 -Q\!\left(w+\frac14+\frac{3d}4\right)
 \right],
$$
$$
F_B(q)-F_A(q)
=\frac13\left[
 Q\!\left(w+\frac14+\frac d4\right)
 -Q\!\left(w+\frac14+\frac{3d}4\right)
 \right].
$$
Every Gaussian argument is thereby specified through the three
displayed inverse-survival quantiles and the constant $1/4$.
P3 derives these formulas from all possible BH rejection sets; P4
proves strict positivity of their difference; and P5 proves the
uniform bound $F_J(q)<q/2<q$. All arguments apply to each finite
$q\in(0,1/2)$ and require no unproved quantile-spacing estimate,
finite grid check, simulation, or asymptotic approximation.
