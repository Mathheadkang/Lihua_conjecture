---
type: candidate
title: >-
  Negative equicorrelation at the PSD edge that exactly cancels the loading,
  against parts 2, 4 and 5
status: failed
target_asset: gaussian_simes_schur_array_compactification
checks:
  H1: pass
  H2: pass
  NOT: fail
mode: refute
round: 1
slot: 1
direction: boundary_degenerate
statement_digest: 3ff8e143d2d88073822e605c70956af7082d952917d813001866b18b04299581
performed_by: 52538116+Mathheadkang@users.noreply.github.com
created_at: '2026-11-13T05:51:19.466Z'
base_commit: 98aac83f1d5b2ff948788ff34d4eaccd70d3ddce
extension_version: 0.0.4
---

## Object

$\sigma=1/2$, $q=1/4$, $N=1+(1-\sigma^2)/\sigma^2=4$, and $\Sigma\in\mathcal C_4$ with off-diagonal entries $-1/(N-1)=-1/3$. This is the PSD boundary of equicorrelation (singular, with kernel $\mathbf 1$). The loaded matrix $(1-\sigma^2)\Sigma+\sigma^2J$ has off-diagonal entries $\tfrac34(-\tfrac13)+\tfrac14=0$, so it equals $I_4$. The test is whether a degenerate negative array whose loaded covariance is exactly independent (the $\sigma=0$ geometry) causes a discontinuity, or a gap between $\max\Phi_\sigma$ and $B^\sigma$.

## Checks

### H1

$\sigma=1/2\in(0,1)$: pass.

### H2

$q=1/4\in(0,1/4]$: pass.

### NOT

Fails.

- **Lawfulness of $P_\Sigma$.** It is a Gram array with repeated indices, so it is PSD, and it is exchangeable. Also $\mathbb E\,C_{12}=\tfrac14\cdot1+\tfrac34\cdot(-\tfrac13)=0\ge0$, as Gram arrays of iid vectors require. Such negative structure exists only through a fixed finite $N$; it cannot persist in the infinite exchangeable array at a fixed scale, because $\mathbb E C_{12}=\|\mathbb E v\|^2\ge0$.
- **Part 4.** The loaded clone model has 4 independent types with weights $m_j/n\to1/4$. The limit is $F_q(I_4)=q$ exactly (Monte Carlo $0.2495$).
- **Part 2.** Nearby lawful arrays $C_{ij}=-1/3+\epsilon$ give loaded independence plus $\tfrac34\epsilon$ equicorrelation in fixed dimension 4. $F_q$ is continuous there by the same null-hyperplane argument. The near-independence that causes the discontinuity in idea_ed169268dd35 needs both $N\to\infty$ and correlation $\to0$, and the loading $\sigma^2>0$ blocks that in any infinite exchangeable array.
- **Parts 5 and 6.** The value $q\le B^\sigma(q)$ is attained by $P_\Sigma$, and it is consistent with $\max_{\mathfrak P_0}\Phi_\sigma=B^\sigma$.

## Failure

NOT fails: loaded independence can be reached only at a fixed finite $N$. There the clone limit and finite-dimensional continuity hold, so no discontinuity or value gap appears at fixed $\sigma>0$.
