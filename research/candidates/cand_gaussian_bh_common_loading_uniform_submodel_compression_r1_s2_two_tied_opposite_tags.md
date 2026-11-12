---
type: candidate
title: Two tied zero means with opposite analytic tags
status: failed
target_asset: gaussian_bh_common_loading_uniform_submodel_compression
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: fail
mode: refute
round: 1
slot: 2
direction: small_cases
statement_digest: 559f931c8cf870c13d2afe6f41bae6c492b9b6e20edb09e35b2275ac15e3ed5d
performed_by: unknown
created_at: '2026-11-09T05:14:18.431Z'
extension_version: 0.0.4
---

## Object

For every positive integer m take N=2,d=1, v_1=v_2=1, theta_1=theta_2=0, ell_1=1 and ell_2=0. Fix any q in (0,1/2) and sigma in (0,1). With independent standard normals G,Z, both scores equal T=sqrt(1-sigma^2)G+sigma Z. Sample I_1,...,I_m iid uniformly from {1,2}, independently of G,Z, and write K=sum_j 1{I_j=1}.

## Checks

### H1

Pass: q and sigma have the required fixed ranges.

### H2

Pass: N=2,d=1 and both deterministic residual directions have unit norm. Their equality, and the resulting singular Gram matrix, are expressly admitted.

### H3

Pass: the true-tagged mean is zero and hence nonpositive; the alternative-tagged mean is zero and hence nonnegative. The latter is an admitted point of the target's analytic completion.

### H4

Pass: the independent standard normals and the identical score representation are exactly the specified common-loading Gaussian model. Each score has marginal variance one.

### H5

Pass: the sampled indices have the prescribed independent uniform law; all copied scores and tags retain their original values, with no fresh Gaussian noise. Use ordinary largest non-strict BH.

### NOT

Fail: put B=1{S(T)<=q}. Equal scores force normalized rank rho_N=rho_m=B: if any positive rank qualifies then terminal rank qualifies, and otherwise both ranks vanish. The full FDPs are D_N=B/2 and D_m=B K/m. The common score is standard normal, so E B=q. Since K is Binomial(m,1/2) independently of B,

$$
\mathbb E[|D_m-D_N|+|\rho_m-\rho_N|]
=q\,\mathbb E|K/m-1/2|
\le q\sqrt{\operatorname{Var}(K/m)}
=\frac{q}{2\sqrt m}.
$$

This converges to zero, uniformly for q in every compact subset of (0,1/2), indeed uniformly throughout that interval. Thus perfect ties and opposite tags at the same zero mean do not create a counterexample in this smallest mixed-tag model.

## Failure

NOT fails: the rank is identical under resampling and the entire FDP discrepancy is a binomial tag-proportion error bounded by q/(2 sqrt(m)).
