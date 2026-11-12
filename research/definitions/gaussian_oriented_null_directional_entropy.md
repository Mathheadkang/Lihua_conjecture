---
type: definition
title: Definition (oriented null directional entropy)
status: approved
source:
  kind: original
depends_on:
  - gaussian_multifactor_representation
  - gaussian_null_loading_coefficients
tags:
  - gaussian
  - multifactor
  - directional_entropy
  - oriented_loadings
---

## Definition

Use a [Gaussian multifactor representation](./gaussian_multifactor_representation.md) and its [Gaussian null loading coefficients](./gaussian_null_loading_coefficients.md) for the one-sided testing track. If $m_0>0$, an oriented null grouping is a partition $G_1,\ldots,G_H$ of $I_0$ into nonempty sets, with unit vectors $v_h\in\mathbb R^d$ such that
$$
a_i=r_i v_h\quad\text{for every }i\in G_h,\qquad r_i=\|a_i\|.
$$
Thus nonzero loadings in a group lie on the same oriented ray. Opposite nonzero directions require different groups. Zero loadings may be assigned to any group; if all null loadings are zero, one group with an arbitrary unit vector is permitted. Set
$$
m_{0,h}=|G_h|,\qquad \pi_h=\frac{m_{0,h}}m>0,\qquad \sum_{h=1}^H\pi_h=\pi_0,
$$
$$
\mathcal E_0=\sum_{h=1}^H\pi_h\log\frac1{\pi_h}.
$$
The oriented null directional entropy $\mathcal E_0$ is attached to the chosen grouping and representation; its masses are normalized by all tests, not just the true nulls. Here and below $\log$ is natural. The group projections $Y_h=v_h^{\mathsf T}Z$ are individually standard normal and need not be independent. If $m_0=0$, use the empty grouping $H=0$ and set $\mathcal E_0=0$; there are no group projections or positive group masses in that case.
