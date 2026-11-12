---
type: idea
title: >-
  Global spectral diffuseness does not permit independent rare-count replacement
  at BH ranks
status: draft
idea_kind: test_case
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
tags:
  - covariance-decomposition
  - spectral-cutoff
  - actual-bh-rank
tried_in:
  - target: gaussian_bh_one_sided_universal_order_upper
    round: 2
    slot: 3
    statement_digest: cd12dcc669b996361216cbba6573ecfdf68a5a7c79acc1bbf89869a2e1233389
    outcome: no candidate written (show idea_27c06facb739 for what was found)
---

Portfolio B first-gate calculation for [the unchanged target](../assets/gaussian_bh_one_sided_universal_order_upper.md), following [the portfolio](idea_00ec9e272a12.md). This is a draft diagnostic, not a proof or counterexample to either completion root. No existing asset or plan is changed. Native library searches for covariance decomposition, spectral Gaussian concentration, and multiscale coherent BH yielded no applicable decomposition theorem. The restricted directional-entropy and central-window statements were read; neither controls the conditional residual crossing below.

## Concrete decomposition and proposed stronger gate

Write the ORIGINAL test frame as A=N^{-1} sum_i v_i v_i^T, with unit v_i. Thus trace(A)=1. Let L=log(1/q), tau=1/L, and P be its spectral projector for eigenvalues at least tau. Exactly, rank(P)<=L and ||(I-P)A(I-P)||<=tau. This preserves original test fractions and splits independent Gaussian coordinates in the ambient representation; it does NOT make residual tests independent.

A concrete candidate gate for treating the residual as an independent-count perturbation would require a universal C such that, whenever ||A||<=tau, its all-null count B(u)=sum_i 1{v_i.G>=u} at every actual BH GRID threshold S(u)=qk/N satisfies Var(B(u))<=C N S(u), possibly with an additional factor polynomial in L. This diagnostic disproves that stronger gate already at k=1. It does not disprove an integrated O(q sqrt(L)) estimate for the ACTUAL largest-rank payoff. No conditioning on a free rank is substituted for that payoff.

## Exact equicorrelation calculation at enormous finite dimensions

Take q=exp(-L), rho=1/(2L), N=ceil(exp(L^3)), all means zero, and
$$
v_i=\sqrt{\rho}\,e_0+\sqrt{1-\rho}\,e_i .
$$
The nonzero eigenvalues of A equal rho+(1-rho)/N once and (1-rho)/N with multiplicity N-1. For large L they are all below tau, so this entire model is declared diffuse by the proposed global cutoff. All dimensions are finite.

At the actual BH rank-one grid level p=q/N, put u=S^{-1}(p). Given Z=G_0, the indicators are independent with probability
$$
\pi(Z)=S((u-\sqrt{\rho}Z)/\sqrt{1-\rho}).
$$
Let a=sqrt(rho)u and b=u sqrt(1-rho). On a<=Z<=a+1/u, pi(Z)>=S(b). For u>=2 and rho<=1/2, elementary Mills inequalities give
$$
\frac{S(b)}{S(u)}\ge\frac12\exp(\rho u^2/2),\qquad
\mathbb P\{a\le Z\le a+1/u\}\ge\frac c u\exp(-\rho u^2/2),
$$
with an absolute c>0. Indeed S(b)>=phi(b)/(2b), S(u)<=phi(u)/u, and the interval probability is at least phi(a+1/u)/u. Consequently
$$
\frac{\mathbb E\pi(Z)^2}{p^2}\ge\frac c u\exp(\rho u^2/2).
$$
No asymptotic interchange of dimension and q occurs: this is a finite-model inequality. The exact variance identity is
$$
\frac{\operatorname{Var}B(u)}{Np}
=1-p+(N-1)p\left(\frac{\mathbb E\pi(Z)^2}{p^2}-1\right).
$$
Here (N-1)p=(1-1/N)q MUST be retained. Since u^2=2L^3(1+o(1)), the displayed lower bound still diverges at least like exp(L^2/2-L+o(L^2))/u. This exceeds every fixed power of L. Thus global average spectral diffuseness alone cannot justify the stated independent-count variance replacement.

The same failure persists strictly below the 1/L correlation scale: take rho=L^{-2}, N=ceil(exp(L^4)). Again ||A||<tau, while rho u^2/2=L^2(1+o(1)); the variance ratio diverges. In general the scale relevant to a threshold u_k is rho u_k^2, not merely rho L. A cutoff adapted to every k would have to address scales down to 1/log(N/q); simply using its coherent rank bound would reintroduce log N.

These calculations concern deterministic BH GRID counts, not the probability that the largest BH rank equals one. They refute the concrete count-comparison gate, not actual Gaussian BH FDR.

## Other analytic stress tests, with original fractions

Nearly identical pairs: take half the vectors sqrt(1-epsilon^2)e_0+epsilon e_1 and half sqrt(1-epsilon^2)e_0-epsilon e_1. Then A=diag(1-epsilon^2,epsilon^2). If epsilon^2<tau, the coherent projector retains e_0 and the residual raw frame has norm epsilon^2. But after conditioning on the coherent factor the standardized residual directions are +e_1 and -e_1; their normalized frame has norm one. A conditional unit-variance comparison therefore loses epsilon^{-2} if inferred from the raw residual frame. The integrated small-noise effect may still be harmless; no impossibility claim follows.

Regular simplex: for N vertices, correlations -1/(N-1) and A=I/(N-1) on their span. The cutoff calls this diffuse for N-1>L. At a common null threshold, every off-diagonal indicator covariance is nonpositive (the bivariate Gaussian exceedance probability increases in its correlation, as direct differentiation gives its positive density). Thus Var(N^{-1}B)<=p(1-p)/N in this test. Negative correlations do not invalidate the frame decomposition itself; they provide no general conditional-independence theorem for heterogeneous means.

Independent clone blocks of integer sizes n_j retain masses a_j=n_j/N and directions e_j. Exactly A=diag(a_j) and C(p)=sum_j a_j 1{P_j<=p}, where the P_j are independent uniform. Hence Var C(p)=p(1-p)sum_j a_j^2. All blocks with a_j<tau are globally diffuse, including arbitrarily large exact clone blocks. For ordered block p-values P_(j) and cumulative ORIGINAL masses A_j, ordinary BH selects the largest j with P_(j)<=q A_j and rejects all blocks through it; these are the actual non-strict comparisons, including multiplicities. One may not substitute independent per-test counts or a separate threshold q a_j for that common crossing. With equal block sizes this is exactly ordinary BH on the independent block p-values, illustrating why a failure of a concentration proxy need not imply large FDR. Heterogeneous masses can occupy arbitrarily many scales, which the formulas retain.

## Precise surviving gate and next route

The weaker estimate actually needed is still an integrated decomposition/aggregation theorem for E[V/(R vee 1)] with its common largest non-strict BH rank and original null labels: it must charge the rare diffuse bursts and coherent triggers together by O(q sqrt(L)), rather than compare every rare count to an independent count. The equicorrelation example does not refute this weaker payment, and fixed rare-event losses could rescue it. The available directional-entropy bound has an uncontrolled entropy term on general pieces; the central-window bound leaves the shell; conditional iid results do not apply to the normalized correlated residuals above. None supplies the surviving integrated gate, so no executable root plan is warranted.

A substantially different continuation within covariance analysis is rank-adaptive spectral trimming at scales u_k^{-2}, together with a proved ORIGINAL-mass Carleson-type budget across nested rank scales and random correlated backgrounds. Such a budget must be formulated and tested first; it is not established here. It cannot merely sum the coherent ranks or tail-count upper bounds across k. All arbitrary means, negative null means, singular models and q-dependent dimensions of the main target remain required; the zero-mean finite diagnostics only refute the explicitly stronger shortcut.

## Tried

- Search round 2 for gaussian_bh_one_sided_universal_order_upper (slot 3): no candidate written (show idea_27c06facb739 for what was found)
