---
type: search_round
title: 'One-sided Gaussian BH upper-bound search: round 4 obstructions'
target_asset: gaussian_bh_one_sided_sharp_upper
mode: refute
round: 4
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
  - known_counterexamples
candidates:
  - cand_gaussian_bh_one_sided_sharp_upper_r4_s2_single_antagonistic_alternative
  - cand_gaussian_bh_one_sided_sharp_upper_r4_s4_independent_negative_pairs
statement_digest: 03b9629ae9bd4a6f3de6d1b9c08dfb86fb31a1aa0b7c62a1844a84111ad32086
performed_by: unknown
created_at: '2026-11-04T10:39:51.371Z'
extension_version: 0.0.4
---

## Obstructions

- **Independent all-null pairs cannot accumulate inflation on the proposed scale.** In [the negative-pair candidate](../candidates/cand_gaussian_bh_one_sided_sharp_upper_r4_s4_independent_negative_pairs.md), each pair has correlation $-1/2$, pairs are independent, all means are $0$ or $-q$, and the total covariance has rapidly growing full rank. For each pair the auxiliary group p-value $W_b=\min\{1,2\min(p_{2b-1},p_{2b})\}$ is superuniform by marginal validity and a union bound; the group p-values are independent across pairs. An original BH rejection event implies a group BH rejection at level $2q$, because $R$ rejected coordinates occupy at least $R/2$ pairs. Thus the original all-null FDR is at most $2q$, uniformly in the number of pairs, and NOT fails after normalization by $q\sqrt{\log(1/q)}$. This argument is scoped to independent all-null pairs; it does not require the particular negative correlation within a pair, but it does require the stated cross-pair independence and all-null setting.

- **Independent composite nulls with at most one alternative give only order-$q$ FDR.** In [the antagonistic-alternative candidate](../candidates/cand_gaussian_bh_one_sided_sharp_upper_r4_s2_single_antagonistic_alternative.md), the centered null coordinates are independent standard normals, their means are strictly negative, and the sole alternative is a negatively correlated normalized sum of those normals with a positive mean. Write $R=V+A$, where $A\leq1$. If $V\geq1$, then $R\leq2V$ and the $V$th ordered null p-value is at most $2qV/N$. The null p-values dominate independent uniforms pointwise, so a false discovery implies an independent-uniform crossing at level $\alpha=2qM/N<2q$. The candidate's finite-level calculation yields $\operatorname{FDR}\leq2eq/(1-2eq)=O(q)$ for sufficiently small $q$, uniformly in the enormous null dimension. Hence NOT fails. The argument remains valid for arbitrary nonpositive null means and the sole alternative's allowed finite mean and joint Gaussian dependence on the nulls; it does not cover dependent centered nulls or a growing population of alternatives.

## Limitations

- **The two logarithmic-rank sign-cube models remain unresolved test cases.** The [all-null sign orbit](../ideas/idea_17bd1034395f.md) and [mixed-mean sign cube](../ideas/idea_bd097b4b530f.md) are draft ideas, not failed candidates or surviving refuters. The round's report and their current records do not settle their BH asymptotics, and no sign-cube obstruction is asserted here.
- The missing sign-cube calculation is the simultaneous $q\downarrow0$ behavior of the actual BH FDR while rank, dimension, means, and the finite testing arrays vary with $q$. The [conditional sign-cube free-energy approach](../ideas/idea_4cbdb4b7e0d9.md) remains a draft route: a conditional rate or fixed-parameter likelihood calculation alone does not establish the Gaussian-integrated global BH limit. Uniform tail prefactors and discretization errors on the $q\sqrt{\log(1/q)}$ scale remain necessary, together with the actual global cutoff and the distinction between an all-null rejection event and mixed-mean FDP. A fixed-model or fixed-level limit does not justify an interchange of these limits.
- Inconclusiveness of the current bounds in the examined factor representations does not prove that every equivalent factor representation is unhelpful. Covariance rank, common-factor dimension, residual variance, and oriented-null complexity remain distinct. The available approved entropy and radial bounds keep their stated coverage; these test cases do not invalidate them or establish that their hypotheses fail in every representation.
- The pair comparison does not extend here to dependent blocks or mixed alternatives, and the single-alternative argument does not extend here to general dependent nulls or many alternatives. Neither obstruction supplies a general monotonicity theorem allowing arbitrary negative true-null means to be replaced by zero.
- No verified one-sided asymptotic counterexample was obtained in this round. The unrestricted upper bound and its proposed constant $1/\sqrt\pi$ remain open; the two scoped order-$q$ exclusions and the unresolved sign-cube test cases have different evidentiary status.
