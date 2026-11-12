---
type: search_round
title: >-
  Round four spherical population BH exclusions by radial envelopes and
  admissible cutoffs
target_asset: spherical_isotropic_population_bh_bound
mode: refute
round: 4
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
  - cand_spherical_isotropic_population_bh_bound_r4_s1_vanishing_null_at_cutoff
  - cand_spherical_isotropic_population_bh_bound_r4_s2_d5_subthreshold_atom
  - cand_spherical_isotropic_population_bh_bound_r4_s2_d6_subthreshold_atom
  - cand_spherical_isotropic_population_bh_bound_r4_s2_d7_subthreshold_atom
  - cand_spherical_isotropic_population_bh_bound_r4_s3_tiny_null_edge_atom
  - cand_spherical_isotropic_population_bh_bound_r4_s4_sparse_null_strong_mean
  - >-
    cand_spherical_isotropic_population_bh_bound_r4_s6_pure_null_d5_variable_level
  - cand_spherical_isotropic_population_bh_bound_r4_s7_d4_half_u_small_null
  - cand_spherical_isotropic_population_bh_bound_r4_s8_all_null_large_dimension
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-05T00:31:22.511Z'
extension_version: 0.0.4
---

## Obstructions

- **The entire all-null family has one radial onset of contact and FDR at most the nominal level.** For every integer $d\geq4$, every $u\geq104$, $q=2Q(u)$, and $W=\delta_0$, one has $F_r(x)=2H_r(x)$. For each $x>u$ there is a unique $b(x)>x$ with $H_{b(x)}(x)=Q(x)/q$. It is continuous, diverges as $x\downarrow u$ and as $x\to\infty$, and therefore attains a finite minimum $b_*=b(x_*)$. At $x=u$ there is no finite-radius contact; at $x>u$ admissibility is exactly $r\geq b(x)$. Thus a finite contact exists exactly for $R\geq b_*$, and the all-null FDP is its indicator. The Gaussian marginal identity and radial monotonicity give $Q(x_*)=\mathbb E H_R(x_*)\geq\mathbb P(R\geq b_*)Q(x_*)/q$, so $\operatorname{FDR}_{\rm pop}\leq q$, below the proposed right side. This analytic argument in `cand_spherical_isotropic_population_bh_bound_r4_s8_all_null_large_dimension` is independent of its displayed $d=105^4,u=105$; it excludes every all-null dimension, including $d$ depending on $q$. It also subsumes the pure-null candidate `r4_s6_pure_null_d5_variable_level`, whose separate $\chi_5$-tail calculation yields $\operatorname{FDR}_{\rm pop}<3q$ for all $u\geq105$. The global-onset proof step is saved as the draft approach `idea_5a1b54ccbfa6`; it gives no mixed-law conclusion.

- **A null-only radial envelope excludes every Borel mean law at $u=104$, $d\in\{5,6,7\}$, and $\pi_0\geq1/2$.** The three `r4_s2` candidates display a subthreshold atom, but their NOT calculations use no property of the alternatives. Set $a=(d-1)/2$, $b^2=u^2+2(d-1)\log u$, and $B_a=a^{a-1}e^{-a}/\Gamma(a)$. The spherical support-edge inequality and lower Mills bound imply, for all $x\geq u$,
$$
\frac{H_r(x)}{Q(x)}\leq A_d(1+u^{-2})r^{-a}u^{1-a}e^{r^2/2},\qquad A_dC_d=B_a,
$$
where $C_dr^{d-1}e^{-r^2/2}$ is the $\chi_d$ density; the left side is zero for $x\geq r$. The contact identity, FDP at most one, and zero null FDP for $r\leq u$ give
$$
\frac{\operatorname{FDR}_{\rm pop}}{q\pi_0}\leq B_a(1+u^{-2})u^{1-a}\int_u^b r^a\,dr+\frac{\mathbb P(R>b)}{q\pi_0}.
$$
For $\pi_0=1/2$, exact rational estimates and the incomplete-gamma tail bound in the candidates give respective strict upper bounds $3259/500$, $1489/200$, and $3081/400$, all below $193/25$. The proposed coefficient exceeds $193/25$, using $M_d>13/50$ and $\log312>11/2$. Increasing $\pi_0$ leaves the integral term unchanged and only reduces the normalized radial tail, so the same bounds hold for every $\pi_0\geq1/2$. This excludes arbitrary atomic, continuous, singular, and unbounded alternative laws at these stated parameters, not arbitrary dimensions, levels, or smaller null proportions. It extends the null-envelope route already recorded as `idea_3afb7bc15f1e`.

- **Enough alternative mass at or above a deterministic cutoff prevents sparse-null counterexamples in the specified families.** In dimension seven, for every $u\geq104$, $W=p\delta_0+(1-p)\nu$, $0<p\leq1/3$, and $\nu([u,\infty))=1$, let $Q(x_4)=Q(u)/4$. Then $u<x_4<u+1$ and, for $r\geq u$, the coordinate density bound $f_7\leq15/16$ gives $H_r(x_4-\mu)>3/8$ at every alternative mean. Hence $F_r(x_4)>1/4$, the actual first contact is at most $x_4$, and $\operatorname{FDR}_{\rm pop}\leq4qp$. The proposed coefficient exceeds six. This extends `r4_s1_vanishing_null_at_cutoff` from $p=e^{-u^2},\nu=\delta_u$ to the stated family by the same lower bound. If $0<p<1/4$ and instead $\nu([u+1,\infty))=1$, the cutoff $a=Q^{-1}((1-p)Q(u)/2)<u+1$ is admissible at every radius, since every alternative contributes at least one half. It yields the sharper $\operatorname{FDR}_{\rm pop}\leq2qp/(1-p)<(8/3)qp$, covering `r4_s3_tiny_null_edge_atom`. The same half-mass argument applies at $d=8,u=104,p=1/1024$ to every $\nu$ supported on $[2u,\infty)$ and gives $\operatorname{FDR}_{\rm pop}\leq(2048/1023)qp<3qp$, below the proposed coefficient there; `r4_s4_sparse_null_strong_mean` is its atomic instance. These support and mass restrictions are essential to the displayed admissible-cutoff arguments; they do not exclude arbitrary sparse-null mixtures.

- **A dimension-four cap lower bound excludes a small-null family with alternatives at least half the initial cutoff.** For every $u\geq104$, $d=4$, $W=p\delta_0+(1-p)\nu$ with $0<p\leq1/4$ and $\nu([u/2,\infty))=1$, set $Q(x_8)=Q(u)/8$. One has $u<x_8<u+1$. The exact cap value $H_u(u/2)=1/3-\sqrt3/(4\pi)>3/16$ and density bound $2/\pi$ imply $H_u(u/2+1)>3/16-2/(\pi u)>1/6$. Therefore $F_r(x_8)>1/8$ for every $r\geq u$, since at least three quarters of the population has mean at least $u/2$. Thus $x_r\leq x_8$ there, while the null FDP is zero for $r<u$. Averaging $\operatorname{FDP}_{\rm pop}(r)\leq16pH_r(u)$ gives $\operatorname{FDR}_{\rm pop}\leq8qp$. The proposed coefficient is greater than eight because $M_4=1/\pi$ and $\log(3u)>5$. The calculation of `r4_s7_d4_half_u_small_null` depends only on these mass, support, dimension, and level restrictions, so its displayed $p=1/4,\nu=\delta_{u/2},u=104$ is one member of this excluded family.

## Limitations

- All nine recorded round-four candidates pass their listed hypotheses and fail NOT. The exclusions above are analytic arguments for their explicitly stated families; a list of failed candidates and the absence of a survivor do not prove the draft theorem or give it a verification verdict.
- The all-null result covers every allowed dimension and level, but positive alternative mass destroys the direct identity between FDP and contact existence and need not preserve radial monotonicity of $F_r(x)$. No mixed-law generalization of that global-onset argument was established. The dimension-five pure-null tail calculation is a separate, weaker check within the all-null family.
- The unrestricted-law null-envelope argument is confined here to $u=104$, $d\in\{5,6,7\}$, and $\pi_0\geq1/2$, in addition to the earlier board's dimension-four result. The remaining small-null cases, mixtures with substantial mass below the admissible-cutoff support boundaries, mixed laws at general $d\geq8$, and general $u>104$ outside the displayed support-restricted families remain unexcluded by this round. There is no uniform mixed-law bound as $d$, $W$, and $q$ vary together.
- The new concrete objects are atomic. Arbitrary continuous, singular, or unbounded alternatives are covered only where a displayed family argument genuinely does not use their internal distribution: the fixed-parameter null envelope and the stated lower-support families. This supplies no exclusion of every unbounded mean law or every weak/strong mixture.
- Listed directions without a candidate record, including further growth-dimension or sparse-mean probes mentioned in the search report, supply no independently reconstructible exclusion. No numerical scan, absence of a numerical survivor, or finite parameter grid is treated as a proof or an exhaustive search.
- The general target still requires global first-contact control or a valid replacement for arbitrary mixtures, including births, switches, degeneracies, and positive variation as a measure where used, together with conditional radial transport and general cutoff estimates. The cutoff and envelope arguments avoid tracking these events only for their stated families. An almost-everywhere contact derivative estimate alone would not close the remaining gap.
