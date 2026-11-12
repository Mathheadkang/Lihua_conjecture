---
type: idea
title: >-
  Common true-null direction: centered scalar innovation controls arbitrary
  finite BH cascades
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_bh_mixed_coherence_trace_budget
tags:
  - gaussian-bh
  - mixed-coherence-budget
  - common-null-direction
  - innovation
---

This is a scoped proof step extracted from the checked round-4 candidate cand_gaussian_bh_mixed_coherence_trace_budget_r4_s3_coherent_null_cascades, not a proof of the unrestricted target and not a researcher approval.

Assume every true-null observation vector equals one common unit vector v. Their nonpositive means, the finite number of tests and dimension, and all alternative means and unit-vector geometry are arbitrary, including dependence on q. On FDP support B/f=v s with s=1/h(u_R) in (0,1/H]; since a rejected true null implies v·G≥U, 0<F≤q. Under the prescribed terminal tilt, a_t=v k_t with k_t=E_Q[s(W_1)|F_t].

The checked candidate first derives entropy energy E_Q∫||β_t||²dt≤2D, then obtains the innovation Brownian motion Z_t=W_t−∫_0^tβ_rdr. The bounded scalar martingale obeys dk_t=∇k_t·dZ_t and E_Q∫||∇k_t||²dt=Var_Q(s), proving absolute trace integrability for K_t=v⊗∇k_t. Boundedness of a and finite entropy energy also give absolute drift integrability. Ito covariance and conditional expectation prove the required endpoint identity before its use: M=F E_Q[s(W_1)v·Z_1]=F E_Q∫tr K_tdt=lim_{τ↑1}M_τ. Conditional Jensen yields x≤H²E_Qs²≤1.

Now v·Z_1 is centered with variance one (independence from s is unnecessary). Center at the deterministic maximal mark 1/H and use (s−1/H)²≤H^(−2)−s² for 0≤s≤1/H. Thus |M|≤F sqrt(E_Q(s−1/H)²)≤(F/H)sqrt(E_Q(1−H²s²))≤(q/H)sqrt(1−x). In particular M_+≤q sqrt(1−x) for U≥3. This covers arbitrary actual-rank changes, multiple collapsing rank intervals, correlated alternatives and conservative null means as long as the true-null vectors remain exactly common. The correlated one-null pair candidates are instances of this family, rather than separate obstruction mechanisms. Distinct true-null directions remain uncovered; no necessity or sufficiency conclusion for the entropy-linear term follows.
