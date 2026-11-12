---
type: definition
title: >-
  Definition (compensated private Gaussian clones and common population
  crossing)
status: approved
source:
  kind: original
depends_on:
  - gaussian_multiple_testing_model
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
  - false_discovery_rate
tags:
  - gaussian_bh
  - private_clones
  - compensated_variation
---

## Definition

Fix a finite [Gaussian multiple-testing model](gaussian_multiple_testing_model.md) with $N\ge1$, arbitrary means $\theta\in\mathbb R^N$, and positive-definite unit-diagonal covariance $\Sigma$. Fix $q\in(0,1/2)$ and $i\in[N]$ with $\theta_i\ne0$. Choose any finite-dimensional representation
$$
G\sim\mathcal N_d(0,I_d),\qquad T_j=\theta_j+v_j\cdot G,\qquad
\|v_j\|=1,\qquad v_j\cdot v_k=\Sigma_{jk}.
$$
Here $[m]=\{1,\ldots,m\}$ for each positive integer $m$, $I_d$ is the identity matrix, and dot products and norms are Euclidean. Write $S=\overline\Phi$ for the [standard normal survival function](gaussian_test_pvalues.md), put
$$
\phi(t)=(2\pi)^{-1/2}e^{-t^2/2},\qquad h(t)=\frac{\phi(t)}{S(t)},\qquad
I_0=\{j\in[N]:\theta_j\le0\},
$$
and use one-sided p-values $S(T_j)$. For a score vector $t$, let $\mathcal R_q(t)$ denote [ordinary largest-rank BH](benjamini_hochberg_step_up.md) applied to $S(t_j)$, including multiplicities and non-strict inequalities. Its original fixed-label FDP is
$$
f(t)=\frac{|I_0\cap\mathcal R_q(t)|}{|\mathcal R_q(t)|\vee1},\qquad F=\mathbb E f(T).
$$
Thus $F$ is the original [false discovery rate](false_discovery_rate.md).

For $\varepsilon>0$ set
$$
s=\frac{\varepsilon}{\sqrt{1+\varepsilon^2}},\qquad
t_s=\sqrt{2\log\frac{1}{\sqrt{2\pi}\,s}},\qquad
d_\varepsilon=s(t_s+t_s^{-1}).
$$
Restrict to sufficiently small $\varepsilon$ so $0<s<\phi(0)$ and $\theta_i+d_\varepsilon$ has the same sign as $\theta_i$. Equivalently, $t_s>0$ is the unique positive solution of $\phi(t_s)=s$. Let $(\xi_b)_{b\ge1}$ be independent standard Gaussians, jointly independent of $G$. For every integer $K\ge1$, give every original group exactly $K$ copies and define
$$
T_{jb}^{K,\varepsilon}=T_j\quad(j\ne i),\qquad
T_{ib}^{K,\varepsilon}
=\theta_i+d_\varepsilon+\frac{v_i\cdot G+\varepsilon\xi_b}{\sqrt{1+\varepsilon^2}}
\quad(b\in[K]).
$$
The expanded model is exactly jointly Gaussian with variance-one marginals; its covariance may be singular. Its actual one-sided true-null set is $I_0\times[K]$. Let $\mathcal R_{K,\varepsilon}$ be ordinary BH at level $q$ for all $NK$ expanded p-values, let $R_{K,\varepsilon}=|\mathcal R_{K,\varepsilon}|$, and set
$$
F_{K,\varepsilon}
=\mathbb E\frac{|(I_0\times[K])\cap\mathcal R_{K,\varepsilon}|}{R_{K,\varepsilon}\vee1}.
$$
Every expectation here includes both $G$ and the private Gaussian variables used by the finite array.

The following deterministic functional of $G$ defines a proposed population representation; this definition makes no finite-copy convergence assertion. For $0<x\le N$ put $u(x)=S^{-1}(qx/N)$ and
$$
m_\varepsilon(G)=\theta_i+d_\varepsilon+\sqrt{1-s^2}\,v_i\cdot G,\qquad
b_\varepsilon(x,G)=S\!\left(\frac{u(x)-m_\varepsilon(G)}s\right),
$$
$$
H_\varepsilon(x,G)=\sum_{j\ne i}\mathbf1\{T_j\ge u(x)\}+b_\varepsilon(x,G),
$$
$$
J_\varepsilon(x,G)=\sum_{j\in I_0\setminus\{i\}}\mathbf1\{T_j\ge u(x)\}
+\mathbf1\{i\in I_0\}\,b_\varepsilon(x,G).
$$
Set $u(0)=+\infty$ and $b_\varepsilon(0,G)=H_\varepsilon(0,G)=J_\varepsilon(0,G)=0$. Define the single common largest crossing and its fractional FDP functional by
$$
\rho_\varepsilon(G)=\sup\bigl(\{0\}\cup\{x\in(0,N]:H_\varepsilon(x,G)\ge x\}\bigr),
$$
$$
D_\varepsilon(G)=
\begin{cases}
J_\varepsilon(\rho_\varepsilon(G),G)/\rho_\varepsilon(G),&\rho_\varepsilon(G)>0,\\
0,&\rho_\varepsilon(G)=0.
\end{cases}
$$
The mass $x$ is measured in original-coordinate units, so the corresponding expanded rejection fraction is $x/N$. The chosen group contributes a fractional mass $b_\varepsilon$ to the same crossing used by all other groups. Relating $\rho_\varepsilon$ and $D_\varepsilon$ to finite-copy BH, including crossing births and switches, requires proof.
