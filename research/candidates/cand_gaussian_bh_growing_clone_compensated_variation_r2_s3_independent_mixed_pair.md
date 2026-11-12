---
type: candidate
title: >-
  Independent two-test fractional-null diagnostic satisfies the compensated
  formula
status: failed
target_asset: gaussian_bh_growing_clone_compensated_variation
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  H7: pass
  H8: pass
  H9: pass
  NOT: fail
mode: refute
round: 2
slot: 3
direction: idea_b79422ba062c
statement_digest: 46328f001bbe3459d7271829f214a45295c81cd70e93df51f95566dd3ccb4fc3
performed_by: unknown
created_at: '2026-11-08T22:56:18.570Z'
extension_version: 0.0.4
---

## Object

Set $N=d=2$, $\theta=(-1,1)$, $\Sigma=I_2$, $q=1/4$, $i=1$, and $v_1=e_1,v_2=e_2$. Thus $T_1=-1+Z_1$, $T_2=1+Z_2$ for independent standard normals. Use exactly the construction and original labels in the target: $I_0=\{1\}$, $K$ exact copies of coordinate 2, and $K$ compensated private Gaussian copies of coordinate 1. This settles the unfinished test case idea_b79422ba062c, rather than changing its parameters.

Write $u(x)=S^{-1}(qx/2)$, $u_r=u(r)$, $\alpha=\sqrt{1-s^2}$, $d=s(t_s+t_s^{-1})$, and
$$
m=-1+d+\alpha Z_1,\qquad b_m(x)=S((u(x)-m)/s),\qquad A(x)=S(u(x)-1).
$$
All limits below take $K\to\infty$ first for fixed sufficiently small positive $s$, followed by $s\downarrow0$.

## Checks

### H1

The original model is finite with integer $N=2\ge1$ and fixed means $(-1,1)\in\mathbb R^2$.

### H2

$\Sigma=I_2$ has unit diagonal and $z^{\mathsf T}\Sigma z=\|z\|^2>0$ for every nonzero $z\in\mathbb R^2$, so the original covariance is positive definite.

### H3

$q=1/4\in(0,1/2)$, the chosen index is $i=1\in[2]$, and $\theta_1=-1\ne0$.

### H4

$G=(Z_1,Z_2)\sim N_2(0,I_2)$ and $v_j=e_j$ give the required finite unit-row representation, with $v_j\cdot v_k=\Sigma_{jk}$.

### H5

The p-values are the one-sided values $S(T_j)$, the original true-null set is exactly $\{1\}$, and every procedure is ordinary largest-rank BH with non-strict inequalities. The calculations below retain both the null-only and the alternative-present branches and their common largest crossing.

### H6

For each integer $K\ge1$ use exactly $K$ copies of each group. Only group 1 changes, to
$$
T_{1b}=-1+d+\alpha Z_1+s\xi_b,
$$
where the $\xi_b$ are independent standard normals independent of $G$. This is precisely the prescribed normalized private-noise construction because $s=\varepsilon/\sqrt{1+\varepsilon^2}$ and $\alpha=1/\sqrt{1+\varepsilon^2}$.

### H7

For sufficiently small positive $s$, $s<\phi(0)$, $t_s>0$ is defined by $\phi(t_s)=s$, and $d\to0$. Restrict further to $d<1$. Then the expanded means are $-1+d<0$ and $1>0$, so the actual expanded true-null set is precisely $\{1\}\times[K]$. Every expanded marginal has variance $\alpha^2+s^2=1$ and the full expanded vector is jointly Gaussian.

### H8

The experiment uses the required iterated order of limits; no fixed-$K$ estimate is used to exchange limits. The inner limit is justified directly below by a conditional empirical argument.

### H9

Use the original signed coordinate-face measures. With $A_2=A(2)=S(u_2-1)$, direct largest-rank BH evaluation gives
$$
\Delta_{1,1}(Z_2)=\mathbf1\{1+Z_2<u_2\},\qquad
\Delta_{1,2}(Z_2)=\tfrac12\mathbf1\{1+Z_2\ge u_2\}
$$
outside null-probability endpoints. Indeed, at face $u_1$, an alternative already above $u_2$ makes the two-rejection decision insensitive to the face; otherwise crossing $u_1$ creates a null-only rejection. At face $u_2$, crossing creates two rejections exactly when the alternative is above $u_2$. Therefore
$$
\mu_{1,1}(\mathbb R)=\phi(u_1+1)(1-A_2),\qquad
\mu_{1,2}(\mathbb R)=\tfrac12\phi(u_2+1)A_2.
$$
These are the actual signed jumps, with both original labels retained.

### NOT

**Fails: both target conclusions hold for this object.** Here is an analytic check of the previously unresolved fractional-null diagnostic.

#### Exact population branch selection

For fixed $m$ let
$$
x_1(m)=\max\{x\in[1,2]:1+b_m(x)\ge x\}.
$$
This maximum exists in $(1,2)$: at 1 the inequality is strict and at 2 it fails. Continuity implies $1+b_m(x_1)=x_1$. Let $x_0(m)$ be the largest positive crossing of $b_m(x)\ge x$ on $(0,1]$, or 0 if there is none. Put
$$
M_1=\min_{0<x<1}\{u(x)-sS^{-1}(x)\}.
$$
The minimized function diverges to $+\infty$ at both endpoints when $s<1$, so the minimum is attained and $x_0>0$ if and only if $m\ge M_1$.

For a realized alternative score $y$, its exact group enters the population count at $a=2S(y)/q$. If $a\le x_1$, then $x_1$ is the common largest crossing. If $a>x_1$, no alternative-present crossing exists: any such crossing is at most $x_1$, where the alternative is still absent. Any null-only crossing is at most 1, hence below $a>x_1>1$, and the common largest crossing is $x_0$. Consequently the actual population FDP is
$$
D(m,y)=\mathbf1\{y\ge u(x_1)\}\frac{x_1-1}{x_1}
+\mathbf1\{y<u(x_1)\}\mathbf1\{m\ge M_1\}.
$$
The chosen null contributes its fractional mass $b_m(x_1)=x_1-1$. Averaging only over the independent alternative gives the exact expression
$$
g_s(m)=A(x_1(m))\frac{x_1(m)-1}{x_1(m)}
+[1-A(x_1(m))]\mathbf1\{m\ge M_1\}.
$$

#### Finite-copy convergence, including absence of a positive crossing

Conditional on $(m,y)$, replace $b_m$ by the empirical fraction $b_{K,m}$ of the private normal samples. The empirical distribution converges uniformly almost surely, hence $\sup_x|b_{K,m}(x)-b_m(x)|\to0$.

Except on a set of $(m,y)$ of probability zero, the selected positive population root is simple and is separated from the alternative-entry point $a$. To see the first exclusion, the root equation on a branch with $r-1$ exact groups is
$$
m=G_r(t):=u(r-S(t))+st,\qquad r=1,2.
$$
Each $G_r$ is analytic and its derivative is not identically zero; its critical points, and hence its critical values, form a countable set. The law of $m$ has a density. The second exclusion follows by conditioning on $m$ and using the continuous independent law of $y$. At a selected simple root, uniform empirical convergence and the strict crossings on its two sides give convergence of the largest empirical crossing to that root. Larger crossings cannot appear at a fixed distance away: on the corresponding compact sets the upper semicontinuous population count minus $x$ has a strictly negative maximum. At each positive selected root $H=\rho$; an entry jump with strict excess would extend the crossing to its right and cannot be the largest endpoint.

When the population crossing is zero, one also needs to exclude empirical rejections whose ranks vanish relative to $K$. For fixed $m$ and $s<1$, Gaussian tail asymptotics give
$$
b_m(x)=x^{1/s^2+o(1)}=o(x)\quad(x\downarrow0).
$$
Choose a sufficiently small fixed $\delta<a$ so $b_m(x)/x\le\kappa<1$ on $(0,\delta]$. At rank $\ell\le\delta K$, a crossing requires $\operatorname{Bin}(K,b_m(\ell/K))\ge\ell$. For $\ell\ge L$, the Chernoff bound is at most $\exp(-c_\kappa\ell)$, uniformly in $K$; their sum tends to zero as $L\to\infty$. For the finitely many $\ell<L$, the union bound is at most $K b_m(L/K)\to0$. On $[\delta,2]$ the strict population gap and uniform convergence exclude a crossing. Thus the conditional probability of any finite-copy rejection tends to zero in the zero-crossing case as well.

For a positive limiting crossing the empirical null fraction converges to $b_m(\rho)$ and the exact alternative indicator is stable. The finite-copy FDP therefore converges in probability to the displayed $D$. Since FDP is bounded by 1, conditional convergence and bounded convergence yield
$$
\lim_{K\to\infty}F_{K,\varepsilon}=\mathbb E D.
$$
This proves the first target conclusion for this object, rather than assuming the population representation.

#### Root births and the fractional-FDP remainder

Define
$$
c(x)=-u'(x)=\frac{2}{q\phi(u(x))},\qquad c_r=c(r)=\frac1{r h(u_r)}.
$$
On $[1,2]$, $c$ is positive, smooth and decreasing, since $u(x)>0$. For $r=1,2$ and positive $t$, the derivative of $G_r$ is
$$
G_r'(t)=s-c(r-S(t))\phi(t).
$$
The product subtracted from $s$ is strictly decreasing for $t>0$. For small $s$ there is a unique positive minimum point $t_r$, satisfying
$$
c(r-S(t_r))\phi(t_r)=s.
$$
For $r=1$ this is also the global minimum defining $M_1$. Indeed $u(\Phi(t))\ge-t$ for $t\le0$. Large negative $t$ therefore give $G_1(t)\ge(1-s)|t|$, while on any remaining compact negative interval $u(\Phi(t))\ge u(1/2)>u_1$. Their values exceed the positive minimum for all sufficiently small $s$.

Set $M_2=G_2(t_2)$. This is the minimum on $t\ge0$ for the alternative-present branch; it is the birth of its high root. For $m\ge M_2$ the largest root is
$$
x_1(m)=2-S(t),\quad t\ge t_2,\quad m=G_2(t).
$$
For $m<M_2$ there is no root with $t\ge0$, so $x_1<3/2$. Since $M_2\to u_2<u(3/2)$,
$$
0<x_1-1=b_m(x_1)\le S((u(3/2)-M_2)/s)=O(e^{-c/s^2}).
$$
Also $M_1>M_2$ for small $s$. Thus the exact $g_s$ is exponentially small below $M_2$.

Above $M_2$, the difference of $g_s$ from the two-step function
$$
\frac{A_2}{2}\mathbf1\{m\ge M_2\}+(1-A_2)\mathbf1\{m\ge M_1\}
$$
is bounded in absolute value by $C(2-x_1)$, because $A$ and $(x-1)/x$ have bounded derivatives on $[3/2,2]$. The density of $m$ is uniformly bounded for small $s$. On the high branch $0\le G_2'(t)\le s$, so its integrated contribution is at most
$$
C\int_{M_2}^{\infty}(2-x_1(m))\,dm
\le Cs\int_{t_2}^{\infty}S(t)\,dt
\le Cs\frac{\phi(t_2)}{1+t_2^2}
=O(s^2/t_s^2).
$$
The last inequality follows from $\int_a^\infty S(t)dt=\phi(a)-aS(a)$ and the lower Mills bound $S(a)\ge a\phi(a)/(1+a^2)$. The critical equation implies $\phi(t_2)=O(s)$ and $t_2\sim t_s$. Therefore, with $\lambda=s/t_s$,
$$
F_{\infty,\varepsilon}
=\frac{A_2}{2}\Pr\{m\ge M_2\}
+(1-A_2)\Pr\{m\ge M_1\}+o(\lambda).
$$
In particular the fractional-copy FDP has not been discarded pointwise: its entire integrated error has just been bounded at a smaller scale.

#### Compensated expansion

The critical equations and Gaussian Mills expansion give, for $r=1,2$,
$$
t_r^2=t_s^2+2\log c(r-S(t_r)),\qquad
t_r=t_s+\frac{\log c_r}{t_s}+o(t_s^{-1}),
$$
$$
S(t_r)=\frac{s}{c_r t_s}(1+o(1)),\qquad
M_r=u_r+st_s+\frac{s}{t_s}(1+\log c_r)+o(s/t_s).
$$
Thus $M_r-d=u_r+\lambda\log c_r+o(\lambda)$. Since $1-\alpha=O(s^2)=o(\lambda)$,
$$
\Pr\{m\ge M_r\}
=S(u_r+1)+\lambda\phi(u_r+1)\log(rh(u_r))+o(\lambda).
$$
The original conditional FDP averaged over the alternative is
$$
\frac{A_2}{2}\mathbf1\{T_1\ge u_2\}+(1-A_2)\mathbf1\{T_1\ge u_1\}.
$$
Subtracting its expectation gives precisely
$$
\lim_{\varepsilon\downarrow0}\frac{F_{\infty,\varepsilon}-F}{s/t_s}
=\sum_{r=1}^2\log(rh(u_r))\mu_{1,r}(\mathbb R).
$$
A short scalar computation gives $u_1=1.1503493803760079$, $u_2=0.6744897501960817$, $A_2=0.6276025367807749$, face masses $0.014717274962823724$ and $0.03081074175216178$, and coefficient $0.03608922386092275$. These numerical values only check the displayed exact formulas; the limit is established by the preceding bounds.

## Failure

NOT fails: the original independent mixed-label two-test diagnostic has the finite-copy population limit and exactly the claimed compensated coefficient, with its fractional-null mass and both root births retained.
