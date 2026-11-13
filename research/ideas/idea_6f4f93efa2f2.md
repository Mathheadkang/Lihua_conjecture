---
type: idea
title: >-
  Mills-penalized acceptance is equivalent to the fixed-level Gaussian Simes
  cap; no design-free per-scale bound is summable
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_mills_penalized_subset_supremum_acceptance
tags: []
---

Agent calculation (plan stage, 12 November 2026), not yet checked. (1) Equivalence. Lemma => cap: the reduction gaussian_simes_mills_penalized_subset_reduction gives E_q subset {M_A >= (1/2)sqrt(log(1/(Aq)))-1} for q<=e^{-1}/A, so at a small enough q, P(E_q)<=1-delta_0 for every Sigma. Cap => lemma: if for some alpha_0<=1/2 and delta>0 the one-sided Gaussian Simes test at level alpha_0 accepts with probability >=delta for every Sigma, take A=1/alpha_0 and s_0=0. Simes acceptance at level 1/A means t_(j)<Phibar^{-1}(j/(NA)) for all j. The Riemann bound sum_{j<=k}Phibar^{-1}(j/(NA))<=NA int_0^{k/(NA)}Phibar^{-1}=NA phi(z_k)=k tau_A(K) (idea_32196f2dee9b, step 1) then gives X_K<tau_A(K) for every K, so M_A<0. Hence the target is, up to constants, exactly the uniform fixed-level Gaussian Simes conjecture, which amplification shows is equivalent to gaussian_simes_one_sided_uniform_linear_bound. The route does not shrink the open problem; it restates it. (2) Per-scale obstruction. Take N/k independent blocks of k exact clones (nonnegative correlations). Then P(M^(k)>0)>=P(max_b g_b>h(z_A)), which is about (N/k)Phibar(z_A+1/z_A), about 1/(eA), at every single scale k. So no per-scale bound p_k that is uniform over Sigma can have sum_j p_{2^j}<infinity. That rules out union or chaining over dyadic size classes, and Gaussian-correlation products over the symmetrized per-scale sets {|X_K|<=tau_A(K) for |K|=k}, unless a design-dependent scale budget sum_j P(M^(2^j)>s)<=C holds. Nothing available supplies such a budget. (3) M_A is convex (a maximum of affine functions), so by Ehrhard a uniform bound E M_A<=s_0 would suffice. But that bound is stronger than the lemma, and Borell-TIS over the log N scales gives only about tau_max sqrt(log log N).
