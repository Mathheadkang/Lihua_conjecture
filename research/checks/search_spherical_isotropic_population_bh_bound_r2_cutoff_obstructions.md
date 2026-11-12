---
type: search_round
title: Round 2 restricted strong-mean obstruction and unresolved contact families
target_asset: spherical_isotropic_population_bh_bound
mode: refute
round: 2
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
  - known_counterexamples
  - extremal
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - cand_spherical_isotropic_population_bh_bound_r2_s1_near_double_contact
  - cand_spherical_isotropic_population_bh_bound_r2_s6_support_edge_contact
  - cand_spherical_isotropic_population_bh_bound_r2_s7_d5_two_strong_means
  - cand_spherical_isotropic_population_bh_bound_r2_s7_d7_two_strong_means
  - cand_spherical_isotropic_population_bh_bound_r2_s7_d9_two_strong_means
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-04T23:58:06.692Z'
extension_version: 0.0.4
---

## Obstructions

- Strong alternatives with a fixed radial cutoff cannot supply a counterexample in the following restricted families: fix $u=104$, $q=2Q(u)$, and $(d,\pi_0)\in\{(5,1/4),(7,1/2),(9,3/4)\}$, and let the alternative part of any Borel law $W$ be supported on $[4u,\infty)$. For $0<r\leq2u$ and $u\leq x\leq2u$, every alternative rejects, so $F_r(x)\geq1-\pi_0$. The Gaussian tail ratio $Q(2u)/Q(u)<1/4\leq1-\pi_0$ makes $2u$ admissible, bounds the first contact by $2u$, and gives $\operatorname{FDP}_{\rm pop}(r)\leq2\pi_0H_r(u)/(1-\pi_0)$. Using $\mathbb EH_R(u)=Q(u)$ and $\operatorname{FDP}_{\rm pop}\leq1$ on the remaining radii yields
  $$
  \operatorname{FDR}_{\rm pop}\leq\frac{q\pi_0}{1-\pi_0}+\mathbb P(R>2u)
  \leq\frac{q\pi_0}{1-\pi_0}+2^{d/2}e^{-u^2}.
  $$
  The explicit tail comparisons in `cand_spherical_isotropic_population_bh_bound_r2_s7_d5_two_strong_means`, `cand_spherical_isotropic_population_bh_bound_r2_s7_d7_two_strong_means`, and `cand_spherical_isotropic_population_bh_bound_r2_s7_d9_two_strong_means` give respectively $\operatorname{FDR}_{\rm pop}<(7/3)q\pi_0$, $3q\pi_0$, and $5q\pi_0$, each below the proposed bound. The argument depends on the alternative support lower bound rather than on having exactly two alternative atoms; it excludes these support-restricted families at the three fixed parameter pairs. This possible proof step is saved as the draft approach `idea_2fe4ecca259b`.

## Limitations

- The two boundary candidate failures are object-specific, so they do not establish exclusions for all degenerate-contact families. For `cand_spherical_isotropic_population_bh_bound_r2_s1_near_double_contact`, the explicit radial exclusion calculation requires $R>104.13$ for positive FDP and bounds its FDR by $0.943q$. For `cand_spherical_isotropic_population_bh_bound_r2_s6_support_edge_contact`, an exact first contact at the null support edge coexists with the global first-contact upper bound $x_r\leq Q^{-1}(Q(u)/4)$, giving FDR at most $4q\pi_0$. Both fail NOT, while retaining all the recorded hypotheses; neither result excludes every near-double or support-edge construction.
- The near-double candidate's double-precision local tangency optimizations are exploratory diagnostics. Their small residuals do not certify all first contacts or simultaneous births. The failure of NOT instead rests on its separate radial upper-bound argument. The support-edge candidate's displayed decimal quantiles likewise serve only reproducibility; its failure argument uses exact inequalities.
- The earlier search report mentions high-dimensional and sparse-mean numerical exploration, but the supplied pack contains no test specifications, parameter grids, error control, or reconstructible outputs for those probes. No numerical family exclusion is inferred from that report. Directions listed as tried without a candidate record likewise supply no additional exclusion.
- Arbitrary alternative mass below $4u$, general null proportions and dimensions, continuous or unbounded mean laws outside the restricted strong-mean families, all $u\geq104$, and joint dependence of $d$ and $W$ on $q$ remain uncovered. In particular, the restricted-family obstruction above does not establish the theorem's uniform asymptotic claim.
- Global first-contact births and switches, degenerate contacts beyond the two explicit objects, positive variation as a measure, conditional radial transport, and the required general cutoff bounds remain unresolved. An almost-everywhere derivative estimate would not fill these gaps. The five recorded candidates failed NOT; their failure and the absence of a survivor supply no proof or verification verdict for the draft target.
