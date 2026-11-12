---
type: candidate
title: Increasing regular polygons of rank-two Gaussian directions
status: failed
target_asset: gaussian_simes_one_sided_uniform_linear_bound
checks:
  H1: pass
  H2: pass
  H3: pass
  H4: pass
  H5: pass
  NOT: fail
mode: refute
round: 1
slot: 3
direction: drop_hypothesis
statement_digest: 15d52b3eb80faa8138461b0390ec347f4eb6a5465aae5494d0e050fea1bae614
performed_by: unknown
created_at: '2026-11-09T04:15:08.641Z'
extension_version: 0.0.4
---

## Object

For integers j >= 3 choose any even N_j >= 4, allowing arbitrary growth with j, and set q_j = exp(-j). For i = 0,...,N_j-1 put v_i = (cos(2 pi i/N_j), sin(2 pi i/N_j)). Let G be a two-dimensional standard Gaussian and T_i = v_i dot G. Thus Sigma_{i,l} = cos(2 pi(i-l)/N_j). This tests arbitrarily dense directions, exact antipodal correlations, and singular rank two while retaining centered joint Gaussianity.

## Checks

### H1

Pass. Each N_j is a positive integer.

### H2

Pass. Sigma is the Gram matrix of the unit vectors v_i, hence symmetric positive semidefinite with unit diagonal. For N >= 4 it has rank two.

### H3

Pass. q_j > 0 tends to zero and eventually lies below every proposed fixed q_0 > 0. Throughout, q_j < barPhi(1).

### H4

Pass. T is exactly jointly centered Gaussian, as a linear image of G, with the displayed covariance.

### H5

Pass. Use p_i = barPhi(T_i) and the ordinary Simes event with non-strict comparisons and multiplicities. The following bound applies to that actual event.

### NOT

Fail. In fact rejection probability is less than 4q for every even N >= 4 and 0 < q <= exp(-3).

Write R = ||G||. A crossing at k <= 2 implies min_i p_i <= 2q/N, whose probability is at most 2q by the union bound and the uniform marginal p-values.

For a crossing at k >= 3 set f = k/N and t = barPhi^{-1}(qf). Here t >= 1. If R < t there can be no crossing. Otherwise the directions with projection at least t lie in a closed arc of length 2 arccos(t/R). A regular N-gon has at most N arccos(t/R)/pi + 1 vertices in that arc. Consequently a crossing implies

$$
\frac{\arccos(t/R)}{\pi}\ge f-\frac1N\ge\frac f2,
\qquad
R\ge\frac{t}{\cos(\pi f/2)}.
$$

Because t > 0 and directions are antipodal, k <= N/2, so all these expressions have positive denominators. The exact radial tail is P(R >= r) = exp(-r^2/2). All crossings with k >= 3 are therefore contained in the single radial event whose threshold is the smallest of the displayed thresholds over k. Its probability is at most the supremum of their radial tails; no union bound over k is taken.

For any such f and t, use tan(x) >= x and the elementary Mills lower bound barPhi(t) >= phi(t)t/(1+t^2). Since barPhi(t) = qf and t >= 1, this gives

$$
\begin{aligned}
\frac{\exp\{-t^2/[2\cos^2(\pi f/2)]\}}q
&\le \sqrt{2\pi}\, f(t+1/t)\exp\{-\pi^2t^2f^2/8\}\\
&\le 2\sqrt{2\pi}\,(ft)\exp\{-\pi^2(ft)^2/8\}\\
&\le \frac{4\sqrt{2\pi}}{\pi\sqrt e}<2.
\end{aligned}
$$

The last inequality maximizes y exp(-pi^2 y^2/8) over y >= 0. Adding the probability at ranks at most two proves P(Simes rejection) < 4q, uniformly in N and hence for every dimension growth schedule N_j. This candidate family has bounded probability-to-level ratio.

## Failure

NOT fails: regular polygon rank-two Gaussian families obey a dimension-uniform bound below 4q, including arbitrarily dense directions.
