---
type: candidate
title: Singleton composite-null Mills field is constant under the FDP tilt
status: failed
target_asset: gaussian_bh_entropy_coherence_trace_budget
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
statement_digest: 282de99c92b14dd593f40c0583da4cc65ddd227e11dcc3d261ec31f0e3456ce2
performed_by: unknown
created_at: '2026-11-08T07:12:17.023Z'
extension_version: 0.0.4
---

## Object

For any fixed $\theta\le0$, take $N=d=1$, $v_1=1$, $T_1=\theta+G$ with $G\sim N(0,1)$. Let $q_n=\overline\Phi(3)2^{-n}$, $n\ge1$. The calculation below holds at every $q\in(0,1/2)$, hence at all sufficiently small members of this sequence for any proposed positive $q_0$.

## Checks

### H1

$N=d=1$ are finite positive integers.

### H2

The single vector has unit norm, the covariance is $[1]$, and the fixed original true-null set is $\{1\}$ for every $\theta\le0$.

### H3

The positive levels $q_n$ decrease to zero and satisfy $q_n\le\overline\Phi(3)$. Thus they eventually satisfy any asserted $q_0>0$.

### H4

With one p-value ordinary largest-rank BH rejects exactly when $G\ge U-\theta$, where $U=\overline\Phi^{-1}(q)$. On this event $R=V=1$ and otherwise both counts are zero. No alternate rank or threshold is introduced.

### H5

$f=\mathbf1_{\{G\ge U-\theta\}}$ and $F=\overline\Phi(U-\theta)>0$ for every finite $\theta$ and $q>0$.

### NOT

The Mills field satisfies $B=f/H$ identically, where $H=h(U)$. For every $t<1$ and every latent point, its heat posterior is therefore $a(t,z)=1/H$. Consequently $K_t=0$, $x=1$ and $M=0$. The terminal tilt is a Gaussian tail conditioned law, so $D=\log(1/F)<\infty$. Absolute trace integrability holds trivially. The proposed inequality is $0\le0$ for every positive constant $C$, even when the negative null mean varies with $q$.

## Failure

NOT fails: the exact heat field is constant, and the trace budget holds with equality for the entire one-test composite-null family.
