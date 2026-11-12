---
type: candidate
title: Relabelling nulls along the auxiliary translation path
status: failed
target_asset: gaussian_bh_signed_label_halfline_stein_identity
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: fail
  NOT: unknown
mode: refute
round: 3
slot: 3
direction: drop_hypothesis
statement_digest: d3fb61916137dfc085bea1f638521abd2a8ea4841b661d5f9f84d49785283ab4
performed_by: unknown
created_at: '2026-11-07T05:31:35.916Z'
extension_version: 0.0.4
---

## Object

Take $N=2$, $\theta=(0,1)$, $\Sigma=I_2$, $Z\sim N_2(\theta,I_2)$, and $q=S(1)$. Apply ordinary one-sided BH. As a proposed auxiliary convention, count the set $I_0(t)=\{j:\theta_j-t\le0\}$ along $Z-t\mathbf1$, instead of the fixed original null set.

## Checks

### H1

Pass: $N=2$ is finite and positive, and both means are real.

### H2

Pass: the score vector is jointly Gaussian with the stated means.

### H3

Pass: $I_2$ is positive definite and has unit diagonal.

### H4

Pass: $q=S(1)>0$ is exactly the permitted upper endpoint, and ordinary BH is specified.

### H5

Fail: the original true-null set is $I_0=\{1\}$. At translation time $t=2$, the proposed convention instead counts $I_0(2)=\{1,2\}$, because the translated mean vector is $(-2,-1)$. This violates the explicit requirement to keep the original labels fixed throughout the auxiliary path.

### NOT

Unknown: checking stops at H5; no conclusion of the lemma has been tested for this inadmissible convention.

## Failure

H5 fails because relabelling by translated means changes the null set along the auxiliary path.
