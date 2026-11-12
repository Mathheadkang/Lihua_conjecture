---
type: search_round
title: 'Round 3: centered thin-band mass and scoped noncollinear sign obstructions'
target_asset: gaussian_bh_mixed_coherence_trace_budget
mode: refute
round: 3
directions:
  - boundary_degenerate
  - small_cases
  - drop_hypothesis
candidates:
  - cand_gaussian_bh_mixed_coherence_trace_budget_r3_s1_coalescing_rank_band
  - cand_gaussian_bh_mixed_coherence_trace_budget_r3_s2_independent_mixed_pair
  - cand_gaussian_bh_mixed_coherence_trace_budget_r3_s3_near_unit_normalization
statement_digest: 3c4f7eca379603e53ffd48c73869d12508d38f68f5f792a85af33304907ad513
performed_by: unknown
created_at: '2026-11-08T10:11:34.498Z'
extension_version: 0.0.4
---

## Obstructions

- A collapsing positive-trace rank band does not evade the square-root budget in the checked same-direction two-null family. For $N=2$, $v_1=v_2=1$, $\theta=(0,-c)$, $A=\overline\Phi^{-1}(q/2)$, $U=\overline\Phi^{-1}(q)$, $c=A-U+\delta$ and $0<\delta<1/A$, actual BH has rank one on $E=[A,A+\delta)$ and rank two above it. With $b_2=1/H$, $b_1=1/h(A)$, $\Delta=b_2-b_1$, $r=Hb_1$ and $p=Q(E)$, the prescribed posterior is $a_t=b_2-\Delta\rho_t$, where $\rho_t=\mathbb Q(Y\in E\mid\mathcal F_t)$. After establishing absolute trace integrability and the endpoint identity, centering at $b_2$ yields $M_+\le F\Delta\sqrt{2Dp}$, whereas conditional Jensen gives $1-x\ge p(1-r^2)$. Since $F=q/2$, $D=\log(2/q)\le U^2$ and $H\ge U$ for $U\ge3$, these imply $M_+\le q\sqrt{1-x}$ uniformly, including arbitrarily fast collapse of $\delta$. The failure is retention of the same square root of band mass on both sides, rather than a lower bound requiring separated cutoffs. This scoped proof step is recorded in [Centering a two-mark scalar posterior retains the thin-band mass in the coherence budget](../ideas/idea_b3e3aa1c2640.md).
- Independence rules out positive trace for the checked two-test mixed-label family $N=d=2$, $v_i=e_i$, $\theta=(0,\mu)$, $\mu>0$. The only FDP-supporting regions are $E=\{z_1\ge U,z_2\ge U-\mu\}$ with $f=1/2$, $B=e_1/(2H)$, and $J=\{z_1\ge A,z_2<U-\mu\}$ with $f=1$, $B=e_1/h(A)$. Hence $a=e_1(c+\Delta\pi)$, with $c=1/h(A)$ and $\pi$ the posterior weight of $E$. The independent heat factors give $\partial_{z_1}\log(\pi/(1-\pi))=[h((U-z_1)/\sqrt{1-t})-h((A-z_1)/\sqrt{1-t})]/\sqrt{1-t}<0$. Thus $\operatorname{tr}K<0$ and $M_+=0$ for every $\mu>0$. The candidate verifies absolute trace integrability and the endpoint identity independently, using the bounded terminal-mark martingale and its finite squared-gradient energy. This obstruction covers precisely these independent mixed pairs, not all noncollinear Gaussian models.
- A Gaussian statistic formed from a nonunit observation vector cannot test the unit-diagonal covariance target. The normalization diagnostic uses a scalar vector of norm $1+q$, so its H2 check fails; H3, H4, H5 and NOT remain unknown. This is a hypothesis obstruction only and supplies no heat-trace or budget conclusion.

## Limitations

- The orthogonal all-null $N=2$ calculation obtained $F=q$ and endpoint integral $\int z\cdot B\,d\gamma_2=q$, but its budget calculation was not completed. Neither value alone establishes the signed heat trace, its absolute integrability, the endpoint identity, the coherence deficit, or the proposed budget. This calculation is not a checked failed candidate or a verified budget case.
- The independent mixed pair adds one genuinely noncollinear geometry. Correlated mixed pairs, nearly collinear perturbations, multiple noncollinear directions, arbitrary covariance rank and dimension, and complexity growing with $q^{-1}$ remain unresolved.
- The positive-trace calculation covers only the displayed all-null same-direction two-mark family with a single coalescing rank interval. Unequal directions, more than two terminal marks, interacting rank changes, cancellation among vector marks, and mixed-label positive-trace cascades are not controlled by its centered-mass argument.
- General nonpositive true-null means, unequal means within larger blocks, several alternative blocks and unrestricted mixed-label covariance remain uncovered outside the specific earlier and current families. The independent family covers every $\mu>0$ only at $N=2$ and covariance $I_2$.
- No round-3 calculation establishes necessity or sufficiency of the entropy-linear term, the universal mixed budget, or unrestricted absolute trace integrability and endpoint identification. The normalization diagnostic stops at H2 and cannot settle any later check. No admissible counterexample was found; the target remains unproved.
