---
type: search_round
title: 'Radial loading round 2: fixed smoothing and limits of the negative search'
target_asset: gaussian_bh_same_potential_radial_loading_variation
mode: refute
round: 2
directions:
  - known_counterexamples
  - extremal
  - boundary_degenerate
candidates: []
statement_digest: 4fdd9f2e842b76290c660caf30ede224f0ee87a0eba3d74506e1fd2489a7ddf4
performed_by: unknown
created_at: '2026-11-09T11:14:33.140Z'
extension_version: 0.0.4
---

## Obstructions

- A radial singularity caused solely by vanishing residual variance cannot occur on the physical interval: the stated relation $r^2\|v\|^2\le1$ gives $c_r^2\ge s^2>0$. In particular, a unit-loading endpoint does not provide a zero-variance counterexample. Constants are allowed to depend on the fixed positive smoothing and other fixed regularizers, so deterioration when those regularizers vary does not itself violate the target.
- Zero-loading trials cannot produce a nonzero radial-kernel or fixed-rank integration-by-parts discrepancy: $v=0$ makes $X(v)=0$, $K_r$ constant in $r$, and both $D_0A$ and $D_0Q_X(t)$ zero. This only excludes this mechanism; it does not certify the other conclusions for a baseline containing zero-loading particles.
- Arbitrary simple directing laws, noise-selected baselines, or newly selected dual pairs cannot witness failure of the contact condition under the stated hypotheses. The target requires a genuine deterministic canonical normalized global maximum and its same fixed matching pair. The supplied round constructs no such object, so a failed contact comparison outside that class cannot be counted as a counterexample.

## Limitations

- Round 2 supplies no candidates and no candidate bodies or detailed calculations. Its search report says that nonzero-loading derivative envelopes, evaluation and third-order control, physical radial intervals, and label boundaries exposed no contradiction. These reported checks do not establish a universal exclusion of counterexamples.
- No explicit genuine global maximum with its fixed matching dual pair and every certificate condition was constructed or verified. The contact-normal conclusion therefore received no direct test on an exhibited lawful maximizer.
- The general finite derivative constants, compactness and derivative identification from evaluation convergence, and radial regularity of the same limiting potentials remain proof obligations. A report of no observed failure is not their proof, and no new proof approach is extracted without a supplied argument.
- The pack supplies no resolution of Borel measurability, representative invariance, contact-derivative integrability, separable directing-law differentiation, or the analytic requirements for bounded-test-weight Gaussian integration by parts. The baseline quantile derivative and the test-weight derivative must both remain present.
- No regularizer-independent estimate, full signed loading balance for measurable hybrid selector or rank-switch weights, or $q$-scaled payment was established. This summary establishes neither falsification nor proof of the target and does not assume extra regularity of those weights.
