---
type: search_round
title: 'Round 5: constant ties, endpoint rank events, and near-zero correlations'
target_asset: gaussian_bh_finite_signed_p_path_identity
mode: refute
round: 5
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates: []
statement_digest: d7a8a4f0b24ea902729e5f1f7788367f78c722f470f62ba2b0bf55c676594eec
performed_by: unknown
created_at: '2026-11-09T21:03:15.264Z'
extension_version: 0.0.4
---

## Obstructions

- A conditionally constant path with correlation zero does not create infinitely many crossing events merely by being constant. Its Gaussian residual has variance one, so equality to any of the finitely many deterministic BH score thresholds has probability zero. This observation does not permit discarding a realized exact tie: the statement retains such a path in the non-strict count. The examined two-coordinate exact-tie case also leaves the clipped path continuous and supplies no violation.
- A rank change occurring only at the excluded right endpoint does not itself force an endpoint jump of the clipped path. In the examined endpoint configuration, clipping gives the required limit of one as the path approaches the endpoint. An endpoint rank event therefore supplied no counterexample to the asserted limit in that configuration.
- The examined near-zero correlations, negative-null weights, and endpoint regimes supplied no new plausible violation of the finite signed identity. The searches did not identify an object requiring a new candidate record; changing these parameters alone did not evade the mechanisms already recorded on the board.

## Limitations

All three round-5 slots returned no candidate. There is no survivor and no newly verified counterexample. These checks exclude only the examined failure mechanisms; they are not a proof of the target, a general treatment of constant threshold ties, or a uniform perturbation argument near zero correlation.

Joint measurability, measurable finite event selection, arbitrary simultaneous crossings and constant ties, the general endpoint and derivative assertions, conditional change of variables, and absolute integrability of the random signed jump sums still require general proofs. The exact signed correction must retain both jump signs and omit removable isolated point discrepancies. No quantitative positive-jump budget, or proof or refutation of the main universal-constant FDR target, follows from this round.

These observations do not add a genuinely new proof step beyond the finite-event and bounded-variation approach already on the board; no separate approach idea is recorded.
