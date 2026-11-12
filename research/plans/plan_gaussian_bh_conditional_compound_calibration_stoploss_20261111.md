---
type: plan
status: succeeded
title: >-
  Self-contained conditional BH calibration through exact stop-loss
  certification
target_asset: gaussian_bh_conditional_compound_calibration
inspired_by:
  - idea_11e09189bc55
  - idea_32fd49aacc73
adapts: []
tags:
  - gaussian-bh
  - compound-p-values
  - conditional-calibration
  - exact-certificate
proof_digest: 41b81625508394b1e7f89586f259b93b73380ed4f820b57b91c0b7cc5ac1fc13
statement_digest: 72c9382ceb1913470689b87acb600c14e6c36c033da80c5f6d7559dceeaafc01
dependency_digests:
  conditional_pvalue_distributions: 77ce2aa2ed17706abfefbad6343ad90d8354ee3d9f30d452b1c3fc7db92c57ac
  benjamini_hochberg_step_up: 2654feec463fe339f6bebe029e9f1cbff9e970db6ad51faa3b66f632a90eb875
  false_discovery_rate: ce88ab68fe7c28f8baff59d3beb8b2c38cbb031634b8dc2f3cb3cad67a3309d1
verified_proof_digest: 41b81625508394b1e7f89586f259b93b73380ed4f820b57b91c0b7cc5ac1fc13
---

## Goal

Target: [Finite-level conditional compound-p calibration for the actual BH rank](../assets/gaussian_bh_conditional_compound_calibration.md).

Prove the unchanged statement completely inside the target asset. First prove the independent compound-p inequality with constant 2 for arbitrary fixed null labels, then apply it separately to almost every conditional product law. No source theorem is assumed. The two linked ideas supply a mechanism and attribution, not proved premises.

## Plan

1. [x] **First gate: recheck the exact finite certificate and its analytic enclosures.** The permitted checker `research-local/compound_calibration_20261111/certify_stoploss_v2.py` has SHA256 `83ff8cbe29317e51b0b03c90d0dd42de0f95ff5efc15d4b0365ebd6294ac8a7d`. Its independent rerun during planning completed every interval and returned $c_{30}\le188507/100000<19/10$; the accompanying `stoploss_certificate_v2.json` agrees. Reproduce that result after verifying the mathematical enclosures in steps 5--6. The original v1 hit a work cap and supplies no certificate. Embed the complete arithmetic core of v2 (or a smaller complete equivalent checker), its parameters, output constants and rational tail assertion in the final shared asset's proof. A local file hash or JSON assertion alone is insufficient: a collaborator must be able to reproduce the proof without `research-local`. Stop if an interval bound, derivative identity, or finite coverage cannot be justified.

2. [x] **Reduce independent compound validity to actual BH ranks.** For independent $X_1,\ldots,X_N\in[0,1]$ with $\sum_{j\in I_0}\Pr(X_j\le u)\le Nu$ for every $u\in[0,1]$, fix $\alpha\in(0,1)$ and condition on the entire nonnull vector. Let $m=|I_0|$, $A(k)=\#\{j\notin I_0:X_j\le\alpha k/N\}$, and $C(u)=\#\{j\in I_0:X_j\le u\}$. For $0\le i\le m$ set $k_i=\max\{k\in\{0,\ldots,N\}:i+A(k)\ge k\}$ and $u_i=\alpha k_i/N$. Prove $k_i\ge i$ and that $k_i$ is nondecreasing. Let $I=\max(\{0\}\cup\{i\ge1:C(u_i)\ge i\})$. Prove, with largest non-strict BH rank, that the actual counts obey $I=V$ and $R=k_I$. Indeed $R=k_V$ follows from feasibility at $R$ and from contradiction if $k_V>R$; every feasible $i$ makes $k_i$ a qualifying original rank, forcing $R\ge k_i$ and $V\ge i$. Prove separately that the BH rejection count equals its largest qualifying rank, including multiplicities: more rejections than that rank would produce a larger qualifying rank. Cover $m=0$, $R=0$, degenerate coordinates and ties. No alternate rejection rule or optimized selector is substituted.

3. [x] **Prove the reverse-hazard bound from product association.** For $i\ge1$ define $a_i=\Pr(I=i\mid I\le i)$ when the conditioning event has positive probability and set $a_i=0$ otherwise. Then $\Pr(I=i)=a_i\prod_{j>i}(1-a_j)$, also when an earlier cumulative probability vanishes. Prove elementary product association: for one coordinate, covariance of two bounded increasing functions equals half the expectation of the product of their increments under independent copies and is nonnegative; induction on the number of independent coordinates follows by conditioning and the covariance decomposition. The same argument gives opposite signs for an increasing and a decreasing function. In the null p-values, $\{I\le i\}$ is increasing while $E_i=\{C(u_i)\ge i\}$ is decreasing, and $E_i\cap\{I\le i\}=\{I=i\}$. Hence $a_i\le\Pr(E_i)$. Conditional on the fixed alternatives, $C(u_i)$ is an independent Bernoulli sum of mean at most $t_i=\alpha k_i>0$.

4. [x] **Establish only the needed Poisson stop-loss comparison.** For convex functions on the nonnegative integers, prove $\phi(k)\ge\phi(0)+k[\phi(1)-\phi(0)]$ for every integer $k\ge0$, so $\operatorname{Bernoulli}(p)\le_{cx}\operatorname{Poisson}(p)$. Conditioning on independent added summands preserves this inequality. Prove by convolution that independent Poisson variables sum to a Poisson variable. For increasing convex $\phi$, an independent Poisson increment upgrades a Bernoulli sum of mean $\lambda\le t$ to Poisson$(t)$. Apply this only to $\phi_i(x)=(x-i+1)_+$, whose expectation is finite, to obtain $a_i\le\Pr(C(u_i)\ge i)\le\beta_i(t_i)$ with $\beta_i(t)=\mathbb E[(\operatorname{Poisson}(t)-i+1)_+]$. Derive $\beta_1(t)=t$, monotonicity, and for $i\ge2$ the exact formula $\beta_i(t)=t-i+1+e^{-t}\sum_{k=0}^{i-2}(i-1-k)t^k/k!$. No ordinary Poisson tail stochastic domination is claimed.

5. [x] **Prove the dynamic budget and the certificate's derivative bounds.** After steps 2--4 the conditional FDR divided by $\alpha$ is $H_m=\sum_{i=1}^m(i/t_i)a_i\prod_{j>i}(1-a_j)$. Its prefix recursion is $H_i=(1-a_i)H_{i-1}+(i/t_i)a_i$. Start with $H_1\le1$. For any established bound $c\ge1$, infer $H_i\le c+\sup_{0<t<i/c}(i/t-c)\beta_i(t)$; if the coefficient is nonpositive its contribution can be dropped, and $a_i\le\beta_i(t_i)$ is used only for a positive coefficient. Prove for $g_i(t)=(i/t-c)\beta_i(t)$ on $0<t\le i/c$ that
$$
g_i'(t)=\frac{i(i-1)}{t^2}\Pr(\operatorname{Poisson}(t)\ge i)-c\Pr(\operatorname{Poisson}(t)\ge i-1).
$$
The first term is between 0 and 1, by the second factorial moment, so $-c\le g_i'\le1$ and $|g_i'|\le c$. At 0 use continuity with $g_i(0)=0$ for $i\ge2$. Prove $\beta_i(t)\le t^i/i!$ from $(k-i+1)_+\le\binom{k}{i}$. Thus each midpoint interval has an upper enclosure from its midpoint upper value plus $c(h-l)/2$, and also the product enclosure $(i/l-c)_+\beta_i(h)$ for $l>0$, or $i h^{i-1}/i!$ for $l=0$.

6. [x] **Audit and embed the exact finite arithmetic certificate.** Explain scaled-integer outward rounding for every positive Taylor term of $e^x$ with scale $10^{40}$ and 140 terms. Bound the omitted positive tail by the first omitted upper term times $1/[1-x/142]$ (all evaluated $x<142$), then invert the positive lower/upper exponential bounds to enclose $e^{-x}$. Evaluate the positive polynomial in step 4 by outward-rounded terms; adding its exactly rational offset preserves the enclosure despite cancellation. The branch-and-bound heap initially covers $[0,i/c]$; replacing a leaf by its two halves preserves complete coverage, and the maximum leaf upper bound encloses the supremum. Terminate only after that maximum is at most the largest sampled lower bound plus $1/10000$; a work-cap exception is failure. Round each resulting $c+\sup g_i$ upward to a multiple of $10^{-6}$. Check all 29 stages $i=2,\ldots,30$, ending at $188507/100000$. Include executable arithmetic and the resulting prefix constants in the asset, with explicit assertions for the prefix bound and tail; samples supply lower bounds for termination only, never the proof upper bound.

7. [x] **Close the infinite tail analytically.** Reset the upper constant after stage 30 to $C=19/10$. Derive Poisson Chernoff directly from its exponential generating function and Markov's inequality: for $k>t$, $\Pr(\operatorname{Poisson}(t)\ge k)\le h_k(t)=e^{-t}(et/k)^k$. Prove $h_{k+1}(t)/h_k(t)\le t/k$ using $e\le(1+1/k)^{k+1}$, so $\beta_i(t)=\sum_{k=i}^\infty\Pr(\operatorname{Poisson}(t)\ge k)\le h_i(t)/(1-t/i)$ whenever $t<i$. For $c\ge C$ and $0<t<i/c$, show $(i/t-c)\beta_i(t)\le(i/t)h_i(t)\le C r^i$, where $r=e^{9/19}/C$. The last maximization uses that $t^{i-1}e^{-t}$ is increasing for $t\le i/C\le i-1$, valid for $i\ge31$. Certify $e^{9/19}<323/200$ by the same rational Taylor enclosure, hence $r<17/20$. Finally check exactly
$$
C+C\frac{(17/20)^{31}}{1-17/20}=
\frac{63849773397438169274766942332299886688227}{32212254720000000000000000000000000000000}<2.
$$
Induct the budget for every finite $m$, including $m\le30$, then integrate out the alternatives. This proves independent compound-p BH FDR $\le\min\{1,2\alpha\}$.

8. [x] **Apply the bound without changing the original ranks or labels.** Fix a conditional product law at a good $z$ and let $K=K_q(z)$. If $K=\infty$ or $qK\ge1$, the target bound follows from FDP $\le1$. Otherwise $\alpha=qK<1$ and transform every coordinate by $X_j=KP_j$ on $\{P_j\le q\}$ and $X_j=1$ on $\{P_j>q\}$. Show independence is preserved. For $0\le u\le\alpha$ the summed null CDF is at most $Nu$ by the envelope at $u/K$; at $u=0$ use right continuity and finite $K$ to rule out null mass at zero. For $\alpha<u<1$ it is constant at its value at $\alpha$, at most $N\alpha\le Nu$, and at $u=1$ it is $|I_0|\le N$. For every rank $k$, $X_j\le\alpha k/N$ if and only if $P_j\le qk/N$. Therefore largest qualifying ranks, complete rejection sets, ties, original null labels and FDP agree exactly. Apply step 7 at level $\alpha$.

9. [x] **Resolve conditional measurability and integrate.** For $0<t<q$, approximate $t$ from above by rational thresholds below $q$ and use right continuity of each conditional CDF to show the envelope equals its supremum over rational thresholds and the endpoint $q$. This is a measurable extended-real function of $z$. Choose a common full-measure set for the regular product kernels and apply the independent argument pointwise there; no uniform-in-$z$ theorem or attainment of the supremum is needed. The bounded Borel BH FDP has its conditional expectation represented by the product kernel, including degenerate coordinates. Obtain the exact almost-sure bound and then the asserted FDR inequality by the tower property. Conclude only this finite calibration lemma, without a Gaussian envelope or unrestricted-main-theorem claim.

## Verification

The first executable gate is the exact finite coverage certificate, already rerun successfully during planning; execution must also justify its analytic enclosures and embed its arithmetic for shared reproducibility. Independently inspect the rank identities and opposite-monotonicity conditional hazard inequality, since substituting an arbitrary selector or treating ordinary Poisson tails as a stochastic upper bound would break the argument. Check $N=1$, empty nulls, all nulls, deterministic alternatives, tied endpoints, zero cumulative reverse-hazard probabilities, $K=1$, $K=\infty$, and $qK\ge1$ directly against the formulas. All scientific estimates used are derived inline, and the final conditional inequality is for the actual original BH FDP. The proof remains draft until the native independent verification stage.

## Assumed definitions

Only the approved definitions already attached to the target are used: [conditional p-value distributions and independence](../definitions/conditional_pvalue_distributions.md), [ordinary BH](../definitions/benjamini_hochberg_step_up.md), and [FDP/FDR](../definitions/false_discovery_rate.md). No unproved draft definition, draft asset, or additional theorem dependency is assumed. Elementary association, convex stop-loss comparison, Poisson generating identities, exponential bounds, and every rank identity are proved in this asset rather than cited as black boxes.

## Source provenance and library check

[The concrete mechanism](../ideas/idea_11e09189bc55.md) and [the source lead](../ideas/idea_32fd49aacc73.md) motivate the route. Barber and Samworth, arXiv:2507.21465v2, Theorem 1 and Appendix A.2, are attribution only; no imported or approved theorem node exists, no paper ID is asserted, and the source's sharper constant is unused. Native library searches for compound-p calibration, Bernoulli/Poisson stop-loss, product association and reverse hazards found no applicable proved result. The nearest surfaced [positive Gaussian Simes result](../library/chi2024_negative_dependence/assets/lib_chi2024_positive_gaussian_simes.md) has incompatible hypotheses and no exposed proof section; it is not adapted or used. Thus `adapts` is empty and there are no failed plans for this target to contrast.


## Outcome

Succeeded: the complete proof is in `research/assets/gaussian_bh_conditional_compound_calibration.md`, under `## Proof`; the frozen statement is byte-identical and the asset remains draft. The proof establishes the exact original BH rank and null counts, reverse hazards from product association, the Bernoulli-to-Poisson increasing-convex stop-loss comparison, all dynamic-budget enclosures, the full standalone exact-arithmetic checker with 29 asserted prefix constants and coverage counts, the analytic infinite tail, and conditional rescaling and measurability. The standalone checker was extracted and rerun successfully, returning `188507/100000` and total upper bound `63849773397438169274766942332299886688227/32212254720000000000000000000000000000000 < 2`. The permitted v2 source hash was verified and its original checker rerun independently of the JSON record.

Only the three attached approved definitions are assumed; no draft definition or theorem dependency is used. A notation audit against those definitions and the configured `macros.tex` and `notations.tex` found no undefined local symbols or conflicting conventions. The proof remains subject to the native independent verification stage. No Gaussian envelope order estimate, unrestricted main theorem, or approval is claimed.


## Verdict

confirmed

Independently checked the statement and proof without consulting the plan reasoning. The largest-rank identities preserve all BH ties and the original null labels, including zero/empty and degenerate cases. Product association has the correct opposite-monotonicity direction; the reverse-hazard recursion handles zero denominators. The Bernoulli-to-Poisson argument proves the required increasing-convex stop-loss comparison, rather than an unsupported Poisson-tail domination.

Checked the derivative/Lipschitz and monotone-product bounds over every real interval, all outward-rounded rational enclosures, and the analytic infinite-tail budget. Independently executed the embedded checker directly from the asset: every prefix, evaluation-count, exponential and final rational assertion passed, printing the stated CERTIFIED result. The conditional rescaling preserves every qualifying rank and rejection, and the rational-threshold envelope, zero mass, cap/infinite cases and conditional-kernel measurability are valid. No unapproved source result is needed.

Verified asset SHA256: `3a29a8472c5552f3957a18014d401c637d754e44cebdfa7eaa225d5c05c469aa`. This confirms only the finite conditional calibration lemma, with no Gaussian envelope/order conclusion.
