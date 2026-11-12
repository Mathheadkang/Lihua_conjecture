---
type: candidate
title: Two separated global minima with joint mean and level perturbation
status: failed
target_asset: gaussian_bh_private_noise_cutoff_signed_transport_variation
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
round: 5
slot: 2
direction: small_cases
statement_digest: 678b5ca0bc054ae3e466058cbe1c77cb985edbf7afbd22f2e2ab1034682a803c
performed_by: unknown
created_at: '2026-11-09T07:04:18.040Z'
extension_version: 0.0.4
---

## Object

Put $c=10^{-3}$, $\sigma=\sqrt{1-c^2}$, $s=c/2$, $q=1/10$, $a=1/20$, and $w=1/4$. In the one-dimensional directing space use only $v=0$, with true atom $(\theta,v,\ell)=(0,0,1)$ of mass $1-w$, and false atom $(\mu,0,0)$ of mass $w$. Thus $A_X=\theta$ and $c_s(0)=c$, with no residual-background dependence. Write
$$
H_\mu(t)=(1-w)S(t/c)+wS((t-\mu)/c),\qquad Q_\mu=H_\mu^{-1},
$$
where the inverse is the upper quantile, and $B_\mu(r)=[S^{-1}(qr)-Q_\mu(r)]/\sigma$.

Define $I_1=[1/8,3/8]$, $I_2=[3/4,1)$ and
$$
m_j(\mu)=\min_{r\in I_j}B_\mu(r).
$$
Choose any root $\mu_*\in(0.60,0.75)$ of $m_1(\mu)=m_2(\mu)$. The calculation below proves such a root exists and that both minima are global, rather than using a numerical near-tie. The velocity is $b=0$ at the true atom and $b=1$ at the false atom, and $\lambda=-1/5$, so $\mu_\epsilon=\mu_*+\epsilon$, $q_\epsilon=q(1-\epsilon/5)$. Use the $C^1$ cutoff equal to zero for $r\le a$, equal to $3x^2-2x^3$ with $x=(r-a)/a$ on $a<r<2a$, and equal to one for $r\ge2a$.

This targets the previously uncovered exact global-tie mechanism, together with a simultaneous level change; it is not an inference from a numerically observed pair of local minima.

## Checks

### H1

The scalar restrictions hold: $0<q<1/2$, $0<\sigma<1$, $s>0$, $\sigma^2+s^2=1-3c^2/4<1$, and $0<a<1/4$.

### H2

The directing law is deterministic, supported on the unit ball, and lawful: the true mean is zero and the false mean is strictly positive. Its second mean moment is $w\mu_*^2<\infty$.

### H3

The displayed cutoff is nondecreasing and $C^1$, vanishes below $a$, and is one above $2a$. The directing law has just two atoms, so no representative or measurability choice is needed.

### H4

Since $v=0$,
$$
c_s(0)^2=s^2+(1-\sigma^2-s^2)=c^2.
$$
The finite score realization is $T_i=\theta_i+\sigma Z+c\xi_i$, with independent standard normal private noises $\xi_i$. Each marginal variance is exactly one. The population conditional tails are precisely the displayed Gaussian mixture, whose density is strictly positive.

### H5

The implicit choice of $\mu_*$ is well defined and certifies an exact global tie. Here are elementary bounds, stated before division by the positive factor $\sigma$. The inequalities $S(4)<0.000032$ and
$$
S^{-1}(.0125)>2.24,\quad S^{-1}(.0251)>1.958,\quad
S^{-1}(.0375)>1.78,\quad S^{-1}(.075)>1.439,
$$
$$
1.281<S^{-1}(.1)<1.282,\quad S^{-1}(.0999)<1.283,\quad S^{-1}(.0249)<1.963
$$
suffice. For every $\mu\in[.60,.75]$, $H_\mu(.004)<.251$, hence $Q_\mu(r)<.004$ whenever $r\ge.251$. At $r=.999$, $H_\mu(-.004)>.999$, so $Q_\mu(.999)>-.004$. Consequently
$$
1.277<\sigma m_2(\mu)<1.287.
$$
For $r\in[.375,.75]$, one has $\sigma B_\mu(r)>1.435$. For $r\le.125$, stochastic domination by $N(\mu,c^2)$ gives
$$
\sigma B_\mu(r)\ge S^{-1}(.1r)-\mu-cS^{-1}(r)>1.488.
$$
The last expression decreases on $(0,.125]$: its derivative is $-.1/\phi(S^{-1}(.1r))+c/\phi(S^{-1}(r))<0$, because both quantiles are positive, the first is larger, and $.1>c$. This also controls arbitrarily microscopic ranks.

At $\mu=.60$, for $r\in[.125,.251]$ use $Q_\mu(r)<\mu+.004$ to obtain $\sigma B_\mu(r)>1.354$; for $r\in[.251,.375]$ use $Q_\mu(r)<.004$ to obtain $\sigma B_\mu(r)>1.776$. Thus $m_1(.60)>m_2(.60)$. At $\mu=.75$, $H_\mu(\mu-.004)>wS(-4)>.249$, giving
$$
\sigma m_1(.75)\le \sigma B_\mu(.249)<1.963-.75+.004=1.217<\sigma m_2(.75).
$$
Coupling the false scores by common private noise proves $|Q_\mu(r)-Q_\nu(r)|\le|\mu-\nu|$, hence both $m_j$ are Lipschitz continuous. The second minimum is attained below one because $B_\mu(r)\to+\infty$ as $r\uparrow1$, uniformly on this compact mean interval. The intermediate value theorem therefore supplies $\mu_*$. The preceding exclusion bounds show that both active minima are global, in separated rank intervals. There may be additional minimizers within either interval; none are discarded.

### H6

The velocity is deterministic and bounded by one, is chosen before observations, and keeps the two tagged means lawful for every sufficiently small positive $\epsilon$. The second moment derivative is exactly $2w\mu_*$. No canonical-zero boundary is crossed.

### H7

The joint level path stays in $(0,1/2)$, and also below $q_{\max}=S(1)$, for sufficiently small positive $\epsilon$.

### NOT

Fail. The certified global tie does not violate the full signed formula. This can be checked directly for this mixture, including its joint perturbation. Write $k_0(t)=\phi(t/c)/c$, $k_\mu(t)=\phi((t-\mu_*)/c)/c$, and $h=(1-w)k_0+wk_\mu$. Its fixed-rank derivatives are
$$
\dot Q(r)=\frac{wk_\mu(Q(r))}{h(Q(r))},\qquad
\dot f(r)=-\frac{w(1-w)k_0(Q(r))k_\mu(Q(r))}{r h(Q(r))}.
$$
In particular the direct true-numerator term is negative and must remain in the formula. Every active suffix minimizer is retained in
$$
\dot M(r)=\min_{t\in\mathcal A(r)}
\frac{\tfrac15m(u_q(t))-wk_\mu(Q(t))/h(Q(t))}{\sigma}.
$$
For completeness this is an exact right derivative at the tie, not selection of a preferred well: uniform differentiability of the two-component mixture quantiles on compact rank intervals, followed by compact minimization, gives the minimum of all active derivatives. No minimizer escapes to one because the Gaussian-mixture quantiles tend uniformly to minus infinity there. Mean coupling and $q_\epsilon\in[.09,.1]$ bound all suffix-minimum difference quotients by a fixed constant, for example $[1+\tfrac29m(S^{-1}(.09))]/\sigma$.

The actual-rank identity follows directly from $H_\mu(u_q(t)-\sigma z)\ge t\iff z\ge B_\mu(t)$. With $g_\epsilon=\chi_a f_\epsilon$, integration by parts therefore gives the exact finite-perturbation expression
$$
\mathcal F_\epsilon^a=\int_a^1g_\epsilon'(r)S(M_\epsilon(r))\,dr.
$$
Equivalently, separate payoff change at $R_\epsilon$ from distribution change of the fixed payoff $g$. The first difference quotient converges to $\mathbb E_Z[\chi_a(R)\dot f(R)]$: monotone ranks have only countably many discontinuity levels, and $Z$ has a density. Its domination follows from the mixture score coupling and the private-density bound on $r\ge a$. The second quotient is dominated by a constant times $|g'(r)|$, integrable since $|f'|\le1/r$ and $\chi_a$ is $C^1$. Differentiating $S(M_\epsilon)$ now yields exactly
$$
\dot{\mathcal F}^a=\mathbb E_Z[\chi_a(R)\dot f(R)]
-\int_a^1(\chi_af)'(r)\phi(M(r))\dot M(r)\,dr.
$$
Thus the tie and joint mean/level change produce the stated nonlinear all-active-minima response, without a discarded signed term. This calculation only checks this particular law; it establishes no general convergence, attainment, representation, or regularizer-removal result.

## Failure

NOT fails: a certified pair of separated equal global suffix minima, with a lawful joint false-mean increase and level decrease, still yields exactly the full signed all-active-minima variation formula.
