---
type: search_round
title: 'Round 3: analytic envelopes at fixed parameters and uncovered uniform scope'
target_asset: spherical_isotropic_population_bh_bound
mode: refute
round: 3
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
  - cand_spherical_isotropic_population_bh_bound_r3_s1_vanishing_pareto_tail
  - cand_spherical_isotropic_population_bh_bound_r3_s2_d4_subthreshold_uniform
  - cand_spherical_isotropic_population_bh_bound_r3_s2_d5_subthreshold_uniform
  - cand_spherical_isotropic_population_bh_bound_r3_s2_d6_subthreshold_uniform
  - cand_spherical_isotropic_population_bh_bound_r3_s3_log_accumulation_zero
  - cand_spherical_isotropic_population_bh_bound_r3_s4_cantor_weak_means
  - cand_spherical_isotropic_population_bh_bound_r3_s6_sparse_boundary_mass
  - cand_spherical_isotropic_population_bh_bound_r3_s7_d4_weak_continuum
  - cand_spherical_isotropic_population_bh_bound_r3_s7_d5_single_weak_mean
  - cand_spherical_isotropic_population_bh_bound_r3_s7_d6_two_weak_means
  - >-
    cand_spherical_isotropic_population_bh_bound_r3_s8_infinite_moment_accumulation
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-05T00:14:41.408Z'
extension_version: 0.0.4
---

## Obstructions

- **A null-only envelope excludes every Borel mean law at fixed $d=4,u=104$ when $\pi_0\geq1/2$.** In `cand_spherical_isotropic_population_bh_bound_r3_s6_sparse_boundary_mass`, put $S(r)=\sup_{x\geq u}H_r(x)/Q(x)$. The contact identity gives $\operatorname{FDP}_{\rm pop}(r)\leq\min\{1,q\pi_0S(r)\}$, with FDP zero for $r\leq u$. The spherical tail and lower Mills bound yield $S(r)\leq K(1+u^{-2})r^{-1/2}u^{-3/2}e^{r^2/2}$, where $K=8(3/(2e))^{3/2}/(3\sqrt\pi)$. Integrating against the exact $\chi_4$ density only up to $b=\sqrt{u^2+10\log u}$ gives an integral coefficient below $7.26$ multiplying $q\pi_0$; the remaining radial probability divided by $q$ is below $3/u^2$. Thus $\operatorname{FDR}_{\rm pop}<7.3q\pi_0$, whereas the proposed coefficient at these parameters exceeds $9$. The argument uses no property of the alternative law; its extension from the displayed sparse two-atom object to this fixed-parameter family is therefore justified, including continuous, singular, and unbounded laws. This does not extend the bound to other dimensions, other $u$, or smaller null proportions. The proof-step approach is saved as the draft idea [Integrate a null-only radial envelope before tracking contact branches](../ideas/idea_3afb7bc15f1e.md).

- **A globally admissible cutoff excludes a restricted subthreshold-mean family in dimensions $4,5,6$.** Fix $u=104$, $q=2Q(u)$, and $W=\tfrac12\delta_0+\tfrac12\nu$, where $\nu$ is supported on $[u/2,u]$ and $\int\mu\,\nu(d\mu)\geq3u/4$. The three `r3_s2` candidates use the uniform law, but their argument uses only these support and mean conditions. With $(d,k)=(4,6),(5,7),(6,8)$ and $x_k=Q^{-1}(Q(u)/k)<u+1$, the spherical coordinate density bound gives $F_r(x_k)\geq\tfrac14-(c_d/2)(\tfrac14+u^{-1})>1/k$ for every $r\geq u$, where $(c_4,c_5,c_6)=(2/\pi,3/4,8/(3\pi))$. Hence the smallest finite contact obeys $x_r\leq x_k$ there; for $r<u$ the null FDP is zero. Using $\mathbb E H_R(u)=Q(u)$ gives $\operatorname{FDR}_{\rm pop}\leq kq\pi_0$. Each respective proposed coefficient strictly exceeds $k$. This is a family exclusion at the stated parameters, not a bound for arbitrary subthreshold alternatives or arbitrary dimensions.

- **A bounded weak-mean support can exclude all contacts on an initial radial interval.** At $u=104$, every law supported in $[0,1/u]$ satisfies $F_r(x)\leq2H_r(x-1/u)$. The support-edge tail inequality and Mills bounds in the three `r3_s7` candidates therefore apply independently of the internal distribution of its means. For $(d,K)=(4,4),(5,4),(6,8)$, set $r_*^2=u^2+2(d-1)\log u-2\log K$. Their explicit envelopes give $F_r(x)Q(u)/Q(x)<1$ for every $x\geq u$ and $r\leq r_*$. The exact $\chi_d$ tails then give $\operatorname{FDR}_{\rm pop}\leq\mathbb P(R>r_*)<3q$. For $\pi_0\geq1/2$ the proposed right side exceeds $3q$ in all three dimensions. Thus this support-restricted family fails NOT, including atomic and continuous laws; it is not an exclusion of general weak/strong mixtures. In dimension four, the distinct envelope in `r3_s3_log_accumulation_zero` even gives $\operatorname{FDR}_{\rm pop}<2q$ for the same support restriction, explaining why logarithmic accumulation at zero does not itself create a violation.

- **A sufficiently small unrestricted tail does not defeat the weak-mean exclusion at the recorded fixed parameters.** The `r3_s8_infinite_moment_accumulation` calculation applies at $d=5,u=104,\pi_0=1/2$ whenever $W([0,1/u])\geq1-u^{-8}$: the remaining mass contributes at most $u^{-8}$ to $F_r(x)$, irrespective of its locations or moments. Its envelope is below one on $u\leq x\leq r\leq r_0=\sqrt{u^2+8\log u-4}$; any contact below that radial boundary must exceed the null support and gives zero null FDP. The exact $\chi_5$ tail yields $\operatorname{FDR}_{\rm pop}<3q$, whereas the proposed right side exceeds $4q$. Similarly, the `r3_s1_vanishing_pareto_tail` envelope applies at $d=4,u=104,\pi_0=1/2$ to laws with $W([0,u^{-3}])\geq1-u^{-6}$ and gives $\operatorname{FDR}_{\rm pop}<3q/4$. Its displayed Pareto object additionally has finite contacts at every positive radius; that existence fact uses the Pareto tail, while the FDR exclusion does not. These bounds impose explicit small-tail mass restrictions and do not cover arbitrary unbounded mixtures.

## Limitations

- All eleven recorded round-3 candidates pass their listed hypotheses and fail NOT. Their absence of a survivor supplies no proof or verification verdict for the draft theorem. The analytic bounds above justify only the stated families and parameter ranges.
- Every recorded round-3 object uses $u=104$ and dimension $4$, $5$, or $6$. The null-envelope family covers all Borel laws only at $d=4,u=104,\pi_0\geq1/2$; outside it, only explicit support, mean, or tail-mass restrictions were excluded. General $d\geq7$, the full range of null proportions, arbitrary alternative mass between or outside these regimes, and all $u>104$ remain unexcluded by this round. The earlier board's three fixed strong-mean parameter pairs remain separate restrictions.
- The fixed-parameter bounds do not prove the uniform $O(q\log u)=o(qu)$ conclusion, including cases where $d$ and $W$ vary with $q$. The absence of moment assumptions is tested by specific infinite-mean objects and restricted contamination families, not by a uniform argument for every unbounded mean law.
- A remote finite contact need not contribute false discoveries: the Pareto object has finite contacts at every radius but zero null FDP throughout its excluded radial interval. Conversely, proving absence of contacts on an initial radial interval does not control arbitrary first-contact births, switches, or degeneracies at larger radii; the displayed tail estimates merely bound their total possible contribution for these models.
- The recorded decimal envelope values and approximate radii in the sparse-mass and infinite-moment candidates are reproducibility diagnostics. Their failed NOT checks rest on the displayed exact inequalities and radial identities. The stage report also mentions other extreme-scale probes, but the supplied pack gives no reconstructible parameter grids, numerical error bounds, or outputs for those additional probes. No new exclusion is inferred from them or from a direction being listed as tried without a candidate record.
- A general argument must still justify the required global first-contact control (or a valid replacement), positive variation as a measure where used, conditional radial transport, and general cutoff bounds. An almost-everywhere derivative estimate alone does not establish these points. The draft approach recorded from the null envelope identifies a possible route and retains its unresolved dimension, level, and null-mass extensions.
