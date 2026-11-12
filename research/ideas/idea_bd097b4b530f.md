---
type: idea
title: High-rank sign-cube boundary with polar mean ladders and composite-null shifts
status: draft
idea_kind: test_case
origin: agent
related_assets:
  - gaussian_bh_one_sided_sharp_upper
  - directional_entropy_one_sided_fdr_bound
  - multifactor_radial_fdr_bounds
tags:
  - high-rank
  - exact-singularity
  - composite-null
  - polar-mean-ladder
  - unresolved
---

UNFINISHED test case for the final boundary search, not a counterexample and not a failed candidate. Its admissibility and failure of the stated low-complexity sufficient conditions can be checked exactly, but its global BH q-limit has not been determined. No candidate file with NOT pass or NOT fail is justified.

## Exact finite Gaussian object

For q<e^{-4}, put L=log(1/q), d=4ceil(2L), and N=2^d. Index coordinates by every sign vector v in {-1,+1}^d. Let k(v) be its number of plus signs, m_v=(sum_l v_l)/sqrt(d), and a_v=v/sqrt(d). Take Z~N_d(0,I_d) and T_v=theta_v+a_v^T Z.

Let K=3d/4, an integer. For every k=K,...,d define its cumulative sign-cube cap fraction
$$
h_k=2^{-d}\sum_{\ell=k}^d {d\choose\ell},
\quad c_k=\PhiBar^{-1}(q h_k),\quad
u_q=\PhiBar^{-1}(q),\quad \delta_q=1/u_q.
$$
Use the deterministic means
$$
\theta_v=
\begin{cases}
c_{k(v)}+\delta_q,&k(v)\geq K,\\
0,&d/2\leq k(v)<K,\\
-\delta_q(1-m_v),&k(v)<d/2.
\end{cases}
$$
Thus the sparse positive polar cap has a growing mean ladder calibrated to its own cumulative global rank fractions h_k. The negative hemisphere has heterogeneous strictly negative true-null means; the remaining central positive hemisphere has boundary null mean zero. The native one-sided null convention is exactly I_0={v:k(v)<K}. Every alternative mean is positive. All parameters are deterministic.

Apply ordinary BH ONCE to the N p-values PhiBar(T_v), at the original level q. There is no local or layerwise testing. No array of size N was allocated and no finite-q numerical evidence is claimed.

## Verified admissibility

H1: d,N are finite positive integers at every q and both diverge. The number of positive mean levels d-K+1 diverges.

H2: the displayed means are finite, deterministic, and give exactly the stated composite null set, including all negative means.

H3: the covariance is
$$
\Sigma_{v,w}=(v\cdot w)/d=AA^{\mathsf T}.
$$
It is positive semidefinite with unit diagonal. Sign-cube orthogonality gives A^T A=(N/d)I_d, so its exact rank is d~8L and its nullity is N-d. This is a high-rank singular boundary, with no independently added residual noise.

H4: T=theta+AZ is exactly jointly Gaussian. It has no random mean mixture or non-Gaussian copula.

H5: use the specified global BH step-up count and E[V/(R vee1)] with all ties retained.

NOT: UNKNOWN. No FDR asymptotic, no strict excess over 1/sqrt(pi), and no counterexample status have been established.

## Why the approved sufficient conditions do not settle it

The positive cap proportion h_K tends to zero; Hoeffding's elementary sign-sum bound gives h_K<=exp(-d/8)<=q. Hence pi_0=1-h_K->1.

Distinct sign vectors give distinct unit oriented loading directions. Every grouping in the displayed residual-free representation has singleton nonzero null groups, so its oriented-null entropy is exactly pi_0 log N~8(log2)L, which is not o(sqrt L).

This entropy cannot be lowered simply by selecting a factor-plus-independent-diagonal-residual representation of the same covariance. The projection onto range(Sigma) has every diagonal entry d/N<1. For each coordinate v, the kernel vector (I-P)e_v has nonzero v component. In any Sigma=BB^T+D with D nonnegative diagonal, its quadratic form on that kernel vector is a sum of nonnegative terms; therefore D_vv must be zero. This holds for every v. All loading norms in every such representation are consequently one. Two distinct null rows cannot share an oriented unit ray because that would force Sigma_{v,w}=1, whereas (v dot w)/d<1 for v!=w. Thus singleton null direction groups are unavoidable for these representations.

The approved radial bound also does not itself produce the sharp asymptotic constant here. For X~chi_d^2, Paley-Zygmund gives P(X>=d/2)>=d/[4(d+2)]>1/8 for large d. Thus its upper-q radius b satisfies b^2>=d/2 for small q. Since PhiBar(b)<=exp(-b^2/2)/2,
$$
\Delta_1(d,q)=\log[q/\PhiBar(b)]\geq-L+d/4+\log2\geq L+\log2.
$$
With pi_0->1 and all gamma_i=0, the displayed radial and singleton-entropy upper bounds are therefore of order at least qL rather than o(q sqrt L). This concerns the strength of those UPPER BOUNDS, not a lower bound on actual FDR. Increasing factor dimension cannot reduce this radial quantile, and a positive independent diagonal residual is impossible as checked above.

## Exact unresolved global crossing

For fixed z, define
$$
F_z(c)=N^{-1}\sum_v\mathbf1\{\theta_v+a_v^Tz\geq c\},
\quad F_{0,z}(c)=N^{-1}\sum_{v:k(v)<K}
\mathbf1\{\theta_v+a_v^Tz\geq c\}.
$$
The ordinary global BH cutoff is
C_q(z)=inf{c>=u_q:qF_z(c)/PhiBar(c)>=1}, with the empty-set convention infinity. At a finite cutoff the exact FDP is q F_{0,z}(C_q(z))/PhiBar(C_q(z)); otherwise it is zero. The desired task is to integrate THIS single cutoff over the Gaussian vector z. Layerwise or capwise local FDR sums are invalid.

The conditional sign-cube joint cumulant generator is available exactly:
$$
d^{-1}\log E_v\exp\{\lambda\sum_l v_l+\eta\sum_l v_l z_l\}
=d^{-1}\sum_l\log\cosh(\lambda+\eta z_l).
$$
It permits a constrained Rademacher large-deviation analysis by magnetization layer; that inner analysis still needs the outer Gaussian rare-event integral and the global BH maximization. Uniform errors and the q sqrt L coefficient, rather than finite-q inflation, are essential.

The composite-null perturbation is a genuine singular-boundary issue: the negative-hemisphere shift relative to setting those null means to zero is not an odd function of v, whereas every vector in range(A) is odd under v->-v. Thus the mean difference lies outside range(Sigma), and the two singular Gaussian laws have disjoint affine supports for every delta_q>0. Vanishing per-coordinate shifts on typical layers do not justify a total-variation mean reduction. This does not show any FDR increase; it identifies a reduction that must be proved directly for BH if used.

Remaining gap: determine the exact Gaussian-integrated global crossing or a valid upper bound at q->0. Until that is done this is only a precise high-complexity boundary test, outside the checked low-complexity sufficient regimes.
