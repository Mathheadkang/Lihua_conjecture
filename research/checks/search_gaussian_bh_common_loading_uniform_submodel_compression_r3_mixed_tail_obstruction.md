---
type: search_round
title: 'Round 3: competing mixed prefixes and growing orthogonal null clouds'
target_asset: gaussian_bh_common_loading_uniform_submodel_compression
mode: refute
round: 3
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - >-
    cand_gaussian_bh_common_loading_uniform_submodel_compression_r3_s2_three_direction_prefixes
  - >-
    cand_gaussian_bh_common_loading_uniform_submodel_compression_r3_s3_orthogonal_null_cloud
statement_digest: 559f931c8cf870c13d2afe6f41bae6c492b9b6e20edb09e35b2275ac15e3ed5d
performed_by: unknown
created_at: '2026-11-09T05:25:13.867Z'
extension_version: 0.0.4
---

## Obstructions

- In the tested three-direction finite-prefix family, competing mixed-tag crossing roots do not create a persistent discrepancy: the candidate's reported crossing-threshold changes are bounded by a constant times the multinomial frequency error; Gaussian smoothing and direct prefix-FDP comparison then make both expected errors vanish. This excludes the reported finite-prefix family, without asserting that its constants are uniform over arbitrary atom masses or an increasing number of prefixes.
- In the tested growing orthogonal all-null cloud, increasing residual dimension does not preserve a zero-versus-positive rejection mismatch: the candidate reports common-shift control at positive ranks and the approved microscopic-rank estimate for the remaining event. Because every tag is true, positive-rank FDP is exactly one; this all-null reduction does not settle mixed-tag populations.
- A deterministic proof step explains why mixed labels need not require FDP monotonicity once actual positive ranks have been compared. Write their normalized ranks as r and s, and their common-z score thresholds as b_r=u_q(r)-sigma z and b_s=u_q(s)-sigma z. Suppose r,s >= a, both total and tagged empirical-tail errors are at most gamma, and exact positive-rank self-consistency holds: H(b_r)=r and H_m(b_s)=s. Nested threshold sets and tagged-tail domination give |V(b_r)-V(b_s)| <= |H(b_r)-H(b_s)| <= |r-s|+gamma. Hence |V(b_r)-V_m(b_s)| <= |r-s|+2 gamma, and the original full FDPs obey |D_N-D_m| <= (2|r-s|+2 gamma)/a. Thus on this macroscopic event no additional tag-induced discontinuity survives a small rank discrepancy. This is a conditional algebraic proof step, not a proof of the required rank transfer or its probability bounds.

## Limitations

- Only the supplied current-stage pack and its two round-3 candidate failure lines were used. Candidate bodies and their constants were not independently audited; no survivor or confirmed counterexample was reported.
- These two failures do not cover arbitrary many-atom mixed populations, growing numbers of competing roots, cascades or threshold-near tangencies. Orthogonality with all-null labels does not exhaust growing-dimensional mixed models.
- The empirical-tail maximal estimate, two-way trimmed-rank transfer, exact continuous-rank/finite-grid identification, and unconditional self-consistency argument remain proof obligations. The deterministic FDP comparison above assumes self-consistency rather than importing an unprovided proof.
- The macroscopic comparison requires both ranks to exceed a. Events with one or both ranks microscopic still require the approved tagged microscopic bound together with rank control; the all-null candidate alone does not establish this for arbitrary mixed populations.
- Local uniformity over compact q sets, including vanishing of the microscopic bound uniformly in q, remains to be proved. No conclusion uniform as sigma tends to zero follows.
