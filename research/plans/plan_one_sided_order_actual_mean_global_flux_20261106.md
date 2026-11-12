---
type: plan
title: Universal one-sided order through actual-mean aggregate rank flux
status: failed
target_asset: gaussian_bh_one_sided_universal_order_upper
inspired_by:
  - idea_7e2b1eaa2f33
  - idea_bb18a2b30414
  - idea_f2adba6d4a2d
tags:
  - gaussian_bh
  - universal_order
  - conditional_regression
  - actual_null_means
---

## Goal

Target: [Universal order upper bound for one-sided Gaussian BH](../assets/gaussian_bh_one_sided_universal_order_upper.md).

Prove the target as stated: there are finite universal constants $C_1>0$ and $q_{0,1}>0$ such that $F_1(q)\le C_1q\sqrt{\log(1/q)}$ for every $0<q\le q_{0,1}$. Work with every finite $N$, every mean vector, and every unit-diagonal PSD covariance, including singular matrices. The true-null set is exactly $I_0=\{i:\theta_i\le0\}$, ordinary BH uses its largest qualifying rank, and all model parameters and the null proportion may vary with $q$. Neither constants nor their valid interval may depend on dimension, rank, means, covariance, factor count, or directions. This plan does not optimize constants or use the old sharp conjecture as an assumption.

The [actual-mean route](../ideas/idea_7e2b1eaa2f33.md) is a proposal, not a verified lemma. Its aggregate flux estimate below is an obligation to prove, not a premise. The [independently checked auxiliary obstruction](../ideas/idea_bb18a2b30414.md) rules out the separately centered positive-flux gate in [the earlier proposal](../ideas/idea_f2adba6d4a2d.md); it does not refute this target. Preserve all three records.

Library checks at planning time returned no matches for Gaussian BH universal bounds or Gaussian rank-flux bounded-variation bounds. No library result or unpublished supporting claim is being used as a black box.

## Plan

1. [x] **Establish the deterministic force-zero formula with ordinary BH and ties.** For every deterministic $p\in[0,1]^N$, prove $R_q(p)=\widehat k_q(p)$, including multiplicities and non-strict thresholds. Let $p^{(i)}$ replace only $p_i$ by zero and put $R_i=\widehat k_q(p^{(i)})\ge1$. Prove exactly
   $$
   \frac{\mathbf1\{i\in\mathcal R_q(p)\}}{R_q(p)\vee1}
   =\frac{\mathbf1\{p_i\le qR_i/N\}}{R_i}.
   $$
   Show both directions using the maximal qualifying rank, including $R_q=0$, $N=1$, and simultaneous ties. Do not replace BH by its first qualifying rank. Save this proof immediately in Progress before proceeding.

2. [x] **Construct the actual conditional rank curves for the full Gaussian model.** Write $X=T-\theta$ and, separately for each $i\in I_0$, put $\rho^{(i)}=\Sigma_{\cdot i}$ and $W^{(i)}=X-\rho^{(i)}X_i$. Prove that $X_i$ is standard normal and independent of the jointly Gaussian vector $W^{(i)}$, whose covariance is $\Sigma-\rho^{(i)}(\rho^{(i)})^{\mathsf T}$; this requires neither an inverse nor a density for $\Sigma$. The residual coordinates need not be mutually independent. Conditional on $W^{(i)}=w$, retain every original mean and define $R_i^w(x)$ by the p-values $0$ at $i$ and $\bar\Phi(\theta_j+\rho^{(i)}_j x+w_j)$ at $j\ne i$. For $0<q<1/2$ set
   $$
   U=\bar\Phi^{-1}(q),\quad u_k=\bar\Phi^{-1}(qk/N),\quad
   \tau_i^w(x)=qR_i^w(x)/N\in[q/N,q].
   $$
   Prove that the curve is constant off a finite set contained in the affine critical points $(u_k-\theta_j-w_j)/\rho^{(i)}_j$ with $\rho^{(i)}_j\ne0$. Handle zero slopes, coordinates identically at a critical level, coincident crossings, and isolated rank values at a crossing. Define jumps using one-sided limits; changing finitely many point values does not affect the conditional integral against $X_i$. Establish measurability in $w$, including the jump sums, under singular residual laws. Do not assume arbitrary conditional rank maps satisfy the later gate: these curves must come from one common admissible Gaussian model. Save each completed substep in Progress.

3. [x] **Prove the actual-mean bounded-variation identity.** For $i\in I_0$ and fixed $w$ define
   $$
   g_i(x)=\frac{\bar\Phi(x)}{\bar\Phi(x+\theta_i)},\qquad
   h_i^w(x)=\min\left\{\frac{\bar\Phi(x)}{\tau_i^w(x)},g_i(x)\right\}.
   $$
   Prove by explicit normal-tail calculus that $0<g_i\le1$, $g_i'\le0$ for $\theta_i\le0$, and that the $	heta_i=0$ case is included. Prove the endpoint limits $h_i^w(-\infty)=1$, $h_i^w(+\infty)=0$ using the fixed-$N$ bounds on $\tau_i^w$. Split rank intervals further at $\bar\Phi(x+\theta_i)=\tau_i^w(x)$; these switches are continuous for $h_i^w$. With $\mathcal B_i(w)$ the finite set of rank crossings, put
   $$
   J_i(w)=\sum_{b\in\mathcal B_i(w)}[h_i^w(b+)-h_i^w(b-)],\quad
   P_i(w)=\sum_{b\in\mathcal B_i(w)}[h_i^w(b+)-h_i^w(b-)]_+,
   $$
   $$
   D_i(w)=-\int_{\{x:\bar\Phi(x+\theta_i)>\tau_i^w(x)\}}g_i'(x)\,dx.
   $$
   Derive, with the sign of every jump and drift checked,
   $$
   I_i(w):=\int_{\mathbb R}\frac{\phi(x)}{\tau_i^w(x)}
   \mathbf1\{\bar\Phi(x+\theta_i)\le\tau_i^w(x)\}\,dx
   =1+J_i(w)-D_i(w)\le1+P_i(w),\qquad 0\le D_i(w)\le1.
   $$
   Here $\phi$ is the standard normal density and $[a]_+=\max\{a,0\}$. Justify truncation limits, integrability, finite-point ties, and expectation over every singular residual law. Check $N=1$, centered nulls, and strictly negative nulls directly. As a diagnostic, verify that the auxiliary object's former harmonic jumps vanish for this $h_i^w$ when the actual null cannot be rejected on either side; this diagnostic alone proves no uniform estimate. Save full proofs, not a sketch, in Progress.

4. [ ] **First substantive analytic gate: prove a global Gaussian flux budget.** First combine steps 1–3 without dropping the actual means:
   $$
   \operatorname{FDR}
   =\frac qN\sum_{i\in I_0}\mathbb E I_i(W^{(i)})
   \le q\pi_0+\frac qN\sum_{i\in I_0}\mathbb E P_i(W^{(i)}),\qquad \pi_0=|I_0|/N.
   $$
   Then prove the following precise proposition **(G-actual)**: there exist $C_*<\infty$ and $q_*\in(0,1/2)$, independent of all model parameters, such that for every admissible finite Gaussian model and every $0<q\le q_*$,
   $$
   \sum_{i\in I_0}\mathbb E P_i(W^{(i)})\le C_*N(1+U).
   $$
   Attempt the following checkable attack, recording each genuine inequality and its scope: (a) charge a positive aggregate rank drop to the affine coordinates crossing a BH critical level in the direction that removes a rejection, treating simultaneous crossings without counting the same jump twice; (b) integrate these charges under their actual Gaussian regression laws, with the correct crossing Jacobians, keeping the actual-null truncation in $h_i^w$; (c) sum using the *global* active-null and BH-rank budget from the same model to obtain a finite numerical upper bound of the displayed form. Handle zero slopes and deterministic residual coordinates separately, rather than invoking a nonsingular coarea density for the whole model. The needed charging and averaging inequalities themselves must be proved. A restatement of (G-actual), an arbitrary pointwise bound for each conditional map, or a separately centered-null comparison is not a proof. The estimate is on the sum over true nulls; do not silently strengthen it to a dimension-free bound for each $i$.

   **Failure condition:** stop at the first essential unproved charging or averaging inequality in this step. If the only justified estimate retains $\log N$, rank, factor number, direction entropy, a restricted covariance class, or an uncontrolled exceptional event, record its exact formula and the missing bound, and report the plan failed. Do not carry (G-actual) as an assumed lemma or proceed to claim the target. A counterexample to (G-actual) is only an auxiliary candidate unless its *actual original* FDR is independently shown to violate the target with all original hypotheses; keep those two conclusions separate.

5. [ ] **Only if (G-actual) is proved, finish the exact uniform target with fixed constant loss.** For $I_0=\varnothing$ give the zero-FDR case directly. Otherwise obtain $\operatorname{FDR}\le q\pi_0+C_*q(1+U)$. Prove the elementary bound $U\le\sqrt{2\log(1/q)}$ on the chosen small-$q$ interval. Choose $q_{0,1}=\min\{q_*,e^{-1}\}$ and, for example, $C_1=1+(1+\sqrt2)C_*$, verifying the algebra without optimizing it. These constants must be the same for every finite $N,\theta,\Sigma$; take the original supremum at each $q$ only after proving that uniform assertion. No interchange of a dimension limit is permitted. Fill the target's Proof only if every gate is established.

6. [ ] **Request a fresh independent native proof verification only after a complete proof.** The verifier must not have derived or executed these steps. They must reconstruct the force-zero identity, the weighted BV formula and its signs, every estimate in (G-actual), singular and tied cases, actual negative-null weights, all dependencies, the universal constants and interval, and the exact supremum quantifiers. Agreement, simulations, or absence of a main-target counterexample cannot establish the target. An unresolved gate leaves the theorem draft.

## Verification

The execution must give the exact full-model theorem, not a factor, block, population, fixed-rank, or fixed-dimension substitute. The only proposed reduction of the uniformity problem is (G-actual), which remains to be proved. Check that $W^{(i)}$ is independent of $X_i$ but may have dependent coordinates; all means, including every negative true-null mean, remain those of the original model. Check largest-rank BH, non-strict inequalities, coincident and isolated crossings, zero regression slopes, rank-one and other singular covariance matrices, $N=1$, no true nulls, and $	heta_i=0$ endpoints. Each fixed-$N$ integration must be valid before a universal estimate is claimed. In particular, fixed-$N$ integrability is not an estimate uniform in $N$.

For (G-actual), require explicit inequalities explaining where joint Gaussianity, PSD geometry, and the common-model null/rank budget remove complexity dependence. Check all constants and every exceptional-set cost. No unproved library result, counterfactual mean reduction, conditional independence of residual coordinates, or native approval of an unrelated restricted theorem may fill this gate. Short Python calculations may test a proposed equality or candidate, but never certify a universal estimate; heavy local searches are excluded.

If any step fails, preserve the completed mathematical substeps in this plan's Progress, identify the first failed or unproved proposition and the exact strongest bound reached, and distinguish a route obstruction from a main-target refutation. The executor must write each finished substep promptly, with each edit at most about 6,000 tokens, and return a short status of at most five lines. A partial execution continues from its disk-backed Progress; it is not reported as proved.

## Assumed definitions

All definitions used here are approved: [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md), [Gaussian test p-values and true nulls](../definitions/gaussian_test_pvalues.md), [ordinary Benjamini-Hochberg step-up procedure](../definitions/benjamini_hochberg_step_up.md), [false discovery rate](../definitions/false_discovery_rate.md), and [uniform worst-case Gaussian BH false discovery rate](../definitions/gaussian_worst_case_bh_fdr.md). There are no assumed draft definitions, unproved dependencies, or library black boxes. The normal-tail calculus and every intermediate assertion above must be proved locally. In particular (G-actual) is not an assumed definition or dependency.

## Difference from failed plans

- [The earlier one-sided free-center pooled-shell plan](plan_gaussian_bh_one_sided_free_center_pooled_shell_20261106.md): the researcher's handoff identifies its unresolved pooled-shell budget scaling at step 5c(v), with a further dimension-uniform decoupling obstruction outside block models. This plan instead conditions directly on each actual Gaussian null coordinate and its exact residual vector, with no block approximation or factor dimension. It seeks a global $O(N(1+U))$ flux estimate with fixed constants; it does not seek a sharp constant or an $o(qU)$ decoupling error. This is a different proposed mechanism, not evidence that the old obstruction is solved.
- [The separately centered flux proposal](../ideas/idea_f2adba6d4a2d.md): its stronger positive-flux gate is contradicted by the independently checked auxiliary family in [the negative-null risk](../ideas/idea_bb18a2b30414.md), while that family's actual FDR is below $q$. Here $g_i$ and $h_i^w$ retain the original negative means and the nonrejection drift. The old proposal and its failure evidence remain unchanged; avoidance of its ghost jumps does not establish (G-actual).

## Progress

### Step 1: deterministic force-zero identity (proved in this execution; not independently verified)

Fix a positive integer $N$, $0<q<1$, and any deterministic $p\in[0,1]^N$. Write $r=\widehat k_q(p)$. If $r>0$, the number $m$ of p-values at most $qr/N$ is at least $r$. If $m>r$, then $p_{(m)}\le qr/N\le qm/N$, so $m$ would be a larger qualifying rank, a contradiction. Thus the rejection count is exactly $r$. If $r=0$, its defined rejection set is empty, so again $R_q(p)=r$. This argument includes all ties, zeros and non-strict threshold equalities.

Fix $i$ and let $s=\widehat k_q(p^{(i)})$. Its zero p-value ensures $s\ge1$. Lowering one p-value cannot increase an order statistic, so $s\ge r$. Suppose first that $i$ is rejected for $p$. Then $r>0$ and $p_i\le qr/N$. For every $k>r$, both $p_i$ and its replacement zero are at most $qk/N$. Their replacement consequently leaves the count at that threshold unchanged. Rank $k$ fails for $p$, so it still fails for $p^{(i)}$. Hence $s=r$, and $p_i\le qs/N$.

Conversely, if $p_i\le qs/N$, replacing zero by $p_i$ leaves the count at threshold $qs/N$ unchanged. That count for $p^{(i)}$ is at least $s$, so $s$ also qualifies for $p$. Thus $r\ge s$. Together with $s\ge r$, this gives $r=s\ge1$ and $i$ is rejected. We have proved equivalence of the two indicator events, and equality of the positive denominators on that event. Therefore
$$
\frac{\mathbf1\{i\in\mathcal R_q(p)\}}{R_q(p)\vee1}
=\frac{\mathbf1\{p_i\le qR_i/N\}}{R_i},\qquad R_i=s\ge1.
$$
Off the common event both sides vanish. For $N=1$, $R_i=1$ and this reduces directly to $\mathbf1\{p_i\le q\}$. No distributional or generic-position assumption has been used.

### Step 2: singular regression, finite rank curves and measurable jumps (proved in this execution; not independently verified)

Fix a model, $i\in I_0$, and abbreviate $\rho=\Sigma_{\cdot i}$, $W=X-\rho X_i$. Because $\Sigma_{ii}=1$, $X_i$ is standard normal, $W_i=0$, $\operatorname{Cov}(W,X_i)=0$, and
$$
\operatorname{Cov}(W)=C:=\Sigma-\rho\rho^{\mathsf T}\succeq0.
$$
The pair $(X_i,W)$ is jointly Gaussian as a linear transform of $X$. For every real $t$ and $v\in\mathbb R^N$ its joint characteristic function is $\exp\{-(t^2+v^{\mathsf T}Cv)/2\}$, which factors into its marginal characteristic functions. Hence $X_i$ and $W$ are independent even when $C$ or $\Sigma$ is singular. This proves the product-law integration used below without a conditional Lebesgue density or a matrix inverse. It does not assert independence between residual coordinates. The two-by-two PSD minors also give $|\rho_j|\le1$.

For a fixed residual vector $w$, the other statistics are exactly $\theta_j+\rho_jx+w_j$, with every original mean retained. Force only p-value $i$ to zero and compute the largest qualifying rank $R_i^w(x)$. For each $j\ne i$ and $k\in[N]$, qualification of that coordinate at threshold $qk/N$ is the affine inequality $\theta_j+\rho_jx+w_j\ge u_k$. If $\rho_j=0$, it is constant in $x$, including when equality holds identically. Otherwise it can change only at
$$
b_{jk}(w)=(u_k-\theta_j-w_j)/\rho_j.
$$
There are at most $N(N-1)$ such labelled points. On every component of their complement, all these comparisons, all threshold counts and therefore the largest qualifying rank are constant. Coincident points are included just once in the set $\mathcal B_i(w)$; one-sided limits exist. A special value at a point, including a rank created only by simultaneous equalities, affects neither one-sided limit nor integration against the continuous law of $X_i$. Zero slopes and equalities on whole intervals have already been retained in their constant comparisons. Always $1\le R_i^w(x)\le N$, so $q/N\le\tau_i^w(x)\le q$. For $N=1$ there are no points and the rank is identically one.

For completeness these constructions are measurable under every residual law. Each threshold count is a finite sum of indicators of closed affine inequalities in $(x,w)$, and $R_i^w(x)$ is a finite maximum of qualifying ranks, hence Borel. Each labelled $b_{jk}(w)$ is affine and continuous. List these labels in a fixed order and keep a label only when its value differs from all preceding ones; that is a Borel condition and counts each distinct crossing exactly once. The one-sided value of $R$ or any of the subsequently defined $h$ at $b_{jk}(w)$ is the limit along $b_{jk}(w)\pm1/n$, because the crossing set is finite for each $w$. It is thus a pointwise limit of Borel functions. Finite sums of these one-sided differences, their positive parts and the Borel de-duplication indicators are Borel. No absolute continuity of the law of $W$ is needed. The integration and drift terms below are measurable by integration of Borel integrands against Lebesgue measure, using nonnegative functions where Tonelli is applied.

### Step 3: actual-mean BV identity, including its drift (proved in this execution; not independently verified)

Abbreviate $S(x)=\bar\Phi(x)$ and $\theta=\theta_i\le0$. The normal density is $\phi(x)=(2\pi)^{-1/2}e^{-x^2/2}$. Its hazard $\lambda(x)=\phi(x)/S(x)$ satisfies
$$
\lambda'(x)=\lambda(x)(\lambda(x)-x)>0.
$$
Indeed for $x\le0$ positivity of $\lambda$ gives $\lambda(x)>x$. For $x>0$, integration of $t\phi(t)$ gives the strict bound $S(x)<x^{-1}\int_x^\infty t\phi(t)\,dt=\phi(x)/x$, again $\lambda(x)>x$. Differentiating the smooth positive ratio $g(x)=S(x)/S(x+\theta)$ consequently gives
$$
0<g(x)\le1,\qquad
g'(x)=g(x)\{\lambda(x+\theta)-\lambda(x)\}\le0.
$$
For $\theta=0$, $g\equiv1$ and $g'\equiv0$. In general $g(-\infty)=1$, and its monotonicity and bounds show $\int_{\mathbb R}-g'(x)\,dx\le1$ (by the fundamental theorem on finite intervals and monotone convergence).

Fix $w$. On a component where the rank is constant, write $\tau=qr/N$. Define $h=\min\{S(x)/\tau,g(x)\}$. If $S(x+\theta)<\tau$ (the actual-null rejection region), then $h=S(x)/\tau$ and $h'=-\phi(x)/\tau$. If $S(x+\theta)>\tau$, then $h=g$ and $h'=g'$. The sole possible equality switch on such a component is continuous, because both formulas agree there. There are only finitely many rank components and equality switches. At rank crossings use only the two one-sided limits; an isolated rank value is immaterial for every integral.

For sufficiently negative $x$, $S(x+\theta)>q\ge\tau_i^w(x)$, so $h_i^w(x)=g(x)\to1$. At the other endpoint, $0\le h_i^w(x)\le (N/q)S(x)\to0$. Its absolutely continuous derivative on the complementary intervals is integrable: the rejecting contribution is at most $N/q$, and the nonrejecting contribution in absolute value is at most $\int -g'\le1$. There are at most $N(N-1)$ rank crossing points, with jump magnitudes at most one. Thus $h_i^w$ has finite total variation after its immaterial point values are removed.

Apply the fundamental theorem on each interval cut by the crossings and equality switches, first with finite endpoints and then send them to infinity. Summing the intervals leaves the signed rank jumps $J_i(w)$; equality switches have no jumps. The endpoint identity is
$$
-1=h_i^w(+\infty)-h_i^w(-\infty)
=-I_i(w)-D_i(w)+J_i(w).
$$
Consequently
$$
I_i(w)=1+J_i(w)-D_i(w)\le1+P_i(w),\qquad
0\le D_i(w)\le1.
$$
Every conditional integral is finite, $0\le I_i(w)\le N/q$, and $|J_i(w)|\le P_i(w)+\sum[-\Delta h_i^w]_+\le N(N-1)$. The weaker separate bounds $P_i(w)\le N(N-1)$ and $D_i(w)\le1$ suffice for integrability under any residual law. These are fixed-$N$ bounds only. Measurability was established in Step 2, and the nonnegative Borel integrands defining $I_i,D_i$ allow Tonelli. Taking expectations therefore preserves the identity under singular residual laws, including point masses; no density for $W$ or limit in dimension has entered.

For $N=1$ the rank is constant, $J_i=P_i=0$. Put $b=u_1-\theta$. Directly $I_i=S(b)/q$ and $D_i=-\int_{-\infty}^b g'(x)\,dx=1-g(b)=1-S(b)/q$, so the identity agrees exactly. When $\theta=0$, this is $I_i=1,D_i=0$; strictly negative means give $I_i<1$. The same derivative and endpoint arguments apply to every $\theta\le0$ in larger models without replacing it by zero.

For the specific auxiliary object in [the negative-null centering obstruction](../ideas/idea_bb18a2b30414.md), every former harmonic rank drop occurs at $a_k\le a_2$, with actual null statistic $a_k-B<0$ because $B=3a_2>0$. Thus its actual p-value exceeds $1/2>q\ge\tau_i^w$ on both neighboring sides. On both sides $h_i^w=g_i$, so the former positive jump is zero. This checks only that this particular obstruction is avoided; it is not evidence for (G-actual).

### Step 4 prelude: definitions and the exact FDR normalization (proved in this execution; gate unresolved)

To make the preceding calculation self-contained, its quantities are explicitly
$$
I_i(w)=\int_{\mathbb R}\frac{\phi(x)}{\tau_i^w(x)}
\mathbf1\{S(x+\theta_i)\le\tau_i^w(x)\}\,dx,
$$
$$
J_i(w)=\sum_{b\in\mathcal B_i(w)}\Delta h_i^w(b),\qquad
P_i(w)=\sum_{b\in\mathcal B_i(w)}[\Delta h_i^w(b)]_+,
\qquad \Delta h_i^w(b)=h_i^w(b+)-h_i^w(b-),
$$
$$
D_i(w)=-\int_{\{x:S(x+\theta_i)>\tau_i^w(x)\}}g_i'(x)\,dx.
$$
The finite set $\mathcal B_i(w)$ consists of the distinct labelled critical points from Step 2; points with no rank jump contribute zero. All expectations in what follows use the actual residual law $W^{(i)}=X-\Sigma_{\cdot i}X_i$ in the one common original Gaussian model, not independently selected conditional maps.

Apply Step 1 to each true null, write $R_i=R_i^{W^{(i)}}(X_i)$ and $p_i=S(X_i+\theta_i)$, and use $1/R_i=(q/N)/\tau_i^{W^{(i)}}(X_i)$. Independence in Step 2 and Tonelli give exactly
$$
\operatorname{FDR}
=\frac qN\sum_{i\in I_0}\mathbb E I_i(W^{(i)})
=q\pi_0+\frac qN\sum_{i\in I_0}\mathbb E\{J_i(W^{(i)})-D_i(W^{(i)})\}
\le q\pi_0+\frac qN\sum_{i\in I_0}\mathbb E P_i(W^{(i)}).
$$
Each summand is integrable by the fixed-$N$ bounds of Step 3; the finite sum causes no convergence issue. For $I_0=\varnothing$ both sums and FDR are zero. This establishes the normalization and reduction, but does not establish any bound uniform in $N$ for the final positive-flux sum.

### Step 4(a): exact rank-drop cost and a cascade diagnostic

For a rank drop from $r$ to $\ell<r$ at $b$, put $s=S(b)$, $a=S(b+\theta_i)$ and $t_k=qk/N$. Since $h_i^w(b\pm)=s/\max\{t_{R_i^w(b\pm)},a\}$, elementary integration gives the exact, nonnegative cost
$$
\Delta h_i^w(b)
=s\left\{\frac1{\max\{t_\ell,a\}}-\frac1{\max\{t_r,a\}}\right\}
=s\int_{t_\ell}^{t_r}\frac{\mathbf1\{t>a\}}{t^2}\,dt.
$$
This includes cases where either endpoint saturates, since $t\mapsto1/\max\{t,a\}$ is continuous and has derivative $-\mathbf1\{t>a\}/t^2$ almost everywhere. A rank increase has the opposite sign; equal one-sided ranks give zero. In particular a drop cannot be replaced by a cost for a unit change in rank.

Here is a concrete diagnostic for that issue, also independently checked by the fresh agent `audit_single_crossing_cascade` as relayed by the root driver. Fix $N=4M$, $0<q<1/2$, let $b=S^{-1}(q/2)$, $U=S^{-1}(q)$ and $v=S^{-1}(q(1-1/(2N)))>U$. Take $M$ centered true null statistics $Z$, one alternative $b+U-Z$, and $3M-1$ alternatives $b+v-Z$. All alternative means are positive, and the unit-diagonal covariance is the PSD rank-one matrix from the signs of the shared standard normal $Z$.

For every forced true null, just to the left of $x=b$ all p-values are below $q$, so $R_i=N$, and at equality $N$ still qualifies. Just to the right the distinguished alternative has p-value above $q$. Every other alternative has p-value above $q(N-1)/N$, so it cannot count at any rank at most $N-1$. At most $M$ nulls could count; at ranks at most $M$ their p-values are near $q/2>qM/N=q/4$, so only the forced zero counts. Hence the right-hand rank is one: a single critical crossing causes $N\to1$. The actual-mean weight jumps from $1/2$ to one for each of $M$ true nulls, a total of $M/2$. This invalidates a unit-change or local $O(1/N)$ charge at that crossing, but not (G-actual), whose allowed total is of order $N(1+U)$. Residuals here are zero; no extra normal density factor may be multiplied into these jump masses.

Its actual original FDR is $3q/8$: on $[U,b]$ the rejection rank is $N$ and FDP is $1/4$, contributing $(q-q/2)/4=q/8$; on $(b,S^{-1}(q/4))$ there are no rejections; above $S^{-1}(q/4)$ exactly the $M$ nulls are rejected, contributing $q/4$. Below $U$ there is no false rejection. Endpoints have zero probability. Thus this is neither a main-target counterexample nor an auxiliary counterexample to (G-actual). It requires cascade-aware charging rather than a unit-crossing simplification.

### Step 4(b): a valid crossing envelope, and where it loses the maximal-rank event

The following bound is rigorous but dimension dependent. For a fixed null $i$, define the nonnegative Borel envelope
$$
F_i(x)=\mathbf1\{x>U-\theta_i\}
\min\left\{\frac{S(x)}{S(x+\theta_i)},\frac{N S(x)}q\right\}\le1.
$$
At a positive jump, the rank drops. Moreover $S(b+\theta_i)<\tau_i^w(b-)\le q$: if instead $S(b+\theta_i)\ge\tau_i^w(b-)$, both sides of a rank drop select $g_i$ in the minimum and the jump is zero. Its positive mass is at most its right-hand height, which is at most each of $g_i(b)$ and $NS(b)/q$. Consequently every positive jump is at most $F_i(b)$.

A rank drop must occur at at least one critical comparison with $\rho^{(i)}_j<0$. Otherwise all comparisons changing at that point would move p-values downwards as $x$ increases, and coordinatewise monotonicity of BH would make the rank nondecreasing. To handle coincident crossings, assign each distinct positive jump to the first negative-slope label $(j,k)$ at that point in a fixed ordering. This counts that jump once. Dropping both this assignment indicator and the condition that the labelled level is an actual maximal-rank transition gives
$$
P_i(w)\le B_i(w):=
\sum_{\substack{j\ne i:\rho^{(i)}_j<0}}\ \sum_{k=1}^N
F_i\!\left(\frac{u_k-\theta_j-w_j}{\rho^{(i)}_j}\right).
$$
The loss occurs precisely in this last inequality: it charges crossings of every lower BH critical level even while a larger qualifying rank remains present. The exact jump formula in Step 4(a) retains this missing information, whereas $F_i$ does not.

The marginal crossing integrals for this envelope can be computed without any full-dimensional density. Write $\rho=\rho^{(i)}_j<0$ and $s=\sqrt{1-\rho^2}$. If $s>0$, the marginal $W_j^{(i)}$ is $\mathcal N(0,s^2)$, so a change of variable gives exactly
$$
\mathbb E F_i\!\left(\frac{u_k-\theta_j-W_j^{(i)}}\rho\right)
=\int_{\mathbb R} F_i(x)\frac{|\rho|}{s}
\phi\!\left(\frac{u_k-\theta_j-\rho x}{s}\right)\,dx.
$$
The factor $|\rho|$ is the crossing Jacobian. Residual coordinates may be dependent or jointly singular; only this one-dimensional marginal was used. If $\rho=-1$, then $W_j^{(i)}=0$ almost surely and the expectation is instead the atom $F_i(\theta_j-u_k)$, with no extra density factor. Zero slopes cause no crossings and are excluded. Summing these exact integrals or atoms yields
$$
\sum_{i\in I_0}\mathbb E P_i(W^{(i)})
\le \sum_{i\in I_0}\mathbb E B_i(W^{(i)})
\le |I_0|N(N-1).
$$
This is a justified finite-model estimate, not the desired $C_*N(1+U)$ budget.

### Step 4(c): the crossing envelope itself can be quadratic (independently checked auxiliary diagnostic; not native approval)

There is no way to improve the last display to the required uniform order merely by bounding this same envelope. Fix any $0<q\le S(1)$, so $U\ge1$, and let $N=2M$ be even. Take $M$ centered nulls $T_i=Z$ and $M$ alternatives $T_j=2U+1-Z$, all with the one shared standard normal $Z$. The alternative means are positive, and the covariance is the unit-diagonal PSD rank-one sign matrix. For every null $i$ and alternative $j$, $\rho^{(i)}_j=-1$, $W_j^{(i)}=0$, and the labelled crossing is
$$
b_k=2U+1-u_k.
$$
For $k\in\{M,\ldots,N\}$ one has $U\le u_k\le S^{-1}(q/2)<U+1$. To verify the strict last inequality directly, the normal-tail bound already proved in Step 3 gives
$$
S(U+1)<\frac{\phi(U+1)}{U+1}\le\frac{\phi(U+1)}2
<\frac12\int_U^{U+1}\phi(t)\,dt<\frac12 S(U).
$$
Here $U\ge1$ makes the density decreasing on the integration interval, and its integral strictly exceeds its minimum $\phi(U+1)$. Thus
$$
U<b_k\le U+1,
\qquad S(b_k)\ge S(U+1)>0.
$$
Choose $N$ sufficiently large that $N S(U+1)/q\ge1$, which is possible at every fixed such $q$. Since these nulls have $\theta_i=0$, $g_i=1$ and $F_i(b_k)=1$ for all these $M+1$ distinct critical levels. Using just one fixed alternative label $j$ per null already gives
$$
B_i(0)\ge M+1,\qquad
\sum_{i\in I_0}\mathbb E B_i(W^{(i)})\ge M(M+1)\ge N^2/4.
$$
The definition of $B_i$ also counts the other duplicate alternative labels, but this lower bound does not rely on that additional duplication. Its ratio to $N(1+U)$ diverges as $N\to\infty$ at each fixed $q$; because $q$ can be any value below $S(1)$, restricting to any universal smaller positive interval does not fix this envelope estimate.

For every $k<N$ in this range, however, the actual maximal rank remains $N$ on both sides of $b_k$: at $b_k>U$ the null p-values are below $q$, while alternative p-values equal $qk/N<q$. Thus all $N$ p-values remain below $q$ in a neighborhood, and that lower-level crossing creates no rank jump at all. At $k=N$ alone this argument becomes a genuine boundary. The quadratic envelope cost is therefore largely made of inactive critical levels. This is a counterexample only to the attempted *envelope budget*, not to (G-actual) or to the original FDR target; no claim of a main-target counterexample is made. It shows exactly why the maximal-BH-rank event cannot be discarded before averaging.

The root driver subsequently relayed the fresh, derivation-independent review by `audit_crossing_envelope_fresh`. That reviewer confirmed the safe envelope, the $|\rho|/s$ Jacobian and the $\rho=-1$ atomic case in Step 4(b), as well as this model's lower bound and masking of every $k<N$ by the larger rank $N$. Its actual original FDR is $(q+S(U+1))/2<3q/4$: the FDP is $1/2$ on $[U,U+1]$ and one above $U+1$, since $S(U+1)<q/2$ lets the $M$ nulls qualify alone there. This is an independent check of the auxiliary diagnostic and these intermediate formulas, not native approval of a supporting asset, (G-actual), or either main target.

### Available general numerical bound: harmonic, hence insufficient

For comparison, a self-contained finite-$N$ bound obtained without losing validity under any covariance is
$$
\operatorname{FDR}\le\min\{1,q\pi_0 H_N\},\qquad H_N=\sum_{k=1}^N\frac1k.
$$
This is the standard harmonic bound, not a new order theorem. To verify it here, every true-null p-value has distribution function
$$
F_i(t)=S(S^{-1}(t)-\theta_i)\le t,\qquad 0<t<1,
$$
because $\theta_i\le0$. Each marginal is continuous even when the joint covariance is singular. If $i$ is rejected with rank $R$, then $p_i\le qR/N$. On $t_{k-1}<p_i\le t_k$ (where $t_k=qk/N$, $t_0=0$), this requires $R\ge k$, so its FDP contribution is at most $1/k$. A p-value above $q$ cannot be rejected. Since the event $p_i=0$ has probability zero, summation by parts gives
$$
\mathbb E\frac{\mathbf1\{i\in\mathcal R_q\}}{R\vee1}
\le\sum_{k=1}^N\frac{F_i(t_k)-F_i(t_{k-1})}{k}
=\sum_{k=1}^{N-1}\left(\frac1k-\frac1{k+1}\right)F_i(t_k)+\frac{F_i(q)}N
\le\frac qN H_N.
$$
Summing true nulls proves the stated bound. The nonnegative coefficients justify use of superuniformity; individual bin probabilities were not incorrectly assumed at most $q/N$. The remaining factor $H_N$ is unbounded when $N$ may vary arbitrarily with $q$, so this does not prove the current target.

## Failure

The first unproved essential proposition is Step 4, (G-actual): a universal bound on the *global expected actual-mean positive flux*, $\sum_{i\in I_0}\mathbb E P_i(W^{(i)})\le C_*N(1+U)$. Steps 1–3 and the exact normalization in the Step 4 prelude have been proved above and retained; no main-asset Proof has been written. They remain subject to independent verification and native approval before use as approved supporting results.

The attempted charging/averaging mechanism does not establish this proposition. A single affine critical crossing can cause the whole $N\to1$ collapse in Step 4(a), so charging only a unit rank loss or a local $1/N$ weight omits actual positive jump mass. The safe marginal-crossing envelope of Step 4(b) treats such cascades without falsely asserting residual independence and has the correct one-dimensional Jacobian and atomic cases. But it discards the condition that the crossing is an actual maximal-BH-rank transition. Step 4(c) gives a legal rank-one auxiliary object on which that envelope is at least $N^2/4$ at each fixed sufficiently small $q$, even though all but one of its counted upper-half critical levels produce no actual rank jump. Thus this envelope cannot supply the required universal estimate.

What is still needed is an event-sensitive, cascade-aware aggregate bound which retains the largest-qualifying-rank event while integrating the jointly Gaussian residuals from the same original model. Conditioning on one crossing does not make those residual coordinates independent. The execution has not proved any inequality that removes the inactive critical-level cost uniformly over arbitrary $N$, means, covariance and singular cases. The justified positive-flux bound is only $\sum_i\mathbb E P_i\le\sum_i\mathbb E B_i\le |I_0|N(N-1)$; the separate numerical FDR benchmark is $\min\{1,q\pi_0H_N\}$. Both retain uncontrolled dimension dependence. Neither a fixed-factor result nor the absence of a main-target counterexample fills the gap.

This is a failed proof route, not a refutation of (G-actual) and not a counterexample to the original one-sided or two-sided order targets. The auxiliary diagnostics concern the two attempted charging simplifications only; both have received fresh read-only independent checks as recorded above, without native approval of a new result or main-target counterexample. No universal constant or universal valid interval for the target has been established, and the target statement and all previous records remain unchanged.

## Independent read-only review receipts

At the failed-plan checkpoint the historical heading was “Step 4(c): the crossing envelope itself can be quadratic (auxiliary diagnostic awaiting fresh independent review)” and the Failure text said “the envelope diagnostic is explicitly awaiting a fresh independent check.” These descriptions record that earlier state; the subsequent review receipts below do not erase the candidate's provenance or change the failed status.

- The root driver relayed `audit_crossing_envelope_fresh`: confirmed the safe envelope and its Jacobian/atomic cases, the quadratic envelope diagnostic, and its actual FDR $(q+S(U+1))/2<3q/4$. The confirmed obstruction concerns only the envelope budget, not (G-actual) or a main target.
- The root driver relayed the fresh `audit_bv_core_selfcontained_fresh`: confirmed the partial core $I_i=1+J_i-D_i\le1+P_i$ and the $q/N$ FDR normalization, including ties, singular cases, $N=1$, empty true-null sets, and actual nonpositive means. The reported reviewed excerpt is lines 99–188, SHA256 `2884149b8633a8be5805bbe054ae2ebe9ec7db399c1cfe1cb808fc459e3b682f`; setup variables $X,u_k,\pi_0$ use the cited model and Plan definitions. The earlier partial excerpt review also raised only the need to restate the definitions locally, which the Step 4 prelude now does.

These are fresh, derivation-independent read-only checks as relayed by the driver. They are not a native verification of the whole theorem, approval of a new supporting asset, or a proof of the unresolved global flux budget. The main asset has not been edited.
