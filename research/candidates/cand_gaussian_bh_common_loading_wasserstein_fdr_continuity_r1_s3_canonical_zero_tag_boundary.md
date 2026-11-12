---
type: candidate
title: Canonical alternative means approaching the true-null boundary
status: failed
target_asset: gaussian_bh_common_loading_wasserstein_fdr_continuity
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: fail
  NOT: unknown
mode: refute
round: 1
slot: 3
direction: drop_hypothesis
statement_digest: c7c3378df201906f905a39cc98232cebf031e1b6084f86c0a75c836910b8f564
performed_by: unknown
created_at: '2026-11-09T00:42:21.565Z'
extension_version: 0.0.4
---

## Object

Take $q=1/4$, $\sigma=1/2$, $\mathcal H=\mathbb R$, and the unit direction $v=1$. Let $\xi,Z$ be independent standard normals and put $G=\sqrt{3}\xi/2+Z/2$. Consider the deterministic laws
$$
\pi_n=\delta_{(1/n,1,0)},\qquad \pi=\delta_{(0,1,1)}.
$$
This tests the canonical label change when strictly positive means approach zero. Both the approximants and the proposed limit use lawful canonical tags; the proposed transport changes the tag.

## Checks

### H1

Pass: the fixed testing level $q=1/4$ belongs to $(0,1/2)$.

### H2

Pass: the fixed common loading $\sigma=1/2$ belongs to $(0,1)$, and $\tau=\sqrt{3}/2$.

### H3

Pass: $\mathcal H=\mathbb R$ is a nonzero separable real Hilbert space, and the direction $1$ has norm one.

### H4

Pass: all the laws are deterministic Borel probability measures in the stipulated tagged space. The approximants have positive alternative means and the limit has a zero true-null mean. Their absolute first moments are respectively $1/n$ and $0$.

### H5

Pass: the one-dimensional series representative is $X(1)=\xi$; $Z$ is independent of it. The scores are $1/n+G$ and $G$. The proposed functional uses exactly the definition's non-strict largest crossing and common-cutoff true-tag numerator, with no change of rank convention.

### H6

Fail: the Wasserstein convergence premise of conclusion 3 does not hold. There is exactly one coupling of these two point masses, and its cost is
$$
W_1(\pi_n,\pi)=|1/n-0|+|1-1|+\mathbf1_{\{0\ne1\}}=1+1/n.
$$
Thus the distance tends to $1$, not zero. The discrete tag term separates the canonical mean-zero label boundary.

### NOT

Unknown: not evaluated after the failed Wasserstein premise.

## Failure

H6 fails because changing the canonical tag costs one unit in the stipulated metric.
