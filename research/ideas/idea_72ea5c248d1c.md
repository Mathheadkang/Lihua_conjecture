---
type: idea
title: >-
  Correlated source-block packing preserves the two-sided half constant in its
  inner population limit
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_two_sided_sharp_upper
tags:
  - proved-restricted-obstruction
  - correlated-blocks
  - inner-population-limit
---

Restricted full-BH candidate upper argument, not a solution of the unrestricted target. Frozen source research-local/correlated_source_blocks_half_constant_candidate_20261104.md SHAad35a6735b905b3cf65747f50ec50fad71d43a6c216724d31e0fac2a6e0a8fab; application cold audit research-local/correlated_source_blocks_cold_audit_20261104.md SHA f7be1e0971375bed7decba6760acb6536cd180fc995fbdec37f85a7f43a69653 found no blocking gap conditionalon(A). Auxiliary(A) is separately bounded-audited and recorded as idea_eb00c6ece2cf. Composition remains same-model mathematical checking, not formal/human verification or native approval.

For each fixedq, finiteJ andpositiveweightsw, exact explicitly specified source-design blocks withmaxloading→0 have populationFDRlimsup <=q[Q^-1(q)/(2sqrt(2pi))+4], evenwitharbitraryloading-dependentGaussianfactorcorrelationsinclsingular. The actual largestBHcutoff isbounded by a strict contact from a deterministic largest-loadingblock; ALLfoldedaltcountsretained. Gaussian-pairstripbound thencontrols allothernullblocks withoutrequiringfactorindependence. Only AFTERthisinnerlimitmayJ,w,corrvarywithq. Arbitraryretunedalternativemeans, weights/JvaryingINSIDEinnerlimit, and uniformfinite-Gaussian-arraytransferremainUNPROVED. This excludesnatural source-block packing counterstrategies inthatpreciseorderedregime, notallmulti-factorGaussianfamilies. Full argument follows.

# Correlated exact source blocks: conditional half-constant obstruction

Date: 2026-11-04. Candidate derivation only. This note is conditional on auxiliary claim (A) below, whose independent audit is pending. It is not an approved research node, a proof of the unrestricted BH target, or a uniform finite-array result. The independent-block note is preserved unchanged.

## Conditional assertion and precise limits

Let Q be the standard normal survival function, phi its density, phi0 = 1/sqrt(2 pi), and p(c) = 2 Q(c). Fix 0 < q < Q(1), a finite number J of blocks, and positive weights w_j summing to one. Define s_j = q w_j. Each block uses the exact three-component source design specified below. For any sequence of positive loadings r_{j,n} with max_j r_{j,n} -> 0, the block factors Y_n are jointly centered Gaussian with arbitrary unit-diagonal positive-semidefinite correlation matrices R_n. Singular and loading-dependent R_n are allowed. Conditional null residuals are independent standard normals independent of Y_n. The source means, conditional population CDF, and population BH rule are retained exactly.

Conditional on (A), the claim is

limsup_n FDR_population(q,w,r_n,R_n)
 <= q [u_q/(2 sqrt(2 pi)) + 3 + Phi(1)]
 <= q [u_q/(2 sqrt(2 pi)) + 4],
where u_q = Q^{-1}(q) > 1.

Consequently the leading normalized limsup is at most 1/(2 sqrt(pi)). Here the small-loading population limit is taken first at each fixed q, J, and w. The finite choices J and w, and all factor correlations, may then depend on q as q -> 0. The displayed constant does not depend on them. This order does not put a supremum over changing weights or an unbounded number of blocks inside the small-loading limit.

The sole additional auxiliary claim is

(A) For every centered jointly Gaussian unit-variance pair (X,V), every correlation in [-1,1], and every u >= 1,

E[1{1<X<=u} M_X(V)] <= u/(2 sqrt(2 pi)) + 2,
M_x(v) = sup_{0<=a<=x} exp(-a^2/2) cosh(av).

The candidate proof of (A) is in research-local/bivariate_gaussian_capped_likelihood_strip_candidate_20261104.md, SHA-256 1bb50ab90a103daa608c7d8cab875b1b667a51de5c3b89418c288be64bbefb3f. Its status is not upgraded here. No claim about arbitrary BH cutoffs follows from (A) alone.

## Exact source design

Put L_a(y) = exp(-a^2/2) cosh(ay) and M(y) = sup_{a>=0} L_a(y). For y > 1 write a(y) for the positive maximizer, y(a) for its inverse, y_s for the unique solution s M(y_s)=1, and a_s = a(y_s). The elementary properties used below are a(y) = y tanh(a(y)y), 0 < a(y) < y, a and its inverse increasing and smooth, and M increasing on (1,infinity).

For a block of level s=s_j and loading r=r_{j,n}, define

b = r p^{-1}(r^2),
W(a) = [1-s M(y(a))] p(a/r)/s, for b <= a <= a_s,
tau = W(b), pi = 1-r-tau,
p(c0) = s(r+tau)/(1-s pi), m = c0+y(b),
mu(a) = a/r+y(a).

Its population mass is pi of nulls with statistic rY+sqrt(1-r^2)epsilon, mass r of primary alternatives with statistic m-Y, and a continuum of secondary alternatives with statistic mu(a)-Y and tail mass W(a). The secondary total mass is tau; there is no extra random-design integration in the definition of this conditional population. These formulas are the inspected source-design formulas, with a harmless sign flip of every null statistic after reversing the common factor; folded null p-values are unchanged.

For fixed s in (0,1) as r -> 0,

tau = O_s(r^2), pi -> 1, y(b) -> 1,
c0 -> infinity, r c0 -> 0, b/r-c0 -> infinity.

Indeed p(b/r)=r^2, p(c0) is asymptotic to sr/(1-s), and the Gaussian quantiles are asymptotic to sqrt(4 log(1/r)) and sqrt(2 log(1/r)), respectively. This also shows the source masses are nonnegative for all sufficiently small r.

## Exact folded counts and actual maximum BH rank

For block j, let S_j(x) be its secondary upper-tail mass: it is tau_j below mu_j(b_j), W_j(mu_j^{-1}(x)) on the secondary mean interval, and zero above mu_j(a_{s_j}). The secondary measure is continuous. At cutoff c > 0 the exact conditional alternative mass is

B_j(c,Y_j) = r_j [1{Y_j<=m_j-c}+1{Y_j>=m_j+c}]
             + S_j(Y_j+c) + tau_j-S_j(Y_j-c).

Both folded tails are present. This retains every primary mass w_j r_j and every secondary mass w_j tau_j at all candidate cutoffs. The exact conditional null tail is

A_j(c,Y_j) = Q((c-r_jY_j)/sqrt(1-r_j^2))
             + Q((c+r_jY_j)/sqrt(1-r_j^2)).

Define the full population qualification function and cutoff by

H(c,Y) = q/p(c) sum_j w_j [pi_j A_j(c,Y_j)+B_j(c,Y_j)],
C(Y) = inf{c>=p^{-1}(q): H(c,Y)>=1}.

This is the actual smallest qualifying statistic cutoff, hence the largest population BH p threshold. Primary-mean atoms and all alternative backgrounds remain in H. When a qualifying cutoff exists, the infimum is attained: the conditional CDF is right-continuous in p, or equivalently H has only downward jumps as c increases and is upper semicontinuous. At the selected cutoff, even if H(C,Y)>1,

D(Y) <= min{1, q sum_j w_j pi_j A_j(C,Y_j)/p(C)}.

Thus the proof needs a preceding strict qualification witness, not an equality at a selected candidate root.

## A contact from the largest-loading block

First consider a fixed factor vector away from the boundaries below. Relabel block 1 so that r_1=max_j r_j, and put s=s_1. Since all counts are nonnegative, H(c,Y) is at least

H_1(c,Y_1) = s [pi_1 A_1(c,Y_1)+B_1(c,Y_1)]/p(c).

The following three witnesses use only block 1; other blocks' alternatives cannot invalidate them.

1. If Y_1<1, take c=c0+h/c0 with any fixed h>0. For all sufficiently small r_1, the primary and every secondary alternative of block 1 are rejected, so B_1=r_1+tau_1. The null ratio tends to one and p(c)/p(c0)->exp(-h). Hence

   H_1(c,Y_1) -> s+(1-s)exp(h)>1,
   C <= c0+h/c0 = o(1/r_1).

2. If 1<Y_1<y_s, put a=a(Y_1) and c=a/r_1+h with fixed h>0. The primary is absent, and all secondary statistics are positive for small r_1. The exact secondary count is W(beta), where beta/r_1+y(beta)=c+Y_1. The implicit relation gives

   beta/r_1-c = -r_1 y'(a)h+O(r_1^2),
   p(beta/r_1)/p(c) -> exp(a y'(a)h).

   The null ratio tends to M(Y_1), so

   H_1(c,Y_1) -> sM(Y_1)+[1-sM(Y_1)]exp(a y'(a)h)>1.

   Here y'(a)>0. From a=y tanh(ay), the relevant implicit denominator is 1-y^2 sech^2(ay)=1-2ay/sinh(2ay)>0. It follows that limsup r_1 C <= a(Y_1).

3. If Y_1>y_s, take c=a_s/r_1. The null term alone tends to sL_{a_s}(Y_1)>1. Therefore r_1 C<=a_s<a(Y_1) eventually.

All three strict inequalities persist when the factor value moves to a fixed limiting value away from 1 and y_s. Combining them gives

r_1 C -> 0 on Y_1<1,
limsup r_1 C <= a(Y_1) <= Y_1 on Y_1>1.

This is a statement about the full BH maximum. It holds for any correlations among factors; no independent-block FDRs have been added.

## Uniform null-tail passage at the actual cutoff

For every fixed lower cutoff c_min>0, fixed K<infinity, and compact set of factor values, the elementary tail asymptotic is

sup_{c>=c_min, rc<=K} |A_r(c,y)/p(c)-L_{rc}(y)| -> 0 as r->0.

On bounded c intervals this follows by continuity, with L_{rc}(y)->1. For c tending to infinity, apply Mills' ratio to (c +/- ry)/sqrt(1-r^2). Uniformly for rc<=K and bounded y, the exponential parts become

exp[-(rc)^2/2 +/- (rc)y] (1+o(1)),

and their half-sum is L_{rc}(y). To make the uniform argument explicit, split at an arbitrary large fixed c=A: Mills' errors above A are O(A^{-2}) uniformly, while the below-A errors vanish as r->0; then let A increase. The same assertion holds when y moves within its compact set.

Because every r_j<=r_1, the actual-cutoff contact bounds therefore imply, outside null-probability boundaries,

limsup_n A_{j,n}(C_n,Y_j)/p(C_n) <= 1 on Y_1<1,
limsup_n A_{j,n}(C_n,Y_j)/p(C_n) <= M_{Y_1}(Y_j) on Y_1>1.

These are limsups for each fixed block j. The same bounds hold with moving factor vectors converging to Y, as used next. No bound on an unselected candidate cutoff is substituted for C.

## Varying correlations and bounded convergence argument

The preceding limits also suffice if R_n varies with loadings. To bound any subsequential limsup of FDRs, select a subsequence on which the index of a largest-loading block is fixed and R_n converges to a correlation matrix R. The finite-dimensional correlation matrices form a compact set. With a fixed standard Gaussian vector Z, couple Y_n=R_n^{1/2}Z and Y=R^{1/2}Z using the principal matrix square roots; their continuity, including at singular matrices, gives Y_n->Y almost surely. Each Y_j is still standard normal.

All contact and tail arguments above hold for these moving factor vectors. The boundary events Y_1 in {1,y_s,u_q} have probability zero even if R is singular. As D_n is bounded by one, reverse Fatou applies directly to the FDP; no exchange of expectations of unbounded likelihood ratios is needed.

Let X=Y_1 and u=u_q. On X<=1, the limiting FDP is at most q. On 1<X<=u it is at most q sum_j w_j M_X(Y_j), with the outer cap at one available but unnecessary. On X>u use only FDP<=1. Thus

limsup_n E D_n
 <= q Phi(1)
    + q sum_j w_j E[1{1<X<=u}M_X(Y_j)]
    + Q(u).

Every pair (X,Y_j) is a centered Gaussian unit-variance pair. Auxiliary claim (A) includes the perfectly correlated pair j=1 and all singular pair correlations. Since sum_j w_j=1 and Q(u_q)=q, the claimed bound follows:

limsup_n FDR_population
 <= q [Phi(1)+u_q/(2 sqrt(2 pi))+2]+q.

Finally u_q/sqrt(log(1/q))->sqrt(2), giving the coefficient 1/(2 sqrt(pi)). The constants remain independent of J, weights, and correlations under the exact order of limits stated at the start.

## Open boundaries

The proof remains conditional on the stated auxiliary strip lemma until its independent audit is returned. It rules out packing gains only for the exact primary/secondary source designs in this population inner small-loading limit. Arbitrary retuned alternative means, a simultaneous limit with changing weights or infinitely many blocks inside the loading limit, and a finite-array upper bound uniform over N are outside scope. A q-dependent finite Gaussian construction needs a quantitative empirical/discretization/threshold transfer at o(q sqrt(log(1/q))) scale; no such transfer is claimed here.

The preserved predecessor is research-local/two_factor_full_bh_separated_scale_obstruction_20261104.md, SHA-256 085be193821fa97b85ec2fe2fb8a78da891086e70acd32ebaf1d092d20f0c586.
