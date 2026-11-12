---
type: search_round
title: 'Round 1: full-private-noise endpoint and bounded-dimension obstructions'
target_asset: gaussian_bh_one_sided_private_noise_floor_order
mode: refute
round: 1
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - >-
    cand_gaussian_bh_one_sided_private_noise_floor_order_r1_s1_unit_floor_singular_alternatives
  - >-
    cand_gaussian_bh_one_sided_private_noise_floor_order_r1_s2_two_antialigned_nulls
  - >-
    cand_gaussian_bh_one_sided_private_noise_floor_order_r1_s3_full_private_null_singular_alt
statement_digest: 13ea882c68f2e481926074b4d0aebd215f088e2fc535bf626cb19200b933661d
performed_by: unknown
created_at: '2026-11-11T01:16:15.791Z'
extension_version: 0.0.4
---

## Obstructions

- Full-private-noise nulls form one overlapping family, covering both the unit-floor singular-alternative candidate and the full-private-null singular-alternative candidate. Whenever every true null has actual private noise s_i=1, unit variance forces every null loading a_i=0. Null p-values are then mutually independent and independent of the entire alternative block. Ordinary largest-rank BH therefore satisfies FDR <= (m_0/N) q, with equality for zero null means; in the two reported candidates this is q/2. Arbitrary singularity, ties, or q-dependence of the alternative block does not undo this independence. Thus the normalized ratio is at most 1/sqrt(log(1/q)), which tends to zero. This obstruction covers the whole endpoint s_0=1 and actual full-private-null models within smaller-floor classes; it does not cover general models with 0<s_0<1.
- Uniformly bounded dimension rules out any small-case family, including the two antialigned-null candidate, regardless of its particular negative correlation. For N<=M with M fixed, any rejected null has p_i<=q since the BH cutoff is at most q. Superuniform null marginals and the union bound give FDR <= P(V>0) <= m_0 q <= M q, so the normalized ratio is at most M/sqrt(log(1/q)) and tends to zero. A candidate refuting the uniform target cannot remain in a dimension bound fixed across its q-indexed family.
- The proof-like reductions above are recorded as draft approach idea_d7fe1abf6391; they exclude these families only and provide no general fixed-floor aggregation bound.

## Limitations

- All three reported candidates fail NOT. No counterexample survived this round, and absence of a survivor does not establish the target.
- The round does not control growing N with genuine common-factor loadings on some nulls under one fixed 0<s_0<1. In particular, it gives no uniform estimate over arbitrary loading geometry, factor dimension, mixed private-noise levels, null proportions, or q-dependent alternative configurations in this regime.
- Full-private-noise endpoint arguments and bounded-N bounds cannot be substituted for the asserted uniform fixed-floor bound. Neither a floor tending to zero nor modifications of the prescribed largest-rank BH rule would refute the stated target.
- This summary uses the context pack and its candidate failure lines only. Candidate bodies and the full-private-noise BH identity were not independently audited here; the draft approach is not an approved result. The proposed Mehler-kernel and finite-array aggregation steps remain unproved.
