---
type: candidate
title: Barely negative collinear nulls with a genuine BH rank jump
status: failed
target_asset: gaussian_bh_mixed_coherence_trace_budget
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  NOT: fail
mode: refute
round: 1
slot: 3
direction: drop_hypothesis
statement_digest: 3c4f7eca379603e53ffd48c73869d12508d38f68f5f792a85af33304907ad513
performed_by: unknown
created_at: '2026-11-08T09:57:49.237Z'
extension_version: 0.0.4
---

## Object

For every $0<q\le\overline\Phi(3)$ put $U=\overline\Phi^{-1}(q)$, $A=\overline\Phi^{-1}(q/2)$ and $H=h(U)$. Choose any finite
$$
c\ge A-U+1/A,
$$
and take $N=2,d=1$, $v_1=v_2=1$, $\theta_1=0$, $\theta_2=-c$. Write $T=U+c$, so $T\ge A+1/A$. In particular, choosing the smallest permitted $c$ pushes the second mean to the true-null boundary as $q\downarrow0$, while preserving a genuine rank-one rejection interval. Both hypotheses are true nulls. This family also allows arbitrarily negative means and has singular observation covariance.

## Checks

### H1

The testing level is positive and at most $\overline\Phi(3)$; $U\ge3$. For any proposed smaller $q_0$, restrict the same family to $q\le q_0$.

### H2

The dimensions are finite positive integers, both vectors have unit norm, and the finite mean vector is real. The covariance is the positive-semidefinite unit-diagonal matrix with every entry one. The observations are $(G,G-c)$ for $G\sim N(0,1)$.

### H3

The prescribed one-sided p-values are $\overline\Phi(z)$ and $\overline\Phi(z-c)$. With ordinary largest-rank BH, including multiplicities,
$$
R(z)=0\quad(z<A),\qquad R(z)=1\quad(A\le z<T),\qquad R(z)=2\quad(z\ge T).
$$
Indeed the rank-two qualification is $z-c\ge U$, and where it fails the rank-one qualification is $z\ge A$. Thus this uses the actual largest rank rather than a selected qualifying rank. Endpoint inequalities agree with the statement.

### H4

Since every rejection is null, $f=\mathbf1_{[A,\infty)}$ and $F=q/2>0$. The terminal tilted law is the standard normal conditioned on $G\ge A$, with $D=\log(2/q)$.

### NOT

The proposed violation fails uniformly in this entire family. Here are direct checks of the well-posedness and trace estimate, without assuming an endpoint representation to define the trace.

Set $k_1=1/h(A)$, $\Delta=1/H-k_1>0$, $r=H/h(A)$, $p=\overline\Phi(T)/\overline\Phi(A)$ and $s=1-t$. For $t<1$ define
$$
\pi(t,z)=\frac{\overline\Phi((T-z)/\sqrt{s})}{\overline\Phi((A-z)/\sqrt{s})}.
$$
Direct convolution of $B$ and $f$ gives $a(t,z)=k_1+\Delta\pi(t,z)$. Under the tilted path law, $\pi_t$ is the conditional probability of $W_1\ge T$, so $a_t$ is the bounded martingale with terminal value $b(W_1)=k_1+\Delta\mathbf1_{[T,\infty)}(W_1)$. Consequently
$$
r^2\le x\le \mathbb E_Q[(Hb(W_1))^2]=r^2(1-p)+p\le1.
$$
Write $\delta=1-x$. The Gaussian tail logarithmic derivative gives
$$
p=\exp\left(-\int_A^T h(u)\,du\right)\le e^{-1},\qquad
\delta\ge(1-e^{-1})(1-r^2).
$$
The first inequality uses $h(u)\ge u\ge A$ and $T-A\ge1/A$.

Because $h$ is increasing, differentiation of the tail ratio shows $\partial_z\pi\ge0$, hence $K_t=\Delta\partial_z\pi(t,W_t)\ge0$. The tilted density at time $t$ is $\mathcal H(t,W_t)/F$ relative to Wiener measure. Thus direct differentiation yields
$$
0\le F\mathbb E_{\mathbb Q}K_t
=\Delta\left[\phi(T)-\mathbb E_{\mathbb P}\left\{\pi(t,W_t)\frac{\phi((A-W_t)/\sqrt{s})}{\sqrt{s}}\right\}\right]
\le\Delta\phi(T).
$$
Here the first term is $\phi(T)$ by Gaussian convolution, since $W_t$ has variance $t$ under $\mathbb P$. This bound is independent of $t$, proving absolute trace integrability directly and giving
$$
0\le M\le\Delta\phi(T)\le\Delta\phi(A)
=\frac q2(r^{-1}-1).
$$
For completeness the entropy martingale of $\mathbf1_{\{W_1\ge A\}}/F$ gives $\mathbb E_{\mathbb Q}\int_0^1\beta_t^2dt=2\log(2/q)<\infty$: apply Ito to $\log\mathcal H$ up to $\tau<1$ and pass to the bounded-terminal-density entropy limit. Boundedness of $a$ and Cauchy--Schwarz then give absolute drift integrability. The endpoint $\int|zB(z)|\gamma_1(dz)$ is finite because $B$ is bounded. Under $\mathbb Q$, apply the product rule to $W_ta_t$ on $[0,\tau]$, using the bounded martingale property of $a_t$ and $dW_t=d\widetilde W_t+\beta_tdt$. Its drift is $a_t\beta_t+K_t$. The established integrability and $L^2(\mathbb Q)$ convergence of $W_t$ and bounded martingale convergence of $a_t$ justify $\tau\uparrow1$, giving exactly the required endpoint identity. Thus none of the well-posedness assertions fails either.

Finally $A-U\le(\log2)/U$ because $\log2=\int_U^A h(u)du\ge U(A-U)$. The Mills bounds $h(U)\ge U$ and $h(A)\le A+1/A$ imply
$$
r\ge\frac{U}{U+(1+\log2)/U}>\frac12\qquad(U\ge3).
$$
Therefore
$$
\frac{M}{q\sqrt{\delta}}
\le\frac{r^{-1}-1}{2\sqrt{(1-e^{-1})(1-r^2)}}
=\frac{\sqrt{1-r}}{2r\sqrt{(1-e^{-1})(1+r)}}
\le\frac1{\sqrt{1-e^{-1}}}<2.
$$
The square-root term alone bounds this family by $2q\sqrt{1-x}$, uniformly over all its levels and negative mean parameters. Adding the entropy-linear term preserves the bound.

## Failure

NOT fails: despite a barely negative null, a singular covariance and a genuine change in the largest BH rank, this family satisfies the complete conclusions with universal budget constant $C=2$.
