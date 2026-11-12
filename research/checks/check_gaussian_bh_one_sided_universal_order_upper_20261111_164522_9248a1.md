---
type: falsification_check
title: 'Falsification check: gaussian_bh_one_sided_universal_order_upper'
target_asset: gaussian_bh_one_sided_universal_order_upper
outcome: no_counterexample_found
statement_digest: cd12dcc669b996361216cbba6573ecfdf68a5a7c79acc1bbf89869a2e1233389
performed_by: unknown
created_at: '2026-11-11T16:45:22.513Z'
extension_version: 0.0.4
---

## Cases checked

- Round 1, boundary_degenerate: no plausible candidate.
- Round 1, small_cases: no plausible candidate.
- Round 1, drop_hypothesis: no plausible candidate.
- Round 2, known_counterexamples: no plausible candidate.
- Round 2, extremal: no plausible candidate.
- Round 2, idea_27c06facb739: no plausible candidate.
- Round 3, idea_57338934f2f7: no plausible candidate.
- Round 3, idea_8a445ee0b200: no plausible candidate.
- Round 3, idea_aca5b09e9a0c: no plausible candidate.
- Round 4, idea_b5466535b0cc: no plausible candidate.
- Round 4, idea_b87c754c46ad: no plausible candidate.
- Round 4, idea_d31f99b82bbb: no plausible candidate.
- Round 5, idea_e2f38f5dda41: no plausible candidate.
- Round 5, idea_ec6e01a9d5e2: no plausible candidate.
- Round 5, boundary_degenerate: no plausible candidate.
- Obstruction: Every model with an empty true-null set has false discovery rate zero, so this family cannot refute a positive upper bound.
- Obstruction: A rank-zero covariance cannot satisfy the unit-diagonal hypothesis for any positive number of tests. Singularity itself is admissible and is not excluded by this observation.
- Obstruction: For each finite admissible Gaussian model, every coordinate has variance one and hence a continuous marginal distribution. Each equality to any of the finitely many BH thresholds therefore has probability zero, even when the joint covariance is singular. A putative failure relying only on positive probability of such exact threshold equalities cannot work; this does not remove ties between coordinates or change the largest-rank BH convention.
- Obstruction: For valid null p-values under arbitrary dependence, the harmonic bound gives FDR <= (|I0|/N) q H_N, where H_N = sum_{k=1}^N 1/k. Consequently, for every fixed dimension ceiling M, all models with N <= M have FDR/[q sqrt(log(1/q))] <= H_M/sqrt(log(1/q)), which tends to zero as q decreases to zero. Bounded-dimensional families, including the checked cases N=1,2,3, cannot yield an asymptotically unbounded ratio. The dependence on H_N prevents this bound from proving the target's dimension-uniform conclusion.
- Obstruction: A lower-bound construction attaining only a finite multiple of q sqrt(log(1/q)) does not refute an upper bound with an unspecified universal constant. The primary-source worker reports that Lei, arXiv:2607.14812v4, gives the one-sided lower bound q sqrt(log(1/q))/sqrt(pi) + q/2 + o(q), consistent with the proposed order; it does not supply an asymptotically unbounded ratio. The source leads are idea_4e6b9464da07 and idea_af05c3f05dab.
- Obstruction: The arbitrary-dependence harmonic bound FDR <= pi0 q H_N, where pi0=|I0|/N and H_N=sum_{k=1}^N 1/k, rules out an asymptotically unbounded normalized FDR for every model sequence with pi0 H_N=O(sqrt(log(1/q))). In particular, unbalanced sequences with pi0 H_N=o(sqrt(log(1/q))) have FDR/[q sqrt(log(1/q))] tending to zero, even when N grows. This is a restriction on such sequences and does not bound the unrestricted supremum over N and pi0.
- Obstruction: The specified nonnegatively equicorrelated Gaussian family in idea_27c06facb739 is admissible, but Gaussian positive regression dependence gives BH FDR <= pi0 q <= q. Its large rare-count variance therefore obstructs an independent-count approximation rather than the main FDR upper bound. Varying this family's count variance alone cannot turn that proxy failure into a main-theorem counterexample.
- Obstruction: The collinear all-null finite mean grids in idea_8a445ee0b200 cannot refute the main bound. With a>0, theta_j=-aj/N, a common standard Gaussian Y, and S=barPhi, their exact largest-crossing threshold is b_N=min_{1<=j<=N}{aj/N+S^{-1}(qj/N)}. Every summand is at least S^{-1}(q), so FDR=S(b_N)<=q for every finite N. The separate question of transferring finite-model rare-clone derivatives through atomization does not furnish a counterexample to the main FDR bound.
- Obstruction: In the proposed two-level Gaussian hierarchy of idea_aca5b09e9a0c, a group's conditional null density depends on one combined latent projection. Multiplying two separate tilt gains therefore does not establish the claimed enhancement: the actual conditional density must be computed for the combined projection. This obstructs that product calculation, not every hierarchical or degenerate Gaussian family.
- Obstruction: The mixed-label rank-one family of idea_b5466535b0cc has actual FDR below q, uniformly over its size parameter m>=2 and 0<q<=S(1), where S=barPhi. Specifically, set N=2m, c_k=S^{-1}(qk/(2m)), mu=c_m, b=c_{m+1}, and M=c_1+2mu+2; its scores are m null copies of G, m-1 alternative copies of mu-G, and one alternative M-G. The rechecked largest-rank calculation gives FDR=q/2+S(M-b)/(m+1)<q/2+q/[2m(m+1)]<=q. The first Hermite contribution can grow with m only because other orders compensate it; losing that cancellation refutes an intermediate bound rather than the main theorem.
- Obstruction: With a single independent uniform null p-value and any fixed realization U of the alternative environment, the force-zero largest rank L(U) gives conditional FDP expectation (1/L(U))(qL(U)/N)=q/N. Thus the model in idea_b87c754c46ad has FDR=q/N even when its selected-null energy entropy grows. That entropy growth cannot by itself be interpreted as FDR inflation. The identity requires the stated independence and uniformity; it is not a bound for arbitrarily dependent nulls.
- Obstruction: The rank-one single-null Gaussian ladder in idea_d31f99b82bbb is controlled for all N>=2 and 0<q<=S(1): with u_j=S^{-1}(qj/N), scores T_0=X and T_j=2u_j-X, and b_j=2u_j-u_{j+1}, its full BH FDR is q/N+sum_{j=1}^{N-1}S(b_j)/[j(j+1)]<=q H_N/N<=q. Its positive harmonic remainder rules out a uniform per-null bound Cq/N, but its total FDR remains below q; that auxiliary failure does not refute the main universal-order statement.
- Obstruction: The negative-mean cluster family of idea_e2f38f5dda41 has all means nonpositive and all covariances nonnegative. Centering increases its scores coordinatewise and can only increase the all-null rejection event; the centered Gaussian model is PRDS and has BH FDR at most q. Thus the original all-null family also has FDR<=q. The loss in the proposed cluster-comparison denominator is an obstruction to that auxiliary comparison, not a counterexample to the main FDR bound. This argument uses the all-null labels and nonnegative covariances of this family.
- Obstruction: In the finite-replica family of idea_ec6e01a9d5e2, every true-null-to-coordinate covariance equals the nonnegative common-loading variance sigma^2. Gaussian PRDS on the true-null coordinates therefore gives ordinary BH FDR<=pi0 q=q/2, even though some alternative-to-alternative covariances are negative. A fold or steep pointwise response in this family does not overcome its actual FDR bound. This obstruction concerns finite replicas with their original Gaussian null p-values and labels; it does not assert PRDS for arbitrary signed covariance or independence of conditional compound p-values.

## Limitations

All three workers wrote no candidate files. The boundary worker found no new admissible family, which is an absence of a constructed counterexample rather than an exclusion theorem. No unbounded ratio FDR/[q sqrt(log(1/q))] was established, and no main conjecture was resolved.

The simultaneous regime in which q tends to zero, regularizing noise vanishes, means change, and the number of tests or directions grows remains allowed and unresolved. Singular limits and q-dependent degenerations outside the stated PRDS families are not ruled out by these checks. The two special-family controls do not bound aggregate false discoveries under arbitrary signed Gaussian dependence.

The finite conditional compound-p calibration and its independent source verification, the Gaussian averaged-envelope estimate, and the uniform singular-limit gate were not established in this round. In particular, PRDS of individually valid Gaussian null p-values in the displayed finite families does not justify replacing independence by PRDS in a calibration theorem that assumes independence and only aggregate conditional validity. These family bounds are search obstructions, not a proof of the dimension-uniform upper bound or an approval of the draft ideas.

Object search: 0 candidate(s) in 5 round(s).
