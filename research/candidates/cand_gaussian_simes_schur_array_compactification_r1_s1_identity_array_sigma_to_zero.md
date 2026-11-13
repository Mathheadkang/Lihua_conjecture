---
type: candidate
title: >-
  Independent-residual (identity) all-null array as the loading vanishes,
  against part 6
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

$q=0.05$, a sequence $\sigma_m\downarrow0$ in $(0,1)$, and the all-null array $P_I$ with $C_{ij}=0$ for $i\ne j$ (equivalently $P_{I_N}$ as $N\to\infty$, or the equicorrelated arrays $C_{ij}=\rho\downarrow0$ of idea_ed169268dd35). Under the loading, $\Phi_{n,\sigma}(P_I;q)=F_q(\text{equicorrelated }\sigma^2\text{ in dimension }n)$, whose $n\to\infty$ limit (Dey 2024, Theorem 4.3, cited in the idea and not imported here) is at most $\overline\Phi(\sqrt{2\log(1/q)+\log(1-\sigma^2)})$, which tends to a value strictly below $q$, while $\Phi_{n,0}(P_I;q)=F_q(I_n)=q$ for every $n$. So the infinite-array functional is discontinuous at $\sigma=0$ along this family. The question is whether this breaks part 6, $\lim_{\sigma\downarrow0}B^\sigma(q)=B(q)$, or part 5.

## Checks

### H1

$\sigma_m\in(0,1)$: pass.

### H2

$q=0.05\in(0,1/4]$: pass.

### NOT

Fails. Part 6 is a statement about the finite-model supremum $B^\sigma(q)$, not about $\Phi_\sigma(P)$ for a fixed infinite array, so the discontinuity at $\sigma=0$ never enters.

- Upper bound: $(1-\sigma^2)\Sigma+\sigma^2\mathbf1\mathbf1^{\mathsf T}$ is symmetric PSD with unit diagonal, so it lies in $\mathcal C_N$, and $B^\sigma(q)\le B(q)$ for every $\sigma$.
- Lower bound: fix $N$ and $\Sigma\in\mathcal C_N$. The event $\{\exists k:p_{(k)}\le qk/N\}$ is a finite union of intersections of the half-spaces $\{T_i\ge\overline\Phi^{-1}(qk/N)\}$. Its indicator is continuous off the hyperplanes $\{T_i=\overline\Phi^{-1}(qk/N)\}$, which are null under every $\mathcal N_N(0,R)$ with $R\in\mathcal C_N$ because each $T_i$ is standard normal. Since $\mathcal N_N(0,(1-\sigma^2)\Sigma+\sigma^2J)\Rightarrow\mathcal N_N(0,\Sigma)$ as $\sigma\downarrow0$, $F_q((1-\sigma^2)\Sigma+\sigma^2J)\to F_q(\Sigma)$. Hence $\liminf_{\sigma\downarrow0}B^\sigma(q)\ge F_q(\Sigma)$ for all $\Sigma$, so the liminf is at least $B(q)$.

For this family, $F_q((1-\sigma^2)I_N+\sigma^2J)\to F_q(I_N)=q$ for each fixed $N$, even though $\lim_N$ at fixed $\sigma>0$ stays strictly below $q$. The order of limits matters for $\Phi_\sigma(P_I)$, but $B^\sigma$ takes a supremum over $N$, so any fixed $N$ can be used. Part 5 at fixed $\sigma$ also holds: $\Phi_\sigma(P_I;q)\le B^\sigma(q)$ because each $\Phi_{n,\sigma}(P_I;q)$ is a single loaded finite model. No part asserts $\Phi_\sigma(P;q)\to\Phi_0(P;q)$, or that maximizers converge as $\sigma\downarrow0$.

## Failure

NOT fails: part 6 is a finite-model value statement. It follows from inclusion in $\mathcal C_N$ and fixed-$N$ continuity, so the discontinuity of the infinite-array functional at $\sigma=0$ does not reach it.
