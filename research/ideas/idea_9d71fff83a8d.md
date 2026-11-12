---
type: idea
title: >-
  Frozen-ray conjecture: the planted overlap dominates the excess
  log-likelihood, which closes the early window w ≤ K sqrt(log α) and leaves
  only late detection
status: draft
idea_kind: observation
origin: agent
related_assets:
  - gaussian_frozen_ray_maximal_likelihood_ratio_conjecture
tags:
  - side-chat-20261111
  - frozen-ray
  - planted-path
  - zone-occupation
  - late-detection
  - numerically-checked
  - not-natively-verified
---

Side-chat refinement of the proof program idea_dc6cf14ab94d for the [frozen-ray maximal Gaussian likelihood-ratio bounds](../assets/gaussian_frozen_ray_maximal_likelihood_ratio_conjecture.md). The pointwise inequality (F2) is elementary and was checked numerically. The occupation bound is a proposed lemma whose proof sketch is incomplete at one named step. Scripts: research-local/carrier_cap_prds_20261111/early_window.py.

## Setting

Unit directions $u_j$, weights $\omega_j$, $L_w(y)=\sum_j\omega_j\exp(w\langle u_j,y\rangle-w^2/2)$. Planted path: $J\sim\omega$, $X=u_J$, $G$ standard Gaussian and independent, $Y(w)=\log L_w(wX+G)$. Posterior weights $\pi_w(j)\propto\omega_j\exp(w\langle u_j,wX+G\rangle-w^2/2)$, overlap $\Gamma_w=\sum_j\pi_w(j)\langle u_j,X\rangle$, score $s_w=\sum_j\pi_w(j)\langle u_j,wX+G\rangle-w$.

## Two facts

(F1) Along the planted path,
$$
\frac{dY}{dw}=s_w+w\,\Gamma_w .
$$

(F2) For every realization and every $w>0$,
$$
w^2\,\Gamma_w\ \ge\ Y(w)-\log L_w(G).
$$

Proof of (F2). Let $\pi^0_w$ be the posterior weights at the null point $G$ and $M(\lambda)=\log\sum_j\pi^0_w(j)\exp(\lambda w^2\langle u_j,X\rangle)$. Then $M(0)=0$, $M(1)=Y(w)-\log L_w(G)$ and $M'(1)=w^2\Gamma_w$. Convexity of $M$ gives $M'(1)\ge M(1)-M(0)$.

In words: the overlap of the posterior with the planted direction is at least the excess of the planted log-likelihood over the null log-likelihood, divided by $w^2$. Numerically the slack $w^2\Gamma_w-(Y(w)-\log L_w(G))$ was nonnegative to rounding error in every sample of three geometries.

## Consequence: the early window

At a point of the path with $Y(w)\ge a-2$ and $\log L_w(G)\le a/2$,
$$
\frac{dY}{dw}\ \ge\ s_w+\frac{a/2-2}{w}.
$$
At each fixed $w$ the score is the conditional expectation of a standard normal variable under the planted law, so $\mathbb P(|s_w|>\sqrt{2\log a})\le2/a$, and $\mathbb P(\log L_w(G)>a/2)\le e^{-a/2}$ because $L_w(G)$ has mean one.

Proposed lemma. For every $K$ there is $C(K)$ such that, uniformly in the number of directions, their geometry and the weights,
$$
\mathbb E\,\mathrm{Leb}\{w\le K\sqrt a:\ Y(w)\in[a-2,a+1)\}\le\frac{C(K)}{\sqrt a}.
$$

Sketch. By Fubini the two exceptional sets contribute at most $K\sqrt a\,(2/a+e^{-a/2})$. On their complement the path moves upward through the zone at speed at least $\sqrt a/(2K)-\sqrt{2\log a}-2/(K\sqrt a)$, so each passage takes time $O(K/\sqrt a)$. Missing step: a bound on the expected number of re-entries into the zone, which needs the exceptional events along the path and not only at fixed $w$.

Numerical check of $\sqrt a\,\mathbb E\,\mathrm{Leb}\{w\le3\sqrt a:\ Y(w)\in[a,a+1)\}$ for $a=4,8,16$: 60 random directions in dimension 8 with random weights gave 0.53, 0.59, 0.64; two tight clusters plus a diffuse background gave 0.49, 0.57, 0.62; 400 uniform directions in dimension 150 gave 0.39, 0.52, 0.59. One direction gives about 0.71.

## Meaning for the program

In the zone-occupation reduction of idea_dc6cf14ab94d, a violation of the conjectured tail can only come from $w>K\sqrt{\log\alpha}$. Call this late detection: the planted point has log-likelihood only $a=\log\alpha$ at signal energy $w^2/2\gg a$. There (F2) is weak, since it gives $w\Gamma_w\ge a/w\ll\sqrt a$, and the localization $|w^*-w|\le1$ of the maximizing scale has to be used. Uniform directions in high dimension show both effects: the path crosses the zone slowly, and the planted scale is rarely the maximizing one.

Two uses:

1. The open inequality of the program can be restricted to the late regime, with the early window treated as a lemma once the re-entry step is closed.
2. The stress tests of idea_57338934f2f7 should be aimed at priors whose planted log-likelihood stays below $a$ until $w\gg\sqrt a$ while $w\mapsto\log L_w$ has curvature close to $-1$ at its maximizer. A prior with late detection, sharp maximizer and slow crossing at the same time is what a counterexample would need.
