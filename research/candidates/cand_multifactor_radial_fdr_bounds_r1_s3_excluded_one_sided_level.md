---
type: candidate
title: Omitted one-sided level restriction
status: failed
target_asset: multifactor_radial_fdr_bounds
checks:
  H1: pass
  H2: pass
  H3: fail
  H4: unknown
  NOT: unknown
mode: refute
round: 1
slot: 3
direction: drop_hypothesis
statement_digest: c1bc65d229f2e3db424011091017ad2c03cd4b99cd43b5a9fc22c50df1a8d8a7
performed_by: unknown
created_at: '2026-11-04T06:39:44.119Z'
extension_version: 0.0.4
---

## Object

Take $m=d=1$, $\theta_1=0$, $a_1=0$, and independent standard normal variables $Z,\varepsilon_1$. Thus $T_1=\varepsilon_1$. Use track $s=1$, the ordinary Gaussian one-sided p-value, and ordinary BH at $q=1-\overline\Phi(6)$.

## Checks

### H1

Pass. This is a valid Gaussian multifactor representation with a zero loading and an independent standard normal residual.

### H2

Pass. The mean-zero coordinate is a true one-sided null, and the testing rule is ordinary BH with its prescribed Gaussian p-value.

### H3

Fail. Here $q=1-\overline\Phi(6)>1/2$, violating the explicit one-sided hypothesis $0<q<1/2$. This object omits that hypothesis and is not a counterexample to the original statement.

### H4

Unknown. Not checked after H3 failed.

### NOT

Unknown. Not checked after H3 failed; no violation of the original theorem is asserted.

## Failure

H3 fails: the testing level is outside the one-sided range, so the object is excluded before the conclusion is tested.
