---
type: definition
title: >-
  Definition (signed near-active posterior gradients and lawful mean-level
  cones)
status: approved
source:
  kind: original
depends_on:
  - gaussian_bh_private_smoothed_directing_population
  - gaussian_bh_marked_exchangeable_parameter_array
tags:
  - gaussian_bh
  - signed_variation
  - near_active_selectors
  - complementarity
---

## Definition

Fix a deterministic directing law $\pi$ with $M_2(\pi)<\infty$ in the [private-noise-smoothed unit-ball population](gaussian_bh_private_smoothed_directing_population.md), with its parameters $q,\sigma,s,a,\chi_a$, kernels, quantiles and actual largest rank $R$. Write $S=\overline\Phi$, $\phi(t)=(2\pi)^{-1/2}e^{-t^2/2}$, $q_{\max}=S(1)$, $U=S^{-1}(q)$ and $u_q(t)=S^{-1}(qt)$. Here $s>0$ denotes private smoothing, and every test is one-sided. All parameter laws and mean velocities are chosen before the Gaussian innovations.

For $x=(\theta,v,\ell)$ and residual background $X$, use $A_X(x)$ and $c_s(v)$ from the private-smoothed population and set
$$
k_{X,x}(z)=c_s(v)^{-1}\phi((z-A_X(x))/c_s(v)),\quad
h_X(z)=\int k_{X,x}(z)d\pi(x),\quad
h_{0,X}(z)=\int\ell(x)k_{X,x}(z)d\pi(x).
$$
For $0<t<1$ put
$$
p_{X,t}(x)=\frac{k_{X,x}(Q_X(t))}{h_X(Q_X(t))},\qquad
m_t=\frac{S(u_q(t))}{\phi(u_q(t))}.
$$
These are posterior densities relative to the fixed law $\pi$, and scalar inverse-Mills coefficients, respectively. Write $m(z)=S(z)/\phi(z)$, so $m_t=m(u_q(t))$.

For $0<r<1$ define the barrier, suffix infimum and active set by
$$
B_X(r)=\frac{u_q(r)-Q_X(r)}{\sigma},\qquad B_X(1)=+\infty,
$$
$$
M_X(r)=\inf_{r\le t\le1}B_X(t),\qquad
\mathcal A_X(r)=\{t\in[r,1):B_X(t)=M_X(r)\}.
$$
The associated result must justify finiteness, attainment and measurability; they are not assumptions of this convention. Set
$$
g_X(r)=\chi_a(r)f_X(r),\quad w_X(r)=g_X'(r),\quad
w_{X,+}(r)=\max\{w_X(r),0\},\quad
w_{X,-}(r)=\max\{-w_X(r),0\},\qquad a<r<1.
$$

For an integer $j\ge1$, let $\mathcal T_j$ be the measurable rational-valued maps $t(X,r)$ such that
$$
r\le t(X,r)<1,\qquad B_X(t(X,r))\le M_X(r)+1/j
$$
for $\mathbb P_X\otimes dr$-almost every $(X,r)\in\Omega_X\times(a,1)$. Arbitrary values may be assigned on an exceptional null set. For each sign, the integrated selector vector is
$$
V_\pm(t)=\frac1\sigma\mathbb E_X\int_a^1
w_{X,\pm}(r)\phi(M_X(r))
\bigl(p_{X,t(X,r)}(\cdot),m_{t(X,r)}\bigr)\,dr.
$$
Whenever these vectors belong to $L^1(\pi)\times\mathbb R$, define
$$
C_j^\pm=\overline{\operatorname{co}}^{\,\mathrm{weak}}
\{V_\pm(t):t\in\mathcal T_j\},\qquad
C^\pm=\bigcap_{j\ge1}C_j^\pm.
$$
The weak topology is $\sigma(L^1(\pi)\times\mathbb R,L^\infty(\pi)\times\mathbb R)$ with pairing
$$
\langle(g,c),(b,\lambda)\rangle=\int gb\,d\pi+c\lambda.
$$
For a subset $C$ of this space, $h_C(b,\lambda)=\sup_{(g,c)\in C}\langle(g,c),(b,\lambda)\rangle$ is its support function. This notation asserts neither nonemptiness nor uniform integrability, weak compactness, support-limit identities or complementarity.

For a canonical directing law, meaning $\pi\{\theta=0,\ell=0\}=0$, let
$$
E_0=\{x:\theta(x)=0,\ell(x)=1\}.
$$
The mean-level cone $K\subset L^\infty(\pi)\times\mathbb R$ consists of bounded Borel representatives $b$ with $b\le0$ $\pi$-almost everywhere on $E_0$, unrestricted off $E_0$, together with $\lambda\in\mathbb R$ when $q<q_{\max}$ and $\lambda\le0$ when $q=q_{\max}$. Its polar is
$$
K^\circ=\{(g,c)\in L^1(\pi)\times\mathbb R:
\langle(g,c),(b,\lambda)\rangle\le0\text{ for every }(b,\lambda)\in K\}.
$$
The cone $K$ is a testing cone; this definition does not identify it with the norm closure of uniformly lawful velocities. Its use in an extremal inequality requires a separate approximation argument.
