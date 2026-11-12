---
type: idea
title: >-
  Finite equicorrelated null models obstruct an absolute square-root cluster
  contraction modulus
status: draft
idea_kind: test_case
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
tags:
  - universal-order
  - cluster-contraction
  - auxiliary-counterexample
  - finite-gaussian
  - independent-scoped-audit
tried_in:
  - target: gaussian_bh_one_sided_universal_order_upper
    round: 3
    slot: 1
    statement_digest: 00cfb3c66a8136044b1cb19c4e657b92bca75995aa6b9711598a30aa2009eff2
    outcome: no candidate written (show idea_0e63e86f1cc7 for what was found)
---

This is an independently scoped-checked finite auxiliary counterexample to an OVERLY STRONG ABSOLUTE near-copy cluster modulus. It does NOT refute the main universal-order target, the common-anchor negative-flux gate, or a favorable SIGNED contraction inequality. Keep this distinction in any subsequent plan.

Proposed auxiliary modulus being tested: |FDR_original-FDR_anchor|<=C q sqrt(delta)[1+U], U=S^{-1}(q), with a finite universal C, no restriction on cluster size, all means and original truth labels preserved, delta=max_i(1-corr(T_i,T_anchor)). Counterexample family: fixed0<q<=S(1), all means0, N jointly Gaussian coordinates

$$
T_i=\sqrt{1-\sigma^2}Z_0+\sigma\varepsilon_i,\qquad 0<\sigma<1,
$$

with independent standard normals. Original covariance is positive definite and off-diagonal1-sigma^2. Take C=[N] and contract all coordinates to the ACTUAL member T1, so delta=sigma^2 and the endpoint is N exact copies of a standard normal. Endpoint ordinary BH FDR is exactly q.

Here is a finite-N certificate; no population approximation is substituted for a finite model. Let H=phi(U)/q, L=log(1/sigma), d=sigma sqrt(L), h0=sigma H sqrt(L). Choose sigma sufficiently small that

$$
h_0\le\min\{1/2,S(\sqrt L)\},\qquad
\sigma\{u_{q/2}+\sqrt L\}\le u_{q/2}-U,\qquad
\phi(U+d/2)\ge\phi(U)/2,
$$

where u_s=S^{-1}(s). Such sigma exist for each fixed q. For every0<s<1,

$$
u_{qs}-\sigma u_s\ge U+d.
$$

Proof: if s<=1/2, use u_qs>=max(u_q/2,u_s), hence u_qs-sigma u_s>=(1-sigma)u_q/2>=U+d. If s>1/2 write h=1-s. Then u_q(1-h)-U>=h/H. If h>=h0 this supplies d; if h<h0<=S(sqrt L), then -sigma u_s=sigma u_h>=d. These are elementary marginal Gaussian quantile comparisons.

Put A=U+d/2, rho=1-sigma^2 and

$$
p(s)=S\left(\frac{u_{qs}-\sqrt\rho A}{\sigma}\right),\qquad
\eta=\max_{0\le s\le1}\frac{p(s)}s<1,
$$

extending the ratio by0 at s=0. The strict inequality follows from the uniform quantile gap, p(1)<1 and p(s)/s->0 as s->0, because the Gaussian tail exponent is1/sigma^2>1. Let I=-log(eta)-1+eta>0 and epsilon=[q-S(A)]/2>0. Choose integer K so e^{-IK}/[1-e^{-I}]<=epsilon/2. Then choose FINITE N>K so

$$
N H_{K-1}p(K/N)\le\epsilon/2,
$$

where H_m is the harmonic sum. Such N exists since N p(K/N)->0. These displayed inequalities define a finite, checkable certificate even if N is very large.

Condition POINTWISE on Z0=z<=A: coordinates are then independent and their exceedance probability at BH rank k is at most p(k/N). For1<=k<K, Markov and monotonicity of p give sum_k P(count>=k |Z0=z)<=N H_(K-1)p(K/N)<=epsilon/2. For k>=K, the mean count is at most eta*k; binomial Chernoff gives P(count>=k |Z0=z)<=exp(-I k), whose sum is<=epsilon/2. Integrate these pointwise bounds over z<=A (conditioning only on Z0<=A would not preserve independence). The all-null finite-model BH FDR, exactly its rejection probability, is therefore at most S(A)+epsilon. Hence

$$
q-\operatorname{FDR}_{N,\rho}\ge\frac{q-S(A)}2
\ge\frac{d\phi(U)}8
\ge\frac{q\sigma(1+U)\sqrt L}{16}.
$$

For the last bound use H>=U>=1. The ratio to q sqrt(delta)(1+U) diverges as sigma->0, so no finite C in the proposed absolute modulus exists. This is a finite Gaussian family: N is chosen anew after sigma, never asserted uniform under a hidden order of limits.

Independent scoped audit: a fresh reviewer independently checked the quantile split, small-s limit, finite K/N existence, pointwise-conditional Markov/Chernoff bounds and constant arithmetic. It confirmed the auxiliary counterexample and emphasized conditioning on Z0=z before integrating. This is not native approval of an asset or counterexample to the main target.

The SIGN matters: original FDR is SMALLER than anchor FDR in this family. Thus the candidate does not contradict FDR_original<=FDR_anchor or any one-sided upper comparison retaining signed deficits. A next contraction plan must avoid the disproved absolute square-root modulus; it may retain signed decrease or explicitly allow a sqrt(delta)*sqrt(log(1/delta)) spread cost.

Additional finite-dimensional calibration (candidate, not a dimension-uniform result): mean-preserving rotations of a same-original-null-category cluster obey the elementary Rice bound |DeltaFDR|<=sqrt(2/pi) sum_i alpha_i sum_(k=1)^N phi(u_(qk/N)-theta_i)<=sqrt(2/pi)N phi(U)sum_i alpha_i, alpha_i=acos corr(T_i,T_anchor), q<=S(1). This retains actual cascades but loses N, so it does not repair the main goal. The finite counterexample above shows why merely deleting this dimension cost in an absolute estimate cannot be justified.

## Tried

- Search round 3 for gaussian_bh_one_sided_universal_order_upper (slot 1): no candidate written (show idea_0e63e86f1cc7 for what was found)
