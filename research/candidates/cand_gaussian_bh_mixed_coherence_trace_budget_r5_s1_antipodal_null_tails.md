---
type: candidate
title: Singular antipodal null tails have positive trace but a rank-cutoff deficit
status: failed
target_asset: gaussian_bh_mixed_coherence_trace_budget
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: fail
mode: refute
round: 5
slot: 1
direction: boundary_degenerate
statement_digest: 3c4f7eca379603e53ffd48c73869d12508d38f68f5f792a85af33304907ad513
performed_by: unknown
created_at: '2026-11-08T10:31:02.996Z'
extension_version: 0.0.4
---

## Object

For every $0<q\le\overline\Phi(3)$ take $N=2$, $d=1$, $\theta=(0,0)$ and $v_1=1$, $v_2=-1$. Write
$$
U=\overline\Phi^{-1}(q),\quad H=h(U),\quad A=\overline\Phi^{-1}(q/2),\quad c=1/h(A),\quad r=H/h(A).
$$
This is a genuinely different boundary family from a common true-null direction: the two null directions are opposite, and the terminal mark changes sign. The exact orthogonal-pair obstruction also does not apply. Here the positive trace comes from selection between opposite directions although the positive rejection rank is always one.

## Checks

### H1

The level satisfies $0<q\le\overline\Phi(3)$, so $U\ge3$ and $q<1/2$. The computations are uniform in this entire interval and therefore cover every possible smaller universal $q_0$.

### H2

The dimensions $N=2,d=1$ are positive integers, and $\theta=(0,0)\in\mathbb R^2$ is finite.

### H3

Both observation vectors have norm one. Their Gram matrix is
$$
\Sigma=\begin{pmatrix}1&-1\\-1&1\end{pmatrix},
$$
which is positive semidefinite with unit diagonal and rank one. With $G\sim N(0,1)$, the observation vector is $(G,-G)$, exactly jointly Gaussian.

### H4

Both indices are true nulls. Their prescribed p-values are $\overline\Phi(z)$ and $\overline\Phi(-z)$, summing to one. Thus the largest-rank BH rule cannot select rank two, since that would require both p-values to be at most $q<1/2$. It selects rank one exactly when the smaller p-value is at most $q/2$. With the required non-strict endpoint convention,
$$
R(z)=V(z)=\mathbf1_{\{|z|\ge A\}},\qquad
f(z)=\mathbf1_{\{|z|\ge A\}},\qquad
B(z)=c\operatorname{sgn}(z)\mathbf1_{\{|z|\ge A\}}.
$$
There are no ties on the support; endpoints have Gaussian measure zero.

### H5

The FDP mean and prescribed terminal tilt are
$$
F=2\overline\Phi(A)=q>0,\qquad
\frac{dQ}{d\gamma_1}=q^{-1}\mathbf1_{\{|z|\ge A\}},\qquad
D=\log(1/q).
$$
Use exactly the path tilt $d\mathbb Q/d\mathbb P=f(W_1)/q$. For $s=1-t>0$, set
$$
p_+(t,z)=\overline\Phi((A-z)/\sqrt s),\qquad
p_-(t,z)=\overline\Phi((A+z)/\sqrt s).
$$
The prescribed heat posterior is therefore
$$
\mathcal H=p_++p_-,\qquad
a(t,z)=c\frac{p_+-p_-}{p_++p_-}.
$$
No tilted measure, terminal mark or rank convention has been changed.

### NOT

**Fails.** The well-posedness and endpoint conclusions hold, and this family obeys the square-root budget with $C=2$.

First establish all well-posedness statements before estimating $M$. Let $b(W_1)=c\operatorname{sgn}(W_1)$ under $\mathbb Q$. Conditional expectation under the prescribed path tilt gives $a_t=\mathbb E_{\mathbb Q}[b(W_1)\mid\mathcal F_t]$, $a_0=0$, and $|a_t|\le c$. The usual entropy identity is justified here directly by applying Itô's formula to the positive heat density on $[0,\tau]$: its relative entropy at time $\tau$ is half its drift energy. As $\tau\uparrow1$, the density martingale converges to $q^{-1}f(W_1)$; its densities lie in $[0,1/q]$, and $u\log u$ is bounded on that interval. Dominated convergence under $\mathbb P$ therefore gives
$$
\mathbb E_{\mathbb Q}\int_0^1\beta_t^2dt=2D<\infty.
$$
Consequently $Z_t=W_t-\int_0^t\beta_sds$ is innovation Brownian motion under $\mathbb Q$ and extends to time one. Heat calculus gives $da_t=K_t\,dZ_t$. The bounded terminal-mark martingale converges in $L^2$, so Itô isometry yields
$$
\mathbb E_{\mathbb Q}\int_0^1K_t^2dt
=\mathbb E_{\mathbb Q}b(W_1)^2-a_0^2=c^2.
$$
In particular,
$$
\mathbb E_{\mathbb Q}\int_0^1|K_t|dt\le c,\qquad
\mathbb E_{\mathbb Q}\int_0^1|a_t\beta_t|dt\le c\sqrt{2D},\qquad
0\le x\le H^2c^2=r^2<1.
$$
Also $0\le D=\log(1/F)<\infty$. The endpoint integral is absolutely finite since $|B|\le c$ and $\mathbb E|G|<\infty$.

For completeness the endpoint identity follows without assuming it: $b(W_1)=\int_0^1K_t\,dZ_t$, hence $\mathbb E_{\mathbb Q}[b(W_1)Z_1]=\mathbb E_{\mathbb Q}\int_0^1K_tdt$ by the cross isometry. Conditional expectation and the established absolute drift integrability give
$$
\mathbb E_{\mathbb Q}\left[b(W_1)\int_0^1\beta_tdt\right]
=\mathbb E_{\mathbb Q}\int_0^1a_t\beta_tdt.
$$
Since $W_1=Z_1+\int_0^1\beta_tdt$ and $q\mathbb E_{\mathbb Q}[b(W_1)W_1]=\int zB(z)d\gamma_1(z)$, this proves the stated endpoint identity and its agreement with the absolutely integrable signed trace. Explicitly,
$$
\int zB(z)d\gamma_1(z)=2c\phi(A)=q.
$$

The trace is strictly positive. Differentiating its explicit posterior, with $\lambda_\pm=h((A\mp z)/\sqrt s)$, gives
$$
K(t,z)=\frac{2c\,p_+p_-}{(p_++p_-)^2\sqrt s}(\lambda_++\lambda_-)>0.
$$
Nevertheless, the previous square-energy identity and Cauchy--Schwarz imply
$$
0<M=q\mathbb E_{\mathbb Q}\int_0^1K_tdt\le qc.
$$
The rank-cutoff gap uniformly absorbs this bound. To show this with explicit constants, let $X$ be standard normal conditioned on $X\ge u$, $u\ge3$. Gaussian tail translation gives
$$
\mathbb P(X-u\ge y)\le e^{-uy},\qquad
\mathbb E(X-u)^2\le2/u^2.
$$
The conditional variance identity $h'(u)=1-\operatorname{Var}(X)$ then implies $h'(u)\ge1-2/u^2\ge7/9$. Also
$$
\log2=\int_U^A h(u)du\le h(A)(A-U).
$$
It follows that
$$
h(A)^2-H^2
\ge\frac79(A-U)(h(A)+H)
\ge\frac79\log2.
$$
Since $1-x\ge1-r^2=c^2(h(A)^2-H^2)$, we conclude
$$
M_+\le qc\le\sqrt{\frac9{7\log2}}\,q\sqrt{1-x}
<2q\sqrt{1-x}.
$$
The entropy-linear term is nonnegative. Thus this entire singular antipodal zero-mean pair, including levels tending arbitrarily quickly to zero, cannot refute the proposed mixed budget.

## Failure

NOT fails: opposite null directions create a positive trace, but their fixed rank-one cutoff forces a coherence deficit that uniformly absorbs the trace energy bound.
