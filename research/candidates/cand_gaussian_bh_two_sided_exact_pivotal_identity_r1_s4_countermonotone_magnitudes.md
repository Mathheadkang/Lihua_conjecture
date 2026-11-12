---
type: candidate
title: Countermonotone Gaussian magnitudes with independent signs
status: failed
target_asset: gaussian_bh_two_sided_exact_pivotal_identity
checks:
  H1: pass
  H2: pass
  H3: fail
  H4: unknown
  NOT: unknown
mode: refute
round: 1
slot: 4
direction: known_counterexamples
statement_digest: 10fd42aac96d6f560ddc31272941b5f90f8a40eb9cbddd044801e18b7016e6b1
performed_by: unknown
created_at: '2026-11-06T20:02:43.032Z'
extension_version: 0.0.4
---

## Object

This is a pathological copula ansatz, not an admissible counterexample. Take $N=2$, $q=1/4$, $\theta=(0,0)$, $U\sim\operatorname{Unif}(0,1)$, and independent uniform signs $S_1,S_2$, independent of $U$. Define
$$
T_1=S_1\overline\Phi^{-1}(U/2),\qquad T_2=S_2\overline\Phi^{-1}((1-U)/2).
$$
Both marginals are $N(0,1)$; the signs give covariance zero, so their covariance matrix is $\Sigma=I_2$. Their absolute values have the deterministic countermonotone relation inherited from $U$ and $1-U$. The project library search for counterexamples returned no entries; this checks the classical pathological-copula mechanism rather than importing a cited theorem.

## Checks

### H1

$N=2$ is positive and finite, $q=1/4\in(0,1)$, also within the copied fixed-notation range.

### H2

The proposed mean vector is in $\mathbb R^2$. The actual covariance matrix is $I_2$, symmetric PSD with unit diagonal: each signed magnitude has a standard normal law, and independent centered signs make the cross moment zero.

### H3

Joint Gaussianity fails. If $(T_1,T_2)$ were jointly Gaussian with covariance $I_2$, its coordinates, and hence its absolute values, would be independent. Instead $2\overline\Phi(|T_1|)=U$ and $2\overline\Phi(|T_2|)=1-U$ sum identically to one. Two independent continuous uniform random variables do not have a deterministic sum. This violates the exact joint-Gaussian model hypothesis, even though both marginals and the covariance matrix look admissible.

### H4

Unknown: checking stopped at H3.

### NOT

Unknown: checking stopped at H3. No claim about failure of the target under its hypotheses is made.

## Failure

H3 fails: the countermonotone magnitude copula has Gaussian marginals but is not jointly Gaussian, so it cannot refute the exact Gaussian identity.
