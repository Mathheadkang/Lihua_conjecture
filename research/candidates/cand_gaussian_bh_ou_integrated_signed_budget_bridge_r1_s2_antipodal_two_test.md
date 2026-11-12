---
type: candidate
title: Two-test antipodal mixed-label tail interval with signed FDP cancellation
status: failed
target_asset: gaussian_bh_ou_integrated_signed_budget_bridge
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  NOT: fail
mode: refute
round: 1
slot: 2
direction: small_cases
statement_digest: 3160ccfce0ac60cf0a63c60984ceea3c7d11be0f22bcea357fccd9ee0cfaf782
performed_by: unknown
created_at: '2026-11-09T21:56:18.237Z'
extension_version: 0.0.4
---

## Object

For every $0<q\leq S(1)$, set
$$
a=S^{-1}(q),\qquad b=S^{-1}(q/2),\qquad c=(a+b)/2.
$$
Take $N=2$, $d=1$, $G\sim N(0,1)$, and
$$
T_1(G)=G,\qquad T_2(G)=a+c-G.
$$
Thus $\theta=(0,a+c)$, $I_0=\{1\}$, $\pi_0=1/2$, and $\Sigma_{12}=-1$. This family tries to make the two opposite FDP jumps near $a,c$ cancel in the OU budget while maintaining excess FDR. All calculations below use the original two-coordinate BH procedure, including its simultaneous events.

## Checks

### H1

$N=2$ is a finite positive integer for every level in the family.

### H2

Both means are finite real numbers, $a\geq1$, and $a+c>0$. Hence the null set is exactly $\{1\}$.

### H3

The covariance is
$$
\Sigma=\begin{pmatrix}1&-1\\-1&1\end{pmatrix}.
$$
It has unit diagonal and eigenvalues $0,2$, so it is an allowed singular covariance.

### H4

The family uses precisely $0<q\leq S(1)$, and $1\leq a<c<b$.

### H5

The displayed representation has finite latent dimension $d=1$ and unit loading vectors $v_1=1$, $v_2=-1$, whose Gram matrix is $\Sigma$.

### H6

The full actual-BH FDP, up to isolated threshold points, is
$$
f(x)=\frac12\mathbf1_{[a,c]}(x)+\mathbf1_{[b,\infty)}(x).
$$
Indeed, both tests are rejected exactly when $a\leq x\leq c$: both scores then exceed the rank-two threshold $a$. On $(c,b)$ neither test is rejected, because neither both scores exceed $a$ nor either score exceeds the rank-one threshold $b$. On $[b,\infty)$ only the null is rejected. Rejection of the alternative alone elsewhere contributes zero FDP. Consequently
$$
F=\frac12\{S(a)-S(c)\}+S(b)=q-\frac12S(c)>q/2>0.
$$
The three distinct net FDP jumps are $(a,1/2)$, $(c,-1/2)$, $(b,1)$.

Here the signed-mixture representation of $J$ follows directly from Mehler differentiation rather than being presumed. For $0<\rho<1$, put $s=\sqrt{1-\rho^2}$. For a single step at $z$,
$$
\partial_x T_{-\log\rho}\mathbf1_{[z,\infty)}(x)
=\frac\rho s\phi\left(\frac{\rho x-z}{s}\right),
$$
and the Gaussian density identity gives
$$
\phi(x)\frac\rho s\phi\left(\frac{\rho x-z}{s}\right)
=\rho\phi(z)\varphi_s(x-\rho z).
$$
Finite linearity and $dt=-d\rho/\rho$ therefore yield
$$
J(f)=\int_0^1\left\|\frac{\phi(a)}2\varphi_s(\cdot-\rho a)
-\frac{\phi(c)}2\varphi_s(\cdot-\rho c)
+\phi(b)\varphi_s(\cdot-\rho b)\right\|_1\,d\rho.
$$
The signed mixture is formed before its norm. Its integral is nonnegative, and the triangle inequality bounds this expression by $\phi(a)/2+\phi(c)/2+\phi(b)<\infty$. Thus the ordinary gradients exist, this $J$ is the actual defined budget, and the change of variables involves finite integrals.

For the null's exact conditional-p path, the residual is zero and $x=u(t)$. Write $s_c=S(c)\in(q/2,q)$. Its actual rejection count and clipped path are, away from the finitely many endpoints,
$$
R_1(t)=\begin{cases}1,&0<t<q/2,\\0,&q/2<t<s_c,\\2,&s_c<t<q,\end{cases}
\qquad
A_1(t)=\begin{cases}2t/q,&0<t<q/2,\\1,&q/2<t<s_c,\\t/q,&s_c<t<q.\end{cases}
$$
There is no net jump at $q/2$. The only actual jump is the downward jump at $s_c$, with charge $1-s_c/q$. Since the null mean is zero, both its exact net signed charge and its positive charge equal $1-s_c/q$. The approved identity gives $F=(q/2)(2-s_c/q)$, agreeing with the direct full-FDP integration. This distinguishes conditional-path charge from the three signed spatial FDP jumps.

### NOT

The ratio does not diverge. For each $\rho$, the integral of the signed mixture is
$$
M=\frac{\phi(a)-\phi(c)}2+\phi(b)=\mathbb E[Gf(G)].
$$
Hence $J(f)\geq M$. Since $f\geq0$ is supported on $[a,\infty)$,
$$
J(f)\geq \mathbb E[Gf(G)]\geq aF.
$$
It follows that, uniformly throughout this family,
$$
\frac{F(F-q/2)}{qJ(f)}
\leq\frac{F-q/2}{qa}
=\frac{q-S(c)}{2qa}
<\frac1{4a}\leq\frac14.
$$
Thus this legal family with positive FDR excess cannot refute the universal gate. There is no zero-budget case because $J(f)\geq aF>0$.

As a separate independent-null dust check, appending any finite number of independent centered null coordinates changes the BH denominator and the paired model, so the preceding ratio is not asserted to persist. Each appended null, conditioned on all other scores in the enlarged $N'$-test model, has a uniform independent p-value. If $K\geq1$ is the BH count with this p-value forced to zero, its clipped path is $\min\{N't/(qK),1\}$: before $qK/N'$ it is rejected with count $K$, and afterwards it is not rejected and the clipped path is one. This path is continuous, with both net and positive jump charge zero, and its individual FDR contribution is exactly $q/N'$. This check uses the full enlarged BH procedure and does not replace its FDP by a partial-label statistic.

The $N=1$ endpoint also cannot refute the gate: a null mean $\theta\leq0$ gives $f(x)=\mathbf1\{x\geq a-\theta\}$ and $F=S(a-\theta)\leq q$; an alternative gives $F=0$. No conclusion about higher-dimensional or growing-$N$ families follows from these small cases.

## Failure

NOT is the first failing check: the full-FDP signed-mixture lower bound gives ratio $<1/(4a)\leq1/4$, so this family has neither unbounded ratio nor a positive-numerator zero-budget case.
