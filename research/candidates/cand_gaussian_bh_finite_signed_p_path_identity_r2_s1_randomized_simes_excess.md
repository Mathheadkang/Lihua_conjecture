---
type: candidate
title: Random residual crossing in a nonsingular two-null FDR excess model
status: failed
target_asset: gaussian_bh_finite_signed_p_path_identity
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  NOT: fail
mode: refute
round: 2
slot: 1
direction: known_counterexamples
statement_digest: d7a8a4f0b24ea902729e5f1f7788367f78c722f470f62ba2b0bf55c676594eec
performed_by: unknown
created_at: '2026-11-09T20:29:53.809Z'
extension_version: 0.0.4
---

## Object

Take $N=2$, $q=1/4$, $\theta=(0,0)$, and
$$
\Sigma=\begin{pmatrix}1&-1/2\\-1/2&1\end{pmatrix}.
$$
Use the original one-sided Gaussian p-values and ordinary non-strict BH. Both labels are true nulls. Set $a=u(q/2)$ and $b=u(q)$. For label 1, the independent residual is $Y=Z_2+Z_1/2\sim N(0,3/4)$, and the prescribed full path is
$$
T_1^1(t)=u(t),\qquad T_2^1(t)=Y-u(t)/2.
$$
For a finite residual value $y$, define
$$
c(y)=S(2(y-b)),\qquad d(y)=S(2(y-a)).
$$
The proposed attack is a finite-model FDR excess above $q$, with a continuously randomized jump location that can lie on either side of the clipping point $q/2$. Unlike the board's singular deterministic examples, the residual law is nondegenerate and the jump correction must be averaged over this random location. This does not address an unknown-universal-constant linear bound or the main order target.

## Checks

### H1

Pass: $N=2$ is a finite positive integer.

### H2

Pass: $\theta=(0,0)\in\mathbb R^2$, so the original null set is $I_0=\{1,2\}$ and no negative-mean null is removed or relabeled.

### H3

Pass: $\Sigma$ is symmetric with unit diagonal and eigenvalues $1/2$ and $3/2$. It is positive definite, hence an admissible covariance. Use exactly the centered jointly Gaussian observation with this covariance.

### H4

Pass: $q=1/4\in(0,1/2)$.

### H5

Pass: all p-values are $S(T_j)$, and the rejection count is the largest qualifying non-strict BH rank. On the full prescribed path, both p-values are at most $q$ precisely when $t\geq c(y)$, since $t<q$ already implies $T_1^1(t)>b$. Thus, away from event points,
$$
R_1(t)=
\begin{cases}
2,&t>c(y),\\
1,&t<c(y),\quad t<q/2,\\
0,&t<c(y),\quad t>q/2.
\end{cases}
$$
In the last case the second score is below $b<a$, so it cannot qualify as a singleton. At $t=c(y)\in(0,q)$ both coordinates meet the rank-two threshold and the actual non-strict rank is 2. At $t=q/2<c(y)$ the first label meets the rank-one threshold and the actual rank is 1. These equality conventions do not alter any interval integral.

### H6

Pass: $\operatorname{Cov}(Z_1,Y)=-1/2+1/2=0$, and joint Gaussianity gives independence. The residual variance is $3/4$, so the construction uses precisely the statement's conditional path, with both original labels retained. Its first coordinate is $u(t)$, and the second coordinate has slope $-1/2$ as a function of $u(t)$.

### NOT

Fail: the FDR excess is exactly reproduced by the claimed signed identity.

For every finite $y$, a measurable finite event set containing all threshold solutions and the interior clipping point is
$$
E_1(y)=\{q/2,c(y),d(y)\}\cap(0,q).
$$
Both path scores are nonconstant. These continuous functions of $y$ give a measurable finite event construction, and the resulting finite comparisons defining BH and $A_1$ are jointly measurable. On each complementary interval the actual $A_1$ is
$$
A_1(t)=
\begin{cases}
2t/q,&t<\min(c(y),q/2),\\
1,&q/2<t<c(y),\\
t/q,&c(y)<t<q,
\end{cases}
$$
where an empty interval is ignored. If $c(y)\geq q$, the first two cases cover $(0,q)$. Hence $A_1(0+)=0$, $A_1(q-)=1$, and the derivatives are respectively $2/q$, $0$, and $1/q$, exactly the stated rejection-indicator ratio. The extra threshold event $d(y)$ does not cause a net jump.

There is one downward net jump at $c(y)$ when $0<c(y)<q$, including when it coincides with $q/2$. Its magnitude is
$$
D(y)=
\begin{cases}
c(y)/q,&0<c(y)\leq q/2,\\
1-c(y)/q,&q/2<c(y)<q,\\
0,&c(y)\geq q.
\end{cases}
$$
There is no separate net jump at $q/2$ when the two points differ. Thus $0\leq D\leq1/2$, so the finite jump sum is absolutely integrable.

Here $g_1\equiv1$, the Stieltjes integral vanishes, and the baseline is exactly 1. Conditional on $Y=y$, $t=S(Z_1)$ remains uniform on $(0,1)$ and label 1 cannot be rejected for $t>q$. Direct integration of the actual BH contribution gives
$$
\mathbb E\left[\frac{\mathbf1\{1\text{ rejected}\}}{R\vee1}\,\middle|\,Y=y\right]
=
\begin{cases}
c(y)+(q-c(y))/2,&c(y)\leq q/2,\\
q/2+(q-c(y))/2,&q/2<c(y)<q,\\
q/2,&c(y)\geq q,
\end{cases}
=\frac q2\{1+D(y)\}.
$$
This is exactly the claimed formula for $F_1$. Exchangeability gives the same calculation for label 2, hence
$$
F=q\{1+\mathbb E D(Y)\}>q.
$$
The strict inequality follows because $D(y)>0$ for every finite $y>3b/2$, a set of positive Gaussian probability. Both positive budgets equal $D$, so the statement's final bound holds with equality. All conclusions therefore hold in this object, despite the finite-model FDR excess.

As a noncertified numerical diagnostic, composite Simpson integration against the $N(0,3/4)$ density, split at $3b/2$ and $b+a/2$ and truncated at 12 residual standard deviations, gives $\mathbb E D\approx0.02611036584$ and $F\approx0.25652759146$. Doubling the panel count from 1000 to 2000 changes the displayed FDR by about $4.1\times10^{-11}$; this is a numerical stability check, not a rigorous quadrature error bound. The exact formulas above establish the candidate's failure without numerical approximation.

## Failure

NOT is the first failing check: the random downward-jump correction exactly accounts for the nonsingular model's FDR excess, and every other conclusion holds.
