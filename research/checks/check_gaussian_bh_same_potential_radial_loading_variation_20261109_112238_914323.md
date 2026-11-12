---
type: falsification_check
title: 'Falsification check: gaussian_bh_same_potential_radial_loading_variation'
target_asset: gaussian_bh_same_potential_radial_loading_variation
outcome: no_counterexample_found
statement_digest: 4fdd9f2e842b76290c660caf30ede224f0ee87a0eba3d74506e1fd2489a7ddf4
performed_by: unknown
created_at: '2026-11-09T11:22:38.492Z'
extension_version: 0.0.4
---

## Cases checked

- Round 1, boundary_degenerate: no plausible candidate.
- Round 1, small_cases: no plausible candidate.
- Round 1, drop_hypothesis: no plausible candidate.
- Round 2, known_counterexamples: no plausible candidate.
- Round 2, extremal: no plausible candidate.
- Round 2, boundary_degenerate: no plausible candidate.
- Round 3, boundary_degenerate: no plausible candidate.
- Round 3, small_cases: no plausible candidate.
- Round 3, drop_hypothesis: no plausible candidate.
- Round 4, boundary_degenerate: no plausible candidate.
- Round 4, small_cases: no plausible candidate.
- Round 4, drop_hypothesis: no plausible candidate.
- Round 5, boundary_degenerate: no plausible candidate.
- Round 5, small_cases: no plausible candidate.
- Round 5, drop_hypothesis: no plausible candidate.
- Obstruction: Zero-loading trials cannot refute the radial kernel or fixed-rank integration-by-parts identities by a nonzero radial contribution: for $v=0$, $X(v)=0$, $c_r^2=s^2+\tau_s^2$ and $K_r$ is constant in $r$, while $D_0A=D_0Q_X(t)=0$. This excludes that particular violation mechanism, not every conclusion of the target for a baseline containing zero-loading particles.
- Obstruction: An endpoint singularity caused solely by the residual variance vanishing is unavailable on the physical loading interval: $r^2\|v\|^2\le1$ gives $c_r^2\ge s^2>0$, including unit loading at $r=1$. The specified one-sided endpoint derivatives therefore cannot be refuted merely by treating that endpoint as a zero-variance kernel. This does not establish the claimed bounds for convex-limit potentials.
- Obstruction: The earlier search report says the tested kernel identities, parameter endpoints and fixed-rank integration by parts were compatible with the statement. No candidate object or candidate calculation is supplied in this round's pack. Accordingly, there is no verified exclusion of a broader family of lawful global maximizers, and no negative object is inferred from a failed proof attempt or an arbitrary baseline.
- Obstruction: A radial singularity caused solely by vanishing residual variance cannot occur on the physical interval: the stated relation $r^2\|v\|^2\le1$ gives $c_r^2\ge s^2>0$. In particular, a unit-loading endpoint does not provide a zero-variance counterexample. Constants are allowed to depend on the fixed positive smoothing and other fixed regularizers, so deterioration when those regularizers vary does not itself violate the target.
- Obstruction: Zero-loading trials cannot produce a nonzero radial-kernel or fixed-rank integration-by-parts discrepancy: $v=0$ makes $X(v)=0$, $K_r$ constant in $r$, and both $D_0A$ and $D_0Q_X(t)$ zero. This only excludes this mechanism; it does not certify the other conclusions for a baseline containing zero-loading particles.
- Obstruction: Arbitrary simple directing laws, noise-selected baselines, or newly selected dual pairs cannot witness failure of the contact condition under the stated hypotheses. The target requires a genuine deterministic canonical normalized global maximum and its same fixed matching pair. The supplied round constructs no such object, so a failed contact comparison outside that class cannot be counted as a counterexample.
- Obstruction: A zero-loading trial cannot produce a radial-kernel or fixed-rank integration-by-parts discrepancy: when $v=0$, $X(v)=0$, $c_r$ and $K_r$ are constant in $r$, and $D_0A=D_0Q_X(t)=0$. This excludes only this discrepancy mechanism.
- Obstruction: Residual-variance collapse cannot occur anywhere on a physical radial interval, including a longer interval allowed by small nonzero loading: $r^2\|v\|^2\le1$ implies $c_r^2\ge s^2>0$. Moreover, $r\|v\|^2\le\|v\|\le1$, so extending the interval does not alone make the variance-derivative coefficient unbounded. The supplied round report found no contradiction from this mechanism; this observation does not establish all derivative bounds or their passage to a convex limit.
- Obstruction: Divergence obtained solely by sending the smoothing or other fixed regularizers to a boundary is outside the asserted uniformity. The statement permits constants to depend on the fixed positive parameters; such divergence alone cannot violate it.
- Obstruction: A putative integration-by-parts discrepancy obtained by freezing the baseline quantile during Cameron-Martin differentiation, or by dropping the test-weight derivative, tests a different identity. The actual target retains both $D_vQ_X(t)$ and $D_vA$. The round report says its one-dimensional check retained the background derivative and was compatible with the identity, but supplies no candidate calculation for independent verification here.
- Obstruction: An arbitrary simple directing law, a noise-selected baseline, or a newly chosen matching pair cannot test the contact conclusion under the stated hypotheses. It requires a genuine deterministic canonical normalized global maximum and the same fixed matching pair satisfying the full certificate. No such explicit object was supplied this round.
- Obstruction: Residual-variance collapse cannot refute the kernel statements on a physical radial interval: the hypothesis $r^2\|v\|^2\leq1$ gives $c_r^2\geq s^2>0$, including a unit-loading endpoint; deterioration as fixed regularizers vary is outside the asserted uniformity.
- Obstruction: Zero-loading trials cannot produce a nonzero radial-kernel or fixed-rank integration-by-parts discrepancy: $X(0)=0$, the radial kernel is constant, and $D_0A=D_0Q_X(t)=0$; this excludes only that discrepancy mechanism.
- Obstruction: An integration-by-parts discrepancy obtained by suppressing the baseline quantile derivative or the test-weight derivative does not test the stated identity, which retains both terms.
- Obstruction: Contact comparisons for an arbitrary directing law, a noise-selected baseline, or a replacement dual pair cannot refute the contact conclusion: the hypotheses require a genuine deterministic canonical normalized global maximum and its same fixed matching pair.
- Obstruction: A proposed radial-origin singularity caused solely by residual-variance collapse cannot occur: at fixed positive smoothing the physical loading interval has $c_r^2\ge s^2>0$, including $r=0$. The round report says its Hermite expressions through order three at the origin were finite. No expressions or candidate calculations are supplied in this pack, so that report does not establish explicit uniform derivative constants or their passage to limiting potentials.
- Obstruction: An unbounded sample supremum of the isonormal field over loading directions does not itself violate the target's bounds. The conditional kernel envelope explicitly retains $|X(v)|^m$ for each fixed trial, while the potential conclusions concern Gaussian-averaged expressions, uniformly over deterministic trial choices. A pathwise bound on the field over the entire Hilbert ball is not asserted. Thus the family of objections based only on that sample supremum targets a stronger claim; the needed averaged derivative estimates remain to be proved.
- Obstruction: Contact comparisons for arbitrary simple directing laws, noise-selected baselines, or newly chosen matching pairs cannot refute the stated contact condition. Its hypotheses require a genuine deterministic canonical normalized global maximum and the same fixed matching pair satisfying the full certificate. No such global maximum, fixed matching pair, or actual contact particle was constructed, certified, or directly tested in this round.

## Limitations

- Round 5 supplies no candidates. The reported three-atom, two-dimensional mixed-loading calculation was only a short numerical diagnostic for the quantile derivative and the complete integration-by-parts identity. Numerical agreement is not proof; the pack supplies neither numerical values nor candidate calculations for independent verification, and it excludes no general family of directing laws.
- No genuine global-maximum contact condition was tested. In particular, the finite-mixture diagnostic does not establish the loading-normal sign, equality at interior contact particles, or use of the same fixed convex-limit matching pair at a lawful optimum.
- Explicit finite constants for all radial derivatives through order three, uniform bounds for generating potentials, one-dimensional compactness and identification, and convergence of derivatives of every sequence approaching the same fixed limiting potential remain analytic proof obligations. Finite origin expressions and the field-supremum quantifier distinction do not supply those arguments. No new proof-step approach is established by the supplied report.
- Borel measurability, representative invariance and integrability of the contact derivative, differentiation under an arbitrary separable directing-law integral, and the Gaussian boundary and absolute-integrability arguments for every allowed test weight remain unverified here. Both the test-weight derivative and the baseline quantile derivative must be retained.
- No regularizer-limit exchange, regularizer-independent estimate, full signed loading balance for measurable selector or rank-switch weights, or uniform $q$-scaled payment was tested or established. The round supplies neither a counterexample nor a proof of the target.

Object search: 0 candidate(s) in 5 round(s).
