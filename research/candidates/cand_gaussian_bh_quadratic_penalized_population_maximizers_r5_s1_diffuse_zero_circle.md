---
type: candidate
title: Diffuse angular support at the zero-moment boundary
status: failed
target_asset: gaussian_bh_quadratic_penalized_population_maximizers
checks:
  H1: pass
  H2: pass
  H3: pass
  NOT: fail
mode: refute
round: 5
slot: 1
direction: boundary_degenerate
statement_digest: f63154e3e80d27877f3af87a036cd4742c762111af24791b4523d3f69bfe3ea5
performed_by: unknown
created_at: '2026-11-09T03:57:46.921Z'
extension_version: 0.0.4
---

## Object

Fix $q=1/4$, $\sigma=1/2$, and $d=2$. Let $U$ be uniform Lebesgue probability on $[0,2\pi)$ as a parameter measure, independently of all Gaussian randomness. Set
$$
\pi=\mathcal L(0,(\cos U,\sin U),1).
$$
The attempted obstruction is diffuse direction support at the exact boundary $M_2=0$: unlike the earlier dimension-one four-atom simplex, this law has no atoms. Test the canonical-approximation conclusion using the regular polygons
$$
\nu_n=\frac1n\sum_{j=0}^{n-1}\delta_{(0,(\cos(2\pi j/n),\sin(2\pi j/n)),1)},\qquad n\ge3.
$$
This tests a non-atomic zero-moment family; it does not change the scale of the earlier four-atom example.

## Checks

### H1

Pass. The fixed parameters satisfy $q\in(0,1/2)$, $\sigma\in(0,1)$ and $d\in\{1,2,\ldots\}$.

### H2

Pass. The law is deterministic and supported in the prescribed closed tagged domain: every direction has norm one, and every true-tagged mean equals zero. It is a probability law in $\mathcal P_2(\mathcal E)$, with
$$
\int|\theta|\,d\pi=M_2(\pi)=0.
$$
The parameter distribution is independent of the Gaussian randomness.

### H3

Pass. With independent standard Gaussians $\xi_1,\xi_2,Z$, the scores are exactly
$$
T(\phi)=\frac{\sqrt3}{2}(\xi_1\cos\phi+\xi_2\sin\phi)+\frac12Z.
$$
They have the required unit marginal variance and fixed common loading. Use the actual largest non-strict crossing and the original full FDP throughout. Since all tags are true, the full FDP is exactly $\mathbf1_{\{\rho>0\}}$, including the stipulated value zero at rank zero; this is not a replacement rank functional. For example, writing $R=(\xi_1^2+\xi_2^2)^{1/2}>0$ almost surely, the population count at $r>0$ is explicitly
$$
H_\pi(r)=\frac1\pi\arccos\!\left(\max\{-1,\min\{1,(S^{-1}(r/4)-Z/2)/(\sqrt3R/2)\}\}\right).
$$
The largest qualifying crossing of this count defines the stated $\rho_\pi$.

### NOT

Fail. Couple each angle to its nearest polygon vertex, using angular cells of width $2\pi/n$. The circular angular distance is at most $\pi/n$, and the Euclidean chord distance is at most that angular distance. The means and tags agree exactly, so the metric from the definition gives
$$
W_1(\nu_n,\pi)\le\pi/n\longrightarrow0,
\qquad M_2(\nu_n)=M_2(\pi)=0.
$$
Every polygon weight is rational, every direction is unit, and every zero mean has the required canonical true-null label. Each polygon law is realized by its $n$ unit-variance Gaussian scores, one copy per vertex, with exactly the prescribed covariance construction. The approved fixed-loading continuity theorem therefore applies to these exact full largest-crossing FDRs and gives
$$
F(\nu_n)\longrightarrow F(\pi).
$$
Thus this diffuse boundary law admits all three limits claimed in part 2; its zero moment also makes $J_\eta(\nu_n)=F(\nu_n)\to F(\pi)=J_\eta(\pi)$ for every fixed $\eta>0$. No failed conclusion is obtained. This explicit approximation does not establish attainment or any transport assertion for general maximizing laws.

## Failure

NOT fails: nearest-angle polygon quantization approximates diffuse zero-mean directional mass with vanishing Wasserstein error, exactly preserved second moment, and full FDR convergence.
