---
type: idea
title: Antipodal mixed labels force a negative derivative density beyond the cutoff
status: draft
idea_kind: test_case
origin: agent
related_assets:
  - gaussian_bh_private_noise_cutoff_signed_transport_variation
tags: []
tried_in:
  - target: gaussian_bh_private_noise_cutoff_signed_transport_variation
    round: 3
    slot: 1
    statement_digest: 678b5ca0bc054ae3e466058cbe1c77cb985edbf7afbd22f2e2ab1034682a803c
    outcome: >-
      cand_gaussian_bh_private_noise_cutoff_signed_transport_variation_r3_s1_antipodal_false_transport
      failed: H1 ✓ H2 ✓ H3 ✓ H4 ✓ H5 ✓ H6 ✓ H7 ✓ NOT ✗ — NOT fails: antipodal
      mixed labels do produce negative payoff-density transport beyond the
      cutoff, but the complete signed numerator-plus-all-minima formula
      reproduces that contribution with uniform Gaussian-integrable domination.
---

A concrete stress test for retaining signed rank/payoff terms, not a claimed counterexample. Fix sigma,s>0 with sigma^2+s^2<1, tau_s=sqrt(1-sigma^2-s^2), and deterministic directing law mu=(1/2)delta_(theta=0,v=e1,ell=1)+(1/2)delta_(theta=A,v=-e1,ell=0), A>0. Private standard deviations are both s. Parameters are chosen before independent X,Z. Conditional on X(e1)=x>A/(2 tau_s), the true score centre tau_s*x lies strictly above the false centre A-tau_s*x. Equal-variance Gaussian monotone likelihood ratio then implies that the true density posterior at score quantile Q(r) is strictly below the true upper-tail proportion f(r): thus f'(r)=[h0(Q)/h(Q)-f(r)]/r<0 for every r in (0,1). In particular (chi_a*f)' is negative beyond 2a on this positive-probability background, although its cutoff part may be positive. The full derivative must retain cancellation between these signs. Test lawful false-mean velocities b_false=+1 and -1 (epsilon<A), b_true=0, and/or a level velocity, using the actual suffix minimum. Establish the likelihood-ratio assertion and Gaussian integrability rather than treating it as an approved lemma. Never replace the signed density by its absolute value, or optimize rank freely. This is distinct from equal-centre mixtures where f is constant and from the all-null translation example.

## Tried

- Search round 3 for gaussian_bh_private_noise_cutoff_signed_transport_variation (slot 1): cand_gaussian_bh_private_noise_cutoff_signed_transport_variation_r3_s1_antipodal_false_transport failed: H1 ✓ H2 ✓ H3 ✓ H4 ✓ H5 ✓ H6 ✓ H7 ✓ NOT ✗ — NOT fails: antipodal mixed labels do produce negative payoff-density transport beyond the cutoff, but the complete signed numerator-plus-all-minima formula reproduces that contribution with uniform Gaussian-integrable domination.
