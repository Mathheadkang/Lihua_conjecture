---
type: search_round
title: 'Round five: conditional FDP and bounded-cutoff obstructions'
target_asset: spherical_isotropic_population_bh_bound
mode: refute
round: 5
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
  - cand_spherical_isotropic_population_bh_bound_r5_s2_d8_subthreshold_atom
  - cand_spherical_isotropic_population_bh_bound_r5_s3_weak_positive_sparse_null
  - cand_spherical_isotropic_population_bh_bound_r5_s4_ultrarare_null_weak_mean
  - cand_spherical_isotropic_population_bh_bound_r5_s7_d4_third_null_half_mean
  - >-
    cand_spherical_isotropic_population_bh_bound_r5_s8_sparse_null_seven_twentieths
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-05T00:56:37.473Z'
extension_version: 0.0.4
---

## Obstructions

- **Conditional spherical unimodality excludes every law with sufficiently tiny null mass, in every allowed dimension.** For any $d\geq4$ and $r>0$, the density $f_r$ of the spherical coordinate $rv_1$ is even and nonincreasing in $|t|$. For $x,\mu\geq0$, therefore,
  $$
  \frac{d}{d\mu}\{H_r(x-\mu)+H_r(x+\mu)\}
  =f_r(x-\mu)-f_r(x+\mu)\geq0.
  $$
  Integrating the resulting inequality against any Borel absolute-mean law gives $F_r(x)\geq2H_r(x)$. At a finite contact the exact mass ratio then yields $\operatorname{FDP}_{\rm pop}(r)=2\pi_0H_r(x_r)/F_r(x_r)\leq\pi_0$; the no-contact and zero-radius conventions satisfy the same bound. Thus $\operatorname{FDR}_{\rm pop}\leq\pi_0$ for every allowed law and dimension. Every law with $\pi_0\leq e^{-2u^2}$ consequently satisfies the proposed target by its additive remainder alone. The growing-dimension, weak-mean object `cand_spherical_isotropic_population_bh_bound_r5_s4_ultrarare_null_weak_mean` is one such instance, with $\pi_0=e^{-3u^2}$. This genuine conditional proof step is recorded as the draft approach `idea_69abdb6ec943`; its bound has no $q$ factor and supplies no general target multiplier for larger $\pi_0$.

- **The null-only radial envelope excludes arbitrary alternative laws at $d=8,u=104,\pi_0\geq1/2$.** In `cand_spherical_isotropic_population_bh_bound_r5_s2_d8_subthreshold_atom`, put $a=7/2$, $b^2=u^2+14\log u$, and $B=a^{a-1}e^{-a}/\Gamma(a)$. The spherical support-edge bound and the lower Mills inequality give, for every $x\geq u$,
  $$
  \frac{H_r(x)}{Q(x)}\leq A(1+u^{-2})u^{1-a}r^{-a}e^{r^2/2},
  \qquad AC=B,
  $$
  where $Cr^7e^{-r^2/2}$ is the $\chi_8$ density. Null FDP vanishes for $r\leq u$ and is at most one, so
  $$
  \frac{\operatorname{FDR}_{\rm pop}}{q\pi_0}
  \leq B(1+u^{-2})u^{1-a}\int_u^b r^a\,dr
       +\frac{\mathbb P(R>b)}{q\pi_0}.
  $$
  The candidate's rational certificates bound the integral by $36/5$ and, at $\pi_0=1/2$, the normalized exact $\chi_8$ tail by $1/16$. Their sum is $581/80$. Meanwhile $M_8>13/50$ and $\log312>11/2$ make the proposed coefficient greater than $193/25>581/80$. Increasing $\pi_0$ only decreases the normalized tail. No feature of the alternative atom was used, so the exclusion genuinely covers every Borel alternative distribution at these dimension, level, and null-mass restrictions, including singular or unbounded laws. This extends the existing null-envelope approach `idea_3afb7bc15f1e`, without extending it to arbitrary dimensions or levels.

- **A uniformly admissible cutoff plus a logarithmic interval envelope excludes a sparse-null family with means at least one.** Fix $d=4,u=104$, $W=p\delta_0+(1-p)\nu$, $0<p\leq1/1024$, and $\nu([1,\infty))=1$. Let $Q(b)=Q(u)/2048$. The argument in `cand_spherical_isotropic_population_bh_bound_r5_s3_weak_positive_sparse_null` gives $b-u<1/13$ and $H_u(b-1)>49/99440$. Since $(1023/1024)(49/99440)>1/2048$, monotonicity in the mean and radial monotonicity at the positive threshold $b-1$ show that $b$ is admissible for every $r\geq u$. Thus the actual first cutoff lies in $[u,b]$ there. For any $x\in[u,b]$, monotonicity of $H_r$ gives
  $$
  \frac{H_r(x)}{Q(x)}\leq\frac{H_r(u)}{Q(u)}+
  \int_u^b\frac{H_r(t)\varphi(t)}{Q(t)^2}\,dt.
  $$
  Taking the common envelope's expectation, using Tonelli and $\mathbb E H_R(t)=Q(t)$, yields
  $$
  \operatorname{FDR}_{\rm pop}\leq qp\{1+\log2048\}<\frac{87}{10}qp,
  $$
  below the proposed coefficient, which exceeds nine. This extends the displayed $p=1/1024,\nu=\delta_1$ object to precisely the stated support-restricted family. The general cutoff-interval step is recorded as the draft approach `idea_cf9af13d9b02`; its uniform admissibility premise remains essential.

- **Dimension-four cap lower bounds exclude two additional lower-support families via the same deterministic cutoff.** For every $u\geq104$, set $q=2Q(u)$ and $Q(x_9)=Q(u)/9$, so $u<x_9<u+1$. For $W=p\delta_0+(1-p)\nu$, either of the following conditions makes $F_r(x_9)>1/9$ for all $r\geq u$: (i) $0<p\leq1/3$ and $\nu([u/2,\infty))=1$; (ii) $0<p\leq1/100$ and $\nu([7u/20,\infty))=1$. For (i), the exact cap value $H_u(u/2)>3/16$ and density bound $2/\pi$ give $H_u(u/2+1)>1/6$, leaving alternative mass at least $2/3$. For (ii), $(x_9-7u/20)/r<13/20+1/u<33/50$ and the rational trigonometric certificate in `cand_spherical_isotropic_population_bh_bound_r5_s8_sparse_null_seven_twentieths` give $H_1(33/50)>1239147/11000000$, whose product with $99/100$ exceeds $1/9$. Monotonicity in the mean extends both calculations from atoms to their stated supports. Hence the actual first contact is at most $x_9$, and $\mathbb E H_R(u)=Q(u)$ implies $\operatorname{FDR}_{\rm pop}\leq9qp$, strictly below the proposed bound because its dimension-four coefficient exceeds nine for every $u\geq104$. Condition (i) covers `cand_spherical_isotropic_population_bh_bound_r5_s7_d4_third_null_half_mean`; condition (ii) covers the seven-twentieths object. These are lower-support and mass restrictions, not arbitrary sparse-null mixtures.

## Limitations

- All five recorded round-five objects satisfy their listed hypotheses and fail NOT. Their analytic exclusions, including the explicitly justified family extensions above, do not prove or independently verify the full draft theorem. Exact rational arithmetic was used only to check displayed analytic certificates; no numerical contact scan, finite parameter grid, or absence of a survivor is treated as proof or exhaustiveness.
- The new dimension-eight unrestricted-law envelope applies only at $u=104$ and $\pi_0\geq1/2$. The unit-mean logarithmic-envelope family likewise fixes $d=4,u=104$. The cap exclusions cover every $u\geq104$ only in dimension four and under their explicit support and mass restrictions. They supply no uniform mixed-law bound as $d,W,q$ vary together.
- The conditional inequality $\operatorname{FDP}_{\rm pop}\leq\pi_0$ is uniform over all allowed laws and dimensions, but closes the proposed bound by itself only when $\pi_0\leq e^{-2u^2}$. Intermediate null proportions, arbitrary mixtures with substantial mass below the listed support boundaries, and other general levels and dimensions remain unexcluded by this round. Continuous, singular, and unbounded laws are covered only within the expressly stated family arguments.
- No candidate from the other announced directions supplies an independently reconstructible new exclusion in this pack. Extreme-dimensional scaling, broad weak/strong mixtures, and general simultaneous scaling of null mass and means remain unresolved outside the listed families; a direction label or an unrecorded probe is not evidence of exhaustive coverage.
- For unrestricted mixtures the general target still requires global first-contact control or a valid replacement, including births, switches, degeneracies, and positive variation as a measure where used, together with conditional radial transport and cutoff estimates. Uniform deterministic cutoff envelopes bypass contact-branch analysis only when their premises hold; the conditional unimodality inequality does not establish those premises. An almost-everywhere contact derivative estimate alone remains insufficient.
