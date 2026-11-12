---
type: candidate
title: Rank-one signed Gaussian degeneracy has exact Simes probability q
status: failed
target_asset: gaussian_simes_one_sided_uniform_linear_bound
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: fail
mode: refute
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: 15d52b3eb80faa8138461b0390ec347f4eb6a5465aae5494d0e050fea1bae614
performed_by: unknown
created_at: '2026-11-09T04:15:08.641Z'
extension_version: 0.0.4
---

## Object

For any positive integer N and any deterministic sign vector s in {-1,1}^N, let Z be standard normal, set T_i=s_i Z, and take Sigma=ss^T. Let m be the number of positive signs and n=N-m. Choose any level 0<q<1/2, permitting N and s to depend on q. Form the prescribed one-sided p-values. This tests whether perfect positive and negative correlations, singularity, and arbitrary tie multiplicities can create an unbounded rejection-probability-to-level ratio.

## Checks

### H1

pass. N is a positive integer. Both m=0 and n=0 are allowed, as is N=1.

### H2

pass. Sigma is symmetric, has diagonal entries s_i^2=1, and is positive semidefinite because x^T Sigma x=(s^T x)^2>=0. It has rank one, including the maximally singular boundary when N>1.

### H3

pass. T=sZ is centered jointly Gaussian: for every a, a^T T=(a^T s)Z is centered normal with variance a^T Sigma a, with the prescribed zero-variance convention.

### H4

pass. The family is defined for every 0<q<1/2, so in particular for every 0<q<=q_0 for any proposed q_0 in (0,1/2).

### H5

pass. Write U=barPhi(Z), which is uniform on (0,1). There are m copies of U and n copies of 1-U. These are exactly the required p-values; their ordering retains every multiplicity and uses non-strict comparisons.

### NOT

fail. The rejection probability is exactly q, uniformly over N and s, so this family admits the bound with C=1.

For U<1/2, the positive-sign group, if nonempty, consists of the m smallest p-values. The other group's p-values exceed 1/2>q, so none of its ranks can qualify. Within the first group a crossing occurs exactly when U<=qm/N, since the largest threshold in that group is attained at k=m. If m=0, this event is empty almost surely. For U>1/2 the same argument gives the event 1-U<=qn/N. At U=1/2 no rank qualifies since q<1/2. Thus, up to null endpoints, the rejection event is the disjoint union

$$
\{U\le qm/N\}\;\cup\;\{U\ge1-qn/N\}.
$$

Both intervals lie on their respective sides of 1/2, and their probabilities sum to q(m+n)/N=q. Equality threshold events have zero probability even with the ties, since U has a continuous law. Consequently the ratio to q is identically one along every dimension-dependent or sign-dependent choice, including q tending to zero. The conclusion does not fail.

## Failure

NOT fails: arbitrary signed rank-one Gaussian families have exact Simes rejection probability q and therefore cannot violate the proposed uniform linear bound.
