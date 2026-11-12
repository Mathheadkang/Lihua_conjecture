---
type: definition
title: >-
  Definition (quadratic mean penalty for a finite-dimensional tagged Gaussian
  population)
status: approved
source:
  kind: original
depends_on:
  - gaussian_bh_common_loading_tagged_population
tags:
  - gaussian_bh
  - quadratic_mean_penalty
  - deterministic_transport
---

## Definition

Fix $q\in(0,1/2)$, $\sigma\in(0,1)$ and a positive integer $d$. Specialize the [common-loading tagged Gaussian population](gaussian_bh_common_loading_tagged_population.md) to $\mathcal H=\mathbb R^d$, keeping its parameter space $\mathcal E$, unit directions, tags, deterministic laws $\mathcal P_1(\mathcal E)$, metric $c$, distance $W_1$, Gaussian randomness and full FDR $F_\pi$. In particular, a true tag $\ell=1$ requires $\theta\le0$, an alternative tag $\ell=0$ requires $\theta\ge0$, and an alternative-tagged zero belongs only to the analytic completion. Write $F(\pi)=F_\pi$ and define
$$
M_2(\pi)=\int_{\mathcal E}\theta^2\,\pi(d\theta,dv,d\ell),\qquad
\mathcal P_2(\mathcal E)=\{\pi\in\mathcal P_1(\mathcal E):M_2(\pi)<\infty\}.
$$
For $\eta>0$, the quadratic mean-penalized functional and its supremum are
$$
J_\eta(\pi)=F(\pi)-\eta M_2(\pi)\quad(\pi\in\mathcal P_2(\mathcal E)),\qquad
A_\eta=\sup_{\pi\in\mathcal P_2(\mathcal E)}J_\eta(\pi).
$$
The unpenalized completed supremum is
$$
W=\sup_{\pi\in\mathcal P_1(\mathcal E)}F(\pi).
$$
All these quantities are at the same fixed $q,\sigma,d$.

A deterministic Borel parameter transport is a map $T_\epsilon:\mathcal E\to\mathcal E$, fixed independently of all Gaussian randomness. For a law $\pi$, its pushforward $(T_\epsilon)_\#\pi$ assigns to each Borel set $B\subseteq\mathcal E$ the mass $\pi(T_\epsilon^{-1}(B))$. Write $\theta_\epsilon(x)$ for the mean coordinate of $T_\epsilon(x)$ and $\theta(x)$ for that of $x$. Membership of the image in $\mathcal E$ requires a unit output direction and the appropriate mean sign for its output tag. A transport that retains a true tag at zero cannot move its mean upward. Changes of tags do not constitute an upward motion of a retained true null; the transport comparisons below do not assume or authorize reclassification in an ordinary finite model.

A bounded mean displacement at speed $K<\infty$ means $K\ge0$ and
$$
|\theta_\epsilon(x)-\theta(x)|\le\epsilon K
\quad\text{for }\pi\text{-almost every }x,\qquad \epsilon>0.
$$
A fixed bounded mean velocity is a deterministic Borel function $b:\mathcal E\to\mathbb R$ with $|b|\le K$ almost everywhere under the law in question, used in a domain-preserving transport with mean $\theta_\epsilon=\theta+\epsilon b$ for all sufficiently small positive $\epsilon$. A pure direction transport retains both the mean and tag and changes only the unit direction. No differentiability or extremal property of $F$ is part of these definitions.
