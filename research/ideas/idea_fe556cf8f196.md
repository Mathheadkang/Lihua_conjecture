---
type: idea
title: >-
  Bounded correlated alternative counts preserve O(q) FDR under nonpositive null
  covariance
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_bh_one_sided_universal_order_upper
  - gaussian_bh_conditional_subpoisson_calibration
tags:
  - nonpositive-null-covariance
  - correlated-alternatives
  - actual-bh-rank
  - count-chernoff
  - boundary-obstruction
---

Consider an admissible finite one-sided Gaussian model with original null set I0={i:theta_i<=0}, unit marginal variances, and Sigma_ij<=0 for distinct original null labels i,j. Let a=N-|I0| be the number of alternatives. Their means and covariances with the null vector are otherwise arbitrary: neither independence nor saturation is assumed. Run the original ordinary BH procedure, retaining its actual counts V and R, and write A=R-V.

The unconditional Gaussian null-count calculation gives, for s in (0,q] and lambda>=0,
$$
E exp{lambda C(s)} <= exp{Ns(e^lambda-1)}.
$$
Indeed, the Gaussian covariance interpolation from diagonal covariance to the original null covariance bounds the exponential product by the product of its marginals. Every original null marginal is superuniform, so the sum of marginal threshold probabilities is at most |I0|s<=Ns. This uses the null marginal law only; it does not condition on the alternative vector or assume that conditioning preserves covariance signs.

For each v>=1 and k in {0,...,a}, on {V=v,A=k} the actual total rank is the deterministic r=v+k and FDP=d_vk=v/(v+k). At the original threshold s=q(v+k)/N, this event implies C(s)>=v. Split all such index pairs according to d_vk<=2eq or d_vk>2eq. The entire low-ratio part contributes at most 2eq, because its event probabilities sum to at most one. For a high-ratio pair, the count-mgf Chernoff bound with mu=q(v+k) and lambda=log(v/mu)>0 gives
$$
P(V=v,A=k) <= exp{-v log(v/mu)+v-mu} <= (eq/d_vk)^v.
$$
Therefore its weighted contribution is at most eq (eq/d_vk)^(v-1) <= eq 2^(1-v). For each fixed k, summing over v>=1 costs at most 2eq. There are a+1 possible k values. Hence
$$
FDR <= min{1,2e(a+2)q}.
$$
No deletion, relabeling, threshold substitution in the actual procedure, or global FDR monotonicity is used. The auxiliary calculation only groups the original realized counts. For a=0 this reproduces the 4eq all-null bound; for a=1 it gives 6eq with arbitrary correlation of the one unsaturated alternative to arbitrarily many nulls.

Consequences for the main refutation search: uniformly bounded a cannot produce an unbounded FDR/[q sqrt(log(1/q))] ratio. More generally, within the nonpositive-null-covariance subclass, such a diverging sequence must have (a+2)/sqrt(log(1/q)) tending to infinity along its diverging subsequence. This is a boundary/subclass obstruction and not a universal main bound when a grows arbitrarily or when positive null covariances are allowed. The argument is a draft observation requiring native independent verification before use as a proved asset.
