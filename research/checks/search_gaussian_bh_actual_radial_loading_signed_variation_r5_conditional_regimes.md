---
type: search_round
title: 'Round 5: conditional perturbation regimes and mixed-label diagnostics'
target_asset: gaussian_bh_actual_radial_loading_signed_variation
mode: refute
round: 5
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates: []
statement_digest: 7fdc4735d0d5e381ad9fbb0ee8f7ab5df233763c161d5f77194d54300e4e7cac
performed_by: unknown
created_at: '2026-11-09T18:36:09.363Z'
extension_version: 0.0.4
---

## Obstructions

- **Large conditional perturbations alone do not force a domination failure.** On the conditional regime $d_X=\epsilon C_X\ge a/2$, the bounded cutoff payoff lies in $[0,1]$, so its conditional expectation difference quotient has absolute value at most $1/\epsilon\le 2C_X/a$. Thus exceptional backgrounds falling outside the small-perturbation regime do not by themselves produce an unbounded quotient relative to $C_X$. The round found no concrete violation of the actual-rank brackets. This elementary large-perturbation bound does not prove those brackets or the required bound when $d_X<a/2$.
- **Opposite signed contributions alone do not contradict the complete response.** The finite-grid diagnostic for a two-dimensional, three-atom triangular mixed-label law retained both the bulk and rank terms with their opposite signs, and their sum matched the directly computed difference quotient at the tested resolutions. A coarse-grid discrepancy in a low-density region was traced to grid discretization. That discrepancy supplies no obstruction or counterexample. The reported agreement is a diagnostic for the tested law, not a general identity or a formal numerical certificate.
- **The tested endpoint mechanisms supplied no violating object.** The endpoint direction found no concrete violation under the stated positive smoothing, tag, and finite-moment requirements. This records the unsuccessful search direction; it does not exclude all endpoint mechanisms or establish quantitative finite endpoint recovery.

## Limitations

- All three slots wrote no candidates in round 5. There is no survivor, failed-candidate check ledger, or independent counterexample verification for this round. In particular, numerical agreement was not converted into a candidate with an unestablished NOT check.
- The large-perturbation estimate covers only $d_X\ge a/2$. The actual-rank qualifier brackets in the small-perturbation regime, the conditional domination bound there, signed-weight integration, and the outer-expectation interchange remain proof obligations. The large-background mechanism is already represented by the existing idea `idea_10a124fa2814`; this summary adds no duplicate idea.
- The mixed-label computation is restricted to a finite-grid diagnostic for one finite law. It establishes neither a general all-active-minima response formula nor a formal numerical certificate. It does not settle arbitrary tied suffix minima, low-density quantile behavior, or all permissible $C^1$ cutoffs.
- Joint measurability, representative invariance, differentiation under arbitrary directing laws, compact-uniform quantile and barrier differentiation, absence of minimizing escapes to rank one, survival absolute continuity, convergence of survival difference quotients in $L^1(dr)$, and convergence of the actual ranks still require proofs.
- No general proof or formal numerical certificate was obtained. Genuine extremal comparison and canonical finite endpoint recovery with $o(\epsilon)$ errors for full FDR, cutoff FDR, and the second mean moment remain to be justified. The round establishes no identification with a selected dual radial contact derivative, covariance monotonicity, selector Sobolev or bounded-variation regularity, Gaussian integration-by-parts formula, or estimate uniform as the regularizers vanish.
