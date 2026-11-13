---
title: Deterministic penalized Gaussian BH maximizers with ultrametric null directions
type: lemma
status: draft
source:
  kind: original
  note: Route lemma (slot 5) of the researcher-selected ultrametric route (idea_b808cca5bf7f, content idea_ae102c56085d), parallel round of 12 November 2026. Unproved. Intended external input, D. Panchenko, The Parisi ultrametricity conjecture, Ann. of Math. 177 (2013) 383-393, DOI 10.4007/annals.2013.177.1.8, together with Talagrand's positivity principle under the Ghirlanda-Guerra identities, is not in the library and must be imported and verified before use; exact theorem locations are to be read from the source.
depends_on:
  - gaussian_bh_exchangeable_array_variational_compactification
  - lib_panchenko2009_dovbysh_sudakov_mixture
  - gaussian_bh_null_overlap_ghirlanda_guerra_maximizer
uses_definitions:
  - gaussian_bh_marked_exchangeable_parameter_array
tags:
  - parallel-round-20261112
  - ultrametric
  - ghirlanda-guerra
---

# Deterministic penalized Gaussian BH maximizers with ultrametric null directions

## Statement

Use the notation of [the null-tag Ghirlanda-Guerra lemma](gaussian_bh_null_overlap_ghirlanda_guerra_maximizer.md): the [marked parameter arrays](../definitions/gaussian_bh_marked_exchangeable_parameter_array.md), $\mathfrak P_2$, $M_2$, $\mathcal F(\cdot;q,\sigma)$, canonical laws, the event $E_0$ and the null-tag overlap array $R^0$. Fix $0<\sigma<1$, $0<q\le\overline\Phi(1)$ and $\eta>0$, and let $P_*\in\mathfrak P_2$ be a canonical maximizer of $\mathcal F(\cdot;q,\sigma)-\eta M_2$ over $\mathfrak P_2$ with $P_*(E_0)>0$ whose null-tag overlap array satisfies the Ghirlanda-Guerra identities.

Then there exist a separable real Hilbert space $\mathcal H$ with closed unit ball $B_{\mathcal H}$ and a deterministic Borel probability measure $\mu$ on $\mathbb R\times B_{\mathcal H}\times\{0,1\}$ with the following properties.

1. $\mu$ is canonical: $\mu$-almost every $(\theta,v,\ell)$ has $\ell=\mathbf 1_{\{\theta\le0\}}$; moreover $\mu\{\ell=1\}>0$ and $\int\theta^2\,d\mu<\infty$.
2. Let $P_\mu$ be the law of the iid-generated array: $(\theta_i,v_i,\ell_i)_{i\ge1}$ iid with law $\mu$, $C_{ij}=\langle v_i,v_j\rangle$ for $i\ne j$ and $C_{ii}=1$. Then $P_\mu\in\mathfrak P_2$ and
$$
\mathcal F(P_\mu;q,\sigma)-\eta M_2(P_\mu)=\max_{P\in\mathfrak P_2}\{\mathcal F(P;q,\sigma)-\eta M_2(P)\}.
$$
3. $P_\mu$-almost surely, for all pairwise distinct indices $i,j,k$ with $\ell_i=\ell_j=\ell_k=1$,
$$
C_{ij}\ge0\qquad\text{and}\qquad C_{ik}\ge\min\{C_{ij},C_{jk}\}.
$$

Nothing is asserted about the correlations $C_{ij}$ in which $i$ or $j$ is alternative-tagged, about finite support, or about positive definiteness. This lemma asserts no FDR order bound.

## Notes

Role in the route: it converts the Ghirlanda-Guerra identities of the null-tag array into one deterministic maximizing population whose finite samples have hierarchical (tree) null correlations, so that [the null-ultrametric tree bound](gaussian_bh_null_ultrametric_order_bound.md) applies to every finite sample.

Suggested proof outline (not part of the statement): (i) under $P_*(\cdot\mid E_0)$ the array $R^0$, completed by unit diagonal, is a jointly exchangeable Gram-de Finetti array (selection by iid tags under the directing representation of item 6 of [the compactification](gaussian_bh_exchangeable_array_variational_compactification.md) and the approved [Dovbysh-Sudakov representation](../library/panchenko2009_dovbysh_sudakov/assets/lib_panchenko2009_dovbysh_sudakov_mixture.md)); (ii) Talagrand's positivity principle and Panchenko's ultrametricity theorem give, almost surely, nonnegativity and ultrametricity of its off-diagonal entries; (iii) hence, for almost every directing component, the null-tag iid sample array has the property in item 3; (iv) the zero-gap component selection of item 6 of the compactification shows that almost every directing component of the canonical maximizer $P_*$ is itself a canonical maximizer, so one component satisfies items 1-3 simultaneously. Atoms of $\mu$ are allowed; for distinct indices sampling the same particle, $C_{ij}=\|v_i\|^2$, which the conditions in item 3 already cover.
