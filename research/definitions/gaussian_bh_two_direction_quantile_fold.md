---
type: definition
title: Definition (two-direction Gaussian population with an isolated quantile fold)
status: approved
source:
  kind: original
depends_on:
  - gaussian_bh_common_loading_tagged_population
tags:
  - gaussian_bh
  - diffuse_fold
  - signed_deformation_recovery
---

## Definition

Use the parameter space, metric, Gaussian field, population crossing and full FDP of the [common-loading tagged Gaussian population](gaussian_bh_common_loading_tagged_population.md). Fix $q\in(0,1/2)$, $\sigma\in(0,1)$, $p\in(0,1)$, and distinct deterministic unit vectors $v_0,v_1$ in its nonzero separable real Hilbert space $\mathcal H$. Write $\tau=\sqrt{1-\sigma^2}$, $S=\overline\Phi$, and $\phi(t)=(2\pi)^{-1/2}e^{-t^2/2}$. With the isonormal process $X$ and independent standard Gaussian $Z$, put
$$
X_0=\tau X(v_0)+\sigma Z,\qquad Y=\tau X(v_1)+\sigma Z,\qquad
\rho=\sigma^2+(1-\sigma^2)\langle v_0,v_1\rangle\in(-1,1).
$$
Here $\rho$ is a correlation; $\rho_\pi$ below denotes the actual population rank and is a different quantity.

Let $\vartheta\in C^3([0,1])$ be strictly decreasing, with $\vartheta(1)>0$. Define the deterministic tagged parameter probability law
$$
\pi=p\delta_{(0,v_0,1)}+(1-p)\int_0^1\delta_{(\vartheta(c),v_1,0)}\,dc.
$$
The integration variable $c$ indexes a continuum of fixed means. It is not an extra random mean in a finite Gaussian observation. All true mass is the zero-mean atom at direction $v_0$; all alternative means are positive and use direction $v_1$. Thus the scores are $X_0$ and $\vartheta(c)+Y$, respectively. For $0<r\le1$ the actual common-cutoff counts are
$$
H_\pi(r)=p\mathbf1_{\{X_0\ge S^{-1}(qr)\}}+(1-p)\int_0^1\mathbf1_{\{\vartheta(c)+Y\ge S^{-1}(qr)\}}\,dc,
\qquad
V_\pi(r)=p\mathbf1_{\{X_0\ge S^{-1}(qr)\}}.
$$
Set $H_\pi(0)=V_\pi(0)=0$ and use the actual largest non-strict crossing and full FDP
$$
\rho_\pi=\sup\bigl(\{0\}\cup\{r\in(0,1]:H_\pi(r)\ge r\}\bigr),\qquad
D_\pi=\begin{cases}V_\pi(\rho_\pi)/\rho_\pi,&\rho_\pi>0,\\0,&\rho_\pi=0,\end{cases}
\qquad F(\pi)=\mathbb E D_\pi.
$$
In particular, a positive actual crossing with only alternatives rejected has FDP zero.

Put
$$
u(r)=S^{-1}(qr),\qquad r(c)=p+(1-p)c,\qquad g(c)=u(r(c))-\vartheta(c).
$$
The isolated nondegenerate global-fold condition means that $g$ has a unique global minimum $b=g(c_*)$ on $[0,1]$, with $c_*\in(0,1)$ and $g''(c_*)>0$. Set $r_*=r(c_*)$. For $y\in\mathbb R$ define the auxiliary forced-true rank and the conditional kernel by
$$
r_\vartheta(y)=\sup\bigl(\{p\}\cup\{r(c):0<c\le1,\ y\ge g(c)\}\bigr),\qquad
k(y,r)=\frac p r S\!\left(\frac{u(r)-\rho y}{\sqrt{1-\rho^2}}\right)\quad(p\le r\le1).
$$
The auxiliary rank inserts the true mass $p$ before testing its actual rejection condition. It is not defined to equal $\rho_\pi$ on false-only or no-rejection events. Its relation to the actual rank and the representation of $F(\pi)$ are conclusions required of the associated recovery asset, not additional assumptions or an independent optimization over ranks.

Fix $\chi\in C_c^\infty(\mathbb R)$ with $0\le\chi\le1$, $\chi=1$ on $[-1,1]$, and $\chi=0$ outside $[-2,2]$. For $K>0$, $\delta\in\{-1,+1\}$, and $\epsilon>0$, the quantile-bump candidate is
$$
\vartheta_\epsilon^\delta(c)=\vartheta(c)-\delta\epsilon\chi\!\left(\frac{c-c_*}{K\sqrt\epsilon}\right),\qquad
g_\epsilon^\delta(c)=u(r(c))-\vartheta_\epsilon^\delta(c),
$$
$$
\pi_\epsilon^\delta=p\delta_{(0,v_0,1)}+(1-p)\int_0^1\delta_{(\vartheta_\epsilon^\delta(c),v_1,0)}\,dc.
$$
Admissibility of both perturbed quantiles and their precise minima are to be proved. The signed original conditional-FDP jump is
$$
\Delta=k(b,r_*)-k(b,p).
$$
All Wasserstein distances below use exactly the tagged cost $|\theta-\theta'|+\|v-v'\|+\mathbf1_{\{\ell\ne\ell'\}}$ in the approved common-loading population definition.
