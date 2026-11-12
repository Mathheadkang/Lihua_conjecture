---
type: idea
title: Weak joint and labelled loading measures suffice for the conditional CDF limit
status: draft
idea_kind: approach
origin: agent
related_assets:
  - spherical_isotropic_population_bh_bound
  - gaussian_bh_one_sided_sharp_upper
  - gaussian_bh_two_sided_sharp_upper
tags:
  - candidate-transfer-lemma
  - labelled-null-measures
  - deterministic-construction
---

Candidate lemma gives a more transparent sufficient condition for the UC hypothesis in ideas18fb1caae37b/e189af0f66e7 (actual IDs idea_18fb1caae37b, idea_e189af0f66e7). Source research-local/weak_loading_measure_cdf_transfer_lemma_agent_20261104.md SHA1b62236e6c757f5b64044a88586f9532fcd91e32155fc0124ae634f2765a75cd. Not an approved node; must be rederived/verified in native proof stages. If empirical joint(theta,v) measures and each CORRECTLY LABELLED true-null submeasure converge weakly to the regular angular law and its label restriction, then actual p-CDFs and null sub-CDFs converge uniformly over[0,1] for EVERY fixedz!=0. Labels at theta0 are a genuine separate condition; weak joint convergence alone is insufficient. A deterministic finite-partition construction preserves theta<0,theta0,theta>0 and unitdirections, proves nonempty Gaussian array classes without moments or Gaussian-mixture claims. Full candidate follows.

# Candidate weak-loading transfer and deterministic realization lemma

Date: 2026-11-04. This is an independently reconstructed candidate proof, not a research node, approval, native loop-stage report, or completed Strict audit. Scope: only the transfer and deterministic realization requested by the parent agent. The workspace root is not a Git repository, so no root HEAD exists to bind. No existing file was edited.

## Exact statement

Fix an integer $d\ge4$. Let $E=\mathbb R\times S^{d-1}$ and let $\sigma$ denote normalized surface measure. Let

$$
\nu(d\theta,dv)=W(d\theta)f_\theta(v)\sigma(dv)
$$

be a probability measure, where $f$ is jointly Borel, $f_\theta$ is continuous, and $0<\kappa\le f_\theta(v)\le K<\infty$. Put $J_1=(-\infty,0]$ and $J_2=\{0\}$, regarded as subsets of the theta coordinate. For deterministic points $(\theta_{jn},v_{jn})\in E$, define

$$
\nu_n=\frac1n\sum_{j=1}^n\delta_{(\theta_{jn},v_{jn})},\qquad
\nu_{0n}^{(s)}=\frac1n\sum_{j=1}^n1\{\theta_{jn}\in J_s\}\delta_{(\theta_{jn},v_{jn})}.
$$

Assume separately

$$
\nu_n\Rightarrow\nu,\qquad
\nu_{0n}^{(s)}\Rightarrow\nu|_{J_s}\quad(s=1,2),
$$

where weak convergence of finite measures means convergence against every bounded continuous function. Let $Q=1-\Phi$, and, for fixed $z\ne0$, define continuous maps

$$
p_{1,z}(\theta,v)=Q(\theta+v^\top z),\qquad
p_{2,z}(\theta,v)=2Q(|\theta+v^\top z|).
$$

For $s=1,2$, let $F_{n,z}^{(s)}(t)=\nu_n\{p_{s,z}\le t\}$ and $F_z^{(s)}(t)=\nu\{p_{s,z}\le t\}$. Define the labelled null sub-CDFs $F_{0n,z}^{(s)}$ and $F_{0,z}^{(s)}$ using $\nu_{0n}^{(s)}$ and $\nu|_{J_s}$ instead. Then

$$
\sup_{0\le t\le1}|F_{n,z}^{(s)}(t)-F_z^{(s)}(t)|\longrightarrow0,
\qquad
\sup_{0\le t\le1}|F_{0n,z}^{(s)}(t)-F_{0,z}^{(s)}(t)|\longrightarrow0.
$$

There also exist deterministic triangular arrays satisfying all three assumed weak convergences for every such $\nu$.

## Transfer proof

**1. Atomlessness.** For every $a\in\mathbb R$ and every fixed theta,

$$
\int_{S^{d-1}}1\{\theta+v^\top z=a\}f_\theta(v)\,\sigma(dv)=0.
$$

Indeed, since $z\ne0$, the indicated sphere/hyperplane intersection is empty, a point, or a sphere of dimension $d-2$, and hence has $(d-1)$-dimensional surface measure zero. Its integral against the absolutely continuous density is zero. Integration over $W$, or over $W$ restricted to any $J_s$, proves that $h_z(\theta,v)=\theta+v^\top z$ has no atom under each of $\nu,\nu|_{J_1},\nu|_{J_2}$. These are finite measures; a zero measure causes no exception.

The inverse image of any $t\in(0,1)$ under $p_{1,z}$ is one level set of $h_z$; for $p_{2,z}$ it is the union of two level sets. The inverse image of $t=0$ is empty for both maps. The inverse image of $t=1$ is empty for $p_{1,z}$ and is $\{h_z=0\}$ for $p_{2,z}$. Therefore all corresponding pushforward measures on $[0,1]$ are atomless. In particular each population sub-CDF is continuous on $[0,1]$, is zero at zero, and equals its measure's total mass at one. This argument uses only spherical absolute continuity; the stated positivity, continuity, and uniform bounds are stronger than needed.

**2. Pointwise CDF convergence.** For any one of the assumed weakly convergent finite-measure sequences $\mu_n\Rightarrow\mu$, composition with $p_{s,z}$ gives weak convergence of pushforwards: if $g$ is bounded continuous on $[0,1]$, then $g\circ p_{s,z}$ is bounded continuous on $E$. Portmanteau at every continuity point gives convergence of the pushed-forward CDFs at every $t\in[0,1]$. At $t=0$ both empirical and limiting CDFs are zero; at $t=1$ convergence is just convergence of total masses, obtained by testing the original measures with the constant function one.

**3. Uniform CDF bracketing.** Denote any pair of these empirical and limiting CDFs by $H_n,H$. Given $\epsilon>0$, uniform continuity of $H$ permits a grid $0=t_0<\cdots<t_M=1$ with $H(t_{i+1})-H(t_i)<\epsilon$ for every $i$. If $t_i\le t\le t_{i+1}$, monotonicity gives

$$
|H_n(t)-H(t)|\le\max_{0\le k\le M}|H_n(t_k)-H(t_k)|+\epsilon.
$$

The finite maximum tends to zero. Taking a supremum over $t$, then letting $\epsilon\downarrow0$, proves both asserted uniform convergences. No theta moment, theta density, convergence rate, or joint density in $(\theta,v)$ has been used.

## Fully deterministic finite-partition construction

For integer $m\ge1$, partition the theta axis into $(-\infty,-m)$, the intervals $[k/m,(k+1)/m)$ for $k=-m^2,\ldots,-1$, the singleton $\{0\}$, the intervals $(k/m,(k+1)/m]$ for $k=0,\ldots,m^2-1$, and $(m,\infty)$. Thus every theta cell belongs entirely to one of $\theta<0$, $\theta=0$, and $\theta>0$.

Choose a finite Borel partition of $S^{d-1}$ into nonempty cells of Euclidean diameter at most $1/m$, using compactness and a finite cover followed by successive set differences. Take the product partition $\mathcal P_m=\{C_{m1},\ldots,C_{mq_m}\}$ of $E$. Pick a representative $x_{mi}=(a_{mi},b_{mi})\in C_{mi}$ for every cell, so $\|b_{mi}\|=1$, and define the Borel quantization map $R_m(x)=x_{mi}$ for $x\in C_{mi}$. It preserves all three theta strata. For each fixed $x=(\theta,v)$, the theta coordinate eventually lies inside $[-m,m]$, and then

$$
\|R_m(x)-x\|_{\mathbb R^{d+1}}\le\frac{\sqrt2}{m}.
$$

Consequently $R_m(x)\to x$ pointwise. Bounded convergence gives $(R_m)_\#\nu\Rightarrow\nu$ and $(R_m)_\#(\nu|_{J_s})\Rightarrow\nu|_{J_s}$ for both labels. This step requires no integrability assumption on theta.

Write $Q_m=\max_{1\le k\le m}q_k$. For every sufficiently large $n$, select

$$
m(n)=\max\{m\ge1:mQ_m\le n\}.
$$

The maximum exists and is finite, $m(n)\to\infty$, and $q_{m(n)}/n\le1/m(n)\to0$. The finitely many smaller $n$ may use arbitrary points of $E$.

For $m=m(n)$, set $p_i=\nu(C_{mi})$. Choose integer counts $r_i$ by taking $\lfloor np_i\rfloor$ and adding one to the $n-\sum_i\lfloor np_i\rfloor$ cells with the largest fractional parts, resolving ties by the fixed cell order. Then

$$
\sum_i r_i=n,\qquad |r_i/n-p_i|\le1/n.
$$

Take the nth array to consist of $r_i$ copies of $x_{mi}$. For every bounded continuous test function $g$, the difference between its empirical integral and its quantized-$\nu$ integral is at most $\|g\|_\infty q_m/n\to0$. Because every cell and its representative carry the same theta stratum, the identical bound applies after multiplication by $1_{J_1}$ or $1_{J_2}$. Combining this rounding bound with bounded convergence proves exactly the three required weak convergences. All counts, representatives, and arrays are deterministic once the partitions and representative choices are fixed. Nested arrays are not asserted or required.

## Exact finite Gaussian realization and scope checks

For each n, place the unit directions in the rows of the deterministic matrix $V_n\in\mathbb R^{n\times d}$ and the theta values in $\theta_n\in\mathbb R^n$. With a single $Z\sim N_d(0,I_d)$,

$$
T_n=\theta_n+V_nZ\sim N_n(\theta_n,V_nV_n^\top).
$$

The covariance matrix is positive semidefinite, has diagonal entries one, and has rank at most d. This is an exact finite Gaussian vector, including when its covariance is singular. Dimension d is fixed before n tends to infinity, and no rate is claimed. Since the deterministic transfer argument applies to every fixed $z\ne0$ for the same arrays, it applies pathwise to $Z$ on the probability-one event $\{Z\ne0\}$.

Separate label convergence is essential at theta zero: if $\nu=\delta_0\otimes\sigma$, directions have empirical law tending to $\sigma$, and all array theta values equal $1/n$, then $\nu_n\Rightarrow\nu$ but both labelled empirical submeasures have total mass zero while their proposed limits have total mass one. Likewise the fixed condition $z\ne0$ is material to this transfer theorem: for $z=0$, $\nu=\delta_a\otimes\sigma$ with $a>0$ and array theta values $a+1/n$, joint and label convergence hold but the first-track CDFs have a moving atom and their uniform distance to the limiting CDF equals one. Neither example conflicts with the theorem above.

Trust boundary: elementary spherical surface-measure geometry, bounded convergence, and Portmanteau for finite measures. Candidate proof only; the author of this note did not run a separate three-role Strict audit.
