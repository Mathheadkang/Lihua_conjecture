---
type: search_round
title: 'Round 4: coherent-null innovation control and the completed orthogonal pair'
target_asset: gaussian_bh_mixed_coherence_trace_budget
mode: refute
round: 4
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - cand_gaussian_bh_mixed_coherence_trace_budget_r4_s1_three_coalescing_marks
  - cand_gaussian_bh_mixed_coherence_trace_budget_r4_s2_correlated_one_null_pair
  - cand_gaussian_bh_mixed_coherence_trace_budget_r4_s2_orthogonal_all_null_pair
  - cand_gaussian_bh_mixed_coherence_trace_budget_r4_s3_coherent_null_cascades
  - >-
    cand_gaussian_bh_mixed_coherence_trace_budget_r4_s3_near_collinear_mixed_pair
statement_digest: 3c4f7eca379603e53ffd48c73869d12508d38f68f5f792a85af33304907ad513
performed_by: unknown
created_at: '2026-11-08T10:22:26.969Z'
extension_version: 0.0.4
---

## Obstructions

- **A common true-null direction rules out arbitrary finite BH rank cascades, even with unrestricted alternatives.** In every finite model with all true-null unit vectors equal to one common vector $v$, arbitrary nonpositive true-null means and arbitrary alternative means and unit-vector geometry, the actual BH terminal mark is $B/f=vs$, $s=1/h(u_R)\in(0,1/H]$ on FDP support. A rejected true null forces $v\cdot G\ge U$, hence $0<F\le q$. Under the prescribed tilt, $a_t=vk_t$ with $k_t=\mathbb E_{\mathbb Q}[s(W_1)\mid\mathcal F_t]$. The checked coherent-null candidate derives entropy energy and the innovation Brownian motion $Z_t=W_t-\int_0^t\beta_rdr$, then proves the bounded-martingale gradient energy, absolute trace and drift integrability, and the endpoint identity before estimating the trace. That identity gives $M=F\mathbb E_{\mathbb Q}[s(W_1)v\cdot Z_1]$. Centering at $1/H$ uses only the zero mean and unit second moment of $v\cdot Z_1$, not its independence from the terminal mark. The pointwise inequality $(s-1/H)^2\le H^{-2}-s^2$ and conditional Jensen give
  $$
  |M|\le F\sqrt{\mathbb E_Q(s-1/H)^2}
  \le\frac FH\sqrt{\mathbb E_Q(1-H^2s^2)}
  \le\frac qH\sqrt{1-x}.
  $$
  Thus the square-root term alone blocks this entire family uniformly on $0<q\le\overline\Phi(3)$, even when $N,d$, conservative null means, alternative geometry and the number or width of actual-rank changes depend arbitrarily on $q$. The three coalescing all-null marks are included; their separate checked entropy argument also gives $M_+\le(2q/3)\sqrt{1-x}$ for that displayed family. Both correlated one-null pair candidates, including the nearly singular pair, are independently checked instances of the common-null-direction obstruction. They provide coverage rather than additional mechanisms. The scoped proof step is recorded in [Common true-null direction: centered scalar innovation controls arbitrary finite BH cascades](../ideas/idea_94e4ebc2d855.md).

- **The exact orthogonal all-null pair has a rank-cutoff deficit that absorbs its finite-dimensional innovation bound.** For $N=d=2$, $\theta=(0,0)$, $v_i=e_i$, let $A=\overline\Phi^{-1}(q/2)$ and $r=H/h(A)$. The actual largest-rank BH regions have terminal marks $e_1/h(A)$, $e_2/h(A)$ and $(e_1+e_2)/(2H)$. The completed calculation verifies $F=q$, $D=\log(1/q)$, all required absolute integrability and endpoint identifications, then obtains $|M|\le\sqrt2 q/H$ and
  $$
  1-x\ge(1-q)(1-r^2)+q/2,\qquad H^2(1-x)>1/4.
  $$
  Consequently $M_+\le3q\sqrt{1-x}$ uniformly on the displayed level range. This closes the earlier unfinished budget calculation for this exact pair; $F=q$ and the endpoint value $\int z\cdot B\,d\gamma_2=q$ alone were not used as a substitute for the trace checks.

## Limitations

- No admissible counterexample was found in round 4. The checked obstructions do not prove the unrestricted mixed budget.
- General multiple distinct true-null directions remain uncovered, including nearly aligned but unequal true-null vectors, cancellation among vector marks, and positive-trace interactions or cascades in unrestricted mixed-label covariance models. The arbitrary finite-$N$ and arbitrary-alternative conclusion above requires the true-null vectors to be exactly common.
- The orthogonal all-null calculation is complete only for the exact zero-mean $N=d=2$ pair. General orthogonal all-null models with $N>2$, conservative means in orthogonal families, arbitrary covariance rank and dimension with several true-null directions, and uniform bounds as these complexities grow with $q^{-1}$ remain unresolved.
- Arbitrary negative true-null means, unequal null blocks and many alternative blocks are covered by the common-direction argument only when all true-null vectors coincide. No corresponding unrestricted multi-direction result was checked.
- This round does not establish necessity or sufficiency of the entropy-linear term, nor universal absolute trace integrability or endpoint identification. Those checks were completed only within the stated families. The information-label observation listed on the board and any newly proposed information-theoretic route were not checked round candidates and are not promoted to verified obstructions or theorems here.
