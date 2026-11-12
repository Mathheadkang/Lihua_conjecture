---
type: definition
title: Definition (rare downward-mean Gaussian clones and parameter-measure costs)
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
  - rare_clones
  - population_crossing
  - parameter_measure
---

## Definition

Fix a [Gaussian multiple-testing model](gaussian_multiple_testing_model.md) with $N\ge1$, positive-definite unit-diagonal covariance $\Sigma$, and representation
$$
G\sim\mathcal N_d(0,I_d),\qquad T_j=\theta_j+v_j\cdot G,\qquad
\|v_j\|=1,\qquad v_j\cdot v_k=\Sigma_{jk}.
$$
Here $d$ is finite, $I_d$ is the identity matrix, and dot products and norms are Euclidean. Use the [one-sided p-values and labels](gaussian_test_pvalues.md), $p_j=S(T_j)$ and $\ell_j=\mathbf1_{\{\theta_j\le0\}}$, where
$$
\phi(u)=(2\pi)^{-1/2}e^{-u^2/2},\quad S(u)=\overline\Phi(u),\quad
m(u)=\frac{S(u)}{\phi(u)},\quad h(u)=\frac1{m(u)}.
$$
Fix $q\in(0,1/2)$ and a coordinate $i\in[N]=\{1,\ldots,N\}$. Set
$$
U=S^{-1}(q)>0,\qquad u_r=S^{-1}(qr/N)\ (r\in[N]),\qquad
L=N\{h(U)/U-1\}.
$$
The inverse $S^{-1}$ is the decreasing inverse on $(0,1)$. For $\varepsilon>0$ with $\varepsilon L<1$, define the candidate offset measure by its Borel-set values
$$
P_\varepsilon(B)=(1-\varepsilon L)\mathbf1_{\{0\in B\}}
+\varepsilon\frac Nq\int_U^\infty
\mathbf1_{\{\varepsilon(1/U-1/v)\in B\}}\frac{\phi(v)}{v^2}\,dv,
\qquad B\subseteq[0,\infty)\text{ Borel}.
$$
Its positivity, total mass one and support properties are conclusions required of the associated draft lemma. Once these are established, its left generalized inverse and midpoint offsets are
$$
Q_\varepsilon(p)=\inf\{a\ge0:P_\varepsilon([0,a])\ge p\},\quad 0<p<1,
\qquad d_b=Q_\varepsilon((b-1/2)/K),\quad b\in[K],\quad K\ge1.
$$
Every original coordinate has $K$ copies. Define $a_{jb}=d_b$ for $j=i$ and $a_{jb}=0$ otherwise, and put
$$
T_{jb}^{K,\varepsilon}=\theta_j-a_{jb}+v_j\cdot G.
$$
Only parameters with $\varepsilon/U<\theta_i$ are used when $\theta_i>0$. The intended fixed labels of these copies are $\ell_j$. Write $F_{K,\varepsilon}$ for their [ordinary largest-rank BH](benjamini_hochberg_step_up.md) [false discovery rate](false_discovery_rate.md) at level $q$, and $F$ for that of the original model. Label validity is part of the associated lemma, not an extra assumption about negative or zero original means.

For a realization $t=(t_1,\ldots,t_N)$ and $0<x\le N$, define
$$
u(x)=S^{-1}(qx/N),\qquad C_\varepsilon(x;t)=P_\varepsilon([0,t_i-u(x)]),
$$
where $P_\varepsilon([0,a])=0$ for $a<0$. The candidate common population rank and null-count functions, in units of one original group, are
$$
H_\varepsilon(x;t)=\sum_{j\ne i}\mathbf1_{\{t_j\ge u(x)\}}+C_\varepsilon(x;t),
\qquad V_\varepsilon(x;t)=\sum_{j\ne i}\ell_j\mathbf1_{\{t_j\ge u(x)\}}+\ell_i C_\varepsilon(x;t),
$$
$$
\rho_\varepsilon(t)=\sup\bigl(\{0\}\cup\{x\in(0,N]:H_\varepsilon(x;t)\ge x\}\bigr).
$$
The candidate population FDP is zero when $\rho_\varepsilon(t)=0$, and otherwise is
$$
f_{\mathrm{pop},\varepsilon}(t)=
\frac{V_\varepsilon(\rho_\varepsilon(t);t)}{\rho_\varepsilon(t)}.
$$
The denominator is the actual positive fractional rank, including ranks below one. The common crossing is defined globally; whether it represents the finite-copy limit is a conclusion to prove. In particular $H_\varepsilon(N;t)=N$ and $\rho_\varepsilon(t)=N$ are allowed.

Let $\mathcal X=\mathbb R\times\mathbb S^{d-1}\times\{0,1\}$, where $\mathbb S^{d-1}=\{v\in\mathbb R^d:\|v\|=1\}$. The original, discrete-clone and continuous-offset parameter measures on $\mathcal X$ are
$$
\pi=\frac1N\sum_{j=1}^N\delta_{(\theta_j,v_j,\ell_j)},\qquad
\pi_{K,\varepsilon}=\frac1{NK}\sum_{j=1}^N\sum_{b=1}^K
\delta_{(\theta_j-a_{jb},v_j,\ell_j)},
$$
$$
\pi_\varepsilon=\frac1N\sum_{j\ne i}\delta_{(\theta_j,v_j,\ell_j)}
+\frac1N\int\delta_{(\theta_i-a,v_i,\ell_i)}P_\varepsilon(da).
$$
Here $\delta_z$ denotes unit point mass at $z$. For probability measures $\alpha,\beta$ on $\mathcal X$, define
$$
d_{\mathrm{TV}}(\alpha,\beta)=\sup_{B\text{ Borel}}|\alpha(B)-\beta(B)|,
$$
$$
c((\theta,v,\ell),(\theta',v',\ell'))
=|\theta-\theta'|+\|v-v'\|+\mathbf1_{\{\ell\ne\ell'\}},
\qquad W_1(\alpha,\beta)=\inf_{\lambda\in\Gamma(\alpha,\beta)}\int c\,d\lambda,
$$
where $\Gamma(\alpha,\beta)$ is the set of probability couplings with these marginals. This fixes the total-variation convention and transport cost; it asserts no FDR continuity in either metric.
