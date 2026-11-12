---
type: lemma
title: Gaussian isoperimetric profile properties recorded by Bakry-Gentil-Ledoux
status: approved
depends_on: []
uses_definitions:
  - lib_bgl2015_gaussian_ou_profile
source:
  kind: paper
  paper_id: bakry_gentil_ledoux2015_harnack
  location: >-
    Author manuscript, Section 2, paragraph preceding Proposition 2.1,
    printed/PDF p. 8
tags:
  - gaussian
  - isoperimetry
  - analytic_input
---

## Statement

For the [Gaussian isoperimetric profile](../definitions/lib_bgl2015_gaussian_ou_profile.md), $I$ is continuous and concave on $[0,1]$, symmetric in the sense $I(p)=I(1-p)$, and twice differentiable on $(0,1)$ with
$$
I(p)I''(p)=-1.
$$
Its endpoint values are $I(0)=I(1)=0$ and
$$
\lim_{p\downarrow0}\frac{I(p)}{p\sqrt{2\log(1/p)}}=1,
$$
where $\log$ is natural.

## Source scope

This is a restatement of the elementary profile properties listed on source page 8, not a new BH estimate. The source paragraph records these properties without a separate proof. Independent checking remains pending.
