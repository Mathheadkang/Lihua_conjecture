---
type: candidate
title: Antipodal all-null tails obey a stronger linear coherence-deficit trace bound
status: failed
target_asset: gaussian_bh_entropy_coherence_trace_budget
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  NOT: fail
mode: refute
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: 282de99c92b14dd593f40c0583da4cc65ddd227e11dcc3d261ec31f0e3456ce2
performed_by: unknown
created_at: '2026-11-08T07:12:17.023Z'
extension_version: 0.0.4
---

## Object

Take $N=2,d=1$, $v_1=1,v_2=-1$ and $\theta_1=\theta_2=0$. For $0<q\le\overline\Phi(3)$ write
$$
U=\overline\Phi^{-1}(q),\quad a=\overline\Phi^{-1}(q/2)>U\ge3,
\quad H=h(U),\quad c=1/h(a).
$$
The statistics are exactly $(G,-G)$, with their original all-null labels. This candidate tests singular covariance, disconnected tilted support and the $q\downarrow0$ near-coherent limit.

## Checks

### H1

Both directions are unit vectors and the covariance is $\left(\begin{smallmatrix}1&-1\\-1&1\end{smallmatrix}\right)$, a unit-diagonal rank-one positive-semidefinite matrix.

### H2

Rank two would require both $G\ge U$ and $-G\ge U$, which is impossible because $U>0$. Rank one qualifies exactly on $|G|\ge a$. Hence
$$
R=f=\mathbf1_{\{|G|\ge a\}},\qquad F=q,\qquad
B=c\operatorname{sign}(G)\mathbf1_{\{|G|\ge a\}}.
$$
These are the actual largest-rank BH regions, with no surrogate threshold.

### H3

Every $0<q\le\overline\Phi(3)$ is covered. The limiting family $q\downarrow0$ has $a\to\infty$; a single large finite trace ratio would not suffice to refute the universal-constant assertion.

### H4

The terminal tilt $Q$ is standard normal conditioned on $|G|\ge a$, so $D=\log(1/q)<\infty$. Under the corresponding path tilt let $S=\operatorname{sign}(W_1)\in\{-1,1\}$ and $m_t=\mathbb E_{\mathbb Q}[S\mid\mathcal F_t]$. Then $a_t=cm_t$. Conditional heat probabilities are
$$
H_+(t,z)=\overline\Phi((a-z)/\sqrt{1-t}),\qquad
H_-(t,z)=\overline\Phi((a+z)/\sqrt{1-t}),
$$
and $m=(H_+-H_-)/(H_++H_-)$. Write $v_\pm=\partial_z\log H_\pm$ and $\Delta v=v_+-v_->0$. Differentiating the posterior odds gives
$$
K_t=c\,\partial_zm(t,W_t)
=\frac c2(1-m_t^2)\Delta v(t,W_t)\ge0.
$$
For completeness, put $p_t=(1+m_t)/2$. The heat-posterior martingale has stochastic coefficient $p_t(1-p_t)\Delta v$. Applying Ito's formula to the binary entropy on cutoffs $t<1$, then increasing the cutoff to one, gives
$$
\frac18\mathbb E_{\mathbb Q}\int_0^1(1-m_t^2)(\Delta v)^2dt=\log2.
$$
Indeed the posterior starts at $p_0=1/2$ and converges to $\mathbf1_{\{S=1\}}$; its expected information gain is $\log2$. The nonnegative integrand and bounded binary information justify the endpoint limit.

Let $A=\int_0^1\mathbb E_{\mathbb Q}(1-m_t^2)dt$. The posterior mean minimizes squared prediction error, so the estimator $\operatorname{sign}(W_t)$ gives
$$
\mathbb E_{\mathbb Q}(1-m_t^2)
\le4\mathbb Q(\operatorname{sign}(W_t)\ne S)
\le4\overline\Phi\!\left(a\sqrt{\frac t{1-t}}\right).
$$
The last inequality follows by conditioning on $W_1=y$ and using the Brownian bridge $W_t\sim N(ty,t(1-t))$, with $|y|\ge a$. Since $t/(1-t)\ge t$,
$$
A\le4\int_0^\infty\overline\Phi(a\sqrt t)dt=\frac2{a^2}.
$$
The integral identity uses $\int_0^\infty\overline\Phi(\sqrt u)du=\mathbb E(Z_+)^2=1/2$. Cauchy--Schwarz with the binary information identity yields
$$
0\le M=q\mathbb E_{\mathbb Q}\int_0^1K_tdt
\le qc\sqrt{2A\log2}
\le\frac{2q\sqrt{\log2}}{a^2}.
$$
Here $h(a)\ge a$. Thus the absolute trace integral is finite. Also $0\le x=H^2c^2(1-A)\le(H/h(a))^2<1$.

### NOT

A uniform lower bound for $1-x$ prevents this positive trace from violating the candidate. To check it without an unproved Mills derivative estimate, integration by parts and Jensen give, for a standard normal $X$ conditioned on $X>u>0$,
$$
h(u)-u=u\,\mathbb E[X^{-2}\mid X>u],\quad
\mathbb E[X^2\mid X>u]=1+u h(u),
$$
$$
h'(u)=h(u)(h(u)-u)
\ge\frac{u h(u)}{1+u h(u)}
\ge\frac{u^2}{1+u^2}\ge\frac9{10}\quad(u\ge3).
$$
Moreover $\log2=\int_U^a h(u)du\le h(a)(a-U)$. Therefore
$$
1-x\ge1-\frac{H^2}{h(a)^2}
\ge\frac{9\log2}{10h(a)^2}
\ge\frac{729\log2}{1000a^2}.
$$
The last step uses the usual integration-by-parts bound $h(a)\le a+1/a\le10a/9$: the first bound follows from $\overline\Phi(a)\ge\phi(a)a/(a^2+1)$, obtained by bounding $\int_a^\infty\phi(t)/t^2dt\le\overline\Phi(a)/a^2$ in the same integration-by-parts identity. Combining the estimates shows
$$
M\le\frac{2000}{729\sqrt{\log2}}\,q(1-x)
<4q(1-x)
\le4q\sqrt{1+D}\,(1-x).
$$
Thus this entire legal finite family satisfies a stronger uniform linear-deficit bound, even though its tilt has disconnected support and no finite Poincare constant. No universal entropy-stability theorem with extra structural hypotheses was invoked.

## Failure

NOT fails: binary posterior information and the actual tail separation give $M\le4q(1-x)$ uniformly throughout the allowed small-q interval.
