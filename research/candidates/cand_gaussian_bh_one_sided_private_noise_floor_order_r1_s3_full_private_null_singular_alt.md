---
type: candidate
title: >-
  Full-private-noise null with a conditionally deterministic Gaussian
  alternative
status: failed
target_asset: gaussian_bh_one_sided_private_noise_floor_order
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  H6: pass
  NOT: fail
mode: refute
round: 1
slot: 3
direction: drop_hypothesis
statement_digest: 13ea882c68f2e481926074b4d0aebd215f088e2fc535bf626cb19200b933661d
performed_by: unknown
created_at: '2026-11-11T01:15:04.651Z'
extension_version: 0.0.4
---

## Object

For every q in (0,1), fix s_0=1, N=2, d=1 and put
$$
\theta=(0,\mu_q),\quad \mu_q=\sqrt{2\log(1/q)},\quad A=(0,1)^{\mathsf T},\quad D=\operatorname{diag}(1,0).
$$
Take independent standard Gaussian G, epsilon_1 and epsilon_2. Thus T_1=epsilon_1 and T_2=mu_q+G. The alternative has no private noise and its mean varies with q. Use exactly the full largest-rank non-strict BH rule from the statement.

## Checks

### H1

The floor s_0=1 is fixed independently of q and belongs to (0,1].

### H2

N=2 and d=1 are positive finite integers, theta is real, A has the required dimensions, and both entries of D are nonnegative.

### H3

Both marginal variance identities hold: 0^2+1^2=1 and 1^2+0^2=1. Consequently Sigma=I_2 is an admissible unit-variance Gaussian covariance.

### H4

Since mu_q>0, the true-null set is exactly {1}. Its private noise s_1=1 meets the fixed floor. The zero alternative private noise is permitted.

### H5

The factor and both private noises are mutually independent standard Gaussians, as required. In particular, the alternative remains a real unit-variance Gaussian observation even though its conditional private noise vanishes.

### H6

Set U=barPhi(T_1) and W=barPhi(T_2). U is uniform on (0,1), independent of W. Apply the stated non-strict largest-rank BH rule at q. Rank 2 qualifies exactly when U<=q and W<=q. If W>q, the only way to reject the null is U<=q/2, and the null is then the sole rejection. If W<=q, the null is rejected exactly when U<=q, and both observations are rejected. Ties occur with probability zero, but the non-strict inequalities have been retained.

### NOT

Independence gives the exact expression
$$
\operatorname{FDR}=\Pr(U\le q/2,W>q)+\frac12\Pr(U\le q,W\le q)=\frac q2.
$$
Therefore FDR/[q sqrt(log(1/q))]=1/[2 sqrt(log(1/q))] tends to zero as q decreases to zero. A uniform bound already holds with C(1)=1 and q_0(1)=exp(-1). The conclusion fails to be violated.

## Failure

NOT fails: even a zero-private-noise, q-dependent Gaussian alternative yields FDR exactly q/2 when the null is at the full-private-noise endpoint.
