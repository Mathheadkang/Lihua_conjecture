---
type: search_round
title: Round 9 localized cutoff and rare-contamination obstructions
target_asset: spherical_isotropic_population_bh_bound
mode: refute
round: 9
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
  - >-
    cand_spherical_isotropic_population_bh_bound_r9_s2_d4_one_percent_near_threshold
  - cand_spherical_isotropic_population_bh_bound_r9_s3_barely_above_u_atom
  - >-
    cand_spherical_isotropic_population_bh_bound_r9_s5_vanishing_moderate_contamination
  - cand_spherical_isotropic_population_bh_bound_r9_s7_near_boundary_mean
  - cand_spherical_isotropic_population_bh_bound_r9_s8_moderate_geometric_spread
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-05T02:15:03.583Z'
extension_version: 0.0.4
---

## Obstructions

- **A uniform rejection-mass floor on radii above the null boundary excludes a family without following moving contacts.** Let $a\geq u$ and $c>0$ satisfy $F_r(a)\geq c\geq Q(a)/Q(u)$ for every $r>u$. Then $a$ is admissible, the stipulated first contact obeys $u\leq x_r\leq a$, and monotonicity gives $F_r(x_r)\geq c$ and $H_r(x_r)\leq H_r(u)$. For $r\leq u$ every permitted cutoff has zero null rejection mass. Consequently, using $\mathbb E H_R(u)=Q(u)$,
  $$
  \operatorname{FDR}_{\rm pop}\leq \frac{q\pi_0}{c}.
  $$
  In dimension four, $h_r(t)=2\sqrt{1-t^2/r^2}/(\pi r)\leq1/r$ on $(-r,r)$. Thus for **any** $u\geq104$ and any mean law with $W([u,\infty))\geq1/2$, the choice $a=u+2/u$ gives, for every $r>u$,
  $$
  F_r(a)\geq\frac12\left(\frac12-\frac2{u^2}\right)
  =c:=\frac14-\frac1{u^2}>\frac15,
  \qquad \frac{Q(a)}{Q(u)}\leq e^{-2-2/u^2}<\frac15.
  $$
  The lower cap bound holds also when $a-\mu<0$, since then $H_r(a-\mu)\geq1/2$. Additional mean mass only helps. Therefore this family has $\operatorname{FDR}_{\rm pop}<5q\pi_0$ when $\pi_0>0$, and zero FDR when $\pi_0=0$. It includes the three distinct round-9 objects at $u=104$: slot 3's $W=\frac12\delta_0+\frac12\delta_{u+u^{-2}}$, slot 7's $W=\frac12\delta_0+\frac12\delta_{u+u^{-1}}$, and slot 8's unbounded law $W=\frac12\delta_0+\sum_{n\geq1}2^{-(n+1)}\delta_{u+n/u}$. Neither bounded support nor a finite mean was needed for this sufficient mass-floor premise. Here and below $M_4=1/\pi$, and $\pi<4$, $\log(3u)>5$ imply that the target coefficient exceeds $7$, so these bounds lie below its right side.

- **A localized upper rejection envelope improves the mass-floor bound when contamination is small but fixed.** More generally, suppose a common admissible cutoff ensures $F_r(x_r)\geq L>0$ for every $r>u$, and $F_r(x_r)\leq U\leq1$ on $u<r\leq c_0u$, where $c_0>1$. Define $b$ by $Q(b)/Q(u)=U$. The contact identity implies $x_r\geq b$ on this interval, so
  $$
  \operatorname{FDR}_{\rm pop}
  \leq q\pi_0\frac UL+\mathbb P(R>c_0u).
  $$
  These are explicit premises, not properties of arbitrary mixtures. Slot 2 supplies them for $d=4$, $u=104$, $\mu=u+u^{-1}$, and $W=(99/100)\delta_0+(1/100)\delta_\mu$. With $a=u+6/u$, for all $r>u$ one has
  $$
  H_r(a-\mu)\geq\frac12-\frac{10}{\pi u^2}>\frac{49}{100},
  \qquad F_r(a)>L:=\frac{49}{10000},
  \qquad \frac{Q(a)}{Q(u)}\leq e^{-6}<\frac1{400}<L.
  $$
  For $c_0=101/100$ and $u<r\leq c_0u$, the dimension-four cap bound gives
  $$
  2H_r(u)\leq\frac{4\sqrt{201}}{\pi\,10201}<\frac1{500},
  \qquad F_r(x_r)\leq\frac1{100}+\frac{99}{100}\,2H_r(u)<U:=\frac3{250}.
  $$
  The exact $\chi_4$ tail and the lower Mills bound give
  $$
  \frac{\mathbb P(R>c_0u)}q
  <3u^3 e^{-201u^2/20000}
  <4\cdot10^6e^{-100}<0.00288<\pi_0.
  $$
  The penultimate comparison follows from $e^{100}>100^6/6!$. Thus this object's FDR is less than $(120/49+1)q\pi_0=(169/49)q\pi_0$, below the target coefficient. This is an exclusion of the displayed object and of any family meeting the stated envelopes and tail premise, not of all fixed positive contamination masses.

- **Sufficiently rare contamination forces every positive-FDP contact into a rare radial event, independently of the alternative means.** In dimension four with $u\geq104$, let $\varepsilon=1-\pi_0\leq Q(2u)/q$. For any alternative law, $F_r(x)\leq2H_r(x)+\varepsilon$. A positive-FDP finite contact with $r\leq2u$ has $u\leq x_r<r\leq2u$, and hence
  $$
  \frac{H_r(x_r)}{Q(x_r)}\geq\frac1{2q}.
  $$
  For $u\leq x<r$, put $h=r-x$. The cap density, the lower Mills bound, and $e^{-rh+h^2/2}\leq e^{-rh/2}$ imply
  $$
  H_r(x)\leq\frac{4\sqrt2}{3\pi}(h/r)^{3/2},
  \qquad
  \frac{H_r(x)}{Q(x)}
  \leq C(1+u^{-2})\frac{e^{r^2/2}}{r^2},
  \qquad C=\frac{8\sqrt3}{\sqrt\pi}e^{-3/2}<2.
  $$
  The second bound follows by maximizing $h^{3/2}e^{-rh/2}$, whose maximum is $(3/r)^{3/2}e^{-3/2}$, and using $x+x^{-1}\leq r(1+u^{-2})$. Therefore every such contact obeys $g(r):=r^2e^{-r^2/2}<4(1+u^{-2})q$. The function $g$ decreases on $[u,\infty)$, and the upper Mills bound gives $g(u)/q\geq(\sqrt{2\pi}/2)u^3>4(1+u^{-2})$. There is a unique $b>u$ with $g(b)=4(1+u^{-2})q$. The exact radial tail then yields
  $$
  \mathbb P(R\geq b)
  =2(1+u^{-2})(1+2/b^2)q
  \leq2(1+u^{-2})(1+2u^{-2})q<\frac52q.
  $$
  Separately,
  $$
  \frac{\mathbb P(R>2u)}{Q(u)}
  <18u^3e^{-3u^2/2}<\frac{32}{u^3}<1.
  $$
  The latter estimate uses $\mathbb P(R>2u)=(1+2u^2)e^{-2u^2}$, Mills' lower bound, and $e^{3u^2/2}>9u^6/16$. Since FDP is at most one, $\operatorname{FDR}_{\rm pop}<3q$. The mass premise implies $\pi_0>1/2$, so this is below $7q\pi_0$ and hence below the target. Slot 5's family $\varepsilon=e^{-u^4}$ and alternative mean $u+u^{-1}$ meets the premise for every real $u\geq104$, since
  $$
  \frac{Q(2u)}q\geq\frac15e^{-3u^2/2}>e^{-u^4}.
  $$
  This restricted positive-FDP event step was saved through native `record_idea` as draft approach `idea_03335ac9f185`; it gives no target verification verdict.

## Limitations

- The five named round-9 candidate records pass their recorded hypotheses and fail NOT. They are five distinct objects, although slots 3 and 7 are nearby variants handled by the same mass-floor argument. The pack supplies no candidate records for slots 1, 4, or 6, so no additional object coverage is inferred from their absence or from direction labels.
- Candidate bodies were obtained only through native `show` for the five IDs named in the context pack because the one-line failures omit the cutoff, envelope, and contamination premises. The two named definitions were read the same way to recover the exact contact convention and rejection masses. The target's Proof, plans, unrelated candidates, and research folders were not read.
- The first and localized-envelope implications are valid in any target dimension when their stated premises hold; the concrete mass-floor, cap, radial-tail, and coefficient comparisons reconstructed here are dimension-four statements. No uniform-in-dimension extension of those concrete premises is established.
- The rare-contamination step requires $1-\pi_0\leq Q(2u)/q$. It excludes arbitrary alternative supports only in that small-mass regime. It does not cover all vanishing contamination rates, intermediate masses, or arbitrary joint choices of $W,d,q$.
- The one-percent object is excluded at its displayed $u=104$ using its explicit localized cap and tail constants. Its calculation alone does not exclude every mean just above $u$ with every contamination fraction. The moderate-mass obstruction has its own separate premise $W([u,\infty))\geq1/2$.
- General mixtures that lack these mass floors or tiny-contamination conditions, and mixtures spread across competing contact branches, remain uncovered unless an earlier obstruction applies. These bounds avoid tracking the first contact only within their stated families; they do not prove global control of contact births, switches, degeneracies, positive variation as a measure, or conditional radial transport for arbitrary $W$.
- No survivor, numerical grid, or failed search is a proof of the unrestricted population target. This round supplies no proof-verification verdict, finite Gaussian-vector approximation, or resolution of either original unrestricted Gaussian BH target. No existing research file or loop transition was edited.
