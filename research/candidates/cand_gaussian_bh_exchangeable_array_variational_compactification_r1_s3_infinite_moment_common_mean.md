---
type: candidate
title: Infinite-moment common null mean at the boundary of array continuity
status: failed
target_asset: gaussian_bh_exchangeable_array_variational_compactification
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: fail
mode: refute
round: 1
slot: 3
direction: drop_hypothesis
statement_digest: ad34243f88082429829568f6c42e01df9341469c502adef723e491225d546918
performed_by: unknown
created_at: '2026-11-09T05:46:20.121Z'
extension_version: 0.0.4
---

## Object

Test clause 1's continuity assertion without imposing a moment bound. Let the nonnegative random variable H have survival probability P(H>t)=1/(1+t), t>=0. For each positive integer k define a parameter law P_k by theta_i=-min(H,k), ell_i=1, and C_ij=1 for every i,j. Let P have theta_i=-H with the same tags and residual array. Choose parameters before and independently of all Gaussian innovations. Fix any sigma in (0,1) and q in (0,1/2), and write U=S^{-1}(q).

## Checks

### H1

Pass. The common loading and testing level lie in the asserted open intervals.

### H2

Pass. Every mean is nonpositive and every tag is 1, so every mark lies in the lawful closed marked domain, including when H=0.

### H3

Pass. Every residual entry is 1. Every finite principal matrix is the all-ones matrix, hence symmetric, unit-diagonal, and positive semidefinite, since its quadratic form is the square of the coordinate sum.

### H4

Pass. All coordinates share the same mark, and the residual array is constant, so simultaneous finite permutations leave the parameter law unchanged. Gaussian innovations are independent of H by construction.

### H5

Pass. The laws P_k converge to P for finite-subarray weak convergence: under their displayed coupling every finite subarray converges almost surely. The limit has infinite second moment, since E[H^2]=integral_0^infinity 2t/(1+t) dt=infinity. No finite moment assumption is present in the continuity assertion being tested.

### NOT

Fail. Conditional on H, every observation has exactly the same score -min(H,k)+W, where W is standard normal; the combined common and residual Gaussian terms have variance (1-sigma^2)+sigma^2=1. For any finite number n of identical p-values, BH rejects all n exactly when their common p-value is at most q, and otherwise rejects none. Thus for every n,

$$
\mathcal F_n(P_k;q,\sigma)=\mathbb E S(U+\min(H,k)),\qquad
\mathcal F_n(P;q,\sigma)=\mathbb E S(U+H).
$$

These expressions are already independent of n, so each completion exists and equals its finite value. Bounded convergence gives F(P_k;q,sigma)->F(P;q,sigma). The proposed failure of continuity at an infinite-moment parameter law does not occur.

## Failure

NOT fails: a shared heavy-tailed null mean has an explicit bounded continuous FDR functional even when its limiting second moment is infinite.
