---
type: idea
title: Finite global-BH envelope for mutually independent dependence blocks
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_two_sided_sharp_upper
tags:
  - independent-blocks
  - finite-level
  - small-cases
  - partial-obstruction
---

Draft observation for the current search; the literature status of this bound has not been checked, and no novelty claim is made. This is not a new asset or a proof of the unrestricted Gaussian conjecture.

Partition N p-values into mutually independent blocks D. Dependence within each block may be arbitrary. Assume every true-null p-value is uniform on [0,1], as it is for a zero-mean unit-variance Gaussian two-sided test. For ordinary global BH at q,
$$
\operatorname{FDR}\leq\frac qN\sum_{i\in I_0}|D_i|
=\frac qN\sum_D |D|\,|D\cap I_0|.
$$
The statement is also valid for super-uniform null p-values.

Proof: Fix a null i in a block D of size b, and condition on the vector v of every outside-block p-value. For k=1,...,b define R_k(v) as the global BH count after replacing D by k zeros and b-k ones. This count is deterministic given v, depends only on k rather than the positions of its zeros, and satisfies R_k>=k.

On the event that i is rejected, let k be the number of rejected coordinates in D, and let R be the actual global count. Replace exactly the rejected block values by zero and the unrejected ones by one. The original R remains qualifying. At every rank r>R, each originally rejected block value was already at most qR/N<qr/N, so making it zero cannot increase the number of p-values below qr/N. Making unrejected block values one can only decrease that number. No larger rank becomes qualifying, so the modified count remains R. Thus R=R_k(v).

It follows that
$$
E\left[\frac{\mathbf1\{i\ {\rm rejected}\}}{R\vee1}\,\middle|\,v\right]
\leq\sum_{k=1}^b\frac1{R_k(v)}
P\left(p_i\leq\frac{qR_k(v)}N\,\middle|\,v\right)
\leq \frac{bq}N.
$$
The last step uses independence of the block from v and marginal null calibration, not independence within D. Sum over null coordinates to prove the displayed bound. The argument retains one global BH rank and all ties, rather than adding blockwise FDRs.

Consequently if the largest independent-block size b_max(q) is o(sqrt(log(1/q))), the FDR normalized by q sqrt(log(1/q)) tends to zero, regardless of total dimension, within-block covariance singularity or condition number, deterministic mean sizes, or the number of blocks. This is a block-size obstruction and requires actual independence between blocks. It does not apply merely because a covariance graph is sparse or because marginal block covariances vanish for a non-Gaussian construction.

The new round-4 slot-2 candidate independent_signed_triples instantiates b=3, two true nulls per block, B=ceil(exp(log(1/q)^2)) mutually independent blocks, rho=-1/2+q^2 within each block, and nonidentical signed deterministic alternative means. Its covariance eigenvalues are 3/2-q^2, 3/2-q^2, and 2q^2 per block, so the full vector is exactly Gaussian, positive definite and increasingly ill-conditioned. The envelope gives FDR<=2q and zero target normalization. This excludes that prescribed family, not models whose factor sharing connects growing numbers of blocks.
