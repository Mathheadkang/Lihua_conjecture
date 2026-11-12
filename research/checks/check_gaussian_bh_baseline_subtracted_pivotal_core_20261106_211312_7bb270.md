---
type: falsification_check
title: 'Falsification check: gaussian_bh_baseline_subtracted_pivotal_core'
target_asset: gaussian_bh_baseline_subtracted_pivotal_core
outcome: no_counterexample_found
statement_digest: 182210875024e41e07afd86320271d77d4c3101bb674953cf99e16eee40678ba
performed_by: unknown
created_at: '2026-11-06T21:13:12.804Z'
extension_version: 0.0.4
---

## Cases checked

- Round 1, boundary_degenerate: no plausible candidate.
- Round 1, small_cases: no plausible candidate.
- Round 1, drop_hypothesis: no plausible candidate.
- Round 1, known_counterexamples: no plausible candidate.
- Round 1, extremal: no plausible candidate.
- Round 2, boundary_degenerate: no plausible candidate.
- Round 2, small_cases: no plausible candidate.
- Round 2, drop_hypothesis: no plausible candidate.
- Round 2, known_counterexamples: no plausible candidate.
- Round 2, extremal: no plausible candidate.
- Round 3, boundary_degenerate: no plausible candidate.
- Round 3, small_cases: no plausible candidate.
- Round 3, drop_hypothesis: no plausible candidate.
- Round 3, known_counterexamples: no plausible candidate.
- Round 3, extremal: no plausible candidate.
- Round 4, boundary_degenerate: no plausible candidate.
- Round 4, small_cases: no plausible candidate.
- Round 4, drop_hypothesis: no plausible candidate.
- Round 4, known_counterexamples: no plausible candidate.
- Round 4, extremal: no plausible candidate.
- Round 5, boundary_degenerate: no plausible candidate.
- Round 5, small_cases: no plausible candidate.
- Round 5, drop_hypothesis: no plausible candidate.
- Round 5, known_counterexamples: no plausible candidate.
- Round 5, extremal: no plausible candidate.
- Round 6, boundary_degenerate: no plausible candidate.
- Round 6, small_cases: no plausible candidate.
- Round 6, drop_hypothesis: no plausible candidate.
- Round 6, known_counterexamples: no plausible candidate.
- Round 6, extremal: no plausible candidate.
- Round 7, boundary_degenerate: no plausible candidate.
- Round 7, small_cases: no plausible candidate.
- Round 7, drop_hypothesis: no plausible candidate.
- Round 7, known_counterexamples: no plausible candidate.
- Round 7, extremal: no plausible candidate.
- Round 8, boundary_degenerate: no plausible candidate.
- Round 8, small_cases: no plausible candidate.
- Round 8, drop_hypothesis: no plausible candidate.
- Round 8, known_counterexamples: no plausible candidate.
- Round 8, extremal: no plausible candidate.
- Round 9, boundary_degenerate: no plausible candidate.
- Round 9, small_cases: no plausible candidate.
- Round 9, drop_hypothesis: no plausible candidate.
- Round 9, known_counterexamples: no plausible candidate.
- Round 9, extremal: no plausible candidate.
- Round 10, boundary_degenerate: no plausible candidate.
- Round 10, small_cases: no plausible candidate.
- Round 10, drop_hypothesis: no plausible candidate.
- Round 10, known_counterexamples: no plausible candidate.
- Round 10, extremal: no plausible candidate.
- Obstruction: A failure based only on singular covariance destroying frozen-threshold independence is obstructed by joint Gaussian independence: each retained nonmover has zero covariance with the null coordinate, so their joint vector is independent of that coordinate even when its covariance matrix is singular. The mover coordinates in the frozen vector are constants. Thus the frozen threshold is independent of the null p-value. Its values lie in $[q/N,q]$, and conditional uniformity gives $\mathbb E[a(T_i;\tau_i^\flat)]=1$. This is a proof-route observation to be checked in formal proof execution, not a verified proof verdict.
- Obstruction: A failure based on the sign of the subtracted expression is obstructed by coordinate monotonicity of the BH step-up count. Replacing mover p-values by one can only decrease the count, hence $0<\tau_i^\flat\le\tau_i$. For $p\le\tau_i^\flat$, the difference is $1/\tau_i-1/\tau_i^\flat\le0$; for $\tau_i^\flat<p\le\tau_i$, it equals $1/\tau_i$; and for $p>\tau_i$, it is zero. These regimes support the proposed pointwise upper inequality, subject to formal proof execution.
- Obstruction: An empty mover set cannot supply a counterexample through baseline subtraction: then the two threshold vectors coincide. In particular, $N=1$ gives both thresholds equal to $q$ and the uniform null p-value gives $\Delta_i=0$.
- Obstruction: Letting the finite dimension depend arbitrarily on $q$ does not evade these structural observations: the independence argument, positive lower threshold $q/N$, and three pointwise regimes apply separately at every finite admissible $(N,q)$. No uniform-in-dimension asymptotic approximation was used in these observations.
- Obstruction: Endpoint-level examples with $q=0$ or $q=1$ fail the hypothesis $q\in(0,1)$.
- Obstruction: Zero-dimensional and infinite-dimensional examples fail the finite positive-dimensional Gaussian testing model hypothesis.
- Obstruction: Examples with a zero-variance null coordinate fail the standardized Gaussian marginal hypothesis used to obtain the uniform null p-value.
- Obstruction: No new family-level obstruction was established: all five workers reported no distinct admissible candidate and wrote no candidate files.
- Obstruction: No new family-level obstruction was established: all five workers reported no distinct admissible candidate and wrote no candidate files.
- Obstruction: No new family-level obstruction was established: all five workers reported no distinct admissible candidate and wrote no candidate files.
- Obstruction: No new family-level obstruction was established: all five workers reported no distinct admissible candidate and wrote no candidate files.
- Obstruction: No new family-level obstruction beyond the supplied board emerged; no distinct admissible candidate was reported.
- Obstruction: No new family-level obstruction beyond the supplied board was established; no distinct admissible candidate emerged.
- Obstruction: No new family-level obstruction beyond the board emerged; no distinct admissible candidate was reported.
- Obstruction: No new family-level obstruction beyond the board emerged; no distinct admissible candidate was reported.

## Limitations

All five bounded directions (boundary_degenerate, small_cases, drop_hypothesis, known_counterexamples, extremal) yielded no candidate files in this final configured round. Previously excluded families and objects outside the hypotheses were not repeated. No new calculation, numerical coverage, proof coverage, or exhaustive coverage is claimed; there is no survivor to verify, and absence of candidates supplies no proof or verification verdict.

Object search: 0 candidate(s) in 10 round(s).
