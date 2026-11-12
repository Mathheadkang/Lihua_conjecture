---
type: search_round
title: 'Round 3: fixed-smoothing radial search and untested certificate conditions'
target_asset: gaussian_bh_same_potential_radial_loading_variation
mode: refute
round: 3
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates: []
statement_digest: 4fdd9f2e842b76290c660caf30ede224f0ee87a0eba3d74506e1fd2489a7ddf4
performed_by: unknown
created_at: '2026-11-09T11:17:12.423Z'
extension_version: 0.0.4
---

## Obstructions

- A zero-loading trial cannot produce a radial-kernel or fixed-rank integration-by-parts discrepancy: when $v=0$, $X(v)=0$, $c_r$ and $K_r$ are constant in $r$, and $D_0A=D_0Q_X(t)=0$. This excludes only this discrepancy mechanism.
- Residual-variance collapse cannot occur anywhere on a physical radial interval, including a longer interval allowed by small nonzero loading: $r^2\|v\|^2\le1$ implies $c_r^2\ge s^2>0$. Moreover, $r\|v\|^2\le\|v\|\le1$, so extending the interval does not alone make the variance-derivative coefficient unbounded. The supplied round report found no contradiction from this mechanism; this observation does not establish all derivative bounds or their passage to a convex limit.
- Divergence obtained solely by sending the smoothing or other fixed regularizers to a boundary is outside the asserted uniformity. The statement permits constants to depend on the fixed positive parameters; such divergence alone cannot violate it.
- A putative integration-by-parts discrepancy obtained by freezing the baseline quantile during Cameron-Martin differentiation, or by dropping the test-weight derivative, tests a different identity. The actual target retains both $D_vQ_X(t)$ and $D_vA$. The round report says its one-dimensional check retained the background derivative and was compatible with the identity, but supplies no candidate calculation for independent verification here.
- An arbitrary simple directing law, a noise-selected baseline, or a newly chosen matching pair cannot test the contact conclusion under the stated hypotheses. It requires a genuine deterministic canonical normalized global maximum and the same fixed matching pair satisfying the full certificate. No such explicit object was supplied this round.

## Limitations

- Round 3 supplies no candidates and no candidate bodies. Its report states that heavy-tailed means and separable infinite-dimensional loadings did not expose fixed-rank quantile derivative failure. Without the underlying constructions and calculations, these reports do not exclude either general family or prove differentiability under the directing-law integral.
- No explicit actual global maximum was constructed or checked, and no fixed closed matching pair was exhibited and tested. Contact-normal conditions, same-pair closure transfer, and the certificate hypotheses therefore received no direct object-level test.
- General finite radial derivative constants, one-dimensional compactness, identification of the derivatives from evaluation convergence, and radial regularity of the same limiting potentials remain proof obligations. No new proof-step obstruction is extracted as a native approach from the supplied report alone.
- Borel measurability, representative invariance, contact-derivative integrability, and the full separable-law differentiation argument remain unresolved by this search. The one-dimensional report does not establish the required Gaussian boundary and absolute-integrability arguments for every allowed test weight.
- No regularizer-independent estimate, full signed loading balance for measurable hybrid selector or rank-switch weights, or uniform $q$-scaled payment was tested or established. This round establishes neither a counterexample nor a proof of the target.
