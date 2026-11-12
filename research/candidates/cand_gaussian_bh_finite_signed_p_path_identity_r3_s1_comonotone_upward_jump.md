---
type: candidate
title: Perfect positive dependence with a genuine upward clipped-path jump
status: failed
target_asset: gaussian_bh_finite_signed_p_path_identity
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  NOT: fail
mode: refute
round: 3
slot: 1
direction: boundary_degenerate
statement_digest: d7a8a4f0b24ea902729e5f1f7788367f78c722f470f62ba2b0bf55c676594eec
performed_by: unknown
created_at: '2026-11-09T20:33:21.062Z'
extension_version: 0.0.4
---

## Object

Set $N=2$, $q=1/4$, $a=q/4=1/16$, and
$$
c=u(a)-u(q)>0,\qquad
\theta=(0,-c),\qquad
\Sigma=\begin{pmatrix}1&1\\1&1\end{pmatrix}.
$$
Let $X\sim\mathcal N(0,1)$ and $T=(X,X-c)$. Both labels are original true nulls. This tests a genuine upward $A$ jump caused by perfect positive dependence and unequal means. The board's singular examples concern anticorrelation, downward jumps, or removable spikes; the present jump has the opposite sign and is not removable.

## Checks

### H1

$N=2$ is a finite positive integer.

### H2

$a,q\in(0,1)$ make $c$ finite; $a<q$ makes $c>0$. Hence $\theta\in\mathbb R^2$ and $I_0=\{1,2\}$.

### H3

$\Sigma$ is symmetric with unit diagonal and $v^{\mathsf T}\Sigma v=(v_1+v_2)^2\geq0$. The stated representation gives exactly $T\sim\mathcal N_2(\theta,\Sigma)$, including its singularity. For either conditioning label, both residuals are identically zero.

### H4

$q=1/4$ belongs to $(0,1/2)$. All counts below use the full two-coordinate path and the largest non-strict ordinary-BH rank, retaining both original labels.

### NOT

This check fails: both coordinate identities and the other stated conclusions hold.

For label $1$, the full score path is $(u(t),u(t)-c)$. Put $U=S(X)$, which is uniform on $(0,1)$. The rank is
$$
R_1(t)=\begin{cases}
2,&0<t\leq a,\\
1,&a<t\leq q/2,\\
0,&q/2<t<q.
\end{cases}
$$
Indeed, rank two qualifies exactly when $u(t)-c\geq u(q)$, equivalently $t\leq a$; after that the stronger coordinate qualifies at rank one exactly when $t\leq q/2$. Thus
$$
A_1(t)=\begin{cases}
t/q,&0<t\leq a,\\
2t/q,&a<t\leq q/2,\\
1,&q/2<t<q.
\end{cases}
$$
At $a$, the non-strict count chooses the left value, while the one-sided limits are $A_1(a^-)=1/4$ and $A_1(a^+)=1/2$. Therefore $J_1=\{a\}$ and the signed jump is $-1/4$. There is no jump at $q/2$. The slopes are respectively $1/q$, $2/q$, and zero, precisely the claimed rejection indicator divided by $q r_1(t)$, and the endpoint limits are zero and one.

The direct contribution is
$$
F_1=\frac a2+(q/2-a)=\frac q2-\frac a2=\frac{3}{32}.
$$
Here $g_1=1$, so the proposed right-hand side is exactly
$$
\frac q2(1-1/4)=\frac{3}{32}.
$$

For label $2$, the full score path is $(u(t)+c,u(t))$. Both coordinates have p-values at most $t<q$, so $R_2(t)=2$ throughout $(0,q)$ and $A_2(t)=t/q$. Its endpoints, derivative, and absence of jumps follow directly. Its weight is
$$
g_2(t)=\exp\{-c u(t)-c^2/2\}.
$$
It is continuous, nondecreasing, and tends to zero at zero. Integration by parts gives the baseline
$$
g_2(q)-\int_{(0,q)}\frac tq\,dg_2(t)
=\frac1q\int_0^q g_2(t)\,dt
=\frac{S(u(q)+c)}q=\frac aq=\frac14.
$$
For the last equality before $a/q$, the change of variable $t=S(x)$ turns the integral into $\int_{u(q)}^\infty\phi(x+c)\,dx$. The weaker coordinate is rejected exactly when $U\leq a$, then at rank two, giving $F_2=a/2=1/32$. The identity gives the same value $(q/2)(1/4)=1/32$.

All path objects here are deterministic after conditioning, hence jointly measurable. Each score is a nonconstant continuous strictly monotone function of $t$, so each of the four score-threshold equations has at most one solution. Their interior solutions together with $q/2$ form a finite deterministic measurable event set. The displayed formulas show affinity off that set and account for every actual net jump. Baselines are respectively $1$ and $1/4$. The signed sums are deterministic and absolutely integrable. Both positive downward-jump budgets vanish, so the resulting bound is $F=1/8\leq q\pi_0=1/4$.

## Failure

NOT is the first failing check: the genuine upward jump contributes exactly the negative signed correction needed to match $F_1$, while the other label's weighted baseline matches $F_2$.
