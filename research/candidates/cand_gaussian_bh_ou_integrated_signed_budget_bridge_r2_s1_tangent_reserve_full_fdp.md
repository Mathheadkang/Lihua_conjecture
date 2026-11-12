---
type: candidate
title: >-
  Tangent reserve positive-budget counterexample tested with the full FDP OU
  norm
status: failed
target_asset: gaussian_bh_ou_integrated_signed_budget_bridge
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  H7: pass
  NOT: fail
mode: refute
round: 2
slot: 1
direction: known_counterexamples
statement_digest: 3160ccfce0ac60cf0a63c60984ceea3c7d11be0f22bcea357fccd9ee0cfaf782
performed_by: unknown
created_at: '2026-11-09T22:02:23.534Z'
extension_version: 0.0.4
---

## Object

This tests the actual family in the approved example `cx_gaussian_bh_positive_p_path_jump_budget_r4_s3_tangent_reserve_reset`, retrieved by native `show --section Statement` to check whether a counterexample to the related positive-budget statement also refutes this bridge. It does not replace the full FDP by that budget. The board has not tested this growing-number-of-groups family for the present target.

Write $S=\overline\Phi$ and $u=S^{-1}$. Fix
$$
q=S(1),\quad a=-4/5,\quad b=3/5,\quad
\alpha=1/100,\quad\beta=8/100,\quad\gamma=91/100,
$$
$$
r_0=S(2)/q,\quad \lambda=\phi(2)/q,\quad
d=\lambda/(1-a),\quad h=(r_0-\alpha-\beta)/d,\quad H=2+h,
\quad x_0=u(q\alpha)+1/10.
$$
For each positive multiple $N$ of $200$, put $m=91N/200$,
$\Delta_N=2/(dN)$, and $v_j=H-(j-1/2)\Delta_N$ for $1\le j\le m$.
With independent standard normals $X,U$, take all the following scores:

- $\alpha N$ copies of $X$;
- $\beta N$ copies of $2+U$;
- $m$ scores $v_j+aU+b(X-x_0)$;
- $m$ scores $v_j+aU-b(X-x_0)$.

The original true nulls are exactly the scores whose actual means are nonpositive, including whichever driver scores have nonpositive means. Let $f_N(X,U)$ be the ordinary largest-rank, non-strict BH FDP at level $q$ on this entire score vector, and $F_N=\mathbb E f_N$. The OU semigroup acts on this fixed full $f_N$.

## Checks

### H1

$N$ is a finite positive integer; the block counts sum to
$(\alpha+\beta)N+2m=N$. The testing level is exactly $S(1)>0$ and hence belongs to the target range.

### H2

All means are finite real numbers: they are $0$, $2$, $v_j-bx_0$, and $v_j+bx_0$. Labels are determined by these means via $I_0=\{i:\theta_i\le0\}$, without dropping any negative-mean driver.

### H3

The loading vectors in coordinates $(X,U)$ are $(1,0)$, $(0,1)$, $(b,a)$, and $(-b,a)$. Each has squared norm one because $a^2+b^2=1$. Their Gram matrix is positive semidefinite with unit diagonal. Clone multiplicities and the resulting singularity are permitted.

### H4

The displayed construction is a finite representation with $G=(X,U)\sim\gamma_2$. Its rank is exactly two because both $(1,0)$ and $(0,1)$ occur. Increasing the number of driver means does not increase this rank.

### H5

$f_N$ uses every score and the true-null set from H2 in the original BH procedure; thus it is measurable and takes values in $[0,1]$. If $\|(X,U)\|<1$, every true-null score is strictly less than $1$, since its mean is nonpositive and its loading has norm one. Every BH rejection threshold on the score scale is $u(qk/N)\ge u(q)=1$. Consequently there are no true-null rejections in that ball and
$$
f_N(x)=0\quad\text{for }\|x\|<1,
\qquad F_N\le\mathbb P(\|G\|\ge1)=e^{-1/2}.
$$
False rejections inside the ball, if any, do not change this conclusion.

### H6

The OU function is exactly $f_N$ above. Here are direct estimates for its full gradient norm, without taking separate absolute values of jump contributions.

For any measurable $0\le f\le1$ with mean $F$, Mehler differentiation gives, for $\rho=e^{-t}$ and $s=\sqrt{1-\rho^2}$,
$$
\nabla T_t f(x)=\frac\rho s\,\mathbb E[Y f(\rho x+sY)].
$$
For any unit vector $e$, conditioning on $e\cdot Y$ reduces the projection of the expectation to $\int z g(z)\phi(z)\,dz$, where $0\le g\le1$ and $\int g\phi=T_t f(x)$. Moving mass of $g$ to the largest values of $z$ shows that its absolute value is at most $I(T_t f(x))$. Taking $e$ in the direction of this expectation, and then using concavity of $I$, yields
$$
\mathbb E\|\nabla T_t f\|\le\frac\rho s I(F),
\qquad J(f)\le I(F)\int_0^1\frac{d\rho}{\sqrt{1-\rho^2}}
=\frac\pi2 I(F)<\infty.
$$
Differentiation is justified by the Gaussian kernel's integrable derivatives at each positive time; bounded $f$ suffices. Thus the time integral below is absolutely integrable.

Set $\psi(x)=(1-\|x\|)_+$, a bounded $1$-Lipschitz function, and $k=\mathbb E\psi(G)$. Gaussian integration by parts, first for positive time and a smooth approximation to $\psi$, gives
$$
\operatorname{Cov}(f,\psi)=
\int_0^\infty\mathbb E\langle\nabla T_t f,\nabla\psi\rangle\,dt.
$$
Indeed integrate $-\frac d{dt}\mathbb E[T_t f\,\psi]$ from $\varepsilon$ to $M$, then send $\varepsilon\downarrow0$ and $M\uparrow\infty$. The former limit follows from OU strong continuity in $L^2(\gamma_2)$ and the latter from the Mehler mixing limit, first for bounded continuous approximations and then by $L^2$ contraction. Lipschitz smoothing can be passed through these identities by dominated convergence and $\|\nabla\psi\|\le1$; the displayed finite $J(f)$ controls the time integral. The identity therefore applies to this discontinuous BH function.

H5 gives $f_N\psi=0$ almost everywhere. Hence
$$
J(f_N)\ge|\operatorname{Cov}(f_N,\psi)|=F_N k.
$$
The Rayleigh distribution in dimension two gives
$$
k=\int_0^1(1-e^{-r^2/2})\,dr
\ge\int_0^1(r^2/2-r^4/8)\,dr=17/120.
$$
This reconstructs the relevant argument of draft `idea_9146e39dd8dd`, which was retrieved to identify the precise low-rank obstruction. The draft idea is not used as an approved black box.

### H7

On $\{X\ge u(q\alpha)\}$ all $\alpha N$ selected nulls have $p$-values at most $q\alpha$. The rank $\alpha N$ qualifies, the largest BH rank is at least that large, and those selected nulls are rejected. Since $R\le N$, their contribution to FDP is at least $\alpha$. Consequently
$$
F_N\ge\alpha\mathbb P(X\ge u(q\alpha))=q\alpha^2>0.
$$
In particular the lower bound in H6 also proves $J(f_N)>0$.

### NOT

This family fails the unbounded-ratio test, uniformly in its growing number of driver groups:
$$
\frac{F_N(F_N-q\pi_0)_+}{qJ(f_N)}
\le\frac{F_N}{qk}
\le\frac{120e^{-1/2}}{17S(1)}
\le\frac{240\sqrt{2\pi}}{17}<40.
$$
For the penultimate inequality, integration by parts gives
$S(1)=\phi(1)-\int_1^\infty\phi(x)x^{-2}\,dx\ge\phi(1)-S(1)$,
so $S(1)\ge\phi(1)/2$. This covers every $N$ in the specified family and uses the norm of the full semigroup gradient throughout.

For comparison with conditional-path accounting, let $D_i$ be the baseline and $C_i$ the signed jump sum in the approved finite identity. Its exact accounting for this original model is
$$
F_N=\frac qN\sum_{i\in I_0}\mathbb E(D_i+C_i),
\qquad 0\le D_i\le1,
\qquad \frac1N\sum_{i\in I_0}\mathbb E C_i
=\frac{F_N}q-\frac1N\sum_{i\in I_0}\mathbb E D_i.
$$
Thus this normalized total signed charge belongs to $[-1,1/q]$ at the fixed $q=S(1)$. The positive charge instead uses $C_i^+=\sum_tg_i(t)[A_i(t^-)-A_i(t^+)]_+$ and need not equal $C_i$. The known positive-charge pathology supplies no replacement for the full $J(f_N)$ calculated above. No exact value of $F_N$ or positive-charge asymptotic is needed for this uniform obstruction; no claim about higher-rank families follows.

## Failure

NOT fails: the full original FDP of this approved positive-budget counterexample family has bridge ratio uniformly below $40$, independently of the growing number of driver groups.
