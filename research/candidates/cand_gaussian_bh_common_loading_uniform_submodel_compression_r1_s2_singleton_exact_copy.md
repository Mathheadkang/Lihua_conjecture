---
type: candidate
title: Singleton with exact resampled copies
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

For every positive integer m take N=d=1, v_1=1, theta_1=0 and ell_1=1. Fix any q in (0,1/2) and sigma in (0,1). Let G and Z be independent standard normals, set T=sqrt(1-sigma^2)G+sigma Z, and sample all m indices uniformly from the singleton.

## Checks

### H1

Pass: q and sigma have the stipulated ranges and are fixed independently of m.

### H2

Pass: N=d=1 and the deterministic vector v_1 has norm one.

### H3

Pass: ell_1=1 and theta_1=0 satisfies the true-tag restriction.

### H4

Pass: G and Z have precisely the required independent Gaussian laws, and T has the required score representation.

### H5

Pass: I_j=1 almost surely for every j; these degenerate iid indices are independent of G,Z. The m scores are exact copies and ordinary non-strict BH is used with their original tag.

### NOT

Fail: write B=1{S(T)<=q}. For both arrays all scores are identical. The actual largest BH rank is terminal rank one in normalized units when B=1, and zero otherwise. Thus rho_m=rho_N=B and D_m=D_N=B for every m and every Gaussian realization. The expected sum of absolute errors is identically zero. This family cannot violate compression, including its compact-in-q version.

## Failure

NOT fails: exact singleton replication preserves both the full tagged FDP and normalized actual BH rank identically.
