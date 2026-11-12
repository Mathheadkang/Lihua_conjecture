---
type: idea
title: Verified finite Gaussian BH to population-mixture transfer via noisy clones
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_one_sided_sharp_upper
  - gaussian_bh_two_sided_sharp_upper
tags:
  - proved-local-tool
  - population-transfer
  - conditional-independence
---

The one-sided noisy-clone reduction proposed in idea_a193dd86ac1f now has a complete proof and independent version-bound cold review. For every FIXED finite originalGaussian model, define m_iη(g)=θ_i+sqrt(1−η)gi, Fη(t|g)=N^{-1}Σ Q((Q^{-1}(t)−m_iη)/sqrtη), and corresponding actual-null numeratorF0η. Let tη be the largest positive BH contact{Fη(t)≥t/q}, or0 ifnone, andDη=qF0η(tη)/tη forpositivecontact. Then E Dη→FDR_original asη↓0. Off the finitely many originalp_i=qk/N boundaries (probability0 even forsingularcovariance), atomic rank margins locate the largestroot nearqR/N; on its atom-free neighborhoodFη'→0 andthe root is transverse. No-larger-rank ghostcontacts areexcluded globally. ForR0, boundedconditionalmeans andη≤1/4 giveuniformFη(t)≤C_Kt² near0, rulingout tinycontacts; RN is handled frombelowq. Labels/negative nullmeans areunchanged andDη∈[0,1], so boundedconvergenceapplies. Independentfinite clonesT_i,lη=m_iη+sqrtη ε_i,l arePD and admit a safe diagonalfinite-transfer: limη↓0 limsupM→∞|FDR_clonesη,M−FDR_original|=0. This DOES NOT assert naiveM-convergence at everyfixedη: arbitrarypopulation tangencies require care. Proof research-local/gaussian_bh_noisy_clone_population_transfer_20261104_v1.md SHA36a2cae9569628651961327a28a016fb72b446c50bea9f0889e929d5ccb115bf; review research-local/gaussian_bh_noisy_clone_population_transfer_cold_review_20261104_v1.md. Any future upper bound uniform over these finite-factor populationmixtures would transfer to the originalfiniteGaussian target. Factor dimension isstillunrestricted (canbeN); no one-factorcompression or populationupper has been proved. Related to the two-sided target as a proposed analogoustransfer; the written andcold-checked theorem is one-sided.
