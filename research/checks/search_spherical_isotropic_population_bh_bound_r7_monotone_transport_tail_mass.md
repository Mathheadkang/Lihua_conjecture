---
type: search_round
title: >-
  Round seven: monotone weak-mean transport and concentrated heavy-tail
  obstructions
target_asset: spherical_isotropic_population_bh_bound
mode: refute
round: 7
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
  - cand_spherical_isotropic_population_bh_bound_r7_s2_d4_inverse_u_atom
  - >-
    cand_spherical_isotropic_population_bh_bound_r7_s3_weak_bulk_infinite_mean_tail
  - cand_spherical_isotropic_population_bh_bound_r7_s7_d4_two_over_u_atom
  - cand_spherical_isotropic_population_bh_bound_r7_s8_infinite_mean_lomax
statement_digest: 6909caa2801e56b1b457f82e3e23986c42d944b50096ec7cb39f26291eeb6bb7
performed_by: unknown
created_at: '2026-11-05T01:51:57.612Z'
extension_version: 0.0.4
---

## Obstructions

- **Means supported on $[0,u]$ give a monotone first contact and conditional radial transport, hence $\operatorname{FDR}_{\rm pop}\leq q\pi_0$.** This family exclusion holds for every target dimension $d\geq4$, every $u\geq104$, and every Borel $W$ with $W([0,u])=1$. It is reconstructed here from the definitions, rather than adopted from the earlier report. For $x\geq u$ and $\mu\leq u$, both $x-\mu$ and $x+\mu$ are nonnegative. Since $H_r(t)=H_1(t/r)$ is nondecreasing in $r$ for $t\geq0$, $F_r(x)$ is nondecreasing in $r$. The admissible sets are therefore nested, so their smallest contacts $x(r)=x_r\in[u,\infty]$ are nonincreasing and Borel measurable, with $\infty$ denoting no finite contact.

  The transport step also has a global order argument. Write $h_d$ for the $\chi_d$ density and, for finite $x\geq u$, put
  $$
  A(r,x)=\mathbb P(R\leq r\mid Z_1\geq x),\qquad
  f_x(r)=\partial_r A(r,x)=h_d(r)\frac{H_r(x)}{Q(x)}.
  $$
  If $V$ is uniform on $(0,1)$ and $S\sim\chi^2_{d-1}$ is independent, then
  $$
  G_x=Q^{-1}(VQ(x)),\qquad R_x=\sqrt{G_x^2+S}
  $$
  have respectively the conditional normal and conditional radial laws. Both are nondecreasing in $x>0$ under this coupling, so $A(r,x)$ is nonincreasing in $x$. Set $A(r,\infty)=f_\infty(r)=0$. For any successive endpoints $s<t$ of a partition of $[a,b]\subset(0,\infty)$,
  $$
  A(t,x(t))-A(s,x(s))
  \geq A(t,x(s))-A(s,x(s))
  =\int_s^t f_{x(s)}(z)\,dz.
  $$
  Summing telescopes to at most one. On refining left-endpoint partitions, the selectors converge to $x(z)$ almost everywhere because an extended monotone function has at most countably many discontinuities after compactification. The density is continuous in finite $x$ and vanishes for $x\geq z$. On $z\in[a,b]$ it is bounded by $h_d(z)/Q(b)$: when $x(s)>z$ it is zero, and otherwise $Q(x(s))\geq Q(b)$. Dominated convergence and exhaustion of $(0,\infty)$ give
  $$
  \int_0^\infty f_{x(r)}(r)\,dr\leq1,
  \qquad
  \operatorname{FDR}_{\rm pop}
  =q\pi_0\int_0^\infty f_{x(r)}(r)\,dr\leq q\pi_0.
  $$
  Thus jumps, contact births and infinite cutoffs are handled for this monotone family without an almost-everywhere contact derivative. This argument is recorded as the draft approach `idea_0fee0d078331`; it gives no unrestricted-target verification verdict. It includes the support families behind `cand_spherical_isotropic_population_bh_bound_r7_s2_d4_inverse_u_atom` and `cand_spherical_isotropic_population_bh_bound_r7_s7_d4_two_over_u_atom`. Their separate $d=4,u=104$ cap-and-tail certificates were also reconstructed: support in $[0,u^{-1}]$ gives $\operatorname{FDR}_{\rm pop}<(3+4u^{-2})q\pi_0<4q\pi_0$, and support in $[0,2/u]$ gives $\operatorname{FDR}_{\rm pop}<5q\pi_0$, for $\pi_0>0$. The latter excludes finite contacts on $u<r\leq\sqrt{u^2+6\log u}-2/u$ and uses the exact $\chi_4$ tail. These local certificates do not depend on the two-atom choices or their null weights.

- **A sufficiently small mass above $u^{-1}$ excludes a weak-bulk family even with infinite first moment.** Fix $d=4,u=104,q=2Q(u)$ and assume
  $$
  \varepsilon=W((u^{-1},\infty))\leq\frac{Q(2u)}{10q}.
  $$
  Splitting means at $m=u^{-1}$ gives $F_r(x)\leq2H_r(x-m)+\varepsilon$. The dimension-four cap estimate and Mills inequalities give, for $t>100$ and $u\leq x\leq2u$,
  $$
  \frac{H_r(t)}{Q(t)}<\frac34\frac{e^{r^2/2}}{r^2},\qquad
  \frac{Q(x-m)}{Q(x)}<8.
  $$
  A finite contact with positive null FDP necessarily has $u\leq x_r<r$. If $r\leq2u$, its equality $F_r(x_r)=2Q(x_r)/q$ consequently forces
  $$
  h(r):=\frac{e^{r^2/2}}{r^2}\geq\frac{19}{120q}.
  $$
  Let $s>u$ solve $h(s)=19/(120q)$; existence and uniqueness follow from strict increase above $u$ and the upper Mills bound at $u$. Thus positive FDP below $2u$ requires $r\geq s$. Symmetric unimodality gives $F_r(x)\geq2H_r(x)$ and hence $\operatorname{FDP}_{\rm pop}\leq\pi_0$ for every $W$. The exact $\chi_4$ tail and the displayed radial condition now imply
  $$
  \mathbb P(R\geq s)=\frac{120q}{19}(s^{-2}+1/2)<\frac{10q}{3},\qquad
  \mathbb P(R>2u)<q,
  $$
  and therefore $\operatorname{FDR}_{\rm pop}<(13/3)q\pi_0<5q\pi_0$ when $\pi_0>0$. The sparse Pareto mixture in `cand_spherical_isotropic_population_bh_bound_r7_s3_weak_bulk_infinite_mean_tail` has exactly this tail mass and infinite first moment. The family exclusion depends on the tail-mass premise, not on the moment or the Pareto density.

- **A tail mass controlled at a microscopic cutoff gives a separate Lomax-containing exclusion.** Fix $d=4,u=104,q=2Q(u)$, put $\delta=u^{-2}$, and let $s\in(u,2u)$ be the unique solution
  $$
  h(s)=\frac1{10q}.
  $$
  Suppose $\varepsilon=W((\delta,\infty))<Q(s)/q$. Again $F_r(x)\leq2H_r(x-\delta)+\varepsilon$. The independently reconstructed cap and Gaussian-hazard bounds are
  $$
  \frac{H_r(t)}{Q(t)}<\frac52h(r)\quad(2\leq t\leq r),\qquad
  \frac{Q(x-\delta)}{Q(x)}<2\quad(u\leq x\leq s).
  $$
  At a positive-null-FDP contact with $u<r\leq s$, these imply
  $$
  \frac{F_r(x_r)}{Q(x_r)}
  <10h(r)+\frac{\varepsilon}{Q(s)}<\frac2q,
  $$
  contradicting contact equality. At $r\leq u$ the null numerator is zero. Consequently
  $$
  \operatorname{FDR}_{\rm pop}\leq\pi_0\mathbb P(R>s)
  =10q\pi_0(s^{-2}+1/2)<6q\pi_0
  $$
  for $\pi_0>0$. For `cand_spherical_isotropic_population_bh_bound_r7_s8_infinite_mean_lomax`, $a=e^{-u^2}$ and $\varepsilon=a/[2(a+\delta)]<u^2e^{-u^2}$. The lower Mills inequality gives
  $$
  \frac{q\varepsilon}{Q(s)}<3u^5e^{-u^2}<1,
  $$
  so its infinite-mean law satisfies the premise. This family can have unbounded support and does not require any finite moment. It excludes only laws obeying the displayed mass constraint. In both heavy-tail bullets, $\pi_0=0$ gives FDR zero. For $d=4,u=104$, $M_4=1/\pi$, $\pi<4$ and $\log312>5$ make the proposed coefficient exceed seven, so all the stated strict bounds lie below the target right side.

## Limitations

- All four recorded round-seven objects satisfy their listed hypotheses and fail NOT. Their cap substitutions, Mills inequalities, radial-event implications, exact $\chi_4$ tails and constant comparisons were reconstructed; two read-only checks separately scrutinized the two candidate pairs, and another check scrutinized the restricted monotone-transport argument. No numerical contact grid, absence of a survivor, direction label or same-model check supplies exhaustive search or a formal proof-verification verdict for the target.
- The newly reconstructed monotone-transport exclusion covers every target dimension and level only under $W([0,u])=1$. For means above $x$, the tail $H_r(x-\mu)$ has a negative argument and need not increase with $r$, so the nesting premise has not been established for general $W$. This proof cannot be applied silently to an arbitrary bounded, unbounded or mean-dependent family $W_q$.
- The two unbounded-support exclusions retain $d=4,u=104$ and their explicit concentration premises. Infinite first moment alone neither implies either premise nor rules out a counterexample. General strong-mean mixtures, unbounded laws with appreciable mass above the weak cutoff, other dimensions or levels outside the support-restricted argument, and simultaneous variation of $d,W,q$ remain uncovered except where earlier obstructions already apply.
- This pack contains no independently reconstructible new round-seven exclusion for arbitrary contact degeneracies or unrestricted growing-dimensional scaling. For the unrestricted target, global smallest-contact control across births, switches and degeneracies, the required positive-variation measure bounds, and valid conditional radial transport and cutoff estimates remain to be supplied, or replaced by a complete argument. The restricted monotone proof resolves these issues only in its stated family; the fixed-dimensional radial exclusions bypass them only under their concentration premises.
