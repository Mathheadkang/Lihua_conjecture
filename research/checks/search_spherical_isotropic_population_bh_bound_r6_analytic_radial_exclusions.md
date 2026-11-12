---
type: search_round
title: Round-six analytic radial exclusions for spherical population BH
target_asset: spherical_isotropic_population_bh_bound
mode: refute
round: 6
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
  - cand_spherical_isotropic_population_bh_bound_r6_s2_d9_weak_atom
  - >-
    cand_spherical_isotropic_population_bh_bound_r6_s7_d4_microscopic_positive_mean
  - >-
    cand_spherical_isotropic_population_bh_bound_r6_s8_ultraweak_exponential_unbounded
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-05T01:17:48.877Z'
extension_version: 0.0.4
---

## Obstructions

- **Every allowed mean law at dimension nine and the endpoint level fails NOT.** Fix $d=9,u=104,q=2Q(u)$, and allow any Borel $W$ on $[0,\infty)$. Symmetric unimodality gives $F_r(x)\geq2H_r(x)$, hence $\operatorname{FDP}_{\rm pop}\leq\pi_0$; null FDP vanishes for $r\leq u$ and whenever the contact has $x_r\geq r$. For $u\leq x<r$, the exact cap formula and lower Mills bound in `cand_spherical_isotropic_population_bh_bound_r6_s2_d9_weak_atom` give the simultaneous envelope
  $$
  \frac{H_r(x)}{Q(x)}\leq560\sqrt{2\pi}e^{-4}(1+u^{-2})r^{-7}e^{r^2/2}.
  $$
  Integrate it against the $\chi_9$ density $\sqrt{2/\pi}\,r^8e^{-r^2/2}/105$ on $(u,b]$, where $b=\sqrt{u^2+72}$, and use $\operatorname{FDP}_{\rm pop}\leq\pi_0$ above $b$. For $\pi_0>0$ this gives
  $$
  \frac{\operatorname{FDR}_{\rm pop}}{q\pi_0}
  \leq384e^{-4}(1+u^{-2})+\frac{\mathbb P(R>b)}q
  <\frac{64}{9}\frac{10001}{10000}+\frac1{16}
  =\frac{645689}{90000}<\frac{15}{2}.
  $$
  The exact odd-dimensional radial tail, $104<b<105$, and $e^4>54$ certify the tail term $<1/16$. Meanwhile $M_9=945/(1372\sqrt7)>1/4$ and $\log312>11/2$ make the proposed multiplicative coefficient $>15/2$. No property of the alternative atom or its weight enters this exclusion: it covers arbitrary null proportions, singular or unbounded mean laws, and laws without moments, at precisely these fixed $d,u$. If $\pi_0=0$, FDR is zero directly. This is a fixed-parameter extension of the null-envelope route `idea_3afb7bc15f1e`, not a uniform theorem over $d,u$.

- **A microscopic upper bound on every mean prevents contact until an explicitly rare radius.** Fix $d=4,u=104,q=2Q(u)$ and any Borel $W$ supported on $[0,m]$, $m=u^{-2}$. Set $b=\sqrt{u^2+6\log u}$. The dimension-four cap bound $H_r(t)\leq C((r-t)/r)^{3/2}$, $C=4\sqrt2/(3\pi)<2/3$, and Gaussian Mills inequalities give, for every $u\leq r\leq b$ and $u\leq x\leq r+m$,
  $$
  \frac{F_r(x)Q(u)}{Q(x)}
  \leq2C\left(\frac{3}{2e}\right)^{3/2}
  e^{bm+m^2/2}\frac{b+m+u^{-1}}u
  <\frac45\frac{100}{99}\frac{53}{52}<1.
  $$
  For $x>r+m$ the total rejection mass is zero, so no finite contact exists on this radius interval. At $r\leq u$ null FDP is zero even if a contact exists. Thus symmetric unimodality and the exact $\chi_4$ tail imply
  $$
  \operatorname{FDR}_{\rm pop}\leq\pi_0\mathbb P(R>b),\qquad
  \frac{\mathbb P(R>b)}q
  <\frac32\left(1+\frac1{10000}\right)
  \left(\frac12+\frac{16}{10000}\right)<1.
  $$
  Therefore FDR is $<q\pi_0$ when $\pi_0>0$, and is zero when $\pi_0=0$, strictly below the target right side. This excludes the whole stated support-restricted family, including `cand_spherical_isotropic_population_bh_bound_r6_s7_d4_microscopic_positive_mean`, without relying on its two atoms or its null weight.

- **A sufficiently small mass beyond a microscopic mean also forces positive null FDP into a rare radial event.** Fix $d=4,u=104,q=2Q(u)$, set $a=e^{-2u^2}$, and assume the explicit concentration condition $W((a,\infty))\leq Q(2u)/q$. The argument of `cand_spherical_isotropic_population_bh_bound_r6_s8_ultraweak_exponential_unbounded` extends to every Borel $W$ with this condition, since splitting means at $a$ gives $F_r(x)\leq2H_r(x-a)+W((a,\infty))$. Its cap and hazard bounds are
  $$
  \frac{H_r(t)}{Q(t)}<\frac52\frac{e^{r^2/2}}{r^2}\quad(2\leq t\leq r),
  \qquad \frac{Q(x-a)}{Q(x)}<2\quad(u\leq x\leq2u).
  $$
  If a prescribed contact has positive null FDP and $r\leq2u$, then $u\leq x_r<r$ and the contact identity forces $e^{r^2/2}/r^2>1/(10q)$. This function is increasing above $u$, so let $s>u$ solve $e^{s^2/2}/s^2=1/(10q)$. Positive FDP at $r\leq2u$ requires $r>s$. Exact $\chi_4$ tails give $\mathbb P(R\geq s)=10q(1/s^2+1/2)<6q$ and $\mathbb P(R>2u)<q$. Together with $\operatorname{FDP}_{\rm pop}\leq\pi_0$, they yield $\operatorname{FDR}_{\rm pop}<7q\pi_0$ for $\pi_0>0$; it is zero for $\pi_0=0$. The target coefficient is $>7$ because $M_4=1/\pi$, $\log312>5$, and $\pi<4$. In particular, the exponential law with scale $e^{-4u^2}$ has tail $e^{-e^{2u^2}}<Q(2u)/q$ above $a$, so every mixture $p\delta_0+(1-p)\nu$ with that alternative obeys the exclusion, including the recorded $p=1/2$ object. Unbounded support is permitted only subject to the stated tail-mass premise. The weak-mean radial-exclusion step is recorded as draft approach `idea_44ab7b27c6cc`.

## Limitations

- All three recorded round-six objects pass their listed hypotheses and fail NOT by the analytic bounds above. The cap substitutions, Mills inequalities, exact radial tails, and rational constant comparisons were reconstructed; exact arithmetic checked displayed certificates only. No numerical contact scan, parameter grid, absence of a survivor, or direction label supplies a proof, proof-verification verdict, or exhaustive search of the target.
- The dimension-nine envelope fixes $d=9,u=104$. The two dimension-four exclusions likewise fix $u=104$, and require respectively $W([0,u^{-2}])=1$ or $W((e^{-2u^2},\infty))\leq Q(2u)/q$. Their arbitrary-null-mass and distributional extensions follow only from the displayed analytic premises. General dimensions, general $u\geq104$, weak/strong mixtures outside these concentration conditions, and simultaneous variation of $d,W,q$ remain uncovered except where earlier recorded obstructions already apply.
- The present pack supplies no independently reconstructible new exclusion from contact degeneracy, infinite-moment laws outside the stated families, or growing-dimensional scaling. The three candidate records do not establish that those announced directions were exhausted. The unbounded exponential example does not settle arbitrary unbounded or infinite-moment laws.
- The unrestricted draft theorem still needs global control of the smallest contact, including births, switches, degeneracies and positive variation as a measure wherever used, followed by valid conditional radial transport and cutoff estimates, or a complete replacement argument. These family-specific envelopes and radial exclusions bypass contact differentiation only under their stated premises; they do not establish those premises for arbitrary $W$. An almost-everywhere contact derivative bound alone remains insufficient.
