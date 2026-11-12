---
type: search_round
title: 'Round 8: deterministic cutoffs and strong-mean saturation'
target_asset: spherical_isotropic_population_bh_bound
mode: refute
round: 8
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
  - cand_spherical_isotropic_population_bh_bound_r8_s2_d4_strong_half_mass
  - >-
    cand_spherical_isotropic_population_bh_bound_r8_s3_strong_pareto_infinite_mean
  - >-
    cand_spherical_isotropic_population_bh_bound_r8_s4_dyadic_strong_infinite_mean
  - >-
    cand_spherical_isotropic_population_bh_bound_r8_s5_growing_dimension_dominant_mean
  - >-
    cand_spherical_isotropic_population_bh_bound_r8_s6_exact_cancellation_plateau
  - cand_spherical_isotropic_population_bh_bound_r8_s7_d4_strong_atom_two_u
  - cand_spherical_isotropic_population_bh_bound_r8_s8_strong_atom_twou
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-05T02:04:20.575Z'
extension_version: 0.0.4
---

## Obstructions

- **A deterministic admissible cutoff bounds the entire first-contact family.** If a finite \(a\geq u\) satisfies \(F_r(a)\geq2Q(a)/q\) at every \(r>0\), the actual smallest contact exists and obeys \(u\leq x_r\leq a\), regardless of earlier contacts, switches, or equality plateaus. Monotonicity in the cutoff gives

  $$
  \operatorname{FDP}_{\rm pop}(r)
  \leq q\pi_0\frac{H_r(u)}{Q(a)},\qquad
  \operatorname{FDR}_{\rm pop}
  \leq q\pi_0\frac{Q(u)}{Q(a)}.
  $$

  Here \(\mathbb E H_R(u)=Q(u)\), since an independent uniform directional projection of \(Z\sim N(0,I_d)\) is standard normal. A sufficient family-level premise is

  $$
  m=W([a,\infty))>0,\qquad \frac{2Q(a)}q\leq\frac m2.
  $$

  Symmetry gives \(H_r(a-\mu)\geq1/2\) for every \(\mu\geq a\), hence \(F_r(a)\geq m/2\) and also \(F_r(x_r)\geq m/2\). The latter lower bound yields \(\operatorname{FDR}_{\rm pop}\leq2q\pi_0/m\). This uses no bounded-support or moment assumption. For \(d=4,u=104,W=\frac12\delta_0+\frac12\delta_{2u}\), take \(Q(a)=q/8=Q(u)/4\). The Gaussian-tail translation inequality

  $$
  Q(u+t)\leq e^{-ut-t^2/2}Q(u)\quad(t>0)
  $$

  implies \(u<a<2u\), so \(m=1/2\) and the bound is \(4q\pi_0\). This is the same object in slots 2, 7, and 8, rather than three distinct exclusions. More generally, the same cutoff argument bounds every target population with at least one half of its mass at means at least \(2u\) by \(4q\pi_0\); comparison with the target coefficient must still use the actual dimension and level.

- **Saturated strong mass below a radial cutoff excludes the tested heavy tails and dominant-mean scaling.** If \(a\geq u\), \(L>0\), \(m=W([a+L,\infty))>0\), and \(2Q(a)/q\leq m\), then for \(0<r\leq L\) the entire mass \(m\) rejects at \(a\). Therefore \(a\) is admissible, \(x_r\leq a\), and that same mass rejects at \(x_r\). The contact denominator is at least \(m\), so

  $$
  \operatorname{FDP}_{\rm pop}(r)\leq
  \frac{2\pi_0}{m}H_r(u)\quad(0<r\leq L),\qquad
  \operatorname{FDR}_{\rm pop}\leq
  \frac{q\pi_0}{m}+\mathbb P(R>L).
  $$

  These are family-level support and radial-tail conditions, not consequences of infinite first moment alone. They give all three recorded saturation exclusions:

  For the slot-3 Pareto law, \(d=4,u=104,\pi_0=m=1/2\), all positive means are at least \(3u\). Let \(Q(a)=q/4\) and \(L=2u-u^{-1}\). Tail translation gives \(u<a<u+u^{-1}\), so \(a+L<3u\). For \(R\sim\chi_4\),

  $$
  \mathbb P(R>L)=(1+L^2/2)e^{-L^2/2}
  <2e^2u^2e^{-2u^2}<q,
  $$

  where the last comparison uses \(q>e^{-u^2/2}/(2u)\) at \(u=104\). Thus \(\operatorname{FDR}_{\rm pop}<2q=4q\pi_0\). The normalized density proportional to \(\mu^{-3/2}\) on \([3u,\infty)\) indeed has infinite first moment, but its entire nonnull mass satisfies the displayed saturation premise.

  For the slot-4 dyadic law, again \(d=4,u=104,\pi_0=m=1/2\), all positive means are at least \(4u\). Take \(a=u+u^{-1}\) and \(L=2u\). Then \(a+L<4u\) and \(2Q(a)/q<e^{-1}<1/2\). The exact tail and lower Mills bound give

  $$
  \frac{\mathbb P(R>2u)}{Q(u)}
  <18u^3e^{-3u^2/2}<\frac{32}{u^3}<1.
  $$

  The second strict inequality follows from \(e^{3u^2/2}>(3u^2/2)^3/6=9u^6/16\). Hence the FDR is less than \(q+Q(u)=3q\pi_0\), despite unbounded support and infinite first moment.

  For the slot-5 family, \(u=n\geq104\) is an integer, \(d=n^4\), and \(W=\frac12\delta_0+\frac12\delta_d\). Set \(a=2u\), \(L=d-2u\), and \(m=1/2\). Then \(a+L=d\) and \(2Q(2u)/q\leq e^{-3u^2/2}<1/2\). Using \(L\geq d/2\) and \(\mathbb E e^{R^2/4}=2^{d/2}\),

  $$
  \mathbb P(R>L)
  \leq\exp\{(d/2)\log2-L^2/4\}
  \leq e^{-d^2/32}
  =e^{-u^8/32}\leq e^{-2u^2}.
  $$

  Thus \(\operatorname{FDR}_{\rm pop}\leq2q\pi_0+e^{-2u^2}\), strictly below the target right side because \(M_d>0\). This excludes that simultaneous growing-dimension and growing-mean family without a general theorem about moving contacts.

- **Exact cancellation of cap terms can create an admissible plateau without producing a counterexample.** For the slot-6 family \(W=\frac13\delta_0+\frac23\delta_{2a}\), with \(Q(a)=q/3\), symmetry gives the exact identity

  $$
  F_r(a)=\frac23H_r(a)+\frac23\{H_r(-a)+H_r(3a)\}
  =\frac23+\frac23H_r(3a)\geq\frac23=\frac{2Q(a)}q.
  $$

  Thus \(x_r\leq a\), even though the equality contact \(a\) for \(r\leq3a\) need not be the first contact. Since \(x_r-2a<0\), \(F_r(x_r)\geq1/3\) and \(\operatorname{FDR}_{\rm pop}\leq3q\pi_0\), as recorded. In fact the first obstruction's common-cutoff bound also gives the stronger \((3/2)q\pi_0\) here; the recorded weaker bound already suffices. At all the fixed-\(d=4,u=104\) objects above, \(M_4=1/\pi\), \(\pi<4\), and \(\log312>5\) give the target coefficient \(2+4M_4(1+u^{-2})\log(3u)>7\). Consequently each displayed bound of \(3q\pi_0\) or \(4q\pi_0\) is strictly below that target, before adding \(e^{-2u^2}\).

The deterministic-cutoff and localized-saturation steps were also saved through native record_idea as draft approach idea_37962b3f4b08, related to the target. This is a restricted-family proof step, not a verification verdict for the target.

## Limitations

- All seven round-eight candidate files pass their recorded hypotheses and fail NOT. There are five distinct objects: slots 2, 7, and 8 repeat exactly the same half-null atom at \(2u\). Repeated files do not provide independent search coverage. The five listed direction labels likewise do not establish exhaustive coverage.
- Candidate definitions and check bodies were obtained only through native show for the IDs named by the context pack, because the one-line summaries omitted the cutoff, support, and radial-tail premises needed to state family-level obstructions. The two named definitions were also read through native show to reconstruct the exact first-contact convention and rejection masses. The target's Proof, plans, unrelated candidates, and research folders were not read.
- The deterministic-cutoff lemmas hold in any target dimension and at any target level when their explicit premises hold, but the recorded fixed-dimensional numerical coefficient comparisons use \(d=4,u=104\). The growing-dimensional exclusion concerns the specific scaling \(d=u^4\) with an atom at mean \(d\). Neither result supplies the requisite cutoff or tail premise for arbitrary joint choices of \(W,d,q\).
- General mixtures with appreciable moderate means, small strong-signal mass, or distributions spread across competing contact branches remain uncovered unless they satisfy one of the explicitly stated premises or an earlier obstruction. Infinite mean, unbounded support, a strong atom, growing dimension, or an equality plateau by itself does not decide the unrestricted target.
- These arguments bypass global moving-contact analysis within their stated families. They do not establish the general bound across births, switches, and degeneracies of the smallest contact, a positive-variation measure estimate, or conditional radial transport for arbitrary \(W\). The earlier support-restricted monotone-transport exclusion remains restricted to \(W([0,u])=1\); it cannot be extended silently to the strong-mean objects here.
- No numerical grid or absence of a survivor is used as a proof of the population target. This round yields no surviving counterexample and no target proof-verification verdict; it also yields no finite Gaussian-vector approximation and no resolution of either original unrestricted Gaussian BH conjecture.
