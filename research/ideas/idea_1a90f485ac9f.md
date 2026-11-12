---
type: idea
title: >-
  Calibration and e-BH routes cannot beat the Benjamini-Yekutieli log factor
  without conditioning on the Gaussian structure
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
  - lei2026_conditional_fdp_bound
tags:
  - strategic-brainstorm-20261108
  - e-values
  - calibration
  - negative-result
  - tool
  - rank-8-of-8
---

Strategic observation from the 8 November 2026 brainstorm (ranked 8 of 8; payoff is a tool/negative result that saves loop effort). Elementary; the three claims below are proved inline.

1. Calibrator impossibility. Let $f\ge0$ be nonincreasing with $\int_0^1 f(t)\,dt\le1$ (a p-to-e calibrator). Then $\inf_{t\in[q/N,q]}t f(t)\le1/\log N$, because $1\ge\int_{q/N}^q f\ge\inf_{[q/N,q]}(tf)\int_{q/N}^q dt/t=\inf(tf)\log N$. Consequently a pointwise domination $\mathbf 1\{i\in\mathcal R\}/R\le(q'/N)f(p_i)$ for all realizations, which would give $\mathrm{FDR}\le q'\pi_0$ under arbitrary dependence by the e-BH argument of Wang and Ramdas (JRSSB 2022, https://academic.oup.com/jrsssb/article/84/3/822/7056146 ; arXiv https://arxiv.org/abs/2009.02824), requires $f(qR/N)\ge N/(q'R)$ for all $R\le N$, i.e. $q'\ge q/\inf(tf)\ge q\log N$: the Benjamini-Yekutieli shape of Blanchard-Roquain 2008 ( https://arxiv.org/abs/0802.1406 ), which Guo-Rao 2008 ( https://www.sciencedirect.com/science/article/abs/pii/S0378375808000165 ) show is unimprovable over arbitrary joint laws. The closed e-BH of Xu-Ramdas ( https://arxiv.org/abs/2504.11759 ) improves e-BH as a procedure but is irrelevant to bounding ordinary BH.

2. Gaussian mixture e-values are calibrators. $e(T)=\int e^{\lambda T-\lambda^2/2}\,d\mu(\lambda)$ is a valid e-value for every one-sided null ($\theta\le0$) and is a function of $p=\overline\Phi(T)$, so item 1 applies. Explicitly, $\mu=N(0,\tau^2)$ gives $e(T)=(1+\tau^2)^{-1/2}\exp\{\tau^2T^2/(2(1+\tau^2))\}$; at $T=U$ with $\tau=U$ this is $\approx c/(qU^2)$, i.e. a loss factor $U^2=2\log(1/q)$ relative to $1/p$, matching BY when $N\asymp1/q$. No choice of $\mu$ escapes item 1.

3. Conditional e-values add nothing. For $e_i=e_i(T_i,Z)$ with $\mathbb E[e_i\mid Z]\le1$ (valid for e-BH under arbitrary dependence), the best pointwise majorant of $\mathbf 1\{i\in\mathcal R\}/R$ by $(q/N)e_i$ is exactly the leave-one-out identity $\mathbf 1\{P_i\le qR_i/N\}/R_i$, whose conditional expectation is the approved [Lei conditional leave-one-out FDP bound](lei2026_conditional_fdp_bound). So the e-value reformulation does not change the problem.

4. Consequence for planning. Any proof of the order target must use the JOINT Gaussian law through the dependence of the BH level on the factors (the shell program), not through marginal calibration of individual p-values; this is consistent with Lei's Discussion (conditional calibration of Fithian-Lei 2022, https://arxiv.org/abs/2007.10438 , exploits known dependence to avoid the full $O(\log N)$). The only e-value-flavoured route left is an e-process in the bottom-up level filtration (see the optimal-stopping idea from the same brainstorm). Failure criterion: none needed; this is a closed negative observation. Payoff: tool.
