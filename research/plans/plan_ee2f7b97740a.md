---
type: plan
title: Universal one-sided order through compatible rank-chain Gaussian transport
status: failed
target_asset: gaussian_bh_one_sided_universal_order_upper
inspired_by:
  - idea_4f1da6c4220a
tags: []
---

## Goal

Target: [Universal order upper bound for one-sided Gaussian BH](../assets/gaussian_bh_one_sided_universal_order_upper.md).

Universal one-sided Gaussian BH order through compatible rank-chain Gaussian transport. Prove exactly gaussian_bh_one_sided_universal_order_upper: finite universal C_1 and q_{0,1}>0 with F_1(q)<=C_1 q sqrt(log(1/q)) for all 0<q<=q_{0,1}, every finite N>=1, every theta in R^N, and every unit-diagonal PSD Sigma including singular matrices. The original null set I_0={i:theta_i<=0}, non-strict BH comparisons, multiplicities and largest qualifying rank are fixed. All model parameters and null proportion may vary arbitrarily with q; no dimension, rank, factor, eigenvalue, means or direction restriction and no sharp-constant optimization is allowed. This converts the researcher's prioritized grouped-rank idea, while the existing pending global-shift plan remains an untouched standby. The proposed transport certificate is unproved and may fail independently of the target.

## Plan

1. [x] Fix 0<q<=barPhi(1), U=barPhi^{-1}(q), u_r=barPhi^{-1}(qr/N), alpha_i=1{i in I_0}, and actual FDP f. For 0<eta<=1 define C_a=[a Sigma+(1-a+eta^2)I]/(1+eta^2), T_a~N(theta,C_a), 0<=a<=1. Reprove finite-grid constancy and the independent baseline F_eta(0)<=q|I_0|/N, retaining negative null means. Derive F_eta'(a)=sum_{i<j} Sigma_ij/(1+eta^2) times the Gaussian-integrated mixed jumps. The old H was already Gaussian averaged: averaging is not the novelty. Check the i<j factor against trace double counting, N=1, empty nulls and endpoints. Failure: save the first incorrect boundary/independence identity; do not import an unproved old gate.
2. [x] Derive exact mixed-rectangle summation by parts with full rejection-set states BEFORE absolute values or scalar bounds. A face z=(i,j,r,s,B) has background open grid cell B and four quadrant rejection sets S_00 subset S_10,S_01 subset S_11, each computed by largest-rank BH; S_10 and S_01 may be incomparable. Let delta(S,S')=f(S')-f(S) for an actual nested transition; empty transitions contribute zero. Prove Delta_z f=1/2[delta(S_10,S_11)+delta(S_01,S_11)-delta(S_00,S_10)-delta(S_00,S_01)]. For k=|S|>=1, ell=|S'|, V=|S intersect I_0|, DeltaV=|(S'\S) intersect I_0|, retain delta=DeltaV/ell - V(1/k-1/ell) as ONE paired increment. For k=0 use delta=DeltaV/ell separately. Include all maximal-rank empty-gap/deficit constraints specifying B, all admitted sets, and complete cascades. Record the exact four-to-three-face reduction only as a consistency check, not as new progress beyond the failed three-face plan. Failure: any omitted state, cascade, c=0 or alternative-alternative face blocks the plan.
3. [x] Construct finite covariance-weighted transition currents. With phi_{theta,C_a} the FULL joint Gaussian density, m_z(a)=integral_B phi_{theta,C_a}(u_r,u_s,y)dy; include coordinate insertion i,j and counting multiplicities. Put w_z=Sigma_ij m_z/(1+eta^2). An oriented edge e=(S,S') records both actual rejection sets, hence k,ell and every admitted label. Aggregate J_e=1/2 sum_z epsilon_{z,e} w_z, where each top side has epsilon=+1 and bottom side -1, counted with multiplicity; cancel repeated identical edges exactly. Prove F_eta'=sum_e J_e delta_e. No independent Gram witness, beta(H), absolute covariance replacement, dropped background event, or deterministic-level lemma at a random rank is allowed. This finite incidence identity is algebraic reorganization only; it earns a new route only through the restricted transport certificate below. Failure: a merely renamed three-face coefficient or actual trace endpoint is not a certificate.
4. [x] Define and test the NEW auxiliary quantity, the compatible rank-chain transport deficit Q(a). For each edge e=(S,S') and true null h define d_{e,h}=1{h in S'}/ell - 1{h in S}/k, with the second term ZERO for k=0. Thus d=1/ell on entry, d=-(1/k-1/ell) on an old null, and zero otherwise. After forming J_e with all paired increments retained, set p_{e,h}=(J_e d_{e,h})_+, n_{e,h}=(-J_e d_{e,h})_+. A positive packet (e,h) may match a negative packet (g,h) only if the endpoints of e and g are totally ordered by set inclusion: both actual transitions lie on ONE nested rejection-set chain. Different null labels and incomparable branches cannot match. Form the finite bipartite max-flow with positive capacities p, negative capacities n and only those allowed arcs. Define Q=sum p - maximum matched mass. Prove measurability, Q>=0 and F_eta'<=Q by retaining unmatched negative mass with its sign. Prove the independent dual formula Q=max_{A subset positive packets}[sum_A p-sum_{Gamma(A)} n], including A empty. This maximum over finite compatible cut deficits, rather than tr(Sigma H) or its endpoint integral, is the new estimable object. It can be strictly stronger: incompatible negative packets cannot cancel a positive source. Failure: if admissibility is replaced by all-to-all matching and Q collapses to the positive actual trace, reject that replacement as a restatement.
5. [x] EARLY DECISION GATES before a general estimate: reconstruct N<=2 kernels and every Q packet from exact grid enumeration; verify nonzero alternative-alternative mixed faces for N>=3; check exact duplicated coordinates against weighted atomic BH (a block of multiplicity m contributes rank weight m, not one test), including singular limits; check padding by coordinates with negligible rejection probability with original N thresholds; check complete long cascades and alternating null/non-null admitted sets. Evaluate the cut deficits, not only raw coefficients or FDR. Finite Gaussian integrations/short numerics may diagnose Q but establish no universal theorem. Preserve negative true-null means and the audited weak-equicorrelation integrated-beta obstruction with its actual small Sigma_ij retained. Failure: a legal family forcing integral Q/[q(1+U)] to diverge falsifies this auxiliary certificate only; save it and stop without weakening the target.
6. [ ] FIRST CRITICAL UNPROVED GAUSSIAN GATE (GC): prove a finite universal A with integral_0^1 Q(a) da <= A q(1+U), simultaneously for all above finite models and 0<eta<=1. Attack its dual cut deficits directly, using the actual joint Gaussian density and Sigma, not a free covariance. Concrete allocation to attempt: split a maximizing cut's rectangles into their actual nested rejection-set chains; subtract the available compatible negative packet capacities; perform Gaussian integration by parts on the remaining union of grid cells, cancelling shared interior sides BEFORE estimating the exposed sides. Allocate each surviving side's paired new-null-entry/old-null-dilution coefficient to its retained rank interval [k,ell] and actual admitted true labels; keep terminal rank N and k=0 boundary terms explicitly. Use the maximal-rank inequalities on EVERY cell, negative mean weights, and actual covariance contraction in this allocation. A sufficient explicit certificate is a nonnegative residual measure dominated, after integration in a and allocation among true labels, by A(1+x)phi(x)1{x>=U}dx: its mass is A[q+phi(U)]<=Aq(U+2). Establish the map, capacities, IBP bulk/mean terms and this domination, rather than assuming a scalar tail bound for a selected rank. Alternative certificates must still bound the specified finite Q or all its cut deficits uniformly. The allocation and (GC) are obligations, not facts. Failure: uncancelled boundary/cut terms, log N, face/label multiplicity, inverse-noise or least-eigenvalue loss, or only an estimate of integral F_eta' is the precise stop condition; save first unproved formula and attempted allocation. No target proof may be written on that basis.
7. [ ] Only after (GC), integrate the exact derivative to obtain F_eta(1)<=q|I_0|/N+Aq(1+U). For each arbitrary fixed finite model couple T_{1,eta}=theta+(X+eta epsilon)/sqrt(1+eta^2), X~N(0,Sigma), epsilon~N(0,I) independent, and let eta down to zero. Continuous unit-variance marginals make the finite threshold union null even for singular Sigma, so bounded convergence transfers the ALREADY UNIFORM bound; do not exchange a supremum with a limit. Use U<=sqrt(2log(1/q)) and the target's stated sufficient criterion to exhibit finite universal C_1 and interval. Prove every technical estimate inline; write derivations into Progress in fresh-read patches of <=6000 tokens and obtain fresh independent verification before any approval. Failure at any prior gate leaves this conclusion unexecuted.

## Verification

Check full finite-N identities, signed factors and Gaussian integrations first. The new bound is specifically the integral of the finite compatible-chain max-flow deficit Q, with dual Hall-cut inequalities, and is stronger than the total actual interpolation gain. Paired false-entry/dilution increments and every maximal-rank background cell are retained until actual-covariance currents are formed. Proving (GC) and the independent baseline yields q+Aq(1+U); a finite-model bounded-convergence limit covers singular Sigma, and U<=sqrt(2log(1/q)) yields the exact universal order target, with all quantifiers unchanged. Neither a failed stronger certificate, deterministic telescoping, old three-face identity, per-face scalar bound nor a successful restricted/numerical example proves the target.

## Difference from failed plans

- [Actual-mean aggregate rank flux](plan_one_sided_order_actual_mean_global_flux_20261106.md): do not count inactive marginal crossings or separately center nulls. Mixed rectangles retain their full original background cells, then repeated actual rejection-set transitions are aggregated before any positive part. Positive packets can consume compatible negative packets; deterministic harmonic total variation is not the analytic certificate.
- [Signed Gaussian boundary interpolation](plan_one_sided_order_gaussian_interpolation_sdp_20261106.md): its boundary matrix was already Gaussian averaged. Retain the actual covariance coefficient in each current, rather than bounding an unweighted completion. The new finite max-flow/cut functional is defined after exact rank-transition incidence summation, and its restricted compatibility graph excludes arbitrary global signed cancellation. It is not a renamed matrix entry.
- [Actual negative-covariance contact transport](plan_one_sided_order_negative_contact_transport_20261106.md): retain both signs of the full covariance response and all alternative-alternative mixed rectangles. The proposed Gaussian integration by parts cancels interior sides of a compatible cut before estimating exposed sides. The earlier inverse-noise and background-boundary losses are explicit failure tests, not omitted terms.
- [Three-face contact and noise-scale packing](plan_one_sided_order_three_face_noise_packing_20261106.md): the exact three-face identity is old progress and must not be advertised as this plan's innovation. There is no independent Gram maximizer or integrated beta budget. The new object is the unmatched capacity in an explicitly restricted chain graph, with its independent Hall-cut dual. The weak-equicorrelation obstruction retains its actual small covariance multiplier here. A successful scalar or three-face calculation alone does not establish the new charge.

## Assumed definitions

Use only the target's approved [Gaussian model](../definitions/gaussian_multiple_testing_model.md), [Gaussian p-values and true nulls](../definitions/gaussian_test_pvalues.md), [ordinary BH](../definitions/benjamini_hochberg_step_up.md), [FDR](../definitions/false_discovery_rate.md), and [worst-case envelope](../definitions/gaussian_worst_case_bh_fdr.md). There are no assumed draft definitions or unproved dependency statements. All finite-grid differentiation, Gaussian integration by parts, independence baseline, max-flow duality, tail estimates and singular limits must be proved inline. Two planning-time library searches for Gaussian BH covariance interpolation/grouped rank boundaries and Gaussian summation-by-parts face transport returned no matching result. No library result is used as a black box or adapted.

## Certificate conventions and nontriviality gate

For Step 4, packets of zero capacity may be omitted. A transition with identical endpoints has zero increment and is discarded; every retained transition has ell>k, so no zero denominator occurs. The shared null label h is retained even when BOTH differentiated coordinates are alternatives: that null may enter through a cascade or be diluted. Chain compatibility is a defined restriction on the finite cancellation certificate; it is not an assertion that two different background realizations occur on one sample path. Algebra permits a matched positive and negative mass to cancel, while the compatibility restriction makes the certificate stronger. The capacity constraints prohibit using any sink twice.

Before calling Q a new analytic certificate, exhibit a legal finite Gaussian diagnostic or a proof from the BH incidence constraints that its proper cut family supplies information beyond the single total-current cut. If all that can be established is an all-to-all matching equal to the positive total contraction, save that as the first obstruction and stop. Exact representation and a newly named quantity alone do not prove Gaussian cancellation.

The residual-measure domination in Step 6 is an optional stronger allocation to attempt, not a premise or a redefinition of Q. Its tail mass is at most A q(U+2), which is at most 2A q(1+U); absorbing the universal factor gives (GC). A complete attempt must state what measure is allocated, how its mass dominates the max-flow deficit, why all bulk and exposed-boundary terms have been accounted for, and why the asserted domination holds for the full finite cut family, including cuts depending on a. A fixed-cut estimate followed by an unjustified exchange of a maximum and an expectation is insufficient.

## Preservation and execution boundary

This is one new pending plan, created through native conversion of [the prioritized idea](../ideas/idea_4f1da6c4220a.md). Native conversion resolves that idea by this plan without changing its body. The separate [global-shift standby](plan_one_sided_order_global_shift_record_stein_20261106.md) is neither edited nor executed nor declared failed. No main asset, source, approval or setting is changed. The native loop driver, reporting and selection remain the root agent's responsibility. Save each completed derivation and the first failed proposition into this plan using a fresh on-disk read and narrow patches of at most 6000 tokens; do not silently change the target or introduce a replacement statement.

## Progress

### Step 1: finite grid, independent baseline and covariance derivative

For local self-containment, the precise path and expectation used below are
$$
C_a=\frac{a\Sigma+(1-a+\eta^2)I}{1+\eta^2},\qquad
T_a\sim\mathcal N_N(\theta,C_a),\qquad F_\eta(a)=\mathbb E[f(T_a)],\qquad0\le a\le1,\quad0<\eta\le1.
$$
The mean vector and its original null labels stay fixed along this path.

Fix the model in the frozen statement and put $\alpha_i=\mathbf1\{\theta_i\le0\}$. Throughout this execution $0<q\le\overline\Phi(1)$, $U=\overline\Phi^{-1}(q)$ and $u_r=\overline\Phi^{-1}(qr/N)$ for $1\le r\le N$; hence $u_1>\cdots>u_N=U$. Off the finite union of threshold hyperplanes, define a coordinate's bin by
$$
b_i(t)=\min\bigl(\{r:t_i>u_r\}\cup\{N+1\}\bigr).
$$
For each $b\in\{1,\ldots,N+1\}^N$, let $D_b$ be the corresponding open rectangular cell and $c_r(b)=\#\{i:b_i\le r\}$. Its BH rank and set are exactly
$$
K(b)=\max(\{0\}\cup\{r:c_r(b)\ge r\}),\qquad S(b)=\{i:b_i\le K(b)\}.
$$
If $K>0$, $c_K=K$: otherwise $l=c_K>K$ would satisfy $c_l\ge c_K=l$, contradicting maximality. Thus $|S|=K$ and $f$ is constant on $D_b$, with value $\sum_{i\in S}\alpha_i/(K\vee1)$. Equivalently, $K=k\ge1$ iff $c_k=k$ and $c_r<r$ for every $r>k$; $K=0$ iff $c_r<r$ for every $r\ge1$. These conditions retain every maximal-rank deficit rather than testing a single crossing. Non-strict comparisons differ only on the threshold hyperplanes, which have probability zero under every unit-variance Gaussian marginal, including singular joint laws.

At $a=0$, $C_0=I$. Write $R_i^0$ for the BH rejection count when $p_i$ is replaced by zero. If $p_i\le qR_i^0/N$, then the original vector qualifies at rank $R_i^0$ (all $R_i^0-1$ other rejections remain below this threshold), and monotonicity gives $R=R_i^0$. Conversely, if $i$ is originally rejected, replacing its already rejected p-value by zero does not change any qualification above $R$, because it remains among the p-values below each threshold above $R$. Hence it does not change $R$, and $p_i\le qR_i^0/N$. Also $R_i^0\ge1$. Independence gives
$$
\mathbb E\frac{\mathbf1\{i\text{ rejected}\}}{R\vee1}
=\sum_{r=1}^N\frac{\mathbb P(R_i^0=r)}r\mathbb P(p_i\le qr/N)
\le\frac qN\sum_{r=1}^N\mathbb P(R_i^0=r)=\frac qN
$$
for each $\theta_i\le0$, since $\mathbb P(p_i\le t)=\overline\Phi(\overline\Phi^{-1}(t)-\theta_i)\le t$. This retains negative null means and proves $F_\eta(0)\le q|I_0|/N$.

For $\eta>0$, $C_a\succeq\eta^2 I/(1+\eta^2)$ uniformly on $[0,1]$, so its full density $\varphi_a=\varphi_{\theta,C_a}$ and all relevant derivatives are bounded by fixed-model integrable Gaussian-polynomial envelopes. Direct differentiation of the density gives $\partial_a\varphi_a=\tfrac12\sum_{i,j}(C'_a)_{ij}\partial_{ij}\varphi_a$: indeed both sides equal
$$
\frac{\varphi_a}2\left[(t-\theta)^{\mathsf T}C_a^{-1}C'_aC_a^{-1}(t-\theta)-\operatorname{tr}(C_a^{-1}C'_a)\right].
$$
Here $(C'_a)_{ii}=0$ and $(C'_a)_{ij}=\Sigma_{ij}/(1+\eta^2)$ for $i\ne j$. The two symmetric ordered terms cancel the factor $1/2$, leaving one coefficient per $i<j$. Therefore $F_\eta$ is continuously differentiable, including one-sided derivatives at the endpoints, and
$$
F'_\eta(a)=\sum_{i<j}\frac{\Sigma_{ij}}{1+\eta^2}\int f(t)\,\partial_{ij}\varphi_a(t)\,dt.
$$
Integrate over the finitely many cells, then over $t_i,t_j$. Contributions at infinity vanish. At each threshold pair $(u_r,u_s)$ the signed four-cell value is $f_{11}-f_{10}-f_{01}+f_{00}$, where bit 1 means the higher $t$ side. Thus, writing $B$ for any open cell of the remaining $N-2$ coordinates and inserting $i,j$ in their original positions,
$$
F'_\eta(a)=\sum_{i<j}\sum_{r,s=1}^N\sum_B\frac{\Sigma_{ij}}{1+\eta^2}\left[\int_B\varphi_a(t_i=u_r,t_j=u_s,y)\,dy\right](f_{11}-f_{10}-f_{01}+f_{00}).
$$
There is no omitted marginalization: $B$ is retained inside the full density integral. For $N=1$ the sum is empty and the covariance path is constant; for an empty null set every cell value and both sides are zero. This is an exact finite identity and makes no uniform estimate.

### Steps 2 and 3: complete states, paired transitions and actual currents

For a face $z=(i,j,r,s,B)$, let the background bins be $(b_h)_{h\ne i,j}$. In quadrant $v=(v_i,v_j)\in\{0,1\}^2$, insert bins $b_i=r+1-v_i$, $b_j=s+1-v_j$. The following gives every constraint on that face, including all deficits and all labels:
$$
c_t^v=\#\{h\ne i,j:b_h\le t\}+\mathbf1\{r+1-v_i\le t\}+\mathbf1\{s+1-v_j\le t\},
$$
$$
K_v=\max(\{0\}\cup\{t:c_t^v\ge t\}),\quad
S_v=\{h\ne i,j:b_h\le K_v\}\cup\{i:r+1-v_i\le K_v\}\cup\{j:s+1-v_j\le K_v\}.
$$
In this notation $\{i:\cdots\}$ means either the singleton $\{i\}$ or the empty set. Equivalently, for each proposed $k_v\ge1$ require $c_{k_v}^v=k_v$ and all $c_t^v<t$ for $t>k_v$; for $k_v=0$ require all $c_t^v<t$. Intersect these conditions for all four $v$. This is an explicit finite enumeration rule, rather than a relaxation of the background cell. Every admitted label for an edge is the exact set difference of its two computed sets. There is no bound on the jump size, so complete cascades are included.

If a p-value decreases, every qualifying rank stays qualifying, hence $K$ cannot decrease. Every previously rejected coordinate remains below the new larger threshold, so its label remains rejected. Thus $S_{00}\subseteq S_{10},S_{01}\subseteq S_{11}$. Whenever $S\subsetneq S'$ is a side, put $k=|S|$, $l=|S'|$, $V=\sum_{h\in S}\alpha_h$ and $\Delta V=\sum_{h\in S'\setminus S}\alpha_h$. Direct subtraction gives
$$
\delta(S,S')=\begin{cases}\Delta V/l-V(1/k-1/l),&k>0,\\ \Delta V/l,&k=0.\end{cases}
$$
The entry and dilution terms are kept together in $\delta$ until the currents have been summed. For identical endpoints set $\delta=0$. Pure telescoping, before any absolute value, gives
$$
f_{11}-f_{10}-f_{01}+f_{00}
=\tfrac12\left[\delta(S_{10},S_{11})+\delta(S_{01},S_{11})-\delta(S_{00},S_{10})-\delta(S_{00},S_{01})\right].
$$

For a check on the earlier three-face description, a nontrivial crossing of coordinate $i$ at $u_r$ must have upper rank exactly $r$: counts at every other rank stay fixed, and if any rank greater than $r$ qualified, its rejection set would stay fixed too. Consequently, if $r<s$ and there is a nonzero mixed jump, both upper-$j$ sets coincide, $S_{01}=S_{11}$, and the remaining three sets form $S_{00}\subseteq S_{10}\subseteq S_{01}$. To see the common top directly, qualification at and above $s$ is independent of the $i$ bit, since both possible $i$ bins are at most $s$. If the $j$ crossing changes neither $i$ state, the mixed jump is zero. If it changes one, rank $s$ qualifies in both upper-$j$ states and no greater rank qualifies, giving the common set. The case $r>s$ interchanges $i,j$. If $r=s$, all ranks other than $r$ are unchanged. If a larger rank qualifies all sets coincide; otherwise a change requires exactly $r-2$ background coordinates with bin at most $r$, and then $S_{00}=S_{10}=S_{01}\subseteq S_{11}$, with upper rank $r$. A background count at least $r-1$ would force rank $r+1$ in every quadrant (when $r<N$); at $r=N$ that count exceeds the $N-2$ available background coordinates. These are consistency checks of the exact four-state rule, with no new analytic estimate.

Let $\mathcal E$ be the finite set of all distinct proper ordered set pairs $(S,S')$ that occur as sides in the above enumeration. Retain each occurrence: repeated sides on the same rectangle count twice if they occur twice. Define
$$
m_z(a)=\int_B\varphi_a(t_i=u_r,t_j=u_s,y)\,dy,\qquad
w_z(a)=\frac{\Sigma_{ij}}{1+\eta^2}m_z(a),
$$
$$
J_e(a)=\tfrac12\sum_z\epsilon_{z,e}w_z(a),
$$
where $\epsilon_{z,e}$ is the number of occurrences of $e$ among $(S_{10},S_{11}),(S_{01},S_{11})$ minus its number among $(S_{00},S_{10}),(S_{00},S_{01})$. Discard identical-endpoint sides. This includes the actual signed $\Sigma_{ij}$ and the full background event. Substitute the four-state telescoping identity into Step 1 and interchange the finite sums to obtain
$$
F'_\eta(a)=\sum_{e\in\mathcal E}J_e(a)\delta_e.
$$
This sums repeated actual transitions before any sign separation. No Gram witness or covariance bound has entered. It remains an exact algebraic identity, not the Gaussian gate.

### Step 4: compatible flow and its independent finite Hall dual

For $e=(S,S')$ with $k=|S|<l=|S'|$ and each $h\in I_0$, define
$$
d_{e,h}=\frac{\mathbf1\{h\in S'\}}l-\begin{cases}\mathbf1\{h\in S\}/k,&k>0,\\0,&k=0.\end{cases}
$$
Then $\delta_e=\sum_{h\in I_0}d_{e,h}$. Set $p_{e,h}=(J_ed_{e,h})_+$ and $n_{e,h}=(-J_ed_{e,h})_+$. Fix the vertex set of all edge-label pairs once and for all, allowing zero capacities. A positive vertex $(e,h)$ is joined to a negative vertex $(g,h')$ exactly when $h=h'$ and all four endpoints of $e,g$ are totally ordered by inclusion. This fixed graph retains the same null label and every actual set. In particular, no conclusion about simultaneous sample paths is used.

Put $P=\sum p$ and $D=\sum n$. The network has a source connected to positive vertices with capacity $p$, negative vertices connected to a sink with capacity $n$, and the allowed middle arcs with capacity $M=1+P+D$. A feasible flow is a finite nonnegative vector with capacity constraints and conservation at internal vertices. Its feasible set is nonempty and compact, hence its value attains a maximum $L$. Necessarily $L\le\min(P,D)$. Define $Q=P-L\ge0$.

For completeness, maximum flow equals minimum cut here without an assumed combinatorial theorem. At a maximal flow construct the residual digraph, placing forward arcs with residual capacity and reverse arcs wherever the current flow is positive. A source-to-sink residual path would allow increasing the flow by the minimum of its finitely many strictly positive residual capacities; hence there is no such path. Let $W$ consist of the vertices reachable from the source. The sink is outside $W$; all forward arcs from $W$ are saturated, and all original arcs into $W$ carry zero flow. Summing conservation over $W$ shows that the flow value equals the capacity of its outgoing cut. Every feasible flow is at most every cut capacity by the same conservation sum, proving equality.

The cut containing only the source has capacity $P<M$, so no minimum cut crosses a middle arc. If $A$ is its set of positive vertices on the source side, every neighbor $\Gamma(A)$ must be on that side. Additional negative vertices can only increase cut capacity and can be removed. The resulting capacity is $P-p(A)+n(\Gamma(A))$; conversely each such choice is a valid cut. Therefore the exact independent dual is
$$
Q(a)=\max_{A\subseteq\mathcal P}\{p(A)-n(\Gamma(A))\},
$$
where $\mathcal P$ is the fixed finite positive-vertex index set, and the empty set supplies zero. Zero-capacity positive vertices do not improve the maximum because they can only enlarge the neighborhood. Each $m_z(a)$ is continuous on $[0,1]$ by the fixed-model Gaussian envelopes from Step 1, so $p,n$ and this finite maximum are continuous, in particular measurable. After an optimal matching, unmatched positive mass is $P-L=Q$ and unmatched negative mass is $D-L\ge0$. Hence
$$
F'_\eta(a)=P-D=Q-(D-L)\le Q.
$$
This keeps every remaining negative sign. The graph is not replaced by all-to-all matching; the next diagnostic shows that its proper cuts can supply strictly different information from the total derivative.

### Step 5(a): all kernels and packets for $N\le2$, including a strict proper-cut diagnostic

For $N=1$ the derivative, currents and packets are all zero, so $Q=0$. For $N=2$ write $\alpha_1,\alpha_2\in\{0,1\}$, $w_{rs}=\Sigma_{12}\varphi_a(u_r,u_s)/(1+\eta^2)$, with the actual means retained in the density. In row order $(r,s)=(1,1),(1,2),(2,1),(2,2)$, direct use of the four-state rule gives mixed jumps
$$
0,\quad-\alpha_1,\quad-\alpha_2,\quad(\alpha_1+\alpha_2)/2.
$$
The states at $(1,2)$ are $(\varnothing,\{1\},\{1,2\},\{1,2\})$; at $(2,1)$ they are $(\varnothing,\{1,2\},\{2\},\{1,2\})$; at $(2,2)$ they are $(\varnothing,\varnothing,\varnothing,\{1,2\})$. At $(1,1)$ all four states reject both coordinates. With $E_{01}=(\varnothing,\{1\})$, $E_{02}=(\varnothing,\{2\})$, $E_{0t}=(\varnothing,\{1,2\})$, $E_{1t}=(\{1\},\{1,2\})$, $E_{2t}=(\{2\},\{1,2\})$, every current is
$$
(J_{01},J_{02},J_{0t},J_{1t},J_{2t})=(-w_{12}/2,-w_{21}/2,w_{22}-(w_{12}+w_{21})/2,w_{12}/2,w_{21}/2).
$$
For null label 1, the signed packet masses in this edge order are
$$
(-w_{12}/2,0,[w_{22}-(w_{12}+w_{21})/2]/2,-w_{12}/4,w_{21}/4).
$$
For null label 2 they are
$$
(0,-w_{21}/2,[w_{22}-(w_{12}+w_{21})/2]/2,w_{12}/4,-w_{21}/4).
$$
Their positive and negative parts give every $p,n$, also for negative covariance and negative null means. If a label is alternative its entire row is omitted. The only incompatibilities are between an edge using singleton $\{1\}$ and an edge using singleton $\{2\}$; $E_{0t}$ is compatible with every edge. These rows and this graph give the complete finite $N=2$ Hall calculation, rather than just its raw mixed kernel.

Here is an analytic legal diagnostic proving the graph matters. Take $\theta_1=\theta_2=0$, both labels null, $q=\overline\Phi(1)$, $\eta=1$, and $\Sigma_{12}=\rho>0$ sufficiently small. At $a=0$, write $b=w_{12}=w_{21}>0$ and $c=w_{22}>0$. The covariance is then $I$, while the actual derivative multiplier is $\rho/2$. If $v=u_1>1=u_2$, then
$$
\frac cb=\frac{\phi(1)}{\phi(v)}\in(1,2).
$$
The upper bound follows from $\overline\Phi(1)=2\overline\Phi(v)$ and strict increase of the Gaussian hazard $h(x)=\phi(x)/\overline\Phi(x)$: for $x>0$, integration of $t\phi(t)$ gives $x\overline\Phi(x)<\phi(x)$, so $h'(x)=h(x)(h(x)-x)>0$, and $c/b=2h(1)/h(v)<2$. For each label the positive branch packet of mass $b/4$ on the opposite-singleton edge has no compatible negative neighbor; it cannot use the negative packets on the same-label singleton branch. The central positive packet has mass $(c-b)/2$ and can use all negative mass $3b/4$. Thus the exact dual or direct matching gives
$$
Q=2\max\{b/4,c/2-b\}=\max\{b/2,c-2b\}=b/2>0,
\qquad F'_\eta(0)=c-2b<0.
$$
This strict separation persists on a small $a$ interval by continuity. It uses a legal positive-definite model and actual $\rho$, not a free covariance. It verifies nontriviality of $Q$, without establishing its proposed universal integral bound.

### Step 5(b): alternative faces, duplicated atoms, padding and complete cascades

An alternative-alternative mixed face need not vanish. Take $N=3$, $i=1,j=2$ alternative, $h=3$ null, and a background bin $b_3=2$. At $r=s=3$ the states are $(\varnothing,\varnothing,\varnothing,\{1,2,3\})$, so the mixed FDP jump equals $1/3$. For example $\theta=(1,1,0)$ and $\Sigma_{12}=\rho\in(0,1)$, $\Sigma_{13}=\Sigma_{23}=0$ give a legal positive-definite model. The background interval $(u_2,u_1)$ has strictly positive mass under the full density for every $a,\eta$, so this face has nonzero actual weighted flux. It creates the label-3 packet $w_z/3$ before aggregation with other faces. The graph construction therefore includes that label even though neither differentiated coordinate is null. A local face is not by itself a lower bound on aggregate $Q$: repeated-edge currents must first be summed, as in Step 3.

For exact duplicate coordinates, partition the tests into atoms $A_j$ of multiplicities $m_j$, with identical observed p-value $p_j$ within each atom and $\sum_jm_j=N$. Sort atom p-values, combining tied atoms if desired, and put $W_j=\sum_{v\le j}m_v$. If any rank $k$ inside block $j$ qualifies, $p_j\le qk/N\le qW_j/N$, so its endpoint $W_j$ qualifies. Thus the largest qualifying rank is a block endpoint; its rejection set contains whole atoms and its false count uses their original labels. The exact weighted atomic rule is
$$
\widehat j=\max(\{0\}\cup\{j:p_j\le qW_j/N\}),\quad R=W_{\widehat j},\quad
V=\sum_{v\le\widehat j}\sum_{h\in A_v}\alpha_h.
$$
It is not BH on the number of atoms. Its paired increment on a nested atom transition uses the same weighted counts $k,l,V,\Delta V$ as Step 2. At the level of packets, every duplicate original label is still a separate label with its own capacity; replacing a multiplicity-$m$ atom by one label would change the certificate. For $\eta>0$ the path adds independent noise, so exact duplicates do not persist and no reduction of the intermediate $Q$ to atomic BH is asserted. At the singular endpoint, the coupling $T_{1,\eta}=\theta+(X+\eta\varepsilon)/\sqrt{1+\eta^2}$ converges almost surely to $\theta+X$. Its coordinates have continuous unit-variance marginals, so no grid threshold is hit with positive probability even when coordinates coincide. Hence all cell and rejection-set values converge almost surely, and bounded convergence verifies the atomic endpoint FDR. This gives no uniform $\eta$ bound on $\int Q$ and does not bypass the Gaussian gate.

Padding also retains the original denominator. With $M$ active p-values and $N-M$ p-values identically 1, the qualifying ranks are at most $M$ and the procedure is exactly BH on the active coordinates at level $q'=qM/N$. Indeed $q'r/M=qr/N$ for every $r\le M$. Padding by Gaussian coordinates of means tending to $-\infty$ gives this rule almost surely under a fixed Gaussian coupling. For each fixed finite model, fixed $\eta>0$ and $a$, the corresponding currents converge to active-coordinate currents with the original thresholds: background events involving rejection of padding coordinates vanish; faces fixing a padding coordinate at a finite $u_r$ vanish since their integrals are bounded by that coordinate's marginal density times a fixed-model bounded conditional density. All active faces with $r>M$ or $s>M$ are inactive. The finite Hall maximum therefore converges to the active $M$-coordinate $Q$ at $q'$, with zero padding packets. No supremum or uniform-noise limit is interchanged here. Negative padding means remain true-null means throughout.

Complete cascades of any length occur in the grid enumeration. Fix $0\le k<l\le N$, put $k$ labels in bin $k$ when $k>0$, put another $l-k-1$ labels in bin $l$, and put all other labels in bin $N+1$. A trigger coordinate crosses from bin $l+1$ to bin $l$ (if $l=N$, the lower bin is $N+1$). Below the crossing, the largest rank is $k$; above it, it is $l$. Every intermediate rank $k<t<l$ has count exactly $k<t$, and all ranks above $l$ have count at most $l<t$. Thus every admitted label is included in the one transition, with entry coefficient $1/l$ and, for each old null, dilution coefficient $-(1/k-1/l)$. The null/alternative labels in the admitted block may alternate arbitrarily because any finite means with those signs have positive Gaussian density on this open cell for $\eta>0$. This checks $k=0$, $l=N$, long cascades and alternating masks without truncating them to adjacent rank changes. The graph tests inclusion of all actual endpoint labels; it cannot redistribute these capacities across incomparable branches.

A short finite diagnostic additionally enumerated all grid cells at $a=0$, $q=0.01$, $\eta=1$, $\theta=0$ and actual equicorrelation $\Sigma_{ij}=1$ for $i\ne j$ (the original matrix is singular and admissible; $C_0=I$). Each upper bin has probability $q/N$ and the bottom bin has probability $1-q$, so the full Gaussian face integral is the exact product of two univariate densities and the background cell probabilities. Summing all repeated-edge currents and performing augmenting-path matching separately for one label (then multiplying by symmetry by $N$) gave the following floating-point checks:

| $N$ | $Q(0)$ | $F'_\eta(0)$ |
|---|---:|---:|
| 2 | $9.6345781845\,10^{-5}$ | $-3.0214785362\,10^{-5}$ |
| 3 | $1.3976798227\,10^{-4}$ | $-4.0839769326\,10^{-5}$ |
| 4 | $1.6646456327\,10^{-4}$ | $-4.6319174843\,10^{-5}$ |
| 5 | $1.8529607427\,10^{-4}$ | $-4.9683483048\,10^{-5}$ |

This is a diagnostic of the actual cut deficits and their sign separation, not an integrated bound or asymptotic result. The calculation kept $\Sigma_{ij}/(1+\eta^2)=1/2$ in the mixed derivative and the incidence factor $1/2$ in $J$. No unweighted completion or independent covariance witness was substituted.

### Step 6 attempt: exact Hall-cut boundary coefficients and the first analytic obstruction

Fix $a$ and a cut $A$ in the finite dual from Step 4. For every edge-label pair put
$$
\chi^A_{e,h}=\begin{cases}\mathbf1\{(e,h)\in A\},&J_ed_{e,h}>0,\\
\mathbf1\{(e,h)\in\Gamma(A)\},&J_ed_{e,h}<0,\\0,&J_ed_{e,h}=0,\end{cases}
\qquad \beta_e^A=\sum_{h\in I_0}d_{e,h}\chi^A_{e,h}.
$$
This retains the sign of each matched-neighborhood term; in particular a negative selected packet contributes $J_ed_{e,h}$, not its absolute value. Substitution into the Hall deficit gives the exact identities
$$
D_A(a):=p(A)-n(\Gamma(A))=\sum_eJ_e(a)\beta_e^A(a)
=\sum_z\frac{\Sigma_{ij}}{1+\eta^2}m_z(a)\,\gamma_z^A(a),
\qquad\gamma_z^A=\tfrac12\sum_e\epsilon_{z,e}\beta_e^A.
$$
All coefficients are explicit finite functions of the original currents. No maxima or signs have been moved through an expectation. The remaining required expression is precisely
$$
\int_0^1\max_{A\subseteq\mathcal P}\left\{
\sum_{i<j}\sum_{r,s,B}\frac{\Sigma_{ij}}{1+\eta^2}
\gamma_{i,j,r,s,B}^A(a)\int_B\varphi_a(u_r,u_s,y)\,dy\right\}\,da.
\tag{GC-rem}
$$
To finish the plan this must be bounded by $A_0q(1+U)$ with one finite universal $A_0$, independently of $N,\theta,\Sigma,\eta$. Estimating only the same sum with $\beta_e=\delta_e$ would recover $F'_\eta$ and would not control (GC-rem).

The first proposed cancellation was to put the retained $\beta$ on nested rejection-set chains and telescope interior sides as a state potential $G(S')-G(S)$. This is already invalid for a legal proper cut in Step 5(a). For null label 1, take the positive packet on $E_{2t}$ alone when $w_{12}=w_{21}=b>0$ and $c>b$. Its only potentially negative compatible edges have zero capacity; the two negative singleton-1 branch packets are incompatible. Thus its exact cut has $\beta_{2t}=1/2$ and every other $\beta=0$. Along the two actual nested paths from $\varnothing$ to $\{1,2\}$,
$$
\beta_{01}+\beta_{1t}=0,\qquad \beta_{02}+\beta_{2t}=1/2.
$$
No function $G$ on actual rejection sets has these edge differences. The uncompensated cut value is exactly $b/4$, not zero. This demonstrates a retained interior-chain interface, rather than proving divergence of its Gaussian integral. A more general allocation that charges such interfaces instead of erasing them remains possible; no path independence may be presumed.

An integration-by-parts attempt on the actual Gaussian cells likewise leaves a term that has not been controlled uniformly. For each face and fixed $t_j=u_s,y\in B$, let $s_a(t)=C_a^{-1}(t-\theta)$ be the full score. Direct integration of $-\partial_i\varphi_a=s_{a,i}\varphi_a$ from $u_r$ to infinity gives, including every background condition,
$$
m_z(a)=\int_B\int_{u_r}^{\infty}s_{a,i}(t_i,u_s,y)\varphi_a(t_i,u_s,y)\,dt_i\,dy.
$$
Therefore (GC-rem) has an exact representation with the integrand
$$
\sum_{i<j,r,s,B}\frac{\Sigma_{ij}\gamma_z^A}{1+\eta^2}
\int_B\int_{u_r}^{\infty}s_{a,i}(t_i,u_s,y)\varphi_a(t_i,u_s,y)\,dt_i\,dy.
\tag{cut-score}
$$
This identity includes the mean terms through $t-\theta$, including negative null means. A second integration in coordinate $j$, with the background cell $B$ held fixed, gives exactly
$$
m_z(a)=\int_B\int_{u_r}^{\infty}\int_{u_s}^{\infty}
\left[s_{a,i}(t)s_{a,j}(t)-(C_a^{-1})_{ij}\right]\varphi_a(t)\,dt_j\,dt_i\,dy.
$$
Indeed $\partial_{ij}\varphi_a=[s_{a,i}s_{a,j}-(C_a^{-1})_{ij}]\varphi_a$, and integrating $\partial_{ij}\varphi_a$ over this two-coordinate orthant yields $\varphi_a(u_r,u_s,y)$. Neither this operation nor (cut-score) differentiates $B$, so neither creates a background-interface term. Background interfaces would have to be accounted for in a separate attempted differentiation or summation across adjacent background cells, where $\gamma_z^A$ may change; no such cancellation identity has been established here. The nonzero circulation above obstructs the proposed rejection-state-potential telescoping, independently of these fixed-$B$ Gaussian integrations.

Using absolute score bounds would introduce $C_a^{-1}$ or conditional inverse variances. In particular the a priori spectral estimate is only
$$
\|C_a^{-1}\|_{\mathrm{op}}\le\frac{1+\eta^2}{1-a+\eta^2},\qquad
\int_0^1\frac{da}{1-a+\eta^2}=\log\frac{1+\eta^2}{\eta^2},
$$
which has no uniform $\eta$ bound. The first inequality follows directly from $\Sigma\succeq0$. This is a loss in this attempted estimate, not a claim that (GC-rem) itself diverges. The actual covariance contraction cannot simply remove it: the identity $\sum_j(C_a)_{ij}s_{a,j}=t_i-\theta_i$ sums all $j$ with one common coefficient, whereas (cut-score) selects different ranks, backgrounds, and cut coefficients for each pair. No identity equating these differently restricted sums has been established. Replacing them by that full contraction would discard the unresolved interfaces.

Thus neither a nonnegative residual measure of sufficient mass nor its proposed domination by $A_0(1+x)\phi(x)\mathbf1\{x\ge U\}dx$ has been constructed. Rank intervals $[k,l]$ alone do not fix the displayed nonzero cut circulation; their old-null dilution and new-null entry coefficients were already retained in $d$ before the cut was taken. A fixed-cut Gaussian endpoint estimate would also be insufficient, since the maximum in (GC-rem) is taken separately at each $a$. No exchange of that maximum with the a-integral, no uniform bound, and no target proof is asserted here.

### Scope of fresh independent checks received during execution

Two fresh read-only checks, communicated by the root, found no blocking defect in the then-frozen Step 1–3 derivations and in Step 4 plus Step 5(a), respectively. Their reported stable block digests were `f1304947fb41a1a743ea892e2c6303c008eac98d8663a7fe9994a314e76c9d0c` and `b384e20e3bdc62403f217a51a65547d18fc81e76530ba601ce5d041726b4de2e`. The subsequently appended explicit path definition only makes the already specified $C_a,F_\eta$ local. These checks exclude Step 5(b), the Gaussian gate, any uniform singular limit, and the canonical target. They do not constitute verification of the main theorem or approval.

### Step 5(c): retaining the audited weak-equicorrelation scale

The root supplied the exact prior audited family from [the weak-equicorrelation obstruction record](../ideas/idea_61f383a494e4.md), solely to check that its actual covariance was not replaced by an unweighted completion. For fixed $0<q\le0.01$, even $N$, and $v_N=\sqrt{2\log N}$, its means are $-6/v_N$ on half the labels and $\kappa/v_N$ on the others, with $\kappa=2\log(2/q-e^{-3})>0$. For a fixed sufficiently small $t=t(q)>0$, its correlation is
$$
\rho_N=2t/v_N^2,\qquad \Sigma_N=(1-\rho_N)I+\rho_N\mathbf1\mathbf1^{\mathsf T},\qquad\eta=1.
$$
For large enough $N$, this is admissible; the negative means are true nulls, the positive means are alternatives, and the endpoint off-diagonal covariance along the present path is $\rho_N/2=t/v_N^2$. The source's previously audited positive fixed-$q,t$ endpoint gain and unweighted completion obstruction are not reproved here. They are not new evidence against (GC): every current in the present construction retains the factor $\rho_N/2$, rather than deleting it. The old estimate $\Delta F_N\le(\rho_N/2)\int\beta(H_N)\,da$ can force the unweighted integral to grow like $\log N$ while retaining only a fixed weighted gain. For the new certificate the exact relation is $\int Q_N\,da\ge\Delta F_N$; no dimension-divergent lower bound for $\int Q_N$ follows from that old unweighted estimate. The root identified the fresh prior audit block as source lines 292–398, digest `a5654df6756657aa2c3f3296648c0517e4beb71651caa527d4459818e8948b78`. This paragraph preserves that checked model scale and explicitly separates imported audit evidence from derivations completed in this execution.

### Final scoped audit and correction

A third fresh read-only reviewer independently checked Step 5(b) and Step 6, including the diagnostics and fixed-model limits. It identified one local overstatement: integration by parts in the second exposed coordinate, with background region B fixed, creates the ordinary two-coordinate Gaussian Hessian score and no background-interface terms. The author corrected that sentence and distinguished the separate non-potential chain obstruction from the inverse-noise score estimate. The reviewer then accepted the correction and rechecked the corrected Step 5(b)/6 block, then lines 188–268, SHA-256 345e52c4d7175e2f82b4d70f7a6c4609069807a801c14b0f22264dcc3f47db01; the corrected Failure block, then lines 281–287, had SHA-256 9c68ff65257a150115266655c6ed1b6da0f733eb58d110df641c7c76e378ec79. The whole pre-note snapshot was 20e3057b61daff5ac8e2546d887e244e5a899995c1e034173afca7184393da58. No further blocking local defect was found. The uniform integral of Q, the singular transfer of such a bound, and the main theorem remain unproved; these scoped checks are not native target verification or approval.

## Failure

The first unproved essential gate is Step 6, specifically the uniform bound for (GC-rem), the a-integral of the finite compatible Hall-cut maximum. Steps 1–4 give exact finite-grid identities and a genuine restricted max-flow certificate; Step 5 supplies the stated diagnostics and retains the old obstruction's actual covariance scale. None of these bounds (GC-rem) uniformly.

The attempted chain allocation cannot telescope every selected packet as a rejection-set potential: the legal two-test cut displayed in Step 6 has circulation $1/2$ between two nested paths, leaving actual Gaussian cut mass $b/4$. Separately, direct Gaussian integration by parts with $B$ fixed gives (cut-score) and the displayed two-coordinate score identity without background-interface terms; bounding the scores by the available inverse-covariance estimate introduces $\log((1+\eta^2)/\eta^2)$. An additional summation or differentiation across background cells would require its own interface accounting, for which no cancellation identity has been proved. No allocation that pays the non-potential cut mass and removes the inverse-noise loss while preserving all labels, maximal-rank constraints and actual covariance weights has been established. The exact remaining task is to bound (GC-rem) by $A_0q(1+U)$ with a finite constant independent of every model parameter and $\eta$, or to give a legal divergent family for that specific integral.

This failure records an insufficient transport estimate, not a counterexample to (GC), and not a falsification of the universal one-sided Gaussian BH target. Step 7 is unexecuted; no canonical target proof, statement, status, source asset, definition, approval, state or setting was changed. No singular-limit transfer of a uniform bound is claimed. All completed derivations and the first analytic gap are retained above for a fresh continuation or independent audit.
