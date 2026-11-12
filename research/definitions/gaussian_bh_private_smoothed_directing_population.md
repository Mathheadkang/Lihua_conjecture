---
type: definition
title: Definition (private-noise-smoothed unit-ball Gaussian directing population)
status: approved
source:
  kind: original
depends_on:
  - gaussian_bh_common_loading_tagged_population
  - gaussian_bh_marked_exchangeable_parameter_array
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
  - false_discovery_rate
tags:
  - gaussian_bh
  - private_noise
  - rank_cutoff
  - directing_measure
---

## Definition

Fix $0<q<1/2$, $0<\sigma<1$, $s>0$ with $\sigma^2+s^2<1$, and a nonzero separable real Hilbert space $\mathcal H$. Put $\tau_s=\sqrt{1-\sigma^2-s^2}$. A deterministic directing law $\pi$ is a Borel probability on
$$
E_{\rm ball}=\{(\theta,v,\ell)\in\mathbb R\times\mathcal H\times\{0,1\}:\|v\|\le1,\ \ell=1\Rightarrow\theta\le0,\ \ell=0\Rightarrow\theta\ge0\}
$$
with $M_2(\pi)=\int\theta^2d\pi<\infty$. The common-loading unit-sphere definition does not already supply this integrated-private-noise extension. All parameter laws are fixed before observations.

Use the isonormal series representative from the common-loading definition: for an orthonormal basis $(e_k)$ and iid $\xi_k\sim N(0,1)$, put $X(v)=\sum_k\langle v,e_k\rangle\xi_k$ wherever it converges and zero otherwise; finite-dimensional sums have their usual meaning. Joint measurability, almost-everywhere validity for $\pi$ and every stated perturbed law, and representative invariance are obligations of any associated result. No infinite-dimensional identity-covariance Gaussian random vector is assumed. Let $Z\sim N(0,1)$ be independent of $X$.

Conditional on the residual background $X$, set, for $x=(\theta,v,\ell)$,
$$
A_X(x)=\theta+\tau_sX(v),\qquad c_s(v)^2=s^2+\tau_s^2(1-\|v\|^2)\ge s^2,
$$
$$
H_X(t)=\int S\!\left(\frac{t-A_X(x)}{c_s(v)}\right)d\pi(x),\qquad
V_X(t)=\int\ell S\!\left(\frac{t-A_X(x)}{c_s(v)}\right)d\pi(x).
$$
Private standard normals have been integrated in these kernels. In an actual finite sample, each test has its own independent private normal, independent also of $X,Z$. For iid parameter draws $x_i\sim\pi$, the conditional-on-parameters Gaussian scores are
$$
T_i=\theta_i+\tau_sX(v_i)+c_s(v_i)\zeta_i+\sigma Z,
$$
where the $\zeta_i$ are iid standard normals. Diagonal variances are one, and distinct-score covariance is $\tau_s^2\langle v_i,v_j\rangle+\sigma^2$. Unconditional mixing over the parameters is not one Gaussian model.

For $0<r<1$, $Q_X(r)$ is the unique real number satisfying $H_X(Q_X(r))=r$. Use $Q_X(1)=-\infty$, $Q_X(0)=+\infty$ only as extended endpoints. Set $v_X(r)=V_X(Q_X(r))$, $f_X(r)=v_X(r)/r$ for $0<r<1$, and $f_X(1)=\int\ell d\pi$. At rank zero use FDP zero. For $u_q(r)=S^{-1}(qr)$ define the actual candidate largest population rank and payoff by
$$
R(X,Z)=\sup\bigl(\{0\}\cup\{r\in(0,1]:H_X(u_q(r)-\sigma Z)\ge r\}\bigr),\qquad
D=\begin{cases}f_X(R),&R>0,\\0,&R=0.\end{cases}
$$
Fix $0<a<1/4$ and a specified nondecreasing $C^1$ function $\chi_a:[0,1]\to[0,1]$ equal to zero on $[0,a]$ and one on $[2a,1]$. Write $\mathcal F^a(\pi;q,\sigma,s)=\mathbb E[\chi_a(R)D]$ and $\mathcal F(\pi;q,\sigma,s)=\mathbb E D$. Their identification with ordinary finite competitors is a conclusion to prove.

The associated private smoothing of a base marked array replaces its residual matrix by
$$
C^{(s)}_{ij}=\begin{cases}(1-s^2/(1-\sigma^2))C_{ij},&i\ne j,\\1,&i=j.\end{cases}
$$
Let $\mathcal F_n^a(P;q,\sigma,s)$ be the outer expected finite payoff $\chi_a(\rho_n)D_n$ for covariance $(1-\sigma^2)C^{(s)}+\sigma^2\mathbf1\mathbf1^{\mathsf T}$. Its limit, if established, is denoted $\mathcal F^a(P;q,\sigma,s)$. The same convention without cutoff defines $\mathcal F(P;q,\sigma,s)$. The quadratic and normalized objectives replace $\mathcal F$ in the marked-array definition by this $\mathcal F^a$.

A lawful mean velocity is a deterministic Borel $b:E_{\rm ball}\to\mathbb R$ with $|b|\le K<\infty$ such that $(\theta+\epsilon b,v,\ell)$ stays in $E_{\rm ball}$ for every sufficiently small $\epsilon>0$, $\pi$-almost everywhere. For joint mean/level perturbations let $q_\epsilon=q(1+\epsilon\lambda)$, with fixed finite $\lambda$ and levels remaining in the allowed interval. The pushforward law is $\pi_\epsilon$. No velocity can depend on the subsequently observed $X,Z$ or private noises.
