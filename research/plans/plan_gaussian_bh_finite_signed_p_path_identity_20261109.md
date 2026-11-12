---
title: Finite measurable event decomposition and signed p-path integration by parts
type: plan
status: succeeded
target_asset: gaussian_bh_finite_signed_p_path_identity
inspired_by:
  - idea_408804d0bbf6
  - idea_0ffd34ca0c10
  - idea_0b76f3484fd5
  - idea_4f1da6c4220a
proof_digest: 705d1412382427970a06ea15575c19d6a2ba52d86ef9f6e4ac59b74bcc6413ba
statement_digest: d7a8a4f0b24ea902729e5f1f7788367f78c722f470f62ba2b0bf55c676594eec
dependency_digests:
  gaussian_multiple_testing_model: 535694725c29c2ede682edeaeef6e40dce424d3a88330832f592e18853f99db7
  gaussian_test_pvalues: 77bd992c815e7093fd72c2543d655df56c15eef2bf6240d46d729bce9f86ca50
  benjamini_hochberg_step_up: 2654feec463fe339f6bebe029e9f1cbff9e970db6ad51faa3b66f632a90eb875
  false_discovery_rate: ce88ab68fe7c28f8baff59d3beb8b2c38cbb031634b8dc2f3cb3cad67a3309d1
verified_proof_digest: 705d1412382427970a06ea15575c19d6a2ba52d86ef9f6e4ac59b74bcc6413ba
---

## Goal

Target: [Exact finite signed conditional p-path identity for Gaussian BH](../assets/gaussian_bh_finite_signed_p_path_identity.md).

Prove the target's entire frozen Statement and Scope and proof obligations for every finite admissible $(N,\theta,\Sigma,q)$, including singular $\Sigma$, $N=1$, all original labels, and every $\theta_i\leq0$. In the target's notation, obtain exactly
$$
F_i=\frac qN\mathbb E_\xi\left[g_i(q)-\int_{(0,q)}A_i\,dg_i+\sum_{t\in J_i}g_i(t)\{A_i(t^-)-A_i(t^+)\}\right],
$$
its zero-mean specialization, and the stated full-original-FDR positive-part reduction. Prove all finite-event, endpoint, derivative, measurability, baseline and integrability assertions along the way. No estimate uniform in dimension for the positive jump budget, or later OU bridge, is a premise or conclusion of this plan.

## Plan

1. [x] **Make Gaussian conditioning and the actual BH count explicit.** For fixed original $i\in I_0$, prove $\xi_i=0$ and $\operatorname{Cov}(\xi_j,Z_i)=0$. Factor the joint Gaussian characteristic function to prove $\xi\perp Z_i$ even when the residual or full covariance is singular; no conditional density of $\xi$ is required. Construct the path as the displayed Borel function of $(\xi,t)$ and verify $T_i^{\,i}(t)=u(t)$. For every deterministic p-vector prove that the largest qualifying BH rank $K$ equals the cardinality of its non-strict rejection set: if $K>0$ and its threshold admitted $m>K$ coordinates, then $p_{(m)}\leq qK/N\leq qm/N$, contradicting maximality; handle $K=0$ separately. Express $K$ using the finite Borel counts $C_k=\sum_j\mathbf1\{T_j^{\,i}(t)\geq u(qk/N)\}$ and $K=\max(\{0\}\cup\{k:C_k\geq k\})$. This proves joint measurability of $R_i,r_i,A_i$ and freezes the exact ordinary-BH convention.

2. [x] **Enumerate a finite Borel event set, with constant ties retained.** For every $\rho_{ij}\ne0$ form the Borel candidate
   $$
   e_{jk}(\xi)=S\!\left(\theta_i+\frac{u(qk/N)-\theta_j-\xi_j}{\rho_{ij}}\right),\qquad 1\leq k\leq N,
   $$
   retaining it exactly when $0<e_{jk}<q$. These are all solutions for nonconstant score paths, since $u$ is strictly decreasing. Include every $qk/N$ with $1\leq k<N$. For $\rho_{ij}=0$, keep the comparison $\theta_j+\xi_j\geq u(qk/N)$ at every $t$, including equality, and add no event for that comparison. Use a fixed finite candidate list, replace invalid candidates by the sentinel $q$, sort by finite min/max operations, and remove repetitions using Borel equality tests. Exhibit a Borel increasing enumeration of the distinct valid points, of cardinality at most $M=N^2+N-1$. Add $0,q$ only as outer segment endpoints. Thus simultaneous crossings have one event and persistent ties have no fictitious infinite event set. Every threshold comparison, hence $R_i$, is constant on each open segment; clipping events make $A_i$ affine there. Compute its one-sided traces from the segment ranks, evaluated for example at Borel midpoint selectors, and select $J_i$ by unequal traces. This gives a measurable finite jump enumeration and excludes removable discrepancies at isolated point values.

3. [x] **Prove both endpoint limits and the derivative formula using the actual count.** For $0<t<q/N$, the coordinate with p-value $t$ forces a qualifying rank and $R_i\geq1$, so $0\leq A_i(t)\leq Nt/q$ and $A_i(0+)=0$. For $t>q(N-1)/N$, either $R_i<N$ and $A_i=1$, or $R_i=N$ and $A_i=t/q$; conclude $A_i(q-)=1$, including $N=1$. On an open segment of fixed $R_i=k>0$, the clipping definition has derivative $N/(qk)$ when $t<qk/N$ and zero when $t>qk/N$; the non-strict BH rejection criterion for the original coordinate is exactly $t\leq qk/N$. The equality lies in the event set. At $k=0$, $A_i=1$ and both sides of the claimed derivative formula are zero. Record $0\leq A_i\leq1$ and $0\leq A_i'\leq N/q$ off the events. A representative taking one chosen side limit at each event has variation at most $N+M$; restoring arbitrary actual isolated values in $[0,1]$ still leaves finite variation, bounded by $N+2M$.

4. [x] **Establish the null density change and the weight's behavior at zero.** Under the product law of $(\xi,Z_i)$ set $t=S(\theta_i+Z_i)$. Its density conditional on $\xi$ is
   $$
   \frac{\phi(u(t)-\theta_i)}{\phi(u(t))}=g_i(t),\qquad 0<t<1.
   $$
   Reconstruct every original coordinate via the same residual path, with unchanged true-null labels. An original coordinate with $t>q$ cannot be rejected by ordinary BH, whose largest threshold is $q$; equality has zero scalar probability. Apply nonnegative conditioning/change of variables to derive
   $$
   F_i=\frac qN\mathbb E_\xi\int_0^q g_i(t)A_i'(t)\,dt.
   $$
   Prove for $\theta_i\leq0$ that $g_i$ extends continuously and nondecreasingly to $[0,q]$, with $g_i(0)=0$ for $\theta_i<0$ and $g_i\equiv1$ for $\theta_i=0$. Since $u(q)>0$, establish $0\leq g_i\leq1$ and total variation $g_i(q)-g_i(0)\leq1$. This handles negative null means directly rather than reducing them to zero means.

5. [x] **Derive the exact signed segmentwise integration identity.** Integrate $g_i A_i'$ by parts on each open affine segment, first truncating the two outer segments inside $(0,q)$ if needed. Use the continuous bounded-variation extension of $g_i$ to pass to endpoints; $g_i(t)A_i(t)\to0$ at zero and $g_i(t)A_i(t)\to g_i(q)$ at $q$. Upon summing segments the interior boundary terms are exactly $g_i(e)\{A_i(e^-)-A_i(e^+)\}$, once per distinct event. Equal traces contribute zero, hence the sum is precisely over $J_i$. The actual value at an event affects neither the Lebesgue integral nor the Lebesgue-Stieltjes integral, since $dg_i$ has no atoms. Prove
   $$
   \int_0^q g_i A_i'\,dt=g_i(q)-\int_{(0,q)}A_i\,dg_i+\sum_{e\in J_i}g_i(e)\{A_i(e^-)-A_i(e^+)\}.
   $$
   Retain net signed jumps until this equality is complete, as suggested by the linked ideas; do not replace event contributions by coordinatewise absolute values or positive parts.

6. [x] **Justify measurable integrability and finish the exact baseline claims.** The finite Borel enumeration and trace formulas make signed sums and $B_i$ measurable; the jointly Borel bounded integrand makes the Stieltjes integral measurable (or compute it segmentwise from its affine pieces against the fixed measure $dg_i$). Give deterministic, residual-independent bounds
   $$
   \sum_{e\in J_i}\left|g_i(e)\{A_i(e^-)-A_i(e^+)\}\right|\leq M,\quad 0\leq B_i\leq M,\quad 0\leq\int_0^q g_i A_i'\,dt\leq N.
   $$
   Also $0\leq\int A_i\,dg_i\leq g_i(q)-g_i(0)$, so the baseline lies in $[g_i(0),g_i(q)]\subset[0,1]$. These bounds justify taking expectations of the signed identity; they are finite-$N$ integrability bounds only. When $\theta_i=0$, $dg_i=0$ and $g_i(q)=1$, yielding exactly the claimed specialization.

7. [x] **Obtain the full original FDR reduction and audit boundary cases.** Only after the exact identity, replace each signed weighted jump by its positive part, use the baseline bound $1$, and sum over the unchanged original set $I_0$. Verify $F=\sum_{i\in I_0}F_i$ directly from the FDP definition, including the empty-null case, to obtain the target inequality with its $q/N$ factor and $q\pi_0$ baseline. Check the proof explicitly for $N=1$, $R_i=0$ segments, strictly negative null means, singular covariance and correlations $0,\pm1$, constant threshold ties, duplicate or simultaneous events, removable point discrepancies, and changes occurring only at $t=q$. Confirm that none requires generic position, smoothing, deleting coordinates, relabeling, a quantitative positive-jump budget, or an OU bridge.

## Verification

Steps 1–3 establish every path, finite-event, count, endpoint and derivative assertion in the frozen target. Step 4 supplies the exact conditional density and normalization; step 5 proves the pathwise signed identity with the stated one-sided jump sign. Step 6 supplies all measurability, absolute integrability and baseline claims before expectation is taken. Step 7 yields precisely the final FDR inequality while preserving the separately available signed sum. During execution, check the change-of-variable factor $q/N$ and the sign $A_i(t^-)-A_i(t^+)$ against the displayed target, and verify that each event is counted once. The finite $M$ bounds establish integrability and do not assert the separate unresolved uniform budget.

## Assumed definitions

Only the target's four approved definitions are used: [Gaussian multiple-testing model](../definitions/gaussian_multiple_testing_model.md), [Gaussian test p-values and true nulls](../definitions/gaussian_test_pvalues.md), [ordinary BH](../definitions/benjamini_hochberg_step_up.md), and [FDR](../definitions/false_discovery_rate.md). There are no assumed draft definitions or unproved result dependencies. Gaussian residual independence and the particular integration-by-parts identity are proved in steps 1 and 5 rather than supplied by unlisted black boxes. The inspired ideas constrain the bookkeeping; their proposed bounds or other research claims are not assumed.

## Analogue search

Native library searches for finite Gaussian regression, bounded variation, step functions, and integration by parts returned no matching proof. The closest displayed Gaussian-BH analogue, `lib_chi2024_positive_gaussian_simes`, has no `Proof` section under native `show`; its positive-dependence Simes conclusion does not supply this arbitrary-covariance conditional identity. No library conclusion is cited as a black box and no complete library proof is adapted. The finite enumeration, Gaussian characteristic-function factorization and segmentwise calculation above are therefore to be established directly.

## Idea provenance

The teaching-chat agent proposal [Conditional p-path signed BH rank-jump identity and unregularized budget](../ideas/idea_408804d0bbf6.md), read through native `show`, supplies the scalar residual path, clipped $A_i$, weighted signed identity candidate, and finite-threshold enumeration route used here. Its identity, analytic checks, numerical diagnostics and proposed dimension-uniform positive-part budget remain unproved inputs to research, not black boxes in this plan: steps 1–7 prove all finite-identity claims independently, and the quantitative budget is outside this target.

The native disposition [Initial disposition of the three new teaching proposals](../ideas/idea_0ffd34ca0c10.md), also read through native `show`, supplies the separation of finite-identity verification from the positive-part and OU quantitative gates, and identifies simultaneous crossings, constant paths, measurability and conditional integration as explicit audit obligations. This plan adopts that scope and those checks without treating the disposition's analytic screening as verification. The earlier ideas `idea_0b76f3484fd5` and `idea_4f1da6c4220a` supply the related rule of assembling actual net signed rank contributions before taking positive parts. None of the four ideas is cited as a proved result.

## Outcome

The complete proof is in [Exact finite signed conditional p-path identity for Gaussian BH](../assets/gaussian_bh_finite_signed_p_path_identity.md), under `## Proof`, steps 1–7 corresponding to the checked items above. It establishes the frozen Statement and all listed scope obligations, including measurable distinct events and net traces, singular Gaussian independence, actual non-strict BH counts, both endpoints, negative-null density weights, signed segmentwise integration, absolute integrability, and the original-label FDR reduction. The target remains `status: draft`; execution is not an independent verification or researcher approval.

Only the four approved definitions listed above are assumed. No draft definition, unproved result, quantitative positive-jump bound or OU bridge is assumed. The deterministic bounds depending on finite N establish integrability only; the dimension-uniform jump budget remains unresolved and is outside this result. The original target-file prefix, including its Statement and Scope, was preserved byte for byte with SHA256 `1951b0dd980bea2b0740e0b54f789b09e6feb84fec0920f79724eeba772e0330`. The workspace root is not a Git repository, so no HEAD exists here; no commit or synchronization was performed.


## Verdict

confirmed

Independently checked the frozen statement against every step of the written proof. The characteristic-function factorization establishes residual independence even for singular covariance; the one-dimensional change of variables supplies the conditional density without assuming a residual density. The finite Borel candidate enumeration deduplicates all crossings, retains persistent non-strict ties in the BH comparisons, and gives measurable one-sided traces and actual net jumps. The largest qualifying BH rank equals the actual rejection count, so the derivative formula and both endpoint limits hold, including rank zero and N=1.

The continuous null weight has the stated extension at zero for both zero and strictly negative means. Segmentwise integration by parts has the correct signed jump orientation; atomlessness removes isolated point values. The deterministic bounds by M=N^2+N-1 and N justify measurability, absolute integrability and expectation of the exact identity. Its baseline lies in [0,1], and summing the positive-part upper bound over the original true-null labels gives precisely the stated full FDR inequality. No quantitative bound uniform in dimension or later positive-jump/OU budget is assumed or established. No material gap found.
