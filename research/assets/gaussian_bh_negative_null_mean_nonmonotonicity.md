---
type: construction
title: Three-test Gaussian BH nonmonotonicity under lowering a negative null mean
status: approved
source:
  kind: original
depends_on: []
uses_definitions:
  - gaussian_multiple_testing_model
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
  - false_discovery_rate
tags:
  - gaussian_bh
  - one_sided
  - negative_null_means
  - local_nonmonotonicity
---

## Statement

For every testing level $q\in(0,1/2)$, construct an explicit pair of three-test Gaussian models with the following properties. All parameters may depend on $q$.

- P1: There is a common matrix $\Sigma(q)\in\mathcal C_3$, where $\mathcal C_3$ is the set of positive-semidefinite correlation matrices in the [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md). The observations $T^A\sim\mathcal N_3(\theta^A,\Sigma(q))$ and $T^B\sim\mathcal N_3(\theta^B,\Sigma(q))$ are each exactly jointly Gaussian, with unit marginal variances; singular $\Sigma(q)$ is allowed.
- P2: The mean vectors have the form $\theta^A=(0,b,c)$ and $\theta^B=(0,b',c)$ with $b'<b<0$ and $c>0$. Thus only the second mean is lowered between two strictly negative values, the first mean remains zero, the positive alternative mean and the entire covariance matrix are fixed between the two models, and both models have the same one-sided true-null set $I_0^{(1)}=\{1,2\}$ under the [Gaussian test p-values and true nulls](../definitions/gaussian_test_pvalues.md).
- P3: For $J\in\{A,B\}$, use the one-sided p-values $p_i^J=\overline\Phi(T_i^J)$, $i\in\{1,2,3\}$, and the [ordinary Benjamini-Hochberg step-up procedure](../definitions/benjamini_hochberg_step_up.md) at the same level $q$. Let $R_J=|\mathcal R_q(p^J)|$ and $V_J=|\mathcal R_q(p^J)\cap\{1,2\}|$, and define the total [false discovery rate](../definitions/false_discovery_rate.md) by $F_J(q)=\mathbb E[V_J/(R_J\vee1)]$, with expectation under model $J$.
- P4: Lowering the strictly negative second null mean strictly increases the total FDR: $F_B(q)>F_A(q)$ for every $q\in(0,1/2)$.
- P5: Both FDRs remain at or below the nominal level: $F_A(q)\leq q$ and $F_B(q)\leq q$ for every $q\in(0,1/2)$.
- P6: Give exact finite-level formulas for $F_A(q)$, $F_B(q)$, and their difference, with every parameter and Gaussian distribution-function argument explicit, and an analytic verification of P4 and P5 for the entire interval $q\in(0,1/2)$. The formulas must evaluate the full BH FDR, including every rejection-count case, rather than only one null's rejection probability or an asymptotic or simulation estimate.

## Scope

The requested object refutes coordinatewise local monotonicity of one-sided Gaussian BH FDR when the second null mean is lowered between strictly negative values while the first null mean remains zero. P5 is part of the specification: this construction does not assert a violation of nominal FDR control or settle the separate unrestricted zero-mean least-favorability question. No candidate object or proof is asserted here; the construction must be found and verified after the researcher approves these properties.

## Construction

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

## Proof

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

Found by search candidate cand_gaussian_bh_negative_null_mean_nonmonotonicity_r1_s1_quantile_triple (round 1) and verified independently.
