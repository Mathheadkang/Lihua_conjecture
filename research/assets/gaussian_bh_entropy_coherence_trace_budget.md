---
type: lemma
title: Entropy-amplified coherence budget for the Gaussian BH Mills trace
status: deprecated
source:
  kind: original
depends_on: []
uses_definitions:
  - gaussian_multiple_testing_model
  - gaussian_test_pvalues
  - benjamini_hochberg_step_up
  - false_discovery_rate
  - gaussian_bh_fdp_mills_heat_fields
tags:
  - gaussian-bh
  - universal-order
  - fdp-tilt
  - coherence-deficit
  - signed-trace
---

# Entropy-amplified coherence budget for the Gaussian BH Mills trace

## Statement

There exist universal constants $0<C<\infty$ and $0<q_0\le\overline\Phi(3)$ with the following property. For every pair of finite positive integers $N,d$, every $\theta\in\mathbb R^N$, every collection of unit vectors $v_1,\ldots,v_N\in\mathbb R^d$, and every $0<q\le q_0$, consider the [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md)
$$
T_i=\theta_i+v_i\cdot G,\qquad G\sim\gamma_d,\qquad
\Sigma_{ij}=v_i\cdot v_j\quad(1\le i,j\le N).
$$
Here $\gamma_d$ is standard Gaussian probability measure on $\mathbb R^d$. Use the [one-sided Gaussian p-values and original true-null set](../definitions/gaussian_test_pvalues.md)
$$
p_i=\overline\Phi(T_i),\qquad I_0=\{i:\theta_i\le0\},
$$
and apply the [ordinary largest-rank Benjamini-Hochberg procedure](../definitions/benjamini_hochberg_step_up.md) at level $q$, including all multiplicities and non-strict threshold inequalities. Write $\mathcal R$ for its actual rejection set, $R=|\mathcal R|$, $V=|\mathcal R\cap I_0|$ and $f=V/(R\vee1)$, and suppose its [false discovery rate](../definitions/false_discovery_rate.md) $F=\mathbb E f$ is positive.

Form the [FDP-tilted Gaussian Mills heat fields](../definitions/gaussian_bh_fdp_mills_heat_fields.md) for this exact model. In particular,
$$
U=\overline\Phi^{-1}(q),\quad H=\frac{\phi(U)}q,\quad
u_r=\overline\Phi^{-1}(qr/N),\quad h=\frac{\phi}{\overline\Phi},\quad
B=\frac{\sum_{i\in\mathcal R\cap I_0}v_i}{R h(u_R)}\ \text{on }\{R>0\},
$$
with $B=0$ on $\{R=0\}$. The terminal measure is $dQ=(f/F)d\gamma_d$ and $D=D(Q\Vert\gamma_d)$ is its relative entropy. Under the path measure $d\mathbb Q=(f(W_1)/F)d\mathbb P$, where $\mathbb P$ is standard Wiener measure, use the full heat-posterior vector and its spatial Jacobian
$$
a_t=\frac{(P_{1-t}B)(W_t)}{(P_{1-t}f)(W_t)},\qquad
K_t=\left.\nabla_z\left(\frac{(P_{1-t}B)(z)}{(P_{1-t}f)(z)}\right)\right|_{z=W_t},
\qquad 0\le t<1.
$$
Here $P_s$ is Gaussian convolution with covariance $sI_d$, with matrix convention $(K_t)_{jk}=\partial_k a_j(t,W_t)$, exactly as in the cited definition. Then
$$
D<\infty,\qquad
\mathbb E_{\mathbb Q}\int_0^1|\operatorname{tr}K_t|\,dt<\infty,\qquad
x:=H^2\mathbb E_{\mathbb Q}\int_0^1\|a_t\|^2\,dt\in[0,1],
$$
and the finite signed trace
$$
M:=F\mathbb E_{\mathbb Q}\int_0^1\operatorname{tr}K_t\,dt
=\lim_{\tau\uparrow1}F\mathbb E_{\mathbb Q}\int_0^\tau\operatorname{tr}K_t\,dt
$$
satisfies
$$
\boxed{\quad M_+\le Cq\sqrt{1+D}\,(1-x),\qquad M_+=\max\{M,0\}.\quad}
$$
The constants are independent of $N,d,\theta$, all directions, null proportion, covariance rank and every other model-complexity parameter. This covers every unit-diagonal positive-semidefinite covariance matrix, including singular matrices, through any finite Gram realization. Means, covariance, dimension and all other admissible parameters may depend arbitrarily on $q$. Negative true-null means are retained. No free threshold, externally chosen rank, coordinatewise conditional independence, positive-correlation assumption or replacement of the actual BH rule is part of the assertion. Models with $F=0$ are excluded only because the tilted measures are then undefined; they already have zero FDR.

## Research status and provenance

This is the missing-step candidate specified by [the entropy-amplified coherence idea](../ideas/idea_f680cd92181f.md) and the autonomous project reassessment. It is unproved and requires its own native counterexample search and independent proof verification. Its statement does not claim either unrestricted main upper bound and supplies no approved dependency.

The earlier Mills-field execution [records a finite small-loading counterfamily to the estimate $M_+\le Cq\sqrt{1-x}$](../plans/plan_one_sided_order_fdp_entropy_mills_coherence_20261107.md); that plan is failed research evidence, not an approved dependency of this lemma. The entropy factor and the linear deficit in the present assertion are intentional changes; no conclusion of that earlier estimate is assumed here. The candidate must be tested on actual near-coherent selected-null normals, negative null means and false-null-triggered rank cascades with the original Gaussian geometry preserved.
