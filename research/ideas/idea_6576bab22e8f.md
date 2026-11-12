---
type: idea
title: Opposite Gaussian pairs force a BH rejection background in facet constructions
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_one_sided_sharp_upper
tags:
  - background-gate
  - growing-dimension
  - gaussian-pairs
---

Elementary dimension-free gate, independently checked by root. For any K,d,m and unit directions a_j, set X_j=a_j·Z and take m centered null copies X_j and m positive-mean alternative copies μ_j−X_j per group, N=2Km. If μ_j≥2w for allj with w=Q^{-1}(q/2), at least one member of each pair is ≥w, so at leastN/2 p-values≤q/2 and complete BH has R≥N/2 deterministically. Therefore FDR≤(2/N)Σ_nullP(p≤q)=q. No restriction on directions or growing dimension. Robust version (m even): v=Q^{-1}(q/4), g_j=P(μ_j−v<X_j<v). Markov on the number of uncovered groups gives P(R<N/4)≤2K^{-1}Σg_j and FDR≤2q+2K^{-1}Σg_j. If μ_j≥2Q^{-1}(q/2)−C/u, fixedC≥0,u=Q^{-1}(q), Mills ratios yield g_j≤(e^C+o(1))q, hence FDR≤(2+2e^C+o(1))q=o(qu), uniformly in K,d and directions. With unequal null/alternative clone multiplicities m_j,n_j, L=Σmin(m_j,n_j)>0 and μ_j≥2Q^{-1}(qL/N) implyR≥L and FDR≤q M0/L, M0=Σm_j. This excludes natural balanced paired high-perimeter constructions but NOT nonpaired/unbalanced models or the original conjecture. Details research-local/growing_dimension_polytope_background_gate_20261104_v1.md. Gaussian-perimeter literature was motivation only; no perimeter result is used in these elementary proofs.
