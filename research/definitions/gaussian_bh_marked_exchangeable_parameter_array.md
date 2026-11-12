---
type: definition
title: Definition (marked exchangeable Gaussian parameter array)
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
  - exchangeable_array
  - analytic_completion
---

## Definition

Write $S=\overline\Phi$, $\phi(t)=(2\pi)^{-1/2}e^{-t^2/2}$ and $q_{\max}=S(1)$. The closed marked mean domain is
$$
E_{\rm mark}=\{(\theta,\ell)\in\mathbb R\times\{0,1\}:\ell=1\Rightarrow\theta\le0,\ \ell=0\Rightarrow\theta\ge0\}.
$$
The tag $\ell=1$ counts a true rejection. An alternative-tagged zero is admitted only in the analytic completion; canonical finite models have $\ell_i=\mathbf1_{\{\theta_i\le0\}}$.

A lawful marked parameter array is $\omega=((\theta_i,\ell_i)_{i\ge1},(C_{ij})_{i,j\ge1})$ with marks in $E_{\rm mark}$, $C_{ij}=C_{ji}\in[-1,1]$, $C_{ii}=1$, and every finite principal matrix positive semidefinite. Give its space the countable product topology, with the discrete topology on tags. A probability law $P$ on this space is jointly exchangeable if simultaneous relabeling of all indices by any permutation fixing all but finitely many indices preserves its law. Write $\mathfrak P$ for these laws, with weak convergence in this product space (equivalently, finite-subarray weak convergence), and
$$
M_2(P)=\mathbb E_P\theta_1^2\in[0,\infty],\qquad
\mathfrak P_2=\{P\in\mathfrak P:M_2(P)<\infty\}.
$$
These arrays are random parameters chosen independently of the standard Gaussian innovations used to generate the conditional observations. Conditional on $\omega$, for $n\ge1$, $0<\sigma<1$, and $0<q<1/2$, generate the single finite Gaussian model
$$
T^{(n)}\mid\omega\sim\mathcal N_n(\theta_{1:n},(1-\sigma^2)C_{1:n,1:n}+\sigma^2\mathbf1\mathbf1^{\mathsf T}).
$$
Equivalently, write $T^{(n)}=\theta_{1:n}+[(1-\sigma^2)C_{1:n,1:n}+\sigma^2\mathbf1\mathbf1^{\mathsf T}]^{1/2}g_n$, where $g_n\sim\mathcal N_n(0,I_n)$ is independent of $\omega$ and $I_n$ is the $n\times n$ identity matrix.
Use one-sided p-values $S(T_i)$ and ordinary largest non-strict BH to define $R_n$, $\rho_n=R_n/n$, and the full tagged FDP $D_n=\sum_{i\in\mathcal R_q}\ell_i/(R_n\vee1)$. Put
$$
\mathcal F_n(P;q,\sigma)=\mathbb E_{\omega\sim P}\mathbb E[D_n\mid\omega].
$$
The outer mixture is not itself claimed to be a Gaussian observation model. The candidate completion functional $\mathcal F(P;q,\sigma)=\lim_{n\to\infty}\mathcal F_n(P;q,\sigma)$ is used only after the stated existence conclusion is proved.

A finite canonical common-loading model is a deterministic finite parameter list in this construction, with canonical tags and any unit-diagonal PSD residual matrix. Define $W_\sigma(q)$ to be its full FDR supremum over all finite sizes, means and residual matrices; define $A_{\eta,\sigma}^{\rm fin}(q)$ to be the corresponding supremum of FDR minus $\eta n^{-1}\sum_i\theta_i^2$. For $\eta,\delta>0$ define, whenever $\mathcal F$ exists,
$$
\mathcal L_{\eta,\delta}(P,q;\sigma)=\frac{\mathcal F(P;q,\sigma)}{qS^{-1}(q)}-\eta M_2(P)-\delta\log(1/q),\quad P\in\mathfrak P_2,\quad0<q\le q_{\max}.
$$
A lawful competitor is another law in this class (and another allowed level for $\mathcal L$), specified by parameter randomness independent of the Gaussian innovations used to generate its conditional observations. No existence, compactness, directing representation, or derivative assertion is built into this definition.
