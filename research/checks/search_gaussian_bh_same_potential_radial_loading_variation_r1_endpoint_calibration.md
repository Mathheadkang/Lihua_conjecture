---
type: search_round
title: 'Radial loading round 1: endpoint checks and scope calibration'
target_asset: gaussian_bh_same_potential_radial_loading_variation
mode: refute
round: 1
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates: []
statement_digest: 4fdd9f2e842b76290c660caf30ede224f0ee87a0eba3d74506e1fd2489a7ddf4
performed_by: unknown
created_at: '2026-11-09T11:12:24.400Z'
extension_version: 0.0.4
---

## Obstructions

- Zero-loading trials cannot refute the radial kernel or fixed-rank integration-by-parts identities by a nonzero radial contribution: for $v=0$, $X(v)=0$, $c_r^2=s^2+\tau_s^2$ and $K_r$ is constant in $r$, while $D_0A=D_0Q_X(t)=0$. This excludes that particular violation mechanism, not every conclusion of the target for a baseline containing zero-loading particles.
- An endpoint singularity caused solely by the residual variance vanishing is unavailable on the physical loading interval: $r^2\|v\|^2\le1$ gives $c_r^2\ge s^2>0$, including unit loading at $r=1$. The specified one-sided endpoint derivatives therefore cannot be refuted merely by treating that endpoint as a zero-variance kernel. This does not establish the claimed bounds for convex-limit potentials.
- The earlier search report says the tested kernel identities, parameter endpoints and fixed-rank integration by parts were compatible with the statement. No candidate object or candidate calculation is supplied in this round's pack. Accordingly, there is no verified exclusion of a broader family of lawful global maximizers, and no negative object is inferred from a failed proof attempt or an arbitrary baseline.

## Limitations

- There are zero candidates in the supplied round. No explicit genuine deterministic canonical normalized global maximum, with its fixed matching dual pair and all certificate conditions, was constructed or verified. In particular, a simple directing law was not substituted for that hypothesis.
- Beyond the elementary zero-loading and positive-variance checks above, the earlier report is a search outcome rather than a proof certificate. No candidate bodies, detailed computations or independent verifications are included in this summary's context.
- Uniform radial derivative constants through order three, compactness and identification in the stated evaluation topology, and regularity of the same fixed convex-limit potentials still require general arguments. No new proof approach is recorded from the endpoint checks alone.
- Global contact comparisons, Borel representative invariance and integrability of the contact derivative, and differentiability under a separable directing-law integral have not been settled by this round. Neither the bounded-test-weight integration-by-parts claim nor its analytic justifications have been proved here.
- This round does not address measurable hybrid selector or rank-switch weights by assuming additional smoothness, does not establish a full signed loading balance or a regularizer-independent $q$ payment, and establishes neither falsification nor proof of the target.
