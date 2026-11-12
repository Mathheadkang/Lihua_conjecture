---
type: idea
title: >-
  Counterexample probe: two-level hierarchical (GREM-type) Lei construction with
  bump alignment
status: draft
idea_kind: test_case
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
  - lei2026_one_sided_fdr_lower
  - lei2026_integrated_conditional_tail_ratios
  - gaussian_bh_common_loading_wasserstein_fdr_continuity
  - >-
    cx_gaussian_bh_entropy_coherence_trace_budget_r3_s1_unbalanced_antipodal_clones
tags:
  - strategic-brainstorm-20261108
  - counterexample
  - hierarchical
  - GREM
  - multiscale
  - remote-numerics
  - rank-5-of-8
tried_in:
  - target: gaussian_bh_one_sided_universal_order_upper
    round: 3
    slot: 3
    statement_digest: cd12dcc669b996361216cbba6573ecfdf68a5a7c79acc1bbf89869a2e1233389
    outcome: no candidate written (show idea_aca5b09e9a0c for what was found)
---

Strategic direction from the 8 November 2026 brainstorm (ranked 5 of 8). This is the requested "counterexample direction". It is a probe with an explicit candidate construction and an explicit expectation that it FAILS to refute; either outcome is informative. Heavy numerics only on the configured remote server.

1. Why one level saturates at $qU$ (critical reading of the source). In Lei's one-sided construction (arXiv:2607.14812 Section 3, roadmap read: $(\Theta_i,B_i)$ i.i.d. from $\nu^+_{q,r}$, $T_i=\Theta_i+B_iZ+\sqrt{1-B_i^2}\varepsilon_i$, conditional FDP $D_+^*(z)=q$, $qe^{z^2/2}$, $1$ on $z\le0$, $0<z<y_q^+$, $z\ge y_q^+$), the gain is the tilt $\sup_t F_z(t)/t=e^{z^2/2}$ of a null's conditional tail ratio, integrated against $\phi(z)$ (Lebesgue measure appears: $\int_0^y\phi e^{z^2/2}=y/\sqrt{2\pi}$) and capped by $\mathrm{FDP}\le1$ at $qe^{z^2/2}\le1$, i.e. $z\le y_q^+\approx U$. The approved [integrated tail-ratio lemma](lei2026_integrated_conditional_tail_ratios) shows this is the most any single null direction can give. To exceed order $qU$, several heavy null groups driven by INDEPENDENT factors would have to receive their tilts simultaneously at the common level: with loadings $r_g$ and projections $Y_g$, group $g$ is tilted at level $L$ only if $L\approx Y_g/r_g$ within the bump width $O(s_g/r_g)$ ("bump alignment"). For a fixed level the average tilt is exactly $1$ (calibration), and with $G$ independent equal groups the leader-tracking total is $\le y_q/\sqrt{2\pi}$, no better than one direction. So the heuristic says the order target is TRUE, and the only loophole is a mechanism making alignment typical.

2. Candidate construction (all original assumptions satisfied: finite $N$, unit variances, PSD, null means $\le 0$, parameters may depend on $q$). Shared coarse factor $Z_0$ and group factors $Z_g$, $g\le G$, all independent standard normal. Nulls in group $g$: $T=r_0Z_0+r_1Z_g+s\varepsilon$, $r_0^2+r_1^2+s^2=1$, mean $0$. Alternatives of type A: loading $-1$ on $Z_0$, means following Lei's secondary profile $W_r$ (the level tracks $Z_0$ over its middle regime). Alternatives of type B in group $g$: loading $-(r_0'Z_0+r_1'Z_g)/\sqrt{r_0'^2+r_1'^2}$, with a mean profile designed so that inside the $Z_0$-tracking regime the level also tracks $Z_g$ for the heaviest group; group masses geometric ($\pi_g\propto 2^{-g}$, GREM-like) so one group dominates the type-B count at each level (equal masses would average out by the law of large numbers, as in the independent-block records idea_a0de38b6ac99 and idea_11028fd850f5, which are block-diagonal and therefore do not add). Hoped-for conditional FDP $\approx q\,e^{z_0^2/2}e^{z_g^2/2}$ on a product region; if both regimes have length of order $U$, $\mathrm{FDR}\asymp qU^2=q\log(1/q)$, refuting the target. Note: a pure-null hierarchical or log-correlated field cannot work under the global null because nonnegative correlations give PRDS and hence FDR $\le q$ (Benjamini-Yekutieli 2001); alternatives anticorrelated with the nulls are essential.

3. Literature (verified links; abstracts/snippets read): Lei, arXiv:2607.14812, https://arxiv.org/abs/2607.14812 (source, Section 3 construction read in the project copy); Bovier, Kurkova, Derrida's generalised random energy models 1 and 2, Ann. IHP 2004, https://www.numdam.org/article/AIHPB_2004__40_4_439_0.pdf and https://www.numdam.org/article/AIHPB_2004__40_4_481_0.pdf (hierarchical extremal process as Poisson cascades); Kistler, Derrida's random energy models, https://arxiv.org/abs/1412.0958 ; Ding, Roy, Zeitouni, Convergence of the centered maximum of log-correlated Gaussian fields, Ann. Probab. 2017, https://arxiv.org/abs/1503.04588 (only relevant for a continuum hierarchy). Dobriban's two-sided factor-model counterexample to BH control, https://arxiv.org/abs/2607.12208 (abstract read: FDR $>0.0104$ at $\alpha=0.01$, one factor model), is already dominated by the source's lower bounds and does not bear on the order.

4. First testable computation. Population (clone) limit via the approved [common-loading Wasserstein continuity](gaussian_bh_common_loading_wasserstein_fdr_continuity) framework: compute the conditional FDP given $(Z_0,Z_g)$ for a two-group two-level design and the ratio $F/(qU)$ along $q=e^{-U^2/2}$, $U\in\{4,5,6,7\}$; the null hypothesis to refute is "ratio bounded by $1/\sqrt{2\pi}+o(1)$". Analytic companion (bump-alignment lemma): for any two-level design, at the realized level $\sum_g\pi_g\rho_g\le(1+o(1))\max_g\pi_g\rho_g$ unless $|Y_g/r_g-Y_{g'}/r_{g'}|\lesssim s/r$; if proved, it kills this probe and supports the target.

5. Relation to obstacles / failure criterion. A counterexample bypasses all proof obstacles; the design sits exactly where the trace/flux routes lost control (many heavy directions, order-$qU$ trace, cf. the approved low-coherence antipodal counterfamily). Abandon the probe if the population FDP never exceeds the one-level envelope by more than a $1+o(1)$ factor on the grid and the bump-alignment lemma holds; then record the computation as evidence for the conjecture and hand the family to the tree-class positive theorem idea.

6. Payoff: refutation of the current target (changes the research goal), or strong evidence for the order bound plus a concrete structured class for a positive theorem.

## Tried

- Search round 3 for gaussian_bh_one_sided_universal_order_upper (slot 3): no candidate written (show idea_aca5b09e9a0c for what was found)
