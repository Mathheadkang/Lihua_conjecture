---
type: search_round
title: >-
  Round 1: constant posterior fields, antipodal cancellation, and a separated
  collinear rank jump
target_asset: gaussian_bh_mixed_coherence_trace_budget
mode: refute
round: 1
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - cand_gaussian_bh_mixed_coherence_trace_budget_r1_s1_duplicated_null_equality
  - cand_gaussian_bh_mixed_coherence_trace_budget_r1_s2_antipodal_pair
  - cand_gaussian_bh_mixed_coherence_trace_budget_r1_s2_single_null
  - >-
    cand_gaussian_bh_mixed_coherence_trace_budget_r1_s3_barely_negative_collinear
statement_digest: 3c4f7eca379603e53ffd48c73869d12508d38f68f5f792a85af33304907ad513
performed_by: unknown
created_at: '2026-11-08T09:59:37.544Z'
extension_version: 0.0.4
---

## Obstructions

- A constant terminal ratio rules out the entire constant-posterior family: whenever $B=fb$ almost everywhere for a fixed vector $b$, heat convolution gives $a(t,z)=b$ and $K_t=0$ for every $t<1$, hence $M=0$. The tested single-null and identical-null multiplicity models belong to this family; their unit-coherence case therefore cannot violate the mixed budget.
- In the exact two-null antipodal family $N=2$, $\theta=(0,0)$, $v_1=1,v_2=-1$, cancellation between the two disjoint rejection tails forces $0\le M\le2q/u^2$, where $u=\overline\Phi^{-1}(q/2)$. Meanwhile $1-x\ge1-h(U)^2/h(u)^2\sim2\log(2)/U^2$ as $q\downarrow0$, with $U=\overline\Phi^{-1}(q)$. Thus $M_+/(q\sqrt{1-x})$ stays uniformly bounded on $0<q\le\overline\Phi(3)$ and tends to zero at small levels. The square-root term alone blocks this family.
- In the collinear two-null family $N=2$, $v_1=v_2=1$, $\theta=(0,-c)$, with $A=\overline\Phi^{-1}(q/2)$ and $c\ge A-U+1/A$, the actual BH rank jumps from one to two at $T=U+c$. The posterior field has the form $a=k_1+\Delta\pi$, where $\pi$ is the tilted conditional probability of the terminal upper tail, $k_1=1/h(A)$, and $\Delta=1/h(U)-k_1$. Its positive derivative satisfies $F\mathbb E_{\mathbb Q}K_t\le\Delta\phi(T)$, while the separated cutoffs give $1-x\ge(1-e^{-1})(1-r^2)$, $r=h(U)/h(A)>1/2$. These bounds yield $M_+\le2q\sqrt{1-x}$ uniformly over this whole family, including arbitrarily negative shifted means. Singular covariance, a nearly boundary null mean, and one genuine actual-rank jump therefore do not by themselves produce a violation in this tested range.

## Limitations

- No family with two or more noncollinear observation directions was analyzed; arbitrary dimension, covariance rank, and $q$-dependent directional complexity remain uncovered.
- No tested family contains a false null with positive mean. Mixed true/false labels and their effect on the FDP tilt and actual largest BH rank remain uncovered.
- Beyond constant-posterior multiplicities, the nonconstant posterior calculations cover only the displayed $N=2$ families. They do not cover multiple interacting rank jumps, general multiplicities with varying terminal ratios, or growing $N$.
- The collinear rank-jump estimate requires $c\ge A-U+1/A$. The interval $0<c<A-U+1/A$, general collections of unequal nonpositive means, and perturbations away from exact collinearity are not covered.
- No tested family needs the entropy-linear term. The round does not establish that term's sufficiency in other regimes, nor absolute trace integrability, the endpoint identity, or the proposed budget in the full unrestricted model. No counterexample was found and no universal proof follows.

The proof-step-like obstruction and scoped posterior-change approach are recorded as idea_5ad2305afb75.
