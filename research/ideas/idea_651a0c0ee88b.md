---
type: idea
title: Fixed-model compactness and coefficient bounds for the paired Stein program
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_two_sided_sharp_upper
tags:
  - paired-lp
  - compactness
  - certificate-validation
---

Checked finite-model tool, not uniformfeasibility. For any fixedfinitePD Gaussian model andfixedD in the reflectionpairedLP, the truehomogeneous α-recessioncone has onlyzero. A recessiondirectionhasδβ=0 becauseβ isbounded. Its pairedfacefluxes are≥0, so Gaussianintegration givesE[α_C(g)·g]=Σ_allface I_α≥0, whereasallboxsupportsσ_C(α_C)≤0 forceEαg≤0. Equality impliesα_C·g=0a.e. on everypositive-probability openbox, henceα_C=0. Thus anynonemptyfixedD feasiblepolyhedron isbounded; thisdoesnotgiveuniformboundsasparametersdegenerate. Quantitatively putp_C=P(g∈C),m_C=E(g|C). Everyfeasible solution satisfiesΣ_C p_C[σ_C(α_C)−α_C·m_C]≤D−FDR/q+E[N^{-1}Σ_null β_Ci K_u(g_i)]≤D+π0 c_u/2. Eachgap≥Σ_j d_Cj|α_Cj|, where d_Cj is thepositive conditionalmean distance to theallowed finiteendpoint (minimumoftwo distances forboundedinterval). Hence |α_Cj|≤(D+π0c_u/2)/(p_C d_Cj). Rarecellprobabilities/distancescanbe arbitrarilytiny, allowinghugecoefficients. A numerical scaled-budget system thatretainsbaseline/β sourcesisNOTthis homogeneousrecessioncone. Proof andglobaldual beta-columnsum identities: research-local/paired_stein_dual_capacity_compactness_20261104T215541Z.md. The neededuniform bound on the signed dualbaseline remainsunproved.
