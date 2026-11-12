---
type: definition
title: Definition (FDP-tilted Gaussian Mills heat fields)
status: approved
source:
  kind: original
depends_on:
  - gaussian_multiple_testing_model
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
  - false_discovery_rate
tags:
  - gaussian-bh
  - fdp-tilt
  - gaussian-heat-semigroup
  - mills-field
  - coherence-deficit
---

# Definition (FDP-tilted Gaussian Mills heat fields)

## Definition

Fix positive integers $N,d$, means $\theta\in\mathbb R^N$ and unit vectors $v_1,\ldots,v_N\in\mathbb R^d$. Write $\gamma_d$ for standard Gaussian probability measure on $\mathbb R^d$, $I_d$ for the $d\times d$ identity matrix and $\Sigma_{ij}=v_i\cdot v_j$. Then $T_i=\theta_i+v_i\cdot G$, $G\sim\gamma_d$, is a [Gaussian multiple-testing model](gaussian_multiple_testing_model.md), including singular $\Sigma$. The dot and $\|\cdot\|$ denote the Euclidean inner product and norm. Fix a level $0<q<1/2$.

Write $\phi(t)=(2\pi)^{-1/2}e^{-t^2/2}$ and use the [Gaussian test p-values and true nulls](gaussian_test_pvalues.md) in their one-sided form. For each latent value $z\in\mathbb R^d$, let
$$
p_i(z)=\overline\Phi(\theta_i+v_i\cdot z),\qquad
I_0=\{i\in\{1,\ldots,N\}:\theta_i\le0\}.
$$
Apply the [ordinary Benjamini-Hochberg step-up procedure](benjamini_hochberg_step_up.md), with its largest qualifying rank, non-strict inequalities and all multiplicities, to $p(z)$ at level $q$. Denote its rejection set by $\mathcal R(z)$, its cardinality by $R(z)$ and its true-null count by $V(z)=|\mathcal R(z)\cap I_0|$. Define the [false discovery proportion and false discovery rate](false_discovery_rate.md) as the function and scalar
$$
f(z)=\frac{V(z)}{R(z)\vee1},\qquad F=\int f\,d\gamma_d.
$$
The following objects are defined only when $F>0$; a model with $F=0$ needs no tilt.

The upper-tail Mills ratio, rank cutoffs and the level-dependent reference value are
$$
h(u)=\frac{\phi(u)}{\overline\Phi(u)},\qquad
u_r=\overline\Phi^{-1}(qr/N)\quad(1\le r\le N),\qquad
U=u_N=\overline\Phi^{-1}(q),\qquad H=h(U)=\frac{\phi(U)}q.
$$
Define the vector-valued Mills field on the actual rejection set by
$$
B(z)=\begin{cases}
\displaystyle\frac{1}{R(z)h(u_{R(z)})}
\sum_{i\in\mathcal R(z)\cap I_0}v_i,&R(z)>0,\\
0,&R(z)=0.
\end{cases}
$$
Set $b(z)=B(z)/f(z)$ on $\{f>0\}$ and $b(z)=0$ elsewhere. The terminal tilted Gaussian measure and its relative entropy are
$$
\frac{dQ}{d\gamma_d}(z)=\frac{f(z)}F,\qquad
D=D(Q\Vert\gamma_d)=\int\frac{f(z)}F\log\!\left(\frac{f(z)}F\right)\gamma_d(dz).
$$
Here $0\log0=0$, and every logarithm is natural. The letters $Q$ and $D$ refer to this terminal measure and its entropy, not to a selection of one rejected coordinate.

For $s\ge0$, the Gaussian heat semigroup is
$$
(P_s\eta)(z)=\int\eta(z+\sqrt{s}\,y)\gamma_d(dy),\qquad P_0\eta=\eta,
$$
for bounded measurable scalar functions $\eta$, and componentwise for bounded vector functions. Let $\mathbb P$ be Wiener measure on continuous paths $[0,1]\to\mathbb R^d$ starting at zero. Write $W_t$ for its canonical coordinate process and $\mathcal F_t$ for its completed natural filtration. Define a path measure $\mathbb Q$ by
$$
\frac{d\mathbb Q}{d\mathbb P}=\frac{f(W_1)}F.
$$
The terminal law of $W_1$ under $\mathbb Q$ is $Q$. The coordinate process $W$ is standard Brownian motion under $\mathbb P$; it is not asserted to be Brownian motion under $\mathbb Q$.

For $0\le t<1$ and $z\in\mathbb R^d$, define
$$
\mathcal H(t,z)=(P_{1-t}f)(z),\qquad
\mathcal L(t,z)=(P_{1-t}B)(z),\qquad
a(t,z)=\frac{\mathcal L(t,z)}{\mathcal H(t,z)}.
$$
Since $F>0$ and Gaussian heat kernels are strictly positive, $\mathcal H(t,z)>0$ for every $t<1,z$. Its spatial derivatives and those of $\mathcal L$ are taken after convolution. Put
$$
a_t=a(t,W_t),\qquad
(K_t)_{jk}=\left.\frac{\partial a_j(t,z)}{\partial z_k}\right|_{z=W_t}
\quad(1\le j,k\le d),\qquad
\operatorname{tr}K_t=\sum_{j=1}^d(K_t)_{jj}.
$$
Thus $K_t$ is the full spatial Jacobian of a vector heat-posterior field, with no symmetry, gradient-potential or sign assumption. The matrix norm $\|K\|_{\mathrm{HS}}^2=\sum_{j,k}K_{jk}^2$ is the squared Hilbert--Schmidt norm.

Finally define the dimensionless integrated coherence and the cutoff signed trace by
$$
x=H^2\mathbb E_{\mathbb Q}\int_0^1\|a_t\|^2\,dt,\qquad
M_\tau=F\mathbb E_{\mathbb Q}\int_0^\tau\operatorname{tr}K_t\,dt
\quad(0\le\tau<1).
$$
The nonnegative integral defining $x$ is a Lebesgue integral over $[0,1)$; no value of $a_1$ or $K_1$ is required. When $\mathbb E_{\mathbb Q}\int_0^1|\operatorname{tr}K_t|\,dt<\infty$, define
$$
M=\lim_{\tau\uparrow1}M_\tau
=F\mathbb E_{\mathbb Q}\int_0^1\operatorname{tr}K_t\,dt,\qquad M_+=\max\{M,0\}.
$$
Finiteness of these integrals and any claimed bound for $x$ or $M_+$ are mathematical assertions to establish for a result using this definition, not extra restrictions on the Gaussian model.

## Provenance

These are the conventions used by [the entropy-amplified coherence idea](../ideas/idea_f680cd92181f.md). Candidate identities were derived under Progress P1--P3 of [the earlier Mills-field execution](../plans/plan_one_sided_order_fdp_entropy_mills_coherence_20261107.md); that plan failed at a different, stronger trace estimate. This definition neither imports those identities as approved results nor supplies a proof of either trace estimate.
