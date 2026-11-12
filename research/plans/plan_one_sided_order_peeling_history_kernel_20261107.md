---
id: plan_one_sided_order_peeling_history_kernel_20261107
type: plan
title: Universal one-sided order through stopped peeling and paired Gaussian history kernels
status: failed
target_asset: gaussian_bh_one_sided_universal_order_upper
inspired_by:
  - idea_d0a95c94fab5
---

# Universal one-sided order through stopped peeling and paired Gaussian history kernels

## Goal

Target: [Universal order upper bound for one-sided Gaussian BH](../assets/gaussian_bh_one_sided_universal_order_upper.md).

Prove the unchanged statement: finite universal C and q0>0 such that every finite N, every mean vector theta and every unit-diagonal PSD covariance, including singular covariance, has ordinary one-sided BH FDR at most C q sqrt(log(1/q)) for 0<q<=q0. Preserve the original labels I0={i:theta_i<=0}, all alternative means, multiplicities, non-strict comparisons and the largest qualifying rank. All parameters may vary with q; no dimension, rank, entropy, factor, null-proportion or eigenvalue restriction is permitted. No sharp constant is sought.

The [peeling proposal](../ideas/idea_d0a95c94fab5.md) is unproved guidance. Native library searches for Gaussian BH peeling/conditional histories and truncated likelihood/rectangle boundary summation found no result. No extra library theorem, failed plan, or draft observation is a black box. There is no Git repository at this cwd. Before exclusive creation, the source idea had SHA256 93cab3068843f7879ee3be24ca451964d177fb87eb24c30684c93ad4eb1b6044 and the target had SHA256 7f243d3df14d66d69b5997f33bdc8e2e661e55aae45f5d3b0dbf113a4d39c305.

External inspiration only: Jonathan Taylor, Richard Lockhart, Ryan J. Tibshirani and Robert Tibshirani, *Exact Post-selection Inference for Forward Stepwise and Least Angle Regression*, author-hosted PDF https://www.stat.cmu.edu/~ryantibs/journalclub/taylor_2014.pdf , Lemma 1 pp.5--6, treats general known-covariance Gaussian polyhedral truncation. The introduction p.2 leaves sequential FDR combination outside its scope. This hosted copy's publication/version metadata was not verified. Philipp Heesen and Arnold Janssen, *Inequalities for the false discovery rate (FDR) under dependence*, https://arxiv.org/abs/1410.8290v2 , revised 17 February 2015: only its metadata and abstract were checked; no numbered theorem was read or is invoked. Reverse-martingale dependence is an extra assumption, not a property asserted of arbitrary Gaussian p-values. Reconstruct all calculations inline.

Save the first completed derivation in this plan immediately. Save subsequent checkpoints only after re-reading the current insertion region and checking source/target/plan hashes, in patches of at most 6000 tokens. The parent owns native transitions and reports. Stop at the first essential unproved estimate, keeping the exact remainder and completed calculations; an auxiliary obstruction does not falsify the target.

## Plan

1. [x] **Reconstruct the actual largest-rank BH peeling and its stopped compensator.** Put S=barPhi, u_k=S^{-1}(qk/N), U=u_N, S0=[N], m_n=|S_n|, and t_n=q m_n/N whenever m_n>0. Before stopping define S_(n+1)={i in S_n:p_i<=t_n}. Prove the sets decrease and terminate at precisely the ordinary BH rejection set, not an arbitrary self-consistent subset: every qualifying-rank BH set is contained in every S_n, while a nonempty terminal fixed point qualifies at its own cardinality. Cover all ties deterministically. Let

   $$
   \tau=\min\{n\ge1:S_n=\varnothing\ \text{or}\ S_n=S_{n-1}\}.
   $$

   Establish tau<=N+1; no t_n is needed after an empty state. With t_-1=1, V_n=|I0 intersect S_n| and H_n=sigma(S0,...,S_n), define W_n=V_n/t_(n-1) for 0<=n<=tau and freeze W_n=W_tau afterward. At an empty terminal state W_tau=0 with its still-positive preceding denominator. At a stable nonempty terminal state t_(tau-1)=qR/N; hence in every case W_tau=(N/q)FDP. Show all W_n are integrable (finite N and every denominator used is >=q/N). For 0<=n<=N put D_n=0 on {tau<=n}; on {n<tau} put

   $$
   D_n=\sum_{i\in I_0\cap S_n}
   \left\{\Pr(T_i\ge u_{m_n}\mid\mathcal H_n)/t_n-1/t_{n-1}\right\}.
   $$

   Prove E[W_(n+1)-W_n|H_n]=D_n with the freezing indicators included, and derive by finite telescoping

   $$
   \operatorname{FDR}=q|I_0|/N+(q/N)\sum_{n=0}^N\mathbb E D_n. \tag{PH-Doob}
   $$

   This identity assumes neither conditional independence nor a reverse-supermartingale sign. Show explicitly why merely knowing it does not supply its missing drift budget.

2. [x] **Derive each exact actual-mean conditional-history kernel.** Initially take a positive-definite correlation matrix C. For each positive-probability active history h of length n, write its event as one product of score bands B_(j,h), with the original means unchanged. A coordinate removed at a given round lies below that round's threshold and above every threshold it previously passed. An alive i has band [a,infinity), a=S^{-1}(tprev), where tprev=t_(n-1); its next threshold is b=S^{-1}(t_n)>=a. At n=0 use a=-infinity, tprev=1 and the full-space history. Put p_x=S(x-theta_i), p_a=S(a-theta_i), p_b=S(b-theta_i), r=p_b/p_a, and

   $$
   w_{i,h}(x)=\Pr\{T_{-i}\in\prod_{j\ne i}B_{j,h}\mid T_i=x\}.
   $$

   Prove increasing Gaussian hazard by an elementary integral argument, and deduce r<=t_n/tprev for theta_i<=0, including a=-infinity. Define K=0 on x<a and

   $$
   K_{i,h}(x)=
   \begin{cases}
   r(p_a-p_x),&a\le x<b,\\
   (1-r)p_x,&x\ge b.
   \end{cases}
   $$

   Check K>=0, continuity at b, K(a)=K(infinity)=0, and at the first history K(-infinity)=0. Integrate the signed density [1{x>=b}-r1{x>=a}]phi(x-theta_i), whose primitive is -K, to prove the exact formula

   $$
   \Pr(h)\left\{\Pr(T_i\ge b\mid h)/t_n-1/tprev\right\}
   =\frac1{t_n}\int_{\mathbb R}K_{i,h}(x)w'_{i,h}(x)\,dx
   +\Pr(h)\{r/t_n-1/tprev\}. \tag{PH-K}
   $$

   Prove all fixed-model integrations and boundary limits, not just the formal integration by parts. At n=0, w=1, so the kernel charge is zero and the composite-null drift is S(U-theta_i)/q-1<=0. The last ACTIVE comparison can have a<b even when its next set is unchanged, and its kernel must be retained. Only an artificially repeated comparison after stability has a=b and K=0; the actual process is already frozen then. Write the summed nonpositive second terms as B; retain B in the first combined allocation rather than silently discarding it.

   Conditional Gaussian regression gives mean theta_-i+C_-i,i(x-theta_i) and covariance C_-i,-i-C_-i,i C_i,-i. Differentiate the translated rectangle integral to obtain

   $$
   w'_{i,h}(x)=\sum_{j\ne i}C_{ij}
   \{L_{j,h}(x)-H_{j,h}(x)\}, \tag{PH-face}
   $$

   where L and H are the lower and upper j-face conditional densities integrated over the other actual history bands, and infinite faces contribute zero. Preserve the covariance coefficients and signed face orientations exactly; do not replace conditional background laws by independent coordinates.

3. [x] **Complete the exact N=2 and N=3 stress tests before attempting aggregation.** For N=2 and separately N=3 take X~N(0,1), T1=X, T_j=mu-X (j>1), mu=u_N+u_1, C=vv^T with v=(1,-1,...,-1), and I0={1}. Enumerate every peeling branch with its original labels. Prove H1={S1={1}} agrees almost surely with {X>u_1}, has probability q/N, and conditional X is the standard normal truncated below u_1. Its next survival probability is 1, not t1/t0=1/N. Initial and all other drift terms vanish, and this branch contributes exactly 1-1/N to the expected normalized drift. Derive FDR=(q/N)(2-1/N), giving 3q/4 for N=2 and 5q/9 for N=3.

   Independently evaluate PH-K: here w_h=1{x>u_1}, w'_h is the unit point mass there and K(u_1)/t1=1-1/N. This checks orientation, normalization and rare-history mass without pretending a singular conditional law has a density. For each fixed N,q, check positive-definite regularizations C_epsilon=(1-epsilon)vv^T+epsilon I, fixed means and labels, by coupling and threshold-boundary avoidance. Use this only as calibration, with no unproved uniform convergence of face integrals. Also check N=1, all-alternative labels, stable first-round histories and empty histories directly.

4. [ ] **Actually glue sibling-history faces with their different kernel weights.** Refine all finite reveal histories to the common product grid with coordinate thresholds u_1,...,u_N. For fixed off-grid x=T_i and fixed remaining coordinates, replay the finite peeling procedure on each grid cell c. Define the branch weight

   $$
   A_i(c,x)=\sum_{0\le n<\tau(c,x)}
   \mathbf1\{i\in S_n(c,x)\}
   K_{i,h_n}(x)/t_n(c,x). \tag{PH-A}
   $$

   Kernels are zero outside their own alive band. Group every lower j-face from PH-face with the upper j-face of the adjacent cell on the SAME original-covariance conditional Gaussian density. Prove that repeated histories and differing stopping depths yield one coefficient

   $$
   C_{ij}\{A_i(c^+,x)-A_i(c^-,x)\}, \tag{PH-pair}
   $$

   on each actual j-grid face. In particular the n=0 branch weight is independent of all other cells and cancels. Do not identify weights from different descendants. Write the resulting finite exact charge as

   $$
   \mathcal C=\sum_{i\in I_0}\sum_{j\ne i}C_{ij}\sum_{l=1}^N
   \int_{\mathbb R}\int_{\mathbb R^{N-2}}
   f_{-i\mid i}(u_l,z\mid x)
   \Delta_{j,l}A_i(x,z)\,dz\,dx, \tag{PH-paired}
   $$

   where the jump is from the lower to the upper side of T_j=u_l, all other coordinates remain fixed, and the jump is zero on inactive faces. No marginal phi(x-theta_i) multiplies this expression: the marginal tail was already integrated into K. Prove this normalization from PH-K rather than adding an erroneous joint-density factor.

   Compute each jump by coupling the two deterministic peeling runs across that face. Cancel their identical prefix through the first divergent j-membership decision, then display the TWO actual suffix sums of K/t, including every cascade, the last comparison and differing terminal ranks. Apply finite summation by parts to these suffixes, keeping all endpoint and composite-null terms; report the explicit residual rather than declaring that opposite faces cancel.

   As a mandatory saturation diagnostic, for theta_i=0 put h_s(p)=(1-p/s)_+ and verify

   $$
   K/t=h_{tprev}(p_i)-h_t(p_i),\qquad
   A_i=1-p_i-\mathbf1\{i\in\mathcal R_q\}(1-p_i/t_R), \tag{PH-central}
   $$

   with the last term zero at R=0. Prove this including branches on which i dies before the other coordinates stop. Then, for the two adjacent cells, compute the central-null jump as g_(R-)(p_i)-g_(R+)(p_i), where g_r(p)=(1-p/t_r)_+, g_0=0. Increasing T_j makes R+>=R-, so this jump is nonpositive. Its entry and dilution pieces are respectively -g_(R+)(p_i) when i newly enters, and -p_i(1/t_(R-)-1/t_(R+)) when it is rejected on both sides. Check exact boundary cases. This is a concrete cancellation/sign calculation; positive-correlation contributions are favorable for these central-null terms, while original negative correlations remain to be budgeted.

   For theta_i<0 derive and use the exact weighted counterpart

   $$
   K/t=\lambda_i(t)\{h_{p_a}(p_x)-h_{p_b}(p_x)\},
   \qquad \lambda_i(t)=p_b/t,
   $$

   prove lambda_i(t) decreases along decreasing t, and explicitly retain its summation-by-parts differences together with B. Do not replace composite null means by zero or assume their BH denominators are unchanged.

   The first compulsory analytic gate is a NONCIRCULAR estimate of the combined remainder produced by this actual sibling allocation,

   $$
   \mathcal C+\mathcal B\le A N(1+U) \tag{PH-budget}
   $$

   for one finite universal A on a universal small-q interval. First attempt to integrate the central-null signed negative-contact entry/dilution pieces and the composite-null lambda differences on their common original Gaussian faces, before any absolute values. Keep all largest-rank masks and actual C_ij. Show the resulting explicit terminal/interface residual after this calculation. A sufficient stronger bound on C alone is acceptable only if proved and not silently assumed. No null-proportion-linear strengthening is required.

   **Failure rule:** if the available summation by parts or integration by parts only reconstructs PH-Doob, unknown FDR or its weighted equivalent, record that exact saturation as failure of this plan's first aggregate gate. Also stop if the justified remainder still contains uncontrolled log N, face count, negative degree, inverse variance/eigenvalue, free-threshold supremum or auxiliary Gram maximization. Retain the completed PH-pair and PH-central calculations and the exact unbounded residual. Do not call PH-budget proved merely because the total signed drift has been rewritten; the required estimate must bring independently controlled Gaussian mass. A false optional local simplification rejects that simplification only; continue only with an explicit remaining calculation for the combined gate, not a renewed promise to bound it.

5. [ ] **Transfer only a proved uniform budget to the unchanged target.** If and only if Step 4 proves PH-budget, combine PH-Doob and PH-K to obtain FDR<=q+Aq(1+U). For a singular original covariance Sigma, use C_epsilon=(1-epsilon)Sigma+epsilon I with fixed means and original labels. Couple to the original finite vector; each coordinate has a continuous unit-variance marginal, so none hits the finite BH grid with positive probability. Prove almost-sure FDP convergence and then dominated FDR convergence for each fixed N,theta,Sigma. All constants must have been uniform in epsilon. Do not assert convergence of face charges or exchange the all-model supremum with a nonuniform limit. Prove U<=C0 sqrt(log(1/q)) on a universal small interval and extract finite universal target constants. Any prospective complete proof needs fresh independent verification and native approval procedures; until then the target statement/status/Proof stays untouched.

## Verification

Reconstruct every deterministic peeling and history formula independently; check the first-history a=-infinity convention, stopped denominators, exact N=2/3 rare-history charges, lower-minus-upper orientation and the absence of an extra marginal density in PH-paired. The first novel calculation is PH-pair with actual divergent suffixes, followed by PH-central and the composite-null weighted residual. Successful identities are not a uniform estimate. PH-budget must be independently bounded before PSD transfer or any target proof claim. Only then do Steps 1--5 produce exactly the all-finite-model order statement.

## Assumed definitions

Use only the target's approved gaussian_multiple_testing_model, gaussian_test_pvalues, benjamini_hochberg_step_up, false_discovery_rate and gaussian_worst_case_bh_fdr definitions. The source idea is guidance, not an unproved dependency assumed true. No draft asset, additional library theorem, external martingale hypothesis, independent-residual model or prior failed calculation is a black box. All Gaussian regression, hazard, conditional differentiation, finite integration and continuity arguments are rederived inline.

## Difference from failed plans

- **plan_252211621cea:** Its signed half-line K/Abel argument ended at a weighted unknown FDR. Here the finite peeling history supplies new exact band masks and a compensated kernel; PH-central deliberately exposes its own possible terminal-potential saturation. Failure to bound that residual independently is explicitly failure, not a solution obtained by changing notation.
- **plan_503f8fddcbb5:** The global-shift record allocation left record faces minus favorable bulk uncontrolled and pursued a null-proportion-linear auxiliary budget. This plan preserves sequential history probabilities and different K/t weights and requires only an aggregate N(1+U) normalized budget, retaining composite-null losses.
- **plan_ee2f7b97740a:** Compatible Hall cuts left non-potential circulation and inverse-covariance noise loss. This trial computes actual original-Gaussian shared faces of adjacent reveal cells, with no Hall maximum or potential assumption; different suffixes and possible terminal saturation are calculated explicitly.
- **plan_one_sided_order_actual_mean_global_flux_20261106:** Its marginal-critical-level envelope counted inactive cascades and had an N-squared obstruction. Every present face retains both actual peeling trajectories and their original stopping/rank masks; no sum over free critical crossings replaces them.
- **plan_one_sided_order_common_anchor_rotation_20261107:** Its actual-mask Abel collation returned exactly the unknown FDR derivative/variation and gave no independent budget. The new trial keeps the covariance fixed and tests sibling reveal-history cancellation, but explicitly checks whether PH-central and further integration also return the unknown quantity. A second saturation is recorded as failure immediately.
- **plan_one_sided_order_gaussian_interpolation_sdp_20261106:** Its signed boundary matrix had no uniform diagonal completion. Here coefficients are original C_ij on conditional history faces; there is no PSD completion, row-absolute-sum charge, random-level scalar substitution or assertion that Gaussian averaging alone removes multiplicity.
- **plan_one_sided_order_negative_contact_transport_20261106:** Its independent-residual and original-density allocations retained inverse noise and weighted negative degree. Here negative contacts arise only after the explicit sibling K/t pairing, with composite-null lambda corrections retained. That potentially different weight is tested directly; no old negative-contact estimate is assumed and any same remaining degree/noise loss fails the gate.
- **plan_one_sided_order_three_face_noise_packing_20261106:** Its integrated Gram supremum removed the true small covariance coefficient and admitted a logarithmic auxiliary obstruction. This plan keeps the actual C_ij at every face, never contracts against a separately maximized covariance, and seeks a finite signed history charge rather than an unweighted sensitivity budget.

## Progress

### P1. Deterministic peeling and finite stopped compensation (Step 1 complete)

Write $S(x)=\overline\Phi(x)$, $u_k=S^{-1}(qk/N)$, $U=u_N$, and retain the original null set $I_0=\{i:\theta_i\le0\}$. All deterministic arguments below use the non-strict comparison $p_i\le t_n$ and retain coordinate labels. Sets decrease by their definition. Before a nonempty stable state or the empty state, every update removes at least one coordinate; hence there are finitely many updates, and in particular $\tau\le N+1$ (indeed $\tau\le N$).

Let $k>0$ qualify for BH and put $A_k=\{i:p_i\le qk/N\}$. Its cardinality is at least $k$. Inductively, if $A_k\subset S_n$, then $m_n\ge k$, and every member of $A_k$ passes $q m_n/N$; thus $A_k\subset S_{n+1}$. If $k_*$ is the largest qualifying rank, $|A_{k_*}|=k_*$: otherwise its larger cardinality $l$ also qualifies, since $p_{(l)}\le qk_*/N\le ql/N$. Consequently the BH rejection set is contained in every peeling state. A nonempty terminal fixed point of cardinality $m$ satisfies $p_i\le qm/N$ for all its members, so $m$ qualifies and $m\le k_*$. Containment then forces equality of the terminal set and the BH rejection set. If there is no positive qualifying rank, a nonempty fixed point is impossible; the terminal set is empty. Conversely an empty terminal set cannot occur when any $k$ qualifies. This proves the largest-rank assertion, including tied scores and multiplicities, without choosing a tie-breaking permutation.

Set $t_{-1}=1$ and $V_n=|I_0\cap S_n|$. For $0\le n\le\tau$, set $W_n=V_n/t_{n-1}$, and freeze $W_n=W_\tau$ for $n>\tau$. If the terminal state is empty, its preceding state is nonempty and its denominator $t_{\tau-1}$ is defined and positive; $W_\tau=0$. If it is stable and nonempty, $m_{\tau-1}=m_\tau=R$, so $t_{\tau-1}=qR/N$ and $W_\tau=(N/q)\operatorname{FDP}$. Every denominator actually used is either $1$ or at least $q/N$; thus all $W_n$ are bounded by $N^2/q$ for fixed $N,q$ and are integrable. No denominator is assigned after an empty state.

The event $\{n<\tau\}$ is $\mathcal H_n$-measurable. On it,
$$
W_{n+1}=\frac1{t_n}\sum_{i\in I_0\cap S_n}\mathbf1\{T_i\ge u_{m_n}\},
\qquad W_n=\sum_{i\in I_0\cap S_n}\frac1{t_{n-1}}.
$$
This formula also applies when the update at $n+1$ is the first stable or empty state. On $\{\tau\le n\}$ the increment is exactly zero by freezing. Taking the conditional expectation therefore gives exactly the $D_n$ in Step 1, with its indicator $\mathbf1\{n<\tau\}$. Finite summation over $n=0,\ldots,N$ gives
$$
\sum_{n=0}^{N}\mathbb E D_n
=\mathbb E W_{N+1}-W_0
=\frac Nq\operatorname{FDR}-|I_0|.
$$
This is PH-Doob, with no martingale sign or independence assumption. It supplies an identity only: the proposed bound still requires a bound on the total signed drift independent of the unknown FDR. In particular no inequality follows by deleting $D_n$, whose conditional sign has not been established.

Checkpoint provenance: before this insertion the plan was SHA256 `84718314a93502029d1cca83fee30e1389c44a851aed2305996023fe80bca7a1`; the unchanged target was `7f243d3df14d66d69b5997f33bdc8e2e661e55aae45f5d3b0dbf113a4d39c305`; the current source idea was `3d1860de37feadcd8979be5bfc1ad876c4baab829125785694008845f35abe80`. There is no Git repository at this cwd. Only this plan is edited.

### P2. Conditional Gaussian kernels and faces (Step 2 complete)

For this step let $C$ be positive definite. Fix an active history $h=(S_0,\ldots,S_n)$ with positive probability, and write $b_r=u_{m_r}$ for its known score thresholds, with $b_{-1}=-\infty$. A coordinate first removed in update $r\to r+1$, $r<n$, has score band $[b_{r-1},b_r)$; a coordinate still alive has band $[b_{n-1},\infty)$. These constraints are necessary and sufficient to replay precisely $h$, because all preceding memberships are then the recorded ones. Thus $h$ is one product of these actual bands, not a union requiring a new conditioning law. At $n=0$ every band is the whole line. Endpoints can be assigned by the original non-strict survival convention; under a positive-definite Gaussian their probability is zero.

For a live null $i$, put $a=b_{n-1}$, $b=b_n$, $p_x=S(x-\theta_i)$, $p_a=S(a-\theta_i)$, $p_b=S(b-\theta_i)$ and $r=p_b/p_a$. Write $\varphi_i(x)=\varphi(x-\theta_i)$. The Gaussian hazard $H(z)=\varphi(z)/S(z)$ has
$$
H'(z)=H(z)[H(z)-z]>0,
\qquad \varphi(z)-zS(z)=\int_z^\infty (v-z)\varphi(v)\,dv>0.
$$
For $\delta=-\theta_i\ge0$, integration of the logarithmic tail derivative yields
$$
\log\frac{S(b+\delta)}{S(a+\delta)}
=-\int_a^b H(v+\delta)\,dv
\le-\int_a^b H(v)\,dv
=\log\frac{t_n}{t_{n-1}}.
$$
For $a=-\infty$ this follows by a limit, since both tails at the lower endpoint tend to one and the displayed integrals are finite. Hence $r\le t_n/t_{n-1}$. This retains every negative true-null mean.

The prescribed $K$ is nonnegative. At $b$ the two expressions agree since $r p_a=p_b$, and at $a$ it is zero. It tends to zero at $+\infty$; when $a=-\infty$ its lower limit is zero as well. Its weak derivative is
$$
K'(x)=\varphi_i(x)\{r\mathbf1_{x\ge a}-\mathbf1_{x\ge b}\}.
$$
There are no atoms at $a,b$ because $K$ is continuous there. It is integrable: its right tail is bounded by $S(x-\theta_i)$, its bounded middle interval is finite, and in the only unbounded left case it is a constant times $1-S(x-\theta_i)$, whose left tail is integrable. Let
$$
w(x)=\int_{\prod_{j\ne i}B_{j,h}} f_{-i\mid i}(y\mid x)\,dy.
$$
Then $\Pr(h)=\int_a^\infty\varphi_i(x)w(x)\,dx$. The conditional Gaussian law has mean $\theta_{-i}+c(x-\theta_i)$ and covariance $Q=C_{-i,-i}-cc^{\mathsf T}\succ0$, with $c=C_{-i,i}$. This follows directly by setting $Z=T_{-i}-\theta_{-i}-c(T_i-\theta_i)$: its covariance with $T_i$ is zero, and its joint Gaussian characteristic function with $T_i$ factors, so they are independent.

Differentiating its density gives $\partial_x f=c^{\mathsf T}Q^{-1}(y-\theta_{-i}-c(x-\theta_i))f$. Its integral absolute value over the whole $y$ space is a finite constant depending on $C$, independent of $x$ (translate to a centered Gaussian). This proves differentiation under the rectangle integral and a uniform bound on $|w'|$; equivalently one can use dominated differentiation on compact $x$ intervals followed by that bound. Since $0\le w\le1$ and $K\to0$ at both ends, ordinary integration by parts on finite intervals and then dominated convergence give
$$
\frac1{t_n}\int [\mathbf1_{x\ge b}-r\mathbf1_{x\ge a}]\varphi_i(x)w(x)\,dx
=\frac1{t_n}\int K(x)w'(x)\,dx.
$$
Adding $(r/t_n-1/t_{n-1})\Pr(h)$ proves PH-K exactly. In particular there is no missing probability factor on its kernel integral.

For the face formula, $\partial_x f=-\sum_{j\ne i}C_{ij}\partial_{y_j}f$. Integrate each derivative over its recorded band and use the fundamental theorem of calculus. This yields $w'=\sum_{j\ne i}C_{ij}(L_{j,h}-H_{j,h})$, with precisely lower minus upper faces on the same density $f_{-i\mid i}$. Infinite faces vanish. For rigor, the integral over the other band coordinates of an absolute finite face density is at most the one-dimensional conditional marginal density of $T_j\mid T_i=x$, bounded by $[2\pi(1-C_{ij}^2)]^{-1/2}$. Multiplication by the integrable $K$ proves absolute integrability of every fixed-model face integral. It also justifies removing finite cutoffs on infinite faces by dominated convergence. No constant in this fixed-model justification is claimed uniform in $C$.

Define and retain
$$
\mathcal B=\sum_{n,h\ {
m active}}\Pr(h)
 \sum_{i\in I_0\cap S_n(h)}\left(\frac{r_{i,h}}{t_n(h)}-\frac1{t_{n-1}(h)}\right)\le0,
\qquad
\mathcal C=\sum_{n,h\ {
m active}}\sum_{i\in I_0\cap S_n(h)}\frac1{t_n(h)}\int K_{i,h}w'_{i,h}.
$$
There are finitely many histories, so $\sum_n\mathbb E D_n=\mathcal C+\mathcal B$. At $n=0$, $w=1$, so its kernel charge is zero; its individual drift is $S(U-\theta_i)/q-1\le0$. The last active comparison is $n=\tau-1$: even if $S_\tau=S_{\tau-1}$, the *preceding* size $m_{\tau-2}$ may be larger, and $a<b$. For example the singleton rare history in P3 has exactly this property. Its kernel is retained. Only a further artificial repeat after stability would have $a=b$ and $K=0$, and that repeat is excluded by freezing.

### P3. Exact small-model calibration (Step 3 complete)

Take $q<1/2$, first $N=2$ and then separately $N=3$. Let $X$ be standard normal, $\mu=U+u_1>0$, $T_1=X$ and $T_j=\mu-X$ for every $j>1$. Thus the original mean vector is $(0,\mu,\ldots,\mu)$ and its null set is exactly $\{1\}$; its covariance is the admissible unit-diagonal PSD matrix $vv^{\mathsf T}$, $v=(1,-1,\ldots,-1)$. The three exhaustive branches, outside two probability-zero endpoints, are:

- $X<U$: $S_1=\{2,\ldots,N\}$ and $S_2=S_1$, because every alternative score exceeds $u_1\ge u_{N-1}$. Here $\tau=2$ and FDP is zero.
- $U<X<u_1$: $S_1=[N]=S_0$, so $\tau=1$ and FDP is $1/N$.
- $X>u_1$: $S_1=\{1\}$ and $S_2=\{1\}$, so $\tau=2$ and FDP is one.

All alternative coordinates are tied when $N=3$, and all their original labels survive or die together. No tie is split. The rare singleton history $H_1$ is exactly $\{X>u_1\}$ almost surely, has probability $q/N$, and the conditional law of $X$ is the standard normal truncated there. Its next survival probability is one. At $n=0$ the central null has expected drift zero; at $n=1$ the all-surviving branch is frozen, the alternative-only branch has no live null, and the singleton branch has drift $(N-1)/q$. Its expected normalized charge is therefore $1-1/N$. Direct branch integration independently gives
$$
\operatorname{FDR}=\frac{q-q/N}{N}+\frac qN
=\frac qN\left(2-\frac1N\right).
$$
For $N=2$ this is $3q/4$, and for $N=3$ it is $5q/9$. This is not a reverse-supermartingale example: the rare history has strictly positive conditional drift.

For its PH-K calculation $a=U$, $b=u_1$, $t_0=q$, $t_1=q/N$, $r=1/N$, and $w_h(x)=\mathbf1\{x>u_1\}$. Its distributional derivative is a positive unit point mass at $u_1$, giving
$$
\frac{K(u_1)}{t_1}
=\frac{(1-1/N)S(u_1)}{q/N}=1-1/N.
$$
The composite correction is zero since $\theta_1=0$. This singular diagnostic uses a measure derivative rather than falsely asserting a conditional Lebesgue density; it independently checks the sign, absence of an extra marginal density, and absence of a second history-probability factor. It also checks that the final active singleton comparison $a=U<b=u_1$ cannot be omitted merely because its *next* set is stable.

For positive-definite calibration take independent standard $Z\in\mathbb R^N$ and $T^\epsilon=\theta+\sqrt{1-\epsilon}\,vX+\sqrt\epsilon Z$, with the same fixed means and labels. Its covariance is $(1-\epsilon)vv^{\mathsf T}+\epsilon I$, and it tends almost surely to the displayed singular vector. None of its limiting coordinates hits any of the finitely many $u_k$ with positive probability, since each marginal is continuous with variance one. Thus all threshold comparisons, and hence the complete finite peeling and FDP, are eventually identical in this coupling. Bounded convergence gives the displayed limiting FDR. No convergence of individual face integrals, nor any uniform-in-model convergence rate, is asserted.

For $N=1$, the only comparison gives FDR $=S(U-\theta_1)\le q$ when its label is null; its sole drift is $S(U-\theta_1)/q-1$, its kernel charge is zero, and all increments after it are frozen. With no null labels all $V_n,W_n,D_n,\mathcal C,\mathcal B$ are zero. A stable first-round history has $\tau=1$ and only the initial comparison; an empty state has zero terminal FDP with the positive denominator preceding emptiness, and no subsequent $t_n$. These cases agree with P1 and P2.

### P4a. Same-grid face pairing and the two actual suffixes

For fixed $i$ and an off-grid value $x=T_i$, partition the other score coordinates into the finite product grid with boundaries $u_1,\ldots,u_N$. On each cell $c$ every comparison has a fixed outcome, so replay gives its actual history and $J(c,x)=\tau(c,x)-1$. Define
$$
A_i(c,x)=\sum_{n=0}^{J(c,x)}\mathbf1_{\{i\in S_n(c,x)\}}\frac{K_{i,h_n}(x)}{t_n(c,x)}.
$$
Refine every history band into this same grid. For each history a lower face contributes its coefficient with a plus sign, and the adjacent cell's upper face contributes with a minus sign; any subdividing face within the same history cancels identically. Each history's weight $K/t_n$ appears on every compatible cell, once, for that stage. Summing over the finite histories therefore pairs every actual adjacent-cell interface into
$$
C_{ij}\,[A_i(c^+,x)-A_i(c^-,x)]\,
f_{-i\mid i}(u_l,z\mid x).
$$
This reasoning does not require the two cells to have the same number of stages. Repeated prefixes contribute once for each actual stage, while their identical weights cancel across the paired face. The initial $n=0$ weight depends on $x$ alone and has zero jump. The fixed-model absolute-integrability justification in P2 permits every finite rearrangement. Consequently the resulting charge is exactly PH-paired, including the actual coefficient $C_{ij}$ and the actual conditional Gaussian density at that shared face. There is **no** factor $\varphi_i(x)$: the marginal density in PH-K was integrated once into $K$, and PH-face differentiates the remaining conditional density alone.

Here is the explicit deterministic suffix comparison, including composite nulls. Define the actual-mean tail map and its weight by
$$
Q_i(s)=S(S^{-1}(s)-\theta_i),\quad Q_i(1)=1,
\qquad \lambda_i(s)=Q_i(s)/s,
\qquad v=S(x-\theta_i),\quad h_s(v)=(1-v/s)_+.
$$
On a given run write $\lambda_n=\lambda_i(t_n)$ and $H_n=h_{Q_i(t_n)}(v)$, with $H_{-1}=1-v$. Inspection of the two pieces of $K$ gives, also when $x<a$,
$$
K_{i,h_n}(x)/t_n=\lambda_n(H_{n-1}-H_n).
$$
If $i$ has died, both hinges are zero at every subsequent stage, so this expression is zero; it is legitimate to sum it through the entire run. Hazard monotonicity in P2 also gives
$$
\frac d{dz}\log\frac{S(z-\theta_i)}{S(z)}
=-H(z-\theta_i)+H(z)\le0.
$$
Thus $\lambda_i(t)$ decreases as $t$ decreases for every $\theta_i\le0$. Finite summation by parts yields the exact path potential
$$
A_i=\lambda_i(q)(1-v)-\Gamma_i,\qquad
\Gamma_i=\lambda_J H_J+\sum_{n=0}^{J-1}(\lambda_n-\lambda_{n+1})H_n. \tag{P4-weighted}
$$
All displayed difference terms are nonnegative; they are retained, not silently removed. For a nonempty terminal state $t_J=qR/N$; for an empty state $H_J=0$. A null that died earlier also has $H_J=0$.

Across a $j$-face, replay the two runs, keeping all other scores and the original covariance fixed. If they differ, let $d$ be their first divergent membership decision: their $S_0,\ldots,S_d$ are identical, their comparison at $d$ has threshold $u_l$, and only the $j$ membership initially differs in $S_{d+1}$. All weights through comparison $d$ are identical, including $K/t_d$, even when one run stops immediately afterward. For each sign put $J_\pm=\tau_\pm-1\ge d$. The remaining **two actual suffixes** are
$$
\Delta A_i=
\sum_{n=d+1}^{J_+}\lambda_n^+(H_{n-1}^+-H_n^+)
-\sum_{n=d+1}^{J_-}\lambda_n^-(H_{n-1}^--H_n^-).
$$
An empty sum is zero. Each sum uses its own cardinalities and denominators. Uniformly even when $J_\pm=d$, summation by parts makes it
$$
\sum_{n=d+1}^{J_\pm}\lambda_n^\pm(H_{n-1}^\pm-H_n^\pm)
=\lambda_d H_d-\Gamma_{i,d}^{\pm},
\quad
\Gamma_{i,d}^{\pm}=\lambda_{J_\pm}^{\pm}H_{J_\pm}^{\pm}
+\sum_{n=d}^{J_\pm-1}(\lambda_n^\pm-\lambda_{n+1}^\pm)H_n^\pm.
$$
Hence the exact paired coefficient is $C_{ij}(\Gamma_{i,d}^{-}-\Gamma_{i,d}^{+})$. This displays the surviving terminal and weight-drop residual, rather than equating descendants with different ranks or stopping times. If the two runs never diverge the jump is zero.

### P4b. Central-null telescope, entry/dilution coefficients, and explicit cascades

For $\theta_i=0$, $Q_i(s)=s$ and every $\lambda_n=1$. Thus the weighted formula reduces to the exact identity
$$
\frac{K}{t_n}=h_{t_{n-1}}(p_i)-h_{t_n}(p_i),\qquad
A_i=1-p_i-g_R(p_i),\qquad
g_r(p)=(1-p/(qr/N))_+,\quad g_0=0.
$$
If $i$ dies, the hinge after its killing comparison is zero, and every later hinge is zero because thresholds continue to decrease; its full sum is $1-p_i$. If it remains rejected, the last retained comparison leaves precisely $h_{t_R}(p_i)$. These are all paths, including stable first-round paths, so this proves PH-central without omitting a final comparison. At a threshold equality the hinges are zero and the same formulas hold with the original non-strict membership.

Increasing $T_j$ decreases its p-value; for each rank it can only increase the number of p-values below that rank's threshold. Every formerly qualifying rank therefore continues to qualify, and $R_+\ge R_-$. With $p=p_i$ fixed, the exact central jump is
$$
\Delta A_i=g_{R_-}(p)-g_{R_+}(p)\le0.
$$
If $i$ is rejected on neither side, this is zero. If it newly enters, it is $-g_{R_+}(p)$. If it is rejected on both sides (necessarily $R_->0$), it is
$$
-p\left(\frac1{qR_-/N}-\frac1{qR_+/N}\right).
$$
These formulas include $R_-=0$ via $g_0=0$, equal ranks, and $p=qR_\pm/N$ via a zero hinge; the dilution formula never divides by zero. Thus positive $C_{ij}$ gives a nonpositive central charge, while negative $C_{ij}$ gives a nonnegative charge. No assertion about cancellation of the latter has been made.

Two concrete sibling replays expose the different suffix denominators. Write $t_k=qk/3$ for these $N=3$ examples, and use distinct original labels $i,j,k$.

1. Put $t_1<p_i<t_2$ and $t_2<p_k<q$, and cross the face $T_j=u_3$, holding $p_j$ just above $q$ on the lower-score side and just below $q$ on the upper-score side. The lower-score trajectory is
$$
\{i,j,k\}\ \xrightarrow{q}\ \{i,k\}\ \xrightarrow{t_2}\ \{i\}\ \xrightarrow{t_1}\ \varnothing,
$$
with $J_-=2$ and $R_-=0$. The upper-score trajectory is $\{i,j,k\}\xrightarrow{q}\{i,j,k\}$, with $J_+=0$ and $R_+=3$. The shared initial kernel cancels, but the entire lower suffix remains. Centrally its jump is
$$
-[h_q(p_i)-h_{t_2}(p_i)]-[h_{t_2}(p_i)-h_{t_1}(p_i)]
=-h_q(p_i),
$$
because $h_{t_1}(p_i)=0$. For an original composite-null mean put $H_s=h_{Q_i(s)}(v)$ and $\lambda_s=\lambda_i(s)$; the **actual** jump instead is
$$
-\lambda_{t_2}(H_q-H_{t_2})-\lambda_{t_1}(H_{t_2}-H_{t_1})
=-\lambda_{t_2}H_q+(\lambda_{t_2}-\lambda_{t_1})H_{t_2},
$$
where $H_{t_1}=0$. It is not obtained by equating the two descendants' kernels or their denominators. The weight-drop term survives even in this small cascade.

2. Put $p_i<t_1$, $p_k>q$, and cross $T_j=u_2$, keeping $p_j$ on either side of $t_2$ but below $q$. Both trajectories first go $\{i,j,k\}\xrightarrow{q}\{i,j\}$. The lower-score side then goes $\{i,j\}\xrightarrow{t_2}\{i\}\xrightarrow{t_1}\{i\}$, whereas the upper-score side stops at $\{i,j\}\xrightarrow{t_2}\{i,j\}$. Comparisons at $q$ and $t_2$ have equal weights on the two sides; the lower side alone has the final active $t_2\to t_1$ comparison. Hence
$$
\Delta A_i=-[h_{t_2}(p_i)-h_{t_1}(p_i)]
=-p_i(1/t_1-1/t_2)
$$
centrally, and it is $-\lambda_{t_1}(H_{t_2}-H_{t_1})$ for the composite null. This is the actual dilution term with differing stopping depths $\tau_-=3$, $\tau_+=2$, not an artificially repeated zero kernel.

As a finite arithmetic diagnostic, Python using only `statistics.NormalDist` and `math.erfc` exhaustively replayed all product-grid representatives for $N=1,\ldots,5$, $q=0.08$, and checked the central and weighted identities for $\theta_i=0,-1$. Across 16,952 identity evaluations, the peeling rank agreed with the largest qualifying BH rank; maximum absolute central error was $1.6653345369377348\times10^{-15}$, and maximum weighted error was $2.220446049250313\times10^{-16}$. This probes algebra and stopping conventions; it is not an estimate of PH-budget and is not used in the proofs.

### P4c. Signed original-Gaussian integration and exact composite correction

This is the attempted aggregate calculation, before taking any absolute value. All Gaussian densities and covariance coefficients remain those of the original positive-definite $C$; no independent-residual replacement or rank relaxation is made. For central nulls put $G_i(x,y)=g_{R(x,y)}(S(x))$. Its upward $j$-face jump is the nonnegative quantity $E_{i,j,l}=G_i(c^+,x)-G_i(c^-,x)$, explicitly the entry or dilution term in P4b. Hence their signed charge, still with every actual largest-rank mask, is
$$
\mathcal C_{\rm central}
=\sum_{\substack{i\in I_0:\theta_i=0}}\left\{
\sum_{j:C_{ij}<0}(-C_{ij})\sum_l\int f_{-i\mid i}(u_l,z\mid x)E_{i,j,l}(x,z)\,dz\,dx
-\sum_{j:C_{ij}>0}C_{ij}\sum_l\int f_{-i\mid i}(u_l,z\mid x)E_{i,j,l}(x,z)\,dz\,dx\right\}. \tag{P4-signed}
$$
This separates the actual adverse negative contacts from the favorable positive contacts without dropping either. Their signed integration is evaluated below together with the composite-null weight differences.

For any original null $i$, define the two path functions
$$
L_i(T)=\begin{cases}\mathbf1_{\{i\in\mathcal R_q(T)\}}/t_R,&R>0,\\0,&R=0,\end{cases}
\qquad
D_i(T)=\sum_{n=0}^{J-1}
\frac{\lambda_n-\lambda_{n+1}}{Q_i(t_n)}\,
\mathbf1_{\{i\in S_{n+1}\}}. \tag{P4-D}
$$
In this subsection $D_i$ is the explicitly indexed path correction, not the compensator $D_n$ indexed by stage in P1. Here $J=\tau-1$ and an empty sum is zero. Each summand is nonnegative. Its exact denominator is the actual preceding survival tail $Q_i(t_n)$, so it retains the original negative mean rather than substituting a central null. For a central null all these summands vanish.

First compute $\mathcal B$ directly, not by discarding its sign. At $n=0$ its per-null correction is $\lambda_i(q)-1$. At any later active stage where $i$ is alive, the per-history correction is
$$
\frac{r_n}{t_n}-\frac1{t_{n-1}}
=\frac{\lambda_n-\lambda_{n-1}}{Q_i(t_{n-1})}.
$$
The alive indicator is precisely $\mathbf1_{\{i\in S_n\}}$. Shift the index and sum the actual stages, including the last active comparison, to obtain the exact identity
$$
\mathcal B_i=\lambda_i(q)-1-\mathbb E D_i(T). \tag{P4-Bexact}
$$
In particular the entire future correction is retained; it is the expectation of the very weight-drop derivative appearing next.

Next integrate the paired faces of $\Gamma_i$ in P4-weighted, rather than identifying unrelated history descendants. The key own-coordinate regularity is as follows. As $x=T_i$ crosses one of its own grid values $u_l$, the two runs agree through the comparison where $i$ changes membership. The kernel of that comparison is continuous at its upper endpoint $b=u_l$. On the side where $i$ fails it has no later kernels. On the side where it passes, either the process immediately becomes stable, with no later comparison, or the next threshold is strictly larger than $u_l$. In the latter case, at $x=u_l$ the next kernel is at its lower endpoint $a=u_l$ and is zero, and $i$ then dies; any further kernels for $i$ are absent. Thus $A_i(x,y)$ is continuous across its own grid. The same holds for $\Gamma_i=\lambda_i(q)(1-S(x-\theta_i))-A_i$. This argument covers cascades of any length and uses the actual stopping convention. Other-coordinate ties occupy finitely many hyperplanes and have zero conditional Lebesgue measure in this positive-definite calculation.

Within a fixed open grid cell all $t_n,\lambda_n,R$ are fixed. Therefore differentiation of P4-weighted gives
$$
\partial_x\Gamma_i(x,y)
=\varphi_i(x)\left[
\frac{\lambda_J}{Q_i(t_J)}\mathbf1_{\{x>u_{m_J}\}}
+\sum_{n=0}^{J-1}\frac{\lambda_n-\lambda_{n+1}}{Q_i(t_n)}
\mathbf1_{\{x>u_{m_n}\}}\right]
=\varphi_i(x)[L_i(x,y)+D_i(x,y)]. \tag{P4-own}
$$
Indeed $\lambda_J/Q_i(t_J)=1/t_J$; for a stable nonempty terminal state this is $1/t_R$ with the rejection indicator, and for an empty terminal state the indicator is zero. Likewise the intermediate indicator is exactly $i\in S_{n+1}$: if $i$ died earlier, $x$ is already below a smaller score threshold and cannot exceed any later one. Threshold equalities may be ignored in differentiation and keep their non-strict deterministic convention. Own-coordinate continuity proves that there are no missing delta masses in P4-own.

Let $M_i(x)=\int\Gamma_i(x,y)f_{-i\mid i}(y\mid x)\,dy$. Gaussian translation differentiation and integration by parts in $y$, as in P2, imply distributionally on the finite grid
$$
M_i'(x)=\varphi_i(x)\mathbb E[L_i+D_i\mid T_i=x]
+\sum_{j\ne i}C_{ij}\int f_{-i\mid i}(y\mid x)\,d_{y_j}\Gamma_i(x,y).
$$
The second term is exactly the finite sum of original $j$-face jumps of $\Gamma_i$; its negative is the charge $\mathcal C_i$ because $\Delta A_i=-\Delta\Gamma_i$. In particular for central nulls it integrates the signed entry/dilution expression P4-signed, including the negative contacts, before taking absolute values.

Here all integrations over $x$ are justified for the fixed model. One can differentiate on the finitely many $x$ intervals and then concatenate: continuity eliminates internal own-grid endpoint terms. Every paired face is integrable by P2. Also $0\le A_i\le\lambda_i(q)(1-v)\le1$, with $v=S(x-\theta_i)$. For $x<U$, $i$ dies on the initial comparison, so $A_i=\lambda_i(q)(1-v)$; for $x>u_1$, every one of its at most $N+1$ terms is bounded by $Nv/q$, hence $A_i\le(N+1)Nv/q$. Thus $\sup_y A_i(x,y)$ is integrable in $x$ and tends to zero at both infinities. The derivatives of its individual pieces are bounded by a finite fixed-$N,q,\theta$ multiple of $\varphi_i(x)$. Differentiation of its conditional expectation is then justified with P2's translated-density bound. For $\Gamma_i$, subtract the smooth bounded base $\lambda_i(q)(1-v)$; its derivative is integrable and its base is independent of $y$, so its $\partial_x f$ contribution integrates to zero. This proves the displayed formula and its integrated version without a putative uniform inverse-covariance estimate.

The endpoint values are
$$
M_i(-\infty)=0,\qquad M_i(+\infty)=\lambda_i(q).
$$
They follow from $A_i\to0$ uniformly in $y$ and $\Gamma_i=\lambda_i(q)(1-v)-A_i$. Integration of $M_i'$ therefore gives the explicit terminal/interface residual
$$
\mathcal C_i
=\mathbb E[L_i(T)+D_i(T)]-\lambda_i(q). \tag{P4-Cexact}
$$
Combining this with P4-Bexact **after** retaining the actual composite correction cancels the expected weight-drop terms exactly:
$$
\mathcal C_i+\mathcal B_i=\mathbb E L_i(T)-1.
$$
Summing over the original labels, with no change of means or rejected denominators, leaves
$$
\boxed{\quad\mathcal C+\mathcal B
=\sum_{i\in I_0}(\mathbb E L_i-1)
=\frac Nq\operatorname{FDR}_{\rm BH}(q;N,\theta,C)-|I_0|.\quad} \tag{P4-saturation}
$$
For central nulls this was obtained by actually integrating P4-signed: the negative-contact entry/dilution mass minus its favorable positive-contact counterpart equals the unknown normalized terminal rejection mass minus one. For composite nulls the additional interface weight-drop mass is exactly offset by its actual nonpositive drift correction. It does not supply independently bounded Gaussian mass. This derivation is not merely a citation of PH-Doob: it evaluates the common-grid face coefficients, both divergent suffixes, the derivative of every retained weight difference, and both endpoint values, and shows precisely why their result returns to PH-Doob.

An additional finite positive-definite calibration independently checked P4-Cexact and P4-Bexact in $N=2$ with $q=0.08$, $\theta_j=1.2$, $\theta_i\in\{0,-0.7,-2\}$ and $C_{ij}=\rho\in\{-0.6,0.6\}$. Write $b=u_1$, $a=U=u_2$, $t_1=q/2$, $\lambda_0=Q_i(q)/q$ and $\lambda_1=Q_i(q/2)/(q/2)$. Only the $T_j=U$ face is active for $A_i$: across it the full actual jump is $-K_{a,b}(x)/t_1$, so
$$
\mathcal C_i=-\rho\int_U^\infty\frac{K_{U,u_1}(x)}{q/2}\,f_{j\mid i}(U\mid x)\,dx.
$$
Direct branch calculation on the same original bivariate Gaussian gives, independently of this face integral,
$$
\mathbb E L_i=\frac1q\Pr(T_i\ge U,T_j\ge U)
+\frac2q\Pr(T_i\ge u_1,T_j<U),\qquad
\mathbb E D_i=\frac{\lambda_0-\lambda_1}{Q_i(q)}\Pr(T_i\ge U,T_j<U).
$$
These are one-dimensional integrals using the original conditional normal mean $\theta_j+\rho(x-\theta_i)$ and variance $1-\rho^2$. Pure-Python adaptive Simpson integration, requested absolute tolerance $2\times10^{-12}$ and upper score cutoff $25$, compared the face integral with these branch integrals in all six cases. The maximum observed error in $\mathcal C_i=\mathbb E(L_i+D_i)-\lambda_0$ and $\mathcal C_i+\mathcal B_i=\mathbb E L_i-1$ was $4.2455691739995416\times10^{-12}$. For example $(\theta_i,\rho)=(-0.7,-0.6)$ gave $\mathcal C_i=0.001602345002762598$, $\mathbb E L_i=0.18067549237666997$ and $\mathbb E D_i=0.04145859888148696$. This is a numerical normalization/sign check only; finite quadrature and its tail cutoff are not used as proof or as a universal estimate.

## Failure

The first essential unproved gate is Step 4's PH-budget, after the completed deterministic and conditional-kernel calculations in P1--P4c. The actual original-Gaussian sibling allocation has been computed, including noncentral null means, rare histories, final active comparisons, common-grid pairing, two divergent suffixes, central entry/dilution, and the nonpositive composite drift. Its justified summation by parts and signed Gaussian integration terminate at P4-saturation. The remaining quantity is the unknown full-model FDR with its original largest-rank masks, not a new estimate.

To complete PH-budget this route would still require an **independent**, finite universal bound
$$
\sum_{i\in I_0}\mathbb E\!\left[\frac{\mathbf1_{\{i\in\mathcal R_q\}}}{t_R}\right]-|I_0|
\le A N(1+U),
$$
with the zero convention at $R=0$. By P4-saturation this is exactly the desired normalized FDR drift bound; no such bound has been derived. The explicit negative-contact mass P4-signed cannot be deleted on sign grounds, and the composite weight corrections do not repair this gap because P4-Bexact and P4-Cexact cancel them exactly. Bounding a free critical level, total negative degree, number of faces, or an inverse conditional variance has not been substituted for this missing estimate.

Per this plan's failure rule, this terminal-potential saturation marks the plan `failed`; Steps 1--3 are complete, Step 4's identities are complete but its aggregate bound is not, and Step 5 is not reached. The unchanged main target remains draft, with its statement and Proof untouched. This is neither a counterexample to the target nor evidence that PH-budget is false. No assertion about the singular transfer of an unproved budget or a uniform target constant is made.
