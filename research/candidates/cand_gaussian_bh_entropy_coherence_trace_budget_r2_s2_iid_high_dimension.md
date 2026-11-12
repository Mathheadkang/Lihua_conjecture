---
type: candidate
title: Independent all-null models at an arbitrarily large dimension
status: failed
target_asset: gaussian_bh_entropy_coherence_trace_budget
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: fail
mode: refute
round: 2
slot: 2
direction: extremal
statement_digest: 282de99c92b14dd593f40c0583da4cc65ddd227e11dcc3d261ec31f0e3456ce2
performed_by: unknown
created_at: '2026-11-08T07:21:01.191Z'
extension_version: 0.0.4
---

## Object

For every $0<q\le\overline\Phi(3)$, put $U=\overline\Phi^{-1}(q)$ and $H=h(U)$, with $h=\phi/\overline\Phi$. Choose any finite integer
$$
N\ge\max\left\{3,\left\lceil\frac{3q}{\overline\Phi(2H)}\right\rceil\right\}.
$$
Take $d=N$, $v_i=e_i$ and $\theta_i=0$ for all $i$. Thus $T_1,\ldots,T_N$ are independent standard normal statistics and every hypothesis is a true null. Dimension can grow arbitrarily rapidly with $q$ and has no upper bound. This tests a growing-dimensional family, rather than a fixed-dimensional limit or the previously excluded constant-direction models.

Apply the original ordinary largest-rank BH rule. All fields below are those of the target definition, without a free threshold or a chosen rank. The candidate fails its NOT check: over this entire family,
$$
x\le\frac14,\qquad M_+\le2q\le3q\sqrt{1+D}(1-x).
$$

## Checks

### H1

The dimensions $N,d$ are positive finite integers. The means are real, every $v_i=e_i$ has norm one, and the covariance is the identity matrix. The original unit-diagonal Gaussian model is therefore admissible. Every mean equals zero, so its original true-null set is exactly $[N]$.

### H2

The testing level obeys $0<q\le\overline\Phi(3)$, as required by the candidate statement's small-level interval. The denominator $\overline\Phi(2H)$ is strictly positive for every such fixed $q$, so the lower bound on $N$ permits finite integers. No limit or infinite testing model replaces a member of this family. In particular, it is legitimate to choose these dimensions anew at every $q$.

### H3

Use the largest qualifying BH rank, with all original p-values and non-strict inequalities. Its leave-one-out identity is used only as an exact computation of this rule. For an index $i$, replace its p-value by zero and let $r=R_i^0\ge1$ be the resulting largest rank. For any fixed other p-values, the elementary step-up identity is
$$
i\in\mathcal R\quad\Longleftrightarrow\quad p_i\le qr/N,
\qquad i\in\mathcal R\ \Longrightarrow\ R=r.
$$
To check it, decreasing $p_i$ cannot decrease the largest rank. If the original $i$ is rejected at rank $k$, then every new qualifying rank $\ell>k$ would also qualify originally: the original $p_i\le qk/N<q\ell/N$, and the other $\ell-1$ needed p-values are unchanged. Thus the zeroed and original ranks coincide. Conversely, if $p_i\le qr/N$, the zeroed rank-$r$ rejection set still has all its p-values at most $qr/N$, so the original rule reaches $r$; monotonicity gives equality. This proof accommodates ties; the Gaussian calculations also have zero-probability threshold boundaries.

Independence makes $p_i$ uniform and independent of $R_i^0$. Consequently
$$
\mathbb E\frac{\mathbf1_{\{i\in\mathcal R\}}}{R}
=\mathbb E\frac{qR_i^0/N}{R_i^0}=\frac qN.
$$
Summing over $i$ yields the exact ordinary-BH FDR $F=q$. Since all hypotheses are null, $f=\mathbf1_{\{R>0\}}$.

### H4

The exact value $F=q>0$ makes all tilted objects well defined. Their terminal law is
$$
Q=\gamma_N(\,\cdot\mid R>0),\qquad D=\log(1/q).
$$
This follows directly from the density $f/F=\mathbf1_{\{R>0\}}/q$. No independent distribution for a selected rank is assumed.

### H5

Use the precise heat semigroup, path tilt, vector field and spatial Jacobian of the target definition. Because $B=fb$, conditioning under the path tilt gives
$$
a_t=\mathbb E_{\mathbb Q}[b(W_1)\mid\mathcal F_t].
$$
For this exact rejection set, orthogonality gives the terminal identity
$$
\|b\|^2=\frac1{R h(u_R)^2}\quad\text{on }\{R>0\}.
$$
The dimension choice implies $3q/N\le\overline\Phi(2H)$ and hence $u_3\ge2H$. When $R\le3$, monotonicity of $u_r$ and the inequality $h(u)\ge u$ for $u>0$ imply
$$
H^2\|b\|^2\le\frac{H^2}{h(u_3)^2}\le\frac14.
$$
When $R\ge4$, monotonicity of the positive-tail Mills ratio and $u_R\ge U$ imply
$$
H^2\|b\|^2\le\frac1R\le\frac14.
$$
Thus the terminal bound is pointwise, not merely a probability estimate. Conditional Jensen and integration over $t\in[0,1)$ give
$$
x=H^2\mathbb E_{\mathbb Q}\int_0^1\|a_t\|^2dt
\le H^2\mathbb E_Q\|b\|^2\le\frac14.
$$
For completeness, the elementary analytic facts used here are $\phi(u)>u\overline\Phi(u)$ for $u>0$ (integrate $t\phi(t)$ over $t\ge u$) and $h'(u)=h(u)[h(u)-u]>0$.

### NOT

We establish the stronger finite-family bound $M_+\le2q$, including the required endpoint integrability. Let
$$
\mathcal H_t=(P_{1-t}f)(W_t),\qquad
v_t=\nabla\log(P_{1-t}f)(W_t).
$$
Under the path tilt, the innovation
$$
\widetilde W_t=W_t-\int_0^t v_sds
$$
is Brownian motion. This follows on stopped compact time intervals by the Gaussian heat equation and Girsanov; its endpoint extension is justified by the finite energy derived next. With $Z_t=\mathcal H_t/q$, the scalar martingale $Z_t$ under Wiener measure satisfies $0\le Z_t\le1/q$. Itô's formula for $Z_t\log Z_t$, stopped away from zero, gives
$$
\mathbb E_{\mathbb Q}\int_0^\tau\|v_t\|^2dt
=2\mathbb E_{\mathbb P}[Z_\tau\log Z_\tau]
\quad(\tau<1).
$$
The expression at zero is interpreted by continuity. Removing the lower stops uses the nonnegative energy and the bounds on $z\log z$ for $0\le z\le1/q$. As $\tau\uparrow1$, bounded convergence on that same interval and $Z_\tau\to f/q$ yield
$$
\mathbb E_{\mathbb Q}\int_0^1\|v_t\|^2dt=2\log(1/q)=2D.
$$
The heat-quotient Itô formula also gives $da_t=K_t\,d\widetilde W_t$. Boundedness of the terminal field and the martingale isometry yield
$$
\mathbb E_{\mathbb Q}\int_0^1\|K_t\|_{\mathrm{HS}}^2dt
=\mathbb E_Q\|b\|^2-\|\mathbb E_Qb\|^2<\infty.
$$
Since $d=N<\infty$, $|\operatorname{tr}K|\le\sqrt N\|K\|_{\mathrm{HS}}$ proves the target's absolute trace integrability. All endpoints can therefore be taken in the following product identity.

Put $J=\mathbb E_{\gamma_N}[G\cdot B]$. The same exact leave-one-out computation as in H3, now using $\mathbb E[G_i\mathbf1_{\{G_i\ge u\}}]=\phi(u)$, gives
$$
J=\sum_{i=1}^N\mathbb E\frac{G_i\mathbf1_{\{i\in\mathcal R\}}}{R h(u_R)}
=\sum_{i=1}^N\mathbb E\frac{\phi(u_{R_i^0})}{R_i^0h(u_{R_i^0})}=q.
$$
The conditional expectation identity for $a_t$, the Brownian product formula and the two square-integrability estimates imply
$$
J=F\mathbb E_{\mathbb Q}\int_0^1 a_t\cdot v_tdt+M.
$$
Indeed $J=F\mathbb E_{\mathbb Q}[b(W_1)\cdot W_1]$; the drift part is conditioned at each $t$, and the innovation part has expectation $\mathbb E_{\mathbb Q}\int\operatorname{tr}K_tdt$. It follows by Cauchy--Schwarz, without any sign assumption on the drift, that
$$
M\le q+\frac qH\sqrt{2Dx}.
$$
For $U\ge3$, the elementary lower Mills bound $\overline\Phi(U)\ge\phi(U)U/(1+U^2)$ gives
$$
D\le\frac{U^2}{2}+\log\!\left[\sqrt{2\pi}(U+U^{-1})\right]\le2U^2.
$$
For the last inequality, the second term is at most $3U^2/2$ at $U=3$ and remains so: its derivative is at most $1/U$, whereas that of $3U^2/2$ is $3U$. Since $H\ge U$, we have $\sqrt{2D}/H\le2$. Combining this with $x\le1/4$ yields
$$
M_+\le2q.
$$
Finally $1-x\ge3/4$ and $\sqrt{1+D}\ge1$, so
$$
M_+\le2q\le3q\sqrt{1+D}(1-x).
$$
In particular, the normalized trace is bounded by $8/[3\sqrt{1+D}]$ and even tends to zero as $q\downarrow0$ throughout this prescribed large-dimension family. No unbounded-ratio counterfamily arises here. This does not address general dependent directions, mixed truth labels or dimensions outside the displayed subfamily.

## Failure

NOT fails: every independent all-null model in this arbitrarily large finite-dimension family obeys $x\le1/4$ and $M_+\le2q$, hence the candidate trace budget with the fixed universal constant $C=3$.
