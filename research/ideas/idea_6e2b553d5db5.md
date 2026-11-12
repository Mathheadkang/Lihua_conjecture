---
type: idea
title: >-
  Radial truncation gives the sharp frozen-ray moment bound for every rank-two
  geometry
status: draft
idea_kind: approach
origin: agent
related_assets:
  - gaussian_frozen_ray_maximal_likelihood_ratio_conjecture
tags:
  - frozen-ray
  - rank-two
  - radial-truncation
  - search-obstruction
---

The round-two regular-polygon obstruction contains a proof step that extends to arbitrary deterministic probability weights and arbitrary Gaussian correlation matrices of rank at most two. Represent Z_i=<u_i,G> with unit u_i in R^2 and G~N_2(0,I_2), embedding rank one if necessary. Set R=||G||, M_i=exp((Z_i^+)^2/2), S=sum_i omega_i M_i, and a=sqrt(2 log c). Then Lambda<=S and
$$
E min(c,Lambda)<=sum_i omega_i E[M_i 1_{R<=a}]+c P(R>a)<=1/2+a/sqrt(2 pi)+1=sqrt(log c/pi)+3/2.
$$
The second inequality uses {R<=a} subset {|Z_i|<=a}, standard-normal marginal integration, and P(R>a)=exp(-a^2/2). Thus the sharp moment and consequently order bounds hold uniformly throughout this rank-at-most-two family, regardless of weight entropy or directional spacing. This is a candidate proof step and a search obstruction, not an approved result or a proof of the unrestricted target. The regular-polygon tail argument separately uses grid spacing; the displayed radial split alone proves no maximal-tail bound for arbitrary rank-two weights or directions, and gives no rank-uniform extension. Source: the Object and Checks sections of cand_gaussian_frozen_ray_maximal_likelihood_ratio_conjecture_r2_s3_regular_polygon_rank_two.
