---
type: lemma
title: Lei conditional leave-one-out FDP bound
status: approved
source:
  kind: paper
  paper_id: lei2026_gaussian_bh
  location: 'Lemma 4.1, equations (190)-(192), p. 59'
depends_on: []
uses_definitions:
  - conditional_pvalue_distributions
  - benjamini_hochberg_step_up
  - false_discovery_rate
tags:
  - benjamini_hochberg
  - conditional_independence
  - leave_one_out
  - upper_bounds
  - paper_source
---

## Statement

Let $P_1,\ldots,P_m$ have [conditional p-value distributions and independence](../definitions/conditional_pvalue_distributions.md) given $Z$, with fixed true-null set $\mathcal H_0$, and apply the [ordinary Benjamini-Hochberg step-up procedure](../definitions/benjamini_hochberg_step_up.md) at level $q\in(0,1)$. The false discovery proportion from the [false discovery rate](../definitions/false_discovery_rate.md) definition satisfies, for almost every $z$,
$$
\mathbb E(\operatorname{FDP}\mid Z=z)\leq\frac qm\sum_{i\in\mathcal H_0}\sup_{0<t\leq q}\frac{F_{i,z}(t)}t.
$$

## Proof from the source

Let $R$ be the BH rejection count and let $R_i\geq1$ be the count obtained after replacing $P_i$ by zero. The step-up rule gives the pointwise identity
$$
\frac{\mathbf1\{i\text{ is rejected}\}}{R\vee1}=\frac{\mathbf1\{P_i\leq qR_i/m\}}{R_i}.
$$
Conditional independence implies $P_i$ and $R_i$ are independent given $Z$. Therefore
$$
\mathbb E\left(\left.\frac{\mathbf1\{P_i\leq qR_i/m\}}{R_i}\right|Z=z\right)=\frac qm\mathbb E\left(\left.\frac{F_{i,z}(qR_i/m)}{qR_i/m}\right|Z=z\right)\leq\frac qm\sup_{0<t\leq q}\frac{F_{i,z}(t)}t.
$$
Sum over $i\in\mathcal H_0$. This is a source-based reconstruction of the displayed proof, pending independent verification. Conditional independence is an explicit hypothesis; joint Gaussianity alone does not provide independence after conditioning on an arbitrary scalar.
