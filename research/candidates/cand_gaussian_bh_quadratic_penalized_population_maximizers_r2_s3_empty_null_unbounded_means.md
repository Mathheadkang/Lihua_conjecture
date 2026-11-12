---
type: candidate
title: >-
  Empty true-null population with unbounded positive means and exact moment
  recovery
status: failed
target_asset: gaussian_bh_quadratic_penalized_population_maximizers
checks:
  H1: pass
  H2: pass
  H3: pass
  NOT: fail
mode: refute
round: 2
slot: 3
direction: boundary_degenerate
statement_digest: f63154e3e80d27877f3af87a036cd4742c762111af24791b4523d3f69bfe3ea5
performed_by: unknown
created_at: '2026-11-09T03:49:16.614Z'
extension_version: 0.0.4
---

## Object

Fix $q=1/4$, $\sigma=1/2$, and $d=1$. Let
$$
\pi=\sum_{n=1}^{\infty}2^{-n}\delta_{(n,1,0)}.
$$
The law is deterministic, has no true-null mass, and has unbounded mean support. Test whether the empty-null boundary together with unbounded support obstructs the moment-convergent canonical approximation in conclusion 2. This differs from the board's finite mixed-tag zero-mean family: every mean here is strictly positive, and the issue being tested is second-moment tail recovery.

For each positive integer $m$, collapse the tail to mean one:
$$
\nu_m=(1/2+2^{-m})\delta_{(1,1,0)}+
\sum_{n=2}^{m}2^{-n}\delta_{(n,1,0)}.
$$
An empty sum is zero. The finite law has denominator $N_m=2^m$, multiplicity $k_{m1}=2^{m-1}+1$ at mean one, and $k_{mn}=2^{m-n}$ at mean $n$ for $2\le n\le m$.

## Checks

### H1

Pass. The displayed constants satisfy $0<q<1/2$, $0<\sigma<1$, and positive finite integer $d=1$.

### H2

Pass. Each atom has unit direction $1$ and alternative tag $0$ with strictly positive mean. The weights sum to one. The law is fixed independently of the Gaussian variables; its scores are $n+(\sqrt3/2)X(1)+(1/2)Z$. Thus it uses the exact prescribed common loading and tagged domain, with no analytic-completion zero points.

### H3

Pass. The relevant law is in $\mathcal P_2(\mathcal E)$, since
$$
\int\theta\,d\pi=\sum_{n=1}^{\infty}n2^{-n}=2,
\qquad
M_2(\pi)=\sum_{n=1}^{\infty}n^22^{-n}=6.
$$
Each displayed finite law also has finite second moment and canonical labels. Replication with the stated positive integer multiplicities gives the required finite Gaussian realization. No maximizing-law assumption or transport comparison is being invoked in this test of conclusion 2.

### NOT

Fail. The explicit finite canonical laws satisfy all three approximation conclusions. Couple each original atom at $n\le m$ to itself and each tail atom to $(1,1,0)$. Then
$$
W_1(\nu_m,\pi)\le\sum_{n=m+1}^{\infty}(n-1)2^{-n}
=(m+1)2^{-m}\longrightarrow0.
$$
The moment loss is exactly
$$
M_2(\pi)-M_2(\nu_m)
=\sum_{n=m+1}^{\infty}(n^2-1)2^{-n}
=(m^2+4m+5)2^{-m}\longrightarrow0.
$$
Every tag is zero, hence $V_\pi(r)=V_{\nu_m}(r)=0$ for every positive rank, and the defined FDP is also zero at rank zero. Thus $F(\pi)=F(\nu_m)=0$ exactly, regardless of the globally largest crossing. In particular $J_\eta(\nu_m)\to J_\eta(\pi)=-6\eta$ for each fixed $\eta>0$. This boundary object does not violate the target.

## Failure

NOT fails: empty true-null mass and unbounded positive means admit explicit rational canonical approximation with vanishing Wasserstein error and convergent second moments; all FDRs are exactly zero.
