---
type: candidate
title: Growing regular polygons on the singular rank-two boundary
status: failed
target_asset: gaussian_frozen_ray_maximal_likelihood_ratio_conjecture
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: fail
mode: refute
round: 2
slot: 3
direction: boundary_degenerate
statement_digest: 6ead14fa2488e60475cf2c3f8d05592666ae28d3bf23c28b0047c6eacd43fcbe
performed_by: unknown
created_at: '2026-11-10T22:09:30.079Z'
extension_version: 0.0.4
---

## Object

For every integer $n\geq3$, put $u_j=(\cos(2\pi j/n),\sin(2\pi j/n))$, $j=0,\ldots,n-1$, let $G=(X,Y)\sim N_2(0,I_2)$, set $Z_j=\langle u_j,G\rangle$, and take $\omega_j=1/n$. Thus $\Sigma_{jk}=\cos(2\pi(j-k)/n)$. The dimension and number of positive weights are unbounded, while the covariance has rank two. This family is outside the board's rank-one and at-most-two-positive-weights obstructions; the entropy $\log n$ is unbounded. It targets the singular covariance boundary rather than perturbing a previous two-coordinate object.

Use this one $G$ for the whole field $L_w$, for all real $w\geq0$. All assertions below are uniform in $n$, all real $c\geq2$, and all real $\alpha\geq2$.

## Checks

### H1

Pass: every $n$ is a finite positive integer.

### H2

Pass: $\Sigma$ is the Gram matrix of the unit vectors $u_j$, hence symmetric positive semidefinite with diagonal one. Its rank is two, including at $n=3$, so its singularity in dimension $n\geq3$ is permitted.

### H3

Pass: $Z$ is the linear image of a centered standard two-dimensional Gaussian, and has exactly covariance $\Sigma$.

### H4

Pass: the deterministic weights $1/n$ are positive and sum to one.

### H5

Pass: $L_w=n^{-1}\sum_j\exp(wZ_j-w^2/2)$ uses the same Gaussian vector for every real $w\geq0$. The proposed bounds are tested for all $c,\alpha\geq2$, with natural logarithms and expectations under this centered Gaussian law.

### NOT

Fail: this entire growing-dimensional boundary family satisfies all three assertions with constants independent of $n$, its rank, and $c,\alpha$. Here is an explicit calculation, including the sharp coefficient.

Write $G=R(\cos\Theta,\sin\Theta)$, where $\Theta$ is uniform on the circle, independent of $R$, and $\mathbb P(R>r)=e^{-r^2/2}$. Define $M_j=\exp((Z_j^+)^2/2)$ and $S=n^{-1}\sum_jM_j$. Maximizing each summand separately gives $\Lambda\leq S$.

First take $a=\sqrt{2\log c}$. Rotational invariance and $\{R\leq a\}\subseteq\{|Z_j|\leq a\}$ give
$$
\begin{aligned}
\mathbb E\min(c,\Lambda)
&\leq \mathbb E[S\mathbf1_{\{R\leq a\}}]+c\mathbb P(R>a)\\
&\leq \mathbb E[e^{(X^+)^2/2}\mathbf1_{\{|X|\leq a\}}]+1\\
&\leq \frac12+\frac{a}{\sqrt{2\pi}}+1
=\sqrt{\frac{\log c}{\pi}}+\frac32.
\end{aligned}
$$
Consequently the sharp assertion holds with $C_{\rm sh}=3/2$, and the order assertion holds with $C_{\rm ord}=1/\sqrt\pi+3/(2\sqrt{\log2})$.

For the tail, write $\delta_j\in[0,\pi]$ for the circular distance from $\Theta$ to the $j$th grid point, and $\delta_0^*=\min_j\delta_j\leq\pi/n$. The following two deterministic bounds hold:
$$
S\leq1+\frac{4e^{r^2/2}}r\quad(1\leq r\leq n),\qquad
S\leq1+\frac4n\max_jM_j\quad(r\geq n),
$$
where $r=R$. To verify the first bound, terms with $\delta_j\geq\pi/2$ contribute at most one to the average. For the others use $\sin\delta\geq2\delta/\pi$ and
$$
M_j=e^{r^2/2}e^{-r^2\sin^2\delta_j/2}.
$$
The average over a translated regular grid of the even bell $e^{-2r^2\delta^2/\pi^2}\mathbf1_{\{|\delta|\leq\pi/2\}}$ is at most its normalized circle integral plus $2/n$. (Split at its peak and compare each monotone Riemann sum to the integral; each side costs at most one grid cell.) The integral is at most $\sqrt\pi/(2\sqrt2r)<1/r$. Since $r\leq n$, this proves the first displayed bound even with $3$ in place of $4$.

For the second bound, order the positive-cosine distances increasingly as $\delta_{(k)}$. Their spacing gives $\delta_{(k)}\geq\pi(k-1)/n$. For $\delta\in[\delta_0^*,\pi/2]$, since $\delta+\delta_0^*\leq5\pi/6$,
$$
\sin^2\delta-\sin^2\delta_0^*
=\sin(\delta+\delta_0^*)\sin(\delta-\delta_0^*)
\geq\frac{\delta^2-(\delta_0^*)^2}{\pi^2}.
$$
Here $\sin t\geq t/(2\pi)$ for $0\leq t\leq5\pi/6$, and $\sin t\geq2t/\pi$ for $0\leq t\leq\pi/2$. Therefore each of the first two positive-cosine terms is at most $\max_jM_j$, and the sum of the ratios of all remaining terms to this maximum is at most
$$
\sum_{k=3}^{\infty}\exp\!\left(-\frac{(k-1)^2-1}{2}\right)<1
$$
when $r\geq n$. Negative-cosine terms contribute at most one to the average. This proves the second bound, with room in its constant.

Now let $\alpha\geq64$. For $R\leq1$, $S\leq e^{1/2}<\alpha$. On $1\leq R\leq n$, the first bound implies that $\Lambda\geq\alpha$ requires $e^{R^2/2}/R\geq\alpha/8$. Let $t>1$ solve $e^{t^2/2}/t=\alpha/8$. Monotonicity on $[1,\infty)$ and $\alpha\log\alpha\geq64$ show $t\geq\sqrt{\log\alpha}$. The probability of this part of the event is thus at most
$$
\mathbb P(R\geq t)=\frac8{\alpha t}\leq\frac8{\alpha\sqrt{\log\alpha}}.
$$
On $R\geq n$, the second bound implies $\max_jM_j\geq n\alpha/8$. A union bound and the elementary Gaussian Mills bound give, with $\beta=n\alpha/8\geq\sqrt\alpha$,
$$
\mathbb P\{\max_jM_j\geq\beta\}
\leq n\overline\Phi(\sqrt{2\log\beta})
\leq\frac8{\alpha\sqrt{4\pi\log\beta}}
\leq\frac4{\alpha\sqrt{\log\alpha}}.
$$
The total is at most $12/(\alpha\sqrt{\log\alpha})$. For $2\leq\alpha\leq64$, the probability bound by one suffices with $C_{\rm tail}=256$. Hence that one universal constant works for the full tail range. No implication between the sharp and tail assertions was used.

## Failure

NOT fails: regular polygons of arbitrary finite size and singular covariance rank two obey all three bounds uniformly; the sharp truncated-moment bound has coefficient $1/\sqrt\pi$ and additive constant $3/2$.
